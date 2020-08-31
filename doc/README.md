# Differential Privacy notebooks for JVM languages

## Local environment setup

Notebooks in this folder have been tested with
[BeakerX](http://beakerx.com) (available via conda, pip, and docker).
They may also work in other jupyter environments.

We manage dependencies with Maven. You need libdifferentialprivacy-1.0.jar
in your local Maven repository (see below). Other dependencies should resolve
automatically.

## How to make libdifferentialprivacy-1.0.jar available:

1. Make sure you have [Maven](https://maven.apache.org/) and [Bazel](https://docs.bazel.build/versions/master/install.html) installed.
2. Download and build the Java [differential-privacy library](https://github.com/google/differential-privacy):
```
git clone https://github.com/google/differential-privacy.git
cd java
bazel build "..."
```
3. Install `libdifferentialprivacy.jar` in your local Maven repository:
```
mvn install:install-file -Dfile=bazel-bin/main/com/google/privacy/differentialprivacy/libdifferentialprivacy.jar -DgroupId=com.google.privacy.differentialprivacy -DartifactId=libdifferentialprivacy -Dversion=1.0 -Dpackaging=jar
```
