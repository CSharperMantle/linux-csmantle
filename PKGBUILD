# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.1.13.arch0
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
  # FIXME: -arch0 does not have upstream patches.
  #$url/releases/download/$_srctag/linux-$_srctag.patch.zst{,.sig}
  config.x86_64  # the main kernel config file
)
validpgpkeys=(
  ABAF11C65A2970B130ABE3C479BE3E4300411886  # Linus Torvalds
  647F28654894E3BD457199BE38DBBDC86092693E  # Greg Kroah-Hartman
  83BC8889351B5DEBBB68416EB8AC08600F108CDF  # Jan Alexander Steffens (heftig)
)
b2sums=('39db33eae1dcb52ecbbc5a0818ad388fe0cb263f7c8a06b04827b9354e6653f500873354c6c5fe220b332c020087716eef6f4d7915489e4748a6b5c076080e47'
        'SKIP'
        '512543621b3244ee00fbc3a6071a784ed63a269c8c8dd25da0da0a90269ba8539b558b555aa63bad9bf52d96148e3184ad6bba0b62edf9a5ba3111643241a96f'
        '652069e50060a3d84530f004f7064d98d6ac9bb02e690a3510d092d0df17598c9b3d564ae07fdb0dbbecc68d2d12d58c4c78c02cc08fbcbb8c01ba6e6256d922'
        '9682585b979585cd1e2b2fd76879954d0c101c2e27d989da02225881d1b5739c01bc8e8643d9e7fbef257834b6a08d8db247b15727f98ef9eac4c533a027eb26'
        '4f255450641ead6dfada6f5e32823ba02fb383d309122825cca941f33ccaed174eec65e86af75fad22082fd7bb2df5a3241e12589e87646f61202ef62b0dc690'
        'd8fb222e9d6bacc27abd686a346bf27a43de3f1510b2fd0aa25cae4a34e6896592f99bda1f3473377ac28cc7355ecb318edb748f0971d44d97b53d422e039c2f'
        'cb5c5302af38a259366378bbb08d4b4bb9c69b6092933967fa27f9b89e3d0098bdb78bda1dc6eaab86847a9d49ea176beeeb9e2923eeba114a4dadc43d6e6023'
        'beb728efebaf7f895e8098e58a5ec8f457ba1937018304121014a41fa3b0698a7c93edb28e56d6404a45b40320f49f2e8db1f783b7b0f2d362bf7d9d11f9cf61'
        'f3f4a6b6ea0f6c41cb5d03c2c00d31f7518c1d65eb1ec98bdc59112b0653246fda323c5cba2ed17338f6f568edc98710934004459688e2752f6aacdfd8b71209'
        '065b5bf680715042c63e95066f592aaed229700abfc8c30a7fca5dddc1be3df7e724b4da60bad92f0dbf7890a11bb3c03aeba876ec395523959a9ed4ab4ecf6a'
        'ea98ea0d90ee6b2bd77d7fdc0ce24765c00df20ea0017da484a19258b5ae3cca6f017eb648d1414ccc83e6b2956c630ee5fed0f6429b02264440d7e040f7d97f'
        'cf701fd634b483a33bce6ed1af633f2d9f609da73e7cce06c510a9fbc5a13f0243353ea56f54ae9d3641b57df57fc758cb926adf33c71407dacc45351446f3ad'
        'e201c5543838aa316becc86e3ca96c0b922ff0504c8157b812e81c91eba7cf3413aa7271c81186f07e3c907b0cf6e413167245796a9edc216180e186e025300f'
        'd6c866393aa40c6002aac8635066e56ba75423dcaca0f666573ee69706f2ee0494eea532f8bd1fdcd2cad150bde7ca620c918e7859fd177874b8167820b42e7d'
        '48f09f2d3b3c71166f33a381fc96fc9dba46547ebc0ae1a97c96382846454cc8f32f6180d4c7b7ce04b055ab96662409ccbe6688172eaaec1917c2ecd8d14e9e'
        'b8b4bec8313e364edd24aabaa614ab40082667acb85558530e0faf0c3f2cb025c5a67e618f2664c0613246e4f0d6a3f3468780797f00abe456a7941ca089109f'
        '06ff7a46d5af1273fb22fc67499e325608fcf52c99f147fe5cc8de500514e438540d2f87fcc08c9adc55464ab58f97871c9d81354b02487cb29619d3692e52fe'
        'f52c3deb8138f4537236a2e2aeb57b5f7a22994487cec2b50b71dcb154b840a928fc69404e7b77bf99d78f25689f17172c750a3248d2491f8982b1a97f226cdc'
        'dcd443f60ad5afe11ce75f2451893e48deab70e866c74b238284102ee99df69b23717456bd1dda979a78c3ef202d3dd77dccfd472bf038bc13bfdbd07a40b88c'
        '158c483219013b41812f787be98c91b95debce9125cf12d7429dbc228fdd5ca275cb108da6ce43a5141541a5f8a1e1691eb7d904e8c41d255ce142329650a8e8'
        '5daf6cc6049cd00a562122f9480fdeb23243ba0e24e1cd5db751110c47b732b8e520bd7a783759e26acc3068a95bc112ea2b70bc5202ac061580d4afac8594af'
        '3c79ed0c7ce8984d8e2acafa7d0a4fc11892e87a9417f6458c5c01d7192e4a8cdb13a9e7985ab7efbc6dff7ab0217ba8a2a8824a2d3ac761bfe71f9b2b86e914'
        'd173da58f69e8a91ba93737ceeafd111fb3b7ca2facf38874d8f150ce44a56ce08252ecdd834ae73db8e5298e9c92658d9a8aa22e23e391764e6eaebe5d21f61'
        '1c266904df95b61554236ce6251be4ede429be41e7a3c5764284fd1ddba3008ec7bd29f57815d1ad6e98214fb10f0507b177b8e07d29c3e374250af6b877403a'
        'c6938b1c73d2a381f3f6bd816186b8ee8f4b4352e4a7ed45b31cd4dcbf50d140e5761a702d31b5c94650884108d6a5f9f2385a7bf8bd0437ba600190c0199c7c'
        '755558432e05f37ce9eee81ea5eb378adabbc80cb43d3f0b6e712a4a348764d1803a60322d32ccbba23cf035080dc5c2ae43435a24ca0bd3323f151ab8da498e'
        '759c6de6c1d73dc67d93b6a13d8468ff47e798d3bdae7ff324aa71ec9579ff8a5d0cf854eeaecaa78f6401b12703545fa7388864d7ab083f6563c7c952c6a666'
        'c55b877f4df5c5209e3fb9003c9be556c1f836a19991f15958fe5d81e721097ca13eaa18adcaa682a07f63eee3017ec28b608f7655df9d94f5c59106b851b8dd'
        'a2983892939ec86519fd73d42dbc8fba306a69552815a66305a386db47e9bf8e001e888fcf922ea51a923b64c013afb47f4635150dde588e496b76fd45d7e9ac'
        '5c1b8083dfeebabadb7f68fb25bde1623ea796b2e418adc0712e6d9192b54cf473ce0430a9bf3b737c5d849db2c86eb68825f604bf4ef4d445beb9de9418eab7'
        'c852788d4bae37310fb949f83941a79571e2fe54d645c06b7cfeeb849fa54c21eb460d938dd3c470e88f022ff6e740263c3aeff53b174f53075cb64cf929b13b'
        '267d98b12a767d0d3f73fe2fce8d72dddc740282a29e672d04c38251c2057aa011bbc78578350c0374b1096821b8ac2e40e1aa5a9df6882acbc04ef984690daa'
        'e26de0fc51e4624a580440bb454905c9a8fa72d1a25d49f43a5785e4a8ffcdccc834f8c9c842a75e58b4550e56cae3c021b370e6a142dd53b685808e4c1bb9f2'
        '1d6a152f4a169ca7c9c39fe9f87d6a52985ae75ddcc04de2a602304ec039526e80bf3fa4b0416c193e0c7a45148f965c3f09dfe58dc46001bea24b007e65571d'
        '6b140d13e773fa56062a1bed88043d548ab2a896d25ea107b265e52590dfb5a724d842e8190e17be84de32525dc58c9a3caf141684c5c565cb7c97561986b60e'
        'a1e792247d20da9c4f8377eb3b840ff99559fa647781bf82a254a8488a202fe5049687222589ee3b22fccd93743fb94c875ee100e0eb31046eac4510ea272264'
        '78de6a3bd343c42f6fed391e36e0d72f50d245637a5b1cc6e883a10f5051ee1fc81d5c96fd46ca1e8b991420d1276402ff8426e29dc7adee5cc6293685a9a323'
        '733b100ac188122f7f0516b4c980d1aa13df96f284100dd4938346d1a811f30deb56e7a4ca7a2734046c2e7a6dd67a130c5d97a6ba5bc2e374ca9e1fadeb082e'
        '8f387b0ca07b1a0fb8f5c69200dfab9594464f8d62c9028c586a70935d69d7b4450616f07fff1ba977839d786ca5754d1ecfd9837fc36be4d75be7add1e2ee04'
        'b88e61adda1461610f743fa1c583f1604f410c2d100f88730330445384299e725493e55c1dff278ef9699c64868b79f6b03033fc759c67d891d8ae43b858bf94'
        'f07fb0c9ff90eed8b2e1b700652761c0bbd4673a954980f13a6f366162cde4c52a84417b8e661734e141383b363ec2f46a402cbdbe9ed049533434931640bd11'
        '44e6b7eb40675a4304463718a2891b7fafa04549bceda3f4fe14bb24165e80d00ce0d9978581e4f85a73a18a831f2cbc17db4f4d367fbaaef37f58624ff63014'
        'e0bf298fb29ee3f8d5c86d82e4c161d15694cd71fd52854b5a3b52b9484c06d5e846ee705420ce0b86d2109b14686b5a40b178a0b68f5304b0036f83cde85f92'
        '3903355adfe933f1588d3bc40785f1d375074a318052178350a46ea5b76b7b2d3cf647d00855225f5709d824b6af341a3bcd08542eb8dc391b240a7376034129'
        'e83bb227748fddaa1553c71694cda62793c3090ede0ce792f0b0bbc91af1f6d022c2fae1d0c68898dc53a417023ab72081592bd9cc018893acf36254d0fca2ff'
        '94dbfe9759d9372d4092c7924e9e13bed171d06f88aee2b0b250ded5f3c905db17b4766ea8e33033e95d9cee3b0db1231c802b7e11d5f4407125bddda70eb4e4'
        '07785c2e5c8af0503c68717374ad8fd71338f0686386e95637a8c14032897ee4800bd9d8371bc2aef08bb85de5efda0984e6edf37e7d14d6f4a27fc278e483d6'
        '30cb5554045463d9bafb1bda5a9be1226b55a540d36d09fbd8408104512291c9f9dc4a74194b819dbf1e835efa3beeddebfdc53e91b7b45eb5eb31eee246c84f'
        'eaa9aa0f382c3c355535c0144084ae4b7bec415819d0f9de64be594f306f9af8e492ca78f7af6dfdab9f6424a293489f0c3133e29393ed6d4da4edb92caf8c29'
        'a24730434aaed54623e88c0d92900e72238f8d06eba93f49c59d4eb6263b45d6cc2c4d5a8fdbc79950c97d1e6c31fea8be8195559029d286683a9c84dadb3f32'
        '81b6cfd610a333e01f0b325332580d193be01b29b37923fd1e747494c7b594dcc6ad5bf663484d5ba643d9732a1cb227911cd646d3f0d17dcc2f295359e156f8'
        'a7ead5201c1eea6a51fbe7cbca70134af9e3d0f441a16e8169ee0c8e7982e4e9f43cd0c8ba628a755a161966478031d99e2147b7ffa7acd5d8bb4c09c13c70a0'
        '921a27d0203919282523e2adb9381aa470f8373e786dbd2b82d56ab91bad4487950da1f4f2e8e32b83b2d2e5694b25f3e340927fcb7d4344fb0a75fe15bdb45f'
        '13aafa57a9b783ebb873bc7fa3b19e7b5804459de95a91f8a67c72c19573941ccc4009f86e5d2c9b382ddc8818b6fb112f3dfcbf42f7e1f51ef8db754fe62d5a'
        'e2eaf6281c6dfea8a8f53a56be1bdf3f0c078917add57a5dbd5ad6d834747ec67e073e180e0bbea8222b615da21429efffe2d8288ceb6768c53e53bedc3e5f5e'
        'ed1a98e8755b06e422a94d3ce3eea2214b28432955be5080a88cf16e01de4f438140391b113f7174461167d9452478a112716c5d17a163d4c26dc197107afb3c'
        '7c2a78ed2e4e1aaa95caa524f5f0121063dc1f01117df56d913c746004ef2b64e0a1ba33d2a8deb5b0e9457270ca96d7d239631e298c62ea5a6143359a4e84d1'
        '3c1a8d4bf2a869f8adbc9a6d621834d616e0b7eb80f81101f92914ff2acea7d9bda1d34da0ad725a71709714381e1cd6b0bfff36b7fa174a35fe4abccc2e9420'
        '4005519bb08d0b393da499f30d37ff1ced59c6225f9007848510bbc106945d394735966e5a75cd9d10471db90e8c6ee0ff7244addcb52b048dd5d9be0e78bb32'
        'e44393c10b90470639144d7e7ccfe8e7dce4859d978bd6a2bd56ddeeacb2feff25d2dd4998d9dbc2ab5b733e8ad56a28115792ff2e9b0649ffe7797a1c49c677')

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
         '0001-add-sysctl-to-allow-disabling-unprivileged-CLONE_NEW.patch'
         '0002-udmabuf-Do-not-create-malformed-scatterlists.patch'
         '0003-block-try-slab-allocation-in-bio_alloc_bioset-before.patch'
         '0004-Revert-tracing-perf-Fix-stale-head-for-perf-syscall-.patch'
         '0005-Arch-Linux-kernel-v7.1.13-arch0.patch'
         '0006-BACKPORT-FROMLIST-drm-Makefile-Move-tiny-drivers-bef.patch'
         '0007-FROMLIST-drm-radeon-Call-mmiowb-at-the-end-of-radeon.patch'
         '0008-FROMLIST-LoongArch-Update-the-flush-cache-policy.patch'
         '0009-FROMLIST-USB-core-Enable-root_hub-s-remote-wakeup-fo.patch'
         '0010-FROMLIST-scsi-Bypass-certain-SCSI-commands-on-disks-.patch'
         '0011-FROMLIST-PCI-Prevent-LS7A-Bus-Master-clearing-on-kex.patch'
         '0012-FROMLIST-RFC-drm-amdkfd-disable-HSA_AMD_SVM-on-Loong.patch'
         '0013-BACKPORT-FROMLIST-drm-ttm-save-the-device-s-DMA-cohe.patch'
         '0014-BACKPORT-FROMLIST-drm-ttm-downgrade-cached-to-write_.patch'
         '0015-BACKPORT-FROMLIST-rust-export-BINDGEN_TARGET-from-a-.patch'
         '0016-FROMLIST-rust-generate-a-fatal-error-if-BINDGEN_TARG.patch'
         '0017-FROMLIST-rust-add-a-Kconfig-function-to-test-for-sup.patch'
         '0018-BACKPORT-FROMLIST-ACPI-PCI-check-if-the-root-io-spac.patch'
         '0019-FROMLIST-kbuild-install-extmod-build-do-not-exclude-.patch'
         '0020-BACKPORT-FROMLIST-LoongArch-detect-and-disable-sc.q-.patch'
         '0021-FROMLIST-i2c-ls2x-Add-clocks-property-parsing-and-ad.patch'
         '0022-FROMLIST-iwlwifi-add-new-pci-id-for-6235.patch'
         '0023-FROMLIST-cpufreq-loongson3-Make-this-drvier-depend-o.patch'
         '0024-FROMLIST-cpufreq-loongson3-Adjust-the-width-of-id-an.patch'
         '0025-FROMLIST-cpufreq-loongson3-Replace-per-package-mutex.patch'
         '0026-FROMLIST-cpufreq-loongson3-Use-global-physical-CPU-I.patch'
         '0027-FROMLIST-cpufreq-loongson3-Replace-IOCSR-read-write-.patch'
         '0028-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
         '0029-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
         '0030-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
         '0031-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch'
         '0032-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch'
         '0033-AOSCOS-loongarch-re-introduce-add_numamem_region-ini.patch'
         '0034-AOSCOS-loongarch-basic-boot-support-for-legacy-firmw.patch'
         '0035-AOSCOS-loongarch-parse-BPI-data-and-add-memory-mappi.patch'
         '0036-AOSCOS-loongarch-add-MADT-ACPI-table-conversion.patch'
         '0037-AOSCOS-loongarch-correct-missing-offset-of-PCI-root-.patch'
         '0038-AOSCOS-loongarch-fix-missing-dependency-info-in-DSDT.patch'
         '0039-AOSCOS-loongarch-fix-DMA-address-offset.patch'
         '0040-AOSCOS-loongarch-fix-HT_RX_INT_TRANS-register.patch'
         '0041-AOSCOS-arch-loongarch-add-la_ow_syscall-as-in-tree-m.patch'
         '0042-AOSCOS-la_ow_syscall-add-kconfig-for-module.patch'
         '0043-AOSCOS-Revert-rcu-Fix-rcu_barrier-VS-post-CPUHP_TEAR.patch'
         '0044-AOSCOS-drm-loongson-add-ls7a1000_support-module-para.patch'
         '0045-AOSCOS-drm-amdgpu-disable-ABM-Adaptive-Backlight-Man.patch'
         '0046-AOSCOS-kvm-disable-enable_virt_at_load-by-default.patch'
         '0047-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
         '0048-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
         '0049-AOSCOS-USB-core-only-enable-root_hub-wakeup-on-MACH_.patch'
         '0050-FROMLIST-gpio-loongson-64bit-Add-back-the-support-fo.patch'
         '0051-AOSCOS-ACPI-scan-Add-pwm_lookup_entry-for-PWM3-on-LS.patch'
         '0052-CSMANTLE-Revert-FROMLIST-rust-generate-a-fatal-error.patch'
         '0053-AOSCOS-drm-ttm-fix-incorrect-caching-type-caused-by-.patch'
         '0054-BORE-linux7.1-rc1-bore-6.6.3.patch'
         '0055-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
)
# vim:set ts=8 sts=2 sw=2 et:
