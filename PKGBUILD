# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.0.12.arch1
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
  config.x86_64  # the main kernel config file
)
validpgpkeys=(
  ABAF11C65A2970B130ABE3C479BE3E4300411886  # Linus Torvalds
  647F28654894E3BD457199BE38DBBDC86092693E  # Greg Kroah-Hartman
  83BC8889351B5DEBBB68416EB8AC08600F108CDF  # Jan Alexander Steffens (heftig)
)
b2sums=('2c53f205a940b0f9f68653b92ef46d49f828cbef3cfa8cf94d050c8e6df05c4fcaa4f9b9681b9130b14e3c790d31208eb244d123249a93e35e8e6165f3d858c9'
        'SKIP'
        '26230d1a111b24fe9239273acdfacda37c5bf009f861c448ad25392dcca433514246d629a077ce5c66478c7e0f4e5477ce5f95c91d08b3a02cc87bb35b849bcf'
        'SKIP'
        'dafee1f25d231199834869a5ce76a85eebb3c1ceac86f604270e93a40a22f29bcf797822481aff5aa5020c12359b9ad87ad8e0d36727166522510a07539d69d4'
        '652069e50060a3d84530f004f7064d98d6ac9bb02e690a3510d092d0df17598c9b3d564ae07fdb0dbbecc68d2d12d58c4c78c02cc08fbcbb8c01ba6e6256d922'
        '7b59edcee464209b0ff2e4b06c58babdc3d56801e1f73351bf6f140b39c53feb96d786434cb8b0db39ac94cf4ef905dec9c158758c4e41aeea16b9fa7f21c3f2'
        '82bb78c66948a572f35c8f0b6ba924e122a075632efb304693dfad2331898accdc80610d187e93ba5e18edd7f12131bea1ea2cd31b4987047cfe1bd6079eb3e6'
        '39dedf68e8228601d41b5b1e925bf87041b6a346ef721cca7fc7c04a9c0939ccd44ae373462b3f47c88c3aa23bc958537038ddd76ccf09b6db109e9ac564b524'
        '2e7125dbc01b3bed0fc8611392b6c78dabe04e4f0db6234cd69959da5ccbec3cfce59a2076cafbaa205156a7aca4c7329bdc12dc149c479206d5445227dbd8bc'
        'c6c52598bdc9f445931695615736a4cbbd3c0cd0751732bd064deb77c6fec16bf5d9a895121af69d5b058018a8a4a42b9840e08934582a759cfcf93ca9aca2f6'
        'e42c0304944542ad8a5d4d457d356392a74aed9bb9953e81ff248314d4587b81a39197730bc4f22c463a4b979ddda1d8a556f8bb9c759eacb48f1635ba958fe9'
        '5128c764fcfbe97cbcafa07a705b83af8574bbe40ba334065ab06ef724878479ddc649c45650c1eeee5e6810f9466a4d689cb21fbea083f2aa6d7b0672aa693a'
        'c75996a581997b46b153b3af2c26ac7f5d3c81d081f3d8947c497385a9c68dccc54abb945efd3de6c89d495bb06e2c5eeb123ee71a0b90f3baf9b444ca12264e'
        '2a68b9da1730a8601e24ac87896ec4e813284b978fa8a5bb287c26eba5483b487ce5bd1aca96d076974b03e7cd17fdc48ea10665a803b96cf95798ffcd87af29'
        'a7bf4447af7607459b48f4a90df5ab327d07312a62c70b6d552f9107f18649d820d28a4babd97e776cb79874f9fc4899879aa7cf03c55f066269c6e2c73ba3ee'
        'e09596ac9ad12da102ec2b4798dca5a94707dda0380ffefc1fc99bbb6073fbb862dd3797c28b90457dee45bfeeeadd6bd07cc9fd0dafffc713f94c895f628a9e'
        'c07abe62ef1f8cb0514ff112ed691697cbfac43260fb0c978c6788d53a72ffd23dbfd73b4b567b2b3da358c2f1da7067f2236e0f6919525eb19ea24d32d13749'
        '0754c20407c1f3e82ed284cd3b176c41004b2cb66c70f1c5b8877350d7f4517899245fa3525141a981a707fc01b39d906b708ed7b127a2769fd04ee96d2f2cfb'
        'ba1f43e48e371f6e859da06a31367c535ca0a08c801fdfb4fa674cfd31e62ce493f6cfe83019874d0c01619c0190020c9bd4d1bfeede546c84ee8cba40f380b4'
        '2da85502b13b1d7a44feb6f3a1197ec7133ecd094d3b6502d05d8065d8ba68aeec2806d1c55acb170a115a2d9cad382cb2f0b60ab8f8eb23a8612966391fe9f7'
        '4b27d5619a3baf1544202f2729f2fadd5e67419c5dffa091c4111db66aaa3067d128cdab5bde1ce76650f021f1fc8574da11e0c2086a05db1bde3a238fabc3e8'
        '620bbb4cc1859e8893b99dbb34c59cd52ebe987a07ceb85887d0d70c095cea495f8f4b9090f3c0ef9e6442411325f18c4a295f33e911c1e63b928540f425470c'
        '497c6ebe436236e0d397d1111cd0aa5dc32c7ed938a9d682a4a6037d0c8c38cd3eb2364dbf20bac1595b989a71e00ee3d665ebc4cde42135e3d6c992a46d29a8'
        '1e448ef2a73bdd3728aed19f8d1edc334b9d763e7f8cbf1431ff2cfe6fd8099d9b5bcd7cdffd6b3b2451ad77720a9b8750bc8620b4e9af528470801d0bf2ac73'
        '962ecbdf7b914c16561105391ac22d08321be2358c738ce5ebd239367f52e2514e250fdec51851ef0c74be0b45132c3fe571e5fc1fb91382dfe81452c5494ed4'
        '7fab3947be452e135140270c7001b2f96d5dcd031e6e621cb81fb7439b692931933efc94c2f3dd058d8b8e8f38e36fd4629e70b6631b4ea2940250f5043f0e32'
        '8ac47feb37e5db82a331700c4722b135153238e4bf3dad40c00360352eebedc20927d11aefeb37af984734de1fbfd80580ca55ff4620203d7019f40f891aae86'
        '9f849ebce3a38fc5bb923b307ae5db9882a2c09ebfe6046146773ccea36d91fb6b8bdcf524abd3618888ad6e5de75aa2654561cadbf5e83465a472a751a86ae4'
        '332de7421439c5cbc652d4c78a873d01bb7fbfa68eae24e8a02c8132862b1aaf6079bb72f200bef134a60655f7dcb79de7107595e47186be104f587f8fc841ea'
        'c3af99e9ea661fc04b014803b15ab30c40dd36f0a06f1380e1f36e7b6fb335cb1fe7584267841e112a53bb3dc45535cd07ea792c5ec3ac57c7e93a3f2534e574'
        'afd069dc42cfb89b41b618ccca53da9cb0ed0b4db6b7c661ece04121cfa40c5695433a7b28b500b5ce0944b50e9e1d348a829d116c61fc9c5783d71554e7966c'
        'c050778807342c6eb9691c7eca4a3e74bd6ba3104999a5de67e7f4393efd9377fb03ac9c4b298e1f7a893e679dee2e99eaa639d926c461e35088a103fc6709d3'
        '0106f7c4f1265dfa5c91de860b9e7655bf78164c63d954f3754e02814ce3bd00c00ee911c02924e9ff20f458c354d46c08a6ea65d8e474279874b29d5a81c70f'
        'd3bb1e45d8120e87eb353bf4bd8d2ba85df777fe1440509a6aa177d5b969e987b707ab6116f9ccca4dc074473086f4f5a05f1029d66783433ba08490d621afa9'
        '5bb2c409cfdd9993c6f732dfb5dfed8fbe6faa39953035f6127e99d6b23af9083301e4bd8a7b41ed396e9ed8a854d32717461b232125b2edec7bd3c5f5f8a626'
        '7243e64fb9c03a33ad7d21188128b056f60fbffba7abb87c5404f0e5089933f39d6483d2c561093724bce2c4e939da39f6937792d3e6bd21f1c55a0658b1eb6c'
        '597ab69c754d215e277807d85c7958ecfe8057622abc8f2ccd6fd29d129d646ad4e2394bd748cd319a485572e70d43f9eadd6e3115f34a363c66d2d8f2d93d32'
        'a37c54e9a10e1f97f2b7e42bfd612a764b3d3239ce2d5c45a4a5acc7520cba6a8c4bbf9c3498e8fb35ebb5aa9f164b1cb8619bfc5bef189eba93f0aaba7363fc'
        'b3bda184f8da6def9d3043a499e7dc1fc0c1f8fdef08d31fa04bc0ada651e4f887b03b3e204d1d554a88fcf043dffc5ac2b5075e29462cd46ef892b50d164ac3'
        '5f038253868ed7affe1b4017a397c43e35185cb82c75fb21e8f7318291a41cdc9e43d9f58f3f45d2a3d11626403812ba7f3ce4ff8d1281fe7989ce63536b9734'
        '35fa89f3dbc6174dbc65853665cb97c85827ca74d993d8b3c03320f9976e7935d2eed4a8bdebb921a566e0fed161c1f8a710849ddec6785980ea797a826a772c'
        '529823125386a0d4c480b5301c93565d1c6c08e6d8cfeb53061538272da8a62b5d93039f3d9be630252af1d3e933dd98ed32a5b5eb57e2166e81d0a3067c5de2'
        '960c46dbd0c0cf9cd8e9141984d9693923633776d8a6ec13be1e62dbd7ac95e56b324d2a904f0bd3ddf3da4a42441264822d28d24aa5e076a505e084f1851986'
        'efe6a01b3f48d02d43f558fb36ef6933dabd33c05a0f888076d25601d38ce7113747b91814621702efa830c13f7a5c0e3a40d0e4327bf351129d33f25e03bd24'
        'dd06f3dfc80ecc766f8d38906ecaed2bad1d30f52d977549e3f437631d218e3d3516078df54d5ca5e67aee3ab3f26457c668e405e9be14fc9de2b98f4d582cf3'
        'c12ff361b98a8c68a978c9c3a068ac25c441ed3a96ee9a253eba6a363878463967dbbc86de5d24bffd88c87715d6364c6dd8fe12f5f8b8685309cf7cd5bb3853'
        '637230b3ee809a716f7d42023342e7c0e335f035228810299cb79cdbb7af71d5e5aa2f0a80ace14b2a716ad077add4df59ebac0b99c581bf5305d1cefe9559d3'
        '96cb9d4735526ff8b119212e705adb67e037b2b00e052d34ff8daa7647b69cd39b9fb535dbbc2b86416e3f46d5331c59de830517cbe1a86ff215415908875fee'
        'd0aea66d7c93eea6f9f4f439261e78d2c615e8bc6c492061aae78f350367b78565d6e62d83fc05f16f10071275c70e8f8e9b4f035159f2c2034a10eb9fdec6e2'
        'c41ef0f41c4867c4228f6fdda69b73eecb64b19adc4adfc60a700bd458e778b6480f4c1836a5c0479e98cfae7d6e14110e500a159adb4ee919a258ae980edaaa'
        '0ab284ec7343ec493a7a599014a869858c77835c916fc08ab46bd69d2cf6c161dbb826da0487ff6eed4c368835c7287f4f465cee6dbaa0218e378f3359454f2a'
        'd2e5c13647ca13f62a422fb28fe2b4d4bfb915645b7861a1390517e64fc05fe556f7ba7d84836115b023e302e51b88cbda0b937d072d136c259c5094e5f90532'
        '2c736bb2c7d2c015fbbdad360d3588892153c385d5f3681ab1333ec1555e1a72dd28a252c2c80fa6ec11e54fd6795ecae543d76a8c831d0df68a39e4271b19cc'
        '5f09aa10f92307a3d1a37f7000ea1a746ea792869129832d9489dd98ae78b87cac5edd7530a55aee83b5bb8666952c6a10a5ddbc4208cd8997f3f0353db95bc7'
        'e557fece636fb19342cb592de792be2ef1671bebb62c12f0e792b9220e0b23af8fc6a3093fadcade71fbd89cf6760294cb931307dc49ae14a294e61f6136448a'
        'a732057711f5040dd4f602bf47fec02805662a9bc2648c955179050d5ddfa1d12e55d2682739d9a4b756baceada5a92fcfc7c9223df88c685a14ca68bf6b38a2'
        '7a88e85d3535c7d96a688a91de5fa72fbcebb9586dbd7b1578878e8ca55353c7cafab12a0541745a24154a00707d4945348218c286aea7ddaac149bac21c9f25'
        '714dacb2ea93ffe2f2ba885a7bfd30433d4b8b3ffd916788b3415c0953ba6cc2963da4cd29553498dc54a47f79992632e54b3facd036d1dbe8a06d0d1e4d9f2e'
        '3785570a0897a852453267cb377e8558fe0b92b36657024eab292d4237db8e8e3f7ba04f9c813a6e8cad16b1d91b80e9949d2de0f1dc167a5a9069280404bfc3'
        'c14e62a83cfc719cdd5a44ab93d95d2c59eadfd146867d12cae33c0377b67aa4750d704ba9f5e67934e1178ce1ccdb4b978b8130d89b6cad28b6e127a98b7920'
        '15bacda810c4d4c177d16fdb19ccb94fa202dc184b61be63c39d66d66853194cbec320d3361668e480ef3a3affea267b45ffb2db514cad40699bb0bb9f0d9017'
        '4801f0b24632456e1600b8bfcb153d3368f6e2c4ecb6cbd17c8e4cf7315f9e060b163d607aa64994f538ea1c78fa6345218c012c437f55d14c2705fe077eaea8'
        'e82c3d8c733fa0a15472e93bcb60f4fbaf01e148f271f72f0482277f750c06c8a11d14083ae1b646e035869bc4c20481ebf34988a30531ad4e74ee56d5874362'
        'b6900ea16bc9a722d874bdaba86bb7dfa09a13ffa64153416d783a7a1cc0ed92a123a62745b2d70f3c7af89ea8da90e2d5407c701acc6073c0dea8091e47b387'
        '1ce25a6f12bf546b75fc01d8731008ac40e4211ddaa03932f6e935b47d9b15668290e6542f37ac4a5a8cbb10af0e04a6fe5d45b177e8703593df20283e480ed1'
        '93a599f7965ee9a668a631b63ce20ae718bc3d0a7e0cdea4ccdf565969b88a33c92d92736f4f831c501c1cda9f6b6b8b38636793d8d3f855dc43e1aa14020c39'
        '0203ea735d86f58e0f528eeea15d804def46c1a42d5159520a2fcdcd0459ae8d4b3aa90478808ce4b23ba007d331f1791fe38501c94d4985266c2ca8b7cb11bc'
        '3edfc46104470cd3fcfeb6b1770e46a9868850b085cb259d5063f333456697096e468bde2a77bd2349261f5753dcdba6de1c46753ed0c01e92e216fddc9da95c'
        '4286a3d56b97bbdfa036a884b441d1b63cf567075b3331f69a944a81654a5e8029b3389a0ebfa892a4ff41ad6e252d62502eef3f8acfbf334ef56ee45ef6b96e'
        '1b891476e61eeac72e715e6ec69916d3507897e96ee666180ee3068f9e1a274d74a303bb4766177775218e3d74fcaf76ec39ede2c104f725ae79ab601b780582'
        '1790de757ee85893e67ea131411a35fa8e7a42229bd7b09675198c99f88fc1a1827a62013fb3e234af4a54d54e5b34999f7a5dac7be9dbf68f93189148e47caf'
        'bf8d62ed74ca26a1eaa425401483ed853ae95daadc3a12314b17b42888d62225f56bd5bfbc264077588713512baf87352a988892fd20380764c064ef71b10703'
        '1d0f8bd972ac5361f15700f76e2047c7e90f48caa081425995629a235d140a424a3eba977fcbf94ff0a52610b55bdcc3c7fdce6db4814713cf2c23a8e4e99057')

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
      "$srcdir"/config.x86_64 \
      "$srcdir"/001-arch4loong64-addition.frag.config \
      "$srcdir"/002-aosc-loongarch64-16k.frag.config \
      "$srcdir"/003-local.frag.config
  else
    cp ../config.x86_64 .config
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

