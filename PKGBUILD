# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.0.9.arch1
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
b2sums=('ab7b2f892fb20a54afaf3bfe7d6951a2ebd88742332fb0c516d8041e9989fe20bef39fd21818be71a1fa984aa1122a6496d0ab919b07e646e0ef82a55dae3070'
        'SKIP'
        '789c814511f36b95d3263057d6f2acfea593f109947153e021b591b2a44c6ad09ecb61bed096d3896b0eb567cb2d58884d9dddfdcb9a93fc09969761b1993194'
        'SKIP'
        'dafee1f25d231199834869a5ce76a85eebb3c1ceac86f604270e93a40a22f29bcf797822481aff5aa5020c12359b9ad87ad8e0d36727166522510a07539d69d4'
        '652069e50060a3d84530f004f7064d98d6ac9bb02e690a3510d092d0df17598c9b3d564ae07fdb0dbbecc68d2d12d58c4c78c02cc08fbcbb8c01ba6e6256d922'
        'e31028c4d808982740991d450b7dfd77e36bfbb620205ee7a34b3c6937dcf75202d77a136e58ffaa325995d929f8a1095b6f6467992174d2b9c5fad034eee418'
        'fa656e5f44c069d93baafd37e4a947ca90aa9805c391b963d5ad2cfee99f75e620d6c86587a1f07fb3640a94f6f84917626cea5e901ef0db00da2c275630645a'
        '03e69951a7c848565e88d5fdb9f6a1bc2dcbb7fcaf617a10dee16b56fc1aa7c1fa8fff8ca711284a7526bdd83c44dcfdf6e658a735d25f120369c575b4c520fa'
        '5c5bbf6f8b28abd4b704d536cad3ea3fd8bde0f0daf1dd7c53aba5fac6b038b36cf76add7d39746b2b5016e5ce9432fa347868901128d84eec6ce333dffad68c'
        '30b946fccab920e10e1fa290c93bc0984e0a3cadb34d02a8ac6b70664bc2ac3e0282fcca8200126573223e0e7a4a31fd1a791cf76f62e0552ce39c17c3dbc905'
        '1e0199d4fcffb0ce9cbebf0e3d224b1e887cd2c36ca812ce210c83d50d0058b22838c8b4c94f95bc82dc8d11c2100b50eae2e4d5abfb1df894fdb6544b9b8b0b'
        'ca6ef082a188e63e108f41e6d03a8e476f61506daf40988b91568ac8899b61d8e82a4696dff1ef352685f6980dacd962c801f13bcca719c84cf4cfe95894622f'
        '0f4b0323d7aa33e0c87b9cebf4cd9b425fbf15a4ae69f1734cc710ca511349abd79af8ac74fe706751160e08dd3dc29cff6bfbf47784b4ac932f7a51dd98cbdb'
        '8681f763c6d19550170d661bd2dfa53027a2f9e32a0dfa07286dd78b2e6c1b073fe8b48cb5d9824d23e634bd2a3aed264d4e6c4f9c0fa2f6da6d1edc66b0e6c0'
        '27da1b7f665f8aaba771274d5e149d6b0963a68a9fb67cef6107cb30ea003218e0714d23b55219d3567d9102d7417a47c27856c32af207a8107f1d6de3dee522'
        'd1fb534d0aa6a1e2cc390a1b81fb712c30a5703c627ca42f4c9c52d660ec0041ed9847cbda82e4e3a64ba6fb9a3e66be47e97e0a4e0905da611baa5a983d5a5b'
        '6d45a4abd6d941e0fb4b143511da249dc5f7afb03fdea0fa99f07b89d4b404c354bd95442ef1238bb817d1d347ad5fc2aa826c233ca603cbdfbcb2096c10e43d'
        'b77fc690e959e819468af8e8d5c789ecb55d84c3ee067fa4181758ff27eefc1d71c3e5bafe7465da854046a2ce87a412ae4b67ecfdb9ebdc29235601f386afe2'
        '8fb4dfc1d1794f7c9ea2277848a12e979a2b579c3c4bb9417f5fe1be28c9229dd1480b7444a614fac782757ed1e6df371bd89a3474e6537c521b0741cc0227e3'
        '053306145aad1278ff67bebb75db21557a8551d1860d90c2311633dd86cef432c94ccd92a98d586eab25a0b10b5cb73910236cc616e518402155cfb116bfae52'
        '6a02822936505637d0e24b0e0ffacbf4accefdc841d40d70953fe95af58614baaf894cf585fd200b318149e47bad5c20b8c59ee0805a96c6aa3cbdfe55b1baf2'
        '336b2fc87d0c4b092947108511e11c7db13751a6f72738476b0cb441a191893daef15b2c62bd3713dea6a45fd17578f816c08e87f5679971346dc442c18f00f5'
        'a23817a89be500cfa3f95b2837286a1d25e935fc86abc656810149a3b095099b125e80376b8309d1a4effa9c289b2d0f292ea907163fe54259c35c76ca08ad86'
        '5bc3ffdaea28140652e9f41abc977f8f54409706329e8950d829adbb1b12936dfd0cb4f570a7bdb6f57abf3d342df56e454268cff16aaaee92effd0edb3924ab'
        '9a6d6dd7b86da916a750f9fbf4192a5b5b9cc5a7314baae4fba6372069796c8a0aeae570067b0f16644ef2168c9d2b3e702d956f6433877e762b8c5313da5851'
        '3644341996cf271846a404c8497f2d3b89bed58f6507e7f67d5f4e53f1fba6710abeecdf8b73b3423abd2a2abc13501505692fc39c5f9ec47313c2b7cf783144'
        '0f5e4f8dffbabfcc5a2b7681422d865e73daf3f18f5de180959f0219ae0a4c22bf594eb8f44ec3a157c9fcde20f6c4b1191e9d8ffae1d9c2b8423a6209e9867c'
        'a5e8601cba665479fe21bf7f8ffcce9544d49d5d3c83a3f08791e9596084b115fa6c8cba12dfb5a36f93c845bac7ec56da4507b0e5a4b92e3fc4313ffa0f7412'
        'a110d1d0069e1e04a5a978471a47e87bd8a843e0b99cfa83c2524a17d763520a6edaf065db5e07f8d3b472b5d63da60246ee24539831043b02562aadd0e20272'
        '3b7ac14960b85595c8f13097f00bacfec97166eeaeccea94b19d7d3726b71a8fec662d15dfd853d93fa701d3137bd15363ecaeeccff4e8443adff19f66cf3510'
        'f57f71f6de7ac13299e0ad6700d41962aa469fd194681f8b7f4ac90d91a1eeb361c80fa356ffc12b65395221209c5f09244878bd7b7eb1b3f32c13adddc77dcc'
        'b7075f3f68e205b28ae5e98b06a67fc21d7ae16a46ef27d9a33710fde7f41d15b013d858bf4fb24f035b2a95f580586f785fbba804e164c99a8644a93ad3bf6c'
        '69162c85e652b7f74c07eabe9cc8b8a9535129c6cc8864b209db761090c953c6e5b9c556a6a731c4a98f40d12adf6ceab4b0183fb1fd9679067124b43c7dfb4c'
        'a0e727d6a4bc378aaaab17f699c00178abd88e440b515d3c789b8db25cb65bfc55c75ed9e98243f719ff781005586ec833b37e09689003b39694cb0fcab1552c'
        'b119482e8462c76d1c2a4ec85d2dc95adfa4e10c4f1211dff6c3efbed2d8c7c8b11912fba13871a81ba1cc53141665c33a1e6d660fc7dc6e6024fcedaa9eda97'
        '75f2bb44b17713a4ce84fe18786b0b60f6e210f26b38206a69bc311e703101643fbcacd5243bdf04d922780b62b55b50b61b66c53d4ef66fbc5c93d4acab4083'
        'f319cbdb7983008378f8ce41e1454a3593885b9e649dc4d601fb449470eb598821ca2fabcdc3dd68599e8cb9754a1476b241b4839c109af30c8414c473fd4ba2'
        '44403f6d304d303fcb8033c939ab6508e0a7170246796dab72d972d0b9436be3ec9538e41e56ffaa09f40a5da27cde42bb4f85d252f735feeda67a6ef8ace18d'
        'c92cbfc7968c2349680cbc9592b78b889ddf0a54e2d008280f62226a19235d13c50de284aa2b5da8d59579bcfe608155992efe2b9e1deb8849a72a1205a49d49'
        'f80bf45071db8f173121609e29ef3171b40b4243d85375c2b5fd794caf9f6816b363251d32813c7a8f15c11619da5491612994f14c02d034bbb21a532926555e'
        'f343919df228fe1d7379a3944fd4a60f7973f0cfce8b9563ddd67c82ab58f442eb4350707369995a5fa600ae11335b802d78d76fab2bdcdf88dc4b829d08e960'
        '2e0f035e975f10625563e4b9847a1f80afe4186501a23e66aab1b43d161ea0f4d8af7611447299df1f38a25a950d390d3afaef542ef46b1ec467260aa4bbf618'
        '5aa1c717639e69ea456ff85da51ca4720d3440d1ea8128e3fceb51b0e3f7e2d0981e52e567bf814416017fba0ef874d62b46cc5edeeee90c43092aef2b9a6ec1'
        '7a2b1835f25824111de1ad513abb490a32d125d8b43d574fa3536e42790da0a17ccb1fee806b91d271b2490886da420749c92ed17abb8f40a84147cc8bdbb08b'
        '635af58b3aa6d3f69348d77c43f8a43a13df969cac2e20d81970fa482147fd1275939c70f6b8b6f51751bdb734bbce2f074f829080fdd582d6b46b323e09fc2c'
        'dc9ccb559762526f78b4fa25f6090387c099ca1fcfaaa33b90e2493a3df001d34b13aac089ad10df96e94366f0a608640649c7f4396cc8d45d3cc831dfa75a40'
        '9fd0e44a576fa0c1422f8cc40708ff42cfb3271f2139ce4c958d5dca3d09c02343acb3606b32397a4cff17976875fdfc84d3185f94eea4ee917ad318b628d331'
        'ac6e82563e6e1e1e3871eb66e532501dec2b979863d01e0a16cdfd8ec709ebaa039f90abd6f86df88326969156e839999da5be9268ac3439fbbb910a1da97f18'
        'db09769d75eb6799aab9651a5f1564557faffdec954128d9295fd329b73b7bd1a4ba448d6fdb3f6321f7a701aeeac3ccf84c971ac629fa711baf8462cb96bb34'
        '9bdc7d7d01f5f39054aecbae899dd909c8ca1c7c6a49d66f7debc290c9e32022a6decbd97844005e4720c59080b3c4efe79df37d2e1449abdc8f701d35a31f64'
        'dfc5232834003d84bc3365be56ee0e854095f5fd6e0185bde7d33988f2e9967ee0afd0c32378c56ff2c9e728ee5a9a22c7a488137944f76a9f992fdecf15c39d'
        'b5b799addf410ecca4a79c932e90812450c5f74ca10bd46548a640a8888f0d28f89ceae01bd1eb1b97f66947d9242b4e3aa8bc453c36a73a219381ccc0209d06'
        '0d395cf6fac25075a5b4901791074d07ab6b0dfa04109834528b48dc4a48c8499c9490e74684f8bc891129a1934b35d6366de4dd4a37cc7b07817b8666fbdba5'
        'e0fed3f14bbc5c9f11deb1c144d9df8f53ebc7b89bd28bdefdee1bbe51bacdb759fcf275ca8129513a653da6f292bee491cd45e467cdfb902060b4921f333da7'
        'c61c18683568a090f8c38c87ca8debf8325d505f8580a7297fdbc60e6d783c5ec1e17e97e96fe8d7e626f1ec3c15c4efcc0bf4c9e60ca1a9d1c4412e140fb9b6'
        '9e2518887c4726f82783ce2c0a00f43a5cdb8f0d8d31e1ac4186ab9f05df1698f8e44fda428e93e64b408774d7d5c95005001644bd37bce9eaba0dcf652ad3b7'
        'b60c7f5ed4efd5c37e31dec721f88560cd62006d348c5d8e339272208e669770160cff3c13b8cf1426c2856f544d61961ca1596deeea26f99083786f81907ba7'
        'd531be7231750dba092a76270268b6a3b9694488e5dc12740da6394fbf91073d59b3414a7267222696b599f10f2aed6cf39e5c6d7b241aad7dcccf061ca5d35c'
        '5bb174162cc78188dbdaf835e8f4d6536c2c2267f1d7ba3b1d413e45503f053c7a8bd7c49133410a781c3c4d36d226e315ff88dcb3d99c3a9562124180a43187'
        '859f1862cfd35bda1f281166ece6b7383a800ad3c67353e38232a273ddb6afa862022530f5c6a43c076408c8a3ae78e8008e3ef11afa7ddb0ce4e1d7ef630796'
        '2cf367098b8e953aad6ce1ed0d77b80d5d20dc3380dd6c10719d3a2520f90781c82575b6e58b79ec1d9251ca527269722762986ce8e10d5f43fe55205799c5d4'
        '537b82750ab0dd02fc4958381470d5613bc3bd3599b4d2e07396839c6cd9080d12f1c0deee485602d63559de767661b955b20fc651cbd9f7000aaa7f8a381f32'
        'b063e00ed2633224684847a7d9b1aa91d15160a85918a631333234c523ec7b1bcf17c18043b3a807b2c09dc2b2589b10f6c4fee80c96539d7678c9d01ab37169'
        '9208b60d759eba05a6ad85ff7674509a0f70cf0f7a33f12a1aeb47babf7d8b477d584c20662cb34f095cb9dd14c767b2d3d73382896938cec0cc638e99741365'
        '8b28c1f9bae2e1bb064528bb1c706253f82d50e93b41abba60eb18c0a7a335d0949143afb2ada5951ccf1eed918a63dfaf85c0ea08b88958b764529473c9a0bf'
        '4c57d1ebd5fc4f61293d522e313270af849bdd809069c5d5628fb11a3763c2858a97feeffc607da35dd4a8a1390dbd5f783c782159114fd61e5a3c257036e9eb'
        '553f14749863fad17a064d8637d50e20895823677d5bfdbdc9d42a6f1da79d519eaae33d1fdcccb477334667ae94f0964ad0dd5e66a59cc572c12ac2c2a37ba0'
        'b7b5493378a796517d547622d96b0417fb9eac86cafa0fa17a7f5c5e6aad8f6a289566a942372ca5cd3ea3dfa3083cba7ccb413e5f1a3c6aead84d58ad3b2c36'
        '18d6956e348ede2c248b4af2e3549eb5365b81a574386a5fa97bdbe85f53bf4c48b871ffea42660ef0563ddcbb6721ec91bf380209f068dcf6ae80a653fc4b43'
        '90eefca4d386464d16368eccf8e83131c2c2aa72c6d6a6753397c32ff455f68acfec8d4c3e1aae2b387fdb113c42827e936c63979074efb1490f509f15912265'
        '453480fd0b51086155417a731898c274e4c8cefb79605a912c9601255d915d18fbefc87964e0070007c8d5edb66e398b9c21b1aa2f9a678d1b72403e28b8b20e'
        '715801f2a76ea71fffc85895c7475be30345b6fc08ea2a06cd886c11d9b41dc8aa0cd0b6c5904f33855af3b1fa9816a1db844d56589f6ffd0c389bf18467189e')

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
