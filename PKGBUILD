# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.1.7.arch1
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
b2sums=('1a1884d4ac6e5b2a49b5f4835635c47b33552568a01b2cd65186a252da00e0578af2830c60a88208ec0834f718779815663dd7be148903b58f72e22ac8673e94'
        'SKIP'
        'f3c197f565e52a2b692798c0afcc2e783e504fe8fe34303c39ed50c374b81d98f8d4b38ef8e99cc37cd7ad9e7fa4d122a961b16b8cc20f80f8af6f59b3123aea'
        'SKIP'
        '512543621b3244ee00fbc3a6071a784ed63a269c8c8dd25da0da0a90269ba8539b558b555aa63bad9bf52d96148e3184ad6bba0b62edf9a5ba3111643241a96f'
        '652069e50060a3d84530f004f7064d98d6ac9bb02e690a3510d092d0df17598c9b3d564ae07fdb0dbbecc68d2d12d58c4c78c02cc08fbcbb8c01ba6e6256d922'
        '9682585b979585cd1e2b2fd76879954d0c101c2e27d989da02225881d1b5739c01bc8e8643d9e7fbef257834b6a08d8db247b15727f98ef9eac4c533a027eb26'
        '4f255450641ead6dfada6f5e32823ba02fb383d309122825cca941f33ccaed174eec65e86af75fad22082fd7bb2df5a3241e12589e87646f61202ef62b0dc690'
        'a6a8783876c9a390e6856b77133afec13fa05ccbd2e6dc29c653383650c03f41120ac6ed4a367aecd5ad902029d257ec1608fd8fe5e251a342d270a5862b91a0'
        'e7dd8e3fca168b4e460264b86af185da66bb20c04b11c86608322d9b29893c35adb885cc8335fa5dc0c5d37b000fdac8db5161b602ad8560e3f8fa9227a7e30d'
        '12233bb8446199befd8f95930202acd8c73b87cee8da5ea2b001dc3f7777ff03ea0fa62b883518bfc5d4864aa2cae5e00be267d92ded725cd4664df6e5d21074'
        '083934cafa01764529ac634948c5980eae1685a99669df9619b179027cf9851e48467170769cda134913ee9ae84e475f0dec9b8408d3fd11b119621280ce9216'
        '9c29aa64f190ed77491dda634bc559e740e5c2acfa9e5db980b625cfd6aae0999a3c6ec372e86c8cf2974720cfde76b6c51a02eabfd6a4dc0685736392752189'
        '091ee8bedd5dcfd4991e9603118f9ff5d49d789609ea9641e451893f9656359b6a0d6f663b4634f91e152a8eb57f639f77042aa158dd23e2f989527438584532'
        'f736417f0b786d7f36a3927c8c5c910a26fc66156f5ee1f3344b886d4c7b8ab22380c144571e14e47cdaa8dc7f836a8f901bebf1f8682e85ac515946e6f252c4'
        '85a79f9cfbd8ebf7f4ba061bd6f1b55414233e5c8111f719bf0da80c96788cd09441c718ab78d2e2f62dd2366a494262e4cb63e5d4cd3b26acc6eb894c5675a6'
        '4c1407392b1d1822030161e65eb8c8bcc583f5006a42d164133a28fa43453ae88574733b316e35f2b1fa84132e72480b982e63e1b48b282fddccaaae1cd19944'
        '691ddb3f183830f44bd0835673e71aacbfc16bd21e51a13cbe18a0e7b26e95b72867f5c982d336cc8f26c64115d3dc44f8ef168b658dc1d6cf33e5bf5189dc6e'
        'c34e416549bda383629723bca88450041f99fc8649d052cc5a25d75997adae55c48b3bbd8541bc1a082bacd08db904043e0974ce94aa442f87929546f06d3746'
        'f97cf114bb8b5b368a107decd7b4b98589dca80c711b15a00e856cd153ff4a27f1a42ee23234ad08935bdc87b55aa92471faee0bd6d909e1ad4d4e452eebb434'
        'fffd0debdcedd88a370f290902baaa09e7c0cfc0d00a4b1edce3dd14489f4b3a3e5b682863653e7bac61550dd90f51e8ae90a3cd565ceb4e4f9da6ff3dc1f44c'
        '69123ab874fee42af750ecb0db75ef25b2f592d7704bf21ae7e09cea58cb0e745a06b5d574f5d8c7995503bbf1139938b791f426f0ac5588fa68b99e2e5448a1'
        '25e802364fc782f6eedc8533d7d4c39e438d356353b7fc7fb21ff4e6bff91481bd970a4f4c1b7327aca8a6da41f041487cbdef60b41a4dc1e63e5f04e7791bb6'
        '5d4723683fe3b79162325db6f8796778e40c24664f0422b274779d18b404448deaecc5c74d1dcdf6da561e71dd1910ecaf44cd8065ef6e6d9b668aa03eeed2e7'
        'fb4cf54af6625a4e1cd454f22f98ed79df97a57e416d874c340a04525e078f53e4c6e2ebfc9f53a2e9735f4f539716606a7acee3ed14979efaf8718e4c89550d'
        'cda61b6bdf9692b799b13e1fe66afd335f78ec7bc92f06557b5c626fb992e63cf8409269d72f82d0c1cd50326b50d9027c60fd0f851cbc1467a7aed53fe7a6b8'
        '19d50093c6f3d1aec2dec867a0ce2e9684bc8e2c6ee1b59f8b0cd01543897448883340b7b138ac1b17eda60bd0368f86da3448406b619f4e58d493db75d362b8'
        'efee1b6adced362aaa33582d9e0171bc65356f92f1e80862b2e65eaea516cccba576ae1a7e3389bb8d6505a810034eed6c0bbe9db785f80e00871906864077cf'
        'ea4d364e0470323b3827e247b2d424f3dbd2a9673f2851d38eaa5e89044536a2f040a475c4ef32c175a92edbf7d16fcfcf95511aa5a8ed63f39acc9a80ec4589'
        '62cfc2e459120fb3bf148befdc84cb617398bb165c4b79507f2c5aa7082fbed3fd40b473be0854b92657ca5a41c00f2a2dc676eccd5e957150bf356911cca237'
        '2c6bbc0b28e54669ea529cb604f8b5191d2c66cb9592d954fdb4a67b28eb3aab0073c6efd7cbb3381a6480ca839138914aea065943b3af0ff1e7978891ceab33'
        'e8d7b53524ec52b92c0fa64a8dbdff2d8afd5af27b5ea0ba48218e5edf56a134c702f7f8497da3956723433b148c5ec0c36c89ae6bcaa0efef5a4eee8f1eee39'
        '02f58f8d7390961d0e6081407f6537b327458253855c2d6cbcee5b3beb273c7bdde3b1652aefefb99c5c38011184f79087db4c562fcf96ef7b55390f007b64ef'
        'a6b89fcd7e4923dbbededc87cbceed32969f95c644cdc104b94df046c2f178a578411c4a6950b10b907f34a8cd09373c47fe70ef69fd83370bcf7b5e00f890e5'
        'fa9b34527e309fdaf5902008e9d566ab5be12158775d6f57ce900fc34728b7b34e2bd3565a255aed18ba1b935e48f6229c361ae05337b416dc979ca204bdd6d3'
        '672b5edcfdf08159fc7ab2cbddef847eeaa52025e02ec7092d883d3cae613e66c76c55d91c1a048cf65655293126ddc312f406f7a00559f56956b287085747db'
        'f359d00a8f0e8d8c587bdf7561a3d0aa065c77ab6b18a58507778799196e7dd80940d58db0e34f522106602a83cb9f644d0b4df78d17a196ac3f1e7e336affa8'
        '92d12b0031cd1b2e8d311c075399682a8b0b936a45937870e3927df489be5d69acd4381b42ab6b06bb8ce440f6183d6f01ec44afa764e14f8f16ebccbb4c9c04'
        'f367e1396ee745e66cba71d854a9d808d608b5bf3d0eedb2388904fa14042c7dd1b5d33c28e3722657b858a66a99329896e4ce629f6972ee91b885b2f8e9f876'
        'dc0b14bec7676381b381285744868222b2a043d199fa67b18f2ac9184193b769c07232eade1e5ce44d963e8b01412af55d196789bf03e4c0487b36e228bde60b'
        'caf35be053c6b032a38e3c185db8f2e7416c31de8897479811d3a9a8d8c39519579764453e0ce112f48d66471125b38c32c1996767cb41b96d15d5f72e6ca8f8'
        'e014f369cd4f43e4f09cce8721c5a7ea7b4095cd84fb570270023650091e2dc89dba75474f68ca523b2bf07ad1623c440781e37f6005422dac79e1462e2c0d48'
        '973b0cbdc08774463053e0916c71b293abe296ddcd4965027bace88da8199dfcb5ef299844a0ee4a9df8df22e6ba112147ec78dbcc98bfa5bc9f045e2c13c57f'
        '01ead40f799e1cfc55ebb936e01c26d80cbb06af852a60558aab900d2a734d2b68cc79e293cafee0030422350edf6efce7871b7277c5826951bcb3afe3a72d75'
        '2c65713a8859546f05013969f9ebc9bc03895f2df3d494c79a8746064682d1ba1b96515671e1a5b3969e6615934b8ab6ac127457b0a58b44cdcdbe9b4f1a5814'
        'f395075395919d24f496aa0cbb5be3c3e9f4d7aa7c72efadb711ef1de15df40bab65569cd395b6d64221dc71136ce25395e9c9a97bc9a1bd1ec2540b6968d93a'
        '02ef3c92f1d222443dbb5c2801270cde7ec7076e8fd8f5434dbc761e512366327db3de7bde8f06024d3d822d8febdf54e26da12f0a484ca60624f64b7fb51761'
        'c9d9de59c09a3cb4a14058c45b7ec6b8156ecb6d94c0daeeabd3c8529117a6c42a4fe335c0a333f471fea7eed6f8f4e4ca7ab00271e1c266502c893678ecda1b'
        '28d8969b1f263a1ce9f73e4dabc3a1f9290b380c3f4b60011c28738ab12a550264bd3beeb36944df23842f0c41424b2b5c195b49bd376a4ee7faa745ce6eb945'
        'aa218f46bc888584d0a89d3ba200585440b890cd3561aa2548f1a73006e22f5de646f7de02635f38d32f625365c7b4a6a0e924c945592049c59c075ce9169dd3'
        '439fc86bc0a5f8cc88538578f2f6e3bfd8b5f26518f256f54ed7cbcfff00fc6eea389ee6306d27ee43004662f163114b444b7c6e28f341e757b3d6462376b1fd'
        '80158fe7ae65c3bbd5b217d364ef13afe785c40363c1390848937a9c768b7331255ca56ad69527e3735417d6ed4741ede9b7d20c43be17a7f5c85e54fca41c2f'
        'a90da23f47786bd62776d124e8d7ee9b2944b5c269615ff1234d858d7c8c240e297a13b02083487d7445dba75625d2ed0f0ad690d2e02d0eeb7a1b0f12c67b3f'
        '033e6ebbf501dbaf6888e070d15b68da7e811ef5c4c60b3c48fd3e341e6ecb75eef55b9ac9694b3a10cc66f3b853e46f966c374224c43a344330fcfac11dde33')

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
         '0018-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
         '0019-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
         '0020-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
         '0021-LOONGSON-cpufreq-loongson3-SMC-boost-test.patch'
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
         '0035-AOSCOS-drm-loongson-add-ls7a1000_support-module-para.patch'
         '0036-AOSCOS-drm-amdgpu-disable-ABM-Adaptive-Backlight-Man.patch'
         '0037-AOSCOS-kvm-disable-enable_virt_at_load-by-default.patch'
         '0038-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
         '0039-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
         '0040-AOSCOS-USB-core-only-enable-root_hub-wakeup-on-MACH_.patch'
         '0041-FROMLIST-gpio-loongson-64bit-Add-back-the-support-fo.patch'
         '0042-AOSCOS-ACPI-scan-Add-pwm_lookup_entry-for-PWM3-on-LS.patch'
         '0043-CSMANTLE-Revert-FROMLIST-rust-generate-a-fatal-error.patch'
         '0044-AOSCOS-drm-ttm-fix-incorrect-caching-type-caused-by-.patch'
         '0045-BORE-linux7.1-rc1-bore-6.6.3.patch'
         '0046-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
)
# vim:set ts=8 sts=2 sw=2 et:
