FROM foundationfedora43

ARG LLVMMINGW_NAME=llvm-mingw-20260505-ucrt-ubuntu-22.04-aarch64
ENV LLVMMINGW_PATH="/opt/$LLVMMINGW_NAME/bin"

RUN rm -rf /opt/wine /opt/package /opt/artifacts; mkdir -p /opt/wine /opt/package /opt/artifacts
COPY ./ /opt/wine/
RUN ls -la /opt/wine/
ENV PATH="$LLVMMINGW_PATH:$PATH"
RUN cd /opt/wine; ./configure --prefix=/usr --libdir=/usr/lib --with-mingw=clang --enable-archs=arm64ec,aarch64,i386 --enable-tools --disable-tests
RUN cd /opt/wine; make -j `nproc`
RUN cd /opt/wine; make DESTDIR=/opt/package install
RUN tar -C /opt/package --zstd -cf /opt/artifacts/hangover-wine_HOVERSION_fedora43_aarch64.tar.zst .
