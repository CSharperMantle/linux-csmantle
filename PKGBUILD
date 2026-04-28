# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=6.19.14.arch1
pkgrel=1
pkgdesc='Linux'
url='https://github.com/archlinux/linux'
arch=(loong64)
license=(GPL-2.0-only)
makedepends=(
  bc
  binutils
  cpio
  gettext
  glibc
  libelf
  libgcc
  openssl
  pahole
  perl
  python
  rust
  rust-bindgen
  rust-src
  tar
  xxhash
  xz
  zlib
  zstd

  # htmldocs
  graphviz
  imagemagick
  python-sphinx
  python-yaml
  texlive-latexextra
)
options=(
  !debug
  !strip
)
_srcname=linux-${pkgver%.*}
_srctag=v${pkgver%.*}-${pkgver##*.}
source=(
  https://cdn.kernel.org/pub/linux/kernel/v${pkgver%%.*}.x/${_srcname}.tar.{xz,sign}
  $url/releases/download/$_srctag/linux-$_srctag.patch.zst{,.sig}
  config  # the main kernel config file
)
validpgpkeys=(
  ABAF11C65A2970B130ABE3C479BE3E4300411886  # Linus Torvalds
  647F28654894E3BD457199BE38DBBDC86092693E  # Greg Kroah-Hartman
  83BC8889351B5DEBBB68416EB8AC08600F108CDF  # Jan Alexander Steffens (heftig)
)
b2sums=('64c2a0003d8080f268772d36923ff6ef8b2d55320ea08b77ad39384c98c9a5c1a8e71425470619aa3aa4dda8941f46aa9da364748cfa8fd9f8507a5ddd7ac03a'
        'SKIP'
        '6536f9ccb408f89b0a6dc86fdbb09f4229e9e4ea5ed210d118484a18ca8a82a1e1060114877ce7286b721d59587a8a70b5ed4616c4ec4925b0bdf5b25227e6fe'
        'SKIP'
        'bef3377ad86440af76e9dde4c29c9f4aaad42f5fe343f7d31f5eb537d6d358602f996f5d63986af275f2e92f94e71dc28c320edc8c03d05bd64dbd8ed23d75dc'
        'dfd366b283243f95c318471fe35e3a36646a38388dd6c4d9746bc981985a02ea303d75127244e9feac14564a8f49385483dfb56a8842814bdf97ca747bc2a4d5'
        '46f0fd181d20e8ba9e535264b443517c9a41700491f96a80d20f357d721c32652299c71949929c364b6471a7bb4bb6a09dde60fe1e3ad2fe4faa8a52708b49c0'
        'c999ed59f498d1e7b379999602aa47ede3a8080f2210547fb6c8d99aaf51003fece7a5ea26d71f50dc09af29cffe4167258037789919707524f8de9f1d453bdb'
        'e3ad9bd643726fa13ccc8dbd85b1b0a5d9b32ca99420bac3858396e904781940210e4f49df51ef50d863c55ce9a909110dd09be034106c28b00299db748af1cc'
        'd8562302bdea4169a9ae59e1386e7f1ace05166ee150360f950e6e5b8721b25d22d05e934ee5f1a0fe5dbf3d4dba23ab026976e16eb8ea541cda100eaf9df805'
        'e42309342e3a6179f07a6ebe812888b7ec298f68d36f6da4933b8a18e004267e41b001b37d1e31c4067dfb8dc9946b042bf01207d26ef86805724ba6a97b7a44'
        'ef3eba8c8322c14a7cb1ee02c766f6f938b525f993865ba161808a58aaf1ce08bbba620c58c3aa835dd01477d5df302332f5de6788ccc2c166f568ede65bb011'
        '1232863725145581d58de20b73e3cfb212fb14b0f9c71bf9b82df75dcea1e0325a09bb78d85fb26ada8393e6e1907232b446874e0c7efca1687a6dbdcc47c35d'
        '606223a96b0bdef2a621a7ef7cd0f8b9514a204f2208acc791cf3523a555e8b6cf14b009ddfef55b3a78ca94f7dd86919d68a32db385f02f2c7923cdf17af805'
        '21125a5686ee93c11d1614dd2e32ee429104515df9313788a23d519bc5497722b35d828b67033e8b2521b62b53e3ba22e7cc4bca95adb8e005ad61f7cc34d739'
        'bf37f08d926d74f198c35e526c9d49d34c20f1cd6354c29a8d74445c618d54487640571354ada2f939c2a5ca2e46b5ddb0e252c9d0b0a761cc5a1896ba4e918e'
        'bda85776c63fccc0d2fc33a0d1364bfa0f6bd16ed38e32445fff8e572106af31f5a7cd91d16a960f0e3c7e3d94a5edda67f725e482bf1deea3dd52e13fc2dc40'
        'e0f671bbba6f36c7ac99168acc15acf8f7748781820b7f0344aa42f442edeb23d9647644a25bd7d3b27194485b9c3475ed176981db9e7a525ec2596bfdb37f00'
        'f65971ff5071206eb19bb8a3b7937953ea16d0b62cb169c6b6e59a03028a90300a20412651f19f3d910b12a5891465ab7dadd7c6627f6b55aa02cbefb963cd5f'
        'e79b212252b422368cff136652634904493265ad71111a200129e7ad45caf770a6cd080347735a04bd9c461decc5e1d3dfe2d63a9f1b9fce719149f4b987839f'
        '4189a04f3bbffe32e3e31dd29bb1b3c3cb0e954850750494738f152c0d50318809f281c46345bb136a119a927180f2e1f5018908f64a765c51dae58b00949a56'
        'af2b77789f72db4aed23ecf0ec70757c1afcf7b391f16e998d33d21e70faed022b7aa7ec9618c3325480f118e87f4e087d3b39a3c1c46cf357eb5a26ef60c6b2'
        'bdc03efaf8861b62dc433b48a44b7cf3ba6b258acbaf74954e06ffdce5fb96b5c2970e3057dbee560fc32b24b948bc6cb3bd2bbfa70d774ea54ff3e23b8e76a8'
        'e3cf01af2753b75fde8c01e33146deef587f7488c7769845052da6b9cc29662455a829bff1bfe8cc8f824d17b30dff0739bbe75906a5d09d30511c5496b59c9f'
        'e9bfdf986ca2a90afa8b67ddebb4b2edabf8e13a4ecfa14006d56606ee3ae2500db9fd237e7b67e7d9628b9e667262a10ae81a7e473f513701fc99b7ec4f2d5f'
        '1d124dbe926f8370fe19ebdbd70e6a1a0f7d13700e6d36480b0361d43bf3e8e5dced0d390c6bf8a23ade3e6818160ffdca5712592b72582608c9161512914ce1'
        'c7873788e62a176fd98a7b26050152ed4bd628c25c54a6127b8d1932681bcd3a43ac9d2274c0b078295ce65a6351821e6b9fdddff02180c30d17867fa59baecf'
        '882005466ac9ccfd8c7df0290ac4a4fc2ef1b3268e9766a33d753cd3c062b04fac74621e0b66dea01c3f27a25ad77e7fe6968fb0ba7fc56c884e541d23747fa7'
        'e95d1cf261cc7ec58f4dda0529b19ecf9de65a202b4ea267598603219c45056207d58be1e0634f71bb8189e1317ffba1c89f2c74054d5dc2974ffc5690d2b2e8'
        'e861ab7403e3c240f42d8e98fe594fd53b654162a3071c0becd4f42a44195064804f69da728739e741c47cc304a65531b80e2480552141d2289afeca570ae2df'
        '46efa4d4bd658897ab5742c52e08586c50eed111a1b1e93f89c8c96769856ad96305097106380e630a8cd81be4ac78f4376338ed86f4ef25f6acd4e7c77174bd'
        '05146443d47e9c4e0efa66bca3e8ff0085fa34c4cce9958bc8acddd1d41b29095436f0f6994e7fdc4dd606fd7878e61807f843da0cb586d885d3eadeea1e58b7'
        '2e21a477e5afaa69952d49f497f36d6ec27af0644846af81fbb0b5ff244fc210ef168a704b57491d03369ee860d9fea1387744a1c3cb670a1be86679c2fe4a3d'
        '6708a5d38e527aebf3aaada52172ef8b1c90744b357197f1c5b96def3de82016ee216e1f0876c3b68ccf749aef1e46de9c47329c31da224cc715eceef9cdf6b9'
        'e5a6cade944fc26c905a4385664d31d0263db9106e324285bbd0d378ec3df9a32005d87bb04e5cb5d5cd97e63afb5d3e62fcf8d8402b7064c61fc042f854930d'
        '9b078d87b1bd40c548e3a693188e3aefca2900af665d0dcfa98083d59dc3e4fc69ae4a76a3c7f51d545c923019276855b2ebfaa0a4b2a5dcc20ad08b9c3873f5'
        '9d845064a0383be943406ccbb1bb82a55f23a64797529d4061f997f52f1838ebffb7823ad82a1046329855f386efb0274244d0c7a4eea6153f6dd79a9f5c274a'
        'fc57b20a6390b38ef2b77619afe305b6acef4271873ab195c4a9422357aa244fbd0ac0d2482b2186c86ac15c750279c35ca5ded323bf6201a04ba2f4cb0fc93e'
        '5188322b261cc0b6ab861c4fa505298c0c16d535b2bf57108de6ab4459ce82061b10f54fbc56ee44f5a4336bd8704ff3dcb66bc5edadc4836824b4bde70ec9ad'
        '8b9361df0decc15a49673bcef310998fc8c7c0e80e31c4bdc5a426414dffe4f9ab774a9b4d220ee9003fa9aa5c66e80bcc7306f923b4aad63e1752e9c084a2eb'
        'c2c9d8e3500ee665cd5da11f162f8af1a530048999b197adfd6ac5c93108779a67b183df6aa46e72a83550c70820b09a7ba9b97503e911889ff7bd9a40ce6070'
        'f33f564621f9cc5d2cc83bd04ca3abf479d55d972d01b674ed86e4225a0d20af625f25f6a996022554be902e4fcd6bc16842be67bf511b804ad424fe8f20ba12'
        '6dea04e6c848fbd4ca59e0bdc5f1cc5a820e4a8b4fe16f22a853c31d9337207528cc395971d6263fcb7290e199db9751d979809e7100963ba4eb9233f9c59f09'
        '0e83bd9aa9deaed6f48a830585c809b09e77ef80cee0d96da5ff60f4fef9000f4492e14a4f02fa3ca3f6c119f087e126d65af6ae12104ba636022551b13e3fa7'
        '47da528689b35b46f1212173e4882be52cc56cdcc9a83805c57d4b1cd06509e1c667f1bcbbd469545697466d36c835f2a5f97e6d02f62f36707d520bdfaab5ba'
        'dab14d7c2e130608e0f028a099a1b7d9075166aae9ca2429697a79335dbbf49104f1634df0df33fab7d990f05c8e3e50ff5991a562d5c091fd0f727159dc5fcb'
        '8ad15fcbd94b5103d95e9260382533862157d88bf6c886c6a044641b6b7869706d05ffed1e35648acb878d6f9ddabe01f8f00dc2a68c376654ccd5f671199023'
        'd52f6d7cbe81c43e0fc8d1bb4b6f0569a26df3a770944d7fa1ba5d42daa376c62e697f91b4344d74887979b6d8234b1172499bd7ebd15a015905845dacfd1ae3'
        '63544b8b37122eb2c1cf7da0dec2f9ea7969d40714ea5e00a3435e9ee78826dac2123e3879d87b48161e7c7f1af5b453a2242cacc5e16b59ab9bc48d19f19dd0'
        'a5c449679ec73efe0f3035f32763d623e8d0b851ee93fd97f8943cbb8895b2bd5b2ecec7ce7c77d9ae64899b0925d48d1cc6fcf8f423524c720f500cd6de507d'
        '754bc408e3d9d5f62867a5b22b72b4b5966025de9ae62dc51f503194e94f73061135374c461b12cdf76aaddc40cf79f70a5551157d919ebc9e3f3dcae394ca20'
        '070599d74600ebb6a4b0ba60be0547deb2aa14e766f248f736f58829919dc9c4ca545b8961db300a17656bb8f975ac86b177d00ce3ccb2d0f71ad77e84161d1f'
        '3fba5154e7093131c62feba8cb697a06f932ecaeb0e21a701ad904d1734919b1ce1b6a0fa2b0c39a4e237c7d04215ff75bd361a550b6b23a3b73fbd54ef96269'
        '67ad16b92790c8737f0ac018853e10d8cb7d39fd0a2d0ef02cea54da7dd888069208b1b053ecadbdd40bb06ade164c0f10d66d8594d77a69de34721ad0d355c2'
        '7c617a068847e18d4a388ab0fe4e2e60937e0ef1244d5d9a56dfe2b3be3b7624c538999b78b870798391e4d2e74bf79a175b8734e3bdacd5769910bf1c7c9987'
        '15a19474ceea70dd78a214d09f79785b13ff0a1158c874b03f0479d65c8075366ef10eb704a46737b99f04622f60e40411f865a47a55d84ac78ab96cf759d92c'
        '9b82ed08b5f71ac4ec3cf8f35c531f67d69541fa282a77fe2121c17e0f13fe2df3426dcd97a7ce8dd1b548053d3616c2d1792a8be3a3d680218242ec045cb22f'
        '8ee786924c14a64b7feadc89933c716feab92b690c5ffe5cd24732eac7948a2a9f258142e32ae0a09646175ef0eeefc82ccb89d7c8ecf1ec446e24c859e8a840'
        '31b26c1852c348db0640d585eed8c2161718873b1a626c5e586a980a473ad2b7153b6c64695e4df57560d3c1d93844424d3a49eee7b0e9132960a37dd24f031b'
        '4b899b9ab834f8fa6c671788db1e1161dc5ec2ae28cfd6c2156d44ffdeccab4257cc5b12bfc870aa6018d05a8fb6ee5df4d158fc4ec4715b978cd70b74993d92'
        'faaab6f7b28aa6e1270f7261a8db1f3c9fab96b38f17e21a5372027f700b85a800b4506e06b3db6da8983dc54fba58ce3a251118c32820e6273aa4d2ea495e25'
        '66fa5882580867f49a58fd8fd5077de49777602f93740de0a06eaace18e19b1dae3c4d7ade45f769dc0a1f8175d99c3053bba03941767f15966a82c3ee7ff430'
        '5b4e4b1341eb1e76d67cfbda1534959521958622527391f82204be8ffbfec47860f2a0cee03540aeecac91e22b8d08d620fb4a812d96afb43aa0a6ef35089313'
        'b86f13efeef23555ad9d2b8b0eecf56bd04bc01147341d096a7c4c0d8ce69f21ec731379fbe4154ae6aca83229983ef3b36592f23b99b76a21fd268c6f3cb116'
        'a1cbbe8f8c5252abfe3703fadb8b03bd6eb7df29cc888530ee80dbb03583573ef6c2a4be6ce4a138c912d9d307206b58f27f94f0dad83b88eccce19daa17e25d'
        '27357be0138aac0ce2b49f23229454f70c34b2217ed9221161d6604ab68daa4efb58cc5e900391af158a1807232e1772b2af51ee29f049546c90ccc3c02552ad'
        '9d6ef23e794ea578fb38743c26e40dfd12f2507b0ce69330e032939027d1bb9c1209c98150bf17c87c83609ba350608e441df8c050cf32d6422f2f61ee503511'
        'c38a92a41e8988b94bcf9529a7dded0759b8cab60169950c1ac8f9e46f687687b009aaa855c1e33fed14b3666bc6591c7658f2efa18c032b6d1506eb5c4f2e4b'
        'f8ecb0e573e7e35a89880e917250c43d06c0c5a75cc220c2f5600991e165ac3381b09a19dae595f2f329f6de297fcd3698897a3802b173f98b25db9ab55a2dba'
        '0cbf273169072ec06667ec85084beb31fdaa0731391a547924dbae0e3cfe45f4014f6a3cf6f7d8f1103d7aadcc8eef4e8da316e2f87a3996e647ff5bbc66fe63'
        'e46b5d8a0e47c128cc30f7ef550fabb408bbbfbb1b17bc946a7b657242b355c55437cb7546413459c96946c55cc11bd0498fedc0c80ab2e4685cd06321559f49'
        '0676a1a586c9412c7094cacaba2249867a8aff298794b9f984f2e2a8f9051c73b3ed3449a7c752e0616f0ae5aa3ad2dda02556d7352f77b68ce7b7785f8fd7cd'
        '008fde66177aa64a58bbf77caad4f66283790c918dbb2286249e6ece6eab79484adaf4904edc702345ef4dc1d3c0d0a60ed6b087b7ef7e294766337de3d67b2a')

export KBUILD_BUILD_HOST=archlinux
export KBUILD_BUILD_USER=$pkgbase
export KBUILD_BUILD_TIMESTAMP="$(date -Ru${SOURCE_DATE_EPOCH:+d @$SOURCE_DATE_EPOCH})"

prepare() {
  cd $_srcname

  echo "Setting version..."
  echo "-$pkgrel" > localversion.10-pkgrel
  echo "${pkgbase#linux}" > localversion.20-pkgname

  local src
  for src in "${source[@]}"; do
    src="${src%%::*}"
    src="${src##*/}"
    src="${src%.zst}"
    [[ $src = *.patch ]] || continue
    echo "Applying patch $src..."
    patch -Np1 < "../$src"
  done

  # Ensure amdkfd is avaliable
  sed -i '/^[[:space:]]*depends on DRM_AMDGPU && (/ {
    /LOONGARCH/! {
        s/)[[:space:]]*$/ || LOONGARCH)/
    }
  }' drivers/gpu/drm/amd/amdkfd/Kconfig

  echo "Setting config..."
  if [ $CARCH == loong64 ]; then
    ./scripts/kconfig/merge_config.sh \
      "$srcdir"/config \
      "$srcdir"/001-aosc-loongarch64-16k.frag.config \
      "$srcdir"/002-local.frag.config
  else
    cp ../config .config
  fi
  make olddefconfig
  #make listnewconfig
  #make menuconfig
  make prepare

  make -s kernelrelease > version
  echo "Prepared $pkgbase version $(<version)"
}

