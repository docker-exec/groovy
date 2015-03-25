# Docker Exec Image: Groovy

A Dockerfile describing an container capable of executing Groovy source files.

# Build

```sh
git clone https://github.com/docker-exec/groovy.git
docker build -t dexec/groovy .
```

# Usage

In a directory containing a script e.g. foo.groovy, run:

```sh
docker run -t --rm \
    -v $(pwd -P)/foo.groovy:/tmp/dexec/build/foo.groovy \
    dexec/groovy foo.groovy
```

## Passing arguments to the script

Arguments can be passed to the script using any of the following forms:

```
-a argument
--arg argument
--arg=argument
```

Each argument passed must be prefixed in this way, e.g.

```sh
docker run -t --rm \
    -v $(pwd -P)/foo.groovy:/tmp/dexec/build/foo.groovy \
    dexec/groovy foo.groovy \
    --arg='hello world' \
    --arg=foo \
    --arg=bar
```
