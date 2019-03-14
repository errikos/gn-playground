# gn-playground
Getting started with GN and Ninja - this is a very simple project with a basic tree of a GN setup.

# What is GN?
GN is a meta-build system that generates build files for [Ninja](https://ninja-build.org/).
GN and Ninja are used to build Chromium. To find out more, check the [GN page at googlesource](https://gn.googlesource.com/gn/).

# Getting started
You will need [depot-tools](https://commondatastorage.googleapis.com/chrome-infra-docs/flat/depot_tools/docs/html/depot_tools_tutorial.html) in your `PATH`. It is a prerequisite for GN to checkout the repo using `gclient`.

To checkout:
```
mkdir gn-getting-started && cd gn-getting-started
gclient config \
        --name "gn-playground" \
        --unmanaged \
        https://github.com/errikos/gn-playground.git
gclient sync --with_branch_heads --with_tags
```

To build:
```
cd gn-playground
gn gen out/Default
ninja -C out/Default hello_world
```

You will then find the `executable` under `out/Default`.