build() {
  cd $_srcname
  make all
  make -C tools/bpf/bpftool vmlinux.h feature-clang-bpf-co-re=1
  # make htmldocs SPHINXOPTS=-QT
}

_package() {
  pkgdesc="The $pkgdesc kernel and modules"
  depends=(
    coreutils
    initramfs
    kmod
  )
  optdepends=(
    'linux-firmware: firmware images needed for some devices'
    'scx-scheds: to use sched-ext schedulers'
    'wireless-regdb: to set the correct wireless channels of your country'
  )
  provides=(
    KSMBD-MODULE
    NTSYNC-MODULE
    VIRTUALBOX-GUEST-MODULES
    WIREGUARD-MODULE
  )
  replaces=(
    virtualbox-guest-modules-arch
    wireguard-arch
  )

  cd $_srcname
  local modulesdir="$pkgdir/usr/lib/modules/$(<version)"

  echo "Installing boot image..."
  # systemd expects to find the kernel here to allow hibernation
  # https://github.com/systemd/systemd/commit/edda44605f06a41fb86b7ab8128dcf99161d2344
  install -Dm644 "$(make -s image_name)" "$modulesdir/vmlinuz"

  # Used by mkinitcpio to name the kernel
  echo "$pkgbase" | install -Dm644 /dev/stdin "$modulesdir/pkgbase"

  echo "Installing modules..."
  ZSTD_CLEVEL=19 make INSTALL_MOD_PATH="$pkgdir/usr" INSTALL_MOD_STRIP=1 \
    DEPMOD=/doesnt/exist modules_install  # Suppress depmod

  # remove build link
  rm "$modulesdir"/build
}

_package-headers() {
  pkgdesc="Headers and scripts for building modules for the $pkgdesc kernel"
  depends=(
    binutils
    glibc
    libelf
    libgcc
    openssl
    pahole
    xxhash
    zlib
    zstd
  )
  provides=(LINUX-HEADERS)

  cd $_srcname
  local builddir="$pkgdir/usr/lib/modules/$(<version)/build"

  echo "Installing build files..."
  install -Dt "$builddir" -m644 .config Makefile Module.symvers System.map \
    localversion.* version vmlinux tools/bpf/bpftool/vmlinux.h
  install -Dt "$builddir/kernel" -m644 kernel/Makefile
  if [ $CARCH == x86_64 ]; then
    install -Dt "$builddir/arch/x86" -m644 arch/x86/Makefile
  elif [ $CARCH == loong64 ]; then
    install -Dt "$builddir/arch/loongarch" -m644 arch/loongarch/Makefile
  fi
  cp -t "$builddir" -a scripts
  ln -srt "$builddir" "$builddir/scripts/gdb/vmlinux-gdb.py"

  # required when STACK_VALIDATION is enabled
  install -Dt "$builddir/tools/objtool" tools/objtool/objtool

  # required when DEBUG_INFO_BTF_MODULES is enabled
  install -Dt "$builddir/tools/bpf/resolve_btfids" tools/bpf/resolve_btfids/resolve_btfids

  echo "Installing headers..."
  cp -t "$builddir" -a include
  if [ $CARCH == x86_64 ]; then
    cp -t "$builddir/arch/x86" -a arch/x86/include
    install -Dt "$builddir/arch/x86/kernel" -m644 arch/x86/kernel/asm-offsets.s
  elif [ $CARCH == loong64 ]; then
    cp -t "$builddir/arch/loongarch" -a arch/loongarch/include
    install -Dt "$builddir/arch/loongarch/kernel" -m644 arch/loongarch/kernel/asm-offsets.s
  fi

  install -Dt "$builddir/drivers/md" -m644 drivers/md/*.h
  install -Dt "$builddir/net/mac80211" -m644 net/mac80211/*.h

  # https://bugs.archlinux.org/task/13146
  install -Dt "$builddir/drivers/media/i2c" -m644 drivers/media/i2c/msp3400-driver.h

  # https://bugs.archlinux.org/task/20402
  install -Dt "$builddir/drivers/media/usb/dvb-usb" -m644 drivers/media/usb/dvb-usb/*.h
  install -Dt "$builddir/drivers/media/dvb-frontends" -m644 drivers/media/dvb-frontends/*.h
  install -Dt "$builddir/drivers/media/tuners" -m644 drivers/media/tuners/*.h

  # https://bugs.archlinux.org/task/71392
  install -Dt "$builddir/drivers/iio/common/hid-sensors" -m644 drivers/iio/common/hid-sensors/*.h

  echo "Installing KConfig files..."
  find . -name 'Kconfig*' -exec install -Dm644 {} "$builddir/{}" \;

  echo "Installing Rust files..."
  install -Dt "$builddir/rust" -m644 rust/*.rmeta || true
  install -Dt "$builddir/rust" rust/*.so || true

  echo "Installing unstripped VDSO..."
  make INSTALL_MOD_PATH="$pkgdir/usr" vdso_install \
    link=  # Suppress build-id symlinks

  echo "Removing unneeded architectures..."
  local arch
  for arch in "$builddir"/arch/*/; do
    if [ $CARCH == x86_64 ]; then
      [[ $arch = */x86/ ]] && continue
    elif [ $CARCH == loong64 ]; then
      [[ $arch = */loongarch/ ]] && continue
    fi
    echo "Removing $(basename "$arch")"
    rm -r "$arch"
  done

  echo "Removing documentation..."
  rm -r "$builddir/Documentation"

  echo "Removing broken symlinks..."
  find -L "$builddir" -type l -printf 'Removing %P\n' -delete

  echo "Removing loose objects..."
  find "$builddir" -type f -name '*.o' -printf 'Removing %P\n' -delete

  echo "Stripping build tools..."
  local file
  while read -rd '' file; do
    case "$(file -Sib "$file")" in
      application/x-sharedlib\;*)      # Libraries (.so)
        strip -v $STRIP_SHARED "$file" ;;
      application/x-archive\;*)        # Libraries (.a)
        strip -v $STRIP_STATIC "$file" ;;
      application/x-executable\;*)     # Binaries
        strip -v $STRIP_BINARIES "$file" ;;
      application/x-pie-executable\;*) # Relocatable binaries
        strip -v $STRIP_SHARED "$file" ;;
    esac
  done < <(find "$builddir" -type f -perm -u+x ! -name vmlinux -print0)

  echo "Stripping vmlinux..."
  strip -v $STRIP_STATIC "$builddir/vmlinux"

  echo "Adding symlink..."
  mkdir -p "$pkgdir/usr/src"
  ln -sr "$builddir" "$pkgdir/usr/src/$pkgbase"
}

