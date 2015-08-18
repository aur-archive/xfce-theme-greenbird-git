# Maintainer: James Duley <jagduley gmail>
# Contributor: Diego <cdprincipe@at@gmail@dot@com>
# Contributor: Philip Müller <philm_at_manjaro_dot_org>
# Contributor: Pablo Lezaeta <prflr88 (arroba) gmail (dot) com>
# Contributor: Robert Gormly <rggormly_at_gmail_dot_com>

_pkgname=artwork-greenbird
pkgname=xfce-theme-greenbird-git
pkgver=14.20131013~4~g51efd00
pkgrel=1
pkgdesc="Desktop theme for Xfce based on Graybird, used on Manjaro"
arch=('any')
url="http://manjaro.org"
license=('GPL2' 'CCPL')
depends=('gtk-engine-murrine')
makedepends=('git')
optdepends=('faenza-green-icon-theme: matching icon theme'
            'lightdm-gtk-greeter: lightdm theme'
            'lightdm-unity-greeter: lightdm unity theme')
provides=(xfce-theme-greenbird)
conflicts=(xfce-theme-greenbird)

source=("git+https://github.com/manjaro/$_pkgname.git")
md5sums=("SKIP")

pkgver(){
  cd $_pkgname
  echo "$(git rev-list --count HEAD | sed 's/-/0.git/g' ).$(git describe --always | sed 's/-/~/g' )"
}

package() {
  cd "$srcdir/$_pkgname"

  # create theme dirs
  install -d -m 755 "$pkgdir"/usr/share/themes/Greenbird{,-compact/xfwm4}

  # install compact theme
  install -m 644 xfwm4_compact/* "$pkgdir"/usr/share/themes/Greenbird-compact/xfwm4/

  # clean up
  rm -rf {.git,.gitignore,LICENSE.{CC,GPL},README,xfwm4_compact}

  # install theme
  cp -r . $pkgdir/usr/share/themes/Greenbird/
}

