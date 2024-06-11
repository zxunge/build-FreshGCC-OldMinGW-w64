Automatic 32-bit and 64-bit Windows build of fresher [gcc][] compiler and older [mingw-w64][] runtime.

Builds are linked statically to their dependencies and provide only static runtime libraries (libstdc++, libgomp, libwinpthread and others).

Download binary build as 7z archive from [latest release][] page.

To build binaries locally run `build.sh`. Make sure you have installed all necessary dependencies.

To build binaries using Docker, run:

    docker run -ti --rm -v `pwd`:/output -e OUTPUT=/output -w /mnt ubuntu:24.04
    apt update
    DEBIAN_FRONTEND=noninteractive apt install --no-install-recommends -y \
        ca-certificates libgmp-dev libmpc-dev libmpfr-dev libisl-dev xz-utils texinfo patch bzip2 p7zip cmake make curl m4 gcc g++
    /output/build.sh 32
    /output/build.sh 64
    exit

[gcc]: https://gcc.gnu.org/
[mingw-w64]: http://mingw-w64.org/
[latest release]: https://github.com/zxunge/build-FreshGCC-OldMinGW-w64/releases/latest
