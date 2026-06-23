# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.0.13.arch1
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
b2sums=('c92878038062d7f41f805fa8d2bcbc4f1621c7d07e6b210b0ed03b3aa078832b4978761c391db3583459902acb1b22072ee5ebbcd6e37e9e263308b9c9521a5d'
        'SKIP'
        'ae188d8aea54fcf1d0851951d44071914171c880fb635467fd11e10585b886b65cf4f7313b6005c050c1eceb8f640d2a22bcc0699ecda9847fdec050765baef4'
        'SKIP'
        'dafee1f25d231199834869a5ce76a85eebb3c1ceac86f604270e93a40a22f29bcf797822481aff5aa5020c12359b9ad87ad8e0d36727166522510a07539d69d4'
        '652069e50060a3d84530f004f7064d98d6ac9bb02e690a3510d092d0df17598c9b3d564ae07fdb0dbbecc68d2d12d58c4c78c02cc08fbcbb8c01ba6e6256d922'
        '7b59edcee464209b0ff2e4b06c58babdc3d56801e1f73351bf6f140b39c53feb96d786434cb8b0db39ac94cf4ef905dec9c158758c4e41aeea16b9fa7f21c3f2'
        '82bb78c66948a572f35c8f0b6ba924e122a075632efb304693dfad2331898accdc80610d187e93ba5e18edd7f12131bea1ea2cd31b4987047cfe1bd6079eb3e6'
        '0a2c992f28dd8940b28106ab8b262586e50f31253a6042ec949bfff0412c13860aa10090ddc383b60ded42503963d6958ff48b8fa091dc22b02a4d42e540ccf7'
        '64fb14a8f200027e32661dfd4abc9c60b344bbcb2274c949e3c1be85f59438f1dbbed66ad87040519d3f9cb55a331faf3bc6c917540faaba17480bffb74e43dd'
        '70bd6f026f2516a011eb5ca5dbb5b0771358315182275b43c73882a90065ec08520bd235067baa81ac8163441bd0452304854def15bb6c0f33577da85f8d9463'
        '65cd19f3c679e72a3d3268beb95c86abe6d4f7711ca70bbbeb022a320ab616fb5c86cc40285b9f48118a0a239cc1a87f6d69dd5ce491a273c660ec94d6b84eec'
        'ece481687455cdc94a5bd0c107c6326c51f347a6652ce6fdcfdd7fa06a1c08cd5d26745a91eb0f638a92f839df313dc8e6ff673b1532ea8437b01ca0e1692b28'
        'd77df2fb447fa03cbd4c26692049002feb74d22d9739d98200ddd2d89d3f38afdc964996aef71bd25bdfd219c6f3b1b1cf24681e9be08a99b780ca24d3715eff'
        'b5cab408e240c910e380c2d040c3b9969603bf92ee4b6e7bacad3bf1f0834f53b4e62baeec0c17d2642f5c98317772ddd366571a603a05e751ea209469f6ee9b'
        'a7920e0cb2792c75428cbcae5974f1de81f70492f39cfd51493c5d84d0bb385c704d863c8404732d113b43ce75cff09fcee96ef3c6fc5239bd38a16362da52a8'
        '6f64eed6c17e1a9331c12719eef846e4e9e5511ecbd8fe442d6824596eb0bf54985e5250651e5ce82dbd9acad1687afa0b6157614ea851eed1ff62f6d503404c'
        '6cab5790a84742ae3232b323eab3bc8cd32a4c1f316e80af394762967a3b13ea7e912125d67ff06da72546f09c813890d429994993bc3f0bca1f4fd491d2958e'
        '8326ac1957a1ac80f7353cbc6460799b5a16e225dd10295a75beaff39d7ce0849a44265f0be7bdc125628d9e373df64feb724d530d60cfca373d410e578f553d'
        '6452ad2cfb6a47a94d0bf78f33be9e521dde5404b5f5b1e58b85a91b81eb5f67f7dea7aa2ccd31a569c864fa552bf9cefca35d89516fca53363a85d1e45e5070'
        '82b5dc3aadba71ef37477961ae4635c8821d0a0b347e1eff4e1feaccc131fa2f8c12a9f1c3dff6cc158a8b3b14b05f0ffd334beb80fca3c2dc7dc688b394dd69'
        'bb49eed59aba48e60e724ae9db21507fbf017c58049c9e690182fac98a65f7f4b4443615801de197517f223feda9e98ef51a2c19dc1967f7489563c153450dc0'
        '974a890ab3b03833a641bb0800ee23ada198cc0740632613d21fc915373b6b7df1861e51c88f0fa8a7b9e26d1bfda791cedb5824e8901a48869a5a21bcba9ff0'
        'c5474dc9627383ed002f9e9f71692281ac38fd85bc872ace8cfa79f0da54ce60a44c50804837c5c22b1db6c11c5e758d4144dd416e559e70dccfaf53664774c3'
        '0bc9fc90e4516ace9cdf2f23c52fd0015e11f47d5adb36bbf7e3fd2fc4058577c2a50628228997364659ea2d2d3ebd99c3303878686826190e674c2b920aaf8e'
        '686aa34e75c3c61ac1b9b0d35022b0163ff72b57525fee866ec1092adc4e16dbb9c196ed80d02c671ecf7e803bd83041e41e4282e8be0bd024bd17546b1df40a'
        '3572103fb5f850bddced14ea4baa86ef91fc374b0618a1ca95027e6d2990696edf43cc07a4c2ba6d783654ac60cc3e8ca629b91b1b2108f4462497f311a47539'
        '07c07a19f6be149d597e636e4b932d8a3d58c36a0a56c8b8c647258c3cab80da4dd6aea481915a90a9f1a2df94bb0a086e24bed6e381cb99318aea721b48b437'
        '0a2f02f0f12723a64a8aac782d171e84d5e0bc26af828fb9ddd5cf2e9bb769753918e0d3d8680d66c469e4165dc334600529307569e6f37491b050e476a4aaab'
        '022b06e737a5ff59feb22d1634c0e864b03bc762cfa16fd11581d35a47f76ce2a272f19e7beb52a6f17aa0e84cdf11019c5c0a87c3cab47471f0db8feebdf8f6'
        'e7af5222ebd9f5feebe1b1f45c329366b462676902100f7807e112b8dfc85588242c7003f8fe549e62761fd63102b800bfcb31292a1c4fb41141706decf17e7f'
        'ec50182f8dc6e01b1b541e2fa7dce39944a4de9a325a25abf9933bab0fe32ef41acd28ef57bb5cd229954f853c14721c9068935669dec264c7e998eb315cb557'
        '71f220229d07fdbe1b7e0c23499a435eb2677c7791ae102b989362590be1ecf2d5e60d0999d1638ea834a54c36305a022717eeee65b48d450b3aad6ac31b8ffa'
        'ea49b8072a132c68647dbc34d47b354c20c041f3af489d0c3997fcd079a419817779dee6f6df4b216280e965e55a2ab870fda7ca3c2bdd411e562a26ba09d423'
        '5e8dfaf4d4e151e27c7ea7aa9464b3ec01e69c20753b9c76f377641e71d7501bd2369b7d04073c66d756259316bd0f66efaf1ab861317388cfbcc668de333399'
        '620ddcdd19855bf798390bc23ce7e355fe81bd5ae1e7594b969d7902fa0ac2d135e2617e4aefd17e6d530ee68ce4e0808e5734292f57cbc49ccf39bc0dd6ca80'
        'e6972a3e451ec6db030e98e0ab5c3b68d0a44a7671662688d9cf7796a0b93233fc4e621a08093449445ebb6ff02b9c2b960f2fb8a6bb30637a81aef9e82618eb'
        '7353d75c9af1e147a3e60cae7279188444e9a73c615605b7b697763aed78d36f0339c61a837f0933c0a0978556bef0f41ac7e3df69087e087b8f76da9d9570c6'
        '4c81a4c4e972d0b16c7a1918972866fe21d9c7a1c9190088bf4f7c7e270548597bd91ef0f237063e08e1d57a0024515653047a29d125024830e38c1752b0b907'
        '437a1459435f60fb2327b065c0972f63b9f05d536b20aace34fac4f13255fbc644d1fd0f10053f76b6343f8a7a89b6d5e744da9783c38f33662962c672332f3a'
        'd4ff81251a51bb83a2f962e952a96084a6719b74d5566e02c0d97b95f4786f9dc41da088964a43dfe03d4ce4a354143453e6f4fd811eaaeaecbc9f7f1461dde6'
        '95496ab6f8e2d768c18cbf518878b0a362ecfac3836c0d6bd0fb06c95b150f71c6b4d7d1e0ae6564fb9bd647f640536cdeb40fb182a63dfbca01f6b30043caea'
        'a93e0b6f71acdc3ed35c1e4d81982131b8c6378411674ddfa9bffd1c8d26b1eded296b1eddec8a3a720ae77f1c24223d9a7d173acd5e5b43d49e9df1291e0dec'
        'd3131f40fc581e1800def7e14db8939ef4533776fe95158b46e5203dacfc05b870ee2777da5ac69fd48da3ada1bf2ad096eb3b95ff248099abb5377d7d29bd82'
        '8a79529c1836fc015b22ba0d538eb4137d83cc43e3997231f67462f4fec8373c86bc349b3a968a530ec87d3eef1387648b1d79ad0c224e0756ec4d639b4eada2'
        '4e83ebfcb431bc61a6d277b5641e124c77fc165a508191afffa30c4b965045362a794df09bb017d89b97f2d7fd5c0f02bf059c596cd869a30b808dff7c5cad12'
        'a29ca868c30b1cf37cfa78cc5dab13f2f5eb3770ebf292eefe5b0e469791aff835850f63c2d35fd3b97d7e102868d23e96551b0081680063d6cd9a0ea1331f79'
        'd2f442e3e1da840a46d2b783c8b5dbd84f54af8b806c26d75904e3f98cee3338afe6abc989ee4481a478aa480032db5036df185a41353f6f8d9bf025731f43ce'
        'da950affbab72fff70e0ddd92685ebed1b250a666654cc3a2972876fe0cec1625097c9416af11ac5ae750856ec94e7ad66a6c515fcd1b2bfbd78a6eb3590f80a'
        'a636faa6647d8f33eb253424036e36e66133388fa6beb298bbb053854a8d54df31d515484e446b94f4e08f70f1934ac360e7b09d51be801eb65c7ec78b57439e'
        'c76d58326ba2bf6f5b550558f6f9cd4d935d830f99b0316cd2d2323a2d70a97eaf7be8ff940a6189a150f86c38c6d0542b275d19b3c2aaf72b02452ad829f046'
        'a197da04f1b920a13db47cc4f6b6da67c70a445b7470da3e1cde8ca05c514951f92ee79a5c0fd0214a54879f6774146359d7dec9365d51fa98bf77c32a95a2fb'
        'f0135fb2e86056dba2e055f09bd07c719bf4416edc71bdb5cb60a40304eff18b4aab40bbb6ad135aa333e2e57cee1cdbfaf2f1b4f6b1b590d08f785585690c37'
        '6a02bbb180c9f727b5c3bffa989b6f86a816caca742479e0f64e2ebde9d365b462b802059a43b30bae4b0212aa8b93a92d445fc29d81dbd5782973ebffe242b7'
        '89c592802a283050c6bd16a5091d7b66e812df16ff25f5a96fc2c52a3aef57139506018905be480f7cc83016f891642c9e45986eac6d2cdeb1a8eadd904de314'
        'f97758e4ed3a630e535094185c74d848977e20697b181fba7ce49153720c0ae61c94bcc5968077b341aac99bf1528b85ec7b0fff53aeceab3b127650f07a3daa'
        'ec0703cfb5b97b9da92ea0f03de2fd78894901ee2a5cb09399741aa0bcad044df5037fa45e84e8b525a1f8e7d58c0d7abca50527fefd23ba8e6caf77899d69a8'
        '331a83dbba30d69b1bbc3a2f8ae94fbdf6862af6da4a58b417d23c01f64832fa12eccb10b417dc7ca135ac8260c47b12e8a5938522730b98d86e8b667e7a12a9'
        'eb58edbb775e5fe594f0a4b0b1125fa9f52e3f8f17119dbe024ecbf6121c31b5c50985e14a9dc3babd5951c76bdf5d3435b6723144b89ee4e3e9ee5fd9df5217'
        'f0b323dc242bbd399cdfa375575fc39efa9054274944861de1b88eb9c41ce77dd979e64eede9b8f36c56cb1600b8d0e5b663f13c0debbf6f8584608747bac31a'
        'f21ddc00fe39e0bbe7a7f42055a81f8be3b608b8347eaecf05da4d2849560afeef4f649745b5276e9838ca95d562ceed6503c23bae55bbe8df71e90bb9c8014a'
        '782b09c45618d35d91d137fc70956f7a120b7ffc7ee408239aa558ca1bc7a84c4ee2175ec6846ba6b7988dea368257435799a6c382ff22ea9a9f0e7f27b67766'
        '6304b426673f7438015864e86fd2232a54834ec5c237cf626ed43573ade49911590a3ef5c95c5247d05126aae032d3b8a9855e3c20520515a4291f1974400720'
        'c2824452afe947e056e17a83e95a589f44576a48a10a79ab80059071b631fedea6e858c9be333d5918335347d31b3c385cb8007b7b2c4dcd137e14719e302e8b'
        'bce372e73857179969ce604ba664bf208a326f66ad31895c891db0650a694703fd7be6211ad43e8d42508a3eb69f5d8a1bf7621d2e6e7dd1ca661a24c4cf2498'
        'aaec88f08ee17d9158c2c06f498cc94541a79604419554869d0a4e96da0a784078dd40a1ec7ad1cbfd550b30a1e83a2d7b87076ebfe183fbe57090a1f4004c19'
        'fa06bbd96e3097d3c5e3b037dd0bb3caa3899bbf1b617be3ca6d83a8c659b64b250c09f1188b27823612c4b0cc19c66871bc015826563bf98b87c4a9d393cd86'
        '3f886dfc9ce0cb780b23a4fb950b342dafb0bd6fe0fe18ed7ccee0334b10900acce4fea2a39dbe0aede8e653354d23594353ce68bf9b9ae5e2795e8135890d3b'
        '49772592f081ecbd87680eefc1ee32847a30c81edb89e7001548580b08dd68aed21a325fce6d3be7f3fb440a970f4d978114803066a8117d32d0eec8717bbf4b'
        'af5b98d2db755f98507b96fb88ad85be9527ecf129172a7b33087957c67a0b74250d3b7d802694c2ebfdefc30be12ef86ed9f28827a31836f4f3504da0a90eaa'
        '20afbc6ef280ba525dffcf5fd400c2270ce1340042a458c0029552e7dffb81eb8ed7dd8ff02ddc365d513bca85498ae63019db163e9337f73b7377d9d00e3cd2'
        '92c28145daf2214a5147af2b0a32ceb36b14fd739a0d44df5f435757693102e9df4f51762fbb775251a45978139728627a0d90f0f7504fa060be940b740a57bc'
        '92025c5de8fbe7a8466c8d27eeda62786cc3615ef7fcd822475d560e274403a086ed5646dedba915bd2345205b15147d0b72101026c713fa385005dba8e89d24'
        'da9f68523760db164d98f231492d21ef99a4f79996f9d6b0fdee7985b52896a555163f8e1ce9b2b68f5134567039afc43ae062f2eb93bfd3858406bd4cbb72cc'
        '536cd266dbab10e6789bbebed67ce0f789fa5e45fd1007eb2cb18088b262970d9e5de6e9ce5120a8ab2ea870eb4c224e27f3f655fae59e287243278b23bf32ba'
        '4dc088692def5c91319e583ff64d5b43452475873db2c494e923958076a907fe75e28cab5bda101b9769f161065fb506d2ef2905f7cb97cd4fc46d3cb2361c08'
        '3c4989c3a1f15da1ae3c0d3e763543dd3f573d839de37eada698af7250b9dcacbd8961176a5b2cc50056620adee8045a09a3534df073b6e515801c9a63bdd389'
        'bc57eb3fdf76f419b850483d0716ca21b6497e1a9171c00205fd37c683b7df49e82913ecc3df71ba8157760b856a70d3cb85298392a5d18bcf0e2fad59289980'
        'a40e59a3c27f291617e14b9b9e13c5c3650e46085635fc424e48a6835b04cf639afd83a0f1b6a0ee14f54ceb78c65399ed7e9b0d1e3b5300e1cbbf835a7dcaab')

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
