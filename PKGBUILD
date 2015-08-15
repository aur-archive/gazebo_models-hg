# Maintainer: Aris Synodinos <arissynod-gmail-com>
pkgname=gazebo_models-hg
pkgver=757.de9abaab0588
pkgrel=1
pkgdesc="Models in Gazebo define a physical entity with dynamic, kinematic, and visual properties."
arch=('any')
url="http://gazebosim.org/"
license=('Apache')
depends=('gazebo')
provides=('gazebo_models')
conflicts=('gazebo_models')
makedepends=('mercurial' 'cmake')
_hgroot=https://bitbucket.org/osrf
_hgrepo=gazebo_models
source=("$_hgrepo::hg+$_hgroot/$_hgrepo")
md5sums=('SKIP')


pkgver() {
  cd $srcdir/$_hgrepo
  echo $(hg identify -n | head -2 | tail -1).$(hg identify -i | head -2 | tail -1)
}

build() {
  mkdir -p "$srcdir/$_hgrepo"/build
  cd "$srcdir/$_hgrepo"/build
  cmake ..
}

package() {
  cd "$srcdir/$_hgrepo/build"
  make DESTDIR="$pkgdir/" install
}
