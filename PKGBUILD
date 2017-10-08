# Maintainer: Eric Vidal <eric@obarun.org>


pkgname=obarun-build
_commit=6405fcec2a7831cc5df7579e2772a1b1412eb48d # tag 0.1.2
pkgver=0.1.2
pkgrel=2
pkgdesc="Script for building package on clean environment with lxc container"
arch=(x86_64)
url="https://github.com/Obarun/obarun-build"
license=(ISC)
depends=('bash' 'lxc' 'iproute2' 'iptables' 'git' 'pacman' 'obarun-libs')
optdepends=('cgmanager-s6serv: cgmanager service for s6')
makedepends=('git')
backup=('etc/obarun/build.conf')
#source=("obarun-build::git+https://github.com/Obarun/obarun-build#tag=v${pkgver}")
#source=("git+https://github.com/Obarun/obarun-build#commit=$_commit")
source=("git+https://github.com/Obarun/obarun-build#branch=dev")
md5sums=('SKIP')
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal

pkgver() {
	cd "${pkgname}"
	
	git describe --tags | sed -e 's:-:+:g;s:^v::'
}

package() {
	cd "${pkgname}"

	make DESTDIR="$pkgdir" install
}
