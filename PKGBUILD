# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=6.18.7.arch1
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
sha256sums=('b726a4d15cf9ae06219b56d87820776e34d89fbc137e55fb54a9b9c3015b8f1e'
            'SKIP'
            '57c22879f2228398564091db2ec9b186acbd56dfb0e1072f83418bfdd3829aae'
            'SKIP'
            '505d823490e964e66ebe5889a3701347b4e4e2faf1772b3964f0360a176eadf8'
            '60e26da620d96a7c0fad031d25b11b7d02a809d558b819bef2b10575f96e8195'
            '5c084d32912b39d2bdfe53c252b94a091f23ef0b572a2306013a11e9f0f201b3'
            '642431546b3f83cdfc96165d6726da16119a613de2f73fe28ac43f9b3ec4618a'
            '7bf85fc1e3381e8c144d2ca6007c17549416d3892c46f127c9db38954f493e0e'
            'bbf6eef641057271ba60e2aa3b6e07bc39a3cfba3bbc8f13f9b38bd73dafadbb'
            '9c3abc268df4e6ceaa41f6d45dbec68ba992b890b2794c4a0894ab02b88646d3'
            '2e2c8a46491700cf8a950570a7726db94f2dde49dd9dd2f87c98e438dc5eb00e'
            '6743924d978b8803314e56e6e8f74d9818aff6efb65b3c88a6c4ad3badbad7d5'
            '68c1a1481736fd3583832fb05053bb4b398c85f194f18d2debc43b4a04a4351f'
            'aac51c35426cc15a4fc7a4c90e95c66db7ba16a4fcbfccf9bd3180651bbeb006'
            'c999431b61ab274a01d67d5efea136c406953b09b8040f411057042081b9b464'
            '978e6ae47ee131c1f63fbd4aac0e706dc472058522fe557194f56b3c1cc54616'
            'a119c08cbd37ea37c120e9f87259202aab99f91e72816bb538cf6df04421c02e'
            '52594c548f4d3fb7ba332f61c1fccca569d2fd4da940f4e58334f35d4984e5e7'
            '38550857cfe4c737fb95c4dcd76cb05ae43c01b78b0863543769fe8a9cd7fedc'
            '196d927cc2150b5e7d9951107c07378d90007403a1989b897d253747d8425228'
            '73a81fa1c2b2ed9a9636ee115518761a2b1835a80243f1be62b8358c7594c3f8')
b2sums=('3ad31b9b36ea2c8f865c87e63c97a4e7b6684abee35ae71d5838026de9f476edb4c847adab315235293c5f37f8f3b90799ae2b3d41915716710eae63acbf6863'
        'SKIP'
        '8ece2f1b2fc6530cdd65e597141550c184089a206b9aa49cb9e46d61d2e7cf9c3f07f35ed523670d892aa7e62626644a5b1e98dd9c6acd824cb7ad3254c17665'
        'SKIP'
        'f31d83e1e10bb901d0d25c1db0ad2844584ff1014c8bf36f342fcf1999f41e5e2d5ddfa20a5a23d4626c6b35005c7e01ebe8ae7f3de3d4b61a189a49add3a158'
        'b8c684b5baf73e687d8bb3379a757ec25d788b512b01fc10fc601930f087c7d411d338026ace88df603b201f512ce57bff28a2b646ddbf9e8ed9f65fba10681d'
        'fd9316238c9d3638c2283438f8752876ac49de9aa7de6cac0a7f6209d15dcdb9988af353e4044c627e6cccb86b12f8ed3912c6fa3e8be61af031c80275ce4ffe'
        'ac7e07c438da0f8d53d5b5dd3d4eecad0564002ffe128d31b32d06daef8cc3939ba955e74aef3c5d4e900511bd18f639039d6ec6d2cb56a5efd7693731a00c15'
        '83709e7f218bf1140c3512d3efb2ebccf66ed8e960196d9bbe52063d71956a51b37eeadcfd1c38b9c3a3075acd2a234df443a3a9b98fbcc9385787ce889b8161'
        '0fe07d345550ee0ecb9e5aeac8e47e4e41dbf3a335a3644ca4157e9739b74653d45a53fc140b0e7b9bd1c74dffd1a44aab8058e0c6e5168a161bc06a7246b8fe'
        '65140502e5ac9bb105894e61e2bc5de49a8c68c38ce7d7b335f2f4646cad16a15ed0277f57a0f8619ee866e8df8d250c2f2858b1ffef3ea0f19ecff91789ad20'
        'e4940ed6b002d677211155a13da1fc86ac1716847eca27d8fe0205af19eaf188461e24b04d430f379d0b15dd4795b0361f44e27745dbaad6e6dc71938d23d8f2'
        '8da5b68854e80199dc21246eebaa7be0d1cc3f06d9cc733907a546020c4fbeebf4ff49bf148a76c4ac6dde7738fb30f2c27e38eff7ded71ab59015856ee0edd0'
        'f662648b505a3222323a02e3626ef9b0dc6a73e7a3ecaabcc219ffc85daf84582c68dec20506d41f1d078e4423040a6e342cf2cce59e2cfee78c7112427ed7a4'
        'f706e994b209dbd3f6a4211c818b1a598908aa741d2e856c3ca420c0f2cec9c64a827377b14e517401dc97cdb1359d5d193826b8e4dac9e391a71680e2dada03'
        'f3e6307470730bd62d45280af7254707acc742a9846a4c91f8de755407787bbbac88b1037483abe5e94d5a17a5803c22d1e19ac70e9bdfaab0871622dacd66fa'
        '763e88f0f0a6b06e6da406192ec3dfc123b97fd5dd4daeb9eafa14292e4edc187cfab08f23163bc2b7b26fc7cbfa15bd2cf4a3417b8ab860adbb97e54290efc5'
        '77bb7818297698ebf70c90ec0d43aca51590b8329c8e4eb238c31b604d96d718a036c06fc42e6c9e5fa41b7d25bf54a87a8113935f130fbd17ae162899202776'
        'fea50d1f3f98979f7cca8de56f2d782c2c34b201bb2b600f665c7dc17b6306779b8338d450934365964ece3ec9fd25dda28f85bf406b2351ca9639e4f6b290b8'
        '2dae9670d3eb62b31d3d6f1c75dd85ad8cf2c3bf34f045137b31ea094761ac84fa0da2793cdb3cdd5d1f07c706047ece19812536e5c558fbd66668d4214d6325'
        '0c4f067cbbfee6671af06a50cd6fef6a77123d57b66458a6eb6f8b119380935ed48236c854502f84952d1cd97e9bc72807204485bd40e9213bafbaa92fedd95d'
        '4d44fdccb21790defddb0a792f6f1eb9016c87ab4146914db12bdb7cdbd40835aaba3742cc242749e53a18aacb9d5c5ccd63e5de4527f47fdae9444300d7d51a')

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
)

# vim:set ts=8 sts=2 sw=2 et:
