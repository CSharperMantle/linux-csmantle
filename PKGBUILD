# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.1.9.arch1
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
b2sums=('873b4d4426295e291118481d911dc2bc67588bb9b1025c19faf7c2a3971cad439efce1c4f244a40a2983d9e7fe405adfb880c0df92ff2e616d0880178129a551'
        'SKIP'
        '6e7b73dbbdb66a414c634df2e7b2d248aa6071f04c4f2fe52346441ab490192894ee903ba72b8e47ab25c511e4dac14cf824f175f183687b1fd61bd087209afb'
        'SKIP'
        '512543621b3244ee00fbc3a6071a784ed63a269c8c8dd25da0da0a90269ba8539b558b555aa63bad9bf52d96148e3184ad6bba0b62edf9a5ba3111643241a96f'
        '652069e50060a3d84530f004f7064d98d6ac9bb02e690a3510d092d0df17598c9b3d564ae07fdb0dbbecc68d2d12d58c4c78c02cc08fbcbb8c01ba6e6256d922'
        '9682585b979585cd1e2b2fd76879954d0c101c2e27d989da02225881d1b5739c01bc8e8643d9e7fbef257834b6a08d8db247b15727f98ef9eac4c533a027eb26'
        '4f255450641ead6dfada6f5e32823ba02fb383d309122825cca941f33ccaed174eec65e86af75fad22082fd7bb2df5a3241e12589e87646f61202ef62b0dc690'
        'd158219c3f5ac0dd0efd5c583fe9a90bce5eed7948b6809a503c7a3cd9605ae39086eca8c2dfae9615d0a037693d4a78793d320e8bafca25a078a242023b12a9'
        '7407206a309c719ab9741fddb32c02a4baafea0a8523cc453e52cff92df676a323a270ed7d66a81b57f3ea4171bad62944427de990401f4127664476f61694ee'
        '31027932d2ac5cc9c702277d5c298feeb390ea90cad85a46fc5f30387e150958bf5b529ee96ecd0935faa163c78ab1289024982b2615552ea968080e3c9eb2a0'
        '614adc407de09b452bd6ee780146cafe23833345a17a895a9577414a902551af7fd96fed39d0571ae938d8bc01b3c3b3969307117c19faeb6b81e651b407d54c'
        '628fc87aea95844c00ce2efe6378fc9ee730ce032bb93ca99b297da94e5d855758867bc9fd1b19f23ce64fed83eb1f523420dadc4692ace5d36c4b2ad0e25065'
        'f7bd0cbb01ba8d35af679c0b17d724560dc09e45c1101aa6446703c198de5713bfd7499994863f2d8e767625c12760d4b8018c26bff36f17012001c078a50af4'
        '95a8cb75c8300d53bb81431774ceb41fd3543cdf325983366b68accc43d0da345f3576c1bc6b10ad69e96058658751ce6541a4ab28215b65c1cbe137b6fd3297'
        '1994606a63a40853b1cf3e2a9debc90390aeed4e0df22ef353ba066f153fc914f80e3159853219176f6eaba7900bcb198b07b45cc4e25dac9058feec22f85686'
        '95d37d649bad13039a8c142e3fe9acc74e7d5320592d1cb61f0d85b56b37af95e919684e48a99f762b3ac211454ef8c502bc5545c17e21e1dc21a0be12b75ba7'
        '08d6290bb7ee5fde5744642fb774420c37052f8d3a86594abcf15d5f4199444f0c9d2e9902f73d8b59cc5be2267f0ba8d3252795b52b674a30c03254b6881ef9'
        '88fe5342c935879b893e36a762ae6737ca757a273f155a99d13eb6b099a26d54d199cb87edcacbe478f6c61878e74680055dd03ef1e26a5f16d67e649d78e195'
        '2f3ebdc5067723aff434a488969470ba2488bbb3f5f8e57fd1be2cb6b4457f643f9825761bb0620c1732dd3459d2edc49a21644451d031d9c4564784ad741ca4'
        '9bd9022092ef5a78f03186e4c632b42cbae6a9eeb4b36784010cc30af9c28e5703e26a43d403afa9f404df1054a8dc0e60a4c78d5f991428d1ec9efa5f9c69d5'
        '4f442f34d3350820b19184772be693023dd3b98db4cb9fdb8d2ad8fb8d9d888690281adadc8936f0f5e6c35d532bc6938628656c480013d76f46cc03b4c5e2db'
        'cae3374f4ebaac7a51bfd4ff3af01f78e4c3c269565e48cf01feba670207897095495ef7dbec2d1528d22aaad572b098187298ad0f7565f36bfc8248e2747451'
        'ac39238f6c654914df11a2feadf7ebd05361139e420c28e5ba85b45f1f37345c745ecfb6eb641acb4c10a2927740f24450df7df7aa0545b630ee823974b0a0ed'
        'f45fa91f4d597902071c7f1591db593dbe6f561809261e649d3e2c4da955eabf1a07bc481334407e0efb9f4bc51d55ca037a8a66c4d1bd1b6e2fcfb54c78e4ca'
        '5de9529b659da59a18bad4cef5868097c0418116d2825c32a8caec59d8c089a7f76fe13d3e5bd9dddd5ebf1671e36ab75da5025681b67a4497675504e2a050af'
        '14ca01c1907a7ece8598fad758e4ab101269b4c9c68b4733c77d4fb6b350b224260b78d03c6bb565d0cf19a2f882fc6fe76b78913e153939ac2e18cf69ec60d3'
        'e0f6f66915889aac4eb8b7c5bb273df46acff74dab4e5057829bd58befd73f369717ed1ceddda4614894a9bd85103dfd56a743699afe99473421abaf6bd82607'
        '9aa3f01b3d79bd918b6f1e22a703694bf66b15d0b3f6a4de375893041c952d9d93315aa570a7fe0c82ab90415b3c38c2cb977810e93cc9d1d17ddaa8a8095b42'
        'f81ba32d53e3368855b5e17d355de3d9d54d179acd09e61d8ede87118b8b8a687cc1b42e749be3db0a6495099e4f9f670f944b4ac8c23dd9c2a55302d5438fe2'
        '5e4ecf87f83f451337a98ed70546da9e55b65f6926e856c121929f75e6df2d1965a53cfac895d2139551c04653e2e082c470f34963bb23b86f92a2d0d8fd3c52'
        '9c43a57d93863fe3904d3e6673ba730b271e3ae442fb3671152f591239d2b847106777e12ec9441af632d7b14ae6cdb1773645e136fdc003766198f9481c3a4e'
        '3a80c796bdd011fee9914dac971fa04574da805efa1a37ebdcc0816ac3281e3bbe2ded95359bacc01919d1894d5c44c134ca9e8ec0678188c52a1b33e874c1ed'
        '566c030c3dda71d46ce82a630091f5ab42f9ab2234638323afa0aff51e1bb762db59678cf9d0b12e90a60b9f313e626e26cab4e49d0ae05d5624a7388facbe26'
        '6e610dc88cd9c2acd2c747f5028257f9c9032141e2d80a9329fd42dc671e7d77d3fade3462e06d68224988a3fd846e920ea5095593c67261a8e66b6ad07f38cd'
        '7fe2e7cd09e1f37a2fc2be4e2b78de2657b615d85e0c9628dfb1922c8b64a75ab916d6be7932045fa87202f182e2db3b4b13fa58abdf993289a7823c91436ff4'
        '5bc752dbac63a3ae5a2ce8d20ed2bd61331e5ae027455e56a46a090b0a22a5894d1e583f41cec9ebd67f5965d7e0f6e3ee74983d239cbe307d987bf502ca9020'
        '9325cdd7af92839276856a684ae380b96498c1122e013de5b2161050679dd96ff4296df48c2d5554639eb0dab54e9bc1dbd891c51564346a3a2d5c5fe008e10c'
        'f2f2bc78e1471147a2d8d03296ef3652e541c01e7a7529bca62c677826fd0f9b05e49071c51f2fb1cd5d58bfcc0b3a0e55c9835b0e52dd549dbf51152e4f2af2'
        'bb1f10d76cc27aaa6cc9f4a62b6d3b9f34d8c04a6f1126fe2a0c6f768817ac7a9dbd5c63ef5afa628ec7ac1ea097543a19f8c7ebbbca7c70ec08c3059c693cc0'
        '8a2c035ba61751bee42ecac2ba650542fcb2cb8c4d1f0cc1e6e3d510c1185e93a29192599b57ce101816dd4ad7c1ef6575be8b4f28fc986331d27fc8e45ee671'
        '027e2e4beb9aef26ba4393ee97ef8c6356d31e4e6db50fbaa45aec3aedb00188e3e561bf70877d73b0ccde88c598b70b106fba28152de1d3aa50a7c2c13a8c86'
        'e855f850ffcb138bda15e0dba69b68a580cf48a76b44f5469dfd2f596f34f8467b58233ca7bc76dc97f7752367664e8101d9391c792acb5ecbf143f16c63c8ee'
        'a16450ee1736a4812a8d0d5dea828c9cca1167d7d6f5ecb8c5a1b33d45d79fd57a0cb6282f5e62517a72fa5e046a47d76f54effbb9fabe0e3f14cb93e2222329'
        '5fd5f1998cd77bd3001d3fecb4cc7e5c63ca5e8fb8cc0cdf3a93e3fb7c82881e433a7615d814e3ed3cda3c6fbd3cfa2b3fc07d8d44dc2713558a1b9b904082ed'
        '838e60e2ce10646597d45bb7c291c5af80e55d21eeb77d74a59678f0d4f8222c874f4b7c44b1d8b0cbdc82d5461456b347d938896666729f72f3cc35481b1a4d'
        'fad0086b258f3d4c628853d701e3ee8f979030b1dac52ace38266f8fa956e9a3b6ea17602889d0a9a8f6d9446b0e09955a3ca85162c3d72a00614d3d401f1927'
        '10b53f42e8e1429c0f3f26102a64f70b651396c158ef4d0f027aebe83f95a6a173e688094756ed7c511a05a2dca853fde89be4b9fbaf20a4b1705ea51becc9cf'
        'fe4a02c6b9a28bf9b6715a679287fcec3a7e52f940e0419b9f1bf72b85b9e7054f022c0a5310978713497290bbe46cd922515e4f99ceb1959caa18ce38daebe4'
        'ed3e71d30f3f66d00cc03e81fb2fe7767be117a1ece6ccb55a79f41b49a0995724c51470487a3ee5c1d7b98973b4f5c6fc1a4160377804c49b98a4e2b68c62ef'
        '28b397d6ebcbf2677cb47115f83ccd1b210f35782895e09e2921858f84bc0fbc8fcb411a48bacda9b4da964a2fc51937a24a2364503f4ce793a79210685ff338'
        'ba631e2970344f7e2d03ad229084ba422988e663774ca033ac39db70fa511d77cabc5afad5b9460ade3d77732869bd6b1cf059ab29d69f047f9d3a50f1527878'
        '5023e3c26fb01ae0b54e1fa220d207d06a944bac93f782de444a0c2ea1331d986a7caa8f01397fea9471a3dc4aa21aed08c6d69f8a977e23540f40a6c3357cd9'
        '46cc968d0087caf88f3eea8229879f6355cabddc7ed4dc98b2cbf9f55752f8eb34549f00ca852c673660651ce3c6477d0be3d6de5d601ecbebf7b0466fad2570'
        'f39f4e0e6fc53e609b508ec9457b2aeaa9fcca809c3a9465036311a2a734b2d7f9eb2cda7991afe5e329c5ced8403eed792b5b3968251ee38c6ebc5a6a35bb74'
        'c5c198c40faff782be377131288afcf0200bb0010fd1f38da6b51aeb37e7bd62ae8aef6fc34b70f1a239705d4939def1667aa0a14855444b1e8a11378ea2a253'
        'cf70b95a3cd482b223245fa40e2f912e89752b884830e857e3d12c5a900facf95c65714e6a2e06e88e19d9656ffc9c533424521314df6833190ec69b4530bb45'
        '9fe8b2e036e7aa6e1b6b44c8666b3e89b47fc54ad1f9e0ca9c354a7263869dd104d0acab51bca1733165e0e9b60bbeefc876771cc4ae353b8ac7fb46d73e1cc9')

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
         '0018-FROMLIST-cpufreq-loongson3-Make-this-drvier-depend-o.patch'
         '0019-FROMLIST-cpufreq-loongson3-Adjust-the-width-of-id-an.patch'
         '0020-FROMLIST-cpufreq-loongson3-Replace-per-package-mutex.patch'
         '0021-FROMLIST-cpufreq-loongson3-Use-global-physical-CPU-I.patch'
         '0022-FROMLIST-cpufreq-loongson3-Replace-IOCSR-read-write-.patch'
         '0023-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
         '0024-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
         '0025-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
         '0026-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch'
         '0027-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch'
         '0028-AOSCOS-loongarch-re-introduce-add_numamem_region-ini.patch'
         '0029-AOSCOS-loongarch-basic-boot-support-for-legacy-firmw.patch'
         '0030-AOSCOS-loongarch-parse-BPI-data-and-add-memory-mappi.patch'
         '0031-AOSCOS-loongarch-add-MADT-ACPI-table-conversion.patch'
         '0032-AOSCOS-loongarch-correct-missing-offset-of-PCI-root-.patch'
         '0033-AOSCOS-loongarch-fix-missing-dependency-info-in-DSDT.patch'
         '0034-AOSCOS-loongarch-fix-DMA-address-offset.patch'
         '0035-AOSCOS-loongarch-fix-HT_RX_INT_TRANS-register.patch'
         '0036-AOSCOS-arch-loongarch-add-la_ow_syscall-as-in-tree-m.patch'
         '0037-AOSCOS-la_ow_syscall-add-kconfig-for-module.patch'
         '0038-AOSCOS-Revert-rcu-Fix-rcu_barrier-VS-post-CPUHP_TEAR.patch'
         '0039-AOSCOS-drm-loongson-add-ls7a1000_support-module-para.patch'
         '0040-AOSCOS-drm-amdgpu-disable-ABM-Adaptive-Backlight-Man.patch'
         '0041-AOSCOS-kvm-disable-enable_virt_at_load-by-default.patch'
         '0042-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
         '0043-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
         '0044-AOSCOS-USB-core-only-enable-root_hub-wakeup-on-MACH_.patch'
         '0045-FROMLIST-gpio-loongson-64bit-Add-back-the-support-fo.patch'
         '0046-AOSCOS-ACPI-scan-Add-pwm_lookup_entry-for-PWM3-on-LS.patch'
         '0047-CSMANTLE-Revert-FROMLIST-rust-generate-a-fatal-error.patch'
         '0048-AOSCOS-drm-ttm-fix-incorrect-caching-type-caused-by-.patch'
         '0049-BORE-linux7.1-rc1-bore-6.6.3.patch'
         '0050-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
)
# vim:set ts=8 sts=2 sw=2 et:
