# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=6.18.6.arch1
pkgrel=8
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
            '60e26da620d96a7c0fad031d25b11b7d02a809d558b819bef2b10575f96e8195'
            '6381c09c2f30f0f13630e84bee702631b64ac0686bd126bcc31f9fe462abc091'
            'e6d46afb58d78667a4e117dbc4b9a895c99f75e0f45fdd7978e17f9234338544'
            '9f52137dfd1635f1246d45369cb39ef447a8ebcbf161a2aaea06eb64cf2818b9'
            '07d4a080350b7bd64066c8fe5b809abfc9fe6369f1910e578b3b1c35eb882a4f'
            '7ecf9af84c113669329e1375beedee2eeb2865561b6dec9ae05b6286c3c7c82b'
            '06d0e43eae4146182e77ab173436383ae03aebcd8a8fca252ce3274265d3b46f'
            '0974e4602fed221533a10aa91cb193f297c29e73df565de986faf71f20ef087e'
            '683b6d3e06aba999393e8db1ac515315e628995a1ab6d87c06073c1dfa947c7c'
            'f565ffa70fdd865ff849e04a52c9fd0081d92178f3be3a2ead52a26e87307a5e'
            'c21265f406e43d5ead71671ce33b01014a12047c927c04ff3b24dce7327592f3'
            '14b0be77e0412d6940bc19cebab48d60221a47d75149c0654170150c46b9af50'
            '37af3bb11ffda7a25257a874524fe46c25c1df99a0fafe71e9abd49cc21ece6e'
            'f0978137bbd84a4f584d66c46ccc39d9c46be5b4392051f06eeff60a73036d69'
            'cbf7176bdeb16ddd584f85ef0bcbf0eb103a41a1509b11ec1a988cf5918f1c51')
b2sums=('f56b4894cef3fdc24d963985d4f497d8a1fd80cae48197aabcf58038132c3c03da74537b47411aebc158483f08bad8200544103f31647b711acb59c4d652e387'
        'SKIP'
        'e99d4b9d40339240b429af1f6911244851fc60bceb444d38e1db405d6c2bd5db7523392366e85ba178495ebb6c92fa83c0160f2e8632ffe76e2a6c380ea5dbaf'
        'SKIP'
        '5a92c071676cfabe4c6276de74fe4d17b957ffd8fcf1298c3a7bbfef50012529e02a40dcedc711021d4de5eb26c63fb27016353382002493ca8797690df34d5b'
        'b8c684b5baf73e687d8bb3379a757ec25d788b512b01fc10fc601930f087c7d411d338026ace88df603b201f512ce57bff28a2b646ddbf9e8ed9f65fba10681d'
        'c071a82674c49462d6d74caf92512c6c0f88f466476b2382836093e31e20cfec2e109cf50ec2bc1df597a25e37deaa2a9ffdced409696839905197a4854ac8de'
        'e232825e26f02d07db33a720cdcbf216589e1afd55570d135288a7c3cec3dcd4c00a908213e6ebcaa1aa5e84287af71a3aba84c0bb8749ba214639df5f539124'
        '3934ec2e80a7ae0a8eb2d53e919af002de423a7fd140e987b94a199da663e36b10402aa5c319909a577503e9e6d0060ca6bcbbda4fca217c86104e9580889b3e'
        '9b9377596b3ee5e7fcf3419322082f780ed93e471d1fa12908a7414aea1ebf667b303e99d0ac7b1aa5ced22433363495092b20f256c51a1a2a19acfcfb7d0147'
        '0ffe4c392c1953f9a916378e78dd7b9abb60b6772b2722c3d0e202037451be4934a0148005af3cd70aff11f55d4d2a935e8986b1a00bb3e4a156d20cc382d52b'
        '8a63d42bba15541f0da8e16d1dd8c48e96d776a9d4c2108fcd36d7fae5d5323ac38bf2785559ab13b5bf108923e4fb56c350c1feabf822729d7672f54214d62b'
        'a0fa9c687cc532a29e3847152eced03b285a1dc5a2c71d7f28ca018db930df73bd1db39eda388cbc764234ac3092c8c899ffd8a10098e8ce9fd1447f75155ca7'
        '9284061f10b8321d472bf12c517eda445b762ecd2495a18caa63bba66471acbf5f462da8438350f594a7992c1198f46c7690c141c2082430c259f9298c9ff5cc'
        '932d8afd50ce5e5084275a8e2d0deca64b744d4e9c1c908cb91340740a7e729a12a1005e64d82feffe2f6136e1bab49dbc41e566bfba2c0b179dccc78f32927c'
        '7754d74e02b039cf32758247e4180bbadb4e042c260ad2e1f1cc8865c4ffc03eb54fe25af2638f9b7680790ba6189055cb74453ea326514deaa6c012e738ba93'
        '32396eaa92f3154277b83aad7fea874a03befe3098a22354c181b3ab3d0f808365e0357cf2cd7191e90e2adcdd5e84b02350dc7288904cff2067e16fc5b31663'
        '13288b734c1fd9c13f9eecd295ee8e3f30cee1a78a6d16fec90628a83d7c65975683c92fbe04da8b0df7dfe1ecbcd62407752b3f2cff50aa3d10120b7a637978'
        '3862f9a50ddcdc74b04566d5be978bb95129be66fc9231d03b5821c29e14ec91c801300d90c0683fb40f56d5796719ca0eedaee6b14e1a528915a19a6bafc1ad'
        '13067fe7cf87cae2bc7bae93c5dfa406905da7242cf491e7fb4942e27f3cd096ab02290e07616dfc83dcf7dcaebbf02e69e0e566f3bf295b728c45ef3d9b9295')

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
                 "0014-FROMLIST-loongarch-retrieve-CPU-package-ID-from-PPTT.patch"
)

# vim:set ts=8 sts=2 sw=2 et:
