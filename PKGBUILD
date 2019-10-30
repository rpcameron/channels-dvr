# Maintainer: 'Robert Cameron <rob@rpcameron.net>'

pkgname=channels-dvr
pkgver=2019.10.29.1947
pkgrel=1
pkgdesc="Channels DVR server"
arch=('x86_64' 'armv7h' 'aarch64')
url="https://getchannels.com/dvr-server"
license=('custom')
optdepends=('chromium: TV Everywhere and Locast support')
source=(channels-dvr.service
        channels-dvr.sysusers
        channels-dvr.tmpfiles)
source_x86_64=("channels-dvr::https://channels-dvr.s3.amazonaws.com/${pkgver}/channels-dvr-linux-x86_64"
               "comskip::https://channels-dvr.s3.amazonaws.com/${pkgver}/comskip-linux-x86_64"
               "ffmpeg::https://channels-dvr.s3.amazonaws.com/${pkgver}/ffmpeg-linux-x86_64"
               "ffprobe::https://channels-dvr.s3.amazonaws.com/${pkgver}/ffprobe-linux-x86_64")
source_armv7h=("channels-dvr::https://channels-dvr.s3.amazonaws.com/${pkgver}/channels-dvr-linux-armv7l"
               "comskip::https://channels-dvr.s3.amazonaws.com/${pkgver}/comskip-linux-armv7l"
               "ffmpeg-dl::https://channels-dvr.s3.amazonaws.com/${pkgver}/ffmpeg-dl-linux-armv7l"
               "ffmpeg::https://channels-dvr.s3.amazonaws.com/${pkgver}/ffmpeg-linux-armv7l"
               "ffprobe::https://channels-dvr.s3.amazonaws.com/${pkgver}/ffprobe-linux-armv7l")
source_aarch64=("channels-dvr::https://channels-dvr.s3.amazonaws.com/${pkgver}/channels-dvr-linux-arm64"
                "comskip::https://channels-dvr.s3.amazonaws.com/${pkgver}/comskip-linux-arm64"
                "ffmpeg::https://channels-dvr.s3.amazonaws.com/${pkgver}/ffmpeg-linux-arm64"
                "ffprobe::https://channels-dvr.s3.amazonaws.com/${pkgver}/ffprobe-linux-arm64")
sha256sums=("ed7d5a050691c1210bec42f22687aa6407e90349e74d9c275a947254e070c6e9"
            "9f4d6dcee4838296da3356e1f7bff10d41ab6bca43a0f266480edae98905ec62"
            "806f873078e4d64a0ed558bfec1078c85ad3f671986bcc4590ed5322041f9858")
sha256sums_x86_64=("4509c2a4e59f3487546274081b3625ac4d4d7051a7a65cb5e293fbcff38e19f7"
                   "24e96adc46bfbe2371eec9e22cb12aa14bac95740934962a872c51e0dafc10c8"
                   "7f81acac28e3c7dc8cc81314ca51bd0dfeda1babca20d0adb66608ee2455b56e"
                   "5d15a8d9795852455aed02ed5f6960887a0dd6100e30b10a6c26d82fc0e96b44")
sha256sums_armv7h=("5cc7454aa0711dcfba4dc916a674cc584ab38e1d685a4d0cfea630752eef5a10"
                   "4bd6ca74b4b519c6f10c7108634a9499c6283be7070e13a31f89a8e92acf4c45"
                   "91281e05d4e443db09427d948e23754b4dc73e3de0cfee8376578dde5f545839"
                   "255c333f4c4590348b5d8ad6f2ad3abf747d91bc1c32291e22e4bbc241f73a99"
                   "9dbd4300b5042f6b620efe652be3ff217fe26ae4441afba6f25d7963eb22376d")
sha256sums_aarch64=("7271130db554d17ceb91dd274761376216973f2cc16d5dcc7090b08f4a4dfe34"
                    "464a67c7734c2b259d5e914bf47986aa3c94e9127c07a2e87541fa2fa9c3fb2f"
                    "dc1227cdd178e8cd0c7897e8e8d64c9f70528112286cf88ae6ade0f5aef081e9"
                    "4bcf6924d1f6bbbc43e1e441d251124257190ac0a9f8c0622982de83ebc475e0")

package() {
    install -Dm750 channels-dvr "${pkgdir}/usr/lib/${pkgname}/${pkgver}/channels-dvr"
    install -Dm750 comskip "${pkgdir}/usr/lib/${pkgname}/${pkgver}/comskip"
    install -Dm750 ffmpeg "${pkgdir}/usr/lib/${pkgname}/${pkgver}/ffmpeg"
    install -Dm750 ffprobe "${pkgdir}/usr/lib/${pkgname}/${pkgver}/ffprobe"
    [ -f ffmpeg-dl ] && install -Dm750 ffmpeg-dl "${pkgdir}/usr/lib/${pkgname}/${pkgver}/ffmpeg-dl"
    ln -s ${pkgver} "${pkgdir}/usr/lib/${pkgname}/latest"

    # systemd
    install -Dm644 ${pkgname}.service "${pkgdir}/usr/lib/systemd/system/${pkgname}.service"
    install -Dm644 ${pkgname}.tmpfiles "${pkgdir}/usr/lib/tmpfiles.d/${pkgname}.conf"
    install -Dm644 ${pkgname}.sysusers "${pkgdir}/usr/lib/sysusers.d/${pkgname}.conf"
}
