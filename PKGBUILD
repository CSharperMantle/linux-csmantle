# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=6.19.2.arch0
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
sha256sums=('88611981582cceb7cdd4d688d9d881073cf4977176252193a23ca6d4b982ee5a'
            'SKIP'
            '9fed188f89847418aaf6416b64457a30bee34dcd0fa42a84dbd0f4dfca063402'
            '157126a09f9a0db855ccada3d560c5a2e469c91186596b7f6b15afd2b983b67f'
            '3240d8042fdf42c1aa8039c0ac4fdaeaa4fd6eb5d9c176914c39b6b477ac6844'
            'bce9c82e44ca4f25981c49c32b09a0fee8791c5fd0b00c778f32b745876e17c6'
            'bcee949f6d5181af7c20f30f86f72644210cc5f2c361614a4c69547b417af480'
            'a64365b7b457613d2dcadcfdf4fea3312883e1d88acd4952a7a52711f5cc5bd3'
            '41780f49a54d839d669eb212ae85ae2a59cb2e1c5a093dbccad31fc4f6d99487'
            '1b930e228b9a0bcead3756eb1ae6060f22a6bd11183edceb63e4ecee0348d2df'
            '6d8ef937e323747b65aff8ed0a9bd54ff48c9e1ef8e203a6a9143a8fabfd6b3e'
            '9ccc7ca6ce7f205a8302f0e90c978c9d1f3712486cdd9d0361443da665ecfebc'
            '45263ddf308504aa0e032cff3f9509039a94e51675606bd8e3741b39ca1d833d'
            '3c2c1d78b8df4add7aec6725ac959cb757362ba6897e9e630b7010b7633e7382'
            'a74cafcc44445aba8781868e27b318085eb31de3d16c35785c532745214aeea0'
            '2358974eeaf877e0e7410a18d2946fe5882eef050b797c4437ef9439ce0f6d90'
            'c8b8457c3d780135e50f8bca66619789b23a923a4ca17067e03165c616d9a098'
            '7c2fc9138b21cfe34909a19f214ae7865ba2fe48a717f3d1c1696483591a5443'
            'e349faa240a72e8b327aaaced5f1155c3fef486d2ba00dc573ce7ef6637a65d5'
            '08ba8a6e245d9f7c501b6bd88bd9cf1bfe4100d83cbd698bcaf62548d9384faf'
            'feb41ff4c838bac981dbc49f961604a4c3a85694f5361a770af676272d5ac72c'
            '0f79ecff93f76be48836bd18490d6e94467edbd1249fbfe552b4d93c43506568'
            'cbd4077734ef130fa49993e202c28f53ccc3fe00bd4e37c1ea5091ec170c1ae8'
            'c3bc777150f0f10738d088025f0c4602a462f3e920a2f872f9108f19bc9147bc'
            '4d8291ee0b4a7df8ff9a47e62e77bfdd9c3a9dda7f778347708cfd12cb12d252'
            '7e6152d8cab7edc7ac43c84483538031a14ac5b628007ee7e6b54dd3031367fe'
            '742de07ac77a846070933bbfc1673f0c4573acb4758f4099d08155209197e6e7'
            '7d7905efafebd1a957540473a89413a31129e909587a53e601e9ba13e927e7be'
            'e7b1b0d6c079c3fe919dac94d873cbd5dbb9502f930a25884f6173d2aff2c607'
            'b0206262e2bd9c5c761c49b69c53ed910dc16c133e24cc55fb772d9c88da071b'
            'f6635b08e19ecdbd5580bf829d82fb8f0f3cf9df92168d42205ed9e46e72914e'
            '2dea54e407ef578114a6832facc4950239285cf150f4a26a8784431463d569ed'
            '010daf099fd6bee0c58aedaf8bf5fe1567c0c7860f2d1fd003766495b2ee277b'
            '0ee1aae8ff14b61bb3ff849281c80b9882e0ab04d6101ee06d6113d806828294'
            'cfc4af17a25418b63b01cf4627f3412122910f4d64a153ce6028cc25dc158107'
            'cd6f68f104fe67742a2bff1301b30b3833a7e26c5d91c168c452d99e9fe8a690'
            '03901a00f6219bf386d0313b3f162e03cdbeaa77ff4b6b838262f75c0debce1a'
            '110fbba1a27a3ce85cfefcc2b74f2c6c4545b9f11f4c9bf0f20453aae2a3414e'
            '277624003e6b58dd1c094c75943f2e96519655ef9b20b69b3c214c014584e2d7'
            '369ee3d21dbea3494bff8d70463fdcd7814a8ab093612f918ef2f92d3c99e513'
            '79cf1ad541c630418913d1ecc3a0114b9da2f7e85e8c84ffcfed5758101375c3'
            'b87255fbfd3a94450135dd7883d3d2afb35213dabee97556dd24e9e90a0b68ef'
            '0bb9f7de911b91b83cecb10599ca7280c43e3aa25ed976dec6cd0b6d77887cde'
            '0b3289b0072328f1b50bc5205104abcb8f26a37535781e3fb5103417d8c7c334'
            '3c459919320af65040dd829f75fc550b794cefd5865e0ced724c43fb200c8b0c'
            '348e5dfc6df314b7241c4283cdd27c563dd7585bc27b3b85fb83d20336af33e2'
            '567f2e89566a97e84d0eccd95aa604de90547d3a788b1f22781a5423b5ab795f'
            '87c8bc9182f766523fdaa84d90f61e0b21512e37eb84403ea08d64ddb94138d9'
            '0fbe974b3c5261a3112007d460f668142e4a1a8ef3c83e89cc7cf6a218035d2d'
            '7989985747ec3f0d8510ca7efef31b84de27f4f8d9714e6cd30c99ebb9e17ecc'
            '3ea28e453d80323d7ed2cd7da6095eabb7a15f65ebc064f3bdb55dab7160d768'
            'd58a8b84ce5c913178ef7315850d94ed9a3fe54af7a4c3d62695bdc5a8bb1e8a'
            'f54cb53fa52f1285b5024b116da497bb8638cd00683a79b77cc403f18574d561'
            '6b75bedf3b22f5d848b4e0ae536eeee5a4509c362f48c5bb58c37c66a99dedce'
            'ef0ebc74347c4965a66a33ff77ef059b852faff421107d24b50382bee13d3737'
            '039a85cbd159bb4e2e37bf2ce899d651510eead983bf4b26cfc2da9ab2ac8133'
            '57222c9696b06c061592b3ebb85b8670259511362665da1685a34badfb061e35'
            '5fd598756d24dcd39a320e00ac573f9f9e52ccd1f0b84506f0a2595a9111502d'
            '6fb424f0f2784c916aaf9e8955798cedba2d01cf58b2821ef3a86bb20a60677b'
            '5e3f8d4c1d426f474b5bbd00d2a89e08df92f66e190b7ec114d1bf34342ef731'
            'dc4c1f284482e8f5c14819dd66f3eec7964da492426b487e8f284885b36d2b59'
            'df8d606b8a1ea8baf0525b4abcb568e3e666cb693f3480eb449ee17ee152769f'
            '6105500352abc90ad724a60c19ea9b616d9ec08baf8f10d1659ee4f936360ff1'
            'f7b2b4983f3736a5dbd40619830fb1ca4119b1d40c03cdf8082c38e2ea92b710'
            'd86cc78678b74f4329d036833fdfc567513ec719414fa341ae1889a0a2a11e15'
            'd0d025d7d51f109090db7d0d08a861b7bd195cf99e8f210a429da4ea922f8121'
            '8055235740683b4104af073b3661b550c2c0c65c371adce0a33d3394bd4a3f7e'
            'fed2b50036e2c239262b804df09c2e93329fb6f034c9ed3ffd237baaba568ffd'
            '8a3175e6a77029b5645bff76b83e44c3006f27fe4c3b67503f4778d042dabeee'
            'da11c3567a40d497b76e2f8d989f71232728eed0fd8c622e320e37389ac38c76'
            '9aaef6ca842d7a4eabd4ef07efd90f71fb9b3b04ed9af02e897f35b20e4d7ae3'
            'd7d6ab0beba3bd4186cd3292f4b50e10987fb9982ad4ce0fae3e322e50da79bc'
            'f08a565c26a3ec32e34eba3890fe7db19ce5511c131056dbcc9f9871002681a7'
            'ac78fc3e8b781cc3d26178bfcd23e6739c2cf2e592baf1d0773a7e5b93dc70a0'
            '09c56fc7835c7ff37c84a529bc97acd549b5fe131c17f6cb21d5cb3fbd628754')
