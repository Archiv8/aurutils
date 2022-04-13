#!/bin/bash

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# [ToDo]: Add files: User documentation
# [ToDo]: Add files: Tooling
# [FixMe]: Namcap warnings and errors

# Maintainer: Ross Clark <archiv8@artisteducator.com>
# Contributor: Ross Clark <archiv8@artisteducator.com>


pkgname=aurutils
pkgver=9.5
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
    "dbafadb5011b8b8576066510276343de5266850703d84bf8f58866d84deb64afc502c7499e929e3f1cdfccbb47ce0fcb588469f643bc2df99e097eb190dc511b"
)
depends=(
    # Official Arch Linux repositories
    "curl"
    "expect"
    "gawk"
    "git"
    "jq"
    "pacutils"
)
# makedepends=()
optdepends=(
    # Official Arch Linux repositories
    "bash-completion: bash completion"
    "devtools: aur-chroot"
    "vifm: default pager"
    "zsh: zsh completion"
    "ninja: aur-sync ninja support"
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
