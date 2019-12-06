# Maintainer: 'Robert Cameron <rob@rpcameron.net>'
# Packager: 'Robert Cameron <rob@rpcameron.net>'

pkgname=channels-dvr
pkgver=2019.12.05.0128
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
sha256sums_x86_64=("997ac2026812c9dfed79648320e292998060702abe92ce0eaf381c39a9a43c9c"
                   "37ba9c96a443e2591310931487d3d10d3b2089eb3ff73049c27e6d91fb408923"
                   "e9fcebdb376e2e95925e2c02f71a7cbc49cdd299bac23f8664014f7a5f08de7c"
                   "32e6d0cc5a0fee178f4e2ab5425eaab8cc84a7f3e685892ce491889346c659f3")
sha256sums_armv7h=("38f1acb4626fef33fab5f4173f502af5ead6ad33c0480f700e6079f21f72c793"
                   "5691543d0caf476e0be4c379d7ff5f5c71900fe7eba7cb72582745c91c254272"
                   "90163074f174f1369a5b5e27fd4932e5a51b518d591f4a6f173970300ae5bec4"
                   "d94f05c3f1e6aa20edab5c743e07ad2a9ba64c6234a875328662db2eea8b3b9a"
                   "34f97bf5c04d0b161de27f2950f1d0386c675beb955f021a33e28d29a07b6805")
sha256sums_aarch64=("e7d489122cbedcd2d0f168e4cefb210bcd7d92f2d157652fb5f303b641c8587e"
                    "28bada6ca2ddb856dcfa0f8b7e8cffcc720064418b5880817d3d8c12de671090"
                    "9d402901c31e9a863e2aab21371c910b463dc667669ec838077e8cd104c55262"
                    "f764b1c52650f8fa98bad0716757ea14a7a11fd3d5a2770cb3a7245a546f906e")

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
