# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=6.18.9.arch0
pkgrel=1
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
  # FIXME: -arch0 packages don't have official patch list from Arch.
  # We track patches together as *.patch files.
  #$url/releases/download/$_srctag/linux-$_srctag.patch.zst{,.sig}
  config  # the main kernel config file
)
validpgpkeys=(
  ABAF11C65A2970B130ABE3C479BE3E4300411886  # Linus Torvalds
  647F28654894E3BD457199BE38DBBDC86092693E  # Greg Kroah-Hartman
  83BC8889351B5DEBBB68416EB8AC08600F108CDF  # Jan Alexander Steffens (heftig)
)
# https://www.kernel.org/pub/linux/kernel/v6.x/sha256sums.asc
sha256sums=('030115ff8fb4cb536d8449dc40ebc3e314e86ba1b316a6ae21091a11cc930578'
            'SKIP'
            '505d823490e964e66ebe5889a3701347b4e4e2faf1772b3964f0360a176eadf8'
            '60e26da620d96a7c0fad031d25b11b7d02a809d558b819bef2b10575f96e8195'
            '9825746de2f73f2f449c84447e84a1ecc6e260f29bc6de5af7d19bf8deec90da'
            'ba0f949ea8aa854007729f5f586ab41228f41bfb895f1f2ce38eb7da10bb61dd'
            'dacac94615591cff4dbd722b4f053cc152952ba5fedd44b64866c8f309aa0664'
            '668b92803b74fa13c0556ca43eacc3ea4eb1fec25ec02362da505ef5019fbc17'
            'a275d5deb91408a59df3a8b65afccb4bb68b458e3517f7e3335d3b1206281d4c'
            '359b53ce4298b0302fb20067c74b5f476ecc2c80a98e9e3c8dae3e0908478126'
            '0cd02400ea380df56270526856689632f360f2a612095378f46031e616e713f9'
            'd9486c08e64a23affa57e14ab1dc542a012068822a0f3ce252dd56d8567c4409'
            'd2af86d94f46a5e4a83b0ce25569446d11edf200a72561299e23d74714188d07'
            'ebb13109a7bd799914f5edb08b54c50f2f3f8293259568600825c21d41962e08'
            'dc75c03709bc96fa912ee69080b4ee8824b6e0768215adc7147b4a2b07b987af'
            '9f3b29ceb8d249bf03c9456ad86c396633862ee9ebf54baf60c60ae62a3ad23f'
            'e6ae120f885527e5f58107092456a0f69bc922e890f8bf13daf4cbe065328a58'
            '1de05e473b614ecdeb9ce9f4c35090129b51a8ec99fbddcb9691da84912a517f'
            '9bec95cc51f0b220b956616682c8889df727777dd1c6ae9e3c796b9b90336153'
            '9dfe6c34e451b47bacbe6569c103817434dd9b835060ab916f08f623635e2594'
            'df70b4f2d7385174abc1f2d855bc4124e300a65c38865da594fb17c57af0f8b8'
            '08c43fa37be7a9e4a0bf09ea649792bbb397c2da8c25295e2ea338c07e41ac9c'
            'cf23d26d09639ee3afa500b4c90e153026f6aaf043f6bdc7cfcfa02ca016a847'
            '07aa019eb3877c094e3c2b95d258a5a223f1d5b2b51cb643e9e7b09ebc762a9b'
            'c4d7bbaea45c5506f560f2278da42947f68dcfcc24aacff7262b71a88a08afe7'
            '2b996c6b97d859c69068f77deb7f417741f4bf4d7fae69d2ac42e1272dbf43da'
            '52146b520f632cff2d0c16d438b1114e8652cde64e7b9979ff4b2ba1b69765fc'
            'd2a561ee93a8c904cdb0d8dca1e4971160424989db3d65ee20d092fb0a43e80f'
            '8e902ec09cf5ea75bee5d0a6295d60e988bbd110c156e11a3938e7e7b8da4dd5'
            '1e83b36f91dc32462c661fb56f225eb6e7581571700c39564ef63b8bda276788'
            '7eab2afe05350c8f3662d448891581f6d49de7aa9d6e9b53959c9b4b70816ba6'
            'fe3f6262828e70b7c4b3282b576384a144b3e5cf1ffe0a233602584b0833111d'
            'ed4e4c5a3b5bb6acea766f6e061428992bd13a575b1d85a937eb0553872a7d99'
            'f90363fbc2017a4eaf1fe14b7edbddd002e094deb8fb493fe39414f72497287d'
            'f0a96baf870a5fe139bed8a7ec8d6b2aef7866db3da96f278d05399e0ae4924d'
            '7099b2675496b4d64576df1f8bec4a6630f1c655ff4b14b3a490fda2b034814f'
            'd3fda32cc2db31b6a4abd4878978bf3dbcf6237377d2e21d78142b393c566dd9'
            '6370829580d337a47d19f5022494ea013bf15beb599c5988841cfa98ec254bf7'
            '24b7ac43caf3f0d845712f5e1a0b35f55fc52be1a20df8f89f225edcbf48e1b1'
            '5b94646772b8fa019cd0a4c91d426058bc4891d1c6ddabd76de0abf7b37ad0e0'
            'cf22dc39df0c91482a0ef0a15306af71f7a3f26ee6dcd32e5577f8f668d8ecee')
b2sums=('9aed902e41583597cb7595efe77504630a621993d20f89365a93cf2ea4d9790a6361d93cbb7fd7603881a4f82b76394b7e12fb4e4a88c9fedb2d63d64a9d49d3'
        'SKIP'
        'f31d83e1e10bb901d0d25c1db0ad2844584ff1014c8bf36f342fcf1999f41e5e2d5ddfa20a5a23d4626c6b35005c7e01ebe8ae7f3de3d4b61a189a49add3a158'
        'b8c684b5baf73e687d8bb3379a757ec25d788b512b01fc10fc601930f087c7d411d338026ace88df603b201f512ce57bff28a2b646ddbf9e8ed9f65fba10681d'
        '61c63559769e92b49d85c6bc081865cea97176ddd05648283cd5e83b863164a4c0e18639efce6dcdfacf7ba06adf457668bd8d79b84b16415455c604aae1502c'
        '7bfb6f0f6d45a4d0c3e941116ccb1744765ddafa37a1aeb553cfd26eda8fb13979870c5f8e1919db347bfccf3760e2f7c2952464d8e02622260f9c5e4449e6ce'
        'd20e4278e2a0aef454225f1145b9baabc7e1faa06f5d97f0f7035db8cb9e5144ff97136e91b9d7a9efb2fb22a7c6fb3d6bf2bf8f4adf779866566388f51fe2ed'
        'a05afc38ebf89afe33f6f604e5e0a6fdf5d0507beada0609a2742635ea044d20bb7250b1bedc82668148509aa791d1a1048111e97c2a136c2e8e34f729524088'
        '7d85e4cec114a40966dbb899b67bb8558f46e79c1b73f8e8a59460086d8d23e420e8d4221507ef7e0be7327c8f0803e4a8c048c90b6b64064e6ada037ebc84de'
        'a32fe12a609ffc0c23ab00b3253271af57e70de53210eec8bdaa989fc9eb83ca755da776a1af97191a82d7bd974515bced48d350c6e26aff3f1f53d64be06041'
        '2faefccef81b5afdb68e820773c66b8eb9a778d7a67899db1eab8660cc0772513e161e60a9ba79ce3f25af552f2c6c47a8ad29f3e4da93f89427dc6c894c989d'
        '1bd6c5eda3fce4f9e198beb05eaa2e3586dfa4e0be880ac05df1eb2b35a853c18c5da7aac3349227663e107b57b6ccb5623fbaf9099218844b0fafbbf9323e87'
        '6818f377157875c1374df8950aeeade5dbde9bf1069e5b73a8cea8a010577ebd3797b473dbee77597bd69f236ec4cc464a98c4c7741e3e45998fc232d3418fae'
        '343b005b9d0179f341d3d4557ec5e27caa9f61c7f8c3b68814ec49914b86e49b99aef1df2388d80c86c8bdfa58dc6d5a6b725ccb6001469d5b1b5da5c6578cc9'
        '156c53ce327fd54b02acee555abf61691811c710185fbc8ce98f93c87358325c78657a06ddd9edb0b4bee7a24644acd6c6e1f0d4eafe2e14a5883baf179f9741'
        '0ad6927d6a84e496b1db3acd59909564c7fe99a1c48b7862b32dd89e66c7695cd12e85763fb12f38cfbd2bf3c190525d59ffcda061395d2ed0bd8328ae6463a4'
        'c798a1cd8ddab59f854d722eab4f22a8658d22bc7a54ad331d6712fff68bc57de6e91f85744096ffeb20f95ea31b435ebf29f1b530591b1975076ff9efc755c5'
        '2c0ae3dee4b881b97dee7a7a52004f5ac9ffa33c2a8417d44feb6cce5376a4d666d36145a483088dffd679839283ff4ca6e76d6c1ed84ba68430b817c99ddcdd'
        '6df937ec736424179d0d31b1ff9bedf53905880ea45baa748e157964e3a31055d4ebb59095e22412d403b8d0ab38d229aef588bd18d222d94b32d8d8e826bd0e'
        'dd84cf9cfea2b8692aab918dcd162a9280e731c95a9d42f35c61f0ce0be60aca3022e0d759e3a054587c9bafb56bfebecd9d050f3bc82a6ca79a2b4feedf8481'
        '3ef6525ee6295344cd7e1f86a6eb285b2314b7c6c2566101c4f4707db3533c2ddf0f9fdf9052f97e92974f667935420650b34dfc52d0965a8a14105dc9777618'
        '29d2fc1aa4d6a541761377fbab4e7e667022806f7d28a8cbb24f03b107c0a5422c0d7852f8699addf1accce9aa8e127a6b60fd1b9c97f0538b4e3f93171f9345'
        '760783cf4c2742e417d8e467654b65688711f7b18bd9205c452a0991ce270dc7354064846b6404eafbf5ae17fcdb9231674fe3d6485cd94a2530394c4196fc14'
        '2c0503a957e6a12038e1c539adfcaabe8fb81aea79b28f0f46c4a46fcf67815695fcd3ad1730ea608d91856bf1f2c2a3fe4f4180eed191b80d94c0a2e1f60ed6'
        '77e6d760fc4d8a690fed7ccef3f31453f82a06db414def9923850bd8807a11c6a2cceb6de01c49a083633db55eae30a970368357f9da274fddd7fe44567ed614'
        'e44ee83ea2cea94afd573f3c7fe84243e9932b9d07322b5c1819443aad4c9e570822fa62c9d53e4dc9eb1f2cc043992c2957fc11a925e7c43ac7b51e7b28a823'
        '6763fd027ed986dd8c8ff07ed9da5f599a4f599a1e184ff80375708a3be3602a3b15f28caf39b7e6808538e4be8846c4841abcd7309a57c44ce01c05c337e1a4'
        '758261cb51d484d815f13eaa93065e6c2e31457331f94eb303c351470a528f2702ae2ec23bc11e92a316c0cdbc9bb3b584f82d44c0b80b1c44d790fc6a403be2'
        '771f00db2745d37ba209e1fd68254da33af8e9bbfdd1056f825ec129d150938882e593b6978df1cfdf6e499a6b239e790d1cdcc534e349913aace394c3de092b'
        'cc5f7bbd9a956c701dc2c689e15fbeecc8dab4f2e013fc679103be1e8572ac4db7bb081fd1df37317660f2f4070d579cde41303379cb6a309eb5357ba20f2691'
        '229c8791ec4705190b2d8a74abc4182b7388481297636d2aaf86e96c1d003e5db1861a44046e5b00e6533b15c68b24d8903f4a0c90827683309839af242c1d71'
        'f06e306ab214aac9d8d064f10dabd88f16c14c87bef4d2f31ddc78d0a0c7a3265bb5756567358e71a303b47a83f0b1df2c80885f0e7d1484ca9074c9d73d6029'
        'f76906fe12d737339edd390b439e35848d0cecfc3f9113b9f94d795bf203bbbda934b1409e63ccfd497abed5a0708b9d562bc9435d732a840685efb9ba440906'
        '401eab0f3fbf5748aaae32f3d4e2fe76d0428f0648b7ee78e8bbce6a2281d946bdebcdf6cde662ec7b17a9d703c3d36af67bff571035948ec537db4359ebde75'
        'aaef70af7c31aa40ff3348a03c5d2242dc241c5309eb22c8d393e8220f50afe96c9aede3a804d855aa71eafcc4bec734fed5c8a98c580d6d7c55ad31e4cbf71c'
        'f96e4c920ff2ee23b54401b9cfc06c6014d5c60c6c9ff5f09bd1eb2ae78ac1b895823e524829956e154eddffba7f08f276dd4773d4d56ebab420fcac89378854'
        '6417f7b7118c7e310d2683be7630829c028c93b14440b7fc8987ee6aec72bd1710cf31535928a882bd37c4bec9090cdeec7f7daee2cd6a2353624bd5090e207e'
        'a215ba2eb810eef5dbf23e2da5b08ffb202754f5fb542e89446c38d1b1a9c0cfe507757074d401d5f45c6850887416f041166e5c9120e57b3bacb9f4ed727d6a'
        'ff1ab11c680b2a4fac8e10c5d8aa2f3d3a3ab625d107923e85b80181c964b4952753201b0cb3b5d4c41b7b6970f2eea9e5a9cf59124e35bba87a73c28398ccc9'
        '47a773159cc7ef4b5c9080f45b17e665c5e5797ef77f7e4059de4783b26511ad7782e763a5302f6c70ee813741b4fbb82943324a21f10b9fd818ae7532fb04a8'
        '64392a2284d6967d1673d64b4bd56061a276c746fd1afc675ce64622f686f2cadadb37004356d41ff7ebbf152bceeddfc01337d6830a419cd04d1264b155266a')

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
         "0001-drm-amdgpu-avoid-memory-allocation-in-the-critical-c.patch"
         "0002-drm-amdgpu-use-GFP_ATOMIC-instead-of-NOWAIT-in-the-c.patch"
         "0003-rust_binder-correctly-handle-FDA-objects-of-length-z.patch"
         "0004-drm-amd-display-Add-an-hdmi_hpd_debounce_delay_ms-mo.patch"
         "0005-Arch-Linux-kernel-v6.18.9-arch0.patch"
         "0006-LOONGSON-irqchip-loongson-eiointc-Improve-IRQ-affini.patch"
         "0007-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch"
         "0008-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch"
         "0009-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch"
         "0010-LOONGSON-drm-ast-Restore-vaddr-field-to-struct-ast_p.patch"
         "0011-LOONGSON-drm-ast-Support-both-SHMEM-helper-and-VRAM-.patch"
         "0012-BACKPORT-FROMLIST-drm-Makefile-Move-tiny-drivers-bef.patch"
         "0013-FROMLIST-drm-radeon-Call-mmiowb-at-the-end-of-radeon.patch"
         "0014-FROMLIST-LoongArch-Update-the-flush-cache-policy.patch"
         "0015-FROMLIST-LoongArch-dts-Add-uart-new-compatible-strin.patch"
         "0016-FROMLIST-serial-8250-Add-Loongson-uart-driver-suppor.patch"
         "0017-FROMLIST-dt-bindings-serial-8250-Add-Loongson-uart-c.patch"
         "0018-BACKPORT-FROMLIST-drm-xe-bo-fix-alignment-with-non-4.patch"
         "0019-BACKPORT-FROMLIST-drm-xe-guc-use-SZ_4K-for-alignment.patch"
         "0020-BACKPORT-FROMLIST-drm-xe-regs-fix-RING_CTL_SIZE-size.patch"
         "0021-FROMLIST-drm-xe-use-4K-alignment-for-cursor-jumps.patch"
         "0022-FROMLIST-drm-xe-query-use-PAGE_SIZE-as-the-minimum-p.patch"
         "0023-FROMLIST-PCI-Prevent-LS7A-Bus-Master-clearing-on-kex.patch"
         "0024-FROMLIST-PCI-Use-local_pci_probe-when-best-selected-.patch"
         "0025-FROMLIST-LoongArch-KVM-Get-VM-PMU-capability-from-HW.patch"
         "0026-FROMLIST-PCI-Release-BAR0-of-an-integrated-bridge-to.patch"
         "0027-FROMLIST-mailmap-map-all-Icenowy-Zheng-s-mail-addres.patch"
         "0028-BACKPORT-FROMLIST-loongarch-wire-up-memfd_secret-sys.patch"
         "0029-ANOLIS-LoongArch-adjust-the-calc-method-of-number-of.patch"
         "0030-AOSCOS-drm-amdgpu-use-amdgpu-by-default-for-si-cik-d.patch"
         "0031-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch"
         "0032-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch"
         "0033-FROMLIST-PCI-loongson-Override-PCIe-bridge-supported.patch"
         "0034-FROMLIST-loongarch-retrieve-CPU-package-ID-from-PPTT.patch"
         "0035-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch"
         "0036-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch"
         "0037-AOSCOS-ast-Drop-drm_gem_vram_-un-pin-calls.patch"
)

# vim:set ts=8 sts=2 sw=2 et:
