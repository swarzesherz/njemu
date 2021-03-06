----------------------------------------------------------------------------------------

※ソースコードのコンパイルについて

作成環境は Cygwin + PSPSDK (revision 2326) です。
おそらくそれ以前の環境でもコンパイルは可能だと思われますが、出来る限り
最新の環境を使っていただくのが望ましいと思います。

※このソースファイルのアーカイブを解凍して出来たフォルダ構造は変更しないで
  ください。変更するとMakefileの修正が必要になります。

コンパイルの際は、Makefileの先頭にあるConfigurationの項目を編集することで
コンパイルの対象を設定します。各項目の先頭に#をつけてコメントアウトする
ことで無効に、#を削除することで有効になります。以下詳細です。


・コンパイルの設定

BUILD_CPS1PSP = 1      CPS1PSPのコンパイルを行います。

BUILD_CPS2PSP = 1      CPS2PSPのコンパイルを行います。

BUILD_MVSPSP = 1       MVSPSPのコンパイルを行います。

BUILD_NCDZPSP = 1      NCDZPSPのコンパイルを行います。

PSP_SLIM = 1           PSP-2000 + CFW3.71 M33以降用のユーザーモードで実行
                       するバイナリをコンパイルします。

KERNEL_MODE = 1        FW1.5のカーネルモードで実行するバイナリを作成します。

ADHOC = 1              AdHoc通信対戦機能を組み込みます。(NCDZPSPでは無効です)

SAVE_STATE = 1         ステートセーブ/ロード機能を組み込みます。

COMMAND_LIST = 1       コマンドリスト機能を組み込みます。

UI_32BPP = 1           ユーザインタフェースの描画を32bitカラーで行います。
                       壁紙も使用可能になりますが、NCDZPSP以外ではメモリの
                       消費を抑えるためにもこのフラグは無効にしておくほうが
                       良いです。

RELEASE = 1            有効にするとREREASE = 1を、無効にするとRELEASE = 0を
                       コンパイルの定数として設定します。
                       ソース中で #if RELEASE 〜 #endif のように使用します。
                       現状は無効にするとbootleg版のゲームが起動できるように
                       なります。

・バージョンの設定

VERSION_MAJOR = 2      メジャーバージョンは大規模な更新を行った場合に変更を行います。

VERSION_MINOR = 2      マイナーバージョンは小規模な更新を行った場合に変更を行います。
                       また、偶数の場合は安定版、奇数の場合は開発版となります。
                       したがって、ver.1.0の次はver.1.2がリリースバージョンになります。

VERSION_BUILD = 0      ビルド番号は細かいバグ修正を行った場合に変更を行います。

----------------------------------------------------------------------------------------

※SystemButtons.prxについて

  カーネルモードで動作するシステムボタン読み取り専用のスレッドを実行するPRXです。
  コンパイル方法は、systembutton_prxフォルダに移動してmakeです。

  なお、コンパイル終了時にnjemuのsrc/pspに一部ファイルを、一つ上の階層にprxをコピー
  します。

----------------------------------------------------------------------------------------
