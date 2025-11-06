# proton-sdk-llvm-mingw

Repository to build and host [Proton's SDK](https://gitlab.steamos.cloud/proton/sniper/sdk) docker images with **llvm-mingw support**, recently added to the project's Dockerfiles.

This project simply automates building the SDK from Proton's provided [Dockerfile for llvm-mingw](https://github.com/ValveSoftware/Proton/blob/fefb4d2a9d81850f0fd4d167570b7ab1e1d2bf55/docker/proton-llvm.Dockerfile.in) from GitHub CI to then push it to a [DockerHub image](https://hub.docker.com/r/sherrydck/proton-sdk-llvm-mingw), making building Proton with it as easy as replacing SDK link.

You can find every tag's build at the repository's [Actions tab](https://github.com/NelloKudo/proton-sdk-llvm/actions/workflows/dockerhub.yml).

## Usage

Edit Proton's `Makefile.in` and replace your `STEAMRT_IMAGE` link with:
```
STEAMRT_IMAGE ?= sherrydck/proton-sdk-llvm-mingw:proton-sdk-llvm-mingw-20250910
```

Alternatively, you can use `sherrydck/proton-sdk-llvm-mingw:latest` to always get the latest tag.

## Compatibility

Only tested with upstream Proton bleeding-edge, since downstream Protons might need some additional flag change/update.