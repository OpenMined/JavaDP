# Differential Privacy notebooks for JVM languages

## Environment

Notebooks in this folder have been tested with
[BeakerX](http://beakerx.com) (available via conda, pip, and docker).
They may also work in other jupyter environments.

We manage dependencies with Maven. You need libdifferentialprivacy-1.0.jar
in your local Maven repository (see below). Other dependencies should resolve
automatically.

## How to make libdifferentialprivacy-1.0.jar available:

1. Install [Bazel](https://docs.bazel.build/versions/master/install.html)
if you don't have it already.
2. Download and build the Java [differential-privacy library](https://github.com/google/differential-privacy):
```
git clone https://github.com/google/differential-privacy.git
cd java
bazel build ...
```
3. Copy `libdifferentialprivacy.jar` to your local Maven repository and
rename it to `libdifferentialprivacy-1.0.jar`:
```
mkdir -p ~/.m2/repository/com/google/privacy/differentialprivacy/libdifferentialprivacy/1.0/
cp bazel-bin/main/com/google/privacy/differentialprivacy/libdifferentialprivacy.jar ~/.m2/repository/com/google/privacy/differentialprivacy/libdifferentialprivacy/1.0/libdifferentialprivacy-1.0.jar
```
