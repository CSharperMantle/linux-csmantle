# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=6.19.arch0
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
  # FIXME: -arch0 packages don't have upstream patches.
  #$url/releases/download/$_srctag/linux-$_srctag.patch.zst{,.sig}
  config  # the main kernel config file
)
validpgpkeys=(
  ABAF11C65A2970B130ABE3C479BE3E4300411886  # Linus Torvalds
  647F28654894E3BD457199BE38DBBDC86092693E  # Greg Kroah-Hartman
  83BC8889351B5DEBBB68416EB8AC08600F108CDF  # Jan Alexander Steffens (heftig)
)
# https://www.kernel.org/pub/linux/kernel/v6.x/sha256sums.asc
sha256sums=('303079a8250b8f381f82b03f90463d12ac98d4f6b149b761ea75af1323521357'
            'SKIP'
            '9fed188f89847418aaf6416b64457a30bee34dcd0fa42a84dbd0f4dfca063402'
            '157126a09f9a0db855ccada3d560c5a2e469c91186596b7f6b15afd2b983b67f'
            '3240d8042fdf42c1aa8039c0ac4fdaeaa4fd6eb5d9c176914c39b6b477ac6844'
            '2812bf0e5c8b5f05964fa3620873a137232ae976f60c1984238af21e79662ed7'
            'e04d395ae02c19385700a5e33a7aec226364c5a3d12cf30ec51514c5004f34a7'
            '20beb4fa6c08091b6937bd59a9d7223211dc75e2b738e69a191ad1b3f447a33b'
            'b2a3335738b2f679f80a34dc45b572c701dca5902cc79965aeb41d78d7779c37'
            '254885bdf8e217cc96c43defae11cff3d8a3869db3fabdcaef283cf1dd908e33'
            'ed01860c78330cc220620d3c1188a1c147613b4b9d1acf783127b823d1e119a9'
            '640e3601d34108e01a68a6cb8c070005b4d1ccd3f9d5b16a812080c09bbf5f86'
            '510cc5d925dbb35503f4193c6a77d760fcf16655b1c1a5d119927474932c0540'
            'cd7432dc1f51e35de15673bc7d8c6bc31c1183d24472cae8a35c116617eb75b6'
            'ef39f9c9c0a0e9e04053584fabe4c076bbd32ca3e72048db1d0ccbaee7f9f985'
            '8b2af5406b4d76e7b535ac62dcb10d26e1c11d9a89e48cc751c629c9402e7150'
            '4a37633226d11242cfd5cba601b1dad4c4ff280d91787902d69796ea28fe360c'
            '67b80f6b999b8f3f54287fc524a6b4b358d450a9b39e4ed0c09d092079c2f3e3'
            '3bddbb1b08d47903bf17be47768093ece473f758b76e619eee7c5dd929800fb6'
            '797ac9a5aba582fe19a5fe316df07ac203b25adc6d4fb3243f9de2b410a09812'
            '0c560ba8d9f170b11228c098d3bec6b6f50e847bf11da6a610765d0ffc15106a'
            '180d6863a268c4a1f62461dddff6285bdfa0787e434475979ad05b4a65675e98'
            '5e90f3165601440336535cb04b0f79e2d9cb35e0b1ab356772a5fb73f18dd1e8'
            '28c232dfcd5d5014cff8de02ff958bee3aafd669e98e004aff9131c72f5f5716'
            '2e0aace96520adba272df082636fcae9a33e6faf3d97bba635a5f2e997e9552b'
            '75a6fb3cd4d42d98d35e019a992720282566d58f04e744c9952dd9bed6fbb39c'
            '08ed8b20aaf74c85c53279f4d6521b52b9fdc0fc06a67373d242893c155505cc'
            'd06841b2c62e683e87557e03378fcbd2c99b202880708f33befbe5a401583d1c'
            'c24b9d8ad84911bbf0b94215b68331e6c0e5100d008ac90c0287d078d6e35ae8'
            '104c1c617de3457e16b619040d4794499f40cd3f5326a7ff5546e4ed75e58846'
            '7a205173e2e1604513a0976775214a70ec3af2e76279bd2fec851d747b59f1b6'
            'ea7ccd2a009520b17946aaa32a29711ef041df91102f8791c8825561dae084aa'
            '4aa2fbd223e42720bf55e2a793151b30748cf9ebb2dd8a412e235303d72da32a'
            '6c6c61db118a61d9fd6e94052da2de7a4b01cd22791d49e0a85f69e48d8239da'
            'd96576fc184e6e6bcc93bea8b0b54af3d9f1aac49059de3d83d8dc76883a1980'
            '785e5bdcc5d18954bf2ae92f35dc689788b22f02d2f89fa2b4ff7084dc67b14f'
            'b7d094391ad4b69c0ca7f252949500bc12b5533efb9f9de47890f20440512ca5'
            'c4bb3d1825d03687bc1a70c4d7c564a863be2a608120af4ce99b699543dd18ae'
            '04662be683ad0b7f43e85190ac95fa2db79274742ef2fff51b21e1962240cd3b'
            'f862e387c80868387b5c290196451b4b017c2d5a56fcc0bc0e0e90d8743b3728'
            '6d53d28fa4ab288e4c282dda96354964af90cfb49853a4447833aac2c8afc406'
            'ab358394f6d09dfd95a628711bfc9b90f31f9ff3b4dbb7f8c5c8600ec147b8df'
            'fb314cd132ccce38bc5c33be896031a5ea9cdeb62a11478158b19d15632c6176'
            '84d7454b63a6de1ccd47ba928ed2d3f3dc98e11bd45b6f4f31c494b837302b48'
            '1a0d60004306d55890cea2975debdc7464e209138370af73eedbce4d2269b0f0'
            'a68674db8ea7c6aff4aec47667ebf116ac535ba4a2b4c7668ecb75a0e6bb1820'
            '73cf33cfe1eb62fdec988a90fc88f27406abd3232c9b5b8fc2f564704d3b52c1'
            '5d5b27b1fc2176ceb52d0ef5842148efd486c58778c22f3c1d9813c0a82a4945'
            '20326f8c070dd59babb82743ca6890080e0a217e6be000db40f0037c8ed1e70c'
            '63ee18791b136d9a0a70c72535915ca3308a9283db8b23e1c3efb9dfa421bd05'
            '983ddd5cdda7efaa5fa0488dcc3a1823385a1d7ed6e668ddf705c5c20f0a5467'
            'cff01209c1dc89e38ec6b6d07c75d099ce1d25fd50a0fb784c0f1a239d84a6fe'
            'cf76f38a0148b847dfd8d090c9287bb19637ff121060f64b8f9e68d95de15560'
            'b9d605aa1d3bfc2e99bc46aff0b1d2ebf56662733c8f7e4274d0435f9da791e6'
            'cd98d60d8b7a2f8f5d67bb174be39cb7b516d3ea1edb4e64b2cb4c1dfc02edab'
            '1336532bb85f3e6d6ca8bd056f27445bca79280585a6f3e34029c81bde3be194'
            '997bd20a237ae7059c2b66cd2c68a24b804c21d1c60990077898472dc239eb07'
            'c80733bb09d877caadd9f6a2cd483a9073a7e350877d40d7a5d3829a6e6d674f'
            '33b9bb5a16d841829c6266fa79c236803238124933c139472067b0e299e31301'
            '1e2a133828e051d0cb7513da8636e4d6d00ed7f3a5bad502f3532e8a2bd66382'
            '0f6a997a9c77d799f31143d9f788b39b7a9af260f73076ebe18adba4271020e5'
            'b35c93f70899b9f37eeccb8cc38d9de8ef44c9d2ff2973ce14c97b30c6871694'
            '64f270e9179b5c19312732868656957565988d9cd3aeb91964a5da46bf77c15d'
            '86ea374d7fd5af4fc18cd4e305500509938ebba1c32cf356f69a586adb972dbc'
            'a5e10d1a3d534120b64cb02e5a1cfd96f949fb91c4cffe2eb6709a4f0497d6a6'
            'd7e9126fd6d5a8ac0b6ab402585ccc420c0cb5934022e4919f3a64cb260be701'
            '25c2774879d66ef84e2e8d076ad85cc45c208095c76813e85d87e5433d0e00e8'
            '30b8da58e7cf0bfc7536bf6f85044114633a4f92002557b0765f210d1d009c81'
            'f373a94db54b31ccff1f875f21bb8cae6901ac30c6956e2eca38c82599fc1771'
            '16c7623f4079c2f8d5bd4be5eedc078d8fd4cc810361c98b6bdb263893402641'
            'de63683ace5ca258d19ce4cba66a7a960ae1025fb4de5b6b990c93e2bf262922'
            '289a7a7fb447a0a47e034a4383b231d38cef16c8368e58c74a445a3de8b156b8'
            'f426351e805804fd3ad8041672ffe4e2017d4802590b69adb87c6d9df29be98f'
            '4e37b0b64f9a3d9da7e1506dea2d33f778032e0593bc81468ecaafc20b65c54e'
            'c272b6dd05a2a221de2cb0d31b5e8937b356149369894b407bec5a792b1661b2')
