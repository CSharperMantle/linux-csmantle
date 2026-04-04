# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=6.19.11.arch1
pkgrel=2
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
  config  # the main kernel config file
)
validpgpkeys=(
  ABAF11C65A2970B130ABE3C479BE3E4300411886  # Linus Torvalds
  647F28654894E3BD457199BE38DBBDC86092693E  # Greg Kroah-Hartman
  83BC8889351B5DEBBB68416EB8AC08600F108CDF  # Jan Alexander Steffens (heftig)
)
b2sums=('7304717954b8ad9eec54071d28d2d6c9af108d2c84686cee9b401e38078d4b39810541a854e458c85349de10959d96edb2ba7e38b0e0a7ebc46949e69e7816b3'
        'SKIP'
        'ac650a52c9097c0fa275742ff56add141677cfe8fe4c8459151eba73991a65c9bfdd072b5f9f139c7167352ec03d71562c5567b72f80ab00ccda5fac5b406b1e'
        'SKIP'
        'bef3377ad86440af76e9dde4c29c9f4aaad42f5fe343f7d31f5eb537d6d358602f996f5d63986af275f2e92f94e71dc28c320edc8c03d05bd64dbd8ed23d75dc'
        'dfd366b283243f95c318471fe35e3a36646a38388dd6c4d9746bc981985a02ea303d75127244e9feac14564a8f49385483dfb56a8842814bdf97ca747bc2a4d5'
        '46f0fd181d20e8ba9e535264b443517c9a41700491f96a80d20f357d721c32652299c71949929c364b6471a7bb4bb6a09dde60fe1e3ad2fe4faa8a52708b49c0'
        '6c10a7457942e021802b18a965a327e08b841022a4acdac038fbc8c248d887649cbf401fea57c94c5f638291ad2ca4d3b0db031424da4a383103e72a7a621003'
        '1975f2f4933557eacbf703130ef8867bfbb94e48ac6de740902b85ce8a431842dbf324ebc5cf85790994ffc89416244046fc23d3d818af0912cbd6a469d5aed0'
        'e4dfe2474e43f036e3587d8a6cbf4b5c976c1c0b53c121d708dfafa0241452aee9dbfa1a1a7cd207b844a26f274c997f85fa1563c4cdbb87f3b31cade0b8050f'
        'f4bdd7fa3b4eeeaed6680d6677dd1df3eaad9d5db2c076e7230a012a552061b61dba49535bad0dc4c1314a8dff6159beaec3374d3bff9dc6388cb1ebe28f79a4'
        '3a3b5ece234ec5c58232d6bdb3d94dfa78ddede9bdc423e6b4dc7dd1c54ac20dfebd4483f13709f2084a493aa2312b29605877bd1b39a3a79f68c0b220782d7b'
        '2584a4c9ffc41a98b67f33f3f8a8caa2e58316571a25e2976fe877185d7cdb5ee5bf7f2ed44bc4167191d9e20454a872950c86f30bfc8f198f62b218eb297d92'
        '4c1578908bcf8eabb49e0a595971e1560b24c1496802fa8cabdc739c30d90105c34522051744da49d9d8b05c5fad87c012840613e682cf5aeafec0367e8cf024'
        '92ed36be81823b3ad428f1c2a1a9f54e5c5b0297de4ab23eb740d85b58ba380da69050ebfdf48b31dbeb9d2df7ca23d2d99c2dc1dd8f5f4827717879d714bfc1'
        '8f668e9537ecbb38a953426ba91aabbe155f6273e17fef9a7d56f119ba87c921cf67bfd13a0b89770d83f58082106cf530135d8da570ec22cf00621922152090'
        'f6869822beabd54c6aa49809d42e66c8f086fe416d11b0e15385d33109e57edb25f4ba299027c549b478923c59c754d2edc29bfd144084290daf6f340e19863e'
        '75db1c077bfe55d26afade3b3b6bbff6a474bab804551c80faf075a7e1d8a36846fc0cebcd8e070010ef10bbbdb0633cf7329ce88203111d85ce784a3d5afa78'
        'c7865b2e097798db34b56b899cc39818fbfa0b36e07da810c3089dc06f6df7f1aeb1b357cd9a160be4335ef8780d716a3b315f15fccead9280ffe12308a76404'
        'ee7ce816ef3d4975de963f0e6787db7876eff965e727bdaf10976bbd73e2725bee0cefe7153b0f43c520c0804308ca742b3554dbc7aefa66edde8dd46d42a8b0'
        '107c238d133a56aad5865c4326127efebe851dab918cb2ba48d351ae65a4f126f034912ca2ab7ab91936e964ea5133212e10724645cbf89571f25f583e15acba'
        'bb53634f839e82042c7565d6b5ee401217b75120092ac10986224b7837dc364be902eb211b759626231b9d1769d8111c8b4e2d458f340f03942514bc5e8eb21d'
        'bd19842e3bed24c1dd44120e230ae28fa0816e3f572f077e3330d4647814c1c14f0d3e7311e54f3c7c0e193c9491d34169ef36600473d76b2c4870b0865616f9'
        '9fe9a24a565c666464a1ef05a639cf1c3d584cc5a1fd2f50a18c65145e5b3bba224103ea4342ad3b47110b237d6b5dbd9d121afaabad313c52ac90c9e16f2b57'
        '8aebb3ae42f43c7b6fffd998e2b0fd4ce599c211133226f58b4e96ce39d6517c882800f08195e7079d631f1fce791a7f42e297f7c767a28cebc711268157b067'
        '1eb0310bc0af11126c2eb81640ead903f15144736f4b85365242603244e4a6e4d319d8a814344e185e279d19e37dc769217008c20542f0a811af24414815b0a0'
        'acb559aa71113e76819881b4ba086111b69850f660d36121c71c8d01fe9fe6a460f50b5c5637405ea1c34182256c94e8a4984d56db1feca643bacd8d9aae0789'
        'ce765dbd48e8f4fdbe0dd7f2cd2ca6ac548f8172b297bdc829689532c57403457ee17ff4fcd22821f06c62875b7c6a14c8ee46c5cc750008ed1f13eabe52053c'
        '14eb06ecb0623b560aa7dbe38fab8c5e242a51b8075d317129e0983443b60117bb15e5710a4392ffc604c4177ce037bccde9d14a5fa0384259e79a44f3939061'
        '4aedb711d1743b20c7fb418b1e9b7dc994edf03305008c73b9548b6946b4312a5f50285fc75e451bc7a61137f2e59f63958bbe27274954cb5664e7aaa488c7c1'
        '91b46b464b6f1e2c13a11178457d8ed69000cb4edde674440fd1b3678a821686ef73e70bd7b34370d8e8f4c8268ed62c755188c777a45825a5b194b9c5a260a5'
        '134c16fb75fb70d076af9bdb466b9e8976d3112650d54955fad7331c175c0bfb6c5a242be900402c62bba966270e802771c267d5a4c9ff2e643aebf7de5c7a68'
        '1c9534f17e1a8cc76746ff9ea50ca3620fd28b2b8e7a727d0101de089b22c7629c88b5b0ef334ab726aa8fd27765495e9dce339a9612de075722f20496f96f81'
        '6c798f72eb618e43437045d16852255a296d296859bdf15d74b7f096039fa1181092e925318f607c8127487dc73ebf561f59b98a651beec95038799eaa970e29'
        'b3faf9fa6ed30b79eed97bfa0e7430f2d74984b848e89f3f68be808f6e1be0c76389c577ddb918d2c938a35529f688b6b11356d6ad886f1a21c1c557a0195a78'
        '4923430c4bbf556a429396a6a600b4e30280e224fe7982a2a292541c8ea08df75db92681fb92385df7a75ebb34971e31872fe8ac42dce89eab5cd684c49c0c9f'
        'd87d3ef7bf597c8e81d69c4a14fdfabec9cf6155bad691d1cce9e9894a202b6f692702c32d261fe624eb906b0b47284b73766d04aa10e41edafa1c6c9c08256c'
        '04ba7dc41060d2127c5f7b6877781063f2a7f0f8c0a396bd009dac2547c8ccc0f4bcd9f7c386f12280aa28af6382960a642a30f405a74314a798647f3f6b48fc'
        '035063ca946169637ef5a1d04c612583a2ebc1c103cc374b4030f486625e57c9b70f937fd82f6036c0468ad1575dcf9c12816f80c83a6c698a4d89243d41bc8f'
        '6eae800730001ddd2ba1d98b5c1b3429925639d701d4bb5c868fea0c9cb34eec0e649c53b0bd80fabf42ba55ff69e78b14c2c3f736b1680c51885455354f9541'
        'cc3a765645f2ec65c2f5ecbc73b8f3bce036b7fc0447457ea26bb95c6763564702f8f25ba0fb2296c3013de57165ca8b29e854ef4723a8775d6168081bb327ac'
        'df44c5e9663553fb9c6d5e70d3ec8eadb6a67474559b6e73affa361331c55a3480e97d67642904b5245bc0bb10924edbfd5a00a3e6b6f22db2641dc201648f55'
        '412310b0dc170a3274b7c9dacd6c70e8de8a26d5c2e3b52abaf66327c148d7986f1d1517e287fb2cf8631cb6e56c9157515cfbf339172d3d29020e5116b550c9'
        '714c13988a937b0c5672b1e5a353672d963402b17f551cefde5788febbfb70f9342b892388427b2cce3f743f1dcd63dd03a712cf3c0d52315e9c9c1082c60b1b'
        '8435a819498c19e0d0d78182cd177c46ac5017a6eae7d1b5b50662ae601800fad6d523de78ae036d1fa90e6f339b2961b0f462d5ada20b6ecdb35df36228ff72'
        '5c707574f96c9e81844a9398ec71f6ccfdd840bf5d8dbc58764b937d606761f16c715a8cab940ef61b447628af119ad662f64110b5fd497723b937e154e63911'
        '6f1a8e8ea099bd33b700f370e56c0c269a87236c0ce31c4dc4fe57f96632502e1a616974c1a937466bb7a1314bd61f51729dfd7e0a55cba5bff019cae80e3fe3'
        'b15040aee05aa7bf73833191322f189acadce51587b1b25a3c62817114831b0aa3edcbf8c17333776272ee0222682e1583aba34a273ba7cc8415d1fc80c2dfe8'
        'ac17a817478d50a98de77bc12076c71ae9f1bef824b151112f4905852cf045b6d22340081d986b752ff16305f8123bb5f80f6caca046e51b21c6423cd40388b6'
        '788b517be7a024294ac55b224aabe930cd5e0057a15b2f2e01e3001836316feb0fcc210f9a824efc3d6d2b6de2ec857443cdb695ddd94afffcf755c3111e352f'
        '0e0d496f83028f72064bd67075a6ab0565546ae8e18a3ef3dd776d312d0ec73ddfabe411a3261dc238ae388d772df12a5408ba323b2738a3fb305b269f8e32f1'
        'd1a304621ca7e6373b37d1821af480495d1e480541e700ac93b45ff4c2cb7b96f0d294ca213afabb0110f63fa3255e6111c1209e1b7c46172fc3923901f1ebaa'
        '2c9e62c1ea926fc06c38d0c58869af24cc6abef61af6b94e2c0148b55ee0ae42d564d668f5623b9d01bd2f068eefc9b1d156adf4bc71fd603a4810cc4d6e3d35'
        '3140cf4e6c93fb1408ebb685f93e6ef146adebf61879d15e2b1d9003e0e19a69dec24301835535af93422a03c776ed0b1d5cc2a3d5759ab30c9cc32fdfce661d'
        'e53eee134e02f145fccc0107b930baaf2b42bc169ac1d4a25196e8c88fc86eeeb10caa1d41e67e92da355d5a9c4153f5f09d50f6aea66315767efbb460de623b'
        '03c2068ff5eb839b374283442659786ed91154b0f977e15fdd43854d3ad9da61efd9221eed31c130fa26312db2b54038d4340f3efd31001c23b33a3f07c880df'
        'e3092fd7ae60577f79b22703efc25e32e3d64e35b6c2f83c57584828334dca3ff02e93192faa3a7fca8596075ab1a6aac5d0242249b47553e7f79b282daf7a7c'
        '5404b07e1bc526020766731ddec51bf8905a9ca5afabbeb7864987a7bab72058e34b8561f0dd32b3af3abc28d8baf911477d59445642fbb7aca023a767089e29'
        'fb5da63b052584e279c377bbf1dbd3a131a6848ee25d2b4dac2d0c117882afe266ccbfc63c16be3dd95b20cd181ad880028dd9e358628b0651c6635b80a4ab0e'
        '8cbe492e76bc5ceff6b38fd4d0b17f1a8ff8b2df3ae7ad94a700ed63f9d19d55ce947f58b95170282ea35f26efba393ac6b2968d07d032c7d389182017d93cfb'
        '996e64dee66724f850cb26c36ad3c47efda61714f684691cd9432200f1879e765bede45ed94fd99bc284c915a1e583a8b35854082783847bf342e190d3e3cb5b'
        'ba14e782d243a28fdabae24c50c8555127c274d4b45858c346b92e1b35f8ace43085d4a241b5bba79426cd9b5360afc7a639fede1f0c0e75c831c775d9a7a1db'
        'c6523de4648c8db9e3cc0e1cd5685e74b93a5eff62d896eb243ec0efbbc4c20a356ca4d7b966fc124efd63345b4e82f99f4e0f5f6757f13552e8a7f8acbac6c0'
        '6b2845de2a9a917ea9fa22e9717128ff1982ba22ea26f4b33ffee1a5eee8aa921d38da733de0ef3e3db83557c1b1f44f8bebba79311c1ea1d4093db88c94275a'
        '540c234995a81f184d1518e143442c68b5b112a3c6d324833ed4ae478241dd1d5b7f9e60c882faf8790dc3e7de485fae6162f276a4f987bc6b3b8b8a7ec24f17'
        '3e9a5008bc4b4a19f812b236c9080b6825e719537a74582f9ec645c388dbd5eb7dc58f68ccd22a4299552f9d9eb43d918b7a2b8177d19ce79b1df1cda6c2d795'
        'fee0d16c8cd2ba3e41decdf5e138ca66b1aeff549243b353d05202f83b34bd6da739109014796ec88347662543c40cfb5d3acf11ea8a626a4c2cd6507e93ec86'
        '800992e3dcb1e463e48681f478c82f2361e35ee0fc38ba1b0e882defe7c494f94e0c672ae18975402571661cc1323f91b98a5fdf8a42d7fa2662a2b8383c9d15'
        'd18b943147b5f9a897b6255dfed91f89c25b3ea8388e168c294e2bf489bac89f272795d8ada94160b35dbc68f386e37d4e516cffe764796564b31ea119035c25'
        '45111de6173a527f4615cd8be87040c4ce42c66a892bdee1b0a216862adb6492e4483319d74c3f11904f4c7bfedc6431b300d5cd7d8395463bdf2f7f64a6ac9b'
        'f180c801750e4bad2283372badbe2bf5b8c300211b6b5ba182f814ce668336c220c184c1565f7f30498dcf4892bdfb59c2dbb9d693e1f8af9c600ed62d06a13c'
        'dc6a9717679126ec9c35dce49662beae3a8005833dc4946286f0d31b8f7b5078422880b65438946439ebee3118350a20967235f0f21600beb2aa52c10bcd2287')

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
      "$srcdir"/config \
      "$srcdir"/001-aosc-loongarch64-16k.frag.config \
      "$srcdir"/002-local.frag.config
  else
    cp ../config .config
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

