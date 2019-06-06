# Bug Description

I discovered this bug while using yarn on a repo with workspaces. I have prettier pinned to an older version `1.14.2` as a dev dependency of the root package. When I add a package that uses a newer version of prettier as a dependency of one of the workspaces, the `node_modules/.bin/prettier` file symlinks to the newer version.

## Steps to reproduce

```
$ yarn prettier --version # 1.14.2
$ yarn workspace some-package add @vue/component-compiler-utils
$ yarn prettier --version # 1.16.3
```
