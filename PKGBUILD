# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.1.5.arch1
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
b2sums=('d1dcf9b2a7ba1ed431d2b2c785ffc9a4ce729e4a004629061a73451a471316f437212004fe128157b5fc56b58bb06e60e758124a88c408e0b9124592c6a2d886'
        'SKIP'
        'a4c870cb5a22b410432d0aa773b591ed7778e8ef5ac46f589a26518d0c0650d7cd2e34566cf850dc827eb0b21f19957a4e50179298ca69c3a55da9a178d942e8'
        'SKIP'
        '512543621b3244ee00fbc3a6071a784ed63a269c8c8dd25da0da0a90269ba8539b558b555aa63bad9bf52d96148e3184ad6bba0b62edf9a5ba3111643241a96f'
        '652069e50060a3d84530f004f7064d98d6ac9bb02e690a3510d092d0df17598c9b3d564ae07fdb0dbbecc68d2d12d58c4c78c02cc08fbcbb8c01ba6e6256d922'
        '9682585b979585cd1e2b2fd76879954d0c101c2e27d989da02225881d1b5739c01bc8e8643d9e7fbef257834b6a08d8db247b15727f98ef9eac4c533a027eb26'
        '4f255450641ead6dfada6f5e32823ba02fb383d309122825cca941f33ccaed174eec65e86af75fad22082fd7bb2df5a3241e12589e87646f61202ef62b0dc690'
        '816345b0d9277d67ea766b7f4f24ccdcc7aaf421633b2bccbebe46f7107a02ebd28fd4b52d94b46ef032dfb64b67d5a269d946f3356c811aa3a376a3c011bbf9'
        '683ad6aeb0fe42222c4c698c259b2a5ebfff6d280cf39b8bc8e0d255b386b738fb090e1572f0ab0a1067fae0d023f931cdc74699a8fb59d0decfc12076ca2949'
        'd8ca5d5a72088c41f416f7d2b7daec71bf8bab98967769d9f1793936790c394197a01862d205c8e177212a4a8f6c7263b26ed5e544b309768be69f150758a60a'
        '178d70a4d90e9f9774779df71a96cddba2d3a578c3c0063ed8a742ddcdb5d7ac7d9ea5a503826b598a011da23472b31ac3391025cdf76079f06bf0e5d2e9d624'
        'f21d335ba47b50af59b0b8913adcc93737ddac0899ace5edd981ad731ed471a570d3dd39e40d94c418ce164d4163e0ea6311f30afb595deb15c5f59a46339a32'
        'b51b34f0c7d548b25bb39e563ad50979f6659ee6fa88bac6879ff4a17920f46d6bcdda57ef3808382f051123c10be13ae9c3ecd530ebb76a9375573bd852741b'
        '347a1cd4999245c2e9d983bdeea84eef7979dfc7d4c8091b24643a1fbad9c9e0b4d748e006c0128c875c2a7a76b3b1f25c658552ed38e667e7d17a50bb22d286'
        'dfc93b3234b854b917e3b217b27a094c6f5cb91115aeb43106c2ad2fea3de81c7e5535f489cad65f9dd19c0a0e1f79abfda9fa664f391432fdc14c133c33d5d9'
        'c4f91507d5976c294bca5e62ba164e9cb4830a1ed59dceaed2e10b93e9545006a4ee1c0260739d5b22c4b66dc2c2e706fc03c3d3d41d90862dbefb91a729e76a'
        '5bc101911ccf4199668b77011b2a5c036ebb6a7697b95f5a560ab5687cb160d50ce9e35d16bab0c3cc9d9a208d4788d5675efeecfdb478228e66b3821194be8b'
        '4fca61c17aca28008a3a5bb84e533da30ce87a66d7d2b4ab4cec537c3100ce8e96b4dcec73061103825487f1c728b5a35bbfcf2e4eb7917b885cbcc67467e808'
        '10854e655e11c1d8f767f77624b475f805a984614fc913e113d32529c7089f6517ffca84bf6aeed9a41bbab49dc74176a896dc5dd69badfdaa0e5c1d5a9722d8'
        '76399a515cafac04c16c0b9ae88103e00b74954702a818ce24c8368b0ed90b7a7b7bc0ec0f741a1b8e2d7fdef94129ae04ff7251f4682fdc3c28afb7af8de546'
        '02982bfef66454fadd9f1d2fdbf4f58291ed54fb3c04dd7137219e984d85206791e85f5dfbba6050dd2445405bf2ee15d027763fedf9d2493b0b424ee02fa2db'
        '0669245e559c28c6a2c8c58590bac6ea5ec3079571d143e029e84851262752d1a716a017540664ec723a1a3a7d657b63b60842a42e30a9ac1bbb4f301f0c7bb3'
        'eca3e60a3563abb09d0984481b9447055aa79c12f773355f67ebddc93a5096dcaad9ff579457a8f31cb1756318a4b5b2cd568b3f4ef18c124090e6667cb33d36'
        '4e658b19cb898ef2fa851f48700079f81d0c0cd8add1ff6a4b531bb13631d6d73118256e8f6f1a47f336d5b80125df3b453b6b473eb62d5047f68d76f43d3fc2'
        '1a0f167e09e7e84002b6a1a9bc2bba52bc27bb6694bc6a6b409d80dbe12607024f46bd13ca50dcfb867ba49050b91c8e682f5d187efc0c68dae1ed9e8e1e7c51'
        'b64a27db76d579476d59b3ce86f13a49273ac4560d74e95caa04bc92c98bf71b201ecb8e855053c11baaee519bc1a8553fb2419b9afc358ef8c9701719185115'
        'bfa716ccf3bce4821dc1c7b842937c0b2b4e7eafe77fe9f01676e69e6b8188251ba07eb556f5edf2636861c57042f44605825686349ec1c313c12a581fb5a732'
        'ddd7664056de78b122fe1fe512e79dfd48b4d86eabf38e5703283e3208d80d00656129b173d486042efb7824bece46fed49cec8272afb4d76b8c97857e82e958'
        '072dac4e7d17f884993d4b5865897bc5fccff8aebbc2d9295d3dafd9d2f30e259d9df494dbe47bb11fe272ebcbfe8661d533f452b38537668124813605edbab6'
        'ccc35eaf76e3c4c424b2c291ce0acc0d081b2700792f9b01993ee2964c4200eb4d0bce3dea6bc58ebae18a6bc3c5bed7ce9041107c8830aea2658df75c371348'
        '6e3d983d369eecf0d383dddad9fdcc802ac11d7e6b8c5b31a639e6fae389cb5ab131571f0f4d0dc8c066973854755ff95c4e7b5e5dd18427d87c9e3965608315'
        'a30bbf28d30255e6b726f5bba514533fa2a2a5b24cf64f1ffb104c3ab011f8b1e6cad2f2387fb79cc72d1c05293d9f2bb2cd5e54cee0660accf8d170fa710d07'
        '9ff9af0656eea798d08eb65df1e0b813964a5609886b09c494aab36be51f1ddcac2076168491cecfc8e2389d85f7fed2f0aa6dbab5ef3286b5ba51a205dcc150'
        '5e3cec61bdb3d340563a89d144c6862f59e6a48b0264c65a066c8f991371d0c0876e3f7d9c8fe42ee6491b4dda34ea2b0ad3ed4d84cb5ee2589c80477274bce9'
        '715e80751a1f61f599d82bab19f52f8be2151fd5b009e88f514f46aa948b8991d906f1483c615ef1b803f15f24b1b8d55fbfdce821d473d874b7aacd29c033b9'
        '77f341e2e2663a19a809deaad65efa7c36309bdfa2225b129cbfb40817b8e4403767718e2bf53237a283dca9f95783100b0ed42493ef4dba8ff10880a5e84d59'
        'a53347bbba57df38c4624f28afd5e61011fc10a120e691c514036080a0cee1f4752a84bae60e21ddc6015ff815dfeccbfbe8c402fd6ade44d8d977fdc7c215cf'
        'cc73c2084310311c6c8a0bca4ce7395714c02c19592ebc31ceb0d06d76b52bfff95c5cd119ad363e0787783b0db90c1a7974944c1638f32b45289a488b4c78de'
        'ecb631a61cf838cd6bd4ca35303c1de12a851ba6036e4c9bad23d28ed9ee86a6d1918130699e1ce746d41ad9306c5225c61b20349c7a19d83aea27f9a3c9cc9a'
        '1e3a6fe3bbe72f983ade1502890b29c86c3ae4ef6ae7e1d83aaf37868d3e7a9560f33e01312fd2218225ab0a1b76f8c4eae405be4b8cc0e36d3fc00856bbabae'
        '764e0c7e9e39152445513d3b582daff9ad1ff87fd29491d527a83670485518e39685cdd4be3b4507743c284802428b22dd3660dad37d7e6137b6211149aa4a44'
        'edaa7805f09b3f610f470bbba3a29867b5fd551a1b7ba2583653c7cc55f572a255f6c5bd5abdea832536ddf3ad95bdf624d8cfc07ca5236fa034d8904f401f6e'
        '761ca8913e7aeabe9936e0d2e2c34871a2b852d5712c01863281804a7510b05bc130f508d4a37bd37fb85f2388f4dba86ee55b1c55ea831367a987640a945854'
        '3553993a3a4fd55c2caccf32fcb8d8154eb17ada0d405a5668cd8babc5412ffde29aabc9e254ddeed94bacd2fb236362d5706b1c1a80384a2a42f4b53f8f9646'
        'c96414ebb1f440f71c6951d8f2b5d2010d64a646eed64e690ca8d0acaead2f4b94e3ab0fa4b334b93f6a990f4288f62f1592ce38525ea5cb32a72601e669a9c8'
        '59344cb56d68d9f2afd5cda05b407d879aba47df6eb8aff4d1413d164c95ff8dca6921c7c500bbd9ab35144aaced26038289a49b69066a0e6d877feac3abffba'
        '4cdc3bb3f7f446ea93210bc0b88dee3b27c0a28ea87e31d43edbb763b7e159a87ba4bd71f533dc3bb9fa3d720394bf78a0b694eedf5e951565fb9889276be07b'
        '06af07c212572209b2484b9d3d9012bf6e6855de8c256dfa4ac75ed0e909a28024b75094b12424c703a43cc5cee9f1d38e3f25ff34fa9bebd5eda57f00d2f030'
        '5a458427e2c87cba9b99c0ada80d4739564d1e7f2c90ac5de29f3f736b77117c3b53b4144b295c22e4906a6cfa2ec54bd6a22600e272f4df9ce12ff113b2ce27'
        '39b605c34d8e0497cdf7605866437b52a7cbbe85af1a268d2eafa699c7bd3b83bf63028ab8d43aebb59b6bf3f815290e91b4e320347dd9da7a08de558231fb56'
        '89986ca7ccd9d0034256413b20d1cbf0b06862ef85bc8e5eaa8f0f060925546660887715efab22dd99c6482a83e2a42c5aca845a2beb1c0cba620d106ebf97ce'
        '749cdff5abf61c9c619554fe7e8e17c64d70a458bad1fa123f3177c910edbeede3f9d8b35b18c78fb40203f0ca7e6379d142bea2c9b8b10b1ea31730449487a9'
        'f24892245ca666c341d97fa3d11678f90ee8b5524dc4729882efdd5d72677f1d59d9c5b3dbc20454c48b772faba3bd2fb39e3e8141de71d03d4ec6cd362d8a14'
        '5e08a5bb18be0391f4dc895443da78eb4ba0411dc425fa5743f4eaebc539707230d6a245e776ebc381662d0df8d32a9929a65d4c10326221e6f0176c8a001437')

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
         '0013-FROMLIST-loongarch-retrieve-CPU-package-ID-from-PPTT.patch'
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
