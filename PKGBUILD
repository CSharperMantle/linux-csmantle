# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.2.4.arch1
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
b2sums=('1dc0bee4d040846ac31672400339c179daf68919b2d923261205febbb4ff654d1ac21a4bc700f5bd46a7676335692565678b8142549d83c1d0a0da3b9db2e3d4'
        'SKIP'
        '911acab50d12d1b81980ae5b639d222e6c2b4471c08b2eb0bf6221036ca435b18a836aac8855834acc56a0a6b01eb60087775df4f83f33d060410327a4786f30'
        'SKIP'
        '43ad5ca423903e7a1a22e1e60fad9c0e65a5081b138222b780396e98115d04bf1d2186b9f9d7d15e066ced9cc3373e8c07339abf32b6ca71ba3e01f6dd1e32a5'
        '652069e50060a3d84530f004f7064d98d6ac9bb02e690a3510d092d0df17598c9b3d564ae07fdb0dbbecc68d2d12d58c4c78c02cc08fbcbb8c01ba6e6256d922'
        '043c18764e8a11dc8da10875fbbc63d63ea001bc176f8954c8ca74a3f85f119ab2cabae90a7e3571e4721e128ef59d7199332b4f2454fc1fb4430cb39aeaad15'
        'e9fdd4f06b918797ca13cbf225aaacfc2919aa63968b8da2e045687a5aa1b10796678782e9e4d7e864adeb714f013e45941af1a360af79d20f76bcbcf27cfaae'
        'e6acaecc078f88504ab40f025b8f3ec91fac3550c51df257e12ee9ac0a2bd195f5933fa10d17d7c3d47ea6446478061db032778fe44be4076dd826b52bcbbdf6'
        'e9d54154a5221df8e09191176a6a34a4bf863266405b29c1863ebed2b409b362057af595cce27a4d8e9fcee700f7eaaed37ad44f517ebe95e1c532f3996a9c13'
        '57f84e837dbcb8ba1519ded6041e1040aac509fc34769c5055daae9671c5a338bd3524831cf5284f31a938a938fb92a4369e7db15fb406919164c060877c9747'
        '341a6d821cb34a1fbb96dd8bbdb68deaa7691a21dd5e54d7dc9a86f6f232e601ba91a93313b37c88f16706fc750b239301940f47e25ebca1383e63073bbc56fd'
        'e79783c146716513c9daa217e50f362d29e5d7ead2afb33bf6abfbacb7ae0f2e9bcf2bc52c2c2fc91d61dd6be7ec3d477176b4057cc14e78f36676dcf7380785'
        'aaf3f8583bbb24d417b5fe2455355e2b9d82b9d2f8cb550925eb59046c26e5f095bd8c5da623a4eeb3a4874259941c1ac83d4742c1ca4720aa8ed28444cb2edf'
        '8776aa487241a0296f2afddede98a191e91b6446fdf8b215c73575bad2d7e3bab3c3f61f22d948955a570e05c4488b60188d46263048bcb69be29ca863a8a51f'
        '496ec332549196e61bbeebe76d4191590a8edf6917ccaca3546babdc2aee1a1fb2bdc0fcfaebed3658a1564eabbe59b6b9127fe7e202bb066e02905dffbd56d4'
        'e2f6eeb766327e513a28750c4194ad96300f7ef0dff93d3ff8ebcb749697933cffda224513b66a7f1ad05791bfd9716d4775540cd227e62b8857d3be0cbeaa3f'
        '3cb6d62284648f233aaea0423cb39801d49c137b49770e842df2530098a2af2bffda095c7c9547d6ef99008d001d35fbe62d9e511b55c2bff2d8f2924f29866c'
        'd952342185dd99554941de3c19454e847daaa709e89bf78a70db771b7ab106fab34794f15bbbfedf568c90d38d645255358569893e64cd893e8376eb7ec68da3'
        'a7a419fb6a7168d06d6dfa21957e073bd567fe22559f0b5fc3ce758f520c7a659c2b7a6190997f7f9b0402cd0534965baca43d96d3d421f83b2e05af685d17f6'
        'd0fa82d251e1275dfacf43df6c9bb0bc55567daad270436b4009509b5de2fd993d4e6d913a2d9f92dbe6c55444b879d934da041863b9c9207a09b637edd7519f'
        '2492deff58a77f0b71b8456867ebed9d2897be8de7b022e194416e8bc52d500b7650fb278a503b451505fae475de31c46cd3e1b50dd40fd6bc76a6adf83a1681'
        '7e0e2158ca77598f022903cf7f341e81a4b34ea3cf6387f9a54586bb48d881b9d9f5a72c394a970dbd3041839fce4a7d78bfa8250dae8a08240b462863917450'
        'f9d0cc4a852bcabcfcd9da8f5dc9a62689c91d776459c6d80ca46eeb1bc2e439466ffd1e22b69dbe44d36873b4d766dae24a462fe0a5b850f39b9abca521bb23'
        'afe54f23029ab5a7516136497f48620a076c1f108f33c8bcca9148db5f35989a8d1c3bd95db18491d5190e225c985e46a67750629769927b7ebbe3b0c0531499'
        'bce8d740b7d2b7415de457b90cece249288d63c07e761cb1b6b1b1c5dd7c3c21cd1bd02168c0ea13c9e5a2a98895ff8728a6dfeb00a81253c6daaa42c9b83cf7'
        '5c1ec86e9ebbb5100560fcdf57d02e08627dfd27df015c932067b9577f434f3bf0c7b9a7bfca5e1a841f70d83323ed3c3f020d85514ba965cd6339ffa569c58a'
        'b9e331bf60d53db7d5e5d346852c20a4e8798d1a33ab2e6c7535c1c30d71b2a24c65cd62b237b05974aeca7f7875f996cd229f23e81ed611fdf36d3a067a7a4e'
        '7613b987cacc81f666fc5b92b21bc52d9d4fca33df900e632d1993c131f920634ac7b3bef32a0748f06c1bdf441ea846eeb39c61593fb94936737371ce8fc57b'
        'ae6c6118e5a4d38c3db435348c241259a90078db9265d40b2a4bad2db3f3040bf8a018c4b02f325f9403a59fe82b3137afc565d9aa3c0fa638b5ff0e007c6f09'
        '1f0a507a3c464b6904609d8410a4993feb56b3fd109ed4d1417c14e8ff4c3d9527d9e94b3571f536564175492d0d8a3980e13a24794d22976b60685c546aee58'
        '04920e4629bc81131d876269a3969e4dead517b3eabdddd64cffe08d1a58ea1c466ee676840998eb6a4641d613c8159e1a01c4576ae8c2f299156b3ef619761b'
        'fa87d82ffcb9d1fc797e0d95ac5f785f5bed6a6b95b233980b7c83e28fa2a2e5751bc0a1396e9ee88ea65041318c393b5ae8d7ec037a0a92987588e01277e41f'
        'cbc9ebce7bb939272461bb0d6d2a6177685f9071afd6ba96d938e7f4083f2f091d7f2c869da338c8730508bc00c7c05702507aa375421f0606ce0e4ae4aa40db'
        '390c65f0090c32a7fd8737988a33104c062a16c8d472d20060c18b148e89ab9a919fb5608726020fd368e7da5d3e3e6c06fa8317688a4e7d403a0c2a8a971d5d'
        'd0df13489519fd24870c87c80270657b352513aa08d334ae78ed1881619baafa267d373fa5ddbfd284a41420cf44afac873c8eebacf0871d474c9c58383dac23'
        'a2edf99fd8414d969065de9f5c4b441999e102d4b0f476b7a5ece2c751d604020392538ca12154844d9269d462e7b675243d15112a9b8c569f778dfb0202aaab'
        '917fbe35589f5d3c5fa4019e7a31ea6395a531da5aa7be183b4ec2264c08110727d6aa7d2a5ff35c1344bddca9fb66912b726f077f756517f0461e7ed1a787e1'
        '942e70eeefcca77d75591ee6cbc3264a3a00585f016443680fc707b0beeb55cff190e45bba3c0058122b57056dc4bb5052fddd0e200c70bec4950dde5f32b010'
        'a66b154f55b9adfe13b48d7752da6ed2787663f323eca0ef108fb3093bb4759e7a5d9d6ad57cde0009aa52dabfbba553b4e4613100ed544b5d6b22e148070245'
        'bfa7e9ed8193763f86b5a8869b65e822bfaca1fcc9c863c39170b1acc2b583d9e176b3ca9dc46469c07e00d266a46c935f3089b586c4842be85dfc2813eafcdf'
        '1ab2c95078607c3ef229de6f3ed2db34c7f9735f5bccc7eeabae1f707572da5e38008baa05c7f773d67837d617fce2ac97203212dabf07a406639747845df638'
        'f8d236b7b57b717a087f7e8e84cd0206c7f3d6163ed0affd7bb8a5271feaa66f004f3c806c76adbd20f93c05d9658e4753ed448237ebd861c92bf43bfec74492'
        'f2bead2e4ac9e490c84264bd6fffc92a4dff1ca924ff0ba6b9c3ab274ef04a9b9a8e99802000dd42e55431d461a7abb1a6f85059747382a52f93af62da9220a3'
        '284a10c1b783cee30575f7f8ddb2045e79a1ca8404c59a3151d653060a42f4a889a85628b87452750dd2379c26bfd288c76360e2b9f6c2b0f9d6544c6b58426f'
        '08ec62c57063c9a5e84864b0e9f1993ffade88a8c2f33f087c3d7c72e23f38a9ae5cf27fa186afedebd4673ecf692f3bdb39d73ba743cac3672e5079e4940d58'
        'dc8af31bedbcec06bfbe8a7f1e922b4541d2bf86af3c297979a4893234e8e7fdb836d43601387c36bf36c6d2d3b88783082c1e15a735fee5b490388ee835bd94'
        '5ec5210c94c6bf45ccf0ccac1d598a98c7846417a2afb0e4be623b83b5e7ec359b709fc9226621024c990d7215f22fd07048e9fef9c7c9dcf10bf138790c7339'
        '16fff4ac827b0c114620fa1365579943268ae00950b4b00fc516c25121eb1543b98962f9e0a409f167d1af9a4b975685c1d41ca22939c2f04e0126c8ea565d4d'
        'f173959199276612037e6e7ba96dca3839fcce6ca1b021971e31b44887bb7e7b2af7c4b862b1f3b990faf6636c1ae7b51cb2254bd08794d46c06b522c8b6ced7'
        '412259704ffd4994f578e47c79f71fe9c8cb5a9eb5cec63193f033f9c5c9836267e1c38b8495d2152fcd8175a94e561a8c4e8242231282185de4d62cd4c8f5b1'
        '5d57f8aa1f3f250e4fea62f4330207792ad027f6427e4a5c05d9962b4e0c30e737e76177d6a947e237e0f3a9af00ca7db7cc1fc65534a4bc83e5e122de830cae'
        '361b58107b2488b03d6207b13b2958bc19aa1663abd517c184f03617d88214e12f162ee49ea703d902d55baf81b09fb17579e4cc1de8821758aa16814e73791f'
        'fd518f7a0908d5200c3ee69be1ca5156c06d23f5e37ef4f4a90dee96389dde805416d91db382cbee071bd7269792709a63406727eaaedc8a5b3a7300e7adbaad'
        'b59b40285fed78cb4589fb6a529b9431a7b590d34101dde647d2aae44b98461718aac80e089f0eea4f6822a79027a6a1442722d59ada60a87c0e8b95d6e53989'
        '16dd5aab146dc25fcabb91cf6264a117a98f0a1225816ecaf657cd87f0c9bf6c8bb91d219de139a6dcfbeb2d319d5e3f8452b60b740774ad7c9a7997e36039f7'
        'd978a5246d1940cc758dbc601c624e3e980dcb320c1ca09a36d96e63288acb5b3a24bc8e4f6de673d4253ef970dc7f8658398df9e61c8883afe64e2b5beded27'
        '58f340b3b70ff729de725b00e16510795ca3ae376e1f30ff0f18ec285cd4b4d2e7289bc3e268651936b0c0fadb1e6aecae5062c236378861e47e3ec3674385ef')

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
         '0001-BACKPORT-FROMLIST-drm-Makefile-Move-tiny-drivers-bef.patch'
         '0002-FROMLIST-drm-radeon-Call-mmiowb-at-the-end-of-radeon.patch'
         '0003-FROMLIST-LoongArch-Update-the-flush-cache-policy.patch'
         '0004-FROMLIST-USB-core-Enable-root_hub-s-remote-wakeup-fo.patch'
         '0005-FROMLIST-scsi-Bypass-certain-SCSI-commands-on-disks-.patch'
         '0006-FROMLIST-PCI-Prevent-LS7A-Bus-Master-clearing-on-kex.patch'
         '0007-FROMLIST-RFC-drm-amdkfd-disable-HSA_AMD_SVM-on-Loong.patch'
         '0008-BACKPORT-FROMLIST-drm-ttm-save-the-device-s-DMA-cohe.patch'
         '0009-BACKPORT-FROMLIST-drm-ttm-downgrade-cached-to-write_.patch'
         '0010-BACKPORT-FROMLIST-rust-export-BINDGEN_TARGET-from-a-.patch'
         '0011-FROMLIST-rust-generate-a-fatal-error-if-BINDGEN_TARG.patch'
         '0012-FROMLIST-rust-add-a-Kconfig-function-to-test-for-sup.patch'
         '0013-BACKPORT-FROMLIST-ACPI-PCI-check-if-the-root-io-spac.patch'
         '0014-FROMLIST-kbuild-install-extmod-build-do-not-exclude-.patch'
         '0015-BACKPORT-FROMLIST-LoongArch-detect-and-disable-sc.q-.patch'
         '0016-FROMLIST-i2c-ls2x-Add-clocks-property-parsing-and-ad.patch'
         '0017-FROMLIST-iwlwifi-add-new-pci-id-for-6235.patch'
         '0018-FROMLIST-gpio-loongson-64bit-Add-back-the-support-fo.patch'
         '0019-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
         '0020-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
         '0021-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
         '0022-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch'
         '0023-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch'
         '0024-AOSCOS-loongarch-re-introduce-add_numamem_region-ini.patch'
         '0025-AOSCOS-loongarch-basic-boot-support-for-legacy-firmw.patch'
         '0026-AOSCOS-loongarch-parse-BPI-data-and-add-memory-mappi.patch'
         '0027-AOSCOS-loongarch-add-MADT-ACPI-table-conversion.patch'
         '0028-AOSCOS-loongarch-correct-missing-offset-of-PCI-root-.patch'
         '0029-AOSCOS-loongarch-fix-missing-dependency-info-in-DSDT.patch'
         '0030-AOSCOS-loongarch-fix-DMA-address-offset.patch'
         '0031-AOSCOS-loongarch-fix-HT_RX_INT_TRANS-register.patch'
         '0032-AOSCOS-arch-loongarch-add-la_ow_syscall-as-in-tree-m.patch'
         '0033-AOSCOS-la_ow_syscall-add-kconfig-for-module.patch'
         '0034-AOSCOS-Revert-rcu-Fix-rcu_barrier-VS-post-CPUHP_TEAR.patch'
         '0035-AOSCOS-drm-amdgpu-disable-ABM-Adaptive-Backlight-Man.patch'
         '0036-AOSCOS-kvm-disable-enable_virt_at_load-by-default.patch'
         '0037-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
         '0038-AOSCOS-USB-core-only-enable-root_hub-wakeup-on-MACH_.patch'
         '0039-AOSCOS-ACPI-scan-Add-pwm_lookup_entry-for-PWM3-on-LS.patch'
         '0040-AOSCOS-drm-ttm-fix-incorrect-caching-type-caused-by-.patch'
         '0041-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
         '0042-CSMANTLE-Revert-FROMLIST-rust-generate-a-fatal-error.patch'
         '0043-FROMLIST-cpufreq-loongson3-Make-this-driver-depend-o.patch'
         '0044-FROMLIST-cpufreq-loongson3-Adjust-the-width-of-id-an.patch'
         '0045-FROMLIST-cpufreq-loongson3-Replace-per-package-mutex.patch'
         '0046-FROMLIST-cpufreq-loongson3-Use-global-physical-CPU-I.patch'
         '0047-FROMLIST-cpufreq-loongson3-Replace-IOCSR-read-write-.patch'
         '0048-FROMLIST-LoongArch-expose-LAMCAS-existence-via-cpuin.patch'
         '0049-BORE-linux7.2-rc1-bore-6.8.0.patch'
         '0050-CSMANTLE-LoongArch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
)
# vim:set ts=8 sts=2 sw=2 et:
