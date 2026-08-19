# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.1.8.arch1
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
b2sums=('84b59e5572d91f5ea1bb603aa7691851bd9549e1bf18a6bec8e27eb8a6e2de2e33da2ad3e3aad501c793e9756e70245a16545e76b65a44ee52b33ccf5c3dd8e7'
        'SKIP'
        '308952977c15ac3ad976ff1d99d0d186814d4b03e1c8512fc3a4c0ac1ecce3f74be8f3900a7fd286492d4f930bedc089674bf713a278fa80c35413e0e6339f97'
        'SKIP'
        '512543621b3244ee00fbc3a6071a784ed63a269c8c8dd25da0da0a90269ba8539b558b555aa63bad9bf52d96148e3184ad6bba0b62edf9a5ba3111643241a96f'
        '652069e50060a3d84530f004f7064d98d6ac9bb02e690a3510d092d0df17598c9b3d564ae07fdb0dbbecc68d2d12d58c4c78c02cc08fbcbb8c01ba6e6256d922'
        '9682585b979585cd1e2b2fd76879954d0c101c2e27d989da02225881d1b5739c01bc8e8643d9e7fbef257834b6a08d8db247b15727f98ef9eac4c533a027eb26'
        '4f255450641ead6dfada6f5e32823ba02fb383d309122825cca941f33ccaed174eec65e86af75fad22082fd7bb2df5a3241e12589e87646f61202ef62b0dc690'
        '02f23576198a63ae51119ddde932ef4dd9579953de5791580521a787446fbdc5f3d21624dd0072d224ceb3ce6dab253a6ce3dfcca5a4af98bceef2e6e84adf86'
        '90bd12f174dd12f396aac2a1d13f6b1ced42543f2645cb096a03412d1a6670bc1cc7d20f5d49778271b654b5c8bf5e6ebbeedf78aa996912d2033863b772108e'
        '299f6b9f4dad739410122a4485726738f15909820a706cf6a167a53992b2bb670d77e8566587a93d2171817ab4a6f3c3607e02db582d0b86aa723c7902243095'
        'df26b6c5c61267acbe08797d77b2a31cb9c2d1668c10845613ae7ec94794399cbfd98de02362600c5c9a14cd085d3b4e1a3142f182913721f4a202ff9e576108'
        'dd343c62d197b907ef537c6fe2ff39bce8bb934236ea9a46166cf0ccb891b67be0543a7ce0163748f9c62816a5d72392958269bfcd4a832e858db8841bee8a28'
        '2183ba889035cefaa5daf05d716fd8d6d39541ff2a1c762ee207737e6792481afa814bb501d42b1fb7b42e38fa9b96a69b1c9557fe6bfd06aced8d67b810e05c'
        'd47f310747a21f167546397801cfa85532c2e02c4139650c2dc04512c2815c3f4866fda279678b518632020a45610fee5f4afed293df80ba09e82fe7c8af38b6'
        'f7b66a3682e6ccb655b90d2d67bc4ed844f2c71ba8193949e73d920e3b68d32b5426cb399eded4277b69ed58f3a39c20d111a3c5c138533f290d4ee2c8c96d18'
        '722f9d92f832c10a515f90eeff4f7084a65596563f75b741efbd5f385e771eb7da199033c2af1d929fe661596b6363e7c206f3cb53423bd1a4bdcd2aa51e3aa7'
        '3c9181a7301a61370c65f2a8fbd4005f9b90e33d508ab8a98f3bc122263957bbd3eb5b4863bdab7771c15b31cb61c909876275bfa88a51534494fcf82aa4204c'
        'b2577b86cbc6d3c8a8d687b3307573902b88455a6b45be6999df13e0ec5881d06f81c3534a556c6e8ae6de7835a5cccb03c069958d84c371ce0516a08bb9551f'
        '47bbe458d66621c04d09f026e228694aa2bddc6ceebfb25ef03fe1c73b8087af1346e25130d386d93c773d0cca30b10e2cd16051c2119270426fb79578add0d3'
        '336059b196a12969d267a06efce3d3137b6335c8dd73fe6a5e52799c9f98d3d08ea28205a0ac7e504aeaca4f4d9a2196a88420264b93091061fdcc2572e9467f'
        '35759cf0806dfeec40ec3ceb48836c04cc48d983fe1aa004fc3e6e8822df2273201f86b54dcb7de35e2c89ecb582ad3bcdd4ffdca387cfac8c03dac11ad490c3'
        '4cd3f1e7cc792b5da76569b27281ef3d88e2bdafe65718905a075cffe7af6e289136ba73248a06838cb2c47c5aaa2668034f489b12765f898f5cc30bfcc8d925'
        '012dfb37b8234db637742fa4daaf69dfbf66e688443dd5cb342d4b8038645f27d74b654a4055a7e55f55b4584e6026c6d285c19604acfd9ac448a5bb28e77c27'
        '5fa2452a73d1440b15ecc3d21b187025d39e126ba3cca9904e5e499450b1f9c84faa280a9f025770c31b597fbfc637bdcf8458080e38be6321c08765bd7de807'
        'b4274781d1da50af4a0ed2aa86eaedce8b6d6f0ecd9cdcbdb948cb4971afb6c6aead4aae6c8b79e5a6563b1922ce9bb2df6c21c683527d42d0d97f32a0d6522d'
        '79922e67d0b957cb1bf062cb818c418421a32bf15e37ece47e816848217513d5eb6694b0ef79664e6dc79b064882f1f4c26dbd7afae6c5260b735340de6f7e94'
        '021b9b4fc3a6dc5041d748e16bd080074df235f905d83e6b83a5146d66f830c02fb0d826ce599571803b5b57b1aede697b06661483b55028b4baabbc778d53a8'
        'af23d5dfe92efa2280989315f090f6b50737209ba39ac02fc1bf349f996cc4f1191acd0a865255d438b559392692c6dfe7cfde5f13a07320f6df418f3967133d'
        '1e6607261c43c0aacd0f4cb2a2f4e9340998541b78d9dbd886cd413e08f69e63ed0e67b53d1abae0d772ebdc02cfac215e9da6f8001042f400857c0d179b762a'
        '3addba21ceb015aa965c463e65e5591c103ffc259aa4f0ed7420dca9d3c96882406b687595f8fb03f109d013212098689fbce0e783c4225f1200b313299d613d'
        '49b10b3565ee8c7c487881489ca7e08065e83b724e9bf7f65973339c996e4efa8f4682d43d17b68251b251715c8515347e215e600874bd57d3488ec8926e30ec'
        '9590e2220409f14743c75aa6569938b50623112236d7ba3b2fda91c32157cceb34042fcc2e96b3770aafdab607b481da051312f0e4f14996d4251b4b2ab2f86d'
        'ada356789073dfa277f66323a8653e36e6526f9d8dc530a51ee92a8eca146b2958a9da4e8985ec40c269a3c213b212b60415cd96d7130d64b70f67cc37d92f95'
        '906d49bfbc18867b5bb33d6cec7a1600b8c82c53cffc9034fe01f41a2799258be036fa8237323aa9bb69f56892f93a74459d78109bb7b7e4d5509905a91fba1c'
        'dd167666ddca3a1202d25c752950b38e3787683137ab23309a9fc2baaa4c712047e90d7d910cdfa2f69a3a964dd553f1fd1a8acb4115311a36d1e8abf56e235d'
        'a95cac26224784d17dcfaddd6ba73f490b0275a8f3de3b29f90b1c0e965379e6de2c77e73749cc34a06ca0def191dc3e406fb7cd14c7167c18c37c981cd4806b'
        '06dde5035331e8c18adb77fd3d98f90e2e7d5fcf86a0dcb09e1875a1812954386234b58714a3e5fce6d5572f09e2a3cf9496d7910dcc5538115f27ad9ab6fdf7'
        'ff9b782ff0d35728dff6692b3dc4a6d6cb1cf645192d72066d8ca5def3625e3f0b06c650b333370548bb51bbe09322468810ece0453ae5e07b5f69ee936ac63a'
        '445b448fc54287bb0dfe3debd81cabd87cc9b24c7f89148ebcc760cc8d3cde0617e5d025e6b37d5c42f311574a3715a2f6feb1ab2c8345fd7831fa3f6b5a0134'
        'd69e37a8f74f27bbb64d5f5c9afb917ffddf91f6e6b822f15efa3cf2ed0b6a71218e9da022901524f4a31c706526536effddc6b4d595c207efdcc057b697b72d'
        '24704b068df391da2a271c9917090d24074171101673fba9bd6bc29e4e2e9c834b3b54cc6a880a92f910ac60f22dbd9a19d08e32d4fcf85d978695ffd0b341ad'
        '62d97abd58f18c92b27f5ff6f90a8ea73f10684ae017fe68a5516eb60d0e8a2bb27e7245a71039431a74d456cd8f5359e6219dd12d0a7aa691d67257f1323aff'
        '35635bd7438d91a43caef7d3603743234aa78317572dcd638850ef534e7da1b48f0a35da330d1566b4ebffb097b3ca66c9e3456a967556ea809f6039cd5c85ce'
        'b042ec26a63ab230ec0341bdad37c6cd52972f25010e2f3fc31d5dd4790eaaf50b820f26e3e022b33ae5107f63c0b4cc448d57a8dac0a5696fa4ec6381bc60df'
        '50050b2bcf1b495718942442ebc4ca52af1ef394f32da08708a9e22ea09a4acd2d0d0de6cfb6b64a3306303f2170ad3eabdfe6573e10878d2811d9fa6eb7885b'
        '7914ee30ecd54c23e3a58d587e6f02f5183e5fa1e5e222303d1feb89d5e02c812b18d9cb4c38208e53b06ba1243bb7619023de36d4c9a5730eecaca0a8f88969'
        '42587c4980227d6e57800c4031749ea30a499cd55dc66bc4a889aefffa44bdc13d022bd11ad8da8624adfa2a8ac57807182fed8c76beb7db5fa3f549503d0717'
        'b88b41fd46be00b6ead38ba35f97b76a59533fd3d77f16149322adb611180c3770f6f172c5b8e12e3a42968dee3dd2835c66198f7e1bb9ad20b9b391c7a45dce'
        'c9b18688363d368dfa6e5e45d93890d525c120a23f6d6a329e3523553d4bacf72105f6240271ba26d3c235197eb2d79bcc7e0967fe9d2db6336fa6e4c7f1a4c9'
        '6a183a5b9aa71aa94591fe1bcec8c65bd711996e9e615b3f97f4610e178d3090021c1152e425806ef554efb1d13983001be490610ac32cc127321bbea8c386ac'
        '1794a7193a40bf971355266d0304c6f3c9e1bc4abc81bbe86e82d74b1efe3963a43643b2dda86a77ab5da6bd7b57391c4383b41fd725ea782a1b61cd4c208e0d'
        '10d47d054ce4907c9f51607dd73c8ef95b60343b0756584584a7aaa90912a78bc8c7bd09668e98801a6ee25a94076d30fc0c3806c52cda0aeb47923f3b3f678b'
        '9f217c2df15572b47a1b9850e18c4b2bb7cf0132696b69e15b12604aa2f2774df6bb5db6870e01565355c3ebd67ffc46f1fe2f453208c261253ccd9dc60476da'
        'a7cd86e8de770a8f3cd0c0da32381d63fd1f5f2b085e29f0917ce5febbcd8adaf9da30906feb2e2e23bb27cd580d577eeba9cbcdd32f0a72c14fa192e6898aa4'
        'eca286942dafe22016ac1eb775a72e55598ebf26bacca275f15bca0e2a9e4436ba1e2686b1c85d7fdfa3c2adb02391c16a02e00fdd78fd33b8205ed2cc65900a'
        'f7d3acec07795419d03709d2ed2c20bed8881f80448eda467dc6cf745733e4984ec5d68721178bfd2edb2bfa2f09ae588319f75cfce13d4aff8a6f1cd8318c2d'
        '72a858c8b9579c2cae09d2236c0627583f021678eb22b7f563b938333bd5fc1e79fc5f2c8840b95eddc7f327218d98cb2112e4ffab6e20f2f5b0299da260101e'
        '3b7a6f7dad20851c7fee00130e83409f1d90149f6b7dcf33222862c165fd170df3e165ea4da626b5ee66fc5adbfa4ed12309bed0e7b75db439850eaa666cec4b')

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
         '0001-BACKPORT-FROMLIST-Revert-thermal-hwmon-Register-a-hw.patch'
         '0002-BACKPORT-FROMLIST-drm-Makefile-Move-tiny-drivers-bef.patch'
         '0003-FROMLIST-drm-radeon-Call-mmiowb-at-the-end-of-radeon.patch'
         '0004-FROMLIST-LoongArch-Update-the-flush-cache-policy.patch'
         '0005-FROMLIST-USB-core-Enable-root_hub-s-remote-wakeup-fo.patch'
         '0006-FROMLIST-scsi-Bypass-certain-SCSI-commands-on-disks-.patch'
         '0007-FROMLIST-PCI-Prevent-LS7A-Bus-Master-clearing-on-kex.patch'
         '0008-FROMLIST-RFC-drm-amdkfd-disable-HSA_AMD_SVM-on-Loong.patch'
         '0009-BACKPORT-FROMLIST-drm-ttm-save-the-device-s-DMA-cohe.patch'
         '0010-BACKPORT-FROMLIST-drm-ttm-downgrade-cached-to-write_.patch'
         '0011-BACKPORT-FROMLIST-rust-export-BINDGEN_TARGET-from-a-.patch'
         '0012-FROMLIST-rust-generate-a-fatal-error-if-BINDGEN_TARG.patch'
         '0013-FROMLIST-rust-add-a-Kconfig-function-to-test-for-sup.patch'
         '0014-BACKPORT-FROMLIST-ACPI-PCI-check-if-the-root-io-spac.patch'
         '0015-FROMLIST-kbuild-install-extmod-build-do-not-exclude-.patch'
         '0016-BACKPORT-FROMLIST-LoongArch-detect-and-disable-sc.q-.patch'
         '0017-FROMLIST-i2c-ls2x-Add-clocks-property-parsing-and-ad.patch'
         '0018-FROMLIST-iwlwifi-add-new-pci-id-for-6235.patch'
         '0019-FROMLIST-cpufreq-loongson3-Make-this-drvier-depend-o.patch'
         '0020-FROMLIST-cpufreq-loongson3-Adjust-the-width-of-id-an.patch'
         '0021-FROMLIST-cpufreq-loongson3-Replace-per-package-mutex.patch'
         '0022-FROMLIST-cpufreq-loongson3-Use-global-physical-CPU-I.patch'
         '0023-FROMLIST-cpufreq-loongson3-Replace-IOCSR-read-write-.patch'
         '0024-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
         '0025-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
         '0026-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
         '0027-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch'
         '0028-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch'
         '0029-AOSCOS-loongarch-re-introduce-add_numamem_region-ini.patch'
         '0030-AOSCOS-loongarch-basic-boot-support-for-legacy-firmw.patch'
         '0031-AOSCOS-loongarch-parse-BPI-data-and-add-memory-mappi.patch'
         '0032-AOSCOS-loongarch-add-MADT-ACPI-table-conversion.patch'
         '0033-AOSCOS-loongarch-correct-missing-offset-of-PCI-root-.patch'
         '0034-AOSCOS-loongarch-fix-missing-dependency-info-in-DSDT.patch'
         '0035-AOSCOS-loongarch-fix-DMA-address-offset.patch'
         '0036-AOSCOS-loongarch-fix-HT_RX_INT_TRANS-register.patch'
         '0037-AOSCOS-arch-loongarch-add-la_ow_syscall-as-in-tree-m.patch'
         '0038-AOSCOS-la_ow_syscall-add-kconfig-for-module.patch'
         '0039-AOSCOS-Revert-rcu-Fix-rcu_barrier-VS-post-CPUHP_TEAR.patch'
         '0040-AOSCOS-drm-loongson-add-ls7a1000_support-module-para.patch'
         '0041-AOSCOS-drm-amdgpu-disable-ABM-Adaptive-Backlight-Man.patch'
         '0042-AOSCOS-kvm-disable-enable_virt_at_load-by-default.patch'
         '0043-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
         '0044-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
         '0045-AOSCOS-USB-core-only-enable-root_hub-wakeup-on-MACH_.patch'
         '0046-FROMLIST-gpio-loongson-64bit-Add-back-the-support-fo.patch'
         '0047-AOSCOS-ACPI-scan-Add-pwm_lookup_entry-for-PWM3-on-LS.patch'
         '0048-CSMANTLE-Revert-FROMLIST-rust-generate-a-fatal-error.patch'
         '0049-AOSCOS-drm-ttm-fix-incorrect-caching-type-caused-by-.patch'
         '0050-BORE-linux7.1-rc1-bore-6.6.3.patch'
         '0051-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
)
# vim:set ts=8 sts=2 sw=2 et:
