pkgname=forgejo-config-grug
pkgver() {
  # Use number of revisions and hash as version
  cd "$pkgname"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}
pkgrel=1
arch=('any')
pkgdesc="forgejo config for grug"
url="https://git.grug.se/admin/forgejo-config-grug"
license=('MIT')
depends=('forgejo' 'postgresql-config-grug' 'server-config-grug')
makedepends=()
provides=()
conflicts=()
install="script.install"
package() {
  mkdir -p "$pkgdir/etc/systemd/system/forgejo.service.d"
  cp override.conf "$pkgdir/etc/systemd/system/forgejo.service.d/"
  cp -r forgejo-config-grug "$pkgdir/etc/forgejo-config-grug"
}
