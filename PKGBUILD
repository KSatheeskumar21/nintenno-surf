# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Your Name <k.sath214@gmail.com>
pkgname=nintenno-surf
pkgver=2.1.r93.78addef
pkgrel=1
pkgdesc="My Personal surf build at https://github.com/KSatheeskumar21/nintenno-surf"
arch=(x86_64)
url="https://github.com/KSatheeskumar21/nintenno-surf"
license=('MIT')
groups=()
depends=(nerd-fonts-source-code-pro ttf-jetbrains-mono ttf-joypixels)
makedepends=(git make)
checkdepends=()
optdepends=()
provides=(surf)
conflicts=()
replaces=(surf)
backup=()
options=()
install=${pkgname}.install
changelog=
source=("git+$url")
noextract=()
md5sums=('SKIP')
validpgpkeys=()

prepare() {
	cd "${_pkgname}"
	printf "2.1.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
	cd nintenno-surf
	make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
	cd nintenno-surf
	mkdir -p ${pkgdir}/opt/${pkgname}
	cp -rf * ${pkgdir}/opt/${pkgname}
	sudo make PREFIX=/usr DESTIR="$pkgdir" install
	install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/nintenno-surf/LICENSE"
	install -Dm644 README "${pkgdir}/usr/share/doc/nintenno-surf/README"
}
