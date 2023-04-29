# Maintainer: Benoît Allard <benoit.allard@gmx.de>
# Maintainer: Daniel Bershatsky <bepshatsky@yandex.ru>
pkgname=python-optuna
_pkgname=${pkgname#python-}
pkgver=3.1.1
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
sha256sums=('4e760b067a6234a556e9a707fb47483ffba5ea8bc0b23997766a23e3603b9a82')

build() {
    cd $_pkgname-$pkgver
    python -m build -n -w
}

package() {
    python -m installer \
        --compile-bytecode 1 \
        --destdir="$pkgdir" \
        $_pkgname-$pkgver/dist/$_pkgname-*.whl
}
