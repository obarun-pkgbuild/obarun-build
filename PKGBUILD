# Maintainer: Eric Vidal <eric@obarun.org>


pkgname=obarun-build
#_commit=14161f60a676445b1161faeb0adb5d6882f8015a # tag 0.1.5 fix update of pacman database
pkgver=0.1.9
pkgrel=1
pkgdesc="Script for building package on clean environment with lxc container"
arch=(x86_64)
url="https://github.com/Obarun/obarun-build"
license=(ISC)
depends=('bash' 'lxc' 'iproute2' 'iptables' 'git' 'pacman' 'obarun-libs' 'dnsmasq' 'cgmanager')
makedepends=('git')
backup=('etc/obarun/build.conf')
source=("obarun-build::git+https://github.com/Obarun/obarun-build#tag=v${pkgver}")
#source=("git+https://github.com/Obarun/obarun-build#commit=$_commit")
#source=("git+https://github.com/Obarun/obarun-build#branch=dev")
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