source+=('001-arch4loong64-addition.frag.config'
         '002-aosc-loongarch64-16k.frag.config'
         '003-local.frag.config'
         '0001-UPSTREAM-LoongArch-Override-arch_dynirq_lower_bound-.patch'
         '0002-UPSTREAM-dt-bindings-interrupt-controller-Add-LS7A-P.patch'
         '0003-BACKPORT-FROMLIST-drm-Makefile-Move-tiny-drivers-bef.patch'
         '0004-FROMLIST-drm-radeon-Call-mmiowb-at-the-end-of-radeon.patch'
         '0005-FROMLIST-LoongArch-Update-the-flush-cache-policy.patch'
         '0006-FROMLIST-USB-core-Enable-root_hub-s-remote-wakeup-fo.patch'
         '0007-FROMLIST-scsi-Bypass-certain-SCSI-commands-on-disks-.patch'
         '0008-FROMLIST-PCI-Prevent-LS7A-Bus-Master-clearing-on-kex.patch'
         '0009-FROMLIST-RFC-drm-amdkfd-disable-HSA_AMD_SVM-on-Loong.patch'
         '0010-BACKPORT-FROMLIST-drm-ttm-save-the-device-s-DMA-cohe.patch'
         '0011-BACKPORT-FROMLIST-drm-ttm-downgrade-cached-to-write_.patch'
         '0012-FROMLIST-PCI-Release-BAR0-of-an-integrated-bridge-to.patch'
         '0013-FROMLIST-rust-export-BINDGEN_TARGET-from-a-separate-.patch'
         '0014-FROMLIST-rust-generate-a-fatal-error-if-BINDGEN_TARG.patch'
         '0015-FROMLIST-rust-add-a-Kconfig-function-to-test-for-sup.patch'
         '0016-FROMLIST-PCI-loongson-Override-PCIe-bridge-supported.patch'
         '0017-FROMLIST-loongarch-retrieve-CPU-package-ID-from-PPTT.patch'
         '0018-BACKPORT-FROMLIST-ACPI-PCI-check-if-the-root-io-spac.patch'
         '0019-FROMLIST-kbuild-install-extmod-build-do-not-exclude-.patch'
         '0020-FROMLIST-LoongArch-improve-logging-of-disabling-KASL.patch'
         '0021-FROMLIST-LoongArch-Add-flush_icache_all-local_flush_.patch'
         '0022-FROMLIST-LoongArch-Batch-icache-maintenance-for-jump.patch'
         '0023-FROMLIST-LoongArch-KVM-Add-DMSINTC-device-support.patch'
         '0024-FROMLIST-LoongArch-KVM-Add-dmsintc-inject-msi-to-the.patch'
         '0025-FROMLIST-LoongArch-detect-and-disable-sc.q-if-errati.patch'
         '0026-FROMLIST-ACPI-Enable-FPDT-on-LoongArch.patch'
         '0027-FROMLIST-LoongArch-add-spectre-boundry-for-syscall-d.patch'
         '0028-FROMLIST-dmaengine-loongson-New-directory-for-Loongs.patch'
         '0029-FROMLIST-dmaengine-loongson-loongson2-apb-Convert-to.patch'
         '0030-FROMLIST-dmaengine-loongson-loongson2-apb-Convert-to.patch'
         '0031-FROMLIST-dmaengine-loongson-loongson2-apb-Simplify-l.patch'
         '0032-FROMLIST-dt-bindings-dmaengine-Add-Loongson-Multi-Ch.patch'
         '0033-FROMLIST-dmaengine-loongson-New-driver-for-the-Loong.patch'
         '0034-FROMLIST-LoongArch-add-i2c-clocks-and-clock-div-para.patch'
         '0035-FROMLIST-iwlwifi-add-new-pci-id-for-6235.patch'
         '0036-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
         '0037-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
         '0038-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
         '0039-LOONGSON-LoongArch-Add-canfd-support-for-ls2k3000.patch'
         '0040-LOONGSON-LoongArch-Align-FPU-register-state-to-32-by.patch'
         '0041-LOONGSON-cpufreq-loongson3-SMC-boost-test.patch'
         '0042-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch'
         '0043-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch'
         '0044-AOSCOS-loongarch-re-introduce-add_numamem_region-ini.patch'
         '0045-AOSCOS-loongarch-basic-boot-support-for-legacy-firmw.patch'
         '0046-AOSCOS-loongarch-parse-BPI-data-and-add-memory-mappi.patch'
         '0047-AOSCOS-loongarch-add-MADT-ACPI-table-conversion.patch'
         '0048-AOSCOS-loongarch-correct-missing-offset-of-PCI-root-.patch'
         '0049-AOSCOS-loongarch-fix-missing-dependency-info-in-DSDT.patch'
         '0050-AOSCOS-loongarch-fix-DMA-address-offset.patch'
         '0051-AOSCOS-loongarch-fix-HT_RX_INT_TRANS-register.patch'
         '0052-AOSCOS-arch-loongarch-add-la_ow_syscall-as-in-tree-m.patch'
         '0053-AOSCOS-la_ow_syscall-add-kconfig-for-module.patch'
         '0054-AOSCOS-Revert-rcu-Fix-rcu_barrier-VS-post-CPUHP_TEAR.patch'
         '0055-AOSCOS-drm-loongson-add-ls7a1000_support-module-para.patch'
         '0056-AOSCOS-drm-amdgpu-disable-ABM-Adaptive-Backlight-Man.patch'
         '0057-AOSCOS-kvm-disable-enable_virt_at_load-by-default.patch'
         '0058-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
         '0059-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
         '0060-AOSCOS-USB-core-only-enable-root_hub-wakeup-on-MACH_.patch'
         '0061-AOSCOS-gpio-loongson-64bit-Add-LS7A-GPIO-interrupt-s.patch'
         '0062-AOSCOS-ACPI-scan-Add-pwm_lookup_entry-for-PWM3-on-LS.patch'
         '0063-AOSCOS-Revert-FROMLIST-rust-generate-a-fatal-error-i.patch'
         '0064-AOSCOS-LoongArch-Canonicalize-the-CPU-package-ID-fro.patch'
         '0065-BORE-linux7.0-rc2-bore-6.6.3.patch'
         '0066-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
)
# vim:set ts=8 sts=2 sw=2 et:
