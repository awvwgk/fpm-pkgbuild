# Maintainer: Sebastian Ehlert  <awvwgk at gmail dot com>

pkgname=('fortran-fpm')
_pkgname='fpm'
pkgver=0.2.0
pkgrel=1
pkgdesc="A package manager and build system for Fortran."
arch=('x86_64')
url="https://fpm.fortran-lang.org/"
license=('MIT')
makedepends=('gcc-fortran')
conflicts=('fpm')
source=("${_pkgname}.f90::https://github.com/fortran-lang/fpm/releases/download/v${pkgver}/${_pkgname}-${pkgver}.f90"
        "https://github.com/fortran-lang/fpm/raw/v${pkgver}/LICENSE")
sha256sums=("79d5041f5cebd1adff999017b3b5f88d8814267dbd0faaa0f7c720411ede463e"
            "b7e33601c0130d1a674fcc772ed9b7804460d1896469a5b219ba4062efcd9fb9")

build() {
  cd "${srcdir}"
  gfortran "${_pkgname}.f90" -o "${_pkgname}"
}

check() {
  cd "${srcdir}"
  "${srcdir}/${_pkgname}" --version
}

package() {
  install -Dm 755 "${srcdir}/${_pkgname}" "${pkgdir}/usr/bin/${_pkgname}"
  install -Dm 555 "${srcdir}/LICENSE" "${pkgdir}/usr/share/licences/${_pkgname}/LICENSE"
}
