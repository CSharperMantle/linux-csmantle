# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.0.11.arch1
pkgrel=2
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
b2sums=('e198c4edf9cc681c602e4c0bd8d92ff9d93433c95a525d8d94e5ad59aa9da2299a5048690841263e925835e3960d621fab137afd3522020f58d4fe1a09041ac7'
        'SKIP'
        '17d5fbaf51a1930dbacadcf3eacc286e471e44fd1526516b7fa51f7e83b62c9d24e69e1cf9c5c111288160964b8e44d1138306de2ebc84b242e33f09d6d6e13a'
        'SKIP'
        'dafee1f25d231199834869a5ce76a85eebb3c1ceac86f604270e93a40a22f29bcf797822481aff5aa5020c12359b9ad87ad8e0d36727166522510a07539d69d4'
        '652069e50060a3d84530f004f7064d98d6ac9bb02e690a3510d092d0df17598c9b3d564ae07fdb0dbbecc68d2d12d58c4c78c02cc08fbcbb8c01ba6e6256d922'
        '7b59edcee464209b0ff2e4b06c58babdc3d56801e1f73351bf6f140b39c53feb96d786434cb8b0db39ac94cf4ef905dec9c158758c4e41aeea16b9fa7f21c3f2'
        '82bb78c66948a572f35c8f0b6ba924e122a075632efb304693dfad2331898accdc80610d187e93ba5e18edd7f12131bea1ea2cd31b4987047cfe1bd6079eb3e6'
        '4a2bdf8189bbfe32e000c8a99f17cb17b4aec559ee27c137fbd780a141839a7b783dd42d70846c755de9f1ace558305d92abb62e90e7a9df5f5a238dff0d3f53'
        '001390b31cade92a810d5ee3e0e5c33ede3b38cac6c45ec9b956bc4ed5bcd9d4c7fb0baaf24101976bf286eb889e530319e4e899ecb1bd8ba068c8adb46b3eb5'
        'a8d844cfa8feec4905aa2cdb2da2fa00f764746b02042a04f706fffb41b17ca849d8d0dd0884332aa9b65bbae496a851ca0b33d1567edf6cca4e7493274e1b7a'
        'd0b3d65a5a3e03c3968a2b41dc60daffed46c229b0ef89c460f57c8cb5810eeea6ba0b23e4b6e7629e42f075ab56b73ec47e7a0e4655b3e34fad22f6f38560aa'
        'aa685dfce23e2a10f64fbc75fe1ece656f8c670e1b669444d12107c142ea0697dfa19b8b5efc20c0d9b00ee7369b773c927c4a5eac74462bbad49366a034d27c'
        '6a468875dc641fe02941940364992bcc9b17d8667311acb6619abfdb7ded9c5545c901f9ea07c9782f31479a3e215ae612e3753f8918e9e7e1bb9734a5b3683a'
        '186a6bd1e0ffb632ecfcfbd3ed50a296bda4ab30baa191c54bf34cc068756d5d57367390eec9a00f25d98bcaf8af2699c5573cc2c65bdacb91fdeb5d3b086ebe'
        '267a0e6b29fe590f6b0c16e16cd5a0ac5500589c7144478bb13c3d753557aafa10628389126bff14c196326ff8df8c4e422685082180bc3e048c93835ff0da71'
        '34bd1aad16a2687b3976606eeec85a78f28be8e12639433728eefa7ae9e99ccc794bdca204d52856d246d0105682db76b04e0369d58354ee36bef07096697d32'
        'bafccd5bfa377fab56148d58510eac90dda953903a3f1df7e63f82faad3171c3a161b0da1af767a6a646b59113a2f5ca10beff3660dd5dfa36ba6b1ffbfb6091'
        'fbf86c4035a2639487d789c7361804188dbecd63805b8a89738dc4ae3a90ebc2c4c57c290674d4e8da73a3aa5e811bcc5a62dea2dd37b3dff732890f0c7e4f20'
        '4c99733fcdc332d891e0a8427846550c86c517e61b4b1959312bf9efb437d83d0388f244aa000d2c37d6056fb49c44efc3d2b841b0dd3c1fb3ef7ec7bca9e79e'
        '2490d77ade057549bc63d8380b385e2eca84aac352007d7089ecc8944a5ca70704912d4986ec7c9af34278776068bc86d8dd9c6afca26835f0852f54f9ed3f27'
        '154b35515fdf63444aaf599ed641812c42459b9a2d1309f2f4573dcb16a233025a849b807432b817da984520d8fb24e1337364ff4e656f87ea97b2af95b039c2'
        '8332107f15d5e589b4d4ab1d3dd753081495ccfe7fd58b24c0ebddcbdffc9c20ae5bbcfa339549e74f45184f5f035e06b4699a458bf7bebc052ec4b2d470a82f'
        'd5eaca4fb6054738ab832ce8fa716580ce7b29d51c7b4c4b5ab8bb18ea0900d1e5417e38a60e6ffa73abce8ea09f5e7d1fb0dfc7c0f80df19cf0a176045fcaa1'
        '3721dc1a8b82e322c8c23a572963b9ddd2c19c865373d67824aecf98210eba12820317bd54d82594a3abb0073b9ad2db61c7a7aafdcf59a185aebc4e925b8b3a'
        'd3c8e082bc97ab22fcc3e79ccb5c7e9042266b3ff9025057dda3126dfd02008f3dca637408a28ca35b45632b398f417dc671c41e8b0f1ad1814c211e27dda67e'
        '2984c45ed038c48c5a6eeb6bfba0490c27a1d5fe1cbe5c5c58100b7a1bb50ec6ff6279030bb2dc1f22c853f76ca927a9ae03e0fd84cfced1255606453a4a4438'
        '3304b32fb5e2d2860a8463120443b717460d2ad5249e43f9eb96f2b5a074732eed7346de8dc3a3357253fd65186b1ec16d7c06c891ce3685a3893231adac1fe2'
        'd8f86eda9ebfb325c096298ddb329572e2c9eb6ca4b3b5b0e0a0f1c95c774dbff23d752b96c54f12bfebf9ed2a96176277edb8e042ad69531a7b34cf1ec9b8b4'
        'fb67a0d3a389f34258375b8118860cac2d1de4016819245ecb43de7f03d88c071e87cde33e369d242a8d53b0b911433897efb09ea5dd423e7382617ad66a124d'
        'bc1f700cca7c71309afc50d4e0e813c22c7b2b0da70e69c598ba4ac4c5c17e3cd1b6a062474b302ca4287f06c1af16de8efddfd2bda7aa58b4105b85b5ea0c04'
        'e252e33211b1ca5c34a7c82be849223079d697ac5cbe74902560980b557822077588db3ef007366ab4070d8140dd35f0ff58260f57980d06133b6f4892bd304c'
        'fc800c910b5618b7d388a311b6e2e56871aee412aae48b38c856e5c0ee62749db7399d61e3b978196039983cbe318d2e22d6911da9580af3f3405797b2b2ddd4'
        '6c465af53dfa8673484535eba1c0cddd6280662087aa68fc5aad829e9511b7fb002f2a3c4ff05f5da63743d6589b9f9ff0b519b6c01111ae69947cced36ba73e'
        '6018585a3585b4d47b7c9c2943f0c5e2fdc6259cbd756a79fbc8d9fddda12408e6345b6b4bcb9b799a8d31e1dbcef112f221f0cd33d7997ef7f818de7e2769c8'
        'bc953b16dfd92af6360cd5adabc3241f3dde3a94f1362768eada7404a21b5c53a7c6b8d9882e807a30837c7620bc1a5f67ad0b6db6352e3d4702ce9aee808c0d'
        '4aba681c912cd181f084314781aa59acca74ea2feaf69935eeef41267feea62c9b17368a4def2cc080ed2a1ccc02d8607ea9bef2fa6e3aaa4d9175757752718e'
        '03032c7c9e6392d9efaa5595a03f58a451ea3df20fc15fd4ae72fb13ddc2cb58e3429f6794269a067c9e772905f1ecfe40a07cc5d3b15ec16e9daec72de6554b'
        '73e28ef2a6b432c0d593ef263150a7da1c066da64e644b88077f5cbf15e84127dd470fe14174d61658deab4b5efa9e6f624f4cc65df67f9deea582e04603a8f7'
        '93b1aad76d93f22c2d0d9135f2922b48a5141e7eb41d6c5b254c3e43b2795042f3c18a67b71b9ffb907fd95e40e2c240d8fa7b5a09434bbd4407ef1e431b0630'
        '4dd280b3d718874c5d2faf2d6a798947b7c517ea778a81c5a266fbd696bf95bac4df1795b56db25f1edba8078418e562f174b04334dc4fd30ed16c708455a157'
        'd79d080ef8de62ea556aa5e4026ab58de276ee9ad79d190931baa42385e460616f95ad9852b53dc1d08585d9ba80b843c69f5df66e3b6adbb1356120d7921afe'
        '11cb8c6fee55ebe9120f5980eb70b43884ddb9033d2d4d8ad41195a88d25c0f6d7e3a88eefceb102ada696c0f0597d97d6ccff651ab668647b0a60875d2f7da0'
        '43d40b62593ca3ce542f31fbdb41273a8e003631c1b7c910e7f7d17e3adb2801f2ab5d9755546304d888679e565965ca4e30862aade9c08eedec2dfeea6e80c9'
        '8af2ab570ab02715eb28a42d9397b47b91023a8faca1ab29352501cb8f27d9c24f452028f547fd43165ed7b0ded1f3f07068f8dc92843d9754736fca1c04533c'
        '12d9a537baffac5c8e4c2dd8fecd309c1ccab5049ba90d60df61421be5557b8269b5687754bf39a8709a4a828728b58e5897a5693bf8da5f90978f139a4c252b'
        'eaceb0961c3d02cbe19485b308ad8fd4215d4d56ef6efef8b6db4d037c85424701013c627d34a7e2952c79cc17d222c25114110589eac0f6172a7feafdeaab54'
        'd7e17fb753b0255c2c61693f622a75aedf97ac4ce4e98344994c319e599114beb9459b5601137de2dc243cea97b70dab5175ea933903a070405e9f4671eef21d'
        '653c677c370bac449605f85fb3841455769496e71b4b3c35c3869af81032517523d3237b6b41b03e66fe81568470d3d60431ffa3984d737689b77c6c4dd58d01'
        '4a6de0e230729060fb8170ee5fecf3b2afbbf8e8c8eaadfd3471611d04c0cd640415ed9345c446c23fa8ed567f50461d1ae45f25a8799aa7ea1ed50b20a02721'
        '8c81ec9821fdf2fd7ced112e754a18d254b2dcb050d76caebca72cf9fb6b3794c21ed098cb2b4ff14758602a658eb9234bbbfe9b88ccfee991132f0746790ece'
        '35942fed565c662edc659a4a2dfa60b554489602242c91e37b6835b2e9187aa2a9c701e6c2cc04653bc0b90d40990c9595892783cb895637d9d76fdae1b22b1c'
        '44111080923b244c6445eb55027773df3bb651280e144896eafdc7cee1b15ea87528fefdd151d8d3197cc4d7a787e792d12b6799695c22b57a438d84892df3e0'
        '46eaa495c5f7821139e3f6ca9323f450ab2f6ada64b837033219eb7f5c6cbadcca0389acc35eb5eeb24eb1d24f80663454ea5169b00550249a7ce4193c92eea8'
        'e4ceaff68a43b64e7b2fc4263f73a858f41e3665a40bbe371e1d50c33f950893bbc9542aba6eebd8810a1da67a713df4fb8cf8297c43eda4c9039f7ed72a43e5'
        'f8bf3f8b6d0625531bc0953dfe2b612ce6b54e14d3e8b3ab545a775886ba121e47e8dc3b02a3befe8fe2222cee210aada9ac821f75481c4c01b0e065131cfef6'
        'dea7caf994d2eb0b0c759fcdd055f8093b736df8523e83c2c02eba653a393e15ac3b7013ab518ef3b3a39168dc7be479719bcc4b29e565f5dc70ad2e7a5556ee'
        '9e07cf24f1c0c63923b6a9cf71334257046679dfff89232ed472b2fb7dc1d60316d5e6ad7851a99567d249817301aff3b48cd350d3f60d90206a3bb1e7325da8'
        '1d8b8998252b153bd745e1cec5be2d12c2d71cb0f42e60db7442b785384fc8c77648f76cd5b3b162d2f494b11f900cea5298884debe5ed8c3a82f8622a8b580c'
        '3b9c9bc31bfe80bd189adbe4c31379d7e5ce52e9aba938da3c497aec296a60ea126f4c5c50f891b8d4f9c0c0e3933f51da5f8a308c823d9b8f89a8d3e9359772'
        '70365745b22636b483753f70165f3f1296fd01a0d6eac525d7f19b8086b15edf2bf6660acddbdbaca670d50aa057574e120de7b016896617c3f85c3ba9120513'
        '31aebd7feb39a97f33b4f5645ce32a6cea134689a584885fb53d8ac9ad855082a9785c2e63a95612861a0c1eee62f10f28a8af4a49cfec6c0a02a17c47083668'
        '882341f2d7017b4153f2b5e8bd654f7dc60fae246da0e0edb603ecb647437861dacb1dcca4b9b77c5e24013dc7c6f9dfba4ed1174950302daa389ab2f8ce469e'
        '9d3d7653384d6b458511fd0b26e15b78a92f22e548c0be26f605b6037b40dfbbd15145d93fdf0a9fde9f6a59bddc832997298e1603fa6b1366df71e99cfaee4b'
        'e8f0aa8cfe0d61dab6aa8f278311c2769534350b7c80b8c2e732409d49cfb983419f7096fb4cc12c3f5db7dd5c3b805e648633f5a42feeaa36537dd672ecc2a0'
        'a6489f37c7b3af5a64f2b8a70a88abcc41b395a806cdd18e4ec2f6ba5b7a545351ad2aa47c5b6b1513e12cccaf023e224a3b9019ec5e7beb7cb39cc795dceb66'
        '5c2fdbf9577ee9f0ccbc255e506623d462c12ecb3089942391dcf406b8f8d97e14392ce610ce2eb17abe973ec2cc293e9b97bc5aa63a069551376dd17a056178'
        '6ff44899455be1c3008e7cf30334b85e47a18379c762c9bd7c75f7f5815c20272ee70bb6191b18c4ca0f6fff3f763e5535a5969e72b4c22e6a2a22030d7ce72a'
        '234fffa9e43a43ae188f25d26777a4431e54e54f94550a5d97a3d696a5ffbaa28e3daa95d5b0f9b0b490c8e59157c6715dfbc9626b12284ffbd8a93821d678e9'
        'd25db8d060bd5367e41ef8d5b457c27d39aeb9ed57647c7bbf711f07f842761aa9508750a82a9f275770164fc8e2abd36410bb34fba9d901c1fdf5af7b1e257d'
        '6a0c356111d9032f345c8d0126185373eb6de4e4aec91f982fdf2b27a1fe340891004d408c78979ac4ea9bc3d6f25facd7d2c206fdff3227c18ce086b128eeae'
        'f2a87cc54a0ee693eaff3d547f4bd507b1d414a2c52ef3c966249d00af893894ecfbbe4c7b1bd9ca50f03011623c59161d48865fe466424d419c85a1a41b65d3'
        '9dcc8f089b596169d8758876d180fa449e6cd135103c5c4b83378ac969e4eabcea21ef30b1831f1ed2c8acee338414caec7e379600e957fe61e679c589a03b76'
        '496d546fd50985da27852faaf0b8821a5c9b7950b151306d7f2a080113d5b2309e805385cdb2ec4fc94fa05eb552ee2a7af1933b6f80bc7cf1f5f6dc229aadc8')

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
