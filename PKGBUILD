pkgname=projectinvaders-git
pkgver=0.1
pkgrel=1
pkgdesc="Project Invaders is a little space shoot game. It is based on the old-fashion Space Invaders game."
arch=(any)
url="https://github.com/psilentearth/Project-Invaders"
license=('GPL3')
groups=
provides=
depends=('sdl' 'sdl_image' 'sdl_ttf')
optdepends=
makedepends=('git')
conflicts=
replaces=
backup=
install=
source=()
md5sums=()
_gitroot="git://github.com/psilentearth/Project-Invaders.git"
_gitname="Project-Invaders"

build(){
	if [[ -d $_gitname ]] ; then
		git pull origin || return 1 
	else
	    	git clone $_gitroot || return 1
	fi
	cd $_gitname

	chmod +x configure	
	./configure --prefix=/usr
	make || return 1
}

package(){
	cd $_gitname
	make DESTDIR="$pkgdir/" install 
}
