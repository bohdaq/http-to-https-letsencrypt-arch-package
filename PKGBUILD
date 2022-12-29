# Maintainer: Bohdan Tsap <bohdan.tsap@tutanota.com>
pkgname=http-to-https-letsencrypt
binname=http-to-https-letsencrypt
pkgver=8.0.8
pkgrel=1
epoch=
pkgdesc="HTTP server with default redirect to HTTPS and support for Let'sEncrypt Automatic Certificate Management Environment using HTTP-01 challenge "
arch=('x86_64')
url="https://github.com/bohdaq/http-to-https-letsencrypt"
license=('MIT' 'APACHE' 'ISC' 'CC-BY-4.0' 'LGPL-3.0')
groups=()
depends=()
makedepends=(cargo)
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
changelog=
source=("$pkgname-$pkgver.tar.gz::https://github.com/bohdaq/$pkgname/archive/$pkgver.tar.gz")
sha256sums=('790e2fed54c10d1950a91becb603af3ef6e31f4820732b9717276c2e4507bb25')
noextract=()
validpgpkeys=()

prepare() {
	cd $pkgname-$pkgver
	cargo fetch --target "$CARCH-unknown-linux-gnu"	
}

build() {
	cd $pkgname-$pkgver
	export RUSTUP_TOOLCHAIN=stable
	export CARGO_TARGET_DIR=target
	cargo build --frozen --release --all-features
}

check() {
	cd $pkgname-$pkgver
	export RUST_TOOLCHAIN=stable
	cargo test --frozen --all-features	
}

package() {
	cd $pkgname-$pkgver
	install -Dm0755 -t "$pkgdir/usr/bin" "target/release/$binname"
}
