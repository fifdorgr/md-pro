如果你的游戏不吃CPU，用View就比较好，符合标准Android操作方式，由系统决定刷新surface的时机。
但如果很不幸的，你做不到不让你的程序吃CPU，你就只好使用SurfaceView来强制刷新surface了，不然系统的UI进程很可能抢不过你那些吃CPU的线程。
当然其实不止这两种方法来刷新Surface的，这两种只是纯java应用比较常见的方法。
SurfaceView和View最本质的区别在于，surfaceView是在一个新起的单独线程中可以重新绘制画面而View必须在UI的主线程中更新画面。
那么在UI的主线程中更新画面可能会引发问题，比如你更新画面的时间过长，那么你的主UI线程会被你正在画的函数阻塞。那么将无法响应按键，触屏等消息。
当使用surfaceView由于是在新的线程中更新画面所以不会阻塞你的UI主线程。但这也带来了另外一个问题，就是事件同步。比如你触屏了一下，你需要surfaceView中 thread处理，一般就需要有一个event queue的设计来保存touch event，这会稍稍复杂一点，因为涉及到线程同步。
所以基于以上，根据游戏特点，一般分成两类。
1、被动更新画面的。比如棋类，这种用view就好了。因为画面的更新是依赖于 onTouch 来更新，可以直接使用 invalidate。 因为这种情况下，这一次Touch和下一次的Touch需要的时间比较长些，不会产生影响。
2、主动更新。比如一个人在一直跑动。这就需要一个单独的thread不停的重绘人的状态，避免阻塞main UI thread。所以显然view不合适，需要surfaceView来控制。