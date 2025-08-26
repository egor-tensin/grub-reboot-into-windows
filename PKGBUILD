# Maintainer: Egor Tensin <egor@tensin.name>
pkgname=reboot-into-windows
pkgver=0.2
pkgrel=1
pkgdesc='Reboot into dual-booted Windows with a Bluetooth keyboard'
arch=(any)
license=(MIT)
depends=(bash gawk grep)
source=(
    "$pkgname"
    "$pkgname.desktop"
    icon.svg
    sudoers
)
sha256sums=(
    SKIP
    SKIP
    SKIP
    SKIP
)
options=('!debug')

package() {
    install -D -m 0755 -t "$pkgdir/usr/bin" "$srcdir/$pkgname"
    install -D -m 0644 -t "$pkgdir/usr/share/applications" "$srcdir/$pkgname.desktop"
    install -D -m 0644 -t "$pkgdir/usr/share/$pkgname" "$srcdir/icon.svg"
    install -D -m 0640 -t "$pkgdir/etc/sudoers.d/reboot-into-windows" sudoers
}
