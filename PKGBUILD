# Maintainer: Bardia Moshiri <fakeshell@bardia.tech>

pkgname=pulseaudio-modules-droid-jb2q
provides=('pulseaduio-modules-droid-jb2q')
_pkgbase=pulseaudio-modules-droid-jb2q
pkgver=632.6f3132d
pkgrel=1
arch=('armv7h' 'aarch64' 'x86' 'x86_64')
url="https://github.com/mer-hybris/pulseaudio-modules-droid-jb2q"
license=('GPL2')
depends=('pulseaudio-hybris' 'audiosystem-passthrough')
makedepends=('git' 'pkgconfig' 'android-headers' 'automake' 'autoconf' 'libhybris')
source=("pulseaudio-modules-droid-jb2q::git+https://github.com/mer-hybris/pulseaudio-modules-droid-jb2q.git")
md5sums=('SKIP')
options=(debug !strip)

pkgver() {
  cd "${srcdir}/${_pkgbase}"
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

build() {
  cd "${srcdir}/${_pkgbase}"
  rm -rf build
  arch-meson  build
  ninja -C build
}

package() {
  cd "${srcdir}/${_pkgbase}"
  DESTDIR="${pkgdir}" ninja -C build install
}
