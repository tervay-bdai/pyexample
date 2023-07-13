load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "bazel_skylib",
    sha256 = "66ffd9315665bfaafc96b52278f57c7e2dd09f5ede279ea6d39b2be471e7e3aa",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-skylib/releases/download/1.4.2/bazel-skylib-1.4.2.tar.gz",
        "https://github.com/bazelbuild/bazel-skylib/releases/download/1.4.2/bazel-skylib-1.4.2.tar.gz",
    ],
)

load("@bazel_skylib//:workspace.bzl", "bazel_skylib_workspace")

bazel_skylib_workspace()

RULES_PYTHON_VERSION = "0.24.0"

http_archive(
    name = "rules_python",
    sha256 = "0a8003b044294d7840ac7d9d73eef05d6ceb682d7516781a4ec62eeb34702578",
    strip_prefix = "rules_python-{}".format(RULES_PYTHON_VERSION),
    url = "https://github.com/bazelbuild/rules_python/releases/download/{0}/rules_python-{0}.tar.gz".format(RULES_PYTHON_VERSION),
)

load("@rules_python//python:repositories.bzl", "py_repositories", "python_register_toolchains")
load("@rules_python//python:pip.bzl", "pip_parse")

py_repositories()

python_register_toolchains(
    name = "python_scripts",
    python_version = "3.9",
)

load("@python_scripts//:defs.bzl", "interpreter")

pip_parse(
    name = "python_scripts_deps",
    python_interpreter_target = interpreter,
    requirements_lock = "//requirements:scripts.requirements.lock.txt",
)

load("@python_scripts_deps//:requirements.bzl", "install_deps")

install_deps()
