workspace(
    name = "repro",
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

rules_go_version = "0.29.0"

http_archive(
    name = "io_bazel_rules_go",
    sha256 = "2b1641428dff9018f9e85c0384f03ec6c10660d935b750e3fa1492a281a53b0f",
    url = "https://github.com/bazelbuild/rules_go/releases/download/v{}/rules_go-v{}.zip"
        .format(rules_go_version, rules_go_version),
)

load("@io_bazel_rules_go//go:deps.bzl", "go_register_toolchains", "go_rules_dependencies")

go_rules_dependencies()

go_register_toolchains(go_version = "1.18")

rules_rust_version = "0.9.0"

http_archive(
    name = "rules_rust",
    sha256 = "6bfe75125e74155955d8a9854a8811365e6c0f3d33ed700bc17f39e32522c822",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_rust/releases/download/{}/rules_rust-v{}.tar.gz".format(
            rules_rust_version,
            rules_rust_version,
        ),
        "https://github.com/bazelbuild/rules_rust/releases/download/{}/rules_rust-v{}.tar.gz".format(
            rules_rust_version,
            rules_rust_version,
        ),
    ],
)

load("@rules_rust//rust:repositories.bzl", "rules_rust_dependencies", "rust_register_toolchains")

rules_rust_dependencies()

rust_register_toolchains(
    edition = "2021",
)
