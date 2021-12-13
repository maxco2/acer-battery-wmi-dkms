# Maintainer: maxco2 <maxc@stateoftheart.pw>
_pkgbase=acer-battery-wmi
pkgname=${_pkgbase}
pkgver=0.1
pkgrel=1
pkgdesc="A kernel module for acer battery wmi (DKMS version)"
# url="https://github.com/mtorromeo/r8168"
license=("GPL")
arch=('i686' 'x86_64')
depends=('glibc' 'dkms')
makedepends=('git')
# conflicts=("${pkgname}")
source=("git+https://github.com/maxco2/acer-battery-wmi.git"
        "dkms.conf")

install=acer-battery-wmi.install

package() {
	install -Dm644 dkms.conf "${pkgdir}/usr/src/${_pkgbase}-${pkgver}/dkms.conf"

	sed -e "s/@PKGNAME@/${_pkgbase}/g" \
		-e "s/@PKGVER@/${pkgver}/g" \
		-i "${pkgdir}/usr/src/${_pkgbase}-${pkgver}/dkms.conf"

    # install -dm755 "${pkgdir}"/usr/lib/modprobe.d
    # install -Dm644 acer-battery-wmi.modprobe "${pkgdir}"/usr/lib/modprobe.d/acer-battery-wmi.conf
	cd "${pkgname}"
	cp -dr --no-preserve='ownership' src "${pkgdir}/usr/src/${_pkgbase}-${pkgver}/src"
}
sha256sums=('SKIP'
            'SKIP')