b2sums=('d1551c058e9a1201a0fa769b427255f13bb0d73fdd384e2c0302956cc9a1eeba255b013fa87a15fdad508bc00fdae2085590572c76cfe20fe2af31ba87b7d289'
        'SKIP'
        'bef3377ad86440af76e9dde4c29c9f4aaad42f5fe343f7d31f5eb537d6d358602f996f5d63986af275f2e92f94e71dc28c320edc8c03d05bd64dbd8ed23d75dc'
        'dfd366b283243f95c318471fe35e3a36646a38388dd6c4d9746bc981985a02ea303d75127244e9feac14564a8f49385483dfb56a8842814bdf97ca747bc2a4d5'
        'a0903f0cf1edd06558f1fc1725a76ffbf8709593201b0e60ad753c20fc4d856d5fe1ee3cb2e76266f827cd1b3a8ccb09ae3fa3bfbd5efcbd3b2f81faf46e6d0a'
        'a8fb973dde49cc8e88b203048318f3495c17baea86d31104bd4c323326308ed1682df0bf27f47cc40270e6c2ccf9751049db214db8404cc320537aa995504930'
        'da5d8257c151f3814398357da1a28bdbe82bf575626870cad602f023a005798be04352566fa4848c832b0deab126f6cdd9239224ccd2483e9610888ff788f097'
        'af9d17fe654a2e20f977348459f0b45b84942be8afc6c4466139cc8e9b705a62a2b1d4eb8d4b45eebd119c5c5a0872c1fd20f59ac968c92267f8e35d308d3a5f'
        'e63faef4672650b65175c65db8371ab1e6ee4803ae834211c06ea9f3ae7b9e2a0df690726a62f23deceb486994de41c5e01d2071aae1397e6123410770bf5cfc'
        'f846b4dca686ab507b108299f6239f1b8e527be6a76f9a3a3cb4e10d35fb7bc2818ff2d812c2f8142965768407e5dcddac3b2e5f9cee0df9a78ae24613baee44'
        '64a015732a1a753415bc507331b4a4e665cdd01cb92cb4adb476214763f4afcc331161d0615d92d360d7257f4591286300d610992ae6801d6b13186cfe8be7a5'
        'b1dcc82e2b5452eac7239c84ba78d0ed09477097afcbb27f1d063b858d176588928d00d58fa01b273ffbd1841473fbe61469a5bddfb251e68e101bb5ba222056'
        '266875c7e81f32866cefa5c8ea95d3b622cd5be33220851f3a1cd2dad0a8d872a3365f59bc1393f01b9844767fe3ead03df0d997df5092a5f82b404ec1e9ddfa'
        'a8fa4cb41cf35307fca9486da462c99588512c0dc889aca7dd72d66a5fff1a0e46cbcb932ee295bc3fa8536cf1acf5dae51697960c3033af4d4037412f6fa5ea'
        '09bdfec69043129f65b1c03088cce35605bc8234bbba0f882e309a9f93cda53029463626b9f8f7d2880b4255da97bd72f678639bd954f963bfca8786e1866c0b'
        '527d9115102ddadb7bcd77e7259f1f6d49d35b72a5689109137be2fdc06ef5dbddb333be7405a6d3f9121718a16b838abe142f49659d9c3573ab86e23f846323'
        'cb8280d2c4d72d04f51b3d86913495493cbdbeff1390534451c14ad79d652e1bc664565162e5ba640964d64f3475f0f2ea1d786d8820d5a059d3486e531c63e7'
        '5083e121155a0ffdd9ffeb5a63e143d52ee258c59a5ca7769d4443473461d74b4be0351eef75ca24313a1151d6e573e3acc1a64772cbf5c963de059144e7ef65'
        'c78a00ef0516088e0b846cbf62314d9bb362354072fc0f90b6639bec05785dd0fda167d6ea834c10ca4950363c1cc17a31b8eff10e1d785800b1f6c8efd7c7e1'
        'ba6d04456e2a5597848e304559763b2948f34a89889c5dcdd96a88de00de1d6e75d6bc9dcf038c1cccf08ffde9a0ce8c56c42f41955a442c7acf91168a0b21b4'
        '30ce37dfaf511b18e12e8261d007de267b82872107025f435a6d2d40563d0a3f68b923cddbc0c58a2d8b2097475636b246dadd67e8ef69346067097c56562e90'
        '95b0055c02e2740f98b7211e399a5f97d65d1d3c7aff7805486976de9425d29fb7a4af49e9ed6f7528e995536eaa3dcb3747f55dc0a9a4d088b6538df7764e8d'
        'b6f914e875b449e6dfa4c3628b796e88b91264b16def1e544ae5a0ced6b45bdd5380b1136a5620f33291b9aa5622f2d1c5eac54606574a243d3f41289bd22b2a'
        '7d3b74cc043f854419fc5c49246213ff2bbe4e1145f150490d6286411d9bf78bc002a25709e19a1e5560ac7672c20ada023970f19731cf0b23d287c22ae4f677'
        '942f5500a386273d1bc0d975c08275c332726c3fc465fbf190e13682a663495d7e3d3f8d8411bf6739df91b3078568ad9752d4d418f32bee70040f3e8e540987'
        'cd21336266989c79a5a1b93368374a9f000f22eda405a8209df12554e836c5970e395b4afe315fcc43b60a98b07043f33b109fdef813d1de43d56321df3691bc'
        '783ce4ef32e62da373e6ea4bebb58b0c1be27bfa78c5ca0e912264ded36524da5149307fee8c4171b04247f3490bc2002bf7ad31606d2a7816aa53afb8a06287'
        'a0a9f05e2ce506ea1e35be6583eded048529efd7f8343997bcbdd2ac1003caabac41d0e148f8e2b48f53ad0fa8d38cf80bdbd25a1b9f78814fb719fa099fd6c3'
        '7a65909457f42b279cf7962f3f838026c0c7276d72d863cc01b3be6f434ec35c058279e6951f24eb478330fa89324c9304fdd90984dfddb8264bf091f4602d74'
        '50c411bcbf27074b60359e1eba0281bf5aabf3bd20ac0dd5e0fbd135fe3f65528bc3eac30e7a8b124d8b8baeea26342fb9a3783327c0b94f1f157cdaa1adf37c'
        'e593d97caf1341500a3d36b8e4f31b05e1410b0e73b66ea6d211dd34c5b85f5210d4c2448bedf86bb3be1c7ca31b297736b4adc56ccad99434cd7dedabb52f29'
        '5161a1848632ca7a787c233564ad2eb08dd39a550f2cfb9350da8b021e9f410bf9742bb7feface6d5c4fd89d4d86c8f5ffb3469a0c1308adaa547aaa2c0b6b6b'
        '0a39e85161b8d6fefc32cf229406cd123749db0216d29b62e8e3a2ee65aa825614fdd4b688ace9e6b4df82ffad66dcf5fd69e9eec396ec16f8f18a1927b3bc05'
        'dfc55de2b34a83df3a0b7b4f7fb588eaabf6580b572af5ec16b7f371f24c2dfe4fd0f969a29e8f6ed8b5489176e32496739550529dba889c2ff2e93d3a6838a7'
        '00c704feea914fa7a0dc5a86a64f6bdb3a26fc7749167ffb9e0abd68aba1b0d2c6a3e5583adcc1603fb81930fe7df24b3de03e0e04dd4b773bb5d23f1fefd062'
        'c93e08a6855ed87ceabe9d430644de8f80fe3ca48437e7e7e5a5e30ee6b8f8fb6b49b6e9009991e94976857482c1dc50143f85dfe2e45be73c4a0d0ffb17884c'
        '11a29cc01abb350e93fda76163713f07e8635602a2030f6c13deef39aef33e706d4f6cd6c5a6db20460bcbbac36107e7421e6f400892fd00b5f4d64d7bb4c5be'
        'dec1ebc1751dfb30af9737e5a74be8e473b8d62964c9e9c386e5e21400f6e6b0d18df56c8ad05f31c1117964675716296ed83c64aa1d7fd4cbbebc97d614e107'
        'f0e07d0ae3cf0750e2c6639053acb2ff252008ed809c458bc146d5d29e41334c1906124a54e07a30607c7da1e93eff9266929ae0f0c5cd0461efcac71fdbdd36'
        '2a18c199ca7ae8c3427ebd78e4779190d0625ab1945d18896780ebc9a1f72d3fc0d500a1e10e895c933beae05a30f9806499ad4717af4b2ebde350ee78a3eb4f'
        '71a4fd1e830b80491ff2c1e3fa4e2e1133e02cd9dbcf316236abcf88ed462be237e218a941002028efe8d2428add0533ab145fa947bc555d6bdc6d3c84af11d2'
        '62a554ed3cc24f1f0b531efddcfcf287f6542aac29d0b72ec86ac93948c18f43cabf45a102a4096fe93cb05a594c6bd31414e2394622f9e61cbbce5b5598b754'
        'ab3d1364ccc2271e70eed48d7688d4683c999a4f5b6f14bbec7c3473b942e7858de208de4e81b3391c2fa6767e51fa2aa7329d1fefa4a105a56141fe6f36157a'
        '80f014a593e9045350dfdd540799e2c173df8bb6f2b8cba43350f9df36ef1ab788241d99bd97dfab3cf03fd7d0edde360fd751cb12b7f78b34d4db16abf243e8'
        '870af2b7e8c58b98232c434e6bfd9a1dd69e93718235d8c38db400c9536e8ddda14618af64899879a5769d667e3328f03d587238b1398d278f9ecedca2e80590'
        'b0facfe4196545eef7b159f7f8fde8ef3cdff8121ec777e24d397e7fcc3a9ec249d6dd9f7496881c793891b636fa20fe72d0741c55f47dc2787ba109456affe4'
        '3baf0d0760d3ce0be693782707e75efb5cc8693836105e2367a7c2f42ab0779f9975b7ea6aa8ebaf7a6e8e2d83c3e01401343d92cf914d89b360531f23df4ede'
        'b162662c4e42a46bd015098276b7e5e344f8755e9d64c8b5402acd7e2537b0ca5eb81e431449ffa9feca6080ae98aa183596f178ee3eb16e8509e49b9856c37f'
        'a35b0451a775e087f381c13a3ee04da69603a17e6696227cd4d7f82403ebe1a62b8c65e3d7b782b1ab38624452be25c853126cb4d287a40b3abc84ed52252636'
        'e6339c4db911a7ad92ea5b7977ab8cd4c1acb739c3352f5fad5172c3e9764413867400be08f1597e3c7c4e752710c1e21837c99934961b24fc9454bb366792ec'
        '6c0376ca384471f4e426d5c1c9cedb3b6ace1983a725b20746f23ecd054d79ff7804e4d0dadbbddf6b34feb91065ce5952d5d581616856ecb51c23f42332e311'
        '30e86ca26ce2a344fad31ab3a0545e743459d1c538b68188061d8c50bd1a61d4628bac16aaba3bb5ccfe856c755f67fbac1ff7c63340e851754064f89cbb4703'
        '82f37053b9411f5dd08e5628e78dd7ead82a69e83e100d97de2172d904f748834284dff3888327ed6d212b5c4dd1c33053bb67873aed3c1541bde4aefa02a9fb'
        'd5bf7d1d6242b265fbc5cbcb589147b98cdafdc7355872511fc71d53e6a9dea6546a9cabfbda6891a44edac31acffb230cb8eaf24fdafc7ed7738c9bf3b12e33'
        '2d580378664f49d34aeb1e313f76cf1e92b47e8f213d066be0ec64bd2f88edbd51611850be406cd210f731448a9dd47ecc8909c6c10444f86536406688f1416c'
        '224c6195a114f1384949e734f42c36384e4f6d1910c033ae3b408ea3e12b219dbfbd61b4d4c817e4ff1b2d2ce6d928cd01af829c1cbde9c67844c7f2368985c6'
        '10cc6df7b77ee3bd7f22f863fe9205eebd3e3724873588c21d7399b163d38ab90cf222c33b8131a49783d70f42b88ece20d161fb60dd8190216d950afc264abb'
        '1a376d63575a731136b9e38c71a58b7f7a17a1aacfc5b82097c6ecbc964ce04768e024efd4b4b314c7e318b3831d2d04890ac515886e783fa50bab58d2282abe'
        'd4eca5420553ca3c5748fc9f6a1eeb4f53ded427b03edf15992a8912a0fa1c0515931d2a26a3e9c1a8e66e461cb2f7ccf8fff5f172ee7d71900909cafd90b45e'
        'e2cea706d78c6ed511640300533b8c223d901c763425050544e38d6c3020a6092dac4892ad9e8da80051360e98c1b820b801c42bb0e9a222f14ab44baf10e79f'
        'be0e90016e4862656ea1fbe34090850d3d59106e281f3256be2c99d76189fcede8b5388d74f597001dfa4769509654f26da225438f50a899e4945739768daf15'
        '44a667181994c77da3cb955ee4b45f9b6afea6f41970ff58e5035b82f752961b4b22782dc4f1bf0c7361aad6c950e0320d1bfda65aa36025de871fd333526c0a'
        '914ac5016e230f55f0566fc9ad4b6c57ce249811ac3e537d3c58cbffc34e3896c943547a5c5fba48f138a2a21a3438120f6fb2722a60e625936efc0feeb305c3'
        '07cb27dd0ffc02ac563e0f6c26433d08286dfe42e957e90fff4eb4e71730a7cd6802715c4d890f45fcd8a21584e0bffda9c29ebdf3c1bcf90c8e9d2d344500a2'
        'a2a8873408b207fc1c78fabc80cfe85573fa3aa73497528124238b48b1e492223bca85f46328b9372390444f6597f01a460e0fe4bed16b17750ed3943a83d024'
        'fabef9ab32673063479809e1f1380cf700de9405bb8552d09eb7200e666e44f357434869beef2d15197565280fd6009658867124e5ee999f667a3bc1e453cd93'
        '25c9881d9251800b153546eb7e81147e9550119fe2447268b76838572da05459d4e5cb95e6cc216367741f1c3cae1f4918b0df3c5eeef32d276bd181b1352863'
        'c2b6ba7da170bcc7a0ef5a70cf4883c127f0ebe5dc121dd02fa31467001c3685ff89475d0fa4d632db9b6f16557fecefd4de00bcd19efbc2d48e3b475f40e492'
        '15d1bdec6a257b63397047272e8c2622a7f25e0f120544481d113e424fa9f4ee7b113c3e8d092912570608d64714414f31765fe5058299c5c3f4f3313b078805'
        'c0968a968f28ffd0e97b4b2fd97829e714385909e38cd1d6a29f5866a6cbd121e66ec709cf32d648a916427cdabf8c5a49bfdbd61587b391bc42a9ae0cdd5b78'
        'dfa9c1840df7ab6bbd194044e6b388309b2c3eaa218a1ef42241c912d71a6e281c428bd76abd091315f39224feee6382ff55c1c1dd2b2be1d6b7f936a320c3be'
        '1ee8b10094af63dc2650c2af7e024b20c93e4b6913e4899b79502bb8c836e5839e618f292b1042f20e40d2e11ae6cbc35e20e000c8104481f8eb325ff754d8f9'
        'ed9b21ac285b729c064d5b3da543cd564d1b312e72848ab8a10b55e4514f70ca36f7299088c58663b5ee01d488462653d416a942794ae6b18bfb1ca1897f5e56'
        '6ac07dbb8f11ae227f3dee3bb80460c6a3b962bb1ce3c64233f6795cb27b46b60b37ec74bc28fd05c81c5bcb2925102f674fa63c57de332b2ae59aea3669c901'
        'fed1b23a1358ca14bdaeb0c154238bf3828c5ef82496e857005953d1ac19db43e81ad50e63896ff45eea80f8e40d76e1fd4ccc590339eb8ead868c9d432b33a0')

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
  make listnewconfig
  # make menuconfig
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

