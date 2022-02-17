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
    "bfecaf8c550b15482054bcafaa7785ef9aa1de8b378a3c680af5570ef11629a8f51c971eb886615a85c64227266cd9e1993963b77bb210b11000f4ed71a1d62d"
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
