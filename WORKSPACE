load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

RULES_KOTLIN_TAG = "legacy-1.4.0-rc3"
RULES_KOTLIN_SHA = "da0e6e1543fcc79e93d4d93c3333378f3bd5d29e82c1bc2518de0dbe048e6598"

http_archive(
    name = "io_bazel_rules_kotlin",
    urls = ["https://github.com/bazelbuild/rules_kotlin/releases/download/%s/rules_kotlin_release.tgz" % RULES_KOTLIN_TAG],
    sha256 = RULES_KOTLIN_SHA,
)

load("@io_bazel_rules_kotlin//kotlin:kotlin.bzl", "kotlin_repositories", "kt_register_toolchains")
kotlin_repositories() # if you want the default. Otherwise see custom kotlinc distribution below
kt_register_toolchains() # to use the default toolchain, otherwise see toolchains below

RULES_JVM_EXTERNAL_TAG = "3.2"
RULES_JVM_EXTERNAL_SHA = "82262ff4223c5fda6fb7ff8bd63db8131b51b413d26eb49e3131037e79e324af"

http_archive(
    name = "rules_jvm_external",
    sha256 = RULES_JVM_EXTERNAL_SHA,
    strip_prefix = "rules_jvm_external-%s" % RULES_JVM_EXTERNAL_TAG,
    url = "https://github.com/bazelbuild/rules_jvm_external/archive/%s.zip" % RULES_JVM_EXTERNAL_TAG,
)

load("@rules_jvm_external//:defs.bzl", "maven_install")

maven_install(
    artifacts = [
        "com.expedia:graphql-kotlin:1.0.0-RC5",
        "com.expedia:graphql-kotlin-schema-generator:1.0.0-RC5",
        "com.expedia:graphql-kotlin-federation:1.0.0-RC5",
        "com.graphql-java:graphql-java:13.0",
        "org.opentest4j:opentest4j:1.1.1",
        "org.apiguardian:apiguardian-api:1.0.0",
        "org.junit.platform:junit-platform-commons:1.4.2",
        "org.junit.jupiter:junit-jupiter-api:5.4.2",
        "org.junit.jupiter:junit-jupiter-params:5.4.2",
        "org.apache.logging.log4j:log4j-core:2.12.1",
    ],
    repositories = [
        "https://maven-central.storage.googleapis.com/repos/central/data/",
        "https://repo1.maven.org/maven2",
    ],
)

http_archive(
    name = "rules_pkg",
    url = "https://github.com/bazelbuild/rules_pkg/releases/download/0.2.4/rules_pkg-0.2.4.tar.gz",
    sha256 = "4ba8f4ab0ff85f2484287ab06c0d871dcb31cc54d439457d28fd4ae14b18450a",
)