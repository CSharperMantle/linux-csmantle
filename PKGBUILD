# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.0.5.arch1
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
b2sums=('10b9e0c47da78d605d1ff45054e0693045bcbfe9ab1437ababe9b58383a193c89d5a36f9ee806266c743ae8a320ac60620b3e306751ead2e1a77150cf0d985eb'
        'SKIP'
        'd2c2b71ca0e7ee471007df333cb0d04e99ae3130175ca16af1c10c3b208fbaa303e06b1dbd398c483ec1e7953761c04cc52c542f46e4f187367b8c5bd79b0005'
        'SKIP'
        'dafee1f25d231199834869a5ce76a85eebb3c1ceac86f604270e93a40a22f29bcf797822481aff5aa5020c12359b9ad87ad8e0d36727166522510a07539d69d4'
        '652069e50060a3d84530f004f7064d98d6ac9bb02e690a3510d092d0df17598c9b3d564ae07fdb0dbbecc68d2d12d58c4c78c02cc08fbcbb8c01ba6e6256d922'
        'e31028c4d808982740991d450b7dfd77e36bfbb620205ee7a34b3c6937dcf75202d77a136e58ffaa325995d929f8a1095b6f6467992174d2b9c5fad034eee418'
        'fa656e5f44c069d93baafd37e4a947ca90aa9805c391b963d5ad2cfee99f75e620d6c86587a1f07fb3640a94f6f84917626cea5e901ef0db00da2c275630645a'
        '3806ba5dc10b0f4ba02b9454c2fdd75c852c6877dd829597b2d8a16da82793a46820a5234916cdab08947aa31dad3acc1f1865ac050e5c51673ea0ecd06f18f3'
        '9e05da23d5d5833abc1e514dce937c1ca473326773737b95b541a551e9d4d7d9da96c61989dd26ecb89fe8d21b2dad3e51b85592fdd38e5d54722fbb7650b1dd'
        '57ba958a843fb07cbbdf7f5458834779ac1ba3e498f58ac26afab535e32f4b5a00eb58e70b223c4a51c0b69cd09b9c719e2870755ed2cec6d0f3083aba050b8c'
        '99a48a04dd1b5452f3c0c5a75dc016fa23d3a233973982a93c2f4ace93e003fd558cd89b8474c0c0bd3ffc80ef1466444de107a93dfa0e006093e4181261f677'
        'cdf03a3218b8ac77135ef11178072ca93fb80d8e73b31d0b2bf65f6ad862ea9c34dcd045d78306282f52f41a78a64d2c25faa3d5767dbe6035b380a5edbb6d67'
        '67a1b575f7e629299f0dda96d18c760f36404ed9d20fd7eca65451cc24f439f88016961edafe9c3ee401ec718bb45d80e92858277960ba852581cfa16877255b'
        'cb200320ce2b0716898e5198510fb8d81ed9d0ce142e343c4037e6d3a3a7fff9ac42ac809af266108bb549cf7632a0891cf8ead319a26d561b01068750b36dea'
        '1991911e8a7019e611cf4b4d1c2e04f5f18542afd4b53cc1fa9f9432049b57dbac932658aac029f9be84be9cf1296f0ea81b5c2ed858f39a199428ae546372e1'
        'c7f9054e49ec7ae3dc649162f156389b60ed670247be8f1bda0826f73e1f45f31ced69db59799fec190f9d75dd7ccda1acecbff41070d44999bc5e3ea2e46d47'
        '7a3d04735cde8e8318f1b078272f01c1f814a33d9f07be452d1ef4ffca7008ba910fad21ba13364f5363b7ea17441872d4b717f578e0abf203188a889d3c8f68'
        '97aaeb8a8344da68ffa6871ac6674dab5fc5d76658aa207b0cbb088fc6bdb90b5ccdf17de58344b238cd5ef3ae18e6f0a81fc129e0f9b5e546e08d0b538d1d1b'
        '9cdf4a987033345937e46ba830fe343f3f9e1a6e8a641f1c1a2fd99b9f215477bf803d349cd9ad8a669348a24da297fb84671af0ce41cdde047f97e3167187c3'
        '87bf9b8270ccf9be09132c71afae10fd4778493355df53073d6d10236ed429c35b5134806f7656947554520668c0ffb4679d28e31ad9fb1864d572f405a35c99'
        '4cff7aa440a13385bcbed83c3cea84509bfe335510302815583f613e1099c39852da9eec67f7cdc1082e9560fb328c5427d61286991f13ba6214ba51d814df54'
        'dc3429b3d83c9d7322102e8f18e2e6eb8b207103910252242384a5c6f11ed8ba3a8d0e2e5ca7b526ee51f6ecee318ef03f4262ef33b98f2d058725004c27db00'
        '726985a3132ba7a94577ead73b6bcb3d3c037919ee60fd8210e17fe186f9520a55ffa30e5c2ba6b22656f722f767c8207a4f722f6e45d0a6675bfc0b1d8cfb52'
        'b7d777783ab43d33a683a66d95001b79de3ca5fdbb6d5f75798c630cac0e761e0e378222c46d5c3de68b047e7f32971d7f961866c05663730621dcbb20760955'
        '9b8536789a2a0a4b4149b65687d699b17d2b0214e04e0a51b94511eeb615ae790138fa8ebf45d9c2e715eb440926d2b8611ab4b4c4d318f040af048cb6848351'
        'eb485441421d17e1ca0195fc39ab587e5f1a61844fa71186cea961b2258c66e0555d4ce889d9d6c75e1d878246b9c43cb0edf4b8d7e206e49d63ba2deb9e0c2e'
        '43f49d2664ece1dae4b6402226cf9c13509dd56ad9a1a2727c19d150a9d2c28981d629edbda17759dd4c22a994d301c4880c4cf99a34d1fcc4291f221e0e075a'
        'e2541f931453ba9ff5b882ca7a2f5ccca80da85ab3fde150405b35017cae56d6bf4f7cc3c483a1b5f90d98f5bb16baf18ce96ea54c7e81119804c9ed59c54feb'
        '8f05786949f23e35f07d56c7eae7b913c2db8b0f3d0e5cdf656e0d5881f1bd8aad28a89c8581714cbf2e90f3ad83eb3904a1a2e2dff635c388c3aa8f252692e3'
        '1636224fa6fc15ac7e9ca98c8d6f1dec303229501a02aabdbf78c9edab7a47118250fcd97de8ccf298f9f74e3634a99348021991911669bb10393f94d1f253bc'
        'dbdda921a52605b79b593ade3018fb7760e044991ab8817a2b48561f909caffe6e42373f011a39affc34acbb6068c9fada98a37b2bd7734bea47c40a6fefdb39'
        'f160e9d54da5cdf6f9477a459338ea461985c2b08e5e8d2068740823164b51dd266798febba8570679443f41b6361e83a4d8458e124bf3cff049b34aa5e05375'
        'e73068b364b6bd0428cc4c4020dfe3e452bcf07f6498fe3198621e142a0e9e6297194e18e4d225427442892358d285f5cba9783dbcb4434473c3e7a9fbc8f062'
        '92edd4dc9f142bc4baada2681928113bc333964fca59f79645e5d857d0948d1d40ffce8d77844179c46fbb732492dd4aa5dc53cef65755c2f2f719887c8d9304'
        '2630db09d9a838eb3327ed47129adbc12d197f526c6af0700fac26deb68040ee19129c0cdecdb6803515750532fc047380f57cbe312ac24635119252a6939a26'
        '28dd6a225d2a7a8bb2193f01049bddac332e7af2e8161dec8b8563e005278dc3bb840dc4dc2723be982370886741957450e843968e379f49ad56727c7302dbea'
        '26baa575f063e134e2b5c718f6dbc66927d796eab98a57b97f88bfe204c7ae9c7ee5238fba6781e15a4216716e8384a2a3dbeb8b07743017147ee0b97be97536'
        'b35555ac58eb5af3fd389e041a8db97e0eb58023a11097e0fb727cb5951497a639c87458939aa6ca962180f97f978e7d35275d3516584b687b45145b54bdef59'
        '7b7c03bf18edeb22854d8bdccdd745171235db8a6c6deb1589b2b61c9a4932ab247440d8ba57aab8ad418f3569c9b179184bb63595f4bcfee8ff5a4cd3411ced'
        '5f8b57b8e171788a9b683a6bad654b43c200945f8f165a638314d5ce422dc0f4bae9e4c0b97ea79088a8973e477fcd7d9b26f4d2b2f9a81047d4a395278d02e8'
        '37f4aa9c94744ffb1131c6b97b09cedb6957f7242b6d14dc594fa9d6c5a9b20c4626e7b62322ae146bf64247ff0f466756c9abc9142d1dd5b9ff07452a2539a2'
        '255acc2087dd7ea51b77e58493e49f8afabef350069703d35414fe77dfa2e0e021b304f24595cae1a13b1b9e9abbd49ba4df53c7c8170a07dbd73a42bd68ac73'
        '7b573f3dd474fa0e6fb56bf9fe11819c8f84fbf7aec1662632c83d3d02f1bd1533e29b75c080f119c973f13d742dd4a0868fdf50dfe8677d2a0624c85eb9ac51'
        '755312f1542707229c205a6e684687bc9af94bfb44434e2d35b32efa63a7be61f26831c716ee0e4a876e43cfd448ee3c991e7f514401ec5a1982f73d347c9e2f'
        '227986366822f9d126fe85238f3829e65bf1df9df59e88c604c73c5b27426f12c9a08c5997d0ff058882a2bca77f27072c940ee203bf8c8adbc77e50a1388164'
        '934d0ad064bc3e51386ac0ee29c0ba18450d4aee9d5eb15308ebe94aa07a537cfd3b902ebdf69a50ee935267baffa29c9d78f95d81e4af1a0652987fdee3897c'
        'a1ff22543010f2a69d906af9ef783d46be4fff7536cda4b79c92b6d6585e7a8d94acc097510ef14c10bdba7c47038d5363cd48cb8698ed21e1cb5522099a5c2e'
        '1caf17058188f82d5954e264ca488e1e051070b9069de4d96ddeb0cfb8dac4c566b205e9ef0c85ab783802bf0ed10f45e30d33069a3413b2bdb22e13e218fd30'
        '96c96650f0b5d3241bb0525dfbef5973d16597d4cafe2f37af4430065eec1b7abb4158e098906230c986d86d4e1d674ea7aaf6432b0a740771715781f122d22e'
        '5ad0e0881fe851e338d554ebb37720636db9d17af90587b0de50ea87c7fe0b18482ea95be60e93f7befb4423c2a2e61605b8942df21472045a11b40f817892bb'
        '7a27dc6925cc3e387589e7478b80e30e9b6a29e21517296e263dbc78d255e48eeca46742c3e0c2f89721c1ead1ffbfa0daa8df2fe4457dbaed9974804c6afb4e'
        '5b4534066ef439e92ad157e4e73f9c38ba16c7efb62abcc47764f202821e28c8eeafa185d0de25b65f641b756b8c4b468269bfb11d12691e7351925c550adeea'
        '7114d8880b17d65c74bd756bb0a639954bdc7c4c07d047172e44a67150b8c431af30a6c77074705b05ce42b0e81b29ff9cc22992922223584b573f2813cab366'
        '70fd7408822707debe1fa4a0dfc5f0343a3b16638b38053f4548c15604700c5c2b998c58038c6b2316efb974ad9f3128e0faaa0dcd32a28c4c38e4c745372484'
        '6990d01118cb27b4ce7538f40f3f39432316ccfe4b828742642b92b14bb0ac9e7664d3170b97007e2945ff44a816b683217f7d566702ddcd151fde8e83ef0963'
        'f2a17d3be686be269b8dddd749928f2fb62d054749d35d63e9c0d15c753f025fb32a82b4a5cc0c66165b02bae8853b02437045377c5ed372ca3a7f170cf596f8'
        'c5064f1d420a880d01255c43aa64a9d48009ddc32835e8a60fdfbecd19e2aacbb2d97128643b20cddedbcc2194a345789eb55ccf6fceadebb18e9b03fd0a04e9'
        'd48b4c3cc97ab581322628f2dd69b63820781df49cd12650e02a947c18cf8ab92d108b6ac88a7d3cbe3e5795ed3bf114a3627d90906bb97986ddcfe808eab65c'
        'd1ab40ad66ca41a69c97c2509943a93a2fa407cbb5189ae8cb69669ebf5081a046e76045b21fe455fc954115e184dbac6b19a6daf910fc63cd18f6f272eb04be'
        '9f2ee9b939ec04054f2a07a3f5eceb3c66392a2860125cbad6599f646a9b1718bbeec533ea2fb278566ba93ff594a2169015cdf4ed4b4ba65a999e8c73c67f69'
        'b7bc050eeca9c85bf4eb048f9d491a30c24bfac19e49eafd4a5756d522c613f923ea68bcf49badbc719ccd1f2827e0a1170e315a67bf27438aa7869d3af25843'
        '34a6dfa6cca2a7ea8d6f1c88fdc0daef604d20d416815fdd8facf80da196ab5a6800c2c16816c499c826bc8b726e44b951132fa6483426e3e4835a532dc30f0a'
        '6e471ab09ef02837562a144cd4b92790fd5430473dac5482c19b6c4d726137e7495ed41471b0635c08603950352235efd9273b2e588ed7d85384980e0a14195f'
        '4d805714594c92308c6814e98183002c29f606e5fa6d83ef97fdf4ca32cb54a76a3ca8353a57a057cca49eaa031c02e6ebf2b12b52c5faecf4cfdd126ec77bdf'
        '1ee455097fb41d6f3ad35fe6e59c6842114f1c9fc3618d837f11cf58449e67466ce8b7b500bbe5d7306f5d64542b657a3a0b9c8040de6e88594b2a9bbb335b72'
        'cba1764c2da79aa8ab2d7cc5fc6be749aecba9f682012c7497fe523a90b18d652f8b7a99418fbb98ca50d20beb2f97cdec6b95654fe4454f83a2a59c98a89c8e'
        'f00d563c095b39c46fb863e0bce3569bb3ff1f2c6f4c73312bb3cda190b54d08072d2771ee8c49f902ecb3c23a7e49aea78b97decc06139a1cce17159579e36c'
        '84d80fb02db7dad632c540eeec91b786912fad00743231a9a28975d4f2a2f927b48d7c29df039b93a621fd819b5c26a744cf521c5341b16b44423544461c6af2'
        '8633c61513c25a1cf0fccda49c79f3fc8ed815dee6cc9b3170536f795671b0ce0e80251ac1c401b8427a4898b7986b6054f401aa13e1abaab32ce17efed915e7'
        '1196e52eb16287a609d765caa455d4dc9fa68aabeca7d4d4be129087302a42ceee07185953396db1d026a5aa8753f430846d2c23ce2e04b23240f94a4763d950'
        'ff38a442eff68c2e91dd71016145bc264b235bed4f4de3428503dcbdba9a5032c92588fe95e0d04a3f5c7fd75d4d945424a735305a1d16ff492b6bf2e4a6c903'
        '41a9e0da2ebd29f43801340e4770f95e93517ef078008dc56eabc5ae56ab0ccdb821f7d5215f7ca7412b604b00d73a5d94bd31c451df45ca078678d5e0955f92')

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
         '0036-LOONGSON-irqchip-loongson-eiointc-Improve-IRQ-affini.patch'
         '0037-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
         '0038-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
         '0039-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
         '0040-LOONGSON-LoongArch-Add-canfd-support-for-ls2k3000.patch'
         '0041-LOONGSON-LoongArch-Align-FPU-register-state-to-32-by.patch'
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
         '0064-BORE-linux7.0-rc2-bore-6.6.3.patch'
         '0065-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
)
         
# vim:set ts=8 sts=2 sw=2 et:
