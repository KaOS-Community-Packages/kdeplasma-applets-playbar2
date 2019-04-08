pkgname=kdeplasma-applets-playbar2
pkgver=2.5
_pkgver=fix-qtquick
pkgrel=2
pkgdesc="Mpris2 Client for Plasma5"
arch=('x86_64')
url="https://github.com/audoban/PlayBar2"
license=('GPL')
depends=('plasma-framework' 'plasma-workspace' 'kdeclarative' 'kglobalaccel'
    'kconfigwidgets' 'kxmlgui' 'kwindowsystem')
makedepends=('kdoctools' 'extra-cmake-modules')
source=("https://github.com/dkadioglu/PlayBar2/archive/fix-qtquick.zip")
md5sums=('52ca4bb27632429f971eef224e9993da')

prepare() {
    mkdir -p $srcdir/build
    cd PlayBar2-${_pkgver}
    }

build() {
    cd $srcdir/build
    cmake -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DLIB_INSTALL_DIR=lib \
        -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        ../PlayBar2-${_pkgver}
    make
}

package() {
    cd $srcdir/build
    make DESTDIR="$pkgdir" install
}

