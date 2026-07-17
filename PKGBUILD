# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.1.3.arch2
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
b2sums=('b6466e2798627522f0339c670a223b21266f4d4ede39163867c0f122295e54c5d24093abb51d5c6c6c917de0cb199836e81f45f7c391a5cc138cac2a519438e8'
        'SKIP'
        '3a6a946d93a0f31847ad3c58230d4c1700f7611bc5b1a9af9e33ec180c007a47158eb00220edfaa7d5e1467d0ad496a0468d6e5c58606cfc38d9d7dc33dcef3d'
        'SKIP'
        '512543621b3244ee00fbc3a6071a784ed63a269c8c8dd25da0da0a90269ba8539b558b555aa63bad9bf52d96148e3184ad6bba0b62edf9a5ba3111643241a96f'
        '652069e50060a3d84530f004f7064d98d6ac9bb02e690a3510d092d0df17598c9b3d564ae07fdb0dbbecc68d2d12d58c4c78c02cc08fbcbb8c01ba6e6256d922'
        '9682585b979585cd1e2b2fd76879954d0c101c2e27d989da02225881d1b5739c01bc8e8643d9e7fbef257834b6a08d8db247b15727f98ef9eac4c533a027eb26'
        '4f255450641ead6dfada6f5e32823ba02fb383d309122825cca941f33ccaed174eec65e86af75fad22082fd7bb2df5a3241e12589e87646f61202ef62b0dc690'
        'c88a5b9f184f0164ea896e7f8cec266998f91cb611e4a063c0e6219e10f9f223663068a84f42d3585254668a896ef578a657c72292de9278d8dde1e7353642ac'
        'abef3713cfdaae7c01618f5b62f6b222c4136865fc1acb94ea6ec8074dae8d7e909dc88ca96fadc6013492e42bc21ee82028ac2f8ad4286662e1ab8c096cdd87'
        '59dbbeef4ccd70a526f7ae91362930e02c5fca3b082d702cbd6cbc95121b8aa1f4e5d87aaedf56ee2c5ca5772494861634d8a64ca2740802244088dc04607cc4'
        'c566d2ca99f5371219fa71d3c63312561bfc49466bf4dfe35f1b011a72294586eb64ac89006d41a40736109c677815e9254ad632260c39f1d154e8e653cafda6'
        '6ce8f4aa1609d00cf93f2c442458df0a1ac2bb7a432cfd96821f5164675972d4664b185ab4938a48ccaf9d3e9a8be4e61b8c6e409fe019be3f75a10ee3bdb112'
        '48281b748ad0b5ecad679feb3dd9648027894580fece4636282d873d5014b58256956e1da568e5b2a4db0170eb05834e8003faf06d634d5e5f2bba533e5f91c1'
        '2e0b90199094a542c4fb9e3bc475e039e7bda65e3b425657dfe7e20f40a26ad2b0e0a13af94e89605835f85e21b456c83e083134db1c5b95e1a12204541f3ece'
        'e1ef0331b9b32dd96f3a4d30d4d06f6610459461014ed02665bf2f4110974de4d062301c42d2486421ed7dc4a8b7662de2a0464d82e110a54ee0891a33947f09'
        'c538fa2892ffb1f86af953c91bda7cae2dc19e6267126a9809a31bc729d4d637baab77766e1f913c010560b2bb1c4e2983a945dcbd7d3e322aeb8e1ab38f9502'
        'cd9c59258611d20dd7b85ddea8d86b6aa1b5cdf4d446d2daaf549edb802f241c5e0b86be906f1b8fba2fcfb71e466961587fddaa20f4ffdd116c9c2a9a618ba4'
        '490ab78b5843a3ccaa9823eefd26e6eb93445f2f8fb6a76a52d06cd86cdb89b79d3b08b2116ca3c3796d80ee0d429cd3c8740735d6b9debfb564ad6428f8a5bb'
        '564b562b054787f379be9a9a43b9f3639ba42bbc4a31111d49a4da0a02b2b97868da07f922f99c10b2bc010b04936bb623be6bbbd595177016e123718944e9dc'
        '264eb3df2192e2a7e3478627bf510bc0c64b299bf6cb148f11ff45380cd73d434804dfe55a430711e993f2bc229c301febfcb922d9b0f738a5f4edfde86cfaf4'
        '895d712b6749d6bfaa2d8edf3fb15797364bf29f9dbac159ecca1a61cea04ce311ee4b76e74b15d75fc12d762df6399f11246bf2dd0472a53aba6bc42b120ec7'
        'fd6fc24978b14ab60833dbade88ff32d5c5495db72890d8fdc36ba3577989d27994cb4c650619fe7a392d54a8dfafb357465b0e6fd47f9c9ea433cb3aeecb075'
        'b44db6d83e0dd38fda4b5d710c25d9316e0774b599d54074c9907595cf3288a0448192af3b4744c2e355514ef6b620bae0d1e685197a370221f360359b4727cf'
        '26fa4f17b7f76a66ec6a90fc79fb0c4e9eb88a39626acea10cd09fc5ddb8f72613890196a2bfc56ae082397e2df33a16bd5a3242d24aa446c8f66ce546ffba80'
        'd319c41aa593f47b492ee6628fe0d013bc92405c8b369ee3137e39ac92cc56de7d5c0728184bbb671b69ae0bdcb57ae1707fd6df9adc248731020b6b36ee432a'
        '004844e649036c8ea42edbef1152ec0e3bc624fc5971344f393831c6e77d665a423f93b3405c593fe3440a5b54502985296577eb45be5574340443bbc36c4521'
        '75c5e26543903c6039fc201dbf7a543c480c83b4c99c99e87d9edf041c9cbe424698d93bf7192891860a931c17f08440cfe1b47a232101959509258b8bfbbccf'
        '831427852cfc41e8163fd1fdc0fa3fde664f30258b68017b2608dfb3026796ea62ef40f9501f5e8725caeb12783e024c8afbef3e606e1c416878c8e5f929c5f2'
        '29672d41e709c6b6fd9eb46814efb6bfc65c6f0161af988b2f073df835c9aec773850cb54c4aa22246c483651fb29e6adc76f48ff15232bb52ebe6697ed02683'
        'b7bdeb19d5d78c0b1a445ad71a2617051d79ed475239c10f5b080c27dde18929485ec7eefa046c49df5fb023591ff3fced25ca2de2acc90228bf31ab555df351'
        'e9a91e89319908f708558612df0c8451e5aaae36ff1c1c0db99cd98ebf9a507e276ff675247f2f47dd9bbb6447353dc510197d5ee706b16de55f0379767480fe'
        'ebb976cf2298d239b066dfb55bf7c3c41be5fe2a5c49fb5a9e42139fe4b46e5f15cd8ec4f72542ded12429cb00680bcf36c401bad4b25ec83c05b6f9a7f481bb'
        '11af11b37ca575df06836d0febd0c241b026994fbef840924533afe4517df27604c010c4af0f1df99c2aa4fdf3a0a51db88ca688e165b17054bf75c07ee2acc7'
        '2cc3f2af17d0763678f1f9c52e8da2b0156b8e483191a7ee4f29342470c8285febfdac3c965b47a32badf97edd6dcb6c20eb785cc708846efdbd61f0d2c0caa0'
        'e0babb217cfaae596e3e2056c94dc312e1c612699f3970c88ff94845d8c0f8076a72e5a3bd3488d4ff8c04260c3c193393b9203e45fa90d30544c05820776643'
        '2448eeee1fe5ed1d8bb8291df12df6b25d68b27cf67a8833903d678484d07924cd9f5b6d5d683728cef5573151ee64d12809af7c7613892e4dd1df05c4f93920'
        'e41ae2a5d16e11991294f361a37db1e60d421c87171f47afbfe693f7f813d13900f2701fd4437e3fa7b7a6061e233b39efefbbfc73a29b6cdcfbc42e7bce62e0'
        '60362b8b3258ffda56379db97f1e2d9c58aa65105ac695a92f263a21c33b5fba190f970245ade88807aa28374150a9ba99e93924e0e091a51985a9b1a037ed8a'
        '7979556b4ed18600e44e6d653ecdf6b3b8cde02761b24ce555236bc539e66ede57de01b26c5208c64daa344a549c9b0656b7cf178c67f9d84ec0ff34460e2303'
        '60f7b9b4a7c97d39a1fecefebae40cb3857bc1925999876f1e7d81ed0341786aad85e168422e62729efe0e9f539f2a0c1e331e1f797bcad51bb8234885740e11'
        'de866cb1b76d2281be6d3a240f377eb4181c9ed9f5826f6585e9089f57e6c057a4b6d61d580a8dc54f33544dfc66fad4ad3db08e6d336c34471cf014309b7430'
        '0b9f81fcdbe21e1e463069dac489f4c53d27a8a5d66f23dd35eac42519d9d7c5b751869079c6fb68084b2737c20e00411bb2087c9d3285136377f359b91269a1'
        'c11c2141aa24e8917a9ef2a62acdb5e1347b6c84079a6b7ce417551813021edb9dfb23457b50dd36f6ed47464735e6163dd1b9e0e25e3f357c4e2f3761195e60'
        'eb9a7e0d3bc2c03f0fc55b65e8e1dc764e07ef5a45424a940fccb786c4a6fdd903dacc1120a163fc05cd92d90f50b50d7872776c3b891c7c7ad43410302005e5'
        '96924332bcc3d028d4978b37b1e9bb3d144704cf6c21ebe83c9b2e69c9664f9b57481fff7290e530625c2f6022324bbe750271e3f284726a51dc88ebeac32d02'
        '61cb4aecec06c85895564d7a0941450a0eebfc40a1aba76d3dbb66244f50811d85bd9233f9cc3831b2b04797169489b16653d416a2dfe39fe9a1b37f652987b2'
        '3ae5084b6f5d29f8e5b25f1e36eb519d9b2f3337664faea80504e41ecdfd067d61c9508222da361d77d77cf9a16ed7399d7686e39b2f4449dea19afef7f160ef'
        'f559472f57e5034d17075a1de183b1dc6206139e50f93a62a64a47db285d8b886931ab64ea62f053e2c10601fc73680769b35a11b884f4707ce39e56eeb1c83b'
        '590ba77df6ae177a844dd876a2122493a8818f13eb8ccea36ff70f73016d66e81d4d6c0044bb65aaf3a8c45fc579db51ff2fcb624e47b0e86dfa9a845ab14e12'
        '336441275c65d3591a9e893e5c2dcb415af39acb0ca80eaf2fc542bd97e49ac9cf55c8db8239eb1b41053a2198520164383dd5ab8d72cd581c6fe757d0f26767'
        '5d8a59adfd20570d272e572f6e1146506ac524b897748112b95c92e7e841da8533db6ab90ab0b5bf3c1d0662caf28b44ca4e964590eb9930c0235486ca2ab0a0'
        '1cbf1cac43269433d20aa09ffd4f4786a7c7236c41dd386ef5969b7598a0c9513451896993e086a835cccebde7ada043bc200dd5ce88256a9023fb31ce72d599'
        'a9929cd4262966db923f64cd2c15ad45161f47e4e7fbb5ef4b9fd1d83cf8d648ee14fa311ed6468412b18e6be492d035b909aae1e3eafd3daa13737628107c47'
        '3d3ad4e96b0fe152c2746f3dc8f52da2d1f22b2a3f1adda87ced23cce6b9b126201cb5421714e260e56208e59fb2e2d33ceef055e2a61842a52865c889b7cad6'
        '16c64daa2339cf2cea91203b0e158e94dfb8d8ad2f64c7aad8fef39efb6327582fbc50e92cfdce86144b2c5bb26f4ed9d91bb7e58cef1e64935ca61786641dd9'
        'b00aae2362aeabbcf4d70c32f0996828b7ec0a94da5d3216456ac0b8533fddb9d7f136c39bfb78ded70fc02b967f912c894ad67dd2d1b57c3adadb7502be7564')

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
         '0013-FROMLIST-PCI-loongson-Override-PCIe-bridge-supported.patch'
         '0014-FROMLIST-loongarch-retrieve-CPU-package-ID-from-PPTT.patch'
         '0015-BACKPORT-FROMLIST-ACPI-PCI-check-if-the-root-io-spac.patch'
         '0016-FROMLIST-kbuild-install-extmod-build-do-not-exclude-.patch'
         '0017-BACKPORT-FROMLIST-LoongArch-detect-and-disable-sc.q-.patch'
         '0018-FROMLIST-i2c-ls2x-Add-clocks-property-parsing-and-ad.patch'
         '0019-FROMLIST-iwlwifi-add-new-pci-id-for-6235.patch'
         '0020-FROMLIST-LoongArch-KVM-Fix-FPU-register-width-issue-.patch'
         '0021-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
         '0022-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
         '0023-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
         '0024-LOONGSON-cpufreq-loongson3-SMC-boost-test.patch'
         '0025-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch'
         '0026-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch'
         '0027-AOSCOS-loongarch-re-introduce-add_numamem_region-ini.patch'
         '0028-AOSCOS-loongarch-basic-boot-support-for-legacy-firmw.patch'
         '0029-AOSCOS-loongarch-parse-BPI-data-and-add-memory-mappi.patch'
         '0030-AOSCOS-loongarch-add-MADT-ACPI-table-conversion.patch'
         '0031-AOSCOS-loongarch-correct-missing-offset-of-PCI-root-.patch'
         '0032-AOSCOS-loongarch-fix-missing-dependency-info-in-DSDT.patch'
         '0033-AOSCOS-loongarch-fix-DMA-address-offset.patch'
         '0034-AOSCOS-loongarch-fix-HT_RX_INT_TRANS-register.patch'
         '0035-AOSCOS-arch-loongarch-add-la_ow_syscall-as-in-tree-m.patch'
         '0036-AOSCOS-la_ow_syscall-add-kconfig-for-module.patch'
         '0037-AOSCOS-Revert-rcu-Fix-rcu_barrier-VS-post-CPUHP_TEAR.patch'
         '0038-AOSCOS-drm-loongson-add-ls7a1000_support-module-para.patch'
         '0039-AOSCOS-drm-amdgpu-disable-ABM-Adaptive-Backlight-Man.patch'
         '0040-AOSCOS-kvm-disable-enable_virt_at_load-by-default.patch'
         '0041-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
         '0042-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
         '0043-AOSCOS-USB-core-only-enable-root_hub-wakeup-on-MACH_.patch'
         '0044-FROMLIST-gpio-loongson-64bit-Add-back-the-support-fo.patch'
         '0045-AOSCOS-ACPI-scan-Add-pwm_lookup_entry-for-PWM3-on-LS.patch'
         '0046-CSMANTLE-Revert-FROMLIST-rust-generate-a-fatal-error.patch'
         '0047-AOSCOS-drm-ttm-fix-incorrect-caching-type-caused-by-.patch'
         '0048-BORE-linux7.1-rc1-bore-6.6.3.patch'
         '0049-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
)
# vim:set ts=8 sts=2 sw=2 et:
