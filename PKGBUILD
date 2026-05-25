# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.0.10.arch1
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
b2sums=('08dc26e2247186fbfee32ee3251174f8a2e68c6ed6118c0713cb87bb66d427c85b6ae2367af053b158d9ad0d9aaf0846bdebddf84c30558fec89e68ba0dc0957'
        'SKIP'
        '0701e826f811a79123f89c0d034cb753d3a6237ee5e387c8c927efc1114dbeac6ef095e88eedecf18b9d69fcefa605b2425ffb119c5e40026e388464f75c350e'
        'SKIP'
        'dafee1f25d231199834869a5ce76a85eebb3c1ceac86f604270e93a40a22f29bcf797822481aff5aa5020c12359b9ad87ad8e0d36727166522510a07539d69d4'
        '652069e50060a3d84530f004f7064d98d6ac9bb02e690a3510d092d0df17598c9b3d564ae07fdb0dbbecc68d2d12d58c4c78c02cc08fbcbb8c01ba6e6256d922'
        'e31028c4d808982740991d450b7dfd77e36bfbb620205ee7a34b3c6937dcf75202d77a136e58ffaa325995d929f8a1095b6f6467992174d2b9c5fad034eee418'
        'fa656e5f44c069d93baafd37e4a947ca90aa9805c391b963d5ad2cfee99f75e620d6c86587a1f07fb3640a94f6f84917626cea5e901ef0db00da2c275630645a'
        'f4ac794ececa60203cac7a931b251a76de01ebaecfacadb42eb66df056a9fadc8c40dc4862b79e249f48653c32f24fe10c685166bcec8334347ea26e98f79a18'
        '7f3687e352b144f99cfaaa2c284c140b9fb62d62b08143eadd670e2d7b3c5995cf98bb1665d859181263621035234bb0b6fa34212cf6f839cc2c046f3d3f939e'
        '0b9a7b8f9158cef64111804f589ab839e772fe886cb51420bb5ef6980a1ab219eea172f6af6ca822c6dcb9cf3616c4dceb9a16591341e988605d139de7b44a0f'
        '386a7942450f432e4eee51ef0ff44c8f8f0695e6ff8d9dabe75b4ac05357446e15872578408f2449675f3697375c0e242bdb4514c4e426dad30f239bcff2054c'
        'bec6dbddd78304436442396e30206bee07ee9a386142ddfce61048cc24390eddf171fc4ba36e2fe2e487f2dce3162562eabc1bd8472fd86f5d97f04949a75cab'
        'e69e45f49d8aa3c47e367e5b3e5b6d37cf1f6b7962283a06ac5690cad18f64e15ab262521612fe7254f8429639cd656a897b8352540ec664aad35e744fef2b97'
        '7286568edb4f21df7728ce04bb082a76b1e7b1a19e3baf552dfdb792a9598b4e61bac577bfcd6b2371f23d614215be6b38e9260bf3c566ea15dc31f1b0cf2050'
        'eb7034d8154f65a728353c74e5462ef68cd043851c6718a7a3713348a171658cd013b0079b98c9c83b5a230d9363ce65f51c2230e69ab801ceb8366eccb3c32f'
        'a785f11c8dfcc302195fb2b57b10647fc498f07bbe9d9e886c2665c954362e2bb06d0c3919769a43573ebcbe9bb2de99e3da1ef21f7ff2d2c22d9930732a629f'
        'b8378d330e3e44821f3e87cba37980c33af29470db6a68c4e6701233a4a54ede6001c8d218d2af2c2be37481b47e206ec62d58394e2c3f5fde896ad604c81173'
        '962f63737964e012651dcf0f0fe21711915d8d595d08ce7c0290a964b8e65b19b1e0045b37620f04914f5565439ad5a38da7769981cb5079c34210a6a7cedc51'
        'acb7e02aacd1cf33e703b4ac88ebf04d161f86c8b20373e69ed8efda83cef96543b6ab0942f4d89abd337d14c951e85365ac80a46ee336da177ae34f1a6ca9c2'
        'a753a2cae8e897dd22e765c18aa0f0b531af02059181bdb6c99d1041853d70d362f9e3c9e76d00b9d8090be30e3a7895cb0c6fb86a6c14cea99416d47787431a'
        '46d53e8ccbc79c43369c41d571b303c2745566a784513d44e890dff19fdcaadb2a4ea5acb32bf123e5b2e0a2cca76a25b450c7d831452c9bfaccd0b9f30a7a41'
        'fb9c4e71da8ef6420fab2087ffa1d8e04e6623b9e1a3d93836439fa048284cf954e41ba9b99dde468f89915f6031b3a584adc3c51dd47461d2eb92b8666c8764'
        'ced8edba63e29001703a39e013461e5ebd9cad522407d0f1cc5acbb2dbd5acea9cb92c35012b52472906a7c7d9257deab01adb44da77f80cdca446aa2c0af0ac'
        '685a5816bfe1aa65d64da39fd10edd7434e8e339bc3f094069b19c72d579efab621626d3b31f15d0f08a5f9686859564ba78583759d7a6502fb88ca15f866e49'
        'a0a7e4e4cb750961b4645fda40eb0a9a649bfa51d28d2f8cd17a3ffd1c8cf5d3d0f05c7d34d72e97f5d804a42e769437b5ce406f62c6945fcff458350ecef4b1'
        'bc102542531fcca6f9df876c1ca4cc105e7fa3983048b27a108d1defe9ef2ed46b368cbe9bbfffaa766c685c47d1a4290d7948be7c0ec12c2c3c2f89797aeef1'
        '60ae53228ce40ca2c8288f8b5cc4fec1cef6642f95773ad35d83d897df4506536bae1f226ea6ae96496a86eef95e40b53590d8ad9e0c30f056ba459832c6bf74'
        '72bada703a01a14232a1716ba968c3f5e2f1d83ada22e878895bed8ce159e2a2257fd04b2f7644272774549a13677ae4120a4c7b9e33b17b7e03e8259b89eb78'
        'c22f160ad34e4ec9abcf1c9cd5859063b77b059af514cd7893deaaf83276ab7eee44147d5d2ca814c3f0c8e9b4e58f4f7236d6636528a4758f27cda9d6608306'
        '9d498a763b98ba800853abc12131a4a5eb4a5fd0a12e518176c0b43b0a9b18822b3e4436e623b146785eb257be467ca5d29901c7d6bd5e7126946e72378a0317'
        'eaf7a15ebc923d89cc40e72e424d1b9ddbffe6a8383139334ad145d0c5bc9023ef0958f9c9afe04b3c3f534369945816bc2c9067aa8b33cca6fc65edc08b2dd7'
        '267bcd10d16728b6583db3b17e297110656bf8ef8ce9d17bb3d88aec61624ab0362957741f0f682cf4d143bdd60eda2c45d1a0af53fade1edbef9c1955884463'
        'f1b2f8baccb796d1ce0533f07eb66e15ffab429024240255231be046db753562460b3623dd310ba3cc2331891a69a42a0154b228c8b4f4717d85e970682b381b'
        'b98109b10b696c663fbe85aee4e0c4cd7770ea8f124b0d1553ed30b9b05612dee4a9bd5de8899575afa2edcdf3c27be78329740e751fc49046b46ee2e625f9b3'
        'c3a37d6f0bbcbf12de5ec19677b03610dc00aefff1eff3aba1fb246a43863f0bc3b72f624ec93e2486b61608218a31074bb68524e8f01ed32e222ca994f96109'
        '90b23afb57a1f964ce56b2079ec9287a01f1742b1bfe6206ebb8258a7dca98272fe2d960085170021fa97054d4e1cf444cc1fbf5d813dfe19f3eff485fb5d040'
        'bfc62699515e8c127719efda22389f62abbde94cccb89852d5faaab04dff53698e6f079a2ad35ca8e3468be2f945883067311c02e1522221d1237bdc0d01d797'
        '5c736f4391b167e42d62279fee16abb66d970a01a09c2e8c83592251c12a6d6ca1d4b71816d83a758a8744177bb96a3986c99a1d24195a987b636fbf3065bc66'
        'b4926d33e3160347d7d8572ef9589ecff3c3ace084d99f03ef5d5dd4157be683b48f014a0b31baa3642fe43521229904c6dac1ea5fa8a8da0f6626eb8a574c10'
        'eb6ecf165bbe7d742f2d8713054c921edc5ffc8b0b38382057b2132e25d7e9c481f2cd2cef95e8b11057ce5f1b5292d26e4c1289d313263df371b250eae58f4a'
        '2a2ca2ee44e5cdfdc2b9a8cf4e5e58041d1973204679db01307d64432e35498b1433e9f43002b3d2522d4d4555097b133ffdcdc0be504b906e74e8bfca72bdb6'
        'd218f503cd33719b8c0973d2843e6d35cbbbcc3c8c04ed232f198041bf5cce854e22de61101de5c1b9363c91100c8cec77c80b0f8a65d486cfa118471bf1759b'
        '7183dcc69181727b9cce08b0bb357fbb0bee32d84d7032c6b69ca0092242bd21b99dfda4d16993a4d230ac50aa7d352d306fbe3eb72131749f7b87523f4b507b'
        'fd1a6de6f2256bbd783cc763f068446d64124a61a52015bcdfc2546f5c540cb42cb2a4e4cec58c3fc43cc865271eadba3b9ab289b09c35d1a715ed0a60d88042'
        '7ed053f4f6a9c6bfe47ace4b421395c95b5a3529957b46f512fad6b84ad369dadc1727526096a3ce281f78b43e6614bfa8e33a99d3b383d906c53a719b5c8f56'
        '9edba2f34d4f4e384a5268f59dea774e21081572189d62857394912beb8410add826efcc0933f1cecb06214a355646b570c45e9ac22e9ca644a40c42aff06869'
        '33bf079881ad5eca41f663b81350dfad4e027e1acd260d40de0f8d75a1c07458fb966d694d508ec8561fd758c35ac5075b13b7b88ecd9f33980619409e98f516'
        '30aab590038638695cb6a669703ce4eeed04760bd8b7a81815344864623c8348fa0b70d53c313246857f00962997831e55e43c9cdab84f31f1d12984ed6d1313'
        'df25124bb97fc38543fe8ef00b834702626406012c7c622f1659ce83e32eb267a64c398f7f30775a90a5a716f91987efb9a1651155af1f774d7eb6792f6bb4fb'
        'e4e2d008990377c795412db827617f0f1d0385031e62469d49714eb26f49baf37507663455558d04c9fdb7da7cda7e7f3660fbc7f74f304aba7cdc2d0abe92b8'
        'a0805a4e9c9788ae8101f3f947e84ac967e74a472674439aa9bf5705677945154746bab1ff7ddf9d4535877b16e8922d8bd94bff68ce6864ac2439a74bade71b'
        '64729ec354160742d68ae1f866cb97e891e15d5ad792dbe5b4272f2b7efac3a88f330ca41f3285acdce15c5e5190d9b92e66eb6323e75571693aeccaa429410e'
        'b239f6d57a30261201930d225be1b9a3c4731add70d65b2865166f02a6dc0313623253d14ae487c2e695c6694ed22861162761cc396040e4bf5c9b0143c75314'
        'b8e5a922a000a09375ab6917a16092d81da1fb394b8bfdcf9b3f55fb94413df82c462d12f4b9464d423fd428ef7a174f767628055303fe5283974074bd267e5a'
        'cfa43389b8c589adf5df45e8eed46cc669367ca06aa0da5d00a5296ebd3da77f5b5a008702c9fec53034c06950d04d5d49772396ad56f16ebec72e919c0f6ab1'
        'b8b2781b032359e34d7e579144c3c92371e0b731137d3a25cb913cfa071f2fdfe0c810184c1e924c10ca697fe29cdd39e72e244a0c97ff15dd92d63bfa6aee98'
        'a9b87945dc7210977fc8aeccf8ddbbe18b021471d7aea12458aec84d34a02800f5831ffc30734b83799f69929666373924c0d65c45b2cbbe08f0f6da61678bc2'
        'deccfb245362567502471c490318287174ac8113b6bd646f0e6dce159a58142250314615c64bc0ddb379174ad3950c7a2332c08f322d9c9f45aeb8743ca624cb'
        '1d84320f11e7dbdb798c7a7a2dc9fdf741b15e746a51e3d0eea15658f5ae0b6cb3ed4251d6e89875c56422613c65deca8696ee1609bf788d46b6219a81c3cce5'
        'bfb679acf35544b96302082748f8d75548c1a3e86acc7271446ca51db970b82a285259751d0008f9ef8adcd94e135442797fe80a41189cca78fe299a2f04a87e'
        'f4f04e07fce1d3e6c513e3c6511e4e63ed9e3a3ef2cba3ed8e9b2d1175e93ef0b30d5428b16f68185faf247fdffc60f359915728fcd288ae8678182389e403e0'
        '3a6b601354376dba67e8fe3bf1a4516f2616732eb94d7b084c5252a2ed3f7c96bc918e2192e8b8bbc3006262e837ac8abb43b855dd79aab5c8205f9b81b549bd'
        'dfee1293c12f1632b9f194b0271fd2ec1d5854fbef92b791f2d342155f0082b18c8d61e807f4b5a778875b05674e626b1f6756b166de85fa0b7fa670888bf69b'
        '32c36dfccbe95ede1a784ba448ab704d82a56020f02adb4ad63cfc1aa2de5ff3e7564d952722d1e9d4a929709e5255898241f6f5cc4a483beb6edfa5caf8f40b'
        'e8f5ac1c3145baf53b4b7c36f93674aec740c3afe2ec4ecf4518ac63a0181716a13cad52256df2da0626a9d6d3f42fcf4a18f7f64228a328265511c91727bb93'
        '25c4401fcf92d53cd55cb1201390dbaf4f274fcfc200bf0e40066ec8b70701da90ba249a5430e75cf6d1fc0fb6a30b18940d76ee5e635ceedc9df57b89ffe484'
        'bba0527efe330c879819c4eda1de22e0a57ba635a3d427af67da96383445c94f91a3c6d89bb17232e7588d46f2d562c4e25a334f95beebc65505f1ca7424c8b5'
        '25779ae18c9db7d22eea10d20a89bd4fe1ab6bc354b16a6604c75234f27e3e49dcfdd5a52175474e35d6102192d1f2e976b1e487c902d8ecb26eb42947238901'
        '7ed3e8928b254ab3192f9a447d440c561339374ea0b46b65c4f67a45be7e90e289cfb9977cac59afaa366053de25b1495e5237d4407dff4d04b1a5a7d24fc421'
        '5afca77e4f065c5dc1add8cd16b1f495661163ed9897b403be142172ddad92bf8dd0b20ec2c409555d3f66912834e654ce3e3fd5e688c845360ab5a8646de15c'
        '10642deb1980d47b8a014135fb4fd5a60c877935d27f72749c5785225f1bde49c3dd6003124c328dbe9994d274f2db168d966a73c6a942870af20aae85baa6f3'
        '950c7d7da8094d9b93bd86738b848ecce12d95105c057b2920f5abd5a999c3cc94419bf5ec2bb8fefc0142f2bdf4c866a54a758114dc959e051de2ff6ac2c7e5')

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
         '0001-UPSTREAM-LoongArch-Override-arch_dynirq_lower_bound-.patch'
         '0002-UPSTREAM-dt-bindings-interrupt-controller-Add-LS7A-P.patch'
         '0003-BACKPORT-FROMLIST-drm-Makefile-Move-tiny-drivers-bef.patch'
         '0004-FROMLIST-drm-radeon-Call-mmiowb-at-the-end-of-radeon.patch'
         '0005-FROMLIST-LoongArch-Update-the-flush-cache-policy.patch'
         '0006-FROMLIST-USB-core-Enable-root_hub-s-remote-wakeup-fo.patch'
         '0007-FROMLIST-scsi-Bypass-certain-SCSI-commands-on-disks-.patch'
         '0008-FROMLIST-PCI-Prevent-LS7A-Bus-Master-clearing-on-kex.patch'
         '0009-FROMLIST-RFC-drm-amdkfd-disable-HSA_AMD_SVM-on-Loong.patch'
         '0010-BACKPORT-FROMLIST-drm-ttm-save-the-device-s-DMA-cohe.patch'
         '0011-BACKPORT-FROMLIST-drm-ttm-downgrade-cached-to-write_.patch'
         '0012-FROMLIST-PCI-Release-BAR0-of-an-integrated-bridge-to.patch'
         '0013-FROMLIST-rust-export-BINDGEN_TARGET-from-a-separate-.patch'
         '0014-FROMLIST-rust-generate-a-fatal-error-if-BINDGEN_TARG.patch'
         '0015-FROMLIST-rust-add-a-Kconfig-function-to-test-for-sup.patch'
         '0016-FROMLIST-PCI-loongson-Override-PCIe-bridge-supported.patch'
         '0017-FROMLIST-loongarch-retrieve-CPU-package-ID-from-PPTT.patch'
         '0018-BACKPORT-FROMLIST-ACPI-PCI-check-if-the-root-io-spac.patch'
         '0019-FROMLIST-kbuild-install-extmod-build-do-not-exclude-.patch'
         '0020-FROMLIST-LoongArch-improve-logging-of-disabling-KASL.patch'
         '0021-FROMLIST-LoongArch-Add-flush_icache_all-local_flush_.patch'
         '0022-FROMLIST-LoongArch-Batch-icache-maintenance-for-jump.patch'
         '0023-FROMLIST-LoongArch-KVM-Add-DMSINTC-device-support.patch'
         '0024-FROMLIST-LoongArch-KVM-Add-dmsintc-inject-msi-to-the.patch'
         '0025-FROMLIST-LoongArch-detect-and-disable-sc.q-if-errati.patch'
         '0026-FROMLIST-ACPI-Enable-FPDT-on-LoongArch.patch'
         '0027-FROMLIST-LoongArch-add-spectre-boundry-for-syscall-d.patch'
         '0028-FROMLIST-dmaengine-loongson-New-directory-for-Loongs.patch'
         '0029-FROMLIST-dmaengine-loongson-loongson2-apb-Convert-to.patch'
         '0030-FROMLIST-dmaengine-loongson-loongson2-apb-Convert-to.patch'
         '0031-FROMLIST-dmaengine-loongson-loongson2-apb-Simplify-l.patch'
         '0032-FROMLIST-dt-bindings-dmaengine-Add-Loongson-Multi-Ch.patch'
         '0033-FROMLIST-dmaengine-loongson-New-driver-for-the-Loong.patch'
         '0034-FROMLIST-LoongArch-add-i2c-clocks-and-clock-div-para.patch'
         '0035-FROMLIST-iwlwifi-add-new-pci-id-for-6235.patch'
         '0036-LOONGSON-irqchip-loongson-eiointc-Improve-IRQ-affini.patch'
         '0037-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
         '0038-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
         '0039-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
         '0040-LOONGSON-LoongArch-Add-canfd-support-for-ls2k3000.patch'
         '0041-LOONGSON-LoongArch-Align-FPU-register-state-to-32-by.patch'
         '0042-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch'
         '0043-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch'
         '0044-AOSCOS-loongarch-re-introduce-add_numamem_region-ini.patch'
         '0045-AOSCOS-loongarch-basic-boot-support-for-legacy-firmw.patch'
         '0046-AOSCOS-loongarch-parse-BPI-data-and-add-memory-mappi.patch'
         '0047-AOSCOS-loongarch-add-MADT-ACPI-table-conversion.patch'
         '0048-AOSCOS-loongarch-correct-missing-offset-of-PCI-root-.patch'
         '0049-AOSCOS-loongarch-fix-missing-dependency-info-in-DSDT.patch'
         '0050-AOSCOS-loongarch-fix-DMA-address-offset.patch'
         '0051-AOSCOS-loongarch-fix-HT_RX_INT_TRANS-register.patch'
         '0052-AOSCOS-arch-loongarch-add-la_ow_syscall-as-in-tree-m.patch'
         '0053-AOSCOS-la_ow_syscall-add-kconfig-for-module.patch'
         '0054-AOSCOS-Revert-rcu-Fix-rcu_barrier-VS-post-CPUHP_TEAR.patch'
         '0055-AOSCOS-drm-loongson-add-ls7a1000_support-module-para.patch'
         '0056-AOSCOS-drm-amdgpu-disable-ABM-Adaptive-Backlight-Man.patch'
         '0057-AOSCOS-kvm-disable-enable_virt_at_load-by-default.patch'
         '0058-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
         '0059-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
         '0060-AOSCOS-USB-core-only-enable-root_hub-wakeup-on-MACH_.patch'
         '0061-AOSCOS-gpio-loongson-64bit-Add-LS7A-GPIO-interrupt-s.patch'
         '0062-AOSCOS-ACPI-scan-Add-pwm_lookup_entry-for-PWM3-on-LS.patch'
         '0063-AOSCOS-Revert-FROMLIST-rust-generate-a-fatal-error-i.patch'
         '0064-BORE-linux7.0-rc2-bore-6.6.3.patch'
         '0065-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
)
         
# vim:set ts=8 sts=2 sw=2 et:
