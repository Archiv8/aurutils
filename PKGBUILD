#!/bin/bash

# Disable shellcheck rules that produce false positives in this file. Repository
# rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Alad Wenter <https://github.com/AladW>
# Co-Maintainer: Cedric Girard <cgirard [dot] archlinux [at] valinor [dot] fr>
# Contributor: Ross Clark <https://github.com/archiv8/aurutils>


pkgname=aurutils
pkgver=8.2
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
    "ed31372cd615b2a0b4e3a60525d44b8e78faef3545283107dcdd490dbcacd8da0028beffe6a94c173ca94729138c50b1197d43727224e84f8d5717c7dfceb873"
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
