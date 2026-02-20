# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=6.19.3.arch0
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
sha256sums=('0e474968adfcbee32916fd01a89d8ccfd1168d8d32569e76a5c664c793198ebe'
            'SKIP'
            '9fed188f89847418aaf6416b64457a30bee34dcd0fa42a84dbd0f4dfca063402'
            '157126a09f9a0db855ccada3d560c5a2e469c91186596b7f6b15afd2b983b67f'
            '8750c285dc48f1511e565062069b2a027cc3fdae6bf478fa4e5efdde9b8cf9e4'
            '651855a122742fcf9119a37f71f4d0db421f2450322af1c42e977d5e606cfb1a'
            '341a2e51cce274a02a795a8568b4def76218b39c78f1630ccef95fa69f31f805'
            '38f6456f7bd28fdcdfc3f776de1c423d81963c9c27b1f4734ac4feb830fd09ec'
            'd2efe949c3b0b09786d05e0a9ebd784c21f9defe2bf3be217e86419c14daceb5'
            '4fff97021fa4c1e04d961debe372edbbb8d0c67690e33e75bdee54324045ce5d'
            '091dbaf2e34a36e35afec84257e15ae0828dc1a418db400b899e30e341372b00'
            '38c44f5f23c33669909816cbcd813768dcc42d4d504a4b28d85319999781cb58'
            'cf53177269390621b8336a7bb7825292f5a9ececa7218fb98e4a433bbc6bc7fb'
            '3e8bee632aa147c0a86daaf700c4c16d557e7b48bddb0b612c49278b0d4bde48'
            'd0306e234ad6b7fee3ddecb29f94b7364f4a3a1afe78c2d985bb7e767b771576'
            'a2488beb4ddaed5d9d5fc8258505649293cfecb2cf28e8140ff571d0fec42769'
            '04493d098a8888d3ed74405ec0b7f8b755963d0023c4257f12ada4f0e5673189'
            '8dd7aa1740e94860b151f91fc2ca9e5ebc00a742eb5cf7bb1e15c1d974ea9ecd'
            '977504db38586904aa186c73507f0cb18e3c7370d6ca26d2b432b34e63687c2e'
            '436220a3b0907f6134ce3d9fb181166887a1e9f9d21e3109a1c7d825650c4488'
            '49e666a46c18fdc4b92f4637a04866aa99ecc245feee4f34c90dbb7c8b154594'
            'abb0894735b6d41681381206a1e28c58e583b01f9f5264b315ef7b699e5644c5'
            '0b299b7e378de178049fd5d48b09557c5a6d9aa1557d714c97ba1e51c067c316'
            'a6b62d6b4b95b59b73807f60e7f3926825ae1c9640fba2533017c91c6743af1a'
            '282cbdf13bd9e3ddbb484df70acdfb0a22936b4d61522823ea7c48039db831d0'
            '69d60f6cbb9fc90639fe91d35fdb0a5b16e4d84b5a0a1d7d298af590b44b1f6d'
            '82cf93c792634e7e3f012486b67f318767e42cf08d686f05c34df6038e34549a'
            '57b2e49bab72cdf152fea51922f5ff287cfac9c329f6bca33b3ae53a94363e67'
            'd114ac9530a6d5af3e77c1733f01ce79be3af236516bddacf536238ceb4a660c'
            '20d8921d4cb0446e03ab6f4cb6d3a22a358a9fce2488d42c111eb96aec0685a6'
            '53a610ad5812dbca58bdd03ae6a3fdd650ad7b6615a5ebcdb34ecae9ceef964b'
            '929d6dc8038dd1329df499fc3949020cb64a5dee86a61f215ba86d16abde1471'
            '68f44deaa0b42549c3a2db38fa8eb771f81bc5b953f42fc7d53fadc38138133b'
            'f2d6e2ae0ecbf42490390be2ce80a37598565f1c36b9669b862894a2651ada41'
            '13194808f062110a48788b428ef781cad30ef46ecbdd11e4c0a438ed16616611'
            'c40623c62ad0bfd3a70f60bb1922ce90f6352bc2ec494708107e8b689e4e81a2'
            '6a197380360dd1be536fb84fe861b2cc7b09a6ec3bac77968d364556462a8fc4'
            '5b8501f08359e288d5d833e954b08ff8175a1143686f46e0d4c0cf21f4be4195'
            '9ed3f82179c2c8209a0c9d70c7444105c324173b28cc93af07d82b45a2efc2de'
            'daf3cdcfb1f8db1a680aa183e8341b71dcbc379f5fc55d772c849332fbd0f0b9'
            '79382bb88b337fce15d90c7cbf38aebdca02431e87e6c1760d25dcc14b78f94e'
            '94bbc7ebfcde22bf15ab8da4ee063702722dbcb64c9ac395fe0204aeb7973656'
            '2fa9fcc7bb97a87a9292f395b6d7d6fd9b56bf269a12aa0df4aa8f185e86609d'
            'c9b0926195d813a07ee56db91b3ad164161a57b162b41546cdd5bb5ff43e9aa5'
            'c78ec5882234b7eec79e118e3ede8b2112fbf20c7ac63a876b277989aad37ee9'
            '19108aca9c1e39ee3093088e89eb50fe42209a20e87036142a61929029ee8a0b'
            '52cc4b9744800894cc6fba53bf84070a8b71c38629c1a40ab418950ee5c21b4b'
            '01b7342ebade05925a6986694dd79bf82a885cef444cc72f4c9edf8341423fe2'
            'be9cb5e11925b5c187c1815ee8a9dd8fc6e622673eab7bcec12aafeeb3688eb7'
            '57f4f1d41dbba79f9aa68848cb213df1eca6eed65c29892300369575270db86c'
            'ce6c12c80859c387f2aba4fea02e731540d7d0789fc997536897bf952efb5e1f'
            '76ef038b323da8fe67afd951a7189882eb9da40cfeef8080b67bd267ae6a0f27'
            '90b9ac6ea56c5a4f3d25ad0eb2247ce288dc8118a08466c10187aeb5f38e0c61'
            'e65a9845627a9a309982b800620e816472c48f853ddaf74628d8899bc4499609'
            '9581f28a37ee0f2b744701083221a15cfc8c2996a38c9df532d0bed0374bfc55'
            '2d262257702c241798cd7d6afc65d8d3eed62f23bf12f6cddc7ad729a88e6d45'
            'de20b8aef5f32203d62cf3e4fa9bcfe2b6736dbcbb87605bd100aba91c716404'
            '77e83d3042e3d629f1fc6d1d030d15cb1abdbb020ba117c85f3a8aaa01f8341a'
            '7094f9a6c03ed3a07f12f25f082170ac786ee738daef163f6fe4472d51e7938d'
            '885f457a957a9bf024a3a11b83c0c7e750d4ce121037f375465675003acf971a'
            '7ad85c3e797d206b570a10b2e2fa005e70ac655902d4712a2a222abe228fbdd8'
            '8ef44676394a3fbaf706392a2136f25d61a2b3708b53300d7f94934181dc8b07'
            '9e952e2ac93bfb89b3a58bd65d716924d0089af2156f491a5027304f7c3830b7'
            'f2c43cf77fed194ab9ea3463aa4c895d45431feda708009420a93c11fbcad6c1'
            '1af5b9dde0c10e740f342a766306bc14bca775f48291e4239cff684a86740310'
            '4ccc55f6f0a16f0ce4dbf206a4ab4ce3a423e373bd1167af37dca38b2c134e26'
            '4404cc959016735bf90ec68d1fb8ff15ed51b3761e5d1d4c07bc276356d84d1b'
            '6fac946b2d621bd39b819274f954fbbc72a3bbb5cab80f35be0544b4804b2a49'
            'f4f19859db7d640fb0961e7ec0548b9b08bf3c0c0664ebf413267589af09a36e'
            '0638b89e138f3007cc1303669fc4736f98b6ca963724312390433c139577f500'
            '018e27206b982497813bd6f946a1d0807af52d376e9fb7b2a403392d1455df63'
            '4ff5297db33adfd00ff124f2652ab9b211b67e339e731266a1046a8a213003f5'
            '1ea55475b681a52f29459b761238d95ddc0cc9a2fce1670ecd7438cff9a2f54b'
            'cace3a2b8b686ac5dc76054d55df9447134e4122b8a7bb666c00feaad35444c8'
            'd2da929765090e9789ac4fda449bd9b8dd93a36a91970a4f79487fa5673bc48d')
