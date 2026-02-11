# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=6.18.9.arch1
pkgrel=3
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
sha256sums=('030115ff8fb4cb536d8449dc40ebc3e314e86ba1b316a6ae21091a11cc930578'
            'SKIP'
            '4815407239a6df15f8e0362ff652f9faf2e558fd774b08645e80ca664128e390'
            'SKIP'
            '9fed188f89847418aaf6416b64457a30bee34dcd0fa42a84dbd0f4dfca063402'
            '157126a09f9a0db855ccada3d560c5a2e469c91186596b7f6b15afd2b983b67f'
            '3240d8042fdf42c1aa8039c0ac4fdaeaa4fd6eb5d9c176914c39b6b477ac6844'
            'b94581a5c8ca354a3a2a8999669783da01e3b859d5d8771e4d6022f7ccfa0ca7'
            '66b318aac598dd62d21ddc80dfd301e3416d621ed2f59119c2d450636546361a'
            '36d6843af31fc08cabe402ed15e49a23fb65c1f4ad910cb5908dc2939e165bbf'
            '2cea769ce5a4afba95dcfb3d2557dbd620fc04af56067656496a4cf5af68806e'
            'f32382bbd962429aa93c7e16255167a305378705de8671298c843e7438d23c21'
            '4d24a48efcbd66ddf9e09dc518d01da15d6a8c7dc5e94017075e9c7fa15f010e'
            '2b189cd2aa5fc7233691ecce75ace6fc9d945ebdc3e2f63e52eca19077dd390a'
            'c8c7aae4226de65991181bfd7bcad1f90e138cad014481fa9d6f22558ec728d5'
            'cfa876c3dab6645d0c3b9e9d9e5c718d4da48c6f0054dabf0964fd6ee2b9efb0'
            '42204f03b56873a893945310d579d171111302f72b9384c6c51c0b6cac7d1a9c'
            '48d9e6fdb3d4285c7418785f8d92f62f985cd7c58b71ee93eb61034da65af8a7'
            'a86ef342386ec87467c46d0237865ade9226a06ff3b6aa9f73b5b7b338086393'
            '0f5d1044b1744d35aab993a8dac5c961c54969009c5728950a539ce88a18b7de'
            '03097be2aa75528c40c672428603215a5190b5fe41e369c67d2593ac1d23de44'
            '9c4024f617c42700b7ccd08a964fc3072679ec136a7728cdc179d439d78e5242'
            'a0db46928b931e9efc69ada00373ac25b66979ce5c7244c03e36cb2f0442a9c1'
            '7de16fd38cbfa8f9da681d80a4a90251d5cf7b2f3c8649e73a14070b28551961'
            'd5933027a7014908ec4c2e4485b351905dcc7ac83cd536671c0f068571edf3dd'
            '4462e567795fcfff3d380ceb8990df51218d7ad37834aad3d6eab28e759639b6'
            '0831d95067125009df348e807ff6370468c7c09273b097411807638d878a40ba'
            '6da77acb207097e48c898412e48d19190c14e279b20044ce37efd1d1151d4b24'
            '1c6a176cd3d49d45ef90ac68c654d7c31dc6a5b9345783bf1bc6f148bb9b53b5'
            'd5db05b0fdd1d20e65cd75a6a755069244be7b09316e955e50f90a6c37dcb67f'
            '00eb06399fe6b9253d7d392a7ca99ca3d2dcf9d4658863435327d23201039874'
            '179c48909f4fbfc4f02682b0a5c5e795bd972f270bdbf42f3767f2c9f07953b7'
            '08ba0c08241a8cf43bedfc3c7f4fedd72a95e1016860e51c80881715c64a56fa'
            '2ee4d715e91699b2eec199bd1dbd33e92fd2a0b1b989ba7c8ae2c571d99770d6'
            '6c4ad4e3d37f7cab50610a2e845ffde5781b2d29b546cb9f4badd80f71cfe4cb'
            '6f58c1d2bac5f2f1388819c18497940a29602e40bb4df559e55ef9ce089882a6'
            '2e17cd280ef590ba70b940015719bb723259244f89f93c117b34471f67fdab2e'
            '1978a7cbbb9b0c0739a3b02ec3f0d0c03ca86dbce5e910d5080e3fa7f8b379c4'
            'b0fc019b9b9f59b5b15595871107c03edc9c2e408d6e9614e5efb9ee4af05bb8')
b2sums=('9aed902e41583597cb7595efe77504630a621993d20f89365a93cf2ea4d9790a6361d93cbb7fd7603881a4f82b76394b7e12fb4e4a88c9fedb2d63d64a9d49d3'
        'SKIP'
        '0e9a6bbc9baf4e6706699257e811dcdb7d7e6c946a45f660ee56c564d907efaaac53387b29668ca3fc3082c5badc30ee082dac9d8de2bde72c79365af4050b47'
        'SKIP'
        'bef3377ad86440af76e9dde4c29c9f4aaad42f5fe343f7d31f5eb537d6d358602f996f5d63986af275f2e92f94e71dc28c320edc8c03d05bd64dbd8ed23d75dc'
        'dfd366b283243f95c318471fe35e3a36646a38388dd6c4d9746bc981985a02ea303d75127244e9feac14564a8f49385483dfb56a8842814bdf97ca747bc2a4d5'
        'a0903f0cf1edd06558f1fc1725a76ffbf8709593201b0e60ad753c20fc4d856d5fe1ee3cb2e76266f827cd1b3a8ccb09ae3fa3bfbd5efcbd3b2f81faf46e6d0a'
        '75764b3a67a9527171052faeedd427b1a14637b9033ff3d9b45bfa118528353dca7aa3d098f1d6b62dd431881549abec579956f936b870758c116e8e30c52ad5'
        '6082ddbd40a8cb7b6ce3f64aaa52ed11f3ade6ecb647a8ea4558bfa93e8e01ec12372a0fe1b0d19534654894fdc9d53521c9b59c8f9e2a006da45892a0736f7f'
        '7fc6e534d0654e295d1e224b96634cf27b296d297cd0978034bfbd2615fba86b0dd2484a92c2b3a757f37bb158804a106e93df9c3dcba1edb4a98645c8fd050b'
        '9063488d018682732c1864b4bdbdb8891b70d2af3ce827073f3d321cca3d8d7f5fcb7cc904fc8202d42f8ab5b93780f7bb089f8a32b29ad02f3fe3a3f0d7ea4c'
        '9a094edfd956052f1f3adb46382472c99ecb27cf783f70b3b4173556505cccfbf4d736261c407d8c0d3827b2f024b2b5c091fd7252f12803807a89fc0671e28f'
        'eecbbb660d5f8ad40a97cc0202484689e84ab4ad985cd8e3070ac38abf7b5eb9b78ed2c1b72ea0eae90a1987e9fad4ed5233b673905c746e918ac430d2eb21b7'
        '027086250c845f156bcf461da0e1d173a9d9329a9a2da0f02b10603c6de27eb789474782498aef14f74c878a9d69aa2b769005ca620a484e54033839d01f527a'
        'e0136086231e7815be367617a917ad3f87e95a9f167c7cf146205fb2044e2e1d432c3d53d3e9f922a6817d751cf8b6c3dfaf4a3a5f93589ddfb846bf98bb818a'
        'a815fc0a5da2644073fae078e7a5f3ff8a7d10ed2b19c17ffb48c50946483786326d0e0754f3e131fa35b861014e1730b8cce1316e29b192c9eebf601e46721a'
        '50ff901b335288ab7800a66e88fbd6fa1b2ee6bc19bc8e30231e5a331bb7c4df9fcd3c239bcd84ec953c6d6a894514283f898431341979c53b95c21d3548b2a9'
        'b19ef101dca3bfc60993405d244ee55204b8b4c064e976d53a32371248430beb9d0d8bff48ebda9abf61f471a32a8cac1ab32b77a63d82d5af6bc42596aea3a6'
        '8256cafbbc58b9395a937ad52429d3d12f27f28b75f9fe0e30df06e43881c4f26b14933a183b5e036c45d2c530eae39564bb656363b23f0feb9689e2e265ad5e'
        '547f19f9eb064b99757701338747afbbb4a4cc8773820622bbd9c012152ad880119c85a3591906b70c928b5b8f19bed6122040c48445b55d85fa122624ba8796'
        '99d4922b67c90024252e019c75e156c7f36e4fc62a83136053a6a114135eb8ecf698db1c931e981e62338b2ff534b6ced9c0d4bfff649a181d47ec6d78b23c01'
        '24ae2a98d23d97f4f18bba5c164c6b1ee871a6369b46df564f86158d67d30edea3ec5268fb3c33a4c9a1012275549861c602fdc1d5bd55b735c6c8f11a4529a1'
        '838ccb950add66d26ff182d7c4b7351d9254f81ad0c96ab49401339748cc4245872743c298fd738679b556de6b0c2913c7a39036087e3aa138cd1da4f07c9262'
        '1696af325d89b589792e4acd2273680b348eb37aa8add1c053a41d39de26b9961fd6cca24db747ffd103c4aa9ba9afd08df56bee1f35705010d45707f034e321'
        '1ea386e3cb13d0d4420c563067202d74e0191ee9d86b836e69e5a41bc9636950ea5735c028eaf1914bf330994dde1fe0d897873d70763e37cc28b558a91dd9fa'
        '678bd38ade3e4d0caf87c3cc9f749d2e508b330894c0e4efd3e9e0b9884f491d4f606614614035ca4be82dcd203f40444d061b8a96731c876b3a30676c4d180b'
        '8d70310450c758d8199ab237dc5974e39b2d5869f02eb605155d5cd41dd755894470f5f041337483f0479ac3c741b5fa7724b1b1200de00a997b9da2e768b172'
        'bacf12ab94c305e96a7f5273ad9e8d3e9c715fbda0764fd7b6eb977487c87d40d5e20a940ac38060aa2dd1e0cad24f0b3630fc9eb9627fec467351672a0470d6'
        '354fc37f61032ef442cf932201aae4f11b0b7c9e712d74e6d9eb4a02eb9c7752a7aac1334e3bd0cc9fef29f1002f9b0ee2b0ead52f501a36d634293dbbc7954c'
        '11a8f0db85365e9827eab3aa77ce0ed195ce33a8c13df84699541146062e308de0af09ac4356419712bedf1fe113088a960e7f9cdeef077fd163c3798efbd563'
        'ea2d0ca332554f8f300cd7c4a960dcc288f14a157063ca48ff56134a0b1f05d5288de9eb527858fc6b645cba78f12dab79b24bec02b4c5eb45a2d5c2e0ec198e'
        'e3b11f3af3312196ed01d1bdc752b1b3c9f44f3428113d56f1f1c830e827388092ae576f1419518b9a4ba153be8e30bd9b7d471e7a9f9afb0bb8047473c55515'
        'cd2b6b42a79d3d9c84f34ebf21074209116ae6efdc5965a4eb15bc500abceb2c054f7774a0597610d169eceea2abb42287e6b964256e103e756bb1bf54052a25'
        '0f5486f65207c22c8f3f3a07b8085edb30107ac62e7561417ad7e4b13ada178f7e2526db83b1b27f3a2171927b27b122b19df44fad5e877900c168933799da27'
        'aedd884b108deeeadc420db6128e97afd3de46987f60504a28cc0d1c5af0dc8c2d91fcc521692d3644f86c62defbf091740919364601b41091ccd2a3ff1263f2'
        '421526dd2a355d9dbb1ff6e20a30373e90cdc702485cae81929f41f2264030814745c618f72e1d274ff06014a8591652ebbb6a22d082e190952c08890e5aaec5'
        '3df6f473acdc2b4d1a5edd3833d23ebb5fc1efdae5ae274f79c61724b339c106369022ba13dc937d5672f7b252ab6d7b47b1d8beff87209434be819b76836c63'
        '2bbad9399f665af4a8e92f6bbab381381279cb9ddab9fb34a834079b5e4a512cb076876323617dabf976e5b318f355d8ea2c17a76f22e9d7b36cfb7314941810'
        '87bca9664eb25ed81ad04ac521bd4d8bbce28fd6f99478af23eac80a2259c8a31a6f338a4bb91f401443d72512cdc4ded6c981c871fb472a750add47b134deb5')

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
  make listnewconfig
  # make menuconfig
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

source+=('001-aosc-loongarch64-16k.frag.config'
         '002-local.frag.config'
         '0001-LOONGSON-irqchip-loongson-eiointc-Improve-IRQ-affini.patch'
         '0002-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
         '0003-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
         '0004-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
         '0005-LOONGSON-drm-ast-Restore-vaddr-field-to-struct-ast_p.patch'
         '0006-LOONGSON-drm-ast-Support-both-SHMEM-helper-and-VRAM-.patch'
         '0007-BACKPORT-FROMLIST-drm-Makefile-Move-tiny-drivers-bef.patch'
         '0008-FROMLIST-drm-radeon-Call-mmiowb-at-the-end-of-radeon.patch'
         '0009-FROMLIST-LoongArch-Update-the-flush-cache-policy.patch'
         '0010-FROMLIST-LoongArch-dts-Add-uart-new-compatible-strin.patch'
         '0011-FROMLIST-serial-8250-Add-Loongson-uart-driver-suppor.patch'
         '0012-FROMLIST-dt-bindings-serial-8250-Add-Loongson-uart-c.patch'
         '0013-BACKPORT-FROMLIST-drm-xe-bo-fix-alignment-with-non-4.patch'
         '0014-BACKPORT-FROMLIST-drm-xe-guc-use-SZ_4K-for-alignment.patch'
         '0015-BACKPORT-FROMLIST-drm-xe-regs-fix-RING_CTL_SIZE-size.patch'
         '0016-FROMLIST-drm-xe-use-4K-alignment-for-cursor-jumps.patch'
         '0017-FROMLIST-drm-xe-query-use-PAGE_SIZE-as-the-minimum-p.patch'
         '0018-FROMLIST-PCI-Prevent-LS7A-Bus-Master-clearing-on-kex.patch'
         '0019-FROMLIST-PCI-Use-local_pci_probe-when-best-selected-.patch'
         '0020-FROMLIST-LoongArch-KVM-Get-VM-PMU-capability-from-HW.patch'
         '0021-FROMLIST-PCI-Release-BAR0-of-an-integrated-bridge-to.patch'
         '0022-FROMLIST-mailmap-map-all-Icenowy-Zheng-s-mail-addres.patch'
         '0023-BACKPORT-FROMLIST-loongarch-wire-up-memfd_secret-sys.patch'
         '0024-ANOLIS-LoongArch-adjust-the-calc-method-of-number-of.patch'
         '0025-AOSCOS-drm-amdgpu-use-amdgpu-by-default-for-si-cik-d.patch'
         '0026-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch'
         '0027-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
         '0028-FROMLIST-PCI-loongson-Override-PCIe-bridge-supported.patch'
         '0029-FROMLIST-loongarch-retrieve-CPU-package-ID-from-PPTT.patch'
         '0030-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch'
         '0031-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
         '0032-AOSCOS-ast-Drop-drm_gem_vram_-un-pin-calls.patch'
)
         
# vim:set ts=8 sts=2 sw=2 et:
