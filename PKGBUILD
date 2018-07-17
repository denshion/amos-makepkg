pkgname=amos-netlib
_pkgname="amos-netlib"
pkgrel=1
pkgdesc="Fortran library for Bessel Functions of a Complex Argument and Nonnegative Order"
arch=('any')
url="https://github.com/denshion/amos-makepkg"
license=('GPL')
makedepends=('git' 'gcc-fortran')
depends=()
provides=('amos-netlib')
conflicts=()
backup=()
source=('http://www.netlib.org/amos/amos.tgz')
md5sums=('SKIP')
epoch=1
pkgver=1998.07.21
_programs=( 'cqcai.f' 'cqcbh.f' 'cqcbi.f' 'cqcbj.f' 'cqcbk.f' 'cqcby.f'
'zqcai.f' 'zqcbh.f' 'zqcbi.f' 'zqcbj.f' 'zqcbk.f' 'zqcby.f')
_functions=( 'cacai.f' 'cacon.f' 'cairy.f' 'casyi.f' 'cbesh.f' 'cbesi.f'
'cbesj.f' 'cbesk.f' 'cbesy.f' 'cbinu.f' 'cbiry.f' 'cbknu.f' 'cbuni.f' 'cbunk.f'
'ckscl.f' 'cmlri.f' 'cqcai.f' 'cqcbh.f' 'cqcbi.f' 'cqcbj.f' 'cqcbk.f' 'cqcby.f'
'crati.f' 'cs1s2.f' 'cseri.f' 'cshch.f' 'cuchk.f' 'cunhj.f' 'cuni1.f' 'cuni2.f'
'cunik.f' 'cunk1.f' 'cunk2.f' 'cuoik.f' 'cwrsk.f' 'd1mach.f' 'dgamln.f'
'dsclmr.f' 'fdump.f' 'gamln.f' 'i1mach.f' 'r1mach.f' 'xerror.f' 'zabs.f'
'zacai.f' 'zacon.f' 'zairy.f' 'zasyi.f' 'zbesh.f' 'zbesi.f' 'zbesj.f' 'zbesk.f'
'zbesy.f' 'zbinu.f' 'zbiry.f' 'zbknu.f' 'zbuni.f' 'zbunk.f' 'zdiv.f' 'zexp.f'
'zkscl.f' 'zlog.f' 'zmlri.f' 'zmlt.f' 'zqcai.f' 'zqcbh.f' 'zqcbi.f' 'zqcbj.f'
'zqcbk.f' 'zqcby.f' 'zrati.f' 'zs1s2.f' 'zseri.f' 'zshch.f' 'zsqrt.f' 'zuchk.f'
'zunhj.f' 'zuni1.f' 'zuni2.f' 'zunik.f' 'zunk1.f' 'zunk2.f' 'zuoik.f'
'zwrsk.f')



build() {
  cd $srcdir/amos/
  # Compliation flags:
  # -c for static linking;
  # -std=f95 - the oldest standart after Fortran77; this is required to mask
  # the GNU extensions, particulary, the ZABS intrinsic
  # -O3 - optimization
  gfortran -c -std=legacy -ffixed-form -Wall -O3 ${_functions}
  ar r libamos.a *.o
  cd -
}

package() {
  install -Dm644 $srcdir/amos/libamos.a -t ${pkgdir}/usr/local/lib/
}

# vim:set ts=2 sw=2 et: