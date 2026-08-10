# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.1.7.arch1
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
b2sums=('1a1884d4ac6e5b2a49b5f4835635c47b33552568a01b2cd65186a252da00e0578af2830c60a88208ec0834f718779815663dd7be148903b58f72e22ac8673e94'
        'SKIP'
        'f3c197f565e52a2b692798c0afcc2e783e504fe8fe34303c39ed50c374b81d98f8d4b38ef8e99cc37cd7ad9e7fa4d122a961b16b8cc20f80f8af6f59b3123aea'
        'SKIP'
        '512543621b3244ee00fbc3a6071a784ed63a269c8c8dd25da0da0a90269ba8539b558b555aa63bad9bf52d96148e3184ad6bba0b62edf9a5ba3111643241a96f'
        '652069e50060a3d84530f004f7064d98d6ac9bb02e690a3510d092d0df17598c9b3d564ae07fdb0dbbecc68d2d12d58c4c78c02cc08fbcbb8c01ba6e6256d922'
        '9682585b979585cd1e2b2fd76879954d0c101c2e27d989da02225881d1b5739c01bc8e8643d9e7fbef257834b6a08d8db247b15727f98ef9eac4c533a027eb26'
        '4f255450641ead6dfada6f5e32823ba02fb383d309122825cca941f33ccaed174eec65e86af75fad22082fd7bb2df5a3241e12589e87646f61202ef62b0dc690'
        'af9ff2037c32ad83ae801839d3fbd2e308ae51d30abb7a52f8dad0d666c28d61cd902d9063c8cbf97d4ea400ce087e5e2d2cb23c016960739638db317bb50ada'
        '692840f7a7f0a3bbc6f53dc93a1ed1d1ab20e7a01fc00c8b0648531e8d2332712c66c04dc8eb8d12e4ba2081a3bb891bbffc57af0950bba12c677651bace22d2'
        '39fc3253ab3483e3e462ed16535bf50498876c58380206c64c00b27a72378881eb3da1e738c9254233ac6e46bb34619eb493d8ad93f9d4b966bf2ae10e258cfa'
        '1cfdad409e6d947230ed48abfbba45dbd7e3ca2478ed819f2be928768cbdf2ec173264199601108654d49034f65c8b0bbc0e8fa1776fe1b5f5aafcb1bf4142da'
        'f73cee1b55b53a6eb7b95df72f5c0575518828fed3b9ebddab47c345715a92fe178dba11a8b3718b2291c7beae8c2f206135e02a6d6a8be5c3a5bc43801f2832'
        'f76c42700e1c0744ced76b593b7fc7d9ae8d9f52c2dbcbe6fd9dd0df005ba54d654d64ed61f11e5d47053db42192f234c5ed0e84e484d26e4722acbd5a99093a'
        '1d0d1c2b7f64a7d311a6bf464ea46858c689b49b9f5a4bf3c69e9af8ea0d916ab6b27a67e53fba0636ca9a92e01129c905cf567051ce7dd4c9946a3f72f71822'
        '2928eb400fe98185532f4a418c8de666f5ae255dacbcd21189266adbca3f45aadc20944d89641564128b880cfb21f748dffd42d95e4cb41e06350f8e78df5e49'
        '236077560d785445f932d16eccda8c2764e2a3b88e891cfb2bd265e8b0fb6816b958735f0d7073ae78fb42845afc4aaf5a648c87b0220783bb1332aa430bf6b5'
        'e1aea7021d721207d1682c1363631eff35733c287a15fc9dd0380ae994a2a4f8c8b4707e410af38988aa877efaf11739c8d27c3de1cd88aeb3b2e8a81642f024'
        '375906cab264126ccae4bd89fa7e4429fa716aedb035db305eca5dac35179809b4e2dcb5f6367be8478917a26ea86f55c01cff449dc57610155e2a3e9fbc2bd6'
        'cd656a64e54c040dfaa73c1df017504041eeb8243280cdd1eb1466283ee5fd7150935ab75f5a7409f938b3fb15a99ceb12961cb2f2a63b3e9fd3dfc1f8d3e9e4'
        'c81a0fc121f1a19cf1d72467c6097542169329872d85c717b7082ace8b16f389034ee782e4dfe1da0d64eb9d2168daf61a766b75ecc0bda6c9898806571b9811'
        '9219e2bb93dec2a2d20d625fa41e3c6ca4aaf6cc04292c35da71f49183318a0786c4010df34ccb316a9f2abdf4d639d97f2bfb9c7e301e99c2fee4bcb03a7ec8'
        'fbb179326f00e7c31fddf41fe24f4ff55036eb75db88cced4efbb6dfbcb8649834cbaf1d75079e3fd928d569231c25420d1b8d8b0a131f1be5388ba22ece0c90'
        '79ce517c2564a98cb235832f6b05883124a3fa852d7d8ea4eba3310ad45e9dae79027fe7d0292807826c147d91df656b4b2840fdc02c93729a810ae0f8cf6630'
        '06a2cd7013feb79dd6664ce9f7d84b7afcea389ba130d467022b02e1eae15715a7469943f2aa83d39739aa25e8f06350b8d196404e5712b97dc37c9a8e77c8c1'
        'd3a719f3df7a3115841120f6bb022e9a33d1d1349d1c562b3b6a953afb8e1e456df8e9645267154cdf22905a30bebf45980e7449848f911cb590f4ac4d487c55'
        '9eff7f5f82d65a1765f9b750d3f259f292432a7a6b4820d8ffe9604cbe76e117daa9ad4d1c7a6a4f6857fc37d6f33eb13ce7b9ec6eb9441b443715c0945db802'
        '046ea36215bb7670bce70b9ba429064c11a853f904afc351eabc25ced23f7d528195fd33d0b43fc7364cf81ea5565284b830493da4b75812cf94b5c78e9f2243'
        'e97d32d9f2f40a9834bcbf9fcb3729ce8d3ac2439f3f42079d5eeaf8283c24e9aadeca3d1e20adde4105304c234df4db6b5fe0f71ca69423042457b20503abfe'
        'a260ce3f915f047c6ab8d7800dd9104c3b0f8dc7870d41566418d4d8b02ad2a5592a424aaafd09ead5db22736cfad3f30af72da219a4c39846aafcc0d0694280'
        '19e5f3b22930a00039fb56fcb463b0ecc6b277016f0d3dff79076d2f2a6e53146e3c9b02bff2dc67bec49c3618f940adde1954358bc3bc1b0ac05b89f9292293'
        'b8d8d138b4caae7dc7e42a5848a808f8534ff5ea953b4dc0da2f9185e14cb8cf0dbba61872f3dc4f3e30201b4696f5cea3cc3835248a728d6a6129bf1e43dae2'
        'd30288057586000f5164e99c187d06cfb2dc0b13f63bf8ed12564911a5495bbd33f7d2f646dbb967a06f6ada9e6b1be3353949a29367aecafcdc9d35608e08d0'
        '3e6f379c35f0ac2d8872515539168744961332cf3057eb710907ece7870489859757874b478346fdf3330fb56ebb96e03d0d0d329f8df41b39a151e909c139b5'
        '82915dc62608b8e89c9e970b5fe981ff92c74690891f69ece0a659f5f6521d712d50b80d963069308d231a186f08f8317095f4280079bcb0c39b6beb846ee2fe'
        'ee2a2fadadd4d2108bb57b9af77c6c7902155647e586de9605d709c4503c04b61ad270b4086e8f22d157d7fb0ecfecb515a59eabdfe82574d53ee19bd2b14f42'
        '25b4dfd88a6cef6dffae86d310d7e4b93ce2a24f1efd51232eee2c6f42069282e5f634b238652dc7526643ca912e696b1e888a1746c0e166343966da2a531fbe'
        '27ca7059272d34f89fef3f6a4c1f5aa28ed6abfc4d76cd63e6a6e6cf20e7f6c93022536b7db718f90f871ff16e4a8b240f94fb7f11113de5cdd14c16b69b1aab'
        '533ecb8feb6ce6045aad4237b3a6a3a57aa94cb676e5650ec74f4bdcf6ba5c22c9089abc83e7283d3290350f42e0e67a5a4a304c4fee17d4ccc1598c44db6b8f'
        '0944e1fc6a444f0d5233b897bce6ba32ef595fa509bc0a6d9cb266b84b7a86427436c6a0856d85bed927c690579bdfe2ed90c1dff82dc43f906c442d603e2acd'
        'c4ed520bee368e27042a821d01930b01795bf99f1f40a9365222545012eeb1e0252bde908624aed3fb29106cd382e4cdf0bb47fe3a252a46231559a2198a6304'
        '5e58630abd6009415cbc77190006d7566071af66e74e819ef7ecff2f848a77688ff0d15345d539ad0f3bdf3ba82562d07e51269f82f6de136fa0789224debfa5'
        '1f9f4658de383f7e1ee7b1c05503b9770d63ff171f64dbdca8d77ea51e43ecc5d623bf0512ad6b0fa4d2b5bbfc9c83b9fefe9e18822c2ea6651d390826fd3650'
        'fa715043094b775e62266207f5fc947302664e2a53d25dafd1e8dde3ab678eba50525e9408e9c68a32048a8f9d0d817facc7365495986c7e1cae54bbe713595d'
        '831e3a34b3c9b977c62e13899880bdc5982f98644f1d7ee79decc640d6d2c45fc442894e7459f16436dabb807b50818139670699b584377c20bdcf366345f092'
        '85cd320bcdf7c88be9d9e5c27c7b5d23b04602f84b607be7765d135c71682ba88d7a2cb006072e74868dd2b35b6f772ed11a16f41fe4b92afb92a91c932d3f46'
        '089640e84f9a0bcd45208f728a45604c2121bf4c3bc3379bb497187a641d878b9d35e70948dd2677defdb605630c72944b3e391aff500fc84b5f5817c46de5c3'
        '605d7d8bff9f04f16825ec66471bc46ca361cb0067194312425f3d860f18e4ea4c911f4d01d1ae1ff879ee228a65660692f75f7b6322124ead579807d37ea037'
        'f6261288922b4f3daa3d59e5294491e17ec0cbb19530e59c73ecd7be179b746e00ac1b2aed8df011c1d3b66a4d66ddf0c84bdb8108236640406a1cf749dfb2e7'
        '9aba2d5e2c8739467ca5f30ce41562c2f54017eb6dacde290eb14cf1bbc3b983e2267a0086da0a7dc3e059f4b98059ab3d2eb4eebb87903b7a7b97505f31783d'
        '8f5a7e4a636764d68dd0004ea67c02c674659212121fedb188ccd94d955aeaa2f3ce429848330f01a2427bda43d701c27b484b1cc5b45d720958f4b194ca600a'
        'ab0be51e78a693d7ee90600268e11326c54b66c15d5e49d423c2586b7fe74c5ad6d7668aa2930415ef2c6d7c70dcc24aab02b6b476b9b44af7baa63dae15e7d0'
        '670688297bd9b3a870ff17582636dcf0cc50ed90d28cd4e3f779308e8a202dbb26317e74d4db1a8b904b096bda332fece064e8a307852b98beadab906282f313'
        '21690546c792330bfce321b7fc9939edf1e333660db90730dc76669fea19f4a2789ca244fa622af9efbfcb62110419d0e82a824c597702803153ed46e62c2745'
        '4d52aa1eb1b6db27cca7a5aee69f917aa2ff110c2a0f51eaa75823f1ea2d6a2379c84689ef26d7ec729bd3aa32b84f98b4d91e5e2e2a579931d4df98cf79a277')

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
