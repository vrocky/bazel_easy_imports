# Bazel Easy Imports

Bazel Easy Imports is a Bazel workspace designed to simplify the process of importing and using Bazel build rules.

This project includes commonly used rules such as:

- `bazel_skylib`
- `rules_pkg`
- `rules_python`
- `rules_jvm_external`

## Getting Started

This project is a Bazel workspace. To get started, you need to have Bazel installed on your machine. You can find instructions on how to do this [here](https://docs.bazel.build/versions/main/install.html).

Once Bazel is installed, you can use these rules in your own Bazel workspace by adding the following to your WORKSPACE file:

```python
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

git_repository(
    name = "bazel_easy_imports",
    remote = "https://github.com/<username>/bazel-easy-imports.git",  # Replace with your repository URL.
    commit = "<commit>",  # Replace with the commit you want to point to.
)
```

And then loading the desired rules in your BUILD files, for example:

```
load("@bazel_easy_imports//:imports.bzl", "rules_python")
rules_python()
```

## Contents

The project is structured as follows:

```
bazel-easy-imports/
    imports.bzl  # The main file where the build rules are defined.
    .git/
        # Standard git repository files.
    internal/
        # Internal .bzl files for each build rule.
        bazel_skylib.bzl
        rules_pkg.bzl
        rules_python.bzl
```


Each .bzl file inside the internal/ directory contains an init function which sets up the corresponding rule.


License
This project is open source under the Apache License 2.0. See the LICENSE file for more information.

```
Let me know if there's anything else I can help you with
```