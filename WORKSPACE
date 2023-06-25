workspace(name = "australis")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

git_repository(
     name = "jax",
     commit = "c3e242700872c2f7e098a07f3911ee6d2de8132c",
     remote = "https://github.com/google/jax.git",
)

# To update TensorFlow to a new revision,
# a) update URL and strip_prefix to the new git commit hash
# b) get the sha256 hash of the commit by running:
#    curl -L https://github.com/tensorflow/tensorflow/archive/<git hash>.tar.gz | sha256sum
#    and update the sha256 with the result.
http_archive(
    name = "xla",
    sha256 = "4ec16aff3862c5a243db956ce558d7a62eb79f5e20747b0e80802a3b0d12e419",
    strip_prefix = "xla-12de6ec958419b57be248d0acd2d9f757e71748c",
    urls = [
        "https://github.com/openxla/xla/archive/12de6ec958419b57be248d0acd2d9f757e71748c.tar.gz",
    ],
)
# For development, one can use a local TF repository instead.
# local_repository(
#    name = "org_tensorflow",
#    path = "tensorflow",
# )

load("@xla//:workspace4.bzl", "xla_workspace4")
xla_workspace4()

load("@xla//:workspace3.bzl", "xla_workspace3")
xla_workspace3()

load("@xla//:workspace2.bzl", "xla_workspace2")
xla_workspace2()

load("@xla//:workspace1.bzl", "xla_workspace1")
xla_workspace1()

load("@xla//:workspace0.bzl", "xla_workspace0")
xla_workspace0()

load("@jax//third_party/flatbuffers:workspace.bzl", flatbuffers = "repo")
flatbuffers()