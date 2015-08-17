# Maintainer: shadyabhi <abhijeet.1989@gmail.com>
# Author : Bram Cohen

pkgname=python2-google-api-python-client
_realname=google-api-python-client
pkgver=1.1
pkgrel=1
pkgdesc="Google API Client for Python"
url="http://code.google.com/p/google-api-python-client/"
arch=('any')
license=('APACHE')
depends=('python2' 'python2-httplib2' 'python2-gflags' 'python-simplejson')
makedepends=('python2-distribute')
source=("http://google-api-python-client.googlecode.com/files/google-api-python-client-${pkgver}.tar.gz")
build(){
  cd "$srcdir/$_realname-$pkgver"

  # python2 fix
  for file in $(find . -name '*.py' -print); do
    sed -i 's_#!.*/usr/bin/python_#!/usr/bin/python2_' $file
    sed -i 's_#!.*/usr/bin/env.*python_#!/usr/bin/env python2_' $file
  done

  python2 setup.py install --root="$pkgdir" --optimize=1
  chmod +r ${pkgdir}/* -R
}
md5sums=('3a7342a483398587e051ef8b73c20575')