b2sums=('a6026d06097726bfafc19c83c94949c15bee5578bb7a872612a13a9ddbbdc871e18395832da27350aa476ba947c7e8904b1161c455b8bdf4a5fe9127c32c6818'
        'SKIP'
        'bef3377ad86440af76e9dde4c29c9f4aaad42f5fe343f7d31f5eb537d6d358602f996f5d63986af275f2e92f94e71dc28c320edc8c03d05bd64dbd8ed23d75dc'
        'dfd366b283243f95c318471fe35e3a36646a38388dd6c4d9746bc981985a02ea303d75127244e9feac14564a8f49385483dfb56a8842814bdf97ca747bc2a4d5'
        '8f9568afff28bdfed46375a11adac228e23d36bf6eabac99a4b6596aa093d1eda8f8c06d712d0643912290187d695b6ec2d52aaaa5c3b0736ccae7006fb533dd'
        '5e9bb9d645cf56b89a3048974a0f9dda223e7295523f841860dec1f3493e0081b8a47685c475ae20bb2f51b467ce247b8605e28412306a988748e3979bd8da4b'
        '4a74d20c86ef59dbffd7be15af9fb4a385b36f86b7a6989e7287c634c74fce1166211aed042061435c8313436ec14bc014a01e62db0dcd604973c53da6dce093'
        '79d8e4e0ed5faa3dd07ecf92018fa279da7256a5ba47ec2d48ae12dd2f4d9b981f894661e7ce8d113b4ddfaeeec32d38568543712e906a186563586924a3cb0a'
        '336e677bbcc6b987992c91358a5593f25bec71ccee4cc57af7d9fd987a64e7712a45068ed6542407abff7b445b79a06fb7e2f31a03c9f7e79e1ff3e5abbba6f1'
        '7fb3101a7e03a165df6fc4bca9e8737f020c4cc440ab6381a19c9193bb2888506c2838901f2c67e77649c25d98956125bd8f063a60d4707c195b26ef910cc833'
        'efacc2959c79c3cfd9990275cc937ccccbcf9f789530b897688d199ed27c9ebe9696a91af17d56c0d552c8bc5b8ff83850e9d714896a2b15d7e990316b0c6d59'
        '84f6d601ceea3c3bd036533ca0ef6f8360570fb20a0914d37f61fca1ecd2a7cdda35a1d5bd6861a6bf9907b6f0f644271d7ce41eca64abf5fa1e9ef3711c7b68'
        '2702b989db7441b5d7f472295bcce813101aea3a106cc47d7fa05e9c9e15ac80e8053d607812133f035d9789eba3ed303d42495f36b810b99a813591d09de0dc'
        '9510d2f47f38a23ab4c002ee02b669e36e1684d0aacf39410d3e2d3b831722011f8eb69d1ecc825fdc81e011fd9d3ca97666bbdb4490eb2997de980ec1bffddd'
        '2e182b49ad37890522fedabe6904eb3a2db39c553b8c104e59f020bbc257d8d52568700f9472265f96b5eaefca0d91797ecb7f6a6645866bc0762e9942221b4b'
        '9ae2aec04fa24ad74cfbc0e3090b440c3c46c0fec7957da41ce9866ef634712adc9ce94525b99b29b4cca8c58a5332bfc47c8ffe7fcdc4722a38632cc99c0456'
        '927f43df0bea0111f47c95cd71e6286eb12ebe24e5ebec1eee9bd4824da2ef1edfdd05609ac412b0b2db36d671608a23412f3bc629036fb1278bc912615f3f56'
        '8947995e68ebdd9894d7c68c1a13f1fea6397734c71ea9bf3eb05a5b2bf832affc4d63233e17ed6e2d3c37427870f333cdd252b86eb79affe5e7b62e80b3216d'
        '379aa86743defc2022a78ad209edc16829bf6ebe46b48f89f4e9510e030d231131cd3e28c026384bcf20794eabdf5736118cc5fcdbbfb7c4305fa485f01c613e'
        'c5571203e2d1e80cd056d605345af4be3a6df382e53729d61af28e97633f40b1eb598d91da6416b1933aa410c0d4dc1101511c096bda9b052ae63812b283b82c'
        '855f889f99edb31c4731817491df5ae8eeffad84e21e620cf1df4198ed6e13aa141afb12ad19518f13289bc0ac285aae47112290620923d94f04d32a595652fa'
        '68c4b8a6f0384d9051bfa774fa6297edd03edc407902550baa48daa3d87e3299df8e283e8a1f2103a8d6cbc690fdbed1c96434ef3e20938fa59a6c521099dd58'
        '680372936ef9efbf21b3554937877e0521243c1392c1b4472f29ad367d25aa24e95e5467995d434fd991da2de1eb5f75ecc6384ba828612c4ceff22ad578e96f'
        '3abc0446890224f82a1e1380f2d8cf6c5c304dbc3dc4f90482a8ae7b5f09cc792d435e1d8de73c9928c3a521af2ce86f3ef3a2c1ae1098435d42316f46bce86f'
        '86cf1a3fb6ba0490f0b317a0b85d3b3130c37b205d09cce50f7cae4502e304a31a3d35e67e84eec64c3f9977b78a4a43d264aee87928867aae801298f0efd70e'
        'e01ad370323112a1b26e2ea12aa5fbef8eacd6cad9b56123588b20f07a9b85d57c18a50152476a6c78330d90e06cef1946c2d27a938c7d6fffabdf508bfe5e6f'
        'fa31abb99c87877033ecd6fab70de192114c54382082d1a88a901a94a28c2c64a459a50e84e9d6388d4ad14f75bf5d2593edc8767ff61e28c5396b5b6df883b8'
        'aa714d0700b8d799addca55afc06876ab6e09595452a879d874b1f6b7311bec449585826aa87ee32df211535c0b8b93b85871001053221b157455244e4f8c9f2'
        '9eebb46ed5c6b61e0e3ba5b60cb057775a54df3aee6c8890f9f51ce103293c05eb483f50a338abc68b5c773946b620a1419cd567a8eb8e3eec362ef7b85ec6b6'
        '0b69f9a08f799c09218e271a17b5cfea9e687a88aebf2dbb432f84f8508094e78afa0cab5ab93d7df5432026ee5b31de4f30c52bc73d5acb1dea977295ff0840'
        '21bb9c4776f723fc6754414deb84f07841f0987c71926137a55431c2cdea79a454f21640eeb4893a50d3c96259348520f654aeec78792228603ceca9061ed796'
        'b61147e475c417ad4f33af4a572a8dd7977e3ae63053e29db597dc2a600ae6db2302556343b9f3f316d06d38dbac05ff9676355606cf704a0c5da3e5827caa4d'
        '0b3d489aaec82f07e4eed9c0ae35fd023101399946c94e98da7d685f1e4f886d3ddf14454274df0124386897ab461388c65af23cf8f38f1fec07ae154ea911b0'
        'bc70e245840f18a590862c1be16b874c1abe258786c1a016b95102a931fb46631efaa6532ccef1089809c5c5d1ddbbc2d4a23f48f6e58386914463f1d7321f94'
        'cde5180517fb535be1b334e659c78feff9400a03f57cdc6860f39b870ffda66faebc6d05850e7c1320686502f3bb56dd790629c3b5bb60a665840bcc216b8cc5'
        '1626b15fa8d81f817648e0fd6010bb8adbd9ce14c7bec5334a9ea1826955d4d4244579467d791a753288fa3249b99b77c6dd8480a094306a9c007d1717cce906'
        '906ffb5c897127cc215928fef1ddeba292df7c0699604907421066d71d702341482e13a2531c288a5d1fc8315127663c858af55252bf5b2dc696fd17e61ec4f1'
        '57b6b91ac71f68454552fea67cf95f7ddb4edcbc1a334735d7c8a5b1a38c4c4c812400757dee9f148f471b71b789780890df857e2e6635a8cee1af5492f1c350'
        '5c525cba5903c385c6876a40a902de50d75721e1f92a68e0a7966322ea747b598e753b1ca7f3ad82dde80662bcaa108673107a847d666960bf4cd8e4fe5bee87'
        'e82d43b518c4d4b3e4b01a06544fd1d82e4dd818c9eca7ec81734d562abb6bdb92f1a0b6fd96d3ef61c1dc79daffa004003dd2bd059b591522f06734fca168cc'
        'be4a5a5164bc3c4ebe910fd178a3cd752fc92041b7092c813b47952f6622d3ca4306ee1e3e6809d5bfd3d35ff8e871a1ad127a3bb92479b7a860d67146f97d39'
        '47dd97735550e728c30321d3e1d6887393d046da88cafae46e57af9dc12a33e9d54e482dd5c7f12015b38b0d39654d47715b4b38a105a638623c2f9222a21ac0'
        'afcf8c0e52c7534be8d4e77d668c6f2e13e178fbd4091da1b3eacf787f25fcc5b20c6f0aa090cd94fdab6d0494243091c07332f51c192706ab40b6f2e91d67c3'
        '861addf9d1f778cc177c5fe980385c3127608c945d1a92335e4202c40ce46831203d5a2d6391a7070617507bb446fb720326caf1b46cc3f21aa4e6c0216d577f'
        '077210dcf419e135c0a5625fb66ccb001a98e4aa56c59e4cbb8152f9eef3e6828038b16b9a0e4fd874615033127afacbc534af58c9c6ca360da99b3c3c358398'
        '7b09d0623004f9e58434f93359da0d9a6776c857cb77373d283a9959524a939175bcadc916b91df61536bb8110722f5af30c60d6706a6dd503bb36e62d1ca96a'
        '2a859a2a9499cce0d8fc28a9797f8c20707739f5579f568e93169ae29ce522c308a524c61ac6ccbfa438b9a612c4da9a9b7b8cb4942bd513581535dca0123a86'
        '0f56ced9e445891986e04f4be9d0125d72a1aaff4677301a3a8f96096921407e33b33dbd3f6e8fc239755e58107d41d8b38b934a1ab5e3840bdab33072a8ad42'
        '463c8c0c9d3d1cef9ef2ba7c25773cd67b60f929d2670bd96e4c48ef33198c964302cc60e805387cafe42a9cf888992a14bb07768cf9c58d6af50024a0865126'
        'b4a2f4c3160194a8be71f3d12a3befbaec62c6570be87a4b301710342d361cea48d3c804f9230d71cd767d97c2e65b8434dacd12b9076d6934de3a0fb93ac99e'
        '76c080edf27b6d053af93d4aef150876b0bddd5074765e9f15c33c703e735667191493bc4a453d068be437b5ea6cd9fa2dc6e89358fa86db0a7e824e38f2b7d8'
        'dc0c41db5d692141f807bf1b0c20f78c85e540f71ae1eb88b4faf3644443287941a0ea49a855c3a8c6594d2f0107f93ee0c91df5a91f09020454969b962bdeb6'
        '037ca4412eee1994312ce60f18f04bb1ce1c12c1416cee7b62a04e35d7ebb5746ffc9486a843ea3f7a66106ae648d2b8374be30b1aff80041b214e7249b15796'
        'ce79e79682c433cd72927fb321766c0fdad8c5afb8ce62ec2d2638de637ad0f3aaeb234ebdd8335cc784d1471d47bc42bf498117b78e04ebc690c0ff73257735'
        'a8e4bb1841e62465433cd3490bc5ef489c03459ff65895672494bee9300a886180f36522ac4562de1c3ee0be0898197f9e97e1fe3f2c0c661df6ad5e3987a359'
        '0a2ecb28561ea1d0a1204c1088429c62c42d5a36eaa8c75ddb940578bb37edff1ac2fc1890ff324f37178c1505b37a5a49d9c14a9ed01c286dc5674cd24629de'
        'd735ddc2b98766e56c9160655f7cf9b44bf18fd586e7fc335e91e61c0934a245dea5193f940e50f03d79a7c9e1993c3b9cade5ea32bd24b91993e3ffa0acf6ff'
        '136c28981e9e2eb719cfe0f5134bb10ffbb94f7a31fc81f5ec5e7e3fb1765e03089de73e41eae14fab8805aaee434c4258a807dae3ab2c5aea07cc53c3422dbb'
        '8da5f23659b06d2b539b0595d375b0152e8536a2fcd1fd8fa3c25ac8a7efb1abee0a7c860d67e79d8f1be5045a9c6012d37e217a43b2e850841f6d60ecdd0ffe'
        'b70b0b1925abef960ba3a732e8adbe4ddc88318eac539a3a26e3e9550b344f087be135d5b1e24e1877bde7e0b6e47fe1d92bbc1d86a0e1e39112ce4e60867caa'
        'efea91bc558ba01ac7db481154d5ec3809d6d5dd66adab937f63e531c51cfef233333b6df16cf271b1b0af2c2c6e89903c9cc0dd0b852d6d31fc191c80da9746'
        '87187ff30f15d14a87a6d1c32cea3e394614d5cbb14bfdadae53bbb4dfc6a448e179c45c992d7a5a540c52f67ddf5c60b6d64a9e1d09d46a7d5f7ce51a877667'
        '0d86d1d3df509f1f606e10d43f1d62f0c44b8e7aaa2a8abb0e592dd858b4add191519f39070773287dff44e235cda029cbbb61807b1b35ebec0f0a128f11c353'
        '55c6464f7d671a760cfca4c842f92d3a6452075287d141852e02cc474aef3c83ab29b4c1d34e01debc72cb61d5858c7f3e9b339d1fa5c52faf8f455ecc8aabff'
        '691688411f0b8c2358314e6cfb003f13a3d5b989a914154eccbe9e7bff097318b3b50b4eca0c2a3817ff33a504cf1fa35136bd6330dc9fdee9e897ed07a2320b'
        'b3ee6ee70a1b15b16c3088dc03660b075fb852ce898723d7216dcfc8f8ed768be3586a1bc16e6e09f9989f5eaeab012f562dd222d5e79feecba97e4ad5f0ba6e'
        'c337939dc208209e235e8586976ed0294411f2a18e2e6cfbeeee9c3cb78ff17bb8b6fa4aa26a84969afb496d32c212c0ffeca65688e3d8c279846b0aa98847a6'
        '92955aed7c2767c8ccd00781a3e7f13aa475562d96eb38e888897554c09c7bf7f2575ba76644795bd6fed5fb3c7c4a49e3c563bdbe046bd7344a8094fc086dc7'
        '8d8960e6cf3a91b75fe5730421bfcf1a4b435a2ae825bc50af4acdf9766429b4c3b8c8fabea3a051e5b98245e1e75d76dbed55230d1caa87f077e27d3498099d'
        '88f28efbd81196c6ae3ce6b9495a662ed6fbfad75a3bcb62c7064a0f3f89c588e8a718365f5115bc3fef92dcdf02b3f55230255288b83999ddcf53b3f87cfae0'
        '780b5065a185ad5459dc00ac253d6be11fef1d70db9a02e522ded1699a6e36c0835d6a8414f373945ecd291a7ba3bdb8ef2efdccfc652d2f4fe50e2df313b1b7'
        '28c80fa6e54203ef58dd340e9a5b1e8023967f5783efa719ff527b47078c295cc463fabd2fdf51d7584334dc062221aa262b777741bb67b958c8e8a98c51bee3'
        '5c1fa2666741e7611c8b448a0eed6df0bb1f6cb0110f9820c4dd4aa33c459e66bc435e23ac08adfeb99e0ac2e0f11d6ba2041a626e08516e5a62e7b3ae16e3e3'
        '06fb17281c10c7c53bfa8a1beae549767c6f8c7d6d28b4707351a41c6bb55961b2d0afd92628fa55a85613dc3ef473d0c15819d6e7edadc9556386b61c235a6a'
        '1d05c56132fc1e2518fffccd7074e91344435d3eb2d437009f54a41901d3964841251f9b38a8686aef45ebf519895fb9e6e191ee808b3367b4a34f7d3972a0cc')

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
         '0002-Arch-Linux-kernel-v6.19.3-arch0.patch'
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
         '0039-FROMLIST-LoongArch-Add-HOTPLUG_SMT-implementation.patch'
         '0040-LOONGSON-irqchip-loongson-eiointc-Improve-IRQ-affini.patch'
         '0041-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
         '0042-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
         '0043-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
         '0044-LOONGSON-drm-ast-Restore-vaddr-field-to-struct-ast_p.patch'
         '0045-LOONGSON-dt-bindings-dmaengine-Add-Loongson-Multi-Ch.patch'
         '0046-LOONGSON-dmaengine-loongson2-mcdma-New-driver-for-th.patch'
         '0047-LOONGSON-LoongArch-Add-canfd-support-for-ls2k3000.patch'
         '0048-DEEPIN-net-stmmac-fix-potential-double-free-of-dma-d.patch'
         '0049-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch'
         '0050-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch'
         '0051-AOSCOS-loongarch-re-introduce-add_numamem_region-ini.patch'
         '0052-AOSCOS-loongarch-basic-boot-support-for-legacy-firmw.patch'
         '0053-AOSCOS-loongarch-parse-BPI-data-and-add-memory-mappi.patch'
         '0054-AOSCOS-loongarch-add-MADT-ACPI-table-conversion.patch'
         '0055-AOSCOS-loongarch-correct-missing-offset-of-PCI-root-.patch'
         '0056-AOSCOS-loongarch-fix-missing-dependency-info-in-DSDT.patch'
         '0057-AOSCOS-loongarch-fix-DMA-address-offset.patch'
         '0058-AOSCOS-loongarch-fix-HT_RX_INT_TRANS-register.patch'
         '0059-AOSCOS-arch-loongarch-add-la_ow_syscall-as-in-tree-m.patch'
         '0060-AOSCOS-la_ow_syscall-add-kconfig-for-module.patch'
         '0061-AOSCOS-drm-loongson-add-ls7a1000_support-module-para.patch'
         '0062-AOSCOS-drm-amdgpu-disable-ABM-Adaptive-Backlight-Man.patch'
         '0063-AOSCOS-MIPS-Check-address-space-in-ADE.patch'
         '0064-AOSCOS-kvm-disable-enable_virt_at_load-by-default.patch'
         '0065-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
         '0066-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
         '0067-AOSCOS-USB-core-only-enable-root_hub-wakeup-on-MACH_.patch'
         '0068-AOSCOS-ACPI-scan-Add-pwm_lookup_entry-for-PWM3-on-LS.patch'
         '0069-AOSCOS-Revert-FROMLIST-rust-generate-a-fatal-error-i.patch'
         '0070-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
)
         
# vim:set ts=8 sts=2 sw=2 et:
