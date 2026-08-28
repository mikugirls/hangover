FROM menci/archlinuxarm:base-devel

ARG LLVMMINGW_DATE=20260505
ARG LLVMMINGW_NAME=llvm-mingw-$LLVMMINGW_DATE-ucrt-ubuntu-22.04-aarch64

RUN sed -i \
    -e 's/^CheckSpace/#CheckSpace/' \
    -e 's/^[[:space:]]*DownloadUser[[:space:]]*=/#&/' \
    -e '/^\[options\]/a DisableSandbox' \
    /etc/pacman.conf && \
    pacman -Syu --noconfirm \
    autoconf \
    automake \
    bison \
    ca-certificates \
    clang \
    cmake \
    cups \
    curl \
    dbus \
    flex \
    fontconfig \
    freetype2 \
    gcc \
    gettext \
    git \
    glib2 \
    glu \
    gnutls \
    gst-plugins-base \
    gst-plugins-base-libs \
    gtk-doc \
    krb5 \
    less \
    libepoxy \
    libglvnd \
    libgphoto2 \
    libpcap \
    libpulse \
    libtool \
    libunwind \
    libusb \
    libx11 \
    libxcomposite \
    libxcursor \
    libxext \
    libxfixes \
    libxi \
    libxinerama \
    libxkbcommon \
    libxrandr \
    libxrender \
    libxshmfence \
    libxt \
    libxxf86vm \
    lld \
    llvm \
    make \
    mesa \
    nano \
    nasm \
    ncurses \
    ninja \
    openldap \
    openssl \
    patch \
    perl \
    pkgconf \
    python \
    python-setuptools \
    sane \
    sdl2-compat \
    screen \
    systemd-libs \
    tar \
    unixodbc \
    v4l-utils \
    vulkan-headers \
    vulkan-icd-loader \
    wayland \
    wget \
    zstd && \
    pacman -Scc --noconfirm

RUN cd /opt; wget https://github.com/mstorsjo/llvm-mingw/releases/download/$LLVMMINGW_DATE/$LLVMMINGW_NAME.tar.xz; tar -xJf $LLVMMINGW_NAME.tar.xz; rm *.tar.xz
