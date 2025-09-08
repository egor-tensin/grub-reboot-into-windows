# Maintainer: Egor Tensin <egor@tensin.name>
pkgname=grub-reboot-into-windows
pkgver=0.1
pkgrel=1
pkgdesc='Reboot into dual-booted Windows with a Bluetooth keyboard'
arch=(any)
url="https://github.com/egor-tensin/$pkgname"
license=(MIT)
depends=(bash gawk grep)
source=("$pkgname-$pkgver.tar.gz::$url/archive/v$pkgver.tar.gz")
sha256sums=(SKIP)
options=('!debug')

package() {
    cd -- "$pkgname-$pkgver"

    install -D -m 0755 -t "$pkgdir/usr/bin" "bin/$pkgname"
    install -D -m 0644 -t "$pkgdir/usr/share/applications" "share/$pkgname.desktop"
    install -D -m 0644 -t "$pkgdir/usr/share/$pkgname" share/icon.svg
    install -D -m 0640 -t "$pkgdir/etc/sudoers.d/$pkgname" etc/sudoers
}
