pkgname=kdeplasma-applets-playbar2
pkgver=2.5
pkgrel=1
pkgdesc="Mpris2 Client for Plasma5"
arch=('x86_64')
url="https://github.com/audoban/PlayBar2"
license=('GPL')
depends=('plasma-framework' 'plasma-workspace' 'kdeclarative' 'kglobalaccel'
    'kconfigwidgets' 'kxmlgui' 'kwindowsystem')
makedepends=('kdoctools' 'extra-cmake-modules')
source=("https://github.com/audoban/PlayBar2/archive/v${pkgver}.tar.gz")
md5sums=('2b3ed58d2f2d146ad245112d03f1070c')

prepare() {
    mkdir -p $srcdir/build
    cd playbar2-${pkgver}
    }

build() {
    cd $srcdir/build
    cmake -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DLIB_INSTALL_DIR=lib \
        -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        ../playbar2-${pkgver}
    make
}

package() {
    cd $srcdir/build
    make DESTDIR="$pkgdir" install
}
