pkgname=pulseaudio-dlna
pkgver=0.5.2
pkgrel=1
pkgdesc='Small DLNA server which brings DLNA/UPnP support to PulseAudio'
arch=('x86_64')
url=https://github.com/masmu/pulseaudio-dlna
license=('GPL3')
depends=('dbus-python2' 'python2-gobject' 'python2-lxml' 'python2-pip' 'python2-psutil'
         'python2-setuptools')
optdepends=('faac: AAC transcoding support'
            'ffmpeg: multiple formats support'
            'flac: FLAC transcoding support'
            'lame: MP3 transcoding support'
            'opus: OPUS transcoding support'
            'sox: WAV transcoding support'
            'vorbis-tools: OGG transcoding support')
source=("$url/archive/$pkgver/$pkgname-$pkgver.tar.gz")
sha512sums=('298f61d643c35449fbb0001efa69a1792e41518953f58506703f3568902da4457d0f4f9e52b9641df26fc6f978670dd29a7f5d786b99339bd2a71f5fa59dd7db')

build() {
  cd $pkgname-$pkgver
  python2 setup.py build
  pip2 install --user chardet docopt futures netifaces notify2 protobuf requests setproctitle
}
package() {
  cd $pkgname-$pkgver
  python2 setup.py install --root="$pkgdir" --optimize=1 --skip-build
}
