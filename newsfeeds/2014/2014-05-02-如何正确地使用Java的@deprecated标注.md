如何正确地使用Java的@deprecated标注
------------------------------- 

没有什么事情比看到一个没有任何说明的@deprecated标注更让人愤怒的事情了。这种做法只能让人困惑，我到底还要不要用这个已经‘废弃’的方法？如果开发者不希望某个方法再被人用的话，就要好好地为@deprecated标注写说明。这篇文章就讨论了正确地使用@deprecated 标注需要遵守的一些规则。

>什么是使用@Deprecated标注的规则?

## Rule #1: do Javadoc how not to

每当你弃用某方法时，创建JavaDoc告诉其他程序员如何不再使用这个方法。不要只说“这个方法废弃了，不要用它”。因为这就是废弃标注和JavaDoc中@deprecated的字面意义，完全没有必要再重复一遍。Java开发人员作为目标受众，都知道deprecation的意思。

命名新的方法，取代旧有的。(使用@link标注!)这可能还不够，新的方法对应的文档将解释如何使用它。不要在JavaDoc中重复（其字面意义），文档也应遵从DRY原则。另一方面你可能想要描述怎样替换掉旧方法的调用，你可以就重构的细节给出提示。

## Rule #2: do not Javadoc how to

移除过时的JavaDoc文档。有些人可能争辩：维护遗留代码的用户可能还会需要这些文档。事实上，他们使用的是旧版本库中的旧版本方法。旧版本的文档仍旧存在那里，像被刻在石头上（更确切的说是刻在资源仓库的某个版本上）。含有被废弃掉的方法的实际版本不应包含过时的描述文档，那会鼓励程序员去继续使用。对于废弃的方法，只有一种用法：不去用。JavaDoc应该被实时描述，如同rule#1所述。

## Rule #3: 不要在JavaDoc中解释

不要在JavaDoc中解释为什么方法被废弃了。你是一个可靠的的开发，这是你的决定，你的选择，其他人只能忍着。如果愿意，可以写一篇博客记录这次调整的决策背景。这可能有帮助，但它不应被写在JavaDoc中。

JavaDoc的Deprecated API专用来讲解如何不再使用。
重点是如何(how)。而不是“为什么不再使用它(why)”。

## Rule #4: do deprecate

如果你觉得需要弃用一方法，那就去做吧！如果你害怕你的用户，或不想因你废弃掉一些方法导致你用户体验更加痛苦，这个决定将让你自己痛苦。尽你所能去让API维持长久的稳定。但如果有需要被废弃的：立刻扔掉它。不要因“为何当初设计API时没有考虑到未来的变动”而感到愧疚。没有人能完美的预见未来。毕竟，如果你知道未来，生活就无趣了。

原文链接： javacodegeeks   
翻译： ImportNew.com - dust_jead  
译文链接： http://www.importnew.com/10113.html  