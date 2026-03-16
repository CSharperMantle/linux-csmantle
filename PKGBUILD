# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=6.19.8.arch1
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
sha256sums=('aada4722db8bcfa0b9732851856d405082b6a4fa2e3ab067be8db17cdd115b38'
            'SKIP'
            '4d02c253bc7f02101942d073b3b855c2a7f965db442ffb375c6259dddca240a4'
            'SKIP'
            '9fed188f89847418aaf6416b64457a30bee34dcd0fa42a84dbd0f4dfca063402'
            '157126a09f9a0db855ccada3d560c5a2e469c91186596b7f6b15afd2b983b67f'
            '87df2f27fd2e2a47f7200d49ed369ec74f58b0e0adb1969223b33817c055cd06'
            '5cbabd63ec65a61eacfaa9871cd9e4edcb0a12e33387c53a5b2565d36866af3d'
            '90bb5f513bf614b7309aef1656d91452b62ca53aca6ad7dc0b5e76cf7c9a7f89'
            'd6067ecfefc51cc6bd3216bb499b8a2d748b38fe062414a9a61a70be158bab68'
            'ec5294657769a48be880d9a6724f961f3ca111160edba730a168c039ef64b4b1'
            '425090dcf9312260e921faebcf758ef1cb12016975e05f48ec1b321e890cb926'
            '56f58a7e4739fec31a749def844647e6fc8a653bab4dc8367e25f667e2dc611a'
            'a1b53d26ce8fdeca414e7398a6023998fff990745f1d10c1f4c98b51bfb628a1'
            '20af898eefb99039b6da06120053a2b9a90e62fa973b887d2f9daf2990f80e9c'
            'b1007c368ef5bc29775c9ea172478bd9b2a23be0332874e593d3deabcea4b829'
            '527a5ed01851ce9516636a82b2989c3a667dfdf1e53209f97cdaf5956aa11118'
            '46785c03962005d7a173bb72c79d62b46c25afd3605f1c4d7318f33fe3a80734'
            '3f5dd32a0e9babf05d2146ba5ca6693dc2793aecaed8519934e7f85282779d54'
            'ef329342c768e6aebcca63eae1e0a7b0f014dfd1f8f8780ba354f58cde6b635c'
            '3d8a0852e3b11de3779f8855b20225b86f8d26ad13400683ef44eaea729ce5be'
            'd327dd435418519be6baf93afa6d6382b8143b1270a662f0e3e3d6b5e437b502'
            '25d31a37a569993453ac750daa99086e4c0042ce33e48506d967621c076b4c8c'
            '29dc7bcfac4b12d78644ba9e77c7e3164ec2363f9ff6173d722bcbf692364094'
            '1f1c9f4d46c577f3b3ab2194a4b506e2908861afc598ac9168bf60d8bc3f5736'
            'bb0297644c202b3c85908fcb4b48abb878c191bc1474408bf741b687323e582d'
            '08004b11bc3393d12047f905b26b634b3c423b5caabb5de335658ab06660f494'
            'd24ddff414ae31cc0b3e6a6d7a848dd31a19049e2edeb3783fcfb7cf76f76bd7'
            'd126c97f2e94570bf9699c17ed9f823549afb0bd1ac3f9e1a98866054b5b087b'
            'f841d31f1804f2ae7ee66e89d8a9a3507d40c50a26b4e6d62669217261f40fdc'
            '11e19c626a3d131ee8a881312a5665c3e9faf64b9f5bf638ed45075d599c7d70'
            'aee9a42057ac6d32c781e6776b7867196027222cabd4d5037b74c54962a30015'
            '9791feff2eabbebf0548a0accb65aed74b757941957f0cda216eab01d7444eea'
            'a687706c953e1457a5153210a3aff4cb2e2ad2d887ac44a978bb331e17506524'
            '1a165891ce8e6750d2b2302bd2a2ef7bbf1e82bb6555cf0a857ce2d23ce2b400'
            'f5d2677f4eb25b5c4d6a5d2510ffe9b9197045bbc62871f5f85e5e96ed35b074'
            'a3221839dac71df53faf6eae3fe7d14e7b2a00aee8c8dcb64657089826b27933'
            '0090eb3da36bf4f8cbf388d2b26c39a62581f3e3b45bdea861f18fb4485e03ac'
            'e2b6a2a6eb85d20611e4d85b076ed1623f424be88eaf03319f8dd82218a87c66'
            'cf6627f67c102fdd2c50ac468fef42cf9202f56b549fb7fc619f5a4f8684f071'
            'bccc66508a11f5b350e1d77bc51a07e8c871366c79268730362f3b24391fc252'
            '31f1aaf937edcab3a815f7189854aa0ac1af9ef1d66f435c3f78ee6f7f3c7734'
            'bcbf608a2088259070080ab0dba74cbcd69a7a1e25a4ede9637da259b6d253d5'
            'ff27f200112dcdcafafac369bf7ac6b66be9e179fe0754a5942820ba383070d9'
            '696d8f157a23160c645c31c7e302f37594a1f6242179b03efed6e934272f2980'
            'eb855c62ea219a2806302a0a93e79a2fe7b7705d8d1591b9256e86bcac57fbde'
            'e9f9491de86697ef9b3dbe3b9259c68eaf358d08964344e2935007f23b3a18d2'
            '5240367a598e11b5c52d8f76e542fd637a3942c43d221338989fe433600194cb'
            'c51ccf9094f99b1d29e818734a560e9c495390fcb4d06a9770e0c31e2e274f96'
            '731708a13823454ad5b4672c225b059bdf8d80068f45f4bbdcce9e6f6e745216'
            'f5bfcedcd105ae560fc6086cf9d15ba6d2ecec78375a71d65180e7d0ddb87200'
            '6de7115eceec64b5528e4e951c918fd7dae51cdcc5ce8bcf22c0a7c725418869'
            '6f85ab74ac2b39e682af0d82790c588b76c81e48cb918dce41a24baae962add2'
            '6c51310b8ca33ec0520b51ba7bd2f5ae0b370666760313204b3dc26e88164dc5'
            'e401e977b5a59b23a1fa6d7f01868e786d228c6e0b9b98d567768c8f6d237300'
            'dcee561563ccdb00303a4c5226465febf8033e59b49632202417a056d4b535ef'
            'adf448b712bdba863ca12fe8b2021ecb84168572452131ea953fbcbeb80e707d'
            'd3a059513c3939784423d4000762c91ace407a6a8a539e5249dbaa8f7c416205'
            '6a6a7b3e889a246d36a7c2264e52c0d2d0eb33e17d9054f4220c8859efc9a2c5'
            '6595f7c74cbfa2fa80b3f48c2475ab423a9fd70d0738d45b02e2168a9374dea2'
            'cd3f2567c48707cc1ffb87b9c3c505df972c789489cf61681178ed201a415c4e'
            'b48c2a925a64bf76f178ce64256632ad5c28b39cf315d21dac61898ddd120fea'
            '44b300ffda0992607f892dd2ba8f9378bc2397d5b07a87e7db883cb484209fd2'
            '8fc6613f093e651bc23d53bd95a10446d0cd44fc856f0843dd67ecb56ada67fc'
            'e09b4d13bac8c5037df7aaf49fff3406f1679a785eebc1f712b72dbdbe72f681'
            'efc12cd1032b990b94384a28011d5de99fce39766fd486170ebd48b18e233385'
            '27fec0d6f5eee6c73912d6dda28680e5c11024fefef5cd5c7236cbbed1e55813'
            'e4ece0c16b41ab0f61ab1cd180b1262c54bbe2756f79646865611b2daab29998'
            '51fadcf645c67aa72ade1e882d1625161271ab10e4e2baa465f1f173117589a4'
            'e3bd7a97d5455c1f99d79ad85204bf11e957e21b023ccf264c98e52752bc475a'
            '34988cbf208ffc46bd881f24d70d75a4a1e13649e5193fc227db2d3e71858b8e')
