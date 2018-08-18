# 什么是 Prettier

Prettier 是一个固定的代码格式化程序，它支持以下类型：

+ JavaScript, including ES2017
+ JSX
+ Flow
+ TypeScript
+ CSS, Less, and SCSS
+ JSON
+ GraphQL
+ Markdown, including GFM
+ YAML

它会移除掉原有代码的样式，并输出遵循统一样式的代码。Prettier 会参考每行的代码长度，并重新打印它。

如下代码所示：

```js
foo(arg1, arg2, arg3, arg4);
```

因为它正好一行，所以它将保留原样。然而，当我们在这种情况下运行：

```js
foo(reallyLongArg(), omgSoManyParameters(), IShouldRefactorThis(), isThereSeriouslyAnotherOne());
```

显然，我们以前调用函数的格式消失了，因为这条语句实在太长了。Prettier 会针对代码去做一些复杂操作，并重新打印它。

```js
foo(
    reallyLongArg(),
    omgSoManyParameters(),
    IShouldRefactorThis(),
    isThereSeriouslyAnotherOne()
);
```

Prettier 通过解析你的代码库，强制使用统一的风格的代码，因为它会移除掉原有代码样式（这并不会影响 AST 的代码样式）。它会采用自己的规则来重新输出解析后的 AST，该规则将考虑每行最大长度，当必要的时候，会进行换行。