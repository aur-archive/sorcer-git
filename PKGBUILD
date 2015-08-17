# Maintainer: speps <speps dot aur dot archlinux dot org>

pkgname=sorcer-git
pkgver=89.18e6891
pkgrel=1
pkgdesc="A wavetable LV2 plugin synth, targeted at the electronic / dubstep genre"
arch=('i686' 'x86_64')
url="http://openavproductions.com/sorcer/"
license=('GPL')
groups=('lv2-plugins')
depends=('lv2' 'cairomm' 'libsndfile' 'ntk-git')
makedepends=('python' 'boost')
provides=('sorcer')
conflicts=('sorcer')
source=("$pkgname::git+https://github.com/harryhaaren/openAV-Sorcer.git")
md5sums=('SKIP')

pkgver() {
  cd $pkgname
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

build() {
  cd $pkgname
  make
}

package() {
  cd $pkgname

  # plugin
  install -d "$pkgdir/usr/lib/lv2"
  cp -a {sorcer.lv2,presets/*} "$pkgdir/usr/lib/lv2"
}
