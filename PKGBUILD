# Maintainer: RangHo Lee <hello at rangho dot me>
pkgname=soteria
pkgver=0.2.0
pkgrel=1
pkgdesc="A GTK-based polkit authentication agent"
arch=('x86_64')
url="https://github.com/imvaskel/soteria"
license=('Apache-2.0')
depends=('gtk4' 'polkit')
makedepends=('git' 'rust')
options=('!debug')
source=("git+$url#tag=v$pkgver")
b2sums=('51fc36d28df3aeb8840cfdfba402be0039119b6e4c82c77c602dc099b020385b55947d4b9d443242bd2fcf1065c60e1fb85da21af6f909de786ae9c59c4f5f27')

build() {
  cargo build --locked --manifest-path $pkgname/Cargo.toml --release
}

package() {
  install -Dm755 $pkgname/target/release/$pkgname "$pkgdir/usr/lib/soteria-polkit/$pkgname"

  install -Dm644 $pkgname/LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

