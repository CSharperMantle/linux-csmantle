# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.1.11.arch1
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
b2sums=('389da9454f5400639802909ef04069ae5a9d5c3a938feff04d770fb3b47cf152f0cde2ea5ce57addb3e8c1ec3bd3ec3a996c4b65d5d205595db96e61a15db50d'
        'SKIP'
        '061dfec9ad030980e980c6108e4b60dfca8daaf796987bb976bfac0b79f3a84fcb90cfb394a647e904fb5236b3d4837d090e9025c59eddfb57d9a673a38f40d8'
        'SKIP'
        '512543621b3244ee00fbc3a6071a784ed63a269c8c8dd25da0da0a90269ba8539b558b555aa63bad9bf52d96148e3184ad6bba0b62edf9a5ba3111643241a96f'
        '652069e50060a3d84530f004f7064d98d6ac9bb02e690a3510d092d0df17598c9b3d564ae07fdb0dbbecc68d2d12d58c4c78c02cc08fbcbb8c01ba6e6256d922'
        '9682585b979585cd1e2b2fd76879954d0c101c2e27d989da02225881d1b5739c01bc8e8643d9e7fbef257834b6a08d8db247b15727f98ef9eac4c533a027eb26'
        '4f255450641ead6dfada6f5e32823ba02fb383d309122825cca941f33ccaed174eec65e86af75fad22082fd7bb2df5a3241e12589e87646f61202ef62b0dc690'
        'ac5479a0dec478d90484d08beaccde17b294a09a77fed1808db980e15f8582358deeb27644aca93de840ed44e2e4c0254b7623add076bdc14e2e8808e59bb3f1'
        'e9d54154a5221df8e09191176a6a34a4bf863266405b29c1863ebed2b409b362057af595cce27a4d8e9fcee700f7eaaed37ad44f517ebe95e1c532f3996a9c13'
        '57f84e837dbcb8ba1519ded6041e1040aac509fc34769c5055daae9671c5a338bd3524831cf5284f31a938a938fb92a4369e7db15fb406919164c060877c9747'
        '2e87659be34dbdfaa1130f63811f1ff9b354a1dae1a5b3b181dd9a66b1671244671c47fc6d4c8e22a702509f6345d9f61f95db03523eb9c26c3862eff64542bf'
        '4bae397345766b48d240f317fa65277f40533afff341579b7273f1f577e4d24f8a6d31cbfb9a78de50f6c4907adb3f307b6668029b32fe6d79185bcb9b02145b'
        '945871a818b1afadbad197632fd5246ca812fa8a4dcb834e34d2d7c20a35196530516509cb20f8ce79e9a83f1559f7874846a6627c51ad9b61db6c0722cc016d'
        '8776aa487241a0296f2afddede98a191e91b6446fdf8b215c73575bad2d7e3bab3c3f61f22d948955a570e05c4488b60188d46263048bcb69be29ca863a8a51f'
        '496ec332549196e61bbeebe76d4191590a8edf6917ccaca3546babdc2aee1a1fb2bdc0fcfaebed3658a1564eabbe59b6b9127fe7e202bb066e02905dffbd56d4'
        'e2f6eeb766327e513a28750c4194ad96300f7ef0dff93d3ff8ebcb749697933cffda224513b66a7f1ad05791bfd9716d4775540cd227e62b8857d3be0cbeaa3f'
        '023fa756390472508be1d03ddcb2e468cb57a29390a6954d92cfd9cab3693a28f48bb477b604c032927c0222ae8eb34c6aea49077d5b83bab1230eb4a2795a34'
        'd952342185dd99554941de3c19454e847daaa709e89bf78a70db771b7ab106fab34794f15bbbfedf568c90d38d645255358569893e64cd893e8376eb7ec68da3'
        'a7a419fb6a7168d06d6dfa21957e073bd567fe22559f0b5fc3ce758f520c7a659c2b7a6190997f7f9b0402cd0534965baca43d96d3d421f83b2e05af685d17f6'
        '65c32d4adcd4dd33bee64dacc7bed152e892840909b997801cdacee840738f354e144290405e5834b4448fe97d982fffe8bcd8db8d493c52500d91a95df5bb9f'
        '2492deff58a77f0b71b8456867ebed9d2897be8de7b022e194416e8bc52d500b7650fb278a503b451505fae475de31c46cd3e1b50dd40fd6bc76a6adf83a1681'
        '7e0e2158ca77598f022903cf7f341e81a4b34ea3cf6387f9a54586bb48d881b9d9f5a72c394a970dbd3041839fce4a7d78bfa8250dae8a08240b462863917450'
        '677c144ee3bf5359a6680510538b99ab5bcadcfc6cf36e5b2c7ebfb21a591d54474661ac2839328b2bbb552edfd6e837aca0ba16aba171e0779913a6b1b4102e'
        'dc11129a3f2dde8c2630846f19a69f3ca72ee2eb7aea703313df2ffa68f208b03c946c2a0a748bdf45af9b448c5980a7e084bd7122ace8aa7f2bdb17ae53df2a'
        'bd36d3c48849a3b2a208c7d3133b5e1699b25b24f4e204c20e3665c7603cefbf7ac561ff55dcf5fae1e77777aeeb4c4627675620401389acd3ee9eadf205a917'
        '8114653e8116c0e2997f5aac62ccfecc6bdcdd99547462f3b27fa871f0b4f8a251eae5c73e3055180d37f3bae4455cf0dc6eb56e6dc347529e5be4d04ae76fda'
        'c7daccc9bd2413a17078aa818f4b3baab27b90b1f555eeaf56360099aeefd2c359a7f49b579004ce9f56a3898b17f6a61a25843048ecdc3dbfc3dd50c57a7b05'
        '4b6fd11050570b4c7b6150d45867959c2d9b49c5c7cbd4c0e26ad03af240183dc2830f4a6ad29c6dbe99321bb0a48356e4b40cca97358466a49e31d43624daaa'
        'b26f41ae082d8f40b0f24c5cc614085d1ccba2db5e3259b549613ff0ed9490d91b7170f057c6d892904ce9c7cdc4a7b770b8d329edcaed0cb8d0d730e5662f76'
        '05dc0f8774d260c1cbba6cf8f2d07a20eb30983f868a990a5a04da21bdde025099c10605f9e199f0d011591697bdb54c96e890c0b610db1d4f1a4ecf4dd635b0'
        'c0803a0e0809a213f6ff26286ccd85ca52e618e3499bb904e8d9ca36313b44aaf261e97971f15a65d6bd783e3ddd19b53578c82e438d19f2846f4827958d4359'
        'd5a5a97f3d249b106533fa8e8fcceebc70232d2af1ba703589ce923bc2c6025cb0e38e3bce978076aa9e39185ef75dedd42be273064af77cc895216dcb26022f'
        '85a8da415e5e20fc01fbe2889b87241f89f8d15255dff564c4c95643a0e3f508e3d05c9a03dafc3734ebe15e227d2fa9f6bd03fc9beeef57deb622c6acca1326'
        '4b222e359ce9726012bd664cf389b1cdc9dc9e18b3213ac26e5b2036ccb6bc2f228ac8b670ef701ef8eb663a580527fb8f6ba43a3f9a0944964d51ef540a5e41'
        'c3b756203b16e69219a69c194c6a533fd0f175e9cb35b35a45252372971b3d92beec2aef2fc70cc78f4c02ca3776d788999134876cb048c7b7cc566d91b2c601'
        '3405e41147c659baf93380f25a9baec6cf897a90f06dea0b25d45e36745f23d9114bff975dbecbedcddb888e6ad91b05c9150fa6c0234a6bc704bd6d6f65707e'
        'd328a5f7e4c08b70c789fb620583fc29115dfb30ab07779547b92367e816323716d7b37e6a659a99950f171fb6f7801f757f0a8b803682d253957d228cb50c93'
        'a99183823220105e9b21558b1884a9697aee68f82757d6b05ee51bef6dcbf3eccd7b87e9075ab5759983825b7a2aa42b944001a31dbbf6543df1ec2feb7a6742'
        'aad4e51681ccac58a490d2e403674f0e64a62543acfbc9316e427f364d62c916c8bc93ee0536c4233af20c4d8ccc843bfdcd29b417d14e6bc0b87001d7bccc13'
        '9398a7b1d0562d0c10e6b26ad8debce73548cf9fd84406eeee17d5f18262b4d6d61f297d5c69ac5dfbe3fbb44f715ea72f3f100dcfcaa27261f776a8fb05aa54'
        'b78413259b830e2903a507da7f801aff6a5ebf8b78c3df319f899b5513c7767fe36ec38dea4b2b6327a76bc86a15aeaef5186d57d757c5da57b0bd3a6e647a02'
        'bb299ac7cc49e10183bcd7b2157e133903751bd656afd335227d04404daedfb880a0d154e0e4f06292489aeae0815e3fd4e876bfdf615bf84071257607f04d06'
        'e03449e3ac77f29854138b79dfe73c2374219497a538d0b82d60620a0aa18fbfa2ca7f1f64835df27b70f53b9d1b030c001fc13175be99862994e13075dd8fed'
        '583863fe941361661397031ec3832ea19aaa70e6f97b5a1f03c84a6e7ca4200fda8d19d12e8d2153b91cecb2a27388cc371a8b5f46b0af1b849ea84205c799da'
        'c24174aea0cfce469c833530da2639183f36dd5213de7bc5868a3b2fd3f863684f6783e84875386329c82388d64e6c1900cc3afc65b07f4ce7e2eb2a5778c109'
        'e4d15edd62138ddc32790826d87af0c68fe24990c90616ff3b993cd0005e1acef2a8ab96caa24b59cc2079454c1ee851faa693fb305868a61809a13e3992f80d'
        '364c98b4e04912ce16961dd028a91a05681001db67aa6db9d38eb892b55aed073e90bdf6c0549ed640d3eb8df0bc7ab96a38f522e3dd94aca9f33d31e0bc9fe1'
        '131f19de1128c00bfefa13735262f6850ca573b09679bdd3f4d9637ce7f57c0745dedf10ee116b5793a7165251088d33963e86a698d5d524e676e4a9eaaff117'
        'c10d179322e0b0d686be32283c4c08a9cd47e679da141c2f1b1950f21d4c6c94e490f673e38a224c731dd3e6aa0b291f775181218eb9b48b5ebc11461f6f1ab2'
        'bc8b025906acd19b48c29665a3bc06916be55829d6fca9f248aee40dab873ab763758f12829040a5fab12c2e7fd0e13e1db7f4b011922268da799af4b0222793'
        'e7a9bf4d910a48279a0d100b637fb82aeb02124726bf27b95a5239a2d78fb0c82dbbe7c5e8bf5d24fe272007fcc536a7351eaa08ba13c6abdea614bf396f3c08'
        '501a6ca703e24c58a20ad429339a160c89f7a07bad357d8be94c221905775ee08506e59245114b56e49bfb635f1c1b5f8a1070dd2ac88e444c8976f9396e944d'
        '72c06969d00a4bcb7c651c8715fd73c0d77bb17e61ad4ebf369fc5d375575dce2913fd73d5a7ee4c64066126744127b4bc1f09ce7097b1fd4c4cc6fdee84f96a'
        'e2e1858ca1e974eacb65127fcccf955e9aab35d4156fa6b21e658cdc47e7a3e66f58812cd676d30d58735f77306a9b67b6a0dc482d810479cf2183270d872a5a'
        'd404310b9902097cf99d181ace0d3197d4c9cac63678ec0dd350de60e836228fc55d012ee4ccc8bf700a25f173c6a93fb4cce2edbc426304bc3bc7b2862bad7d'
        '9d506b489e88c89eb7de2d5f32626f8ca276f3233b1ba7588b7e4d37691faeed2ebe03dcf2a87d111f1a2dae4d40167e18a395979ef54f52c72e5131b5b6b41a'
        'fc66742485e21c9b664276302244e7cb1fddce86cf63f4e27432c206fbbcb94349cc5dac701f3ac48b351afe77128559786811d7af937787bfe3f377a20fe35e')

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
