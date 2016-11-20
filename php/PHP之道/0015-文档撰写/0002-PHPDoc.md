## PHPDoc 
PHPDoc 是注释 PHP 代码的非正式标准。它有*许多*不同的[标记]可以使用。完整的标记列表和范例可以查看 [PHPDoc 指南]。

如下是撰写类方法时的一种写法：

```php
<?php
/**
 * @author A Name <a.name@example.com>
 * @link http://www.phpdoc.org/docs/latest/index.html
 */
class DateTimeHelper
{
    /**
     * @param mixed $anything Anything that we can convert to a \DateTime object
     *
     * @throws \InvalidArgumentException
     *
     * @return \DateTime
     */
    public function dateTimeFromAnything($anything)
    {
        $type = gettype($anything);

        switch ($type) {
            // Some code that tries to return a \DateTime object
        }

        throw new \InvalidArgumentException(
            "Failed Converting param of type '{$type}' to DateTime object"
        );
    }

    /**
     * @param mixed $date Anything that we can convert to a \DateTime object
     *
     * @return void
     */
    public function printISO8601Date($date)
    {
        echo $this->dateTimeFromAnything($date)->format('c');
    }

    /**
     * @param mixed $date Anything that we can convert to a \DateTime object
     */
    public function printRFC2822Date($date)
    {
        echo $this->dateTimeFromAnything($date)->format('r');
    }
}
```

这个类的说明使用了 [@author] 和 [@link]标记， [@author] 标记是用來说明代码的作者，在多位开发者的情况下，可以同时列出好几位。其次 [@link] 标记用来提供网站链接，进一步说明代码和网站之间的关系。

在这个类中，第一个方法的 [@param] 标记，说明类型、名字和传入方法的参数。此外，[@return] 和 [@throws] 标记说明返回类型以及可能抛出的异常。

第二、第三个方法非常类似，和第一个方法一样使用一个 [@param] 标记。第二、和第三个方法之间关键差別在注释区块使用／排除 [@return] 标记。`@return void` 标记明确告诉我们没有返回值，而过去省略 `@return void` 声明也具有相同效果（沒有返回任何值）。


[标记]: http://www.phpdoc.org/docs/latest/references/phpdoc/tags/index.html
[PHPDoc 指南]: http://www.phpdoc.org/docs/latest/index.html
[@author]: http://www.phpdoc.org/docs/latest/references/phpdoc/tags/author.html
[@link]: http://www.phpdoc.org/docs/latest/references/phpdoc/tags/link.html
[@param]: http://www.phpdoc.org/docs/latest/references/phpdoc/tags/param.html
[@return]: http://www.phpdoc.org/docs/latest/references/phpdoc/tags/return.html
[@throws]: http://www.phpdoc.org/docs/latest/references/phpdoc/tags/throws.html
