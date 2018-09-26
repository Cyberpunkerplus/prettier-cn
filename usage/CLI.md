# CLI

你可以不带任何参数的使用 `CLI` 脚本来运行 `Prettier`去查看其选项。

如果你想格式化具体的某一文件，可以使用 `--write`。你可能为了以防万一，想在你提交代码之前做点什么。

```shell
prettier [opts] [filename ...]
```

实际操作中，它可能是这样：

```shell
prettier --single-quote --trailing-comma es5 --write "{app,__{tests,mocks}__}/**/*.js"
```