# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.1.8.arch1
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
b2sums=('84b59e5572d91f5ea1bb603aa7691851bd9549e1bf18a6bec8e27eb8a6e2de2e33da2ad3e3aad501c793e9756e70245a16545e76b65a44ee52b33ccf5c3dd8e7'
        'SKIP'
        '308952977c15ac3ad976ff1d99d0d186814d4b03e1c8512fc3a4c0ac1ecce3f74be8f3900a7fd286492d4f930bedc089674bf713a278fa80c35413e0e6339f97'
        'SKIP'
        '512543621b3244ee00fbc3a6071a784ed63a269c8c8dd25da0da0a90269ba8539b558b555aa63bad9bf52d96148e3184ad6bba0b62edf9a5ba3111643241a96f'
        '652069e50060a3d84530f004f7064d98d6ac9bb02e690a3510d092d0df17598c9b3d564ae07fdb0dbbecc68d2d12d58c4c78c02cc08fbcbb8c01ba6e6256d922'
        '9682585b979585cd1e2b2fd76879954d0c101c2e27d989da02225881d1b5739c01bc8e8643d9e7fbef257834b6a08d8db247b15727f98ef9eac4c533a027eb26'
        '4f255450641ead6dfada6f5e32823ba02fb383d309122825cca941f33ccaed174eec65e86af75fad22082fd7bb2df5a3241e12589e87646f61202ef62b0dc690'
        '9ce4bcc1cc5aeefcb576bdfa78dc6206d7aed59b7f98459ae01325abbaaa39da70430446e98dfa43bc16e9329c09a38267a427257c226ff801995618241a006e'
        '46848748d6cd37c331994e8abfb2b4e44fef1366e850369ea10119bb6a42b293177e3cb12400f62b7f47d4363a844127675eb565eaa0246b38792e848835e57a'
        '317330ac39b82f1838199fead307825ef008ec8a4bb444e845bce1f687a4b59c3c253fe15a4655dbe791015d8a1e3ef541e7b99c125d786958e37104a5356048'
        'd577235a85fac3e64faa5f626a4d6f7890e3e2fa9d6fc8c8703521e051cb82d20d7dd103b11d1ceb51b19a2e00c019a9f76b452e2643a6e05082da483c0906ad'
        '9446d9d5846d110b7885466982749906225061ecf3e240f22d1c1066857a7e2c209d7309cef4912d33a085112b6aa59b87c1742c75fbe410fe90e33e156fae34'
        '3a33229787ab06dbd353f541de84652b37452e049f3505f3e55f27c3f7c68f3214db29b45560c07b2550171c087ed692d08ac23f3faafe0841740f19c7ba09ae'
        '0ce0e1cea347ce5c065e49b1958cabbed116968e7187c8b703db41805450c1473d4bace6d09cbac70fc27dfb923c3cd286a3d212d6b5fbf0153f27d80203564e'
        'c324a3137c6bf7bfc96266f6ecf32fac59abdc2470c7b82a693083bbd6a9753e31efc781e33364849c6700e52e9b8d8da34093d87fa52945ec38441af3716ae6'
        'a5cdabc2a203bfbc8050229c4f5a4617743280e0e6867341cb395a284239162b1e6f6f1883c5a3c68bce5a988a113fa0edb842f04200efbbec91af8de770faab'
        '44c8a2c3359faad3f3ff46afa3c5c3734a30847c0b93e1d3c903231ae5c24de5863dc38d8cdb97516800d7db76080b236401382cc1dbea024c140613f8a168fb'
        'b9b60edba143dccf93a0e309270a2a2e2803eacb4d9ab2697b1365949cc5996af1305b7d6d6726e9ceeaf01290c828e8eb2cabaca9265f5fc7729b60c84092c8'
        '63485bbef8da201811d53e521b869ee038854a006923949d1354e0ac1e7c22376a2998c649c1f9be456830a522953a1abeeebf1fab66cabbcf3fbf6339d04159'
        '3bab19926be96af9a0b31bd4bfe8380ba7ac49dca8af9eeeac5743c5b1dd7407f32a21270437df0e9c92e93ddc19300cfac4e0917bd157aeca4c470a6364c443'
        '1e21ef7035fd07198595d89a84c731b3e8d733674425c6e160ac3e382c1fce5d34d4ff51c1d5c112af2b3ffe3892ce118ec6b8d76201cf955a333e37f6b3f71a'
        '3e1f22c43e4077bf844bf6b0da25ac10831f11b051e115db5fdd347f4b18e3edb543512709fdb1b19c40796063157a52830afa9e8b40431842508d23591b58ab'
        'b89680a3b0b5177571538a6775215f730cf3a76b523418ab9fada6c431509ed63976c878413d875e1dc907c3acea4b125bce6857d4a41bfb90ff0a93658b83c0'
        'e4c9f02d76210db16b5f6387e5e3139972630664352b4deb3ec9db8655d3d57db9cf09206ab4e67b1f57190ba1f4fa2a440daac0aa4030173763ef53e824da98'
        '46ef42187d27f7615862a7e4224c04ccf7ef810cc83a27c1df7c61bbd9705427fc9f9bf11c6a1e0d314132254325512004b632ef8b6d4655ed8e4cff16fb9233'
        '8b451dfe36468deb69fe85a5e72ba861910b1b8f47591ce7849feeaf12f14890ecfba2fc3a0c49d98acc8ea86857b1a546948f7cb10175aa403f75f8dc989df3'
        '18d943a23f81f41d179883433e5504994079a81e0bb91eda4b7c1f79acc12557bad12492f738bc98173d9b2885bee40be04cf01558b8b22f48ea30fbe24ba280'
        '1075422402bd036831262fa8fd686c05721977448e951bd6a387f0f5384bf5b6a513066c42ea2a8c160c3586165961ef3cd8a0e477747c1f1878f082bd13a786'
        '88a39cf5735c57bbaced10c1e195bb4d5725d1815da87473cde77bfd464f28734f21e7e888166fa00ff5e8772d3673909ee3dc65d1781ee48c3353ede8023b94'
        '736090ec870c6e7363ef6a9b6ec1af66477558ee3f2c64cf25089de8e34013328678bea9cb32b1d834855599a4b7fe91ecc125e20048ba052dc023771fe96692'
        '03c6b813ed9c77afbd4ded1943a58eed647d0a95e001203581d86d41e86b4cc0a9ea6b5ec1d19fa2e5f88363395798d03e970e00279df693163942b65778053f'
        '41cc16ed3515db486cb24532782504916a2f402ac5ba2fbecd99b902087c5fc410ba0c253a616cf7d3e627488e1d77248b3db8b7c33d486f6a84a865ee8a255b'
        'b08f089369e49f0cc4452b36ab82d34485a9d22cd5e28cdad96d5e24c4fd9b28fdec3d42f92047499ef2a9fa91d2a13df8d25800089195a6e830c72bb04cf2d8'
        'f4b5c89d6d37a4e1607389d5f6f92c91495e78ee975fbde24674a7229d026954d196052a3642c35ee7bfbf0f9a9ccc580ab5020e5a7e28354978822f5c44acd5'
        'e11774b8e3c472b9c08d96ce48e4efbd9a8b3728c819afe51a9d6686aae4673dccda8792ff5154f3ec2fff3e62e55d786f0992450c6b2ebda2ca9a9d0037c44c'
        'f8a6b8109395223605a8714e4d9215639f0c111ccaba59b0bb22ac4670ad2383a74680800531549763ebede0809aa7af719f10553fc13956ad458207cb7552fd'
        'dc4004c93cda1dd7bfbaf38b067599b95c098b0ae995f0fa5851803d572681c09d82a33ae6a2b9c7b5a2363beeed800c62bebcefdff9af4d50ef240904f42645'
        '782624cd3d1047413eb7eba5b448902d18a464fd91d882b7500506d0078541a3917b10b6819de12a3b95cfac053f305dae86788007892d22b7a4dc09afe808f9'
        'e90ff31eb264caa2fcf3c702bbb6159795d91fc96598d38576bc85758bae06e85fba0127d62aae7931e785713b50a73d4375a6742bf1a9a473120cf1ef349a1d'
        '66ea5d02f9bf1ac55b3b97ae6b64ccc550b9a45531a1bd33527f1456ede8a5d01a7ae48fe262490eac8fce7c96f86d211394fd4d416e72a8a2cf1dd0bb21db4d'
        'f776b586072befc6c63d1b42b361061fd6965a4cebf2f427e56bc93deea7663ea8525ad294c486539f1284a6ddbf1b0d43e67bdc474a96748e1358c3c6ba064f'
        'a425c92dc500ba6d5b5344735727ab1a119c4e58d9d83904040382b69f9031e0617caccd6e68077a29532580d760eedecd706ad0bf46d45b149332db86109e67'
        '2daac6dc6e789393621aba3b32332c5156247f317f21227ecd3ebb0d0ff839320b2d10cb142e59684cf1d8a6c239d1aaf5d510a59472c1660b8d3c1221f7048b'
        '8aad6563dc47c90d454135134e41b006e3d3662996b9903f4d5fbfe7be0528c378726099f8b335c779fdb37af54f9c19d6ebe7bd8cfa51279a9cc00e701bebf3'
        '58887aae9f9b3f2123d0083e28291b3626ea6878e78948ac422c79bd36b7178b19ce132495db0f9b0a77a26e72a84f2695186211773f572bc07a8affddc6017a'
        '009df8a7ba17c13150669ccbde07b572b8bdd807c3ec3976c34d7edf9a04231baa64bad5446b996cbe16f7ee4f2ec166c33133449f72ee413a5a673b0f160496'
        '6ce1c2bd426c217dcaf854c14d4248d5ea6e42d6f778ced99496abc482e6577e7937ef7fabf548ec00d733df6c6a36a9a563d07af5c1a1ea1a9f78e97b279f3c'
        'dc7610a2216a26d94d33c6bc149c8b3718d935383ebc1fbf55e2ec676fd394306f12f03c85d8af61959284e854da6d8c442c7b455248d8892cc6e56238f23511'
        'baedc02fab544da4f56e9b62d4f92a17644810a675c2da254c18a8e8a5c3d5ae2fde66c50de17abe51ad85e135ea83313e0827357833b2bff6676f94f84893d0'
        '6cd9cc210e8d8cbb4cdc72abf057cca788bd2d2840b851a58307739736bd921cc326e88670e3a37bbc6fe6c757080a0d1849078f14f54748c4befcdd198102f2'
        'f38e6cd294b10e3159b1b06cde668fc0f928c853403ace91484d04ea6a3c8090862c97dbf4b690cb41afc357b53eaf7a0f262c07ff8a6df08a038ee341665dab'
        'b4714b488acae27f26b5188890bfccd9f53a1bfc52463b98208d2a367a5c10ad1e982cecdb1300f1bc76fe80ff82c385eb46e680cb02591f3abf49f3ee8b20de'
        '0d7813016048d60dbc45955b64e81ecffc1e3f71d19f15ccca2d7510ea462ccbecaabcdc82a644a8cde081d81eed598540ffa1152c6664c37fa8bc3b55c75d52'
        '5e73d60a15c32f0666058e5b8760c72acaf72eb814efcd3c986d5e3066dc69d2700a4857a6833a83f7e0c6c4bc3ad7f427947b4802a832a97f6a4a107c4a7a88')

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
         '0019-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
         '0020-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
         '0021-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
         '0022-LOONGSON-cpufreq-loongson3-SMC-boost-test.patch'
         '0023-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch'
         '0024-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch'
         '0025-AOSCOS-loongarch-re-introduce-add_numamem_region-ini.patch'
         '0026-AOSCOS-loongarch-basic-boot-support-for-legacy-firmw.patch'
         '0027-AOSCOS-loongarch-parse-BPI-data-and-add-memory-mappi.patch'
         '0028-AOSCOS-loongarch-add-MADT-ACPI-table-conversion.patch'
         '0029-AOSCOS-loongarch-correct-missing-offset-of-PCI-root-.patch'
         '0030-AOSCOS-loongarch-fix-missing-dependency-info-in-DSDT.patch'
         '0031-AOSCOS-loongarch-fix-DMA-address-offset.patch'
         '0032-AOSCOS-loongarch-fix-HT_RX_INT_TRANS-register.patch'
         '0033-AOSCOS-arch-loongarch-add-la_ow_syscall-as-in-tree-m.patch'
         '0034-AOSCOS-la_ow_syscall-add-kconfig-for-module.patch'
         '0035-AOSCOS-Revert-rcu-Fix-rcu_barrier-VS-post-CPUHP_TEAR.patch'
         '0036-AOSCOS-drm-loongson-add-ls7a1000_support-module-para.patch'
         '0037-AOSCOS-drm-amdgpu-disable-ABM-Adaptive-Backlight-Man.patch'
         '0038-AOSCOS-kvm-disable-enable_virt_at_load-by-default.patch'
         '0039-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
         '0040-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
         '0041-AOSCOS-USB-core-only-enable-root_hub-wakeup-on-MACH_.patch'
         '0042-FROMLIST-gpio-loongson-64bit-Add-back-the-support-fo.patch'
         '0043-AOSCOS-ACPI-scan-Add-pwm_lookup_entry-for-PWM3-on-LS.patch'
         '0044-CSMANTLE-Revert-FROMLIST-rust-generate-a-fatal-error.patch'
         '0045-AOSCOS-drm-ttm-fix-incorrect-caching-type-caused-by-.patch'
         '0046-BORE-linux7.1-rc1-bore-6.6.3.patch'
         '0047-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
)
# vim:set ts=8 sts=2 sw=2 et:
