# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.0.14.arch1
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
        '946b177762e0c7103a8aad813c5d4883c9d70c1a570ed35f44ca9e8368fd1ea9fb17448de4b4bfa650467ab9d5d49e973f6212d0a0e0c9031f5308958a0a9864'
        'e7b5d91c9470a870bc036f1a03c36cca41034d392fca212ef188b9cad27c84cf2d526756e897a2de396a497f39c558b6fe169134d09a68dec813a0c234e193ba'
        '54defa48752c9668a37f7b4dcd20bc28e870caed32a528ebbc73912ee9a94573f3cfc4547f0524b43c61535629fd72d49f6446167be24630ba2729afb5172bd4'
        'cd33393c02552031b2b528480556f2e7d863ca81e19d2471c55d5e95bb205d471e2739cda7c175749362c5f88d0e4ad4fbda0776d9db96a4e6689c2cc24fa23b'
        '1995d693a10da81d9fdeedb9cb1432ee75824148188e900b69bfe955f7f659284008c92355d0ef0f6fe0ede39b17ea8a3e87b4cd7055faf8ecd866e0098b9485'
        'a5e1eb0630dd7c5da70fe58e6b5222847c4789f72e248deb1936dbd6d21e060ce7b10f567c5b608b46fbd6e0e571f7c129b994a212c73fd624d8ae45cb715e15'
        'c89767c844ea3b6d76e9bb8f6ded291b27a6806bc93298d510aabef5f38e59a1ec10dd48d2e94f031cb3b9ea11bf7167378679182168a1ba129c9d4cfd85978a'
        'dc2f299f69bbbc34e2f987fc6f3a627f9bd8755998dbd94cec2769ff91205c5b8f07a4f2baa72ee63f3236f41d429c8e939fdd67b368a2f6868b3889fe1944f4'
        '82a907720161b2948955cc6ae3dba91fa6c01c3bbc192f16c266379c1b49fe080fa219bb1076089d1ded2b2c4863863138e5a3b9d80e0ac4f42105b4a861bda6'
        '9b9802bf5d9435d6df808242455aa39f08ac5415b9fcea9345b2f0693092ab09edd55f21c062cb4bfb6820fccb1ff6f965c09aed796c73818aaa69c52859d012'
        '44900dcc1b993581070d0a905f2795e60a43b572871f1f257d4fd72c26b771c0d3bd2c0988cb0009d0442f9a11c65a9130232643e32a4829bfc090d7707b9ada'
        '329a1c3f717289c559c65d46496632f457d24eeb4201155ac67cf5fe68c9e94e7db6860b81362ff35f8341c3335a74bed6798fd74f42fe807129dd0b625a2624'
        'f651feac9233312343bf51746262bf551fd02de2abdba666f63a88005d38f94487fe23859f4cb899acdb172c19d9908ccf31e0b099e516b77f415000826e3529'
        '00e143e90ae0cde4380d93ee41e5709fe124e2ea430f01c1cc53731d30d3f88f7b3c42a53cc01a26e4f3580587f444d063ed3704d370862774e82ae5d8ac8d9f'
        '49254c9397bb4168eddacacc9f1f228640edea6ccb32e89828ac24b79f4fa4bb749dc29f6c83d9f3d23aae40724cf1033815a91a85dbfc4d23ea683f3f6d7dd6'
        '5ef9582c6b9e424cd674304311f61987fb295565e87cf4c20179aa71e66057ab9e2ff8eecd9f20911a93d2587eb014709b4c38757142dd5b0076f7e5355b9006'
        'e73b62f91a7a4c6a4442b983608cc131eb1729e8fde66a442ca814570ca4c3f0e2ca1d56305f1b42f8190dfe52b6711d7be46e6d7748ff6593bac332a3e78fcd'
        '0ed98f36d451c42115674cf6aecf6debd6f3061b210948bb4790c5a5ce641953241aa04cac126b0d3f92ce9920669a2cec6aa25a2c48918a73425a815b3445e0'
        '04245529d44b52f5206158afab13e9ea86bf4cc3ac9e0c9366bc6fe177b912c5491c5c9be589065664158a88b4bdadf35587561be4ba9c1bf8ca7109c5313f02'
        'cc6e3f176bd58e208a16b4b922f4a9ea742a7ca7b6cee0009321de2a954d15bdd8137e47d4b8bf8c6fab08453d87d6c3a07a958a8cc8f2d25f7a8ff6c2439415'
        '004b2e69e46fa578f7bc80aa091687d17640fc3c05ca4e389a58c27d598a82965760eb0ec67c80573ea1ee872b8a7d21db30c633c74a518c61a6270f2e9750e3'
        '0b75153b21e30ed9d2b7abf0ee1211064c0d72e44e535cb4af6ea2d277ced47dd8aad01e50c1e054c4c1106e3e3173dfb06400c4939bbaad1f95ac332198b559'
        '30d2782036ff6f1a1ad6c0600314b7b5ecefd2f296fd722c6476e6d9a993dd13d344e5c78263014823283f6f20496adda6999a0aa94b3067560cf1e343de0978'
        '6f855e9bc51f18623e596a7b03e4a925022c62a0ea8091d3952ac3bb5b9e2ea75b1ef98fa18d9d86b901542eef6b6341e6a96a9e596e881a2e5505cf1fff0c27'
        'a1622c7678c42e2a23dfa00be5162266be25ad501f8dc8cadd0f381a38e9b3b520ece8a8fd8dcd72a0919d51b55573d6ee8e8f524b54ae0550b0597e0b50f1d6'
        '50885247d03f00f1f0d79a59fc7a8f033c4ea59fd98225ad5705be43269f051989193cf3873a69d9b6dff7f45386ddfe76a5802bae5ba656cc6c5f9c657eab37'
        'afe1c94268ee1dcdd352d88f439c8f96549ccc872a0b3f53ef5504c8bb16efd6b1ec2f8e1870b11afdffd8da978b38395b9be7d66198f10b4d443c929e58cfa8'
        '83902f0fce1312d7c684f27b96811a6ebf0a4e6c033d0ca9b9a6d40b52f1c1d12ecad12d25c0d671ea56336b95702322dd883dad858ec6d20694c6154b0cf5d6'
        'f0d0722709f2ab04c1a6d71f919bf04c4c713362b5a7dc38d6a7e63ab387fa2a8f99c61276924239c0f4086081829f3feaa4c96ac933356604c197bdcc6e5900'
        'f454f64d41c3200f93c2bbe0710b4c1985337d2cd6cb676457570bb62e6f5067b00079387f10a7fc836d45b59ad6702a1976837abfd4b7ffaf05d4ef712e488c'
        'b035e5249647e2f5f16ea2b4a58ed5e216e7cd8b0716b0960428575297a37f11fa2f3a2c66343c889101041a7e84ae82787f23624bf52cdf857d86ce024a30c2'
        '8f535753f679632c5b2f0d3dca4556bd780a601efce749bcc59c8e5e9f78f8b42a18b636180bc39c2a71f0939e4e66365af57597c5d9c10f1f946584985f3585'
        'e86bf22643343d9214ca6d0e60405651b368976ba376961ac530eeabffa59dc10d94bd311d59bb4c8916c7e66c1e1b71f5c51a57d19946c4b89c77ba19823d1c'
        '3eb07ff4dc3bfacc293db6d1061ca88bd254b062372ee2ae4b063f07d6ce26355df41b32017330feba7e61e572fb22adc8571813c464aa79be621e7ccd527dff'
        'a72de903c3b9e35845b180f8326b169f67f2a7bdc1b688d49481ec1474408fd6689126d0f2c586bae4edb288ab0f1fd09a1accd33919f4030de2b7bdd4785472'
        'acbb97f919d64ca25172f508d8466de41d3a27e959d606c1dc616042bdbd70f4856efa387676e2c7a3195fcb5b3acbef1ed0fa16eae640ff76f3e96063d3b453'
        'a2c4307b7dc28ee09897096cfdc929f5729a17584257d376034d9de6e75a1a693db96d6e9b7b8af1285b4eb0cf1c43883aa4286965f1717a9ed7ce4dd75817f6'
        'bf0086bbb23682a89bd9e6331722784825952f6b40d4f2b156a25a96ea70fb224881492904e2170bfaf741bdb417a1c3f9f7f2eea6c4f8fcb9471a37deafb2e7'
        '533ee2622febd477af404d13ee1bb8dbc0c45f83dcab70ce2fa403ea5a1eaa09ddc4421354c6febbc7d30d711b638d06980689dcd62a8b84b8d36a25cd76117f'
        'fe9a313276a8a9b6a1d03f94b2e858c5bd74660fcbf704c166042ae7d56437e2ed4121c34dbc881c1d34d85ab2c01a3391deee95ede6482a48a4ca474af7a80b'
        '7280af5fb31c26cce64b1e2734136576f059360f7a0aea75815414842ec0bc3b44055a972fc9639a412931328230ea9459659dd60834bfb3757e18cbba395dcf'
        '7db04fb15ee6e6e032ada68ed10eef3b6e8222f3292d59ff9d12f33a37bc7d841efb51c0493f32141b9aacabf3d62c7282ce25c3f5ac4ed1012731c3b8f14fe4'
        '70c9ada5fe2727d645e9828231c1e05026f5d3cb5971f9d423c34c7f4ecef11459794e175b6a283e92c583cc4b5d7600d15ebe2afb428ca472b6bb71628b4ad8'
        '859c8ec015a2ab6259f58b7202f8e5ded51e4b504ff556d532bd5a1c9f0b588acc3bd5d1adebf10f35fb487f3d0e0d41c492632920eced2aeb718605eca44e12'
        '41717183e28a912f5f6fd86bfaa60ff41d94f038784aab1d7a4ca8348d6a295dd9d26fb77dbea0c5d4fe48e5265c83f05e5301167af4e19a50d664b9fb77aeba'
        '443e18f3f6d218afdcaabe84630c9cd012317ffacfaf7a407a57c97c11c56fcff9ec680c36f07bd1439517b0bc57251f8ccd29cf2fb821b60c654bf9904ed7d6'
        'db74f8db32214f205ce160bd2e71f177511d23c26957ad3435cfedf9c5dbbeedb57fbbe9468a79d02383c4c7372dab936a16f6994fce52199f7c312b0057314d'
        '28f76bfbef4fa85b37813bce92db80b46b9dd0a6c87859125efa400bca6413cf8007429dbe817219ca3a3e5a11df8eaaa474e0c312c9df3462edd2ab9e69b949'
        'f9d552bdbf20784e96ab30dd37ae7cc2e1b2f335f39fa66ca0a47d9e3f8873e795b488c991cdba660393f370880ded85f01d10eefbd8b85292ecfae05aa33303'
        '1490a9967b3ca7a320f3c8bd9beb0ecb8f627a8ec7870a58f8583bcd4e71517c4931f02ca1ead413e963cf0165ac13defbed223cdbf773b2898563c7eefe2172'
        'e352fe1d37c1f3ba92071316901595cd689b15dae77e12e9caaf81e6ae4263968dafb03d9b43b5cc9c6cefb6abe8ac8c39ba744a8aae0450fe5cde697eb318ac'
        '612390902513f58849601d3106f8d8f0ea285ce081e9d4b9ef013ed0a6565efb98546b5ce51d1fe2d94396759b4eadf34cd0d3c53e0d1a5241da735a9f552e58'
        '4a619b604e5ae4c4e52f77bec9b762cbb029e24c235f636e7f87b6a5df7cef0a71b6e9dd5e83a6e09fa5bda1a5ce207dd55f271475211e0ba161518f573f0177'
        '8e7a7f0e63ee4203cf01abbf879c0b70bfa1d4bf3a22325e507f63a06d59994d995dc3268d14c9c2bb4c719d3fa810697ab7fe32263b752897b7ac072b1f46a2'
        '2c1c0b943f8a924c6bbc89359651212af61f68e08744c9162817afce58f390dee4b94f0c97b262acb087d8ed8215a4d45191027c48736e723dc1be3b8d04db9b'
        'f0d11259bb2b5d0dd479f7f9dd16e2bdfb0143f7f3b1029a13d17105b51ba3e80425d9bfae72242c356435330f9d30546f8c53420f81ae52e132a873ecbf4c57'
        'c29221dc9c2d10520ae3821137a3b54b923efc446cca18626610e435814c61ab03ec4e2040964f72ae1b09ae66be948bf55a73e22349222d743912c2c100206d'
        '929cf553df9f2fda039909a6a9888c9343bfd44dddd2cded082dd338f71f7f1c6861726190e3d72c13e78238358d57f2cb8c7d581451eea8b9f1526ac69c8e1f'
        'dc451936c799b398833d89e80078ba1a946d66a5869feaa4a5d7873d40c38a27f1d7edba5350e9304adca5837709ddaac61a7fad2c1b193c1b1682cfd2868277'
        '7764d40f2159e97ec946170f92bc8d0766149fe92a0cb089e5e311f31bb87e3c629172b74ba51b1cf6951fb468dab2a3693ff4eda973f2f06234e1bec0fe3523'
        '4346eb24c81548d507f8c1edaf3210bd5433c8578180574ee9f4c9237fff60de01833e52a6e9ac268be04ef0bf8ae8cc47150bc16d2412cc83887aad798532cc'
        '7d4b2fcbea23875fd8c87ba8da550d7b0359bde9bdd623861be61e1707b70edfec527451aeab8af09e9a28f0437b5fac894cfb22968ef1bfb61ab46dee496b2d'
        '58b6de7084452ba8d43c239a1f0328465863d75f7ecdd071ed3eecacf3ba4674fa64ccedd0424a9da9134ef52d4e5e9f3bccf939e1bb667360baf59f0ec5be6f'
        '2d5527999d70dce97ac571861598d8808d09668ab9f0854794e4b06bd900b3526ada5a8d04d5c1957dfefcf30f0e1c7b6a81f1bafa0200f44229688d79a36510'
        '00fbf466bc172c2ef5a3ce2aa81ae0b62f27add69fb78d0da54cbdf9a8665c87ff52ee0ece4c143a39b5e352c10bbe683007e2560d142ec135ac6905a824e0a3'
        '1970e1f96f13b639f8c1b5b6d245382e7b4c235802e92a1e2f3652ae8332a36c230134122a6b13d5f42f266a0c1d479afa09e63f2cc9f3c70ea6a234904544b7'
        'c361e948f2acb14d707a53ef5760736cbfa41f2bc85b1125c5227296f0aca75467bae919f93ba03d2e0ab82ba1862b98ed473f1e32a855c4a3eb6bfd1146750b'
        '6b8647ae320a7a252029dba5a65985b65766cdbc108913ffb66ccb1c42c124cc23eec86791dd78f630dd90bcccff3bdd86e8b0c5ebe2ce3b1acd2855f13d8a88'
        '2aaf398d94fef580b9f963d4c218a8ac1c0a5a8c4bbf9b63af4e4e4eaf2c62648753f9d54045971e54aacd8db443b4cdf1c79ff7efb0e2a6eb4e160f86e51f55'
        '4d01c24a20a0371b6dd33e4a051f538ac587345c6a33a2c99fc4767759b27d82b06b7e8c93d1d02a800e98d29b5b067c60783554f7ead1ba4efd531576fbc8b1')

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
         '0069-BORE-linux7.0-rc2-bore-6.6.3.patch'
         '0070-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
)
# vim:set ts=8 sts=2 sw=2 et:
