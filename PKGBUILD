# Maintainer: Eric Vidal <eric@obarun.org>


pkgname=obarun-build
_commit=1ad9353e2c70379964499f20170dd236bab46d39 # tag 0.1.0
pkgver=0.1.0
pkgrel=1
pkgdesc=" Script for building package on clean environment with lxc container"
arch=(x86_64)
url="https://github.com/Obarun/obarun-build"
license=('BEERWARE')
depends=('bash' 'lxc' 'iproute2' 'iptables' 'git' 'pacman' 'obarun-libs')
optdepends=('cgmanager-s6serv: cgmanager service for s6')
makedepends=('git')
backup=('etc/obarun/build.conf')
#source=("obarun-build::git+https://github.com/Obarun/obarun-build#tag=v${pkgver}")
source=("git+https://github.com/Obarun/obarun-build#commit=$_commit")
md5sums=('SKIP')
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal

package() {
	cd "$srcdir/$pkgname"
	
	install -Dm 0755 "obarun-build.in" "$pkgdir/usr/bin/obarun-build"
	install -Dm 0755 "build.sh" "$pkgdir/usr/lib/obarun/build.sh"
	install -Dm 0644 "build.conf" "$pkgdir/etc/obarun/build.conf"
	
	install -dm 0755 "$pkgdir/usr/lib/obarun/build/"
	for file in build/{manage.sh,network.sh,util.sh};do
		install -Dm 0755 "${file}" "$pkgdir/usr/lib/obarun/build/"
	done
	
	install -dm 0755 "$pkgdir/usr/share/obarun/obarun-build/templates"
	for file in templates/{create.conf,pkglist_*,start.conf,makepkg.conf,pacman.conf}; do
		install -Dm 0644 "${file}" "$pkgdir/usr/share/obarun/obarun-build/templates"
	done
	
	install -Dm 0755 "templates/create" "$pkgdir/usr/share/obarun/obarun-build/templates"
	
	install -dm 0755 "$pkgdir/usr/share/licenses/obarun-build/"
	install -Dm 0644 "LICENSE" "$pkgdir/usr/share/licenses/obarun-build/LICENSE"
	#install -Dm 0644 "PKGBUILD" "$pkgdir/var/lib/obarun/obarun-build/update_package/PKGBUILD"
}
