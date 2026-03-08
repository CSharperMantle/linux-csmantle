# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=6.19.6.arch1
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
  $url/releases/download/$_srctag/linux-$_srctag.patch.zst{,.sig}
  config  # the main kernel config file
)
validpgpkeys=(
  ABAF11C65A2970B130ABE3C479BE3E4300411886  # Linus Torvalds
  647F28654894E3BD457199BE38DBBDC86092693E  # Greg Kroah-Hartman
  83BC8889351B5DEBBB68416EB8AC08600F108CDF  # Jan Alexander Steffens (heftig)
)
# https://www.kernel.org/pub/linux/kernel/v6.x/sha256sums.asc
sha256sums=('4d9f3ff73214f68c0194ef02db9ca4b7ba713253ac1045441d4e9f352bc22e14'
            'SKIP'
            '9465435c9e2a655f5bd73b5863c44e262d6e99e9929467f1d647bab2dd5afd26'
            'SKIP'
            '9fed188f89847418aaf6416b64457a30bee34dcd0fa42a84dbd0f4dfca063402'
            '157126a09f9a0db855ccada3d560c5a2e469c91186596b7f6b15afd2b983b67f'
            '8750c285dc48f1511e565062069b2a027cc3fdae6bf478fa4e5efdde9b8cf9e4'
            '4f16515db7b0323d74eba2ca8181377e59b9b25c62b193d657012a97437e04ed'
            '3f339987d5dc940da3826254f4da2accb1209e2c5bf729904c540af785b6d01c'
            'e7f3381426ca0cd3b93d5e363723df7e22e1ca00a3b72c10551dcd7fb71ecff5'
            'bd85c4a77ec36bdd72214483cf35a806656ff2b21953fc727aaf6336f1aceee4'
            '53bd9a9a0b855232d59b463cd704bbecead5d4433bdc5d6873876f39e2ced8d1'
            'e3342b24a63a627e6685762dc7da1f04f51e2cccd5635c51bef6e0623f94123f'
            '5539c53d41bf5d19df42d2f1f46ac89f34b19f0bb41750397c20ccb0c70657d7'
            'cd2a366139b64923defe7ab33bccafada733835c9a53532b44f0ce3cd29e4076'
            '2b5fec505e2d61b35acf2fa7743f5aea9199c03c3d0e513d1c385a032df0e4c5'
            'bf78af7a85323d89915ed060130280dd19d519d623aafc4b4e424fb16970645a'
            '1f04c8585a0913b4b731521dc3136b3727160b8e4b68e44750f842669c4c62bb'
            'f2d38491b224229308311866474128fa393363aa213347013755a95465b1f699'
            '948b2e26036b831a7880e4374fa8895a637ceb5cf1c693d5a46b6855f80d9754'
            'ed804d19e4176681aac33e8d516babe86b320f0e60364710699f0e7af1f7a830'
            'adacc1a9b02e29716b9bd11a02ac3376f8902bedf06d3365b1ba6309c3240106'
            'b86ef4690b4f399533a14175a8b43613d997227215cfc6cc1d32d1db638f6db7'
            '67a138f965ae2dc23d518a872826b17fe038a747a24ac9d09a1ace20234be43d'
            'ea20716c687f7d3ccd28fc0a0a77afa34f38e30f40c4a447cd9856cc2574334e'
            '5346c20cbdee5477240be5c6bb45927aed8f0e42327c239900002e8cbc2bbf76'
            'fc7d2e7f6179abf174a3ce34081a363d2692baf069c0db2aa779b77ad04f159c'
            '974e328d1ab16a989a4453327e3a74ac8c3e0215b34b8461b184fdb9922e5a88'
            '9fbf6a3c2912bee4c3a0fcde5e8d7f79985384fae6a18fcaaf5dda7104e1302b'
            '0bf67c5d05f620697ab17d128d59c86a61bf8596659e7089f2d772387b44b50f'
            'e4ec255502b3b174cacdd2971676d1505ae4c92df6593a7ccc5a7c7072aeabc3'
            '15e32927ca934c3ed06a76fba3ded25b7c1898ee5e5c5dfb5177dbf8f45478f0'
            '8210e49cfba2f0dc27efd443667d9a28e1ad8b09c4e56e7179373c6793f8cae4'
            'e386f141bc90828037f306898202d1bea4078eb6eb5bfb4932f5a5af878603aa'
            '982a5e313d3e94311a1c5a0b5af658da113e721822164f4b6af973c64f1dd8f3'
            '2520afeebba1df4e73748ab6ae5c97e505f34a2940af02146340e76b4633d47c'
            '5c6cabe691a4c12560c9420a0dc0df94ed76623ca07dc0a262268902c91aa82f'
            'ef192bc9b1d5cd70e2ebc9bd5776c17a5c774b89c75df44635ced412bfeda70f'
            'bedfb37d10a4de13b8f736ef812deb45fada9a7902e42aaec2e2ba647e9e4b4a'
            '5e0e708f75ab5df98d4aaf81c91518923985f50518b079fe705c91c2d55a039a'
            'af53c6b2ab382592833db8f34463c958f6cb534eb0f59998505a17d8e666e32f'
            '2b457f8a403326321e79de13a5785aa78d62c2bf3fb49b34446dea3cef6a85fc'
            '74f712a0f43c189170fcee66d3acca3be3730474ad9004b694a6ca72921a5c5c'
            'b16984e15a2694f48696ea4b14a4da0fc0d3bf80622b52537dd41c9e343dd05c'
            'e5d61dbaa7d86726a2e8e93f391a764dbf82b787d6e87467c856b988404a36c7'
            'e0fa404153d29ca9d97044c4bfada90f84621cc9e6b895b4a8b6617d4deb09dd'
            '6ba5aba2db31d8b9cced602986f5cfd7b65b163431d1f60beb29e2354de29408'
            'd58249efb0989d05ab2fc04ed3e28e465dc4ae4570834e9c5e97b44deef6a9b2'
            'dabd152782dcf631116b766ef2f34c5fc6054f77968802471481dd7a041756b6'
            '3140cde844fee2d0f4173091b750b669202afe40265f17c5d95604108bf6f23c'
            'f9f86683d7a33b5dd133122865ae7ddbc553ffc5d51f67d99b0ac2a3fcfdfdcb'
            'cb8e7d5a4fb6d2206bd22752bb8f6c003aa35989877dd5dd97039abc8fb7eedc'
            '78d96493ef951ed703ca8ae2847eb8d6c9440e30b564e93316e3b5a1630a920e'
            'bbb489103509672d9a61e67eaf384176d1f77033eef3596efa2ff47b99d9880a'
            'a55b96ff1ce795ff33cb33420983e1996c4f4d7d81c86fdf4de2c1f1bfeeaffd'
            '89083c043df480ea1328175bc0beab964a89bda964681b1adefc3c44ecb8fce4'
            '21f2249dfd3f564ef2b44f98e7fa9ce1ff29f5b9b9c0663e540e3f94534c2d18'
            '54592dcea70006454a694c1badf08c271c146958bbd5928fe610cf7c7929e051'
            '412bd2e1b615d2a151a09e55e59c075067412f035232701a9af56d60d644eea2'
            '58c1b1634d264233afb6859baec09b04c8e2200d0337a52ee803bd96f5cc2fa1'
            '89a82b2111c6843fa1c4851c5d980c18bf7d971bb12ca007cbc2c96d76fd1a22'
            '9c6332c1a41f08f2fe8a7417cc5f6a4b604c2fa3c6fa8bbabbdd4f0307a43518'
            '5d727ecfd1898080b0f4ee732d380733fff88bc19046adaf25113cc87f91395d'
            '0c1e8577c29d2149f263814f7dbe14480576734f798e99770924261affe3d721'
            'ebea9daedc17c553855910d0fd229105e3ce776a15449bcac14571dbc2f9be21'
            'be9cb203b0813cdcf06d73b7cc7cf9b4bfa1d65b1d8ab5b24b65ca10e4053675'
            'f8ce788624c7f5a7dfc61f9d5dd1c5c55de68c113b7ca1fbda1ed8c80485f784'
            'f1d9a1a5669161e55f44bf755ea3b6106329779a6ccf7c4e7a62b1d60a57843a'
            '4e7fa54974f2ca4bc76ea4b67bbf497f1255226bee3a9eb3e0897cc91137410e'
            'd5499093135d76ef390c7e6d87417f0bb4da371c32272e88184290a8f4fe5643'
            '7ca2b669aec8620fcfbcf5a92246ece9a09c42c0f7ca8d6538f8c7ec862626fd')
