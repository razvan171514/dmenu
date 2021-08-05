# Maintainer: Your Name <youremail@domain.com>
pkgname=dmenu-razvan-git
pkgver=5.0.r8.4a59d30
pkgrel=1
epoch=
pkgdesc="Personal dmenu build. The list of patches is found in the github reopsitory on the file entitled list-of-patches.readme"
arch=(x86_64)
url="https://github.com/razvan171514/dmenu.git"
license=('MIT')
groups=()
depends=()
makedepends=(git make)
checkdepends=()
optdepends=()
provides=(dmenu)
conflicts=(dmenu)
replaces=()
backup=()
options=()
install=
changelog=
source=("git+$url")
noextract=()
md5sums=('SKIP')
validpgpkeys=()

pkgver() {
	cd dmenu
	printf "5.0.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
	cd dmenu
	make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
	cd dmenu
	mkdir -p ${pkgdir}/opt/${pkgname}
	cp -rf * ${pkgdir}/opt/${pkgname}
	make PREFIX=/usr DESTDIR="${pkgdir}" clean install
	install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
	install -Dm644 README "${pkgdir}/usr/share/doc/${pkgname}/README"
}