b2sums=('cbd50ebd08bd10ac95397b61757a330bf670ab32949350e8ed69d82f1b663b37315e31e289b8eb2fea23be9f19c79c2e3b90beadd9349a1c1f8cb0644a699367'
        'SKIP'
        'bef3377ad86440af76e9dde4c29c9f4aaad42f5fe343f7d31f5eb537d6d358602f996f5d63986af275f2e92f94e71dc28c320edc8c03d05bd64dbd8ed23d75dc'
        'dfd366b283243f95c318471fe35e3a36646a38388dd6c4d9746bc981985a02ea303d75127244e9feac14564a8f49385483dfb56a8842814bdf97ca747bc2a4d5'
        'a0903f0cf1edd06558f1fc1725a76ffbf8709593201b0e60ad753c20fc4d856d5fe1ee3cb2e76266f827cd1b3a8ccb09ae3fa3bfbd5efcbd3b2f81faf46e6d0a'
        '040b2787360b2eea75dd472e968a1b903749a7cfb779cb2c7e580036cce5b556a78ba196488b0b43a9291f21f984437149f75f1a350ecb93c2aed190baf25959'
        'f01b4d18ddce8984501c317083fb9dc37d83903c86d1f838a4072e92e953de10d4d08c56b2bcd8bf9b148f2d63dc543816c5f4a592bd2fc4db82a7117fb8b847'
        '2b09b97344683b42b7060983f06723bb75c70776f78c8ec6eff7df85918b708e1e76e815d6a6522a9a58d1acfebe7bdfec2cb32722b7e636976656877a8752fc'
        '35e06305a11c5cf1fd6fa08f1e067f4ead0b4243dfb94ed6fe79a172be4122dc761536c098ff65b4509dcfa1b7bf0932dc8586c0f78d43d4e8b22a886c5c2994'
        'd42e2d35ea3d5fb06da578ebe2b02c834bc56f000075c827f1e0c7304d502422f5d21230df42676deebf1bdd5ac8308bf9d42ff2d6566ab37bfd8304ab34ddab'
        'da2537891c7352816b11e7d91c612478167a882363bd132e7da2721d718efda1de50a42d8c4f489d8d5596aac3faa66db7599705d3f4a9cabe03885b38be35ec'
        'dd6c3244cfb6a121bf34edb3f0b4fa438c2ba0081691ab7b3b0af3a20ee586b2e2fbdf6fa9f4d27410ed76316156c3c711106a087798cb908845dc01139e86fb'
        '025920b47432414746f4fae881ace9d5cc2475e8ef0885ad2bc8a7d3f1ae95b359c8dd87affcba5d62f9ce324b1943a7c58bc7c410d9b4e5827004b89b64a382'
        '43bd7cfb20868ffdf8d1185aa253e760b09ec5e279e5fdec51d183e2d2da38e27bebfd70311eb64581204bf185f0bf3e34f2bbe3cc9a815c86ac133fee6fd79f'
        '94d4e25c46b8ace28cbb397b3c24581b2cecd2831370959e3e00c779c38e52e3ebd483c5d84c6689d8cb652a4b3d45260a99d3072e1b161e5bfd53519f2c70b8'
        '86d6f35c16621c4cfbd287ac9f92a657405e45dfdc71f31895d85251f80de5b026320846c4b689ab592123349041bea541e2ff1dea0d5dc275b0eebd11185456'
        'dd3b6a501ac4b8a661d3d47fccfae7cad3b81d23b8529f80e3b931dd8a5c85c63765c30102a66eff46983f7d6f68fbc0d81ba937e437443fea19ba721ad187ba'
        'd87509a445e654a1a6089bb41b1636c88f5c73229ff9c401555a65e086e18cd4bbcf1f29f581a6b19a98c50e8a076d1e0efa283d2455430f02bbc927fd3c6539'
        '757b85bda315fbfa07fed275c44f8b668a8b9be09c276ffbbc2ed781d3b5eabe29c5c726d303c52a4d2edded19bd268bc1e85c2d099301c2004c52cd3cab5062'
        '47e220ec2cb627769f3bcbc84f8accfa5217dbed30b7e72d4dfedfb283f2fb9e1e42f61d78c4a6f46443a9d3cd4124feda098aaad19ac3d3be19cbb4ad8b8e96'
        'ce0562b10fcca0a7eba6116d45ea93e5e1234321b66cc84ac9c57ef4a506d717eb21719ae2961c5b4d35ca9b7c6beca44e07053047a4d29780dcb1d838ec0715'
        '706f53c882505cbd45b568841249ec2e6f05716cc2fd1a5bbcbce0aeba6059530f5a4ccab09db8816150cb35a35764e6b1e260b1ef2d25fd4a35a4311a0f835b'
        '6be40ee4f0287c9ef2569986a7fbc524196f2c4484c9a1b9b7c288893bb5fdeba92d80b237adfdd58e5ceefc18dbb72f236d49173db77d44f3719c26b5fd7f65'
        '6a74b607657862a210c3af009724b2065abb91f61407f22aed5611f8b6201f34236dbab22eff5b73c5f3156bc5238ce85a86c155ad4725118a0da3fc7d5985bd'
        'c9290a811188e2883680d11fb265e6273043741ecdbf4c8323d3cbaaee7dd67108cbc9947c988c0398fce716f233405e01d850546c9429a9998b2d51195a46e4'
        '97acff3937caa8089fe08c6538709bccbfef42288c8e3947daa4b04dbbee778d00f75cfd748e3f30aca3fbec661986d4471d393b3f9469ded2aeb332f24fde7e'
        'c872846af1bfc7306aaf618954c6e95bdfc907bf06aa9414d4ef2e618dcda7202038f69c827d3d0d836c6bcaeff83ec5ffd7d6f824c2d4e5b4df0e807c19ed57'
        '0f11737a5a3e1310a0deeeb9966827584fdaf80f886f578c654ce5ce5fbca44e68d420b0f65d221fee317eb1759244a73038fc8e2dfbf62ae3c17dc68ece3304'
        '162b594ea218d2e9e27e67b03ef0ec1b00f73ced6cac1dd8e69762cc2469d6b3a241ebc1d1119d52f33abe53b2e1b43ff492fe63291e4ba5b354a7c763c022ff'
        '7401bbb4a304da9eb006f01205532caae20ea7e0d20bfc0c9d5a12ce178d783a0132488e5de7cd44bb34fecf8d588bc690133755d75c5067c040e1e8787ca146'
        'e1f528cc1c1835e6149ca6ad0c383955c1f0287d9f1a6355a4d349e58d56495db94ce397a101fdec5f62807d3e09301aa2ac01ad6087c1c52118dc8f0f0cdb6e'
        '94437543502580851871dc73d7bf1d0e75c495082fa596d3caf52e1ceda60e14bac1a994e55eec61d17a2b79b64217f1de7c1a3f940653a1edbd2d7e2a1fbabe'
        'b47bad274f303e50758498e06fe1ff27cfc751bd5059ff35f30dc71398e1be394e68fca5f2fe1eae5ffb442395d52eda24e538ac21c389bd29546b5733529c77'
        'fdecd5ed4efde861f0f219fc704fded93be0ccf60118fe2893c166bb8ab895c204a7a77806d2e8a6092d516e4b70fcf78400dd6ab4d1c43b33e6e6c9e1c3efe6'
        '51f71d0ed597dd5aba180b3a395d2f24ed67773e77f59306e71d7d8822a0ae2c47b147c5c78a8cec5a28f833f640cc2c7a84a9bbf94b3fb2d34c993357791864'
        '2f946e008b00870745bf2ad92f9ed48d0ac5595f731849aee74558cc861b9ab70b7c41f9f8a07f13325e9143c301c63d800685a61cefbfc745f97375ea3732e0'
        'd31f1e69ba2f0bef221c1d90de5a328a156dc438b195ab46be64c907c49cc21a26152a9d773dbb15eebede11851526c7a680cd9ac697643bf6bee67eaaa386fb'
        '160aab1935e7467c85cadada50c41f0b5bd44a204b43441f6602537a53ff621662ff0e6ecacedb2bce338f0ab3a1a4de9a25279fdf611bb00fa40241edfb8f74'
        '814ec5f843d513304f63d0dc62edc73129f59682dd931d27c1d937694e3719ca8fe630084f64bcf994386dddea325f5275bb898aaa343cf77c19ff2808d76c80'
        'd89807d908796c7b00a12ac82fae97366f732da85ac5514ea4aa6ced96d696b34119483982da4eb5beda9aed7e82ce4c2a27d78d05f4ebb5de234c8ecf146fc9'
        'ff8ef9081120dd8985ecc2c712bce7c7d67b8639b463d5a3741eeb9b3e1170f8cfd8f3d244901368d7e7909a0766524830ce928b4d782f492dea3451d1bc9374'
        '0effbac404203d6e5516e48b88c43de4ba91734bebea55ae80d9e6e618d132e48005cf05d4d2c0c573cb2a7b1ff0e2aeacca8637e7478fb175aca12de7615df2'
        'bda024b00935020ad6504a6ed625621fe6ccfcc9b826ff5be3e061bec5ea7db86cfb0aa42c3d893d9096319c113d9d1d8d71fc4c20cc53adb06cbd3a5b3f0ff8'
        'fc09fe176e7871402cca02e198958ce1067cbf1a6dfe61cf1fea44ffec4ced8715178087190b28a20d09fcb633d47b2630c8e6716c5000dfc4d9a59c60ae97cf'
        '6bc6868a35a8a14fba25e13c3f23b0dbdd913f202f5c8e05f9647ca8a0c28b2c18800a3b1746c8b22421b53fd1f6979c0c220a01a40e84ca404ed4d06514bc29'
        '393323e9df3143cd3a74daea1271f2784f0bdb2a3cd14beb3da89e971c53b8ebdb740d965b7eeba93cdadc3ef5747cd869ca956dd12fb682231a1c44e40ec772'
        '573135591a5252e9268ab488e2f482adf995cfffd2ce149f275888ee73c589f568f268e0ceca180e8b3be6fe7ee407aeadbbc48caa3290091ae95dca0025e2f0'
        '4506983a0113fdc0202245f7d24c4e27978b363c8da9c575b555e97b763496ea501d76a89597f469a758f79906602d90bcce81c60a9ace04bf6f5acf6bbeaef1'
        '3381942533b8948dc2cf3b5586422e95a8c96c00e630f9256388cc1cb4652504a25869134e117fb2500b30aabb96084e19357a87924d24b82347a29486365316'
        '38db22e19c76e402bb2a46867c4737fd6700c6cb2f3932320a7fa182aad624ff1884eb6dca3e3a901e3e5292a5009f67d4531816a1e808066eed61e5ecc8c70b'
        '3b9e6953a1c249ebd8c28e7b61e91e035c544ee9653e294f6a4026c710f897f345a454863430ab8586672ba179411fd5bf238218298593851f141d077670e080'
        'c221e3256249d6d78340d404e42b5f18f518c9c0988ef4d79f3031429fa764799cdb7aeebdfb4a8b8e78e9314f87fcad3a54043de791b48d28111dc91a690b13'
        '997325171fa349c60e386acf8ea5f4353868444e4cbe55738df0aa4e934bb834f43ef7dca75d8c9c1e96c5af489c2404c8ee478cca1d4593867fe922d595e3b8'
        'f186533ab4b33e14c5d5f5b396843f967464c0d047314b5329daa5c0c048caa76e67f3426c2cf49993494e4d71ede746ac2b1a79ed2bc87bdc87d2f9ccaa4c61'
        '88021ee0efc3e45f4e19a9407a4806324bbaf46e56ec7b5b89144562e9eecb0c9bf25ce01c9a41295220f15a52fe1c0160e9952f08efdfc2a541eec387caf856'
        'b98cfc08ffc29e4c52ef7b623053cc8c16ce3feb18071cdecfa2caa83cae6ffb74cd31c41e43db459184eaecd7412f4e3364a531523bf7324bd56792b0d4cc5e'
        'ba87f21ee7425a9d337385411df4c8dc3ad608f611b729b35ba49e5ff8150563c46b41a24cb7d7f5b4bf61151e61eb73d2f33e18fbe699e96b9edc4dba353beb'
        '0f4654fb96403ac013aa7a44868e8aae34a2b6104faaf7835838860739bb36d734f182f305f43c2506e75ab9a3a11a180fe8095fdc65da50704c20c5d342966d'
        '6dec5f96552bac9d788cdf14ef11f6763220f11d886a529c5ee36f7025e8c10d5a26af260ce39ceb3b2182d484fa3f420463ac525ea7ea13eccf29cd87aba48a'
        '9346c7118ba5dcd6a1affc294e1876ca2d52348a92151138ad21f12d4aeba7482e6636562478596ec79f6b12731537e7a40002b4ab22989beb1a89f815b66899'
        '5f8789cf543b31eee1604f92dab158cc09e0292309261397030319b7f3bc644fe8568d3cfb1160dee2e1e91748b86eacff30383e89dc3b24febe3e60abb5295e'
        'ba7e76b66eb2d8c9131dd484851e8531adcc7307a82f9ec66768d0959bd65519e3c86b76339d5535999291b551a70d318348660ff489a0837c4b40261edfdeb7'
        '56d16402e30203e3c07844582c9e87ac6f2df423955ba8f08d262c9d1057d80d5fe91af90ecad227218de674b73b21a500cb61ec53f7e7f3f021f1055b08f5b9'
        '9bd7254f20ff7bd8d289c0f4df5a04cb43c8a2b39feb487a331cfa2622a7b84a63ba55ce7e7cfbdaa0d32edaf918afb000895c4944fc8375f4e09253610f36c7'
        'f79302d443d77faf38cc91093610396c002f35c6ebe054dd51135b32a29f964de9ae5a9b8f07bc3bbc94587efcaa013354bc8e1ca856081a273de4650873ab87'
        'dbbff4eff4564eb6672f9723843d8eef8e90cd6f14a0ebab50a431c2e9343738ed2fca4ce87e6555da698848de57c22470242a279798eb536133d1bf98b2eb1a'
        'e0931fa5bf69531e58cc8fd8283a97ba804da331711ec4e7b133197da4783e4d0e488c0d1fa2ed9e6ef230dc2060325a522e2d9705449ea7090ffbc61d40a263'
        'af7585980e686fe3a56169a29c58002c7b59e0e940c7e788409a3e368410e2b548bdd9f2d3e8738dc21efc576d763ef9dba380d11bf38043872730f846f8c271'
        'd25504cf2c9d793bec6a3ed77317c6758138a9ed82b8af6c1a2390587c8a5fce5ba046223e8d796c3378b2bf9581ce560000310d82dcace3271bfcd6f963c580'
        '45922b814b87167aabc9d0e2c18808d434b5f81dc753cf402ba0090ba50e3957ed4e8842556e9876160bbcefc64c4c93fb8f46f2412ea039b259c9ffc1c7be4e'
        '213187efb7945ffae32cd67457ea3be6cc2537435b4ac18bc4e64d141028e4efd9d09c72514d79f1b51af8b0f5763a8a6964312dba5aec24008955a72b649a53'
        'e2568a11518467cd6c970a3391044ee6c4ce3139fe570faa437a951064eb211b6f4165440662a17c64cc54104e7cb17c8f2a8519effbacde27d1e787746ad21e'
        '19ee27d990e0e68ae6d1ea25178cdfed7e99c7aa3ca033ff6bdbbff188ae6df8d399cb7a088f7cb0562ac9f3485c56dc0790be308fd6bbcd4bee5f965c26adeb'
        '9457c9c40424882dd7d204535bf57eea15d1df510a597416df38daf23e5728e3670c67543c8ded9160d3daf57fae4888901bf43abc85befa689fe9e9671f2e9f'
        'd42a538f93f2dfe5ef5018cdf5364946acdaf639364a4874717774cdbeb3c5f5a0d1457a6037f554afc8d4b394e9ebb68175f096a13e435416d628013493c199')

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
         '0002-Arch-Linux-kernel-v6.19.2-arch0.patch'
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
