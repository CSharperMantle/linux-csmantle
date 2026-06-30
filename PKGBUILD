# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.0.14.arch1
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
b2sums=('f313eb3360dc5cd0e611758b84f9d8d7a984f28b6f832d45823619f66679c56823a18a55eaf7b4704d903b031704cc624f1e055ce25752daa5bf77966839c2d2'
        'SKIP'
        '06512ff2e57bbb6a985101091ddcb197cc708205b6b89d7d28bd7f9cda39887a9289edc02bb9b391107596e5de0a782c953fdc9c332b4d47914741368241b7cd'
        'SKIP'
        'dafee1f25d231199834869a5ce76a85eebb3c1ceac86f604270e93a40a22f29bcf797822481aff5aa5020c12359b9ad87ad8e0d36727166522510a07539d69d4'
        '652069e50060a3d84530f004f7064d98d6ac9bb02e690a3510d092d0df17598c9b3d564ae07fdb0dbbecc68d2d12d58c4c78c02cc08fbcbb8c01ba6e6256d922'
        '7b59edcee464209b0ff2e4b06c58babdc3d56801e1f73351bf6f140b39c53feb96d786434cb8b0db39ac94cf4ef905dec9c158758c4e41aeea16b9fa7f21c3f2'
        '82bb78c66948a572f35c8f0b6ba924e122a075632efb304693dfad2331898accdc80610d187e93ba5e18edd7f12131bea1ea2cd31b4987047cfe1bd6079eb3e6'
        '8a27c606ecfc9e58acdae976a3d98df33633a928f4e19f97d14df9b45266fe13c9a2d1af7025addb627391562f36834fa5e5b8dda67aa50b59179ad29c3c0ccb'
        'bf17abc40802dab316bd1560524077dafea2e3d98e2dba7ecf2204746a3ae1f98f6146db617f0d6e01d56b60d9d6ad2d78f15a8c5477e30b7f36bfd0622af2e9'
        '4e4271db581789df67be30c4768004ba4be38b58291f98fec52599c25afe42e47fafa28c23b00992bd666ea64b2d9954c42013e562bd01b4a5889ccf1174e05c'
        '1292d99acb8b886d8d1e378690ae3481bc512d34c58baf83365d12a1fb9817e7e4908d04a72dda9c4a33ee6a72e563a341dc5155d231ec96ebdd5fa18f0ac00f'
        'c47f59143164561575c96ef0271af9860b1d46cba2ff23a8911804b900d08c5a2f8e5596ec61ff97043eafcda64c6f0e4bb03595faec5e5fa2ec31a1ffa676d5'
        '4755209cc5367cda044a2e765c61f4cbf0f268eeba98a23ed999d5d2333bbb54810cd498a842013a928b90c79d9d7c712d7dfac8865d60bff11d97af61679994'
        'd9172c0df209db0b4cc98e0f94028261c6e68686d288c0012dc278cdec0d7452ae6061365c989a243c054543eeb28ba6857ccd67e472786243783a53663b7602'
        'e62edeb8da15a07ef50004db20f1409a84a4d564c6b7fc1c781039c5e312803decc017b89fcefb42d01e9939e21f5fb17101fff54e3ec2a27c89cda40590b3c7'
        'c442eb99b614fd4379a2364230bd182db613c009289ea32e8172a80667e3d008c8b07755f6e4684883af91ba26eba9d64b18f46dca6a7480ff0e615637ce83ab'
        '4a1dc068e3ec2adf0afd89eb6625fc631b22274841d712724d37f551f05d54b8857a5dbf16645f76e64cd27fd66365fe18145e6a57c2977c67290b70ab301a1b'
        'd35de23d033045aa1eb9ca6fb3dfa2d5a1364fae123a8f2bb3f594b687e3894bc32c8d00cf7b5ffb06414a67974b4cb06960857691eca8513502be2a66593654'
        'dbfc234b898ab2f743f3596a5dd06bb453db5fd4b293733ee423429ced093e209eafc00103c030d172a6470552560845146b342f3e92aa48f5df49bccc533e2f'
        'c3bc9d674034e3b3921c677c600d6aedb0bc8a9467158678347e3431d37f131abf378373b264fc59f09f98a782a96e793da889c6b58f331b94ff6b3168bf2cdf'
        'd853d42aa7af6da4eabcc70a80c746a77c7d55756579cadcb0ab72164ea85512fb657ca26cfd27d03a328863ee76f4393286b9940269c7a5df73e1946eb50aa7'
        'c3a856668fc9d399067380e28dc524a10d94785fe34a4e99ee3f9d3403a1668efe325b956ed92b7eab0961927ed7ce4c3ce12ec4b33de00bce5a58f6ac264f84'
        '8d5debc7c7d69ab19fa2df065f35143efe98d5609f21ff6d446bfc751c26b1d9edbc3b007b1b937366c1224edccc76a24edd06fb286d943c19e609bcc8fd1db1'
        '38a3175db2a542fe09280d8d14dca8f446e6075bb6368c595a855af77ba20007f3247bf627800ea756e703a18489f008ca91fb4463dc69513bbb8c033405841e'
        '82211693723edb7b0d621ce08a66a314e64f4479242bf774623e9a0147daa7ab795725be98e31b70b941d741f00243065465c056fc136c2bd2fd124e8c7f175a'
        'aacbf4586665ca4b297a37494174c86b24707882da113db828cd14f048d2e2c72d01fe5bce922f73a874e755ca945b67e9e0d3428d212dbd4c0c001af15e34ab'
        'd7504968acf0ed566c76c5273fbe6e5a472320695cbd4d427ef7ea10e3c32faf7eb8d7223bbea5ba325ae3ad5bbae58972c20cd018a748daebc34737463c5977'
        '1e25ed93c5a0d7ba081c2e16e90d1a4c5471be9bc34ea05e17f6cab5908cc2034c8834bbe395a5b365c49ed021de752486d8de2ba6a53cd590132f24e377cf3c'
        '305ec7c9f7acc46759c54037081770e83d49266eac2f89117bfc5b131042966152125342d5680fd5c12465348cd499e34d1b1b91ec8aab7aeac88b981f278fc9'
        'cc9448953650b1dbbf897cedb4ca88a7f5545807ffc12cf879f81f76670631e157460b4f9c58f7369204316d3d69a2f34e6263a216491f5607a318733be97a55'
        '2c7b361f43ad6b4b8ad306b8ca8257fd6a6cc29f8d655da82ff5702c17381b913802070bb29d4b64de8938272ad13088e9edf5f591532cb4d11b9eab27ef881b'
        '4b6a205ab6f1d7d37e9d39707ba1f4487c2dcba2d5931ac9ddaee4984a7af6c6f969de4acd68d7b032abf4a1485ee83dcc5914e3dfa96cd634e79ff2f848a2c2'
        '6a06ea02917b008d5dbfb210d2866bd2797aca98a123ff2d69209c2773b72bd09d84b1e716d3c7d8e1405e90a635a132d62aa967352b9fb19767227361c50e27'
        '4991f465547952c25d585551baa2e72e17e93a162d7216a9b2ee468303e62112bc9879fdda9383ecdb65e3e0bfa46496f89c7ca9d29a0bbc725a81bf27532a27'
        'cffd77ab7193ffa6bc08678960ddf19cff8a6ac7a94a2c04bf09a21145fec639fc7211512886fa35c1028130c50280526a7943f46b50a94f97ff574a7b78d314'
        'fe1019e35cead3f449c748cad57b3637e0e6463e050ba1b6732c67328f9284bb712e5ff7add12544229eea335fd5e18324d024636832048fed126bf25d039da6'
        '6a5b182b6bf1e2e321453cf7e3d2b4643929a9d0938abf6aad826f4d26439451bd86741dbaeb57150b80c6a25a5d9aa5fb333e7fe1c42451490c2f863e78197e'
        'e74d3db05125459cc584cf4072107a40795b3b1279417231aeb52e339c1b214abdd8735ac76c6ecc6e7054278fb482b8876f3ebe62ee3808614e88813353cd76'
        '9e6111f67b0838dbf1ca4f3445180cd00fdc74a5e0c5f0491b3291e8a980a9adf92c7c507c3d4ea2480cc668f8d9af6a441e22f554f28e65f74c5eacbea4efa9'
        'f12807fe9a201879c0fb56d0cd5c08a678d8515f765f88e236baf05c5fab77326c5794c0bc3e1b952187531fd326944c716fc0ce08284fee0b8e976c8026d8e1'
        '141750cd375fbaa7ce429b71bab4dbfb86bd0e263e06b5452ef7cf3bae5831a2af8d4ca2633cabaebbe7a16dfe2b54e412471e9096ad549e9bcd9bc0b2792424'
        'ca11d047027fade53209ef383463e7354cc9697526fb12df82b4abe3ca34142f76520f71760846ec9a1843e1202af88a62d2b212b1d7b381fe29965e10d71976'
        'e441a25d895e2ef0a267cd8492e13c0639815277734937731938ad11042d1243a99edb64a0d42e61e87af12cb3a3118430dfa14ce03309526fa3edfa26f7f706'
        'd85b5f0fdbbde049c145426549f10868ae0ed2d0a2a56ec66cf1c204065e5aedfb000df39d0a1287d265559a008b3a8e28d2686657afb169801addb9bddfd29a'
        '450f2c1a2a688118de275bc2e098d3df51d74dc92e00998d6dfd0c4ef26c124d76ed058e28dccca5eb1a8c725f9e777992aa596fb8f37c44cfa070b7dde3ae1c'
        'fcd1620890892a954ec66a80f32576701b59c11f696614b452f59bdad110b551ff2d4dad126c72cc0369ed83a5026cf4a8e7fb60531187f6cdaa03abb85793e7'
        'be4179ff5a72902cee222e60fbb6fe7759efcd7294a6c30dfbfd0bc8612297c41f14ebb2315794cc598f01ecb8e3f2a9279113f34e65de48287e88972ba3ec7b'
        '9a9a52dee56d9e8adc5e638b8c03a995686cdabbb38457e2f6e4d113462eb19b232bc025162dc636c50cf210c083a1cecde75c19915d038b3ef9dfc6e331ef61'
        '4a03857f57f34dc47843f3c4950bd1d3b552e1599ee569f2c7ab88245704d8a42ed91b635210a1f99a590070833356c41599dbd49cd708325edf719b6a1187dc'
        'c99e87aee902c552a5a38ede31e2589ab77d364aad5311383cf1dd1959f2362a84fd08126ac46896d7c16c505a3f10981488fde1dcdb70b07288b5fc225774e0'
        'e43a4ef85a91fca956a907d27bd50c66b5af6e06a1ba1097edcc2aacab92d08b25545df7d3065fe9a5a1f9d260505d113a129f9ef2561d130ebc41df404bbdb9'
        '1ba2e0d625e092c3149ce20d4b01895b37ad40cc41e98f65b41c692c108dab06f0891a3196aa21927edb42f8c840f0cac5fd1403c4c54b1229e1cc4a686ba515'
        'f96bd45f65f89df3e9860319d74e0e6e499217544e511f0150d7feedf1c5eb4f8a81a6372009daf3661c013c99fc1c9a93fcdad5fc56d931bf8f4c2865c84f18'
        'e465e97d1bb08dbb3d1269af2a567a8558c10105bb278227ecad49608b2173785363b810f7650292d1e988c9b0d229945126b62cf096731a5e1fe06d7800c31a'
        '88711fe5d5ab92a2d7bf37dcf938d17116517d60cffc192d66b20db654b8295ca46afdae179ea133a863ed7fa3f584c70f12508e3cb2396be5a87cb04687638b'
        '88c579c51545a633a0adc8edd9d9557e5db0d7a3990ea5b4f343ad8eb1ddf8adff55a51ba6414a73d5d634f85962e793eebd5a592ab64f3524b9f2a763d0aea9'
        'f9390786aff719a10d59ca21c1facc3ec6890a2a14789baa4bd5c1b0ea73951f682e54626b45b82a777327ae2e40396c671b5aaacda976642a13810f89ade89d'
        '973b8928fe313e6a4874887bcfbb7dbe2398a4423a3fc8bdf26d54f52955fd24e6b302f79c7993d9134e067a84abba7de951ead0aeb0d3d4c42acdb08d938aa2'
        '6167ad2aca8dd3c02ea65cae11c7d26445759924c41320b69ceb64fbfe03bb65238e7ecc7d694abb1f08ab6137420aa701ea1f7894453a6aa08a0d5fd6da99de'
        'ca5cd67a6967bf6247e992988005450178a30d2ee9d47d690a2b531602b1952664d5832f6c42bb3bb46c06b47de84daf17da9c6cb7fda0df1d8a0c34feb2866b'
        '32437a2849b6f414394634d32d1325a469813d0cb559936aa775e1a629fd8403878bfc10f3b0e873b866e25e172c626741c77bde451c1dc4bf999fd46b31ec45'
        '8ab9751f7c6bd045fdc58bd2f975ed226913e3a68baf087b8dd691a78ccc962ef0ede7e32f5c83939d9ccf83df80a543333471584664f1074af7d6fc9f6e0f4f'
        'e07799234693e69429b3df795b6e0eef435a2925ead14611be89266988eca0a316d0d5de96e62b1c20854dd87dfd1a6c03fc979f0e20ed99f28a4bacf92121e1'
        '1ded26c97801008d800be4032ef0b54f4b34f912a04803e2fbfbcb30858c4258858554cc4a99db62eeb731f33619eb64592db98648d9ae91aed3706e196696e1'
        'f563c62dc5515d22f9bef71b60c12f9c9af3bcd89cf66358259c3c97937b0d0a1a4b87059b0732c9e2a11703630f3b3edae411ae3b6f75efd55f649bc182058e'
        '4c25c27ecf4ed0f85559ae357f01c38e58f24b0429e2aab16de334c493b9df43dba8d18701da71b80a43eff354304d6fd3620c1fa3117d5701259e2ba50e832d'
        '4d8ad3580ece8dec560ab514f1717d1ffb03b456940f9182ab824c8a46a561347d429fc1061d72d32df40365c4cad76dc927f6a1fac088473fcfe256e8e1b268'
        'c2ced324689fd2ef57d899d9f3c7d1e86824ba9dbd58acb7ef30d71b55af73ed41409725e666e934a0f8587ba56f16762613a5aa7a2b1c997fd2e3ca701539bb'
        'e5581621d729182b22faf28e13fb91966a67f8061f22ad69e89b9b417c55be4775338e6ded628736f29aecec8619a1a53d2172c482974b4adeaffe3b3011298f'
        'b1a25e3493148e9fc7dd1115fdbe599e42c29ad3ec1ab656c7959d766c5f963aa4afb6dce9b9cd1fe241d6744c8d185e3e06df7c1474ee71613c6aecf7326751'
        'dec01a2331bfc4adc986543cc10eb7c869a718dfa5bd7b89647790cb7c9cff439052d2425f957c7a01ab499d46de581abf589f23a00a9e7eae95a7ecf8ed67b3'
        '4943a4246f294c809cb94e90ad2ad1f98c92c79f9a25dfe68f56ebe1afb1c714bdc70c4a384bba1d97bd1da568fcad93f7d47828082085bc6efa1584b583dada'
        '37189af6e1ca9aa14e539d5b13708c6d28991e04566b100d9a1f2bb3d1baf2d72e0150656dc40f7f4b39992297c9daf56bae31423b27620e9167965e0f75b8b9'
        '8a3b165a91fb59016d4a8cb10738ed9798b3601e912c790f467a03423124655f30b004cfe68fc1b383daa3c03e488e37959a20ebc002127d0f38ab663efc2951'
        '455666d31245f8d88e3a0d3b322bfb2099b2075c0c8294df546acffda489ba63c1a62393842ae27d4b2663196655c292459021e0729805b51f207aa90dc92f0b'
        'bc1c723627fad9f0db6e50917c6b68e45a272b038bb8f223ac1cfaca3c37ed591cb3586982628288ec2d51184e869f29e1ef30960aa2d2f45e923a4790f40dd5'
        '758322e21195317d1bdeb09e0dbb093459ccd156fe6d18a4b7519b3783a9a86e710450afb7857d869c31b79ac2f6c7a49702a318e666ceb8dcdf6ee11ede6c55'
        '0f06402808b8cc0757f2a121c693dc97f6a3c33737c021465f6883a9bd80d9fc5a2bd9d016e540e208d5dd2736afa322acf054bf5f2ac8e4b7022c5a768c8c3b')

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
         '0003-UPSTREAM-LoongArch-Improve-the-logging-of-disabling-.patch'
         '0004-UPSTREAM-efi-loongarch-Implement-efi_cache_sync_imag.patch'
         '0005-BACKPORT-FROMLIST-drm-Makefile-Move-tiny-drivers-bef.patch'
         '0006-FROMLIST-drm-radeon-Call-mmiowb-at-the-end-of-radeon.patch'
         '0007-FROMLIST-LoongArch-Update-the-flush-cache-policy.patch'
         '0008-FROMLIST-USB-core-Enable-root_hub-s-remote-wakeup-fo.patch'
         '0009-FROMLIST-scsi-Bypass-certain-SCSI-commands-on-disks-.patch'
         '0010-FROMLIST-PCI-Prevent-LS7A-Bus-Master-clearing-on-kex.patch'
         '0011-FROMLIST-RFC-drm-amdkfd-disable-HSA_AMD_SVM-on-Loong.patch'
         '0012-BACKPORT-FROMLIST-drm-ttm-save-the-device-s-DMA-cohe.patch'
         '0013-BACKPORT-FROMLIST-drm-ttm-downgrade-cached-to-write_.patch'
         '0014-FROMLIST-PCI-Release-BAR0-of-an-integrated-bridge-to.patch'
         '0015-FROMLIST-rust-export-BINDGEN_TARGET-from-a-separate-.patch'
         '0016-FROMLIST-rust-generate-a-fatal-error-if-BINDGEN_TARG.patch'
         '0017-FROMLIST-rust-add-a-Kconfig-function-to-test-for-sup.patch'
         '0018-FROMLIST-PCI-loongson-Override-PCIe-bridge-supported.patch'
         '0019-FROMLIST-loongarch-retrieve-CPU-package-ID-from-PPTT.patch'
         '0020-BACKPORT-FROMLIST-ACPI-PCI-check-if-the-root-io-spac.patch'
         '0021-FROMLIST-kbuild-install-extmod-build-do-not-exclude-.patch'
         '0022-FROMLIST-LoongArch-Add-flush_icache_all-local_flush_.patch'
         '0023-FROMLIST-LoongArch-Batch-icache-maintenance-for-jump.patch'
         '0024-FROMLIST-LoongArch-KVM-Add-DMSINTC-device-support.patch'
         '0025-FROMLIST-LoongArch-KVM-Add-dmsintc-inject-msi-to-the.patch'
         '0026-FROMLIST-LoongArch-detect-and-disable-sc.q-if-errati.patch'
         '0027-FROMLIST-ACPI-Enable-FPDT-on-LoongArch.patch'
         '0028-FROMLIST-LoongArch-add-spectre-boundry-for-syscall-d.patch'
         '0029-FROMLIST-dmaengine-loongson-New-directory-for-Loongs.patch'
         '0030-FROMLIST-dmaengine-loongson-loongson2-apb-Convert-to.patch'
         '0031-FROMLIST-dmaengine-loongson-loongson2-apb-Convert-to.patch'
         '0032-FROMLIST-dmaengine-loongson-loongson2-apb-Simplify-l.patch'
         '0033-FROMLIST-dt-bindings-dmaengine-Add-Loongson-Multi-Ch.patch'
         '0034-FROMLIST-dmaengine-loongson-New-driver-for-the-Loong.patch'
         '0035-FROMLIST-LoongArch-add-i2c-clocks-and-clock-div-para.patch'
         '0036-FROMLIST-iwlwifi-add-new-pci-id-for-6235.patch'
         '0037-FROMLIST-LoongArch-KVM-Fix-FPU-register-width-issue-.patch'
         '0038-FROMLIST-efi-loongarch-Randomize-kernel-preferred-ad.patch'
         '0039-FROMLIST-LoongArch-Skip-relocation-time-KASLR-if-alr.patch'
         '0040-FROMLIST-LoongArch-Avoid-initrd-overlap-during-kerne.patch'
         '0041-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
         '0042-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
         '0043-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
         '0044-LOONGSON-LoongArch-Add-canfd-support-for-ls2k3000.patch'
         '0045-LOONGSON-LoongArch-Align-FPU-register-state-to-32-by.patch'
         '0046-LOONGSON-cpufreq-loongson3-SMC-boost-test.patch'
         '0047-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch'
         '0048-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch'
         '0049-AOSCOS-loongarch-re-introduce-add_numamem_region-ini.patch'
         '0050-AOSCOS-loongarch-basic-boot-support-for-legacy-firmw.patch'
         '0051-AOSCOS-loongarch-parse-BPI-data-and-add-memory-mappi.patch'
         '0052-AOSCOS-loongarch-add-MADT-ACPI-table-conversion.patch'
         '0053-AOSCOS-loongarch-correct-missing-offset-of-PCI-root-.patch'
         '0054-AOSCOS-loongarch-fix-missing-dependency-info-in-DSDT.patch'
         '0055-AOSCOS-loongarch-fix-DMA-address-offset.patch'
         '0056-AOSCOS-loongarch-fix-HT_RX_INT_TRANS-register.patch'
         '0057-AOSCOS-arch-loongarch-add-la_ow_syscall-as-in-tree-m.patch'
         '0058-AOSCOS-la_ow_syscall-add-kconfig-for-module.patch'
         '0059-AOSCOS-Revert-rcu-Fix-rcu_barrier-VS-post-CPUHP_TEAR.patch'
         '0060-AOSCOS-drm-loongson-add-ls7a1000_support-module-para.patch'
         '0061-AOSCOS-drm-amdgpu-disable-ABM-Adaptive-Backlight-Man.patch'
         '0062-AOSCOS-kvm-disable-enable_virt_at_load-by-default.patch'
         '0063-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
         '0064-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
         '0065-AOSCOS-USB-core-only-enable-root_hub-wakeup-on-MACH_.patch'
         '0066-AOSCOS-gpio-loongson-64bit-Add-LS7A-GPIO-interrupt-s.patch'
         '0067-AOSCOS-ACPI-scan-Add-pwm_lookup_entry-for-PWM3-on-LS.patch'
         '0068-AOSCOS-Revert-FROMLIST-rust-generate-a-fatal-error-i.patch'
         '0069-AOSCOS-LoongArch-Canonicalize-the-CPU-package-ID-fro.patch'
         '0070-BORE-linux7.0-rc2-bore-6.6.3.patch'
         '0071-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
)
# vim:set ts=8 sts=2 sw=2 et:
