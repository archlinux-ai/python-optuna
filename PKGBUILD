# Maintainer: Benoît Allard <benoit.allard@gmx.de>
# Maintainer: Daniel Bershatsky <bepshatsky@yandex.ru>
pkgname=python-optuna
_pkgname=${pkgname#python-}
pkgver=3.2.0
pkgrel=1
pkgdesc="A hyperparameter optimization framework"
arch=('any')
url="https://optuna.org"
license=('MIT')
depends=(
    'python-alembic'
    'python-cmaes'
    'python-colorlog'
    'python-numpy'
    'python-packaging'
    'python-sqlalchemy'
    'python-yaml'
)
makedepends=('python-build' 'python-installer' 'python-setuptools' 'python-wheel')
source=("$_pkgname-$pkgver.tar.gz::https://github.com/optuna/$_pkgname/archive/v$pkgver.tar.gz")
sha256sums=('eaf63ef73cf7b92fb25320cb9546b3a4b0bab83d911a353b7e00aa940581ddcb')

build() {
    python -m build -nw $_pkgname-$pkgver
}

package() {
    python -m installer \
        --compile-bytecode 1 \
        --destdir="$pkgdir" \
        $_pkgname-$pkgver/dist/$_pkgname-*.whl
}