b2sums=('612fd1e944194c20bb2e6f9d2b309d5957db5b738bcb7b782c9c25de4c02b341fa5caa9af76d92e88628135b8334f550cc2277d63738098fde950ca05f46e89a'
        'SKIP'
        '8432d3a2fc622cfe08960b1c7e7889c3bbb3f617a0b6c04111f064c792799ac512b0704f67559090535f2b573340c89479997497ad6214aa088283eda4e32cc7'
        'SKIP'
        'bef3377ad86440af76e9dde4c29c9f4aaad42f5fe343f7d31f5eb537d6d358602f996f5d63986af275f2e92f94e71dc28c320edc8c03d05bd64dbd8ed23d75dc'
        'dfd366b283243f95c318471fe35e3a36646a38388dd6c4d9746bc981985a02ea303d75127244e9feac14564a8f49385483dfb56a8842814bdf97ca747bc2a4d5'
        '8f9568afff28bdfed46375a11adac228e23d36bf6eabac99a4b6596aa093d1eda8f8c06d712d0643912290187d695b6ec2d52aaaa5c3b0736ccae7006fb533dd'
        '0d2e54193002da845c07d91b2d29b6548807d551e591dfc53c9c492a5bf7cfaa9ab7ef7024bc7d71260d5ad36ea5b8b33b4545f47662af36f5098fff1aabb68d'
        'bf13a66b6051c9f3172017b95c669953325b72441aedc6e5f7d9eb5dd7d3e5bb3f14d14a96773092847dedd5d4c93b7a56052e8dacb284cee1ed37a69fd91a5f'
        'dc64f2035123e0fec0a03b3e3f5c901183f34cdea43e115bdc1e80690b2a24f7d1191c98b4eaa15d67ad8b461a7d6642d156af5eb6e3aafdd14141fdac0886c3'
        '97cd05cb580b61616c22efd09483b89f11a072501f4b85ce4c6b0f8b25cea4caf595b46cd6a1519690c7089de41e01a73fac92f3f6bf0e4e647046d10b33d03e'
        '9da710b73d9ddd06c80e6c18333419ea7801af25cddf2dc100c8c3b03a678fbc731b44498606b8ab943491f917e60bcd889893e6a212b0a96f59262de8980b95'
        'f2813d2126674906ca03bdaa9821ed4bab4aa29bf4df4695f6c05fff7a6c4f8f9b239c105e18540b788e36fb667e55349a7fd573f3daff5dc5e88f00fda7fc22'
        'ff6436b1d1c9187eb8451ead79474a72bd9844c13cd3fd0d45f77762dd34b5d2b8ec63e3f11ca2042f3b8d7541e3ebe4eb440467a3d21060f53997bef39fa07c'
        'dae305df1ee22cb94da4b59806511a92016ee859a54b8222bd351a037e7a2cf6d819dfa94462b2210710f374f3c67b1d69f26754e3c63a5a223540290c716e9f'
        '91380c1b0b4c3df71a36940d18e8bb483f41a1b5449f30e0952354247a13e4af054b4e20a09eb8fe350a1f4fc6262eff82dcd9ba1bafe285f7538577c5bd5f6e'
        'e4b1be61c61065fc779e9149f864ab502dd78292a46386fce462135b27fbc8a9b97a21e4f9f6e65e2465bda4b2d10c2be27c2048ea9adbdc22d8d0dfa8ce3e10'
        'af9d2492f966ed02ed216ead2923b42958d80c1a8c3723e7e7dde24d7b17241923deda442dda7d7bb38de9459d6f1c76417d2e08858fba923cab3db2d42426bb'
        '0b8f49e9dd352205659f22ce3191a171b6f2e6f0351c6e0c3511db059bc5b53db181550e8ffee43ec70d89ddf3457935d7ddd0d6d947f843a33b6932a7ca1c6a'
        '9ce1eb8493d56bcd41d1f1022d7d7fb5a44f67a7adeae6e10094f991388d1db4e9c7a9ab8efeb350938c19c9abed129a4f7e9cb25bad2053f3898592f620525d'
        'e28b4c74fc04c7b3a6391a4c9e6b53da6c4cf5d6396cc9b3d7f9c20d22fb81e90e80e4aeb6b1b6a0fcef6de2925744f24b35d1cf7fc68b27169dc61619567ee8'
        '75a348096d492370b87b9ab96812fd7241cd97a70b462381016eeec970b0613d92f1484ebee722676f51055a355d446a90f45aee1d6f57863506aa5e193e267a'
        'e6b3f8c49e5c57dad809915f47e100b12fb6749ab644f5576256adb7a9537104f78a430c1154a38734138e7bb8cb895ec388f057a438f454ad95d5136d99c874'
        '7e586f6acdf9f25968a2ab41b7b9658e3b2d0a5c95f6507064873ac8ab3b5c660f6e58fd31955bc6a496ca7211080d764756a960638bbe030be88df5ee013b20'
        '42d511ea2a8bded6fd1e6b49621ad3551fff9d0dd47b893ca51c4f31dc6c07d359d3edcdf9612bd48082e52b1811e447bf18998a6086a6fc14c130a302dd2d0b'
        '0695844107f59a7169825e037c1be0bf818da6ae53d0e122ac2196f993d7c179e51745776043b4514e82fbf1ec9e531b68a640ea4a2892bae92e0f3e01de4155'
        'c5bcb40dbd0ca614b69dff1a887d83bf6ec6206c34cb9ab6c5d79488e538e010e0f94ec8c0d0dd929e239c9bb36d6a19d0a48f1017243db2d61b2dcddaa08f39'
        '409dd2f7c722e6d916ccd1465d3be01df421bf23bb78a74cebe5095a4f84bb27e332a041f3f0b7dfdd666f74b173cb70a1943ec6ad69b2e1cef10ee61e99bed0'
        'f8ab50fafa6d441878b2ea16bf7b2fad2c8352b248bbad68848c94e2fd535080257ef8b3f1f27ddc28a0e451aea23b802b4f4516616ef8ee7072e6aff5233fe2'
        'ea74a520453d173faa9baee0cb86ec40b1cdbcd737ea8184fe235697a2b284593ee34b88544aa9f0741eff7e6872cb9c664f9607f416a7d008568c91407e10c0'
        '23d4d7e6c9dc4d7c5bfafb47db4f0654e4ee56aa8a283356aba187244be6e549453ada9f1a63cf051fa3c311a3d17f0ec9a8e36733c37d665c2856f889beb6c8'
        'ba898fb221aabbf114c5c615904248c6f2d681dfbbda702820a502e8df982e6f299fb3a4af88c90d7344323d7c998ced7e6d0be78fe148891966007198d78a6f'
        'f1f5a5bf1ce602aad9c44a7ec75d834256836541036d8156807ff6d5d0773d7f85ed1ce6a5979b8453143659a8a0b07dd06cfee3ed52f44bfd6fe9466afaf921'
        'a4889101625094f45ab6d4f2e186e48eeafbdafcbdfda7e8efc224bb8f5a2b4a19757d529ab5898ef2d41f7d5ae88b786be2213c196918bf7fde77915e2f95a9'
        'e9d6d3982c4f2ff45bc50831f617cdee03b9e777de2dc5a51acd8c328a01110b3439872e2882885f63d9a833805791a13bb808dc6933a5ad51c32937f12d5ed2'
        '59820d5544aadbd37d131cd7149d761cb5ee6a53d9231735e641c815c1b30dcf8a0ff5b573ca8b5287c7daf79b639b695333e4ef4eed2e1277f27dd25a973be5'
        '8f5780e1c2b5ec4e5bba4732b7ddec0cf182fe212fbdfba2d70c60268897512240d31bcedad895e211fbd51405b7abed504aa0f3bc8cd68efb3a55a40a7b8e26'
        '3da30e3d0e69c04f43473dcf7da9c932143db92b1e4685dfc8862a452e0369144c2c74893f6fb2f7964dea69d5766a4948293d4285efd940b8d6abb8614de52b'
        'e2b9433596608f33f23c074f9e6f92e337a81296df056626159e06e0dddf5bc6048f13fccb00f985e6b550bda03ea6cd756caa3256f891830a1aab8977e23d48'
        '5710455ca3221ecbc839c50927464b9c8f627dc63d2b72a9d369a3b0980c1fcfad9a00360c3bad2c9603a83a8cc00cd24e9b75f68063ed0d934bce0c1943d39f'
        '89dfcdb3d494f6fa84d05eee8ad06df20340c0126b71c57d8fa03f098cec6f79af44fe900bdb6356c8128ea6134922c976cc82724e70c434c9271a1af18fb924'
        '15392c64bbccff11584137982f6cde9dddbbc91de1c183b6d1007f4ae3beca0cc275877a8c4158a40aa8b34ef31540c91e8b83c4764f8ac665d46dfe748cabfd'
        'dc88065cd756b95d73be56f1b490434e688ac021ddb87c8bee81b64e35a6515d56fb7767854d54b25ad93baf68ae3412a5185d47ac3edce94728c49810f2bd8d'
        'fa6ea7670c9b4264f634b76a01dc91f331701eca75ac2a2ed7044ee1ffcced0382877f4ae37d2207a7a815eed6cc7575613d21e87695cb1ad0f637da3e5ba207'
        '7676af36d4bf7ae459bcfe315be1376ef86093de9cdbaa470fe00c7910f39b5d194db3a8928714f2dae40942acde2c23f94f5f66f3b453ab8b4a77a2d86042a8'
        '7ff456b273b87c9f88cb9276e427ca575fec38c56e6406a93c86d57ff974b6b306580008d9fcce55303227b6b9b7d215e605e02231ad500eadfca6fbfc75187b'
        '30b0601255dd220da20ae0022fd234c4f73384f8be3c915cb1bc0c7b1d485b7695d4608ba10b3ef425137a7c31df529d8f6162e4f2e69fc93267123f8cf8bc5d'
        '5c2e3ba45b901f67329823d965794e24c4085b666f332359a71e4ccb9755f7a149d5b4b1a1246f09700087c7e8b1ea49a9a9ae11fe7818ea1eba751a5a340bd9'
        '9671a7454cf56918b8f8fbbe724a6ff6817ad07679108bf15b5d3f57cc135c7d2d455680beedaf56d4a52147ea544d1753a6798e4a9b73f43be95afe2abcd307'
        '5ae5716ed47f53404e6754ca5b203c7165b32ed6d0e360517eeaac517dd788cd5205373b7ef1181d1d72d9e8cc8ad0550d0fb72f3d69ee3b7e18b1065e3c7f08'
        '5bfe1babbd7752012a29a1a0d73485a88c69f7bcd15051e79cd0cd4c20177f737cf079146a4b75b6929942ff0295e2aecba855331d968688f5b47b7673985515'
        '2fabd37b630d6c4fd0338bf0880e4c6174a91fd328c49a67a743623bd989ce71f4019c8497d6ba46f686535bbf2e57d35ce90c48c07b70ee9b49522a2c7e9e4f'
        'fd6a67640a8848699b6b67d9566385e1eab0acdc14a70674696158124fb2d8f1a08b0f96c7e11caac218ce0e202ba71946cb83562bb633f99d9843a79da5e15c'
        '2432e8512db35bfb3720f2d4a6bcd82078f35bb446a08c010dc89c1191ca0ccc9cfa56621aca631214b7b8f5ea89e9e66f9437e28e25653d139155c7aad8a959'
        'bb895f209be4ded2ec6c732d1b09ddafdcb0292f84a93f93f79ca8323c057fc495ee34b8e4fe4d299bdc3972830662b268d2c174d69b39d41149bc600b66fd61'
        '1e013f0c23ccdc0232c35e88af092efb3e01bf8ccf10b2cb6831f4ad29efa44f0a29f642cf92966b4fbb5811f3e622809e08a4b69ce366f3ad7fa253af9353d6'
        '703ae7055a14cc8aca6229e4d82d6120ee4a496bd3cca5bc7ab611c0a6cc338543e62f063370305426f743e7ff4e3ffa8f3f3a924ee0f62cbb618ec808c83be8'
        '02e27e33b86a8aff7e02228d1ece9f97de009fd51c5e6d823c84bd87a85e3165e440681c515fc171bfee1203515d9a7fda4860835c6ded65831f5a2e5b9bdd07'
        '867e51365d9e8ba252d06064657c139211ad445fe3e4b6450d16046013a47c81168da9b47bab59f6e1b00cb84e1f96f60a91d468605a04936f992db105ed37c5'
        'f2b0f636887ac69829eb931ba8cdb9646d89fbb3227540304589129b013f80e576acb3f75b723101d15cfc619db8db098a7fbc77e5ef15496de715f11daa7dd7'
        '7b7e3089fd126f1038a49229a97cd7f4df57f1b2ded6f6c95085a75f1368ca9786f16d1301a53265ae988ec746769fd8cc06bfa0b6f27772b3c65225aa2d3b6e'
        '65670bf743ff938870fe3707f7aeb59e1ead8e07218b9313168aa744256f3861edfd987a266dd58fe6b97492242315ab41bc8dbdcc50804ba1397f591a842a8a'
        '07e14345e8c80609adacf948f3d391f0563ff961e7f572b299ce85d2e9408274e776c410e81af7e279045dabc28f54e5fc756ea02af6d075f3e1916aa70b288e'
        '75387e4afa4b7552506fd052a4a479c56b468989b139604ac8912e7c97d84bba04639b0a569f686c1029ea848b9f2f0c213fdcfefffcfc847c69d5ac0ad493f8'
        '9b7195720863bb3d78cd1323289357400aa8ca82c8940f1527f3a9c54cc607e02911d05b0b14d81d2f9074b2d915c86297ef4a8ef5c9e33bb27d7a8bfc1cd366'
        '19fe8b353a6fca4638c422bf490dc8bafee051e91dab25f20fc8d126c8a503cc4a382a6c2d800c5b16ba1311c008b86739f143cd557314c0d6108defc656039d'
        '8aa192acad85ef6def322a065e5797e931feaf85b40ce9eff7dc68c8f776f149e3287d1d3efc1aeecd7da465629f8de2ec5b796028015003eeaa8fc7883a1d12'
        '6cff98d6a036de590ed9c618d3e9375862ba72fddb0155932771ac75b66f8823688cfefc5354caaee8571e07920bee7758688aca745d53c9c66fefd7cf4bc15c'
        '31b2883d7c9f5ada2b37ef75d4e7c1053b0d210989286bde7557e04294db4fd163f6cd811f7f02e53c39644b122c47d7bd5911f31f9b5a2a26726be3b15a19d2'
        '98ef7f2bb3196ff470db638e745b92cc504b4bea59ad799e4237dae22e669c71f4010ce90ddcdbbbbf7e36dc9ea96e4dc171b6f85711f965af06037109b25c91'
        'c097968bbd5a422844cafe500a70aa06fa56ce9e0caeeffe4aa59e2d48846ca0883e604595ffe7c1fdef7e18985ce2a69bd07dddfba33bd38f611a499e2069da')

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
         '0064-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
)
         
# vim:set ts=8 sts=2 sw=2 et:
