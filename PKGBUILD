# Maintainer: Eric Vidal <eric@obarun.org>


pkgname=obarun-build
_commit=c7167b56b247c76426234937236cd54d1e8a1330 # tag 0.1.4 warm if bridge is not created
pkgver=0.1.4+2+gc7167b5
pkgrel=3
pkgdesc="Script for building package on clean environment with lxc container"
arch=(x86_64)
url="https://github.com/Obarun/obarun-build"
license=(ISC)
depends=('bash' 'lxc' 'iproute2' 'iptables' 'git' 'pacman' 'obarun-libs' 'dnsmasq' 'cgmanager')
optdepends=('cgmanager-s6serv: cgmanager service for s6')
makedepends=('git')
backup=('etc/obarun/build.conf')
#source=("obarun-build::git+https://github.com/Obarun/obarun-build#tag=v${pkgver}")
source=("git+https://github.com/Obarun/obarun-build#commit=$_commit")
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
