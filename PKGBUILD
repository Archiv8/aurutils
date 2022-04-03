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
pkgver=9.1.1
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
    "cef623b2fc7c4a4a417d6c5ab26a7d2b8db071c8d38f0189460d216f1e1a5a4d761d72729b42a5a48d1b3045684476bbbd372eb411abccf462a7f3d26b9b33f5"
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
