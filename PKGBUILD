# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.1.10.arch1
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
b2sums=('fd433e456a207ba881c085d9743dcee706cadc9eed577bb5893419569cc10e494607116fd1bede2bda5c35d9ef76d32e3160473d5d9e7ea378de248a296914dd'
        'SKIP'
        '93e99c1e404d59ddf801d416facfb0f471b7284c55e362d481cb0df9d360bf10b214b4b609c683b2f0832efb6140c8c3849a37b36a8904ce452e96687bd75c6f'
        'SKIP'
        '512543621b3244ee00fbc3a6071a784ed63a269c8c8dd25da0da0a90269ba8539b558b555aa63bad9bf52d96148e3184ad6bba0b62edf9a5ba3111643241a96f'
        '652069e50060a3d84530f004f7064d98d6ac9bb02e690a3510d092d0df17598c9b3d564ae07fdb0dbbecc68d2d12d58c4c78c02cc08fbcbb8c01ba6e6256d922'
        '9682585b979585cd1e2b2fd76879954d0c101c2e27d989da02225881d1b5739c01bc8e8643d9e7fbef257834b6a08d8db247b15727f98ef9eac4c533a027eb26'
        '4f255450641ead6dfada6f5e32823ba02fb383d309122825cca941f33ccaed174eec65e86af75fad22082fd7bb2df5a3241e12589e87646f61202ef62b0dc690'
        '6a4a8523c71a716704cf96865feee7e6fbb7a60faff3735ed65043424ccb8bcd38707761219e913d8df546f31aaaa358f5b67c94a408f165bf1aafdda45116c2'
        'c0d732100e3e9faef9c236533453d6ab2e9336a72c008252240d05cbc5f84e1e0e801e6a343325be4455bb76a47653261b99d0e98c20a3a8d40dccb187c7a06e'
        '540eb0fb157cbb7cf673c7404a7a6cbe5821d3c574362e36608c3b689e7ada9d45dbd9a4203df08d01e3c49c583c9d3fb83ed2b954a79347d903b9a511c0a208'
        'f6f6dd6b918d352a7e3fe9a5036c89807b1b82f4d54bc4aa3cfbd0c13293ecefee83bfdd6322f32165eb69e3db580d24f34be9a2209e3541a38e293b4e5a1287'
        '544f503b47684a3a936e8f4eca6aa1122583c80fc92e0c42bc76944ed11ea6fa1f1d91c5c97a54ae460227efc05c143539f868c4c79bfec307b3aee9e9d92233'
        '0f2b41e5dd48587351b3d4a6e533c1b66c79aec28cde48fe394f84255d230b6cced0cd665ba8cfeeb7ce10ebb809a32f597979a109484ccf11f8414bed0f3e20'
        '80280fba49fa46e4ba730b825110300644b3cecd21fbc021f67450975bab7bf619b46dfa9be85229f8235062798b2d04f32938338633bc32bdab5610662ee0c6'
        '54b6fdeae1e6c517d1458abdb3de76143a4972f9021025310a44032e2b49f13c1190b974534236da2730f9c3baa87901c5fa5c9f5961c635bf1050edfd62fbb9'
        '63ee7f5efa4581171d9c460371826c7010baffc57239031733f993d6a0a2e542d670580a0b54ee24ad81efdabde68422d0c214d9f7d447a150c30db3319cc4c4'
        'a752f78c50e0a97f1fce916169ee77715c28d5bf348b7624d386e30ea4b4489955f6dc27f3e52fbb132a2355d477b2208a4d756ce61ca30a9cc91da17a60c1c8'
        'af45df56ed016976b0fa6f96a133c3b8f4e8d8cf8c1a0398905e484979726fe6e9b761b0b62676ccc5f5bed46ed5af1688ecd160e56e82322f68b790b82f69ea'
        'b51cf236993cd239baf2e71149a50f36559b4e0f6139c8d9e1e7f5745f0f49d3c3f36b230126f991ee026f2ec68a2159d105996aad5af32e440756e35c2b9f3f'
        '0f6cac0d85c4444ed6796228d65d4c5ba038d452e9a52c3804b6a49b92089d47b4437848c082c95148d31fda4d860df5a9c79e43c9539a1ded302d48357934f7'
        'a1c3c93f204fe62522c94361631f5e05e8b92d76fded42e6e52f45eaf4b7fe91a152f1362a24be6f14955edbda5720fcd36a4cffd27880a1e2be03663135c3f4'
        '163b8be064ec5e50d8ec91fd4e4cdf1ac05624170f192fbd513eade6d09ded10deacdf810d9f151f5d51d7e6e3ca6901397d83f8baca7f412ad794a9286cc3a0'
        '2c1eed0976c58a79bd7a5a1f4cb5759941f849d9077f0c199e7b89fa342aeb865e2549bed96671ebd12c24a95c12675f02efc708a73c7a60a16a18f57d6fb80e'
        '23e51c062ca97440e134400ba411ba6dd5f9a85cac4beed37b149515f52bf1f4a6ba0cca8d6f992e5215fb86c8ad99b4f597ed0141d15cabb06be9cc251a31a5'
        'dacc14d5388c034634aba1ce2c947dfe2cef51f6e048540c6eb361724421835f4fc4278d23cc8e2a5971e45276bb7073992dcffd8f6248149dfb1293df33d81f'
        '04d83cc3eeda57d2f47467ba2058695fd943fe7c56535a17df474fd83eadd9e926a2670955dc233cdbe2377dd3f012f3c49d31cf98bea0cc28e0d310a896eb54'
        'f9047dabac0f386877eb448cdd255a987ed74e30e7945e1fda5e882a39f42e1be472582c0cdf31713695ca22576a406f78986bc505eb9c4d794b1f35ff7c8091'
        '669ea32b25567ad6f792a12a76e8f9583ce61ee7ebc629fe8f150db53622022fb80e19b19271e86704f65ab72993e4fdb2100a03f6f8ef35e03ab0ccf6b03446'
        'ca3cbc07b6aabce2bc92ba06858112fb4ed21f7fd547f10f2a29aef4541d0cf3de7d84668e5c8d15c8999fb593418507c9be990e4831b33b8cd9451a53ba8fb1'
        '6abbbb7d885ac5b50c72eb950877b01031df7a1575be168923bc1312c40fc5ebe9b6cba281f295f280c117fbdd0caee385bf25762b96130cc7a0d9da18cbe0c0'
        '27f770408469610f7a6aa59ed6e22d5fa8e5e45dee2b7402f48bb2985b1aa19489ab6b195faacfd6319e4a5e97c71f0616e1ba0250440cd23374494343087815'
        'f387925abaff1222bebf02e2ec2ad0be78d5573d2a0a924254f8037496ebb73248edd1763833d6c7c1710d8ae2527733eaee43bfc71fe5989d2bdf9acda914d4'
        'b9cd7eb4e68001eb20bc449ab211145bc3e5be74a8bee280f4337e9393851d8983bb0f3b407f993d7cff9ccb9455911eccf9ce97962a4685014ebfb197d9e483'
        '8eb88ddb9696de055981bbfb83ec846cc03aa9d06a4820242ff3a7c51cabfee85512720a749779ad39951790a30135485466662297ad91f3c19bec56065efec5'
        '49fb5c3d9e5f57c565f59b1914c803fae3b3470052f9ff5145c78b60e25d5f4611aa3556a871ec09fbb7fecfa333898a56f787aca17adc27948cd8af1aec75d3'
        'e29c200dd183054e297beb582403c65c669876a9ee360c0f5f6fe7e9d096762161d9c57cb7c66c541c6f85b54ac17e30e6ad7b0830fadab1ae3ea8c322a54132'
        '6725f6f14b34aca0df6026747710d62104c36bcd2bd76ba5a2b67dc405dc7149b2545cff71a1137c394a8c08d23b2b856c1d5aaa783869ff80c9ddf24f5b6e61'
        '0c374c93a7ceb46a25ce26b76b02e3cc67b5376a60632e1a022d7776fb3e536c3c30faa056948063e58313605c8351a1bc1b1796ad065d4763f20a758ea623ab'
        '30555f80cc2a9afe451234484652f2835e8026126254756ac69d8abff883368755153daf9479dbcb81f00feab2c78841919bd56e78294cf843cab0b5ba9a04d1'
        'fe8099af8d75ace3c44f807a4bd29c94637a25b275c79dc54510074f0aaeffba38fc39debbdf3118605c7220a1a208e40767ea3dd413983f6014abecf7f0ae1b'
        '2ac8962331f5ecdd4fea24adb6536d2b1fbae656f180096fa068db113d894649f0568f6d757c58a6e9a82c59112d3d3c47f4555215964dfb99943c915240f5a6'
        'ec45110c5a91e5a92c5e735187adac6cf469f05f042501d399a87703c15106250241f96afb4e43ad7db6cc349fe2a03c592af0608b963a37484696109461096f'
        'cdd6b08e5855f687e2e453e177e135b343cac230999f0e2265c4ce6a5f0d691fd35028f84c0e034c4c8e5c7d9a7707966eb0e122d2b2509ac87eca88faacc8ec'
        'ad7f0d1c182345ade185867016573cd6f5362f0925951cc2eee58cdbf779aafa53af42889ba362ab2d75b58d30f9ade0533c72dfd25e5c82d6d0888eaf59f9e5'
        '508fbc0f367a3cfc7b3c7aa8b82f35d95a6bcabd8bc17efbc9ee7b25ff989a31b203328b4f493c6c6037341cfac7c8652321a3924da5afb5c62f992dea627684'
        'ac6a20e1d430d64428c24418d4f4ea1a13e761e621aae213b934cc7fa1b3d1ccb7d034da498584d5a757cef0a5d2f174040aa6873afb3c3efd932a13d116b68e'
        '22d568a39f52cdbe56fe49558800742e274fd2b458acdbc70dd694bd1f9aee9c028b49be59ae70b9889583fcd98e80880092b841516b981d80c317a01c809315'
        '30a7e0ba83668db82fd9b39894ebec6c559d661373b7b8cffdccffec8a52c6963936a29b7f8b05422a43cc87d809cd1742479ac0b8ac6fdf280047f3090cf5b5'
        'f71cfac94dc47b39e1d035d0f32867db148eb27a9654cc0f5170f1bf2cf8e3ff07c34372294427f6c85bcaac724d0c508d90027013ad9c17ae41a93050a09bbe'
        '897914de551a944b3d3eb9f63d954ac7fd6951e85bba9831651ae040695da200e34ff0e1c84930abec547d81bd36627b76179f8da33f341b0ffb6c9d6190cea3'
        '80393e0e011af0c9dcb2979e26d88cc7c44a7334dcd77f0a2118a689b0111b5aa2cf8b018cea1e8f0f8d83c6f6ebd39262c81d43998397d176785bba0e61c7b6'
        '2af862070353bb2f732084998b4423bc4a168facd5c8ecd19ad911018d2d4355951e43524b5d64b7f4adf051e32ad28babfdc60c13928fdc9c2cd84a90b4024d'
        '9f1a51f84b34c871ac37ae45c20a5b3c86ab08443689a88d12c1335f3d01a2e3786360137757c1691c12e4470f2e9888e5411f956b9f196d4f21993f6f74324f'
        '2d520a0f4c382edc9a3b7d3197368f96a6ae6ba9823164968ece6a772372ff3891913da71ad50af52fb54d9f98162f6481628ebc7b11a48e98938d10391a2aba'
        'fdc76795a9b514434fd19d056a8faef3f934a031ec21764811ce3f01f313e494f2416f3f07ce81692bfebbc80c152923bd6680c24cbf812e4512d7448cef92b6'
        '676a6ee9a696374823fc417ba3782c3e5c5de2670458465f78efaf2cd38691da2f7d14fd6bb302024d320a25c4bb950b9fc829908953290a6369f057f05d0523'
        '9c94dd19ea9d9f2d61a3d10fa94b3d6000b1b258d8801b1d1b6dabadbdf83af1d29b792a6c45e3d318c5b6e3f1130f37ddbb37b57074a89f8d9ce580d1add23e')

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