source+=('001-aosc-loongarch64-16k.frag.config'
         '002-local.frag.config'
         '0001-add-sysctl-to-allow-disabling-unprivileged-CLONE_NEW.patch'
         '0002-Arch-Linux-kernel-v6.19-arch0.patch'
         '0003-BACKPORT-FROMLIST-drm-Makefile-Move-tiny-drivers-bef.patch'
         '0004-FROMLIST-drm-radeon-Call-mmiowb-at-the-end-of-radeon.patch'
         '0005-FROMLIST-LoongArch-Update-the-flush-cache-policy.patch'
         '0006-FROMLIST-USB-core-Enable-root_hub-s-remote-wakeup-fo.patch'
         '0007-FROMLIST-scsi-Bypass-certain-SCSI-commands-on-disks-.patch'
         '0008-FROMLIST-PCI-Use-local_pci_probe-when-best-selected-.patch'
         '0009-FROMLIST-PCI-Prevent-LS7A-Bus-Master-clearing-on-kex.patch'
         '0010-FROMLIST-RFC-drm-amdkfd-disable-HSA_AMD_SVM-on-Loong.patch'
         '0011-BACKPORT-FROMLIST-drm-ttm-save-the-device-s-DMA-cohe.patch'
         '0012-BACKPORT-FROMLIST-drm-ttm-downgrade-cached-to-write_.patch'
         '0013-FROMLIST-PCI-Release-BAR0-of-an-integrated-bridge-to.patch'
         '0014-FROMLIST-mailmap-map-all-Icenowy-Zheng-s-mail-addres.patch'
         '0015-FROMLIST-net-phy-motorcomm-Support-YT8531S-PHY-in-YT.patch'
         '0016-FROMLIST-net-stmmac-Add-glue-driver-for-Motorcomm-YT.patch'
         '0017-FROMLIST-MAINTAINERS-Assign-myself-as-maintainer-of-.patch'
         '0018-FROMLIST-rust-export-BINDGEN_TARGET-from-a-separate-.patch'
         '0019-FROMLIST-rust-generate-a-fatal-error-if-BINDGEN_TARG.patch'
         '0020-FROMLIST-rust-add-a-Kconfig-function-to-test-for-sup.patch'
         '0021-FROMLIST-PCI-loongson-Override-PCIe-bridge-supported.patch'
         '0022-BACKPORT-FROMLIST-loongarch-wire-up-memfd_secret-sys.patch'
         '0023-FROMLIST-loongarch-retrieve-CPU-package-ID-from-PPTT.patch'
         '0024-BACKPORT-FROMLIST-ACPI-PCI-check-if-the-root-io-spac.patch'
         '0025-FROMLIST-PCI-MSI-Conservatively-generalize-no_64bit_.patch'
         '0026-FROMLIST-PCI-MSI-Check-msi_addr_mask-in-msi_verify_e.patch'
         '0027-FROMLIST-drm-radeon-Raise-msi_addr_mask-to-dma_bits.patch'
         '0028-FROMLIST-genirq-reserve-NR_IRQS_LEGACY-IRQs-in-dynir.patch'
         '0029-FROMLIST-dt-bindings-interrupt-controller-add-LS7A-P.patch'
         '0030-BACKPORT-FROMLIST-irqchip-loongson-pch-lpc-extract-n.patch'
         '0031-FROMLIST-irqchip-loongson-pch-lpc-guard-ACPI-init-co.patch'
         '0032-FROMLIST-irqchip-loongson-pch-lpc-add-OF-init-code.patch'
         '0033-FROMLIST-irqchip-loongson-pch-lpc-enable-building-on.patch'
         '0034-FROMLIST-kbuild-install-extmod-build-do-not-exclude-.patch'
         '0035-FROMLIST-LoongArch-Select-HAVE_CMPXCHG_LOCAL-in-Kcon.patch'
         '0036-FROMLIST-net-stmmac-dwmac-loongson-Set-clk_csr_i-to-.patch'
         '0037-FROMLIST-LoongArch-Prefer-top-down-allocation-after-.patch'
         '0038-FROMLIST-LoongArch-Disable-instrumentation-for-setup.patch'
         '0039-FROMLIST-LoongArch-Rework-KASAN-initialization-for-P.patch'
         '0040-FROMLIST-LoongArch-Add-HOTPLUG_SMT-implementation.patch'
         '0041-LOONGSON-irqchip-loongson-eiointc-Improve-IRQ-affini.patch'
         '0042-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
         '0043-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
         '0044-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
         '0045-LOONGSON-drm-ast-Restore-vaddr-field-to-struct-ast_p.patch'
         '0046-LOONGSON-dt-bindings-dmaengine-Add-Loongson-Multi-Ch.patch'
         '0047-LOONGSON-dmaengine-loongson2-mcdma-New-driver-for-th.patch'
         '0048-LOONGSON-LoongArch-Add-canfd-support-for-ls2k3000.patch'
         '0049-DEEPIN-net-stmmac-fix-potential-double-free-of-dma-d.patch'
         '0050-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch'
         '0051-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch'
         '0052-AOSCOS-loongarch-re-introduce-add_numamem_region-ini.patch'
         '0053-AOSCOS-loongarch-basic-boot-support-for-legacy-firmw.patch'
         '0054-AOSCOS-loongarch-parse-BPI-data-and-add-memory-mappi.patch'
         '0055-AOSCOS-loongarch-add-MADT-ACPI-table-conversion.patch'
         '0056-AOSCOS-loongarch-correct-missing-offset-of-PCI-root-.patch'
         '0057-AOSCOS-loongarch-fix-missing-dependency-info-in-DSDT.patch'
         '0058-AOSCOS-loongarch-fix-DMA-address-offset.patch'
         '0059-AOSCOS-loongarch-fix-HT_RX_INT_TRANS-register.patch'
         '0060-AOSCOS-arch-loongarch-add-la_ow_syscall-as-in-tree-m.patch'
         '0061-AOSCOS-la_ow_syscall-add-kconfig-for-module.patch'
         '0062-AOSCOS-drm-loongson-add-ls7a1000_support-module-para.patch'
         '0063-AOSCOS-drm-amdgpu-disable-ABM-Adaptive-Backlight-Man.patch'
         '0064-AOSCOS-MIPS-Check-address-space-in-ADE.patch'
         '0065-AOSCOS-kvm-disable-enable_virt_at_load-by-default.patch'
         '0066-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
         '0067-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
         '0068-AOSCOS-USB-core-only-enable-root_hub-wakeup-on-MACH_.patch'
         '0069-AOSCOS-ACPI-scan-Add-pwm_lookup_entry-for-PWM3-on-LS.patch'
         '0070-AOSCOS-Revert-FROMLIST-rust-generate-a-fatal-error-i.patch'
)
         
# vim:set ts=8 sts=2 sw=2 et:
