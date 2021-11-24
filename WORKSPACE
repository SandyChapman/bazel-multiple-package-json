workspace(
    name = "multiple_package_json",
    managed_directories = {
        "@npm": ["app/node_modules"], # Removing this managed_directory, causes it not to be installed
        "@tools_npm": ["devtools/node_modules"],
    },
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "build_bazel_rules_nodejs",
    sha256 = "3635797a96c7bfcd0d265dacd722a07335e64d6ded9834af8d3f1b7ba5a25bba",
    urls = [
        "https://github.com/bazelbuild/rules_nodejs/releases/download/4.3.0/rules_nodejs-4.3.0.tar.gz",
        "https://storage.googleapis.com/bsci-thirdparty/github_com/bazelbuild/rules_nodejs/releases/download/4.3.0/rules_nodejs-4.3.0.tar.gz",
    ],
)
# The npm_install rule runs yarn anytime the package.json or package-lock.json file changes.
# It also extracts any Bazel rules distributed in an npm package.
load("@build_bazel_rules_nodejs//:index.bzl", "node_repositories", "npm_install")

npm_install(
    name = "npm",
    package_json = "//:app/package.json",
    package_lock_json = "//:app/package-lock.json",
    strict_visibility = False,
    symlink_node_modules = True,
)

npm_install(
    name = "tools_npm",
    package_json = "//:devtools/package.json",
    package_lock_json = "//:devtools/package-lock.json",
    strict_visibility = False,
    symlink_node_modules = True,
)
