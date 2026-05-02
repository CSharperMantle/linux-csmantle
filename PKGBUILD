# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.0.3.arch1
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
b2sums=('51eebd3aa3c64779308b0781818fd91921c1a7b0c3ffd361dbff01f8853f1cea7d4c70f6ee2ae3b7817aeca7605b63f12b0fa422d22c0a50fb2306553c49eda4'
        'SKIP'
        'ad245fe70556a42c94d6f16b7c276a476bfb1ed5811a5030d7fefa3f5f226dd722f61c55cb9b76f5ff42082a6cbf88e04dc616adecc91131b68fe59cbed59035'
        'SKIP'
        'dafee1f25d231199834869a5ce76a85eebb3c1ceac86f604270e93a40a22f29bcf797822481aff5aa5020c12359b9ad87ad8e0d36727166522510a07539d69d4'
        '652069e50060a3d84530f004f7064d98d6ac9bb02e690a3510d092d0df17598c9b3d564ae07fdb0dbbecc68d2d12d58c4c78c02cc08fbcbb8c01ba6e6256d922'
        'e31028c4d808982740991d450b7dfd77e36bfbb620205ee7a34b3c6937dcf75202d77a136e58ffaa325995d929f8a1095b6f6467992174d2b9c5fad034eee418'
        'fa656e5f44c069d93baafd37e4a947ca90aa9805c391b963d5ad2cfee99f75e620d6c86587a1f07fb3640a94f6f84917626cea5e901ef0db00da2c275630645a'
        '91c07e2dfb04c1137638f291397fe23fa45bcbff7c54bb3ac2ccf636e4e7e946f6bcfa655b0d395f97f398edac485b6d0f83cbbebfb65c0dd80a11c1c357e66b'
        '28c6585debbbe7331161459ba74e611d62d6b326ab4dce0324ff51c6c8020526739d575fd10589f6a2a921d58d3d401b8b1ad2943eee6c1457b5260373deeaef'
        '443255ba7dcec43eef4994a46fdce02617570af3394090fb42503813ff979f683e5a091f4c9cc498c07d50ef1638873f46faf10282b8ede6c062ec4f4382bf32'
        '0a9e579d133b654d67017dc82d008d4bdf16dcc15d9275af1c783030133f43a24900d4ad76c502ef0cec40586c8de13ab02219f924227dbb57aae7f8c0b80801'
        '866592fb4ccf09a6a871e287a52695737b050b0c319c9c374f18781cb6392fdd4cb1c6f9c4bf020fdda0074074b698ad8197b49868afd1679385c7021f010443'
        'a75f09277838678952b29ab4952e371809c90a8458e645ea79401d312024684d691bd771ec343d4bf320bda1f38bf8fc9f21d841b91f11dd9c7cb6654fc51497'
        '4c60135744826623c6ef0c6c73fb0635e38dc3b099eea64f2fba7e4902cee1a42afe6e42ffd52f924c17f6ac3cee496da85574a72601c80ed86353712587f173'
        '785a95439e07569ad1b5ca52a0836a6999dfa15a844b1867eb1c4354d76ce1ff64cc0e9e2a3493f74265c7af199e24a43d0f796bd8b1d5baa63b88f454f1e972'
        'b68926c4f4be909ee561f67b7ba29fab0994d72714b44738f1a5dc3ff607d7804fb12f16ef84be4941432bfe57ad5653bec42a714b13b91d6966489d000da76a'
        '00a0068a23fe7392eeba0d07a6369e796f12ca6531fceaa711e97778375ee5034e70a4d1a8ec850ebdb79477946ec575e85566054614d4a41669b36ad408319d'
        '0188b5a7f7e7f8d31715cb193a6f9d70199c075787564f26d9d62937c287c142a392a5bc2d0891930d86977f6ce4c7e22d98c26c8c17cbe648ca6a14238befd6'
        '24dad234760fe019b86450956fc57f28531a054973e412f7143e1082a033189e6e47d2247bda12eec7ca0d7dcec737ce4fc833d7e5b6d76c330805863468d62e'
        '0fc1ae4817a728ad653948234a0572fce2dcf9140a59df0ff58c7ca66c6018e34120cac29209d5eb8979b9cd51b05202138f07e6b7ba763bc774cf47022ab28a'
        '00f1447b66768987a6a8a316ad47b2337ef1267940587ed6353582c90704824aa05d64921e08a61899ed7db49e6d9e2f38d6c9a15eca0a2a08816c6275711197'
        '128627d7eda2f1523e8a6cd93e64aa337032b8abc7e43fd8adcfc16fe2fbb00925b49252e85c4b0bb87fd0d261dbd71851fcf255d369daa7e774faacfcb23ce7'
        'e9da52500cc7d3c53389d463e14f36c27ab7a908e189dd8b0c553b3615b427261afbb97a1bf880f4597a7068dd8277be06398512aef523d8e7e3f27961c2dfb0'
        '783003a9f5424e69b75aa21757fb9268bf7228f20d41e3e176b2d6c1a7ab8ec128a6cace809276d9302635ff2a7a9b1455ba0b689fad1882e81c4c91280845d8'
        '0e66407f7b81dbc51dce703c9833b39fd32acf454bb424f288c46310e5b3067be1542a52caa95908cbe6fe5060be89ed9b4dc15dd75e5e2e74b2f97069ac4b12'
        '61339d481ef86c4624677bae927eabcdb3be7aea288a724cea4694c1796ecc7d62e636d6c4e2c28d2685ef4fcac92d5820a9f00c0ea378210f7d9861ff16af60'
        '79b9bf288d626b5ddff82a5e9359d3b683c365281837348ccb434cde83c068107569f85af547cf7040050273be0dd7b069ae08cf78a512204b4ee9f4c20b55f6'
        'c06897ee852518ee519ee6fe522ddb0681f2451709e548e8313a62435342e46faa6b0aa6db8cf55a7b34a79e59894124222008bd026a799184a71c9f0b60eeaa'
        'af98b429e28476214f786f7fc34b421599eb76ad66220ebfad3edd2e943cf5ecc3cc741b89c82b4fa15ea5a5d520d6cc1fc0dab172b33a921768c000a7b7b274'
        '759f48cbf9c77198e8a2aa0c7a2cbf9dda3bccdcb1150b44071a7e60e5ea851d31b5b3af76e5b42c21aef14f546a69f40457e403eef750f75c1138edd92d31e3'
        '310dded372a0e7927f7bb00d2db592c37c46070767e1dac0ddd779984eeb86a69e15279729291bbcbde93d5810928bddf2ef76bd6a92c6d5c367369dc2b96e8b'
        '650cc8a40704b9fb7820ac182ec33da6587249957d92022f0f6cd2931ad18956202ff46e7bd859ea2815fc8e29ee1a9a50ff75f2de0b20b9e2e9af93d303ca1b'
        'fbf15fba1c96cdf2c5dc1985b10c8720dae4dea18363d948d4842d246d708f4262d8b317f3a61a96f41adef9039096eaa47c24677e6a7e91f6990ea634c1ec8d'
        'e8d031395b19b51889386d3d80bd424a5fa2abb9dd02a86bc3ed4ca4e5b0af1509b67c090e8d0f1c84ca4950697fc33bfa84cf959753df03ddb902e614a1c807'
        '75df489fc1a623646df8e85feae732a8aafe9fa3e107e34f98c822599390b49cc3eb2fe486b0402d951c58b63c92403da0af25b6d8a69572ba101ab3118a333b'
        'f1cfa702d6aa24d2ec7186815ac40eabfffaba39cd0a74750028d1eb88375227b7b24b07db54613ce3b3e2d23f8cd33cee2cc964d48b76e3151993e64017a8c0'
        '59175434a3e15b0b716a41b0be17b05f949ceeac5b4d781c5fc59d6b2c3405c696943fc08ed09e6a7a7a4f08c297cd92be339967f4129cb3432251469878889d'
        '5258fd1a66212fa120da006e91f68531c40f7eb0f32a18dd8e80860ea94e3df4361b0abcece201f7899d6344b2acf6c82c31c7608c481c1a8f5fc536749516dc'
        'b4e7070c2b98f6fb67aa30a3aec8661a3c26769f065b0a0fe7ae3fdfe9127fa4d7255d981da7d0feaf7650028206d9ba77e5f7b7e57d6869252a00879616f71f'
        '24fbde55ad051abe1a92841665feff106998e9e314b2cf5c9d6df8106f3d79e03fc9bfc985660330f63219c8d4add9d75f5d4dcf2387cb586cca5191c1d402e5'
        'ac23cedf404ea8c6c25801a0839d9e1cb3403113f4abf95c8808ee6740ceb91d980744aae7280619ec31bc7720714f85c87b1ff278159c5ba62bce22cff68e1b'
        '730cdc5817b6ce1dc7f8d6aaa936fb181c5d5fbafa81d12f3f69f361407aa196b6f436f70af8c026f3c99c3395c4e45e5bbbf3b3a85919fdb52d2d9d360e5905'
        '3567a05381bb8177cc47f6d7eecdf32606546266cb81ca368f6206ee304122316c41290321a5f31ff101acc7aa23373b1f425438a853b5e6a0581eed06cf29af'
        '0b49147e5b05a8686aa44eb465e3981a2b79e29e76a6fbd1659a17b675bcb194e6f4b724c93913be7f0970f50432d534553c46f492734c54245048ae3ed267f2'
        '409828d071980feb75c08d6bebc4b2c28c3138f8b44d8d931f79aad727feb32fbb72d56c199288407349698c48329047924d23c6656cd6cdc44761513e240876'
        '3a76320e28ad69cc0ac3a27f2d1c85ea19ee859d33fd6495b2dadfc5094efe5312773f51b77cbb335f1afd577747d4fdd6790e4c4652565f2d379a7697c88562'
        'b43777b068fae97d951b53dd4d1a107eac6a830f2d3db02565fb44d0277e9990ddf5ad9715e99190bea892a097e8e2208836aa9563edfd353ddbb9bcfdb59b5d'
        '51cb83e95a59b1596c136341a1afb333be992189d72fcb7e1ff3c02ce7c3e1d0a75c93cbbd333b60403a305f76c7d32538d788e8c3243d533e92ea191541c4eb'
        'cee4db64578db2fd479128b671e213e30adf1540a01875481d578f308c5b8336d1be6c58fd921ad710546a6d5f8bea08efc920ad7daa64b36bd1348b19479461'
        'b960f7b2caf6171b6460916fcc1e978486c340b668731bf7ee10a55418fe9ff78808221d2ea4aaca8f0574e3ce39c0d69b12741493c7b7b799b466595c3ba7df'
        '12363916a6516ed398f0a4636380fbc98ce2de8656a2044d777186b4ba696266da261373c0374618eeb8fa16e96fb566833e4ec170ae455d25620d9addba84df'
        'ee5bd93279e09edae0105130d59ddcf3b98e3f7e5215af2623d1c2579e53e596e570729a8a4174387dc224ae043dcbf06ec6bb96b0660c18caf73eae6c89f41b'
        '0fd9553d0e625b640cad25b081686b8fe188681f9756f88149e51f99b3e7b19b370a66e0a4c15d0808556b190cce60613717a23c51e29ba7ed05e0212a46e772'
        '90886cdb7f02c1ebe2cca3ec767178de8b514c6debbe757047a49ee91b639e31e5dd73f330172d9a0f79a8183d0b883274f3e4f3347d21a06b1061a540481ca6'
        'd07ce1d14cb830e3646419d3dfc804047b9b76f3d9d53d787271939d48b9df7a3c3595c087737642df751f70cae6e3b84e3c0076384518d59ba555fc550bfa82'
        'fa728e46526d04d38bd05a15dc58e31a042f6af57af66421282c6a0f019945de4a262d86ddcf14dd0bfdd84b8a872a32bb0fdbae89aec213e8e59fd81a6ec303'
        'c32e71907d14c116d221b12226f2468aba4ab043474c892883ea4cfc2d352d397d22407f9b2962778bffdd1f57cc4cedab96c412badb96098ecc07476a99d0c4'
        '5d08031737781a160c02f0ffd993d30060f8f05928f40b4b7acb8613a8d6aba869f0658c167ed9853f1ec966918a32c2588a7e98d3bc9421622042bf9a64c2fa'
        '97817cce97db4f660cff0064b13d3446db2eaabbd9a061048fce092a8c76bb8137c184eefbc99ff94aa3bbbed5a9d08143598305ad086720ffe989cfa1ba177d'
        '48b328f9cf1d2907faa1adbcf62fd2f22794fe3f78ced9eac83290723ea56013348f964e4c9112b75af30e91b6511eb49b8417b1f2c44e4df8be06cf9a162241'
        '97098ec6033275393b2b086a2c236e303261f324b42252ad653570af3cfd62014086bc8a653c41b861d5b0b89c5443be905e3cc88a61122d174151c292e2ad7f'
        '0686e58792da20b79495f62311e6ddfff2188f2a0c5bf2a8e36d5f4a7dfa22d653c687de58756fbf1516a8905aa77ec4bc6354b04e080ad41a51429ea5eaf267'
        'af1f9cc9788b3e543fd93a289df8ca913468299653e93b7466436a79d6cf01b3f3d03ac7969746611fa91ca47aa3bc9f55ebb35892d282b73aa1370387323723'
        '7078aebe763feb18aad7614e27ea67bf14240e047373d40318db6c79b7ed381d7532319c3bf027c7f5323e8f3b2e2daf8fa173e2928938cd9928aa01dd1542f4'
        'a09c65167ab9eb1a5fffa1ed333e66e9a27e5cf2edd0fa58dd8ebb36c37b88a1ba42b02275d985fd4f2bca09d903fe5796ad9a799e49a85880a99740c7216ea7'
        '24cfd2c417b09b93cbaa1fbee83b2bb9bf2f7c53742ada077496089ce9e048a58664adcb0471c568e2821e88c24c6af2ec991a2064ecc51901809d2005160c62'
        'bb3c8fbbb21be12aa27fbb235e1fd306de3d35c21724c98d7ff43134ca9c1dc712fbf2e45a3a146dd1a6afc876ac8a9df012af4f6d14d89e340752c840fdc414'
        'c5a6845f1dcec8aed341381d4841a1d102cc5820b623b3d8a5e5ea8beae56a020e592be83944c468c08b4afa4577f0ea9f0cac0b53b004e78c8e0aa37332f5f1'
        '2c84604e897023fe5fa40abc3d4c2ff8b0c6b6b1c363f14188e519bdf476d9b19866efec25c18559d44a829892ee5ae75ed3b13d17ad027b810fb625810cf5fe'
        '75f8f71c70928ac3ce397ebcc31315c8baa0e0825ba63c1cf7344c53474ba809b6cfd8c36aa4544a9241172660221b3f9e0060c9b19fe075d709bde4ea63ff2b'
        '1c3faec3a6bdd77dc10370d62b3cdb22884c912b2e8af42bfbac80595047f4ecc6b102776cba41aa934bdf32f8dc685bf0a8c4054eb8c063ce01f7e03971d492'
        'eac44d10b23e82324a1bb56022dfcde09a7700843bcb3b2080aa962c4a8f0846e76ded6b7cf2a464db5f18fad7c7b45cf7724c57a0072e68ce1095feae1afe14'
        'f1ab2aeef91e037acb6fb48acaff70b6d684ac34bbd0f64fc1703268f6d0e8c45d2c89fd2f32c769384a8e5faaa1556de0c86b4a58b369a70152593050ea6e67'
        'cd8f35846628361f6718a4505df58bc4b6c8633e93625683cc3a8d74579649df2074d1402e8666f36cc364d4f7dff97ab2c9bef17b95be5fa4c341998aab55b8'
        '546d4078c593ac1a6d58f9364f77ebd01b783682aec9e022e99eabfc0b9ef8941d4a2fc5ed882cbf06f567091b56ee7f362cfc29990bbe7f932df936be8dde42'
        '52cee8872586da1b46025e9f578d69496c85fb56643bc21138dd3bdecacb30a81300f48f8097287cece141cff7ebe4cbc09bb32223c6da4e33841ad29ed0f85d')

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
         '0001-UPSTREAM-perf-loongarch-Fix-build-failure-with-CONFI.patch'
         '0002-UPSTREAM-LoongArch-Override-arch_dynirq_lower_bound-.patch'
         '0003-UPSTREAM-dt-bindings-interrupt-controller-Add-LS7A-P.patch'
         '0004-BACKPORT-FROMLIST-drm-Makefile-Move-tiny-drivers-bef.patch'
         '0005-FROMLIST-drm-radeon-Call-mmiowb-at-the-end-of-radeon.patch'
         '0006-FROMLIST-LoongArch-Update-the-flush-cache-policy.patch'
         '0007-FROMLIST-USB-core-Enable-root_hub-s-remote-wakeup-fo.patch'
         '0008-FROMLIST-scsi-Bypass-certain-SCSI-commands-on-disks-.patch'
         '0009-FROMLIST-PCI-Prevent-LS7A-Bus-Master-clearing-on-kex.patch'
         '0010-FROMLIST-RFC-drm-amdkfd-disable-HSA_AMD_SVM-on-Loong.patch'
         '0011-BACKPORT-FROMLIST-drm-ttm-save-the-device-s-DMA-cohe.patch'
         '0012-BACKPORT-FROMLIST-drm-ttm-downgrade-cached-to-write_.patch'
         '0013-FROMLIST-PCI-Release-BAR0-of-an-integrated-bridge-to.patch'
         '0014-FROMLIST-rust-export-BINDGEN_TARGET-from-a-separate-.patch'
         '0015-FROMLIST-rust-generate-a-fatal-error-if-BINDGEN_TARG.patch'
         '0016-FROMLIST-rust-add-a-Kconfig-function-to-test-for-sup.patch'
         '0017-FROMLIST-PCI-loongson-Override-PCIe-bridge-supported.patch'
         '0018-FROMLIST-loongarch-retrieve-CPU-package-ID-from-PPTT.patch'
         '0019-BACKPORT-FROMLIST-ACPI-PCI-check-if-the-root-io-spac.patch'
         '0020-FROMLIST-kbuild-install-extmod-build-do-not-exclude-.patch'
         '0021-FROMLIST-LoongArch-improve-logging-of-disabling-KASL.patch'
         '0022-FROMLIST-LoongArch-Make-arch_irq_work_has_interrupt-.patch'
         '0023-FROMLIST-LoongArch-Add-flush_icache_all-local_flush_.patch'
         '0024-FROMLIST-LoongArch-Batch-icache-maintenance-for-jump.patch'
         '0025-FROMLIST-LoongArch-KVM-Add-DMSINTC-device-support.patch'
         '0026-FROMLIST-LoongArch-KVM-Add-dmsintc-inject-msi-to-the.patch'
         '0027-FROMLIST-LoongArch-detect-and-disable-sc.q-if-errati.patch'
         '0028-FROMLIST-ACPI-Enable-FPDT-on-LoongArch.patch'
         '0029-FROMLIST-LoongArch-add-spectre-boundry-for-syscall-d.patch'
         '0030-FROMLIST-LoongArch-Show-CPU-vulnerabilites-correctly.patch'
         '0031-FROMLIST-dmaengine-loongson-New-directory-for-Loongs.patch'
         '0032-FROMLIST-dmaengine-loongson-loongson2-apb-Convert-to.patch'
         '0033-FROMLIST-dmaengine-loongson-loongson2-apb-Convert-to.patch'
         '0034-FROMLIST-dmaengine-loongson-loongson2-apb-Simplify-l.patch'
         '0035-FROMLIST-dt-bindings-dmaengine-Add-Loongson-Multi-Ch.patch'
         '0036-FROMLIST-dmaengine-loongson-New-driver-for-the-Loong.patch'
         '0037-FROMLIST-LoongArch-add-i2c-clocks-and-clock-div-para.patch'
         '0038-FROMLIST-iwlwifi-add-new-pci-id-for-6235.patch'
         '0039-LOONGSON-irqchip-loongson-eiointc-Improve-IRQ-affini.patch'
         '0040-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
         '0041-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
         '0042-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
         '0043-LOONGSON-LoongArch-Add-canfd-support-for-ls2k3000.patch'
         '0044-LOONGSON-LoongArch-Align-FPU-register-state-to-32-by.patch'
         '0045-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch'
         '0046-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch'
         '0047-AOSCOS-loongarch-re-introduce-add_numamem_region-ini.patch'
         '0048-AOSCOS-loongarch-basic-boot-support-for-legacy-firmw.patch'
         '0049-AOSCOS-loongarch-parse-BPI-data-and-add-memory-mappi.patch'
         '0050-AOSCOS-loongarch-add-MADT-ACPI-table-conversion.patch'
         '0051-AOSCOS-loongarch-correct-missing-offset-of-PCI-root-.patch'
         '0052-AOSCOS-loongarch-fix-missing-dependency-info-in-DSDT.patch'
         '0053-AOSCOS-loongarch-fix-DMA-address-offset.patch'
         '0054-AOSCOS-loongarch-fix-HT_RX_INT_TRANS-register.patch'
         '0055-AOSCOS-arch-loongarch-add-la_ow_syscall-as-in-tree-m.patch'
         '0056-AOSCOS-la_ow_syscall-add-kconfig-for-module.patch'
         '0057-AOSCOS-Revert-rcu-Fix-rcu_barrier-VS-post-CPUHP_TEAR.patch'
         '0058-AOSCOS-drm-loongson-add-ls7a1000_support-module-para.patch'
         '0059-AOSCOS-drm-amdgpu-disable-ABM-Adaptive-Backlight-Man.patch'
         '0060-AOSCOS-kvm-disable-enable_virt_at_load-by-default.patch'
         '0061-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
         '0062-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
         '0063-AOSCOS-USB-core-only-enable-root_hub-wakeup-on-MACH_.patch'
         '0064-AOSCOS-gpio-loongson-64bit-Add-LS7A-GPIO-interrupt-s.patch'
         '0065-AOSCOS-ACPI-scan-Add-pwm_lookup_entry-for-PWM3-on-LS.patch'
         '0066-AOSCOS-Revert-FROMLIST-rust-generate-a-fatal-error-i.patch'
         '0067-FROMLIST-perf-annotate-Use-jump__delete-when-freeing.patch'
         '0068-BORE-linux7.0-rc2-bore-6.6.3.patch'
         '0069-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
)
         
# vim:set ts=8 sts=2 sw=2 et:
