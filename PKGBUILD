# Maintainer: graykode <nlkey2022@gmail.com>
pkgname=abtop
pkgver=0.3.9
pkgrel=1
pkgdesc='AI agent monitor for your terminal — like btop, but for AI coding agents'
arch=('x86_64' 'aarch64')
url='https://github.com/graykode/abtop'
license=('MIT')
depends=('gcc-libs')
makedepends=('rust' 'cargo')
source=("$pkgname-$pkgver.tar.gz::https://static.crates.io/crates/$pkgname/$pkgname-$pkgver.crate")
sha256sums=('SKIP')

prepare() {
    mv "$pkgname-$pkgver" "$pkgname"
    cd "$pkgname"
    cargo fetch --locked --target "$CARCH-unknown-linux-gnu"
}

build() {
    cd "$pkgname"
    export RUSTUP_TOOLCHAIN=stable
    export CARGO_TARGET_DIR=target
    cargo build --release --locked
}

package() {
    cd "$pkgname"
    install -Dm755 target/release/abtop -t "$pkgdir/usr/bin/"
    install -Dm644 LICENSE -t "$pkgdir/usr/share/licenses/$pkgname/"
}
