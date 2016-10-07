# Maintainer: William Grieshaber <me@zee.li>
# Contributor: Joao Cordeiro <jlcordeiro at gmail dot com>
# Contributor: Joekey joekey1@gmail.com
pkgname=trigger
pkgver=0.6.4 
pkgrel=1
pkgdesc="Free OpenGL rally car racing game"
arch=('i686' 'x86_64')
url="http://sourceforge.net/projects/trigger-rally/"
license=('GPL2')
conflicts=()
depends=('sdl_image' 'physfs' 'freeglut' 'freealut' 'glu' xdg-utils)
makedepends=('ftjam' 'glew' 'sdl_mixer')
install=trigger.install
source=(http://sourceforge.net/projects/trigger-rally/files/$pkgname-$pkgver/$pkgname-rally-$pkgver.tar.gz
        https://sourceforge.net/p/trigger-rally/discussion/527953/thread/e1cde947/ac20/attachment/hiscore1.h.patch
        $pkgname.png
        $pkgname.desktop)
sha512sums=('047b4e91774b5d866bc15532047a141b8074ea67c582298c41233149589ad261d8d7f68901b93c99484b423fa83d1f3e57ef9f19bd5e31851a98e072a1d1b4df'
            '57714f819ec8fdf3b3ba4b94c0889a40b1ae8feb7d7eb24e1efb431c9591e342a52d47e663cf281424f79022e61e985dc7716a71a64e9501295176e758475653'
            '09867405b809e1856d222949dcc81f897eecb87e270cceaca8fd33745ce38bfb52b0a0cb6b12fe90cd844ade92f77b79f803ed8d7c65b59af6f58a89d176f191'
            'c60d02949131eb1e8b42acdf55ebf3b8290d24bebe89bb12e54001be0f78146e1ad0ae8955d480f484134174dd16975deaa37e2f3880b2972e9bdd71763bdacb')

build() {

    cd $pkgname-rally-$pkgver 
    patch -p 0 -i ../hiscore1.h.patch
    cd src 
    make

}

package() {
    cd $pkgname-rally-$pkgver/src/
    make DESTDIR=$pkgdir install 
}
# vim:set ts=2 sw=2 et:
