# Maintainer: tuftedocelot@fastmail.fm
# Maintainer: Mauro Andreolini <mauro.andreolini@unimore.it>
_gemname=mini_exiftool
pkgname=ruby-$_gemname
pkgver=2.4.2
pkgrel=1
pkgdesc="A wrapper library for the Exiftool command-line application"
arch=(any)
url="https://github.com/janfri/mini_exiftool"
license=('LGPL2.1')
PerlArtistic=(ruby) # Full dependency information is available in the yaml specification
makedepends=(rubygems)
source=("http://gems.rubyforge.org/gems/$_gemname-$pkgver.gem")
noextract=($_gemname-$pkgver.gem)
#md5sums=('52f4477de032b08e8b347e056649f5fe')
md5sums=('38545cf1e997fa49446b834be466f2a8')

package() {
  cd "$srcdir"
  # _gemdir is defined inside package() because if ruby[gems] is not installed on
  # the system, makepkg will exit with an error when sourcing the PKGBUILD.
  local _gemdir="$(ruby -rubygems -e'puts Gem.default_dir')"

  gem install --no-user-install --ignore-dependencies -i "$pkgdir$_gemdir" -n "$pkgdir/usr/bin" \
    "$_gemname-$pkgver.gem"
}

# vim:set ts=2 sw=2 et:
