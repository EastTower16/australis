workspace(name = "australis")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

git_repository(
     name = "jax",
     commit = "0324cac8882e3ea1b2148818ee2322e2b96696da",
     remote = "https://github.com/google/jax.git",
)

# To update TensorFlow to a new revision,
# a) update URL and strip_prefix to the new git commit hash
# b) get the sha256 hash of the commit by running:
#    curl -L https://github.com/tensorflow/tensorflow/archive/<git hash>.tar.gz | sha256sum
#    and update the sha256 with the result.
http_archive(
    name = "org_tensorflow",
    # sha256 = "bfd40279b247d2d0b0dc5c5a776b595c9d4979889dcf0529c85fe9f6ff7a5255",
    strip_prefix = "tensorflow-a3e2c692c18649329c4210cf8df2487d2028e267",
    urls = [
        "https://github.com/tensorflow/tensorflow/archive/a3e2c692c18649329c4210cf8df2487d2028e267.tar.gz",
    ],
)

# For development, one can use a local TF repository instead.
# local_repository(
#    name = "org_tensorflow",
#    path = "tensorflow",
# )

# Initialize TensorFlow's external dependencies.
load("@org_tensorflow//tensorflow:workspace3.bzl", "tf_workspace3")
tf_workspace3()
load("@org_tensorflow//tensorflow:workspace2.bzl", "tf_workspace2")
tf_workspace2()
load("@org_tensorflow//tensorflow:workspace1.bzl", "tf_workspace1")
tf_workspace1()
load("@org_tensorflow//tensorflow:workspace0.bzl", "tf_workspace0")
tf_workspace0()