source+=('001-aosc-loongarch64-16k.frag.config'
         '002-local.frag.config'
         '0001-BACKPORT-FROMLIST-drm-Makefile-Move-tiny-drivers-bef.patch'
         '0002-FROMLIST-drm-radeon-Call-mmiowb-at-the-end-of-radeon.patch'
         '0003-FROMLIST-LoongArch-Update-the-flush-cache-policy.patch'
         '0004-FROMLIST-USB-core-Enable-root_hub-s-remote-wakeup-fo.patch'
         '0005-FROMLIST-scsi-Bypass-certain-SCSI-commands-on-disks-.patch'
         '0006-FROMLIST-PCI-Use-local_pci_probe-when-best-selected-.patch'
         '0007-FROMLIST-PCI-Prevent-LS7A-Bus-Master-clearing-on-kex.patch'
         '0008-FROMLIST-RFC-drm-amdkfd-disable-HSA_AMD_SVM-on-Loong.patch'
         '0009-BACKPORT-FROMLIST-drm-ttm-save-the-device-s-DMA-cohe.patch'
         '0010-BACKPORT-FROMLIST-drm-ttm-downgrade-cached-to-write_.patch'
         '0011-FROMLIST-PCI-Release-BAR0-of-an-integrated-bridge-to.patch'
         '0012-FROMLIST-mailmap-map-all-Icenowy-Zheng-s-mail-addres.patch'
         '0013-FROMLIST-net-phy-motorcomm-Support-YT8531S-PHY-in-YT.patch'
         '0014-FROMLIST-net-stmmac-Add-glue-driver-for-Motorcomm-YT.patch'
         '0015-FROMLIST-MAINTAINERS-Assign-myself-as-maintainer-of-.patch'
         '0016-FROMLIST-rust-export-BINDGEN_TARGET-from-a-separate-.patch'
         '0017-FROMLIST-rust-generate-a-fatal-error-if-BINDGEN_TARG.patch'
         '0018-FROMLIST-rust-add-a-Kconfig-function-to-test-for-sup.patch'
         '0019-FROMLIST-PCI-loongson-Override-PCIe-bridge-supported.patch'
         '0020-BACKPORT-FROMLIST-loongarch-wire-up-memfd_secret-sys.patch'
         '0021-FROMLIST-loongarch-retrieve-CPU-package-ID-from-PPTT.patch'
         '0022-BACKPORT-FROMLIST-ACPI-PCI-check-if-the-root-io-spac.patch'
         '0023-FROMLIST-PCI-MSI-Conservatively-generalize-no_64bit_.patch'
         '0024-FROMLIST-PCI-MSI-Check-msi_addr_mask-in-msi_verify_e.patch'
         '0025-FROMLIST-drm-radeon-Raise-msi_addr_mask-to-dma_bits.patch'
         '0026-FROMLIST-genirq-reserve-NR_IRQS_LEGACY-IRQs-in-dynir.patch'
         '0027-FROMLIST-dt-bindings-interrupt-controller-add-LS7A-P.patch'
         '0028-BACKPORT-FROMLIST-irqchip-loongson-pch-lpc-extract-n.patch'
         '0029-FROMLIST-irqchip-loongson-pch-lpc-guard-ACPI-init-co.patch'
         '0030-FROMLIST-irqchip-loongson-pch-lpc-add-OF-init-code.patch'
         '0031-FROMLIST-irqchip-loongson-pch-lpc-enable-building-on.patch'
         '0032-FROMLIST-kbuild-install-extmod-build-do-not-exclude-.patch'
         '0033-FROMLIST-LoongArch-Select-HAVE_CMPXCHG_LOCAL-in-Kcon.patch'
         '0034-FROMLIST-LoongArch-Add-HOTPLUG_SMT-implementation.patch'
         '0035-LOONGSON-irqchip-loongson-eiointc-Improve-IRQ-affini.patch'
         '0036-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
         '0037-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
         '0038-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
         '0039-LOONGSON-dt-bindings-dmaengine-Add-Loongson-Multi-Ch.patch'
         '0040-LOONGSON-dmaengine-loongson2-mcdma-New-driver-for-th.patch'
         '0041-LOONGSON-LoongArch-Add-canfd-support-for-ls2k3000.patch'
         '0042-DEEPIN-net-stmmac-fix-potential-double-free-of-dma-d.patch'
         '0043-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch'
         '0044-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch'
         '0045-AOSCOS-loongarch-re-introduce-add_numamem_region-ini.patch'
         '0046-AOSCOS-loongarch-basic-boot-support-for-legacy-firmw.patch'
         '0047-AOSCOS-loongarch-parse-BPI-data-and-add-memory-mappi.patch'
         '0048-AOSCOS-loongarch-add-MADT-ACPI-table-conversion.patch'
         '0049-AOSCOS-loongarch-correct-missing-offset-of-PCI-root-.patch'
         '0050-AOSCOS-loongarch-fix-missing-dependency-info-in-DSDT.patch'
         '0051-AOSCOS-loongarch-fix-DMA-address-offset.patch'
         '0052-AOSCOS-loongarch-fix-HT_RX_INT_TRANS-register.patch'
         '0053-AOSCOS-arch-loongarch-add-la_ow_syscall-as-in-tree-m.patch'
         '0054-AOSCOS-la_ow_syscall-add-kconfig-for-module.patch'
         '0055-AOSCOS-drm-loongson-add-ls7a1000_support-module-para.patch'
         '0056-AOSCOS-drm-amdgpu-disable-ABM-Adaptive-Backlight-Man.patch'
         '0057-AOSCOS-MIPS-Check-address-space-in-ADE.patch'
         '0058-AOSCOS-kvm-disable-enable_virt_at_load-by-default.patch'
         '0059-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
         '0060-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
         '0061-AOSCOS-USB-core-only-enable-root_hub-wakeup-on-MACH_.patch'
         '0062-AOSCOS-ACPI-scan-Add-pwm_lookup_entry-for-PWM3-on-LS.patch'
         '0063-AOSCOS-Revert-FROMLIST-rust-generate-a-fatal-error-i.patch'
         '0064-BORE-linux6.19.7-bore-6.6.2.patch'
         '0065-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
)
         
# vim:set ts=8 sts=2 sw=2 et:
