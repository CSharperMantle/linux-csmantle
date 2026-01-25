# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=6.18.7.arch1
pkgrel=2
pkgdesc='Linux'
url='https://github.com/archlinux/linux'
arch=(loong64)
license=(GPL-2.0-only)
makedepends=(
  bc
  cpio
  gettext
  libelf
  pahole
  perl
  python
  rust
  rust-bindgen
  rust-src
  tar
  xz

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
# https://www.kernel.org/pub/linux/kernel/v6.x/sha256sums.asc
sha256sums=('b726a4d15cf9ae06219b56d87820776e34d89fbc137e55fb54a9b9c3015b8f1e'
            'SKIP'
            '57c22879f2228398564091db2ec9b186acbd56dfb0e1072f83418bfdd3829aae'
            'SKIP'
            '505d823490e964e66ebe5889a3701347b4e4e2faf1772b3964f0360a176eadf8'
            '60e26da620d96a7c0fad031d25b11b7d02a809d558b819bef2b10575f96e8195'
            'e380c642cedea5357c9ded7e8142e3f78295864a5866f6404fcbd4b7a105e501'
            '4493046550ff8c040e5b3c3ddaf6d4701cbaa9faec51af7b51ce842d0ea0990c'
            '5e303746be381e5f17110935e0134ab89943151978a9e45ea15303a95f869503'
            '7cda444834cfb95baa580ed389125b8f798353858fbc1a1554fa5f9a320fa109'
            'd3569bf874725839620c88ac6c332bd9604b482965b15936038c4b4d6b727de9'
            '063769a8ea16a3b6320e2c36006db793a73f1cd97d5a11c68ad2e2c9ea50e918'
            '4bdb79309b1988fbd1c346566828c44519a0745ce73aba3b628d2cb4cd30ea10'
            '716154317c32227ea31d08a2a5a41a1c0c7c1112bb38c40201eb314473823a29'
            '66a1b42841b817418211457adaf4d7cdbb9e6e8c91856cc862e42b3adcd841f9'
            '716bcf6590a818356b5c5355f8e3f4c57bcd806cc99a82aa8e9e2875c6c4cd41'
            '2e89c9cbcaac5467d6e75bc051df57d93dfe89abd012b54d55e7382a9a0ab04b'
            '34b3ec4d5ecaf4024acacc848692b7d8aaf731aa5b81bbaad87593b6306dae11'
            'c9ade215c2e780d9aaf16b93c74fdd8003237a24ec2cca5b37e0d8432d6c6a1d'
            '1eac01fa68c1a63d858e499e15411c1c57c2ba35d0dbcd6bc0ae93db67497ba8'
            'fdc21f219f4983560d7f3f3ed9201dcab977ae79e690566908fbaa0310e77fb6'
            '1bf01e2f4efe528c11abfc59367b83089f756abd6d1603fb22e38ccf21f958b1'
            '6dee741ff94e559b1b071930cb4535f20911e008beb8bf5f31c68ece24fa79a0')
b2sums=('3ad31b9b36ea2c8f865c87e63c97a4e7b6684abee35ae71d5838026de9f476edb4c847adab315235293c5f37f8f3b90799ae2b3d41915716710eae63acbf6863'
        'SKIP'
        '8ece2f1b2fc6530cdd65e597141550c184089a206b9aa49cb9e46d61d2e7cf9c3f07f35ed523670d892aa7e62626644a5b1e98dd9c6acd824cb7ad3254c17665'
        'SKIP'
        'f31d83e1e10bb901d0d25c1db0ad2844584ff1014c8bf36f342fcf1999f41e5e2d5ddfa20a5a23d4626c6b35005c7e01ebe8ae7f3de3d4b61a189a49add3a158'
        'b8c684b5baf73e687d8bb3379a757ec25d788b512b01fc10fc601930f087c7d411d338026ace88df603b201f512ce57bff28a2b646ddbf9e8ed9f65fba10681d'
        'fce707275497565f41d00605881f14d56336a59a988c790160f6018142274e45327092faa681fa977bfbf8acc83bc2070ab1d1cd4dab4c0945f00b867d7cc551'
        '11d714da19888f9b4e2a68f5a419a6cbcbf68e82caf7799ed5dd99b6659090f236a6388b506960997dac406c372d1dac504eac1a5f45603f8a41a068995997a8'
        '2e09c14967ddef3fa3ad47b6b88bc6a6af90dea3a794e0a766d7b7fbe008d4c8051d81db5b19d5a28c84a04d45e58b80ce8b50e8af0bdd61503a0198417451e1'
        'a4a305e9d8825cc0d5071e6e525ab632e64df9dd3ca99a294bc29dd56d2504deabf1fa704cc502592cb7138c57706677b2479f850b40542dfaa5a46786f1bdae'
        '3e3300189ce98378a4a7048b97abc7c2d1de2da3baa6d233462484ebb75973ff510bcca0db18f950bfe17ab2123320a014e9dab774ccabfe913bbf27d89575b4'
        'd2096fb96ec858b23af2b5b06c1276bca872de36f8dbef67de5e86999b198c518a73fe9acedff463a98b71670964c06a069557e62c0b1d1e33b0574c23f4bd09'
        '04b14cc9969d14c3c616dca3c17e9483cce49eeef0c45801ca0ac5c93d5b81e56ab9076ad208c5c99c2c1f58423ccf7e3de7e0a9623b31fd86b43423ff8deeca'
        'dabf5f09e6478fe3305fb69fd0f1f4e6294dfe5871901730af2362bfed617d52f9f80c287e9a5c821ace12541df9c36a5c1da853d62e65e258c70cfeedf8620d'
        'a55416d3f4039ae733b67f7744fe89b422082c2f00fa0ab6454094b8d2aa7f9dfedb5b14160da4f3480b34b6dc43ae3a09cb8bc245c56b104ed9d188aabefc3d'
        '9be93c574d5c53bfffc9320d378c95ea3a7161b669ad7c840c9ecdbbf93f281f1408d73addd8b604c73aac094a44a6a5b59688547546b0df5e512e1294ab0e14'
        'c4cbf654561b0f430fcd7e3af76851c3a7d3056e7162a28cb1dcf6a0556b1c1b6d861f9cb5cc9ae239a397dfe7bc19fcf863ed35819c42f9ab0e28bcbf62672d'
        '83fb5c71012dea90ea480d6f991fc515efea7ff7783502de31c4989f9b2cada625e4234d0e8499d628d0fd98b429bb818a4b7db384c967185509b684627adb06'
        '6eb975f0844d0e8e794b9766d6482b7aad068ce924575dc7163c92828989d48e68fa2c42c2cf0e783565a91d5be60461ea3c4da173fc56c4d3edaacaf66f8501'
        '0d870f8bf3af0bde03e5d5f49ea1c3e5a495cbefc90ce1207d6d2fbef79e946edf10f6c36d85f5d33bc382ea6d46226b9d920fc0072ee48e20c4a522d813d477'
        '39c03490e663e939690919bbcebb4cb693338dabb86f481a9ba3d0c1ef22e3dfefae7f11d863fc7306272cc2335eebed6f354b66af94aaf5ccdcef4c46a5a44e'
        'fbbd82fefd714ba5c2667db30f666faf676dad747ad8f3621cee281da9c501e5e61cc370e85d01e23e1e9db9b9b5fa85b9794aefd735001f74c3a4709c28a118'
        'eb9e7d486c3afd35612ec346314c25c7e99314de06cc0c0d81876f00f2004ddb30e20f67af4aa486bc9b5b0e0f6587a108d93087452e3fe8ece214d34ad45a20')

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
  cp ../config .config
  if [ $CARCH == loong64 ]; then
    make savedefconfig
    cat defconfig ../loong-config.16k > .config
  fi
  # make olddefconfig
  make menuconfig
  make prepare

  diff -u ../config .config || :

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
  depends=(pahole)

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

source+=("loong-config.16k"
         "0001-LOONGSON-irqchip-loongson-eiointc-Improve-IRQ-affini.patch"
         "0002-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch"
         "0003-FROMLIST-drm-radeon-Call-mmiowb-at-the-end-of-radeon.patch"
         "0004-FROMLIST-LoongArch-Update-the-flush-cache-policy.patch"
         "0005-BACKPORT-FROMLIST-drm-xe-bo-fix-alignment-with-non-4.patch"
         "0006-BACKPORT-FROMLIST-drm-xe-guc-use-SZ_4K-for-alignment.patch"
         "0007-BACKPORT-FROMLIST-drm-xe-regs-fix-RING_CTL_SIZE-size.patch"
         "0008-FROMLIST-drm-xe-use-4K-alignment-for-cursor-jumps.patch"
         "0009-FROMLIST-drm-xe-query-use-PAGE_SIZE-as-the-minimum-p.patch"
         "0010-FROMLIST-LoongArch-KVM-Get-VM-PMU-capability-from-HW.patch"
         "0011-BACKPORT-FROMLIST-loongarch-wire-up-memfd_secret-sys.patch"
         "0012-LOONGSON-LoongArch-Add-canfd-support-for-ls2k3000.patch"
         "0013-ANOLIS-LoongArch-adjust-the-calc-method-of-number-of.patch"
         "0014-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch"
         "0015-FROMLIST-PCI-loongson-Override-PCIe-bridge-supported.patch"
         "0016-FROMLIST-loongarch-retrieve-CPU-package-ID-from-PPTT.patch"
         "0017-CSMANTLE-pci-loongson-enable-pci-bridge-speed-quirks.patch"
)

# vim:set ts=8 sts=2 sw=2 et:
