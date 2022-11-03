<!--
 * @Descripition: A Readme about the introduction of bazel project template.
 * @Author: Franco Chen
 * @Date: 2022-11-03 11:34:41
 * @LastEditors: Franco Chen
 * @LastEditTime: 2022-11-03 13:12:06
-->
# workspace-template

## Prerequisites

OS: Linux 7 or 8

## How to
The first step is to download bazelisk.
```
wget -O /usr/bin/bazelisk https://github.com/bazelbuild/bazelisk/releases/download/v1.12.2/bazelisk-linux-amd64  \
  && chmod +x /usr/bin/bazelisk && ln -sf /usr/bin/bazelisk /usr/bin/bazel
```

Build all targes.
```
bazel build //...
```

File tree.
```
.
├── WORKSPACE
├── .bazelrc
├── .gitignore
├── BUILD
├── utils
│   └── BUILD.bazel
├── x
├── src
│   ├── BUILD.bazel
│   └── a
└── .bazelversion
```

Build a specific target or run (test.). 
```
bazel build //utils         # equal to: bazel build //utils:utils
bazel run //utils:test -- {args}
bazel test //...
```

The meaning of a target label.
whole: @workspace-template//utils:a
pattern: @{WORKSPACE_NAME,omitempty}//{relative_unix_path}:{target_name}

## About importing external libraries.
@francoccc will complement it.