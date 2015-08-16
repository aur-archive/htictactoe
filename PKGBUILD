# Maintainer: Arch Haskell Team <arch-haskell@haskell.org>
_hkgname=HTicTacToe
pkgname=htictactoe
pkgver=0.2
pkgrel=2
pkgdesc="An SDL tic-tac-toe game."
url="http://hackage.haskell.org/package/${_hkgname}"
license=('custom:MIT')
arch=('i686' 'x86_64')
makedepends=('ghc' 'haskell-sdl' 'haskell-sdl-image' 'haskell-sdl-ttf' 'haskell-array=0.3.0.1' 'haskell-mtl' 'haskell-random=1.0.0.2')
depends=('gmp')
options=('strip')
source=(http://hackage.haskell.org/packages/archive/${_hkgname}/${pkgver}/${_hkgname}-${pkgver}.tar.gz)
build() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup configure --prefix=/usr --docdir=/usr/share/doc/${pkgname} -O
    runhaskell Setup build
}
package() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup copy --destdir=${pkgdir}
    install -D -m644 LICENSE ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE
    rm -f ${pkgdir}/usr/share/doc/${pkgname}/LICENSE
}
md5sums=('43a67e4fb128ad06637cde6f8d659121')
