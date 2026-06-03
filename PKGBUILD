# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.0.11.arch1
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
b2sums=('e198c4edf9cc681c602e4c0bd8d92ff9d93433c95a525d8d94e5ad59aa9da2299a5048690841263e925835e3960d621fab137afd3522020f58d4fe1a09041ac7'
        'SKIP'
        '17d5fbaf51a1930dbacadcf3eacc286e471e44fd1526516b7fa51f7e83b62c9d24e69e1cf9c5c111288160964b8e44d1138306de2ebc84b242e33f09d6d6e13a'
        'SKIP'
        'dafee1f25d231199834869a5ce76a85eebb3c1ceac86f604270e93a40a22f29bcf797822481aff5aa5020c12359b9ad87ad8e0d36727166522510a07539d69d4'
        '652069e50060a3d84530f004f7064d98d6ac9bb02e690a3510d092d0df17598c9b3d564ae07fdb0dbbecc68d2d12d58c4c78c02cc08fbcbb8c01ba6e6256d922'
        'e31028c4d808982740991d450b7dfd77e36bfbb620205ee7a34b3c6937dcf75202d77a136e58ffaa325995d929f8a1095b6f6467992174d2b9c5fad034eee418'
        'fa656e5f44c069d93baafd37e4a947ca90aa9805c391b963d5ad2cfee99f75e620d6c86587a1f07fb3640a94f6f84917626cea5e901ef0db00da2c275630645a'
        '230bcfde35062fb03e7db78b809d3a6cb973b9b45fb85eb1bb39e1525ced3aa28192cd383d40bb23d12281b07a6bb0b175b69b5cf6ca0e36bfa52e0656a00a12'
        '1a9fec232cdf62e9a185c0d3c68aaad9e90122d21ef2f19634ae9512766b29f67fb40a5c3387e0697d8943e6fa9f0f49894ad2c0afac72165620d981507c38e8'
        '32e3deeabbbd8b226f4c6d23a32dc57f6eca3d460b8137426c9f08b5eca00ee94ceb309ac5a5918284a64d79c3d6c92cb1b44286c991726f782392205d1529a4'
        '02eb1c3efeb4fe01e51322957e3a3cd3b39049a139517352a3f7c1331997fab2edcc015decccfda8ca5196a51810b7955f7c782384acd2d081cec5acb9269d2f'
        '24a6460c4b57e45a2498f5e6bfcca46598ff2489cb1d03e6ae31328c0839e00627d8fc80ed39bafad2e92604b65911c82a622923bd24e1448b2484de2f7773fa'
        '5437ffc47807c0a66a6054172f97044681e639bf84b18db65c1554b84718c25592f1f55057ec9990233a1286cf66602fd2df09b72bbb15a7d5a84789bd7af472'
        '23ce53568acb079ae9b3dc20bc9480e5b7f3bd3b2e25e68fcf918057b8a870e7fd0d92869f3aca95e8fe8874681e02afc9d124fb97c7b075cf6178ca06b47fbe'
        '24c31e955beae2f0c72a0df642767af156c08c1224004d34aa6ef0570d4304e9b077ac3009b881d39c296944fa4ff8840bc93f0ba5f05ec7c915a7c664713e82'
        '0b2b5d07e0518d19ca859956fa4a05aa50bf4fb690e00a6de11f3ba9e396bae4296189c2bd9de637f6fb54870716483cfe6b4c450adb7e59babf0b32dd1ac51a'
        '9f695f7c625053c8e478ec4ad2f61af9dcec7f371aa95831a3bfdef21d31ee9ec73a6b5dad6867b41fc3238c528c7f3ece45e50783a2cb803613ae9342c8c3a7'
        'a637ebcbc1711474489930737c8301d63aaebc82f4e66b665ecd156ff6dc81daaa472e6702d4e27731ae99f3ea448be86a1a29aafbfc9484af63406521f84f3d'
        'd7b79682a7a571973687f4bd4914149ac962891889a9d22b38ef103026f4cf9142fb6dfb90fdc0f9344cc1e2db2468819cbd609440a651bf84f110f907b96b00'
        '82fefe9fed52109da780ac18bd61f771eae1b45548cae20fe4f71380af657886153364326eaeef01298937175dec717bd5732395d4767ea55c0358f0157330d7'
        'b5a85119807ce8c1c8dcedb20afd61e5e234f638470d3c2b4e62add275e7715bf1ca33b5042f61cecbc3458d0e45337f3d186f4b810563cb5d2e7a1f8a6ee1bb'
        '88859a23d97fa575afb2b451e1c6e346c2d71759ec3dcfe51612eaa5cf85f3080f92f71827df02d904130c7c2beb0996f2e4402e1cdea6deb2c99e6e74205095'
        '146b57aeba07171f9b460ecd4696693d00eb2a9c20b38fb342163fb01fb8fd45fa7e4998abac7ffead8bddaed3f6ebd5656d7909151ac0a15add3ff0f7695bef'
        'b9da94fa2d6eb2821705859831155a286d579fecf7390ed59e4ac4cc150a53c3529a19a372c7919e6145c1678718a1cda7100f63c6d3f21ebc6d865cb9533043'
        '689fe6568f5724b2e9ac0e095012cbbfe29518302f02f6a41ebf681cdfd56e8b1eeae16fd08cb945db05366e9d81263107b50a7b8e147d0d6835bb95a7df8d46'
        '2d8aeb17b3f6c16ce834ea42201ded5706faeea57c646b413eeefa9b65433e2591f31124ff4ecf0e4aab2e111a9786ef87d160045952045961aa2e2052c0fe13'
        'd0f770182d9bddbb1e2153b76c683879b5f5006f75607eebcda4e909aff2703a1d8d097db9b6b6b7ef1e3f289e30684e4226ae0b8aebeb2347d66ad4a11a26d8'
        '583dcf6502b76d6170cdcdfd36490ec6a02f00d9bc8404e92420647c6088f7cb0ee2c93bd96f8e858554c0a1ecb157dd94542d5fb775e68ef6afc7b11791b1a3'
        'c407efab4bede8c2e62dfc94cfb3c8597cc1f0798a9c3549703d191534bc333d601669c07694c323f79907294441f2e2c43cef96289f9f9ca26826659acb93f2'
        '057b178c9ce58fa3916faac242af33d1c44ef13ffa93dddab5cd14e175369a24c63b66fd869ae7a1d45e1e7cfac912fae80f0d11fd3cf77851629e719263173b'
        '4b45bd179f91a5acfd259199dca65e1717a2eb7d7f677011689575a0bad6d2cdcdb41cc4a74e0a7515845300f36e45e335c8e9d57f162e777c008668e3e208b0'
        '0081b2789123f38bf801825ea83add17c4f1dff82d343380701b898226498a410c3852cb140f71f5e4cc33a0214e0ee4ceb1cd3a4f1f4595348665933af383fb'
        '7a5c36d860cecba9487df7f582829fd4f45667e5146e1170072dffc7288135e8958be1cba0a6f68908e03d763940ccc15b1f5ee78d71f7c28e3bf483a2fe0f53'
        'a296085f7a132fdd7c21b740c43930882890a4b803615ca37ae90c8193732e5c53e00c2249faae6003f95cd6e5fee9cd4d66195f05dda56644e49ad8dfffe149'
        '56c72b3ca240484b15854a833d69a7cad25bf07d535a6a418bc32545f1c8cef631569fb31326dbda883ff1faee0b9a9f786f3e49ba7cac3c61d7ea197221f7ad'
        '8de5cbc684c07e0a8086f83df83368273014dd5d1f01998db32035a6325e93a463b7b46a00998c3530ca166a5ed9f74ae567369bd008afa26eff9e5d5c6b86f2'
        'fc82423f0ad85d97b098ca7446439ac5aaa8fdb66c311e5d74d15780d1ee64612490f2d86f06021cc941f83c563bb10aa9a899fbcd5d6466f7e20ce3fa4979f6'
        'e6559e83566a7f7ef365b05fe6c4f965b47c58448021010ead8cfaac4c0f77dc20ffdff4b686c8573c56b755f188a771aa20ad3d386a08f66f5aa7d523c26e35'
        '0ca02d2a6bb9c923a609fa202326d4c9fa84cc0cc39771bd0faa5c2a0720e527fe324c6425c7b493d3165bead221097dcaece476871d4fb7a7d999880ff582f8'
        'c214b4c1693e6083be800183cbb5494a1c2d0b7bf138346f2101f0267345ae581140fe809edbcc83c7a154b3809518e39182175f06ef07281c017d0e64227514'
        '8582f3241c54f1f77a00292f5a3fdb6118058db367fc002ba5229a33d603f1ae3f24e2167cf9874b4d29456e2dab1acd6fa6391ffb05c39115f37e8eec31f491'
        '71e94bac2926f7d3119e64a919760c809e4ddd55cedae52865bd13c1d88ded1657736574a889ab048ceb1af79129776f061e621edd7405fb015396a66fdc3f2f'
        '9aa837afc8dc6495c40051d96803bd28151b18aa979b6599ff0f42a5d80affb135a60e21b3d81ef4d5391ef9934c81375474bd0ef39b78c723f1e3f1031e42f4'
        '5935f1b62c398a30a11ab3819ea2c8669e997f3cb476943f443e5d4edad1c3f4dbeb7646b131381ae937aa8430c4fd82953e8e4c5ef5fac1ab8e476dbaeff28c'
        '453e77842f05891ccb7addd57887d7593ef4c67c95c214150c1aad718ee0a435c61d09d0f1b29e1023b8d7f061087228a1a26a0c0fd4e4050d371be45ad3d224'
        'bf72ff3e5100c49f70c5fb102b2e7d42dd0117b064ae94526b54dd1c683f0ae72d2a2cb8fda8cb303e4ddb2b08a3d7f5e886d8cde44de17e6e486bdc7e6688e7'
        'd71fb7aac391c4be71212ef526f53cc48e7cd204d604dea71750b0d18dc474e6e5af89d432890c25f8c52000323b81530428d9f3e800d7d3af922850e7a0507f'
        'e00fb02ae6702e155a4c2de29347a9dd3a27fca2ce084730278c7b052e1e80fe0d0384c4b79ac37b986c7c6283a86ba13156815fb5c9968e9057cd2aecf3164d'
        'ec3ff858843ba1249bd409038692b3e1f876f5b9f56904d038271f7f381ef216cf151ed304d7bfa28b5f7a3b2641e8fd73d98a04ad7a22c16c3f5a26a52daf54'
        'fdacd3b9d766414291de7d9f4930aede5a7175bbe75f2ebfbd02a94977fbcb943db117c9b989eed3d07f4b4866a2dc3e349fc11f1f4e41503bdf5ecb193f1d7c'
        '2873941ad3e7f10f83f4398f0cca4a7c05937361a9061086c248a88c53e75e484d2ed6224cfef5ddf639d38220338ca9aca4c0824e0261570b8a541b5f542e4e'
        'c94e1a5098691fa8d0533a9a78b12512264de3ea6798410cdcc5f935c964273fcfcd4cf09a0500d73cc2a7d60ea60b731c0203c90ab03e29e0ea191c45db7e9a'
        '21486c9c2dd446507795c2af6f3cbbaab6c2f965864eae2bfb8959b0dcb0ae04609fcaf3d02cc4938777567a143f360b896e7e771311b16d5e7927d5fcc3ec0e'
        'f3286c8ab48f6b6ced38d06ddc8653342192240d89a0a451111fd3dc6ffd6518186d43348514dd8e77797ae1e0bda23c8ac5f77cad4c9017cb40297f1ef39913'
        '75c1f4193ac1f3739a685f7ad15c0d5aa3e6d27f2227263b496d6d23389b93cfc2d6d1bb87a8c80015df30ea218c6afd8e96e1e444126f1cade570e6f957fa20'
        '27ac417a91969f9cbc6c4df6438512096bbfb2235f22700862d11d5cfb90fa1e2aef10bb1310523e0dbbba620dbbabfca2167f9a20e39dc86e2794c2feed23dc'
        '3b21a8938cd9c6e07a9ec0109a92851cad1c0a51a48da79777cff85c7dde56e59afff9cc54b39a2d48dd0a2ab3f5b1efd66cf314bdc7df9f6b779979404943bd'
        '7220667cd1b5173a2107ef41ba8a73f0596d42ea8512f27476900c8ab99a15c0919cd86a15b8d29f958ce74d690fe254259fbf010c3ac3a0d92ad6c97f1a4ff6'
        '0a94df220f3218aa80979bac2822cd85e5a11d82bdc522727bceba0112befa3ad4da633f3adb6012aa8a2662e1bc326fa80151a375822347d3ffa9edab525334'
        'f2c4c27d7a36918b8aed3f5a2972391fd96c7a68eb5540b5379ff8e0c8a59e3cda915f00a5db2489f773551f3d9245d613a84344856d713003a0247d6d0c9180'
        '2cbc9b5c3d7d931ddc02610a9632b577e2a62297d1ed5cdc6b07c3fcee9cbc777db375806861356bd1d3700d0ababf5c27df2d6ae6c0dcac18b3b5803cf875b4'
        '9f2835b71e825eae0cfa0c95216903015ad05e7830aa5ba9119b29ec85bff99b7f4e7a0dc9d1ec03c2c163b6b1c460c680641fd439994c694369573420067186'
        'f84056429ed24a9bd806151f112ae219da432a67de25ec77d63c1a1c92a542acb054fde6759d3f6ce38e72e4af889e6c4ef85087e38684765709e751d81f386b'
        '7f9ec9316b458dc97b27e5df8c176fe4500a9a6f6831916f18cb1842165ae04ce7fc7146741e988ab63f72c741c8e6c4aed4d75230093942a8e594c6b4680e94'
        '482cbe2788946280c00efde4a0e6b279982df159cb95572616543340d047a7dec69c16fe9b002928b7965a039c813f2411ce3b2712ef821603af87a0593e59c5'
        'dda9106a56a31603d00f10a51185119b5ac6e41f3942fa3229065f2791888a8474ae1ba630b00977019a9fb7c3a286617703b2fbc06b690353f808d399709d79'
        '56ec0db71d07e5aa2292332e13cc074fe1986ba7ead849eec24848f2dbd85e0fe624b70b6f7506ef93d69960a477d9ffe35bd46be8daa746c4293f9024752b80'
        '702389c0222e03effb744f8337a53221f8f59718fba9692f75a9584cd4808f5124a4d13a27c061993c68500740684d80324b27ada6c0f3d6d5c12331bcb7ea4e'
        '38faed52d0f040e7d936d5d54fcf049fd6fbe947a44615b31b834e8b2126bdb536340d38eb2e67aa8c1c279e938a8c1c4ea3b28d1aa99382de60b506d23fe4ec'
        '7106dba2212a20ddcebd717f2594d6bcbc548ff340c59de24f301203bd2ca0dd70ff89b6a3c0a778d85dfda04fea74696f4e64576277fb9b6172e5a1d6aa47db'
        '3d6b4d1185f69dbb369cad751a224d3ebbcccbda3fc9c01451a4f33161132a963bf3243abb835372fde182754bae5ac240cb9ca0d72fc5142116d8af332d9856'
        'e3a3647417fb8bdf428e0c1461c19636b1fcbe39e323e6fe8fb523ed8013c7b086880ab7c74cb63aa01410db271734ad952580c50c78fce602ce8146ecf6da74')

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
