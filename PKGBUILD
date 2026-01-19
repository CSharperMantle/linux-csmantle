# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>

pkgbase=linux-csmantle
pkgver=6.18.6.arch1
pkgrel=1
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
sha256sums=('472497197b2f68d4dbf1bc32cc6dc669ca220ff4c0eb0dc39a9cff9a88f9a31b'
            'SKIP'
            '3cacf131fc916c2f9a9ed5b0a6e9dbfcd207263c25de844ed2ab337665844a3e'
            'SKIP'
            '51aaadd58c905ab2f3dab7f2e2b49ecdb284abe797439f712ac3f77c918c87b5'
            'e175faf735a768ea299fda73086fd54908fc2fe107b38ff46ea4243da3cfbde0'
            'cde52675c44a69282c5b0fd1c6de2affd8f8ddeb0436a2db8bb03f55a9a9ef42'
            'd146728a3b3c722f433e310cad21e93c53e64a7afe948b5b43b077e962750941'
            'c16845f0e9ac9d592e6a8ed2276b96749a58c7a8d95b23f0126a4ee92ee1685b'
            'b82a5f954d688f2d21823a807141596713744f0458d2bac3439c8c203bd6b654'
            '415aa6b21912dce689c11c6e2afcb6d2fb887f38a8c6da18b8f7727d3256d743'
            'c46de055ed82702c20d3c70cc2a268ed48a6fa4ad2a546fd3b339a1366954618'
            '30accab32bd0699304421ad347bd9866820a499b78d473d14e099600912717a8'
            'e629cc73e44a63c4a332c8f77f8e4baa01227a9ed4390bf5ef978b02be9b6b0d')
b2sums=('f56b4894cef3fdc24d963985d4f497d8a1fd80cae48197aabcf58038132c3c03da74537b47411aebc158483f08bad8200544103f31647b711acb59c4d652e387'
        'SKIP'
        'e99d4b9d40339240b429af1f6911244851fc60bceb444d38e1db405d6c2bd5db7523392366e85ba178495ebb6c92fa83c0160f2e8632ffe76e2a6c380ea5dbaf'
        'SKIP'
        '5a92c071676cfabe4c6276de74fe4d17b957ffd8fcf1298c3a7bbfef50012529e02a40dcedc711021d4de5eb26c63fb27016353382002493ca8797690df34d5b'
        '784b6e8e5fb497be064064d3a0a84b1dda852120306c7e7ea9bf7a2463c9c79d3d2df09c699dbb1ed7b1e19b8f5059fd1993cda27a5964627fbd55344d1cb876'
        'f0f3a73bd953fe1c3ec3b06519ca2bdec70231de0470f217b166a9bba44168d27e826898913e38f8045f05dc5b7d84eed6074befab9563814663f1fd9b882873'
        '4a0b268f1a28d4bfa37d9b644477c75a5215083414fe5cc5d637e2edc4895aace9e42b3b33ac0b3e2a15a18340bec651511fa3c347c1c3e347ed3418c033582c'
        'f4b5787523241762389a2ebbe391cc7f4fdef0408c254461f4a54d6f6577f6f7bb525552cd9ccc639da39f06b03f5061578c0c6b009acf9101f6ff17d63111b0'
        '9b349d174549daa31177f2f65971c2c6e8f691882c77f3ba2ff95d55592b22d49b5caf549847ba21fc776f7f29508f10a96bf57f9b04d93956340579e01c8266'
        'be8e7e21b4706e6d7c5ea314c080f6d50cd0fefde7a7694d424d82be6f85d5588fc683514d505f14f74c76b9b435d03281c0761cbb7d177222984f7c4710d70b'
        '6b00b56e99f3c534f51b3991a051c3a158a155c19de1e1d4f344965c56f84ea95b8d2c6fb91b96930847a8c68699a46393235777d6176dfd1c2946b11ea4857e'
        '4513616d06073e36675511be5375e64be7cc2bcff0fecbf959fae4485875d5c0f2428ac8df9492052cce9cf1cc99d44e94cbbd49364146a491d97716d8ca7595'
        'e9e60112c0b5e0d57db30b2dc7b7c0d093d5df846daaaccc7df4f1a8cdbc1e445542132d9db06d87210bacf495d9a95d655f4f227869d38d312234a654a233f1')

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
         "LoongArch-Add-CPU-HWMon-platform-driver.patch::https://github.com/chenhuacai/linux/commit/9367b1a79e9b7b2d09e330d1f4fc0cd195f82091.diff"
         "0001-LOONGARCH-drm-radeon-Call-mmiowb-at-the-end-of-radeon_ring_commit.patch"
         "0016-REVERT-Revert-Mark-xe-driver-as-BROKEN-if-kernel-pag.patch"
         "0017-BACKPORT-FROMLIST-drm-xe-bo-fix-alignment-with-non-4.patch"
         "0018-BACKPORT-FROMLIST-drm-xe-guc-use-SZ_4K-for-alignment.patch"
         "0019-BACKPORT-FROMLIST-drm-xe-regs-fix-RING_CTL_SIZE-size.patch"
         "0020-FROMLIST-drm-xe-use-4K-alignment-for-cursor-jumps.patch"
         "0021-FROMLIST-drm-xe-query-use-PAGE_SIZE-as-the-minimum-p.patch"
)

# vim:set ts=8 sts=2 sw=2 et:
