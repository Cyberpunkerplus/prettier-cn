# CLI

你可以不带任何参数的使用 CLI 脚本来运行 Prettier 去查看其选项。

如果你想格式化具体的某一文件，可以使用 `--write`。你可能为了以防万一，想在你提交代码之前做点什么。

```shell
prettier [opts] [filename ...]
```

实际操作中，它可能是这样：

```shell
prettier --single-quote --trailing-comma es5 --write "{app,__{tests,mocks}__}/**/*.js"
```

不要忘记 globs 周围的引号！这个引号是为了跨平台时候，确保 Prettier 扩展了 globs 而不是你的 shell，它使用了 [glob](https://github.com/isaacs/node-glob/blob/master/README.md#glob-primer) 语法模块。

Prettier CLI 会忽略本地的 `node_modules` 目录中文件，你可以使用 `--width-node-modules` 标记来退出此行为。

## --debug-check

---

如果你担心 Prettier 会改变你的代码正确性，可以在命令上加上 `--debug-check`。如果它检测到代码的正确性可能被更改，它会打印一个错误信息出来。请注意，`--write` 不能与 `--debug-check` 一起使用。

## --find-config-path 和 --config

---

如果你反复用 `prettier` 格式化同一个文件，你可能会因为其尝试查找[配置文件](https://prettier.io/docs/en/configuration.html)而产生一点性能问题。为了跳过这一步，你可能需要告诉 prettier 只查找一次配置文件，并在以后重复使用。

```shell
prettier --find-config-path ./my/file.js
./my/.prettierrc
```

你可以通过 `--config` 来提供配置文件目录：

```shell
prettier --config ./my/.prettierrc --write ./my/file.js
```

如果你的配置文件放在 Prettier 无法找到的位置，比如 `config/` 目录，你也可以通过 `--config` 来找到它。

如果你没有配置文件，或者配置文件已存在，但是你想忽略它，你可以通过 `--no-config` 来替代它。

## --ignore-path

---

路径下存在一个描述忽略文件模式的文件。默认情况下，prettier 会去查找 `./.prettierignore` 文件。

## --require-pragma

## --insert-pragma

## --list-different

## --no-config

不查找配置文件，默认使用。

## --config-precedence