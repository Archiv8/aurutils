#!/bin/bash

# Disable shellcheck rules that produce false positives in this file. Repository
# rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.

# Maintainer: Alad Wenter <https://github.com/AladW>
# Co-Maintainer: Cedric Girard <cgirard [dot] archlinux [at] valinor [dot] fr>
# Contributor: Ross Clark <https://github.com/archiv8/aurutils>

pkgname=aurutils
pkgver=6.1
pkgrel=1
pkgdesc="Helper tools for the arch user repository"
url="https://github.com/AladW/aurutils"
arch=("any")
license=("custom:ISC")
source=(
    "$pkgname-$pkgver.tar.gz::${url}/archive/refs/tags/$pkgver.tar.gz"
)
changelog=aurutils.changelog
install=aurutils.install
sha512sums=(
    "089b0860ce104b057cef262aa8f14bf66c6d20b1fcb61cfd42d35cb0b1bb19064c047645ccc2e7aaee37b6d66efeb857bbb0a4fd6222d50c666aebd4ce0af79c"
)
depends=(
    "git"
    "jq"
    "pacutils"
    "curl"
    "expect"
    "gawk"
)
# makedepends=()
optdepends=(
    "bash-completion: bash completion"
    "zsh: zsh completion"
    "devtools: aur-chroot"
    "vifm: default pager"
)

prepare() {
    cd "$pkgname-$pkgver" || exit
}

build() {
    cd "$pkgname-$pkgver" || exit
    make AURUTILS_VERSION="$pkgver"
}

package() {
    cd "$pkgname-$pkgver" || exit
    make DESTDIR="$pkgdir" install
}
