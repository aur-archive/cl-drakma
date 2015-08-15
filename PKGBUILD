# Maintainer: DavidK <david_king at softhome dot net>
# Contributor:  veox <box 55 [shift-two] mail [dot] ru>

pkgname=cl-drakma
_clname=drakma
pkgver=1.3.9
pkgrel=1
pkgdesc="A Common Lisp web client"
arch=('any')
url="http://www.weitz.de/drakma/"
license=('BSD')
depends=('common-lisp' 'cl-base64' 'cl-chunga' 'cl-flexi-streams' 'cl-puri' 'cl-ssl' 'cl-usocket' 'openssl' 'cl-bordeaux-threads' 'cl-trivial-garbage')
optdepends=('cl-fiveam: for test suite')
install=cl-drakma.install
options=('docs')  # TODO: do when fully supported by pacman
source=('http://weitz.de/files/drakma.tar.gz' 'LICENSE')
#The sources from that website change md5sums, more often than daily, without
#change in content. We have to trust it's not really changing.
md5sums=('SKIP' '63605eed7c939d885851f2e876ce3f14')

package() {
    install -d "${pkgdir}"/usr/share/common-lisp/source/${_clname}
    install -d "${pkgdir}"/usr/share/common-lisp/source/${_clname}/test
    install -d "${pkgdir}"/usr/share/common-lisp/systems
    install -d "${pkgdir}"/usr/share/licenses/${pkgname}
    install -d "${pkgdir}"/usr/share/doc/${pkgname}

    cd "${srcdir}"/${_clname}-${pkgver}

    install -m 644 -t "${pkgdir}"/usr/share/common-lisp/source/${_clname} \
        *.lisp
    install -m 644 -t "${pkgdir}"/usr/share/common-lisp/source/${_clname} \
        *.asd
    install -m 644 -t "${pkgdir}"/usr/share/common-lisp/source/${_clname}/test \
        test/*.lisp
    install -m 644 "${srcdir}"/LICENSE \
        "${pkgdir}"/usr/share/licenses/${pkgname}
    install -m 644 doc/index.html \
        "${pkgdir}"/usr/share/doc/${pkgname}

    cd "${pkgdir}"/usr/share/common-lisp/systems
    ln -s ../source/${_clname}/${_clname}.asd .
    ln -s ../source/${_clname}/${_clname}-test.asd .
}

# vim:set ts=2 sw=4 et nospell:
