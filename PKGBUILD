#!/bin/bash

# Built from the original AUR package by Alad Wenter, "https://github.com/AladW", and Cedric Girard, "cgirard [dot] archlinux [at] valinor [dot] fr".

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
pkgver=10b
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
    "190b5cb3c0fed6efad9f15b83c87dea269ba645c320e91e27d8ae111c183949a602cfd8e75079426719986dbcee1f85d709155dde1ae2e1d87433b32b12e56d1"
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
