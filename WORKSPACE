workspace(name = "bazel_remote_apis")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "com_google_protobuf",
    sha256 = "f6ac7f4b735f9b7c50e45cff845e787eeb4acde9a8955542c9f1f7f95ada876f",
    strip_prefix = "protobuf-23.3",
    urls = ["https://github.com/protocolbuffers/protobuf/archive/v23.3.zip"],
)

load("@com_google_protobuf//:protobuf_deps.bzl", "protobuf_deps")

protobuf_deps()

http_archive(
    name = "com_google_googleapis",
    sha256 = "92f6785379d6cb44f450fee28011f311c3b12b87cddca37b24cf79170530cc9b",
    strip_prefix = "googleapis-5511d65673a3efff6f63a2614b2090e9ef768b12",
    urls = [
        "https://github.com/googleapis/googleapis/archive/5511d65673a3efff6f63a2614b2090e9ef768b12.zip",
    ],
)

load(
    "@com_google_googleapis//:repository_rules.bzl",
    "switched_rules_by_language",
)

# Consumers should override this with their own language-specific requirements.
switched_rules_by_language(
    name = "com_google_googleapis_imports",
    cc = False,
    csharp = False,
    gapic = False,
    go = False,
    grpc = False,
    java = False,
    nodejs = False,
    php = False,
    python = False,
    ruby = False,
)
