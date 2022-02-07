#!/bin/bash

# Disable shellcheck rules that produce false positives in this file. Repository
# rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.

# Maintainer: Alad Wenter <https://github.com/AladW>
# Contributor: Ross Clark <https://github.com/archiv8/aurutils>

pkgname=aurutils
pkgver=4.4
pkgrel=1
pkgdesc='Helper tools for the arch user repository'
url='https://github.com/AladW/aurutils'
arch=('any')
license=('custom:ISC')
source=("$url/releases/download/$pkgver/$pkgname-$pkgver.tar.gz")
changelog=aurutils.changelog
install=aurutils.install
sha512sums=('86a80ae8327aeeb4932c7709767b2be5fae19281a5bcc78b2b10197e97c32afb'
            'SKIP'
            'a2c32b0dba4da40b83ff31cce48a00faed5ed2f663c060a865d31caeb1e4ed39')
depends=('git' 'jq' 'pacutils' 'curl' 'expect')
makedepends=('signify')
optdepends=('bash-completion: bash completion'
            'zsh: zsh completion'
            'devtools: aur-chroot'
            'vifm: default pager')

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