b2sums=('1bb4591dd0adb2472f31adbaaa5eae03743edf6e7a970173afb1ea1c659677102832d69e6ce692deee9ee757b36cba3d63b116a5eee81a7e5226462c40ae5ca0'
        'SKIP'
        '7e6a8cbbb3e9c9d9544f87f490534e68f2a7a7714d857649bc4c6ec60c024e5488641fedee664f7eb8e1cb743c738834fdf665b2660477bf223ca8273c2f38a4'
        'SKIP'
        'bef3377ad86440af76e9dde4c29c9f4aaad42f5fe343f7d31f5eb537d6d358602f996f5d63986af275f2e92f94e71dc28c320edc8c03d05bd64dbd8ed23d75dc'
        'dfd366b283243f95c318471fe35e3a36646a38388dd6c4d9746bc981985a02ea303d75127244e9feac14564a8f49385483dfb56a8842814bdf97ca747bc2a4d5'
        'ee5fb2bd15a6199e42d8496181af49d9f4cbbbfb35b2bb155e50ea74157fcf2f92262d413aba53231c3134db4c2f494dd27e55fa00bcd20f08c885ad20b82182'
        'd85d099f3262afba525c79a1dc111b794c941abb6c8980f9767eb355088f4d96c5cbea5d23a51f63081ba04afc026bcdf9b24f98e688ed5120a7c8721c0ec241'
        'a46b9d930d5ddbf394e2cc15f26c555af8cb238da3bf51fee718eb2954fbb9a85eeb13a23ba1a7368c25991fc5b7f0dcc021a124ee19603135bb6c2dce6a21f4'
        '80795be94e9a06d8c2939633fa9b17eaadff2637f40470921f4885e9e330be0cebd0a714bf0c5eea7274b12d2b971ace0b83350314d857cea41141096b2ddcb2'
        '63224744461d620f7f6ce63dde41cd65ff48c9077e813a5e0ae9d8a2f97b7b1b6ececf7491e69ae2122441450eeb7acfd9fc187286e398b9745e1f07cb4ef565'
        '635afb979079a560630f7cace25444bc1dd57dda2bf94bef2aceccaeba348abb0c5624a2fe67df1ab8a6ee107512f230c7135d02c78b51ffda2f6749b27d0b43'
        'aee84ab016fcf7b858bffe0320e5c904c7765519a1f03da02d5d3eaad3cbe5faa5ff6a40bdc8c4608fd51e3f9c25349f2a7189c171aecefaab7301ad9e17ad2b'
        '63c8d9f3ad1185a87124ccc5d67c3ad2ead5ffcf11c66fa2c537b4e959be684e35c688ccc3e9ffc5f0e7655372371a8f9528383799956723ab2b497cf307c789'
        '83fa3bef1c166c4605cb7680d79d01bd51b44d7c08222360af761db16e3e0308278c649fe8d0742cdc7938fdc1cd234dbe8265263cdf361fb29b16fc41e0b16d'
        '22b15d24030a7fca87ebf12858f86b1a78542b5b39b0d61be8941cb4930d3df47b96ea28fc46d23049b913b686f29e14482864cc387c12139a0f14be7b577131'
        'abd0b88548e608b5867e7eed3690b9d07a14b461e440d737256c9e80c5006070dbe7f0c480b70265e7724a8c0301b41054e544921df98928314bdf143742257b'
        'c98ee338600ed9cc370a5437b51eab9ffae06aa5666bad68efd7ad8052448c1ac6dab0a95ebb081d91bd6d2bebfadf259a61968530d3bf636a1ff0e6ca551996'
        '934999c4b9fae3584e9b8add1b7a476c52b904d238173f5ef6fc1bee8f259502e12a093bd81bb5906934fbdbb6f7b29a21ea67b6e3d269cd9a7521f0d5be3e7c'
        '5e0526fb451721717fe96472df3a42dfcb9e250da86cb7f26d12211664608dcd0242f0312c2f9d93ecec31bbef472055c2767b56686c6dcc1b90cf67407a70b5'
        '906e5e79a89779131f473b481c15dd8d254aa1328b3b96e10e41e71ba28518f46a299673c4cb7420f5bd76d24596a959cc47fb06ce337416d00046f3fc60939b'
        'e5b55f18620528b5a185a935d1195901821472899825d2fee56572fb2362dce94732443c38ab50f03e460ad228108c6b3a6eb8b1e20da5a6b087e864fad7083d'
        'c8e74f6fab1b5fa8c55771bd846b527bd54c70de52684e2c6a1ec8bfacc7aac76f04d50cf8ed2f2891bf3867a631392b15183550b4a897c6e0fa246547cf4dd7'
        '2dc73df2d0e1d83da969f02417c23017964a84ed0bb46306af762c355eccabba743befdfe50caff11d5c8c3dc187d0829b7bf85eb5d681b5dfaa52a2b7fc8150'
        'a07f27dc6b9fcc8a0e3727ec82875da8ea22116b83a2573bc80e972a2f4a483526de51e8037c0cefb15005042392960a5d6db6ef8573f9e9cafd3cd6aac1b398'
        '7422c668218a81ddeb0a90fe3d57473f44bf2fd2b9f19f6b4000fc8d1579f8950fb65d05354bc05d6d0f7ba324e574a34135fceb4ad15dc2bc3afb7487867a73'
        'f0d2a40972fba9f550431c4c4d8e0015eb6f97e3bfc0ee63b4d6ab543098edfe6bacb437ea59038c49ca64108101e464e718fde80c871009dacf90f91801dcd8'
        '172c4ec43495c77bfa4ff3dff8938137e41401a703a98fe65ba192a6874241ef67082662f53a2f3b459dc0cdb433b6986390a577ac307390b9afaa24db4caad7'
        'c3ea26b1a5d7ad272f1f05ec5fa9caa3ca409ab227eb9149b3a93e02c164cf75316d16568d9bbde3b149840d847a5796fce8da3ec925f7d1b390606e0b51d850'
        '619e8ba4e4ac917381607ac13a7196063130e0644469478f0b1e45f0b47701a84cf35262e947a83007d64b585331af8cabdae83c19f8ef02296a89634b1a61d6'
        'f5409b85d28302a5b35ffb918c23f6efdf169047e3c71951a0c3a81d2bdd91a423fd3f444f74fa7a8503e39f58c99b15b6e54475265587cad0b53caacc15b011'
        '44a5362b9ca206fb1b1e86a8986020b5e5d64e5bc919b42eb9638392373aaa4387bc866dd130ea9dcdba91bb07c11b6ff3cf629dbce998b42e932556f97a0237'
        'aa9885a0f70488477cbcef5c3753ed116025913c15f0c767aa402ab51dc76d40d4b6fa90fa79bc8364f862296b4a7418873f4fc5bd9fbea3d1a081388e0598ef'
        '150aba69883e27386e5fc4a1dd7175daf4ebc38390d1fc6d0609ee45df108fe897e9f01fedf7e1878bf9cb4e84e0b308166919e384bd08394f60db8158d37fb0'
        '11c48089ed682933d1cec7f041e69aad6ecd7ccdfa9d6046a0faca8c551304b9bf6be7dd5d0e06745d7f5f88592ac0c67a00eb546c006de3dff6980a33df591d'
        'b158fb09d0551b48606ad4c626e0c1c9b4c5618f59fa5541d8ff668f6dafc7b6467206bc49199218774fa2f655f9fdfbcda7556430dca4f359448313813f915a'
        'f1a64ea842b182f5f2a783721c1fc2fc0826556e6b36a886949906dc6a4525c8f0baed803129389046dce2c0ed554fb69013d8f8756fbba01f0031d8aa4ee304'
        'e15cf515d32ae7dd7e611254e6399a19bcb14e77799600e07c0bd4f487364e64bdc0e59099d81031db5479f9dfbc0b1699b9bd825d989fd3290b2e07c8c22c68'
        'e9421255f4448268a3b23e031a2578ca519f6c754522ccbb3f145d23d03f07877cf19b70e9da76877cd624b4c264d78f921e970855c0e829ea4ffd5569d60761'
        'd7f77b9f514bda3a863d9e1b9f515f9684d7974b2c040fb212b374608f45d934a4ba8e1ab57c27289e1b235836c125d67f9c9d1cecf8d528275c877414e81ba1'
        '76e04afe4fef163c212ee40b9e337f8b1eab4e248f62ddb59e59f1970916e423f89df962c9766a208d285eb4b166cd9fee268ce5efbce1860ac4d5b3e106b517'
        '37e8d2647cfea6637be3eef6232d9690c234cd869ed50fce222e0cd6c08f28723826f9d0ddcaba6c4b2002399e16c08b54019a3ab661fd2ec1b6c60e22c23605'
        'b3b30254ba524e25e560d4755131df86ed2ad04e3d50e91323fc019cc9e691f7723c9a59e0b095689104774433ec2e6d6f50adf652f4ff717d890567dd3570fc'
        'd197957f49d59dea7f93200938c02c39ffabe0e96dc45e94f179ee1e86d5d3804b1e6fd76e948c2e55bfdfa80838b6a58be2dfa3d6ed3af9f870289f90f44e9e'
        '87ea9f265c58f77d04a096676c37c43280f6eec32ac2bb9982007529b01e1bd7a086508fee5c64c82a2890856faa417c300ee6121ffaca56e252da9e60ee911f'
        '6bbabea25bf71b336058d520ccc92d973984ac75f35d791017a17e75022b258082df06312ca94e16534db42b1071c1ed71f90ce6fb17cb238692cc9f983a98b4'
        '87ad925804aacd88cd01d9c97a4f4d91cc4a6661661b95ce3898142a270e200a3c75e13a706f4d2a058186a2d99c15511ab7d74f7ce1c189bfb84f828214472b'
        '6fdd1ab01c51c6f6898b853e7da5eacfdc24672f2a3bda6a225ab64c02211bc0833d974e74a6ed4393afa8cc084c4acd4b058dee7c14e9fda3bdb9560035f83f'
        '9a78d1126a656404c5cd9e2c416085f57853294c84356004c8ff7340aeb4eb3b3a2a6aaf6b475b8db60b2330d1e1599bf672d17cca09cd9933a958e5806a59e4'
        'fb4fe29e01b157bf77bef627a2b1fb188527d47a6051b5d7519274ceaf4677a67b344831a66418e8ba61aae240f16c6ac0a580e2b851344b1aca590b6060b292'
        '01ff65fc8ec0dc8b52660911f267575bbd45522749b27f5e58fda5441851ddf6617e4f13ff6630b5e9dbce50ee06c5a749161b4566a3a7c6c001ba492d8d8254'
        'df8a36ec4aaedddc5a41ebd534191e74afef520ee1b9e56b57468781b50a776ade49adc261913d7a77796cc5ba38549e59606ad857f6d697c9af850af3770917'
        'cb6d67cafa843aab0bc3558087175a87d2ef573ce69546eb158cf65db853c05a05ad1a3303473c876a53cdab12cb76bdde0a4e3e60da21de7664b87b94645339'
        'dcf3fc606dacf6f71fe2eb31b7a2a97fb52b8e5476ec28fd9a59b8173a9fbbcb685a3f98a02ce25e2d54041d8f7cdc6e9ad749522a0747f91298738c7f3a57e3'
        'bba7503c4165ffc82f11162fc50642098f21f7e0e90ba96e8e6f25fee42a64fc366a9b0fc442ceb430caa1a85a39865c5b6c656dc8d624a9a72f839b7f1534d3'
        'c4c686d54705d4a02763959f02093c723d83b2dcf72c9b4622d4e9c1fd654e5b6c6f1807d9adfe062eb12ded490adf60110920043fa74d4afb5ba35ae76606ee'
        '07332d4acc32df31a64777f25362b133b72f3d2684b8ef9e72f7cc4b995013f4353b60cac9560dfca3b9afbc1c37ada25c33e648937882cfe262742d8ea119cb'
        '2ed15de9c7feb70bd2f905e0cac0c38b30e5d30d25c2aba8444a2e1d0ad5574e31f74cc5f6541c3584994b4aa8dba3fee66dab9a8a997e0d5685a260d289656c'
        '7cda631f95f12d5db0c17f92488c1b06d426ce319a1f0ba7e33ed212489b8a6d5fece22cb77bd16c06474a07cecf7c5a557577dbc90a9825f7af1db789fa4ca0'
        'e9023914f9971f71c6a53d1ac723f235e3d28529a9198a81a91e0175fd28e59f18a8c45deeb60f1eb620e44382b58cff428463a26f34eef7f3e6eaef7b5bffc9'
        '4c41949798d5b234df877697bf51998d5fff58a28cca1f9235d72cef06956ab65c221e791aeaf437d1dedbe58b56b245809107f6b85fc3e19fbfab87bbde7866'
        '9fbf545025c3feee8c9168e0393f1418038dc252a42c5b0b878ddcc4f6c0b5ff98f7a819789f9a544b038f47f179f9574274f4305e748f527f3f8b428f1972e4'
        'c81f490d879d8831a4fe55a9a812129ea88012d9b6b4bc7f3a7d3da8089bcc97f77c97564e026df174e9bd3d9c2065b2aaf32d3780509f2db892f52de29ef6cc'
        'd7a4b31ac57839a683e5f796bed8d57e6e7d4f2da9a6b37f76dd317b0a1745f186319b031774f0ecb1e0223c8251e5ef4772d2a536767d80843bc5098c3c0234'
        'eb29caed5bd5102bc45bdb38619ecc17552debc02834786abddba55f40d50ab0eb13de189a0509b657f515cb32ffff0922c08ef6f293963e9c6b3d882b5e76d4'
        'c60eb15f9445dc2905a711d614d67ab2c0658cfb221c89ab4793f96bc1ff343005abb65fbbce27bdd90dfa20fbdb73047c4bece2bf0da48aaa38b152af619481'
        'df580abdf7c7ba947920f2fb2c999f3ed8469dbaad2ebc6706f8b110d580b14f0115d98a87d3891cddf2d30afc831eec6e1cc6b6efa7c313129c90ab90e49b8c'
        '29c93d58903126506adf31fef10a493234f284d1c5a88cb33f239c91ce225424f4118a3f2a9d34c4e12e1a24492f0ec46ece77d5c64b4456f44802d2fb2acc3c'
        'bba4a52df66cb5a9946c93ae9b8ed6e0739bb9756d7ee2465f78717b51a959134635c185745978db3a00e337cc8b67741f4063393f52eb5e0f3efd80826ef936'
        '2d67840e8c3969c7b0261e242e3218d56b393b8146b758071f73d1fe6fdf0b55737c41989c36a727cecd2f6f328b8687bd24032a481c183946a2d3b0be3c64b1'
        'af27c8d90bf129a40522a5332663da7185025b76143ba16878b5916823c5d80429fbfaea7c4e624fd64177636f56ebb6019f0f628306c0726e9fff84ad7ab6df')

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
