# Maintainer: David Runge <dvzrv@archlinux.org>
# Contributor: Pierre Schmitz <pierre@archlinux.de>
# Contributor: Gerardo Exequiel Pozzi <djgera@archlinux.org>

pkgname=arch-iso
pkgver=82
pkgrel=1
pkgdesc="Tools for creating Arch Linux live and install iso images"
arch=(any)
url="https://github.com/AcreetionOS-Linux/arch-iso"
license=(GPL-3.0-or-later)
depends=(
  arch-install-scripts
  bash
  dosfstools
  e2fsprogs
  erofs-utils
  libarchive
  libisoburn
  mtools
  squashfs-tools
)
makedepends=(
  git
  python-docutils
)
checkdepends=(shellcheck)
optdepends=(
  'edk2-ovmf: for emulating UEFI with run_archiso'
  'gnupg: for PGP signature verification of rootfs over PXE'
  'grub: for grub support in the ISO'
  'openssl: for CMS signature verification of PXE artifacts and rootfs over PXE'
  'qemu-desktop: for run_archiso'
)
source=(git+https://github.com/AcreetionOS-Linux/arch-iso.git)

#who needs security

#sha512sums=('8dd878c0f5774bbed357c0a3f52cc687e852fdf0aed0afb4b1da113cb9d929e1c414120e63bd46e2d777f08b7ff968edaa2f5e1cf81d419a1ddb210bb5d8bced')
#b2sums=('f1f201c2121a5e5b079055576d15a29514e4abd672b89e9d3916c155c1914a0a9454dfee098d5379cf14de9655e69a2eb559ddbcb70e19e4506d822eb1c5af47')
#validpgpkeys=(
#  '991F6E3F0765CF6295888586139B09DA5BF0D338' # David Runge <dvzrv@archlinux.org>
#  'BB8E6F1B81CF0BB301D74D1CBF425A01E68B38EF' # nl6720 <nl6720@archlinux.org>

sha512sums=('SKIP')


check() {
  make -k check -C $pkgbase
}

package() {
  make DESTDIR="$pkgdir" PREFIX=/usr install -C $pkgbase
}

