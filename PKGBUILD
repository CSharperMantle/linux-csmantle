# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=6.18.6.arch1
pkgrel=7
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
            '77abcf9beb28745367ca68faec508aab8f3ac5be3d50731fa1e5bb12fe7ac71a'
            '2a81f59a9d4d12f155e0c4a4dfce79efe967af52c287d124900468227dc9fae1'
            '850628aba717b0ba75e4bc4dfc5590b25c01b588568a16ec06a32499c78f6a77'
            'd6e9c31c7468470e3c8fa82e3866feeb5109313051d44ebeb14044e30637442c'
            'cc65a73f421cd720007037fb8511596d3260cf767de05ce4bbeb144288fc476e'
            '71acf58effb086b2ef74eb7c7b738d890bfbed7420919010f148933820c38f1c'
            '9bf452e2804138200e926685de4ae693666694cf89e71e7be3fbb88251d416ce'
            'cd6a18189f83123cb5ed9db3569730e03ee99df317cfca4a32e70b4a41c4026b'
            'a735aa60d178507da1437802902a97edb40a234fd9cd870e1195395aac6df536'
            '888a8f6cf1df8c8aa9cef2be6f268607ee8923e472162ac157ada3006cef039f'
            '305e35dff6299f2e12562cffed29227596d4e79c7e7e6bbcaa0cf261cc0cb557'
            '51a995f87f448d8c2e566da2487c9bd57cf7edfa0bce61c89d6be6923b5f9d2e'
            '2a7af3161b2f2d03fb3c53b4cbbd26721111f238adb2b9c572954d4923ca6265'
            '9b2579e629e9c6cb8fcdf98dcda3cca975e6922eab13d8952bbd4ca9a2016681'
            '4997983e43bf074708b395cae4bc47b2f26b31bbc83c1f658dcd834793477768')
b2sums=('f56b4894cef3fdc24d963985d4f497d8a1fd80cae48197aabcf58038132c3c03da74537b47411aebc158483f08bad8200544103f31647b711acb59c4d652e387'
        'SKIP'
        'e99d4b9d40339240b429af1f6911244851fc60bceb444d38e1db405d6c2bd5db7523392366e85ba178495ebb6c92fa83c0160f2e8632ffe76e2a6c380ea5dbaf'
        'SKIP'
        '5a92c071676cfabe4c6276de74fe4d17b957ffd8fcf1298c3a7bbfef50012529e02a40dcedc711021d4de5eb26c63fb27016353382002493ca8797690df34d5b'
        'b8c684b5baf73e687d8bb3379a757ec25d788b512b01fc10fc601930f087c7d411d338026ace88df603b201f512ce57bff28a2b646ddbf9e8ed9f65fba10681d'
        '477e11b3d63ad8d15f3b1ced6888a57d7760f41d3a02537965d799935af7558ce7b3dcd11f3a74e2b11839e20ed0fc7e54ab2c3979b48219aa1465985683ab27'
        '308166f637cf2ae3e1f4758b24bd7364c7059dbf12a7d689d8ad6eb67e1343be4ee277b379574e1e17641ef611fec09386d19cdaa772e159b57e1a350f5984c2'
        '1f1b144345834fc183a43ef1b4e8f0d7d4414b096f68de5d3fc22c461de9918e129eb6bb9941415234902f27225e8c47e98865f9ae2b064ccdce6ecf6beb12a0'
        '3d00e2e1dd74f953b0af515df2af478680852b12c7066957139cc4d78baf939c569b738f0f43a82d03f2d0350581114f888a92f5e9feb68be12f0269814ef5c6'
        'ea82520229104f075bb248152cc9f31071d3468dda6d236905481fb5b33679062900bb0a487b6bcf33e8361cdfb64df30c55b4f8de72f4980220f1a0daaa7144'
        '74c10fd7cd041b4833faf099156efa4e5de649da7107ab93f0d8526928be6f924b14ed235db30640f5a9d0137b65d88f848b405ad9919045405ac9e6b3c221e3'
        '849366b9cb1ba79724da09eccacb167680af197205c835f85b2cc3d57f94c456b06fc3dadde8e3d56743c665e12d6f157fcc4c566c1594e709bf99fbe8443f03'
        '36d3115a11853d2c7dc1e3ca623ad0722f51c6e2d0b85455acc6c56d676102bb8b708da505214a418af78b26908e54a69fe538d7ab20919bda3dc773e39328b1'
        '5b7e1c9a4e352e9cf86d252bdc53c7ed0c6a914bf27e5b1de58cddff12b1ae8929b9f2bb9a067e99423a0eca78315156144d48ac4349c665f109c86ac3672e9d'
        '46d938ca97fb3f1aab05fa8d6b4eca69e6967774f9a725650048c25e9c1a4bf9fc8fda9aa43757e15deba7bc9f2d161696dbc19446be922a0815faad0e55f50e'
        '56f2f8c8db54de3b8083c2fa18b7f7c3fb1f81917861eda4b292fc189e6fafa5d60f92d82bf945883b75d4eaaa1d697e40afc9417a7cf7603fd74aed0ec63f0c'
        'd4534a5a8229f711cd793f2683494ba75929979c2c749c45bcbfb4585664423054ff64cacd72c2ed8fb5d925af2f27dca01efab237de08850267bf12ace165bd'
        '045974e9ab7e5869330d5376656bdee855e1404190584c160dd310aa6bfa3bde718c7e69c5a68dcbc687fb8e580c008956ab5e74e1ef6935767fa360a6419cb7'
        '14a45d6dcbd2230763febc12935c7f8851e7cc8b3cabcfd6305341321b45661c1a8245a14f93f394d1096d46ad5a2222e264200fddbc2e53642056c589166ce0'
        '4e52b476057b4c89d6cb0557d15193a6bbc3653e6c24ed0cb5c198625c1ed5bccc33dc184b2ad10b9e8b91ffb1d8fe3575531655d40a199b818d3da47289ade8')

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
                 "0014-CSMANTLE-loongarch-print-out-CPU-population-info-for.patch"
                 "0015-CSMANTLE-loongarch-look-up-package-id-in-pptt-when-a.patch"
)

# vim:set ts=8 sts=2 sw=2 et:
