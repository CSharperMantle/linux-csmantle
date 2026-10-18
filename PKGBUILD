# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.2.11.arch1
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
b2sums=('36a455379876a3f452dce7347211ac34ddfda9a445b0b8c0ee92664429a8ea85d2f1a101126b6d748545aaf18e3534f8db53d6110952f3d5487d029ff0f9a800'
        'SKIP'
        '06f49715b71884a0cbad51ab4b526c1516926cb2429e7a6e485aa48ebf277811dec391ae2264501245654275a84af1df3780bf8bf8df755cf47670d6c9397703'
        'SKIP'
        '43ad5ca423903e7a1a22e1e60fad9c0e65a5081b138222b780396e98115d04bf1d2186b9f9d7d15e066ced9cc3373e8c07339abf32b6ca71ba3e01f6dd1e32a5'
        '652069e50060a3d84530f004f7064d98d6ac9bb02e690a3510d092d0df17598c9b3d564ae07fdb0dbbecc68d2d12d58c4c78c02cc08fbcbb8c01ba6e6256d922'
        '043c18764e8a11dc8da10875fbbc63d63ea001bc176f8954c8ca74a3f85f119ab2cabae90a7e3571e4721e128ef59d7199332b4f2454fc1fb4430cb39aeaad15'
        '416c66955560ec4ae58e74586617705ea73d6c29b6312d9ce5d491f8db07be31c947e84e7db7291c6b19eca52e8125b6985717bd1ab08a4fcc11703275edfb77'
        'bb964958b699122b69df1f2f3a00a69d083e0c01b0a2cb49f3db1ee69b3b341c572bf305aea15df7920ba918ddc55ea02f547f0a5bd5c628aaef261be1730cf9'
        '00e79abb76f481bf31b8f42539684380dfaf5b6aa2061e6890f79c671b79ffa2ed1386c5d0fb1c4cdb547a03c44f0fc6b3cef3bcd62f3f7f2095a62d9ce93edd'
        '34b33f5779509bc1bdaa0a19b7fbb1e2b58313996e972bba520c5c8953c69e608f06fec0e88391f9c65f3847ddf44d30a5aa2c5f28595d2dc2c2538ae2d329ff'
        'db0dce5b0547bbcc29aa4b88b07c6b51bee81e342b271219bfd22e23f69a594c7862175b04c04c1c8770c6b3d5de47f7f99c61d017bd71f2bf86a16175830be2'
        '08ee1f718d9db8c7959252c5ef7fc99be460b39c26534ecf6581260dbd0df6d6316066727ea3f01c81025b819f7fbd7adc40fd20f7eeebd87bd5d5708e24d16a'
        '1f9ca2da491c27c5646379812ecaa865b4bb20b523fc1f232d65c1c213ddf88c1477663722d96b38bbe7bc7535fe2d518f0f0f7e18a1971b6926cd7634724a97'
        'd7c5198c83e48e63431e21c8d1f0a1dc08287272c14d298e8b60be407836fb4bbe31162e856f62ddb83bb7f69e6d0a83c7557646e3629361f88d36afea00618e'
        '2324568494d870b22cd329e01eff8c28ecc45ae195427a5a134bc74d65b5728df201bdd3a392cb3fa3f2d4a7a6dfdc0e768301fade4a5922c82a9733c7d0768b'
        '8083d344e27228d58d1740e46e473529506f6e51bdbcbc4552ee53ae55107acfc9a58ad1f0c07846eefdbeb4be6dd77f23f846b88e1aaf96c67b34b1d93c871e'
        'ef29e5d3673472db9ce8f733676ff59115e4bf8588819743fedb71fd721191f22106b93f6d6d4ed2956a3ecdc258b5334f83641b54b77c70e8731e879d71b252'
        'e8e2e49dabf2fb615c329b8a7b07d8aaf543ed02b9bb775b42e17ab0580e4ad6bb52dd479899736602048bbc6bf2dd6bd1da734aba0fbb1eabc0e091a5603881'
        '5e2931bc1f19201fadb282cc444f464eeac4e44d99c3b6309c8e25fb111554376b8fdb5002b723868d1242c0ebb9f18ca62aeb8eeeeff5f2ad7ecb529ee4215c'
        'f175625838126c4272dc5c09730b76e398f3d2ce2cfccc1a6dbe18852a75ac5528757484c2cefd0568fafcacc144437985a2fcb59886b931a4ba52d24029af50'
        '94d66a399374f8cf8cd2e78f6a1504419b142e43a55ad678b6fafb00bd7f5dbf11d2790fc5ff87171db2fb79fb81e080463b423343e280b61bc4a2d6c6a54789'
        'b960dbe3b9b1ef2a2c3f2ecdbe4c4eac308d9d4d5697e5fafa905971aac978dee06758a6720724097b0e9d799dc91b9b6b2dc3d192ecabf0fc618336a350f535'
        '4e6332c6d56e9c2855bb03de0a859736df7be6051e09e4a029704d77354408c0a0a16f4934a9f0b74ff542973f9f068b57233a0f28e7b61e7c16e21fac2a2e13'
        '65728a06de6cf57ac65e1be8530b8dec92a23ad7f632875eee3311f22a352a17680b9f683554758ad3aca65b17080c627e522cb153b2c44fd938279157f5f389'
        'd852de0102dfdb0f3dda709be41f0123739657855b00911da753dcba3775450de98d1326c0976acde3b11b1d41afcf96bb2e956465c701a34130424953ef80f0'
        '5bb791854473b12f22e8d3279041c2e2b08daea8a90d99b238dd5cb78485d9be28cb224da1969b57958894018bd656ed341b610e397e0e2f4789a480eae08325'
        '4dd2089bd5b2e014d1f2667f92897f2daa5aa1eb4b977f67e5001f3c5c2474f8e801542afd4d3aaee2d9cea9c3371bf5e791c04e1245b13bd165ae67322cbe33'
        '2f9b5cdd5ec8a12e374b166305c26fe00e25b7e95354489bef8c08145dfa10e50baeaba53a9db59e15b5a483367dcf0cb2f58823591a76a188263771193d908b'
        'b7f1390fd316c4f31af52952cbcc5270149567b04b2778721ad123b4d190656fc079e814d284cb482a3b0b5762e04b1837b6c31044940fe74ddd1e5eb64eabd0'
        '75b190d3bb8d8b1b72d38ff5beb759be321696a47193e52d87c29701f8eac7c21fe8429e7897e381ee4019ec3b27dbcbd7d020525ace494cbdd40de94475da5f'
        'e8af34f9ce372b138e33dc09a3addaebb8724f4c25d66933634b313a56f8cd4eb74ecd6385025fd89fe52bf4ae6b985f237b4bf153eb97767b74c591bc2f99fc'
        'e90bc9c1c3e3b17bd3c5877a70e39378392f67b05509a08d9334748897126f1df7f5a695731add53cb691981dc246b6084356bcdf83ec3d5dbb06316a818c0c0'
        '9f2491aa72fe181112788e9a91fcc396044ef9f9cacec043453b792c78f45a4aea99284d56375008412e34f7a033c9289d38c6c5ab41493be58f669d41ade347'
        '3d5f15d7bc8340a0ed667b52b94aff73be14a9787cb52203d5e9af47c9d8caac05fff90c1ff8940c63b46be32ed62a5c2f8b9a11039dbe60b6a91e901d31e3fd'
        'a9ebd1376ca72846f739c79f6d7224ededd7c91925c3801a95f28b979d1c64a542fd833dd8d35066458099ebf5543458f58cad7bd44bf87d1965c436b1d2835c'
        'e929aa780daeb7459f12ab51fa420dff2084a9736f42039abd2fa553c05cb83b71dc4b19ec5db0734f052ac167eeaefc6fc22957a7c675aaf674a7ff22616866'
        'dbb77e76decdf7f18298b6693a265ddb1c70db266ec63bc191146bbdf58c3e66153d327746d330a03632c7ecb8389aa6822c479e4e31963e595f04609b60889d'
        '863d564dcd2593191164adf66032d115d8dd0b5743857aa12ac781290695ce71f019d3568b040754c3005cf9da1e63ec1c6b8afe7ad258770c42b868a6b1e931'
        'be513427f9bcf0229f6908eb618b7a93f5aa7aa15bd53af024e524adc484c16ed2a5bd34c8fb0f446c0d071b1e0f5ec206beb75a435b24687cb9254efb924133'
        '4b72eeb65e4f38857a26cd57dc2fd091cbbc816b320d789e88b263e9c35c05c61330eab2c9e663aed665ff4ec7f1b37b5a2f7b1e247a5f84df367ca31fec06e9'
        '800a975dccb9808701096cdcf76cb50bca8dcf323aea5b673115a04250e33c9b93589e42a560289a0f4792bedabc9ec952599f5bf487dafbc85765631491e3ef'
        '91a56a47890332226fd87084109501a51c25995b5da65d93b9d01c3e587fe824170f7eeb9ab6a2e7b0826f2c9299676922fc4de426933b2edd46f294ffba2dfb'
        '60733e90370bf5f63ab8f84f093c4d85dde7384c58b1c5ed3f81792d13c79e0aa28366ed872e1fcb060043df6d801cd33c7e6403eb09c8d42461b4e6e05fee0b'
        'be36d28f63fca5eda7fe3c1e52a36086088e7b4ce5778bba647ffc7e043ac760ed90fe1a504a634eed33c57b6a5ac990a48cd233467010aa813f54796e7fb693'
        '3217db34e3d3cebe069502432c1ef9791a5b57450b6ef30bb59f2dd1a408349ea97445aaa0cab8e069de579ae9f177648496912bbd7e9662575c2a5048ad8363'
        '3042097a130b34a6af67e76dc52b3b0fa4e1876af1bf72dd3711927d766df7041d65f227890960343bf7545713d8bc141fef0f8bbc981c18b0a118e12544affc'
        'f33c9e5795ad7764a651fbdf423cfbb3732cb7bed27a69dda4cb642880295e2ff8f06ec2130cdb0671769d6e5f5187c1c38a13ed1ee5bf440a47ee419c353370'
        'd0bbb17ad893ea422b9cf2377de477048c33ba7f647bcf06585bb023c4a8a10f4a83a13a5c6ab677d230709e3ad1d66180ffc3f5cacd8aef621d386135395ee3'
        '023c61d39ac4662f2cb6396a176faae147c987265355650a498660219e48d13f2eb6ff365b7927ebbbeb1941d4f09086e2a726e036ff7c524eeeb6f134af57cb'
        '3de77cb0ac2726b05942f2e4b9a7214a3d62b0ba7f3858184637c10d458ebeb1f24843af9f36c7366121fe5eafc26493e5a28b584d8e0060dd577d369e776653'
        'a43caf92b3bc03bb49b29189e5a2351b1be8a47b49de3b91b6737f26c7fc476b3d3a79291e93d8e52c3e2dfee3c2de791977a581e7d899b9300a3e03c6a053d3'
        '4f83ffd4a161239a375167abaeb0085682a621f8a49926ec435ba81ae8744d1852a3f2ab3809ef5930b4c30025c93c113fdd75e23b14f89f3af15eb27332eb05'
        '34700b37fdd8ce8277034ff513412183ae2873a041e6174ef9f5da74736306174714e14a10a3d87a6ee6a6c7b0dcdcadc68b7dc145bfe236b1cb21337979d21c'
        '5c6857768b61514bd7e3f8a3c485a06fa957f94bb3af66cc52bcb81ab15b8b27742bb7347de55fb8e9988b6ec58ff606ce49e9a35aa0ad58cd392e11113a3624'
        '12a8b3943d906c623c16bb97f90d3ee9cdfb7e9aa56d0ace9312ef879ff8e5fd81544644090859e394b3f42d3a5f282deb99315baf06f23c62ded4abdd54f66c'
        '4160f1a073824993e1c60f0b7359b1d2c61f16db4a1af4683be304400ddcfd56154afafca77c489c304ebf57814a8ad90cdd068c5805fb504e95b53e2be0053f'
        '0e015e0101c01a04088350b472be0bd26b2e3e8a399e696a906dc02b5da8abf6a9acdf7f49d64171f367aa588e696c6ad0fcd3f1ecbef910a214d0b6aaab6281')

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
