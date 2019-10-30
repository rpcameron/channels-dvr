# Maintainer: 'Robert Cameron <rob@rpcameron.net>'

pkgname=channels-dvr
pkgver=2019.09.23.2227
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
               "ffmpeg::https://channels-dvr.s3.amazonaws.com/${pkgver}/ffmpeg-linux-armv7l"
               "ffprobe::https://channels-dvr.s3.amazonaws.com/${pkgver}/ffprobe-linux-armv7l"
               "ffmpeg-dl::https://channels-dvr.s3.amazonaws.com/${pkgver}/ffmpeg-dl-linux-armv7l")
source_aarch64=("channels-dvr::https://channels-dvr.s3.amazonaws.com/${pkgver}/channels-dvr-linux-arm64"
                "comskip::https://channels-dvr.s3.amazonaws.com/${pkgver}/comskip-linux-arm64"
                "ffmpeg::https://channels-dvr.s3.amazonaws.com/${pkgver}/ffmpeg-linux-arm64"
                "ffprobe::https://channels-dvr.s3.amazonaws.com/${pkgver}/ffprobe-linux-arm64")
sha256sums=("ed7d5a050691c1210bec42f22687aa6407e90349e74d9c275a947254e070c6e9"
            "9f4d6dcee4838296da3356e1f7bff10d41ab6bca43a0f266480edae98905ec62"
            "806f873078e4d64a0ed558bfec1078c85ad3f671986bcc4590ed5322041f9858")
sha256sums_x86_64=("7b1205ced39546e749e426fc6eeea114072c91464e9ae7890db6aaf52e2f47b8"
                   "febcf895947a9d392163ec49378775a87dd5911b261e2b01e7e4568da592be47"
                   "85c1d2e7a735000986b4e35b9e64db229649b0d1063e34c91d86c93bcfb98224"
                   "56884cc03132441cd2e42fd5a6d502fe6bac64cd7b9262338d96626387cb6bf3")
sha256sums_armv7h=("bf6711b4dde3894e0842093a582e03a7f3667e779b77c8f6cb411c71a7a36bf8"
                   "dba6f87a7d899fb755c511810346bb1545eb7322fe7eab98b33f861868f54561"
                   "4aceeb6cbe48a15d7b0343a7484cee220b6045c748d88bc7da22a7336c0efc08"
                   "b6b445613113adcddc25fdbca00c9f73ac70ca07160ddfbcae5be7a0ce42da7d"
                   "6089131ef760a592efc44cd862eb5585c685ed80cca387adebd16740d203f0b3")
sha256sums_aarch64=("211779b0823fea429771e375bdb5cf825c21d41e17d5ae81cffea96b2f8d9aab"
                    "ff73a8bd8462d63cb7bbf7c5049548e42da4a91e525c145c071c72836268b937"
                    "463f1b988c51d516bfa0464b2ff31d91e0d6558fb9fff47106887824e73b21da"
                    "9a5c404317b2d3082ae2a2ed05993b7fa7fc08fc9a3f633e6d9210921f0b58e5")

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
