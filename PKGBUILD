pkgname=xz
pkgver=5.8.1
pkgrel=1
pkgdesc="Library and command line tools for XZ and LZMA compressed files"
arch=('x86_64')
url="https://xz.tukaani.org/xz-utils"
license=('GPL-2.0-or-later' 'GPL-3.0-or-later' 'LGPL-2.1-or-later')
groups=('base')
depends=('glibc')
source=(https://github.com/tukaani-project/xz/archive/v${pkgver}/${pkgname}-${pkgver}.tar.xz)
sha256sums=(0b54f79df85912504de0b14aec7971e3f964491af1812d83447005807513cd9e)

build() {
    cd ${pkgname}-${pkgver}

    local configure_args=(
        --disable-static
        --docdir=/usr/share/doc/${pkgname}-${pkgver}
        ${configure_options}
    )

    ./configure "${configure_args[@]}"

    make
}

package() {
    cd ${pkgname}-${pkgver}

    make DESTDIR=${pkgdir} install
}
