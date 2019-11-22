# Maintainer: 'Robert Cameron <rob@rpcameron.net>'
# Packager: 'Robert Cameron <rob@rpcameron.net>'

pkgname=channels-dvr
pkgver=2019.11.19.2312
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
sha256sums_x86_64=("d8a6666b9d4764f356e64da946cddd7801e6920b9d81bad615a674fcc02c9cce"
                   "e6662500b8ff7ab4a948977485467985d74dada9dc4f3fac43b9c6b613d547f2"
                   "aa4bbf47f65693f359c896c3e19f272ffda0438472270749004e943ddbdd9e58"
                   "c34adee43b945015a11926dee6f4140a00472cb1cdd9f70f3f51263bce3b36d0")
sha256sums_armv7h=("a8b4c4e33d755fb3db1b87d9d4d669ad40278010087785eeb09ab1f0cdc7a793"
                   "5aa622e65e762628439c6334de59e0ea6ddb34864d82788a7b1d0013f68473e9"
                   "00262dff249814c4ebad867b0b4b4cc163aa819d6b4705f28866703af9e02358"
                   "9d488b0d8083467b1f3bd2978a836febac4405fa0aa1cb7e08afcf02b1b4fb5c"
                   "754ec723d0d7f863fa1c93993bc210f85eb7c821b3ab1ada7bf736ca114b9ed4")
sha256sums_aarch64=("e74fcac1daf803ebdabc32acc74619811a0b699ee315c15adea5cdc30dc32dc3"
                    "2b66e42b8118f56be519b7f3c4f1bdd5afd7ed1be8406c270851146ed29cd057"
                    "15d3ee3d86d39002ce3a8023f9fad4c5526c0e23665731f66c6e250c0aad437c"
                    "6dce773195c69b01a5dd8d4773716f015b17db8ac0295bbdac44d43875bda03f")

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
