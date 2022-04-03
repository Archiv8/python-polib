#!/bin/bash

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <archiv8@artisteducator.com>
# Contributor: Ross Clark <archiv8@artisteducator.com>


_pkgname=polib


pkgbase=python-polib
pkgname=("python-polib")

pkgver=1.1.1
pkgrel=1
pkgdesc="A library to manipulate gettext files"
url="https://pypi.python.org/pypi/polib"
arch=("any")
license=("MIT")
depends=("python")
makedepends=("python-setuptools")
source=("${pkgbase}-${pkgver}.tar.gz::https://pypi.io/packages/source/p/${_pkgname}/${_pkgname}-${pkgver}.tar.gz")
sha256sums=("e02c355ae5e054912e3b0d16febc56510eff7e49d60bf22aecb463bd2f2a2dfa")

build() {
  cd "${srcdir}/${_pkgname}-${pkgver}"
  python setup.py build
}

package() {
  cd "${srcdir}/${_pkgname}-${pkgver}"
  python setup.py install --root="${pkgdir}" --skip-build --optimize=1
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
