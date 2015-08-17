# Maintainer : Michael Witten
#
# Derived from perl-crypt-blowfish:
#   Contributor: Sergej Pupykin <pupykin.s+arch@gmail.com>
#   Contributor: Charles Mauch <cmauch@gmail.com>
#
# Contributor: Pedro Alejandro López-Valencia <palopezv@gmail.com>

pkgname=perl-crypt-dh
pkgver=0.07
pkgrel=3

pkgdesc='Perl/CPAN Module Crypt::DH: Diffie-Hellman key exchange system'

_cpan_name=Crypt-DH-$pkgver
url=http://search.cpan.org/~mithaldu/$_cpan_name/lib/Crypt/DH.pm

license=(GPL PerlArtistic)
source=("http://search.cpan.org/CPAN/authors/id/M/MI/MITHALDU/$_cpan_name.tar.gz")
md5sums=(5494c91420bf77de4af808fcafb6c3ce)

arch=(any)
makedepends=(make)
depends=(perl perl-math-bigint-gmp)

build()
{
  cd "$srcdir/$_cpan_name"
  PERL_MM_USE_DEFAULT=1 perl Makefile.PL INSTALLDIRS=vendor
  make
}

check()
{
  cd "$srcdir/$_cpan_name"
  make test
}

package()
{
  cd "$srcdir/$_cpan_name"
  make pure_install DESTDIR="$pkgdir"

  cd "$pkgdir"
  find . -name '.packlist' -delete
  find . -name '*.pod'     -delete
}
