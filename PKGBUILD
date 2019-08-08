pkgname='xtruss'
pkgdesc="An easy-to-use X protocol tracing program"
pkgver=r3279.82973f5
pkgrel=1
arch=('any')
source=('xtruss::git+https://github.com/krafczyk/xtruss#branch=master')
md5sums=('SKIP')
pkgver() {
    cd "$pkgname"
    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

makedepends=('halibut')

build() {
    cd "$pkgname"
    ./autogen.sh
    ./configure --prefix=/usr
    make
}

package() {
    cd "$pkgname"
    make DESTDIR="$pkgdir/" install
}