_package-docs() {
  pkgdesc="Documentation for the $pkgdesc kernel"

  cd $_srcname
  local builddir="$pkgdir/usr/lib/modules/$(<version)/build"

  echo "Installing documentation..."
  local src dst
  while read -rd '' src; do
    dst="${src#Documentation/}"
    dst="$builddir/Documentation/${dst#output/}"
    install -Dm644 "$src" "$dst"
  done < <(find Documentation -name '.*' -prune -o ! -type d -print0)

  echo "Adding symlink..."
  mkdir -p "$pkgdir/usr/share/doc"
  ln -sr "$builddir/Documentation" "$pkgdir/usr/share/doc/$pkgbase"
}

pkgname=(
  "$pkgbase"
  "$pkgbase-headers"
  # "$pkgbase-docs"
)
for _p in "${pkgname[@]}"; do
  eval "package_$_p() {
    $(declare -f "_package${_p#$pkgbase}")
    _package${_p#$pkgbase}
  }"
done

source+=('001-aosc-loongarch64-16k.frag.config'
         '002-local.frag.config'
         '0001-BACKPORT-FROMLIST-drm-Makefile-Move-tiny-drivers-bef.patch'
         '0002-FROMLIST-drm-radeon-Call-mmiowb-at-the-end-of-radeon.patch'
         '0003-FROMLIST-LoongArch-Update-the-flush-cache-policy.patch'
         '0004-FROMLIST-USB-core-Enable-root_hub-s-remote-wakeup-fo.patch'
         '0005-FROMLIST-scsi-Bypass-certain-SCSI-commands-on-disks-.patch'
         '0006-FROMLIST-PCI-Use-local_pci_probe-when-best-selected-.patch'
         '0007-FROMLIST-PCI-Prevent-LS7A-Bus-Master-clearing-on-kex.patch'
         '0008-FROMLIST-RFC-drm-amdkfd-disable-HSA_AMD_SVM-on-Loong.patch'
         '0009-BACKPORT-FROMLIST-drm-ttm-save-the-device-s-DMA-cohe.patch'
         '0010-BACKPORT-FROMLIST-drm-ttm-downgrade-cached-to-write_.patch'
         '0011-FROMLIST-PCI-Release-BAR0-of-an-integrated-bridge-to.patch'
         '0012-FROMLIST-mailmap-map-all-Icenowy-Zheng-s-mail-addres.patch'
         '0013-FROMLIST-net-phy-motorcomm-Support-YT8531S-PHY-in-YT.patch'
         '0014-FROMLIST-net-stmmac-Add-glue-driver-for-Motorcomm-YT.patch'
         '0015-FROMLIST-MAINTAINERS-Assign-myself-as-maintainer-of-.patch'
         '0016-FROMLIST-rust-export-BINDGEN_TARGET-from-a-separate-.patch'
         '0017-FROMLIST-rust-generate-a-fatal-error-if-BINDGEN_TARG.patch'
         '0018-FROMLIST-rust-add-a-Kconfig-function-to-test-for-sup.patch'
         '0019-FROMLIST-PCI-loongson-Override-PCIe-bridge-supported.patch'
         '0020-BACKPORT-FROMLIST-loongarch-wire-up-memfd_secret-sys.patch'
         '0021-FROMLIST-loongarch-retrieve-CPU-package-ID-from-PPTT.patch'
         '0022-BACKPORT-FROMLIST-ACPI-PCI-check-if-the-root-io-spac.patch'
         '0023-FROMLIST-PCI-MSI-Conservatively-generalize-no_64bit_.patch'
         '0024-FROMLIST-PCI-MSI-Check-msi_addr_mask-in-msi_verify_e.patch'
         '0025-FROMLIST-drm-radeon-Raise-msi_addr_mask-to-dma_bits.patch'
         '0026-FROMLIST-genirq-reserve-NR_IRQS_LEGACY-IRQs-in-dynir.patch'
         '0027-FROMLIST-dt-bindings-interrupt-controller-add-LS7A-P.patch'
         '0028-BACKPORT-FROMLIST-irqchip-loongson-pch-lpc-extract-n.patch'
         '0029-FROMLIST-irqchip-loongson-pch-lpc-guard-ACPI-init-co.patch'
         '0030-FROMLIST-irqchip-loongson-pch-lpc-add-OF-init-code.patch'
         '0031-FROMLIST-irqchip-loongson-pch-lpc-enable-building-on.patch'
         '0032-FROMLIST-kbuild-install-extmod-build-do-not-exclude-.patch'
         '0033-FROMLIST-LoongArch-Select-HAVE_CMPXCHG_LOCAL-in-Kcon.patch'
         '0034-FROMLIST-LoongArch-Add-HOTPLUG_SMT-implementation.patch'
         '0035-LOONGSON-irqchip-loongson-eiointc-Improve-IRQ-affini.patch'
         '0036-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
         '0037-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
         '0038-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
         '0039-LOONGSON-dt-bindings-dmaengine-Add-Loongson-Multi-Ch.patch'
         '0040-LOONGSON-dmaengine-loongson2-mcdma-New-driver-for-th.patch'
         '0041-LOONGSON-LoongArch-Add-canfd-support-for-ls2k3000.patch'
         '0042-DEEPIN-net-stmmac-fix-potential-double-free-of-dma-d.patch'
         '0043-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch'
         '0044-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch'
         '0045-AOSCOS-loongarch-re-introduce-add_numamem_region-ini.patch'
         '0046-AOSCOS-loongarch-basic-boot-support-for-legacy-firmw.patch'
         '0047-AOSCOS-loongarch-parse-BPI-data-and-add-memory-mappi.patch'
         '0048-AOSCOS-loongarch-add-MADT-ACPI-table-conversion.patch'
         '0049-AOSCOS-loongarch-correct-missing-offset-of-PCI-root-.patch'
         '0050-AOSCOS-loongarch-fix-missing-dependency-info-in-DSDT.patch'
         '0051-AOSCOS-loongarch-fix-DMA-address-offset.patch'
         '0052-AOSCOS-loongarch-fix-HT_RX_INT_TRANS-register.patch'
         '0053-AOSCOS-arch-loongarch-add-la_ow_syscall-as-in-tree-m.patch'
         '0054-AOSCOS-la_ow_syscall-add-kconfig-for-module.patch'
         '0055-AOSCOS-drm-loongson-add-ls7a1000_support-module-para.patch'
         '0056-AOSCOS-drm-amdgpu-disable-ABM-Adaptive-Backlight-Man.patch'
         '0057-AOSCOS-MIPS-Check-address-space-in-ADE.patch'
         '0058-AOSCOS-kvm-disable-enable_virt_at_load-by-default.patch'
         '0059-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
         '0060-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
         '0061-AOSCOS-USB-core-only-enable-root_hub-wakeup-on-MACH_.patch'
         '0062-AOSCOS-ACPI-scan-Add-pwm_lookup_entry-for-PWM3-on-LS.patch'
         '0063-AOSCOS-Revert-FROMLIST-rust-generate-a-fatal-error-i.patch'
         '0064-BORE-linux6.19.7-bore-6.6.2.patch'
         '0065-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
         '0066-BACKPORT-FROMLIST-perf-annotate-Use-jump__delete-whe.patch'
)
         
# vim:set ts=8 sts=2 sw=2 et:
