pkgname=forgejo-config-grug
pkgver=0.0.1
pkgver() {
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}
pkgrel=1
arch=('any')
pkgdesc="forgejo config for grug"
url="https://git.grug.se/admin/forgejo-config-grug"
license=('MIT')
makedepends=()
provides=()
conflicts=()
install="script.install"
package() {
  depends+=(forgejo)
  depends+=(postgresql-config-grug)
  depends+=(server-config-grug)
  mkdir -p "$pkgdir/etc/systemd/system/forgejo.service.d"
  cp override.conf "$pkgdir/etc/systemd/system/forgejo.service.d/"
  cp -r forgejo-config-grug "$pkgdir/etc/forgejo-config-grug"
}
