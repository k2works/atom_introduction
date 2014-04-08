Atom入門
=================

# 目的
GitHub製エディタAtomの操作方法を修得するため公式サイトのドキュメントページを超訳する  
+ [はじめに](https://atom.io/docs/v0.84.0/getting-started)  
+ [カスタマイズ](https://atom.io/docs/v0.84.0/customizing-atom)  
+ [パッケージの作成](https://atom.io/docs/v0.84.0/creating-a-package)  
+ [テーマ作成](https://atom.io/docs/v0.84.0/creating-a-theme)  
+ [パッケージの公開](https://atom.io/docs/v0.84.0/publishing-a-package)  

# 前提
| ソフトウェア     | バージョン    | 備考         |
|:---------------|:-------------|:------------|
| OS X           |10.8.5        |             |
| Atom           |0.84.0        |             |

# 構成
+ [はじめに](#1)
+ [カスタマイズ](#2)
+ [パッケージ作成](#3)
+ [テーマ作成](#4)
+ [パッケージ公開](#5)

# 詳細
## <a name="1">はじめに</a>
このガイドはできるだけ早く使えるようにするための入門です。  
また、このガイドはAtomの設定・テーマそして拡張をカバーしてます。

### コマンドパレット
Atomで一つだけコマンドを覚えるなら```cmd-shift-P```です。  
```cmd-shift-P``` を押したら現在開いている画面に関連した内容が列挙されます。  
このコマンドは仕組みやキーバインディングを学ぶには一番いい方法です。  
もっと詳しいことは[キーバインディングのカスタマイズ](https://atom.io/docs/v0.84.0/customizing-atom)を参照してください。  

### 基本操作

#### ファイル操作
Atomのウインドウはひとつのディレクトリが対象になります。もし、コマンドラインから```atom```のコマンドを実行するならパスは指定する必要はありません。
Atomは今いる作業ディレクトリにウインドウを開きます。作業ディレクトリはサイドメニューのツリービューのルートとして表示されます。

##### ファイルを見つける
一番早い方法はfuzzy finderを使うこと。  
```cmd-t``` を押してファイル名を入力したらファイル検索ができます。  
```cmd-b``` で今開いているファイルの検索ができます。  
Gitを使っているなら```cmd-shift-b```で編集中・レポジトリ未登録のファイルを検索できます。

##### ファイルの追加・移動・削除
ツリービューの右クリックメニューからファイルの追加・移動・削除などコンテキストメニューを選択できます。  
キーボードから```a```で追加```m```で移動```delete```で削除もできます。

#### 検索

##### 検索と置換
```cmd-f``` でバッファ内の検索ができます。現在開いているプロジェクト内の検索は```cmd-shift-f``` です。

##### タグジャンプ
定義メソッドなどのシンボルに移動するには```cmd-r```を押します。  
この操作で現在開いているファイルのシンボル一覧が表示され```cmd-t```と同様のfuzzy filterで操作できます。  
プロジェクトを横断的に検索するに場合は```cmd-shift-r```を押します。  
ただし事前にプロジェクト用の```tags```(もしく```TAGS```)ファイルを作成しておく必要があります。  
これは[catgs](http://ctags.sourceforge.net/)をインストールして該当プロジェクトのルートディレクトリでコマンドラインから例えば```ctags -R src/```と実行すれば作成されます。  
ホームディレクトリ(```~/.ctags```)に```.ctags```ファイルを作成することでカスタマイズすることができます。  
カスタマイズサンプルは[こちら](https://github.com/atom/symbols-view/blob/master/lib/.ctags)

#### パネル分割
```cmd-k right```もしくは```cmd-k down``` で水平または垂直に画面を分割することができます。
画面を分割したら```cmd-k cmd-right```または```cmd-k cmd-down``` で画面を移動することができます。
```cmd-w``` で開いた画面を閉じることができます。
```cmd-k cmd-n``` 分割した画面をトグルできます。

#### 折りたたみ
画面左側の矢印をクリックすることでブロックを折りたたむことができます。  
キーボード操作での折りたたみ・展開は```alt-cmd-[```と```alt-cmd-]``` です。  
全部折りたたむ場合は```alt-cmd-shift-{```全部展開する場合は```alt-cmd-shift-}``` です。  
また、```cmd-k cmd-N``` で特定のインデントレベルで折りたたむこともできます（Nはインデントのレベル）。

#### ソフトラップ
```cmd-shif-P``` でパレットを開き"wrap"と入力してToggle Soft Wrapを選択すると行を折り返し表示に切り替えることができます。  
デフォルトでは行はエディタの設定サイズで折り返されます。変更したい場合は設定画面の"Wrap at preferred line length"を編集してください。

### 設定
```cmd-,``` で設定画面を呼び出すことができます。この画面で設定を変えたり、パッケージをインストールしたりテーマを変えたります。  
設定の詳細は[こちら](https://atom.io/docs/v0.84.0/customizing-atom)

## <a name="2">カスタマイズ</a>
### テーマを変える
設定を変更する、テーマを調整するまたはパッケージをインストールするには```cmd-,```押して設定画面を開くだけです。

Atomはいくつかのシンタックステーマ同様に明るいのと暗いUIテーマが存在します。自分自身のテーマを作成することもできます。

テーマを変更するには設定画名を開いて(```cmd-,```) 画面左側のテーマセクションを選択します。シンタックスとUIテーマを変更するドロップダウンメニューが表示されているはずです。

また、機能テーマを探したり特定のテーマを検索してインストールすることもできます。

### パッケージをインストールする
設定画面(```cmd-,```)左側の```Packages``` セクションからバンドルされていないパッケージをインストールすることができます。いろいろな機能のパッケージを見れるでしょう、またここからパッケージの検索ができます。ここに表示されているパッケージは公式パッケージ登録サイトである[atom.io](https://atom.io/packages)で公開されています。

また、コマンドラインから```apm``` を使ってパケージをインストールすることができます。  
以下のコマンドをターミナルで実行して```apm```がインストールされているか確認して下さい。

```
apm help install
```

```apm``` インストールコマンド詳細メッセージが表示されているはずです。  
もし表示されないなら、_Atom > Install Shell Commands_ メーニューから```apm```と```atom```コマンドをインストールしてください。

```apm install``` コマンドでパッケージをインストールできます：  
```apm install <package_name>``` で最新バージョンをインストール  
```apm install <package_name>@<package_version>``` で特定のバージョンをインストール  
例えば```apm install emmet@0.1.5``` で0.1.5リリースの[Emmet](https://github.com/atom/emmet)パッケージを```~/.atom/packages.``` にインストールします。

```apm``` を使って新しいパッケージを検索してインストールすることもできます:  
```apm search coffee``` CoffeeScriptパッケージを探します。  
```apm view emmet``` 特定のパッケージに関する詳細情報が表示されます。

### キーバインドのカスマイズ
Atomのキーマップはスタイルシートに似ています。スタイルシート同様、スタイルの要素にはセレクターを使います。Atomのキーマップは特定のコンテキストイベントに関連付けられたキーストロークのセレクターを使います。これはAtomのビルトインキーマップから抜粋したサンプルです。
```
'.editor':
  'enter': 'editor:newline'

'.mini.editor input':
  'enter': 'core:confirm'
```
キーマップは２つの異なるコンテキストの意味を```enter```に定義します。通常のエディタでは```enter```を押すことは新しい行に改行するイベントを```editor:newline```に発生させます。しかし、もし同じキー操作がmini-editorセレクタで定義されていたならばかわりに特定のセレクタに関連付けられた```core:confirm```イベントを発生させます。

デフォルトでは,```~/.atom/keymap.cson```がAtom起動時に読み込まれます。常に最後に読み込まれる、Atomの主要キーマップまたはサードパーティ製パッケージに関連付けられたキーバインドを上書きできます。

_Atom > Open Your Keymap_メニューから開くことができます。

実行可能なコマンドの全てを知ることができます。設定画面(```cmd-,```)を開いて_Keybindings_タブを選択してください。現在使えるキーバインディングを確認することができます。

### さらに進んだカスマイズ
Atomは_~/.atom_ディレクトリにある[CoffeeScript-style JSON (CSON)](https://github.com/atom/season)で構成された```config.cson```ファイルから環境設定を読み込みます:

```json
'core':
  'excludeVcsIgnoredPaths': true
'editor':
  'fontSize': 18
```

設定は```core```と```editor```という一組のネームスペースまたはパッケージでグルーピングされています。  
設定メニューの_Atom > Open Your Config_からこのファイルを開くことができます。
#### 主要項目の設定
+ ```core```
  + ```disabledPackages```: 利用不可能なパッケージ名配列
  + ```excludeVcsIgnoredPaths```: .gitignoreで指定されたファイルは検索しない
  + ```ignoredNames```: Atom全般で無視するファイル名
  + ```projectHome```: プロジェクトが配置されていると想定されているディレクトリ
  + ```themes```: 読み込まれるテーマ名配列、カスケード配置
+ ```editor```
  + ```autoIndent```: オートインデントの有効・無効基本設定(デフォルト有効)
  + ```nonWordCharacters```: 文字区切り用非文字
  + ```fontSize```: フォントサイズ
  + ```fontFamily```: フォント
  + ```invisibles```: 非表示文字コードを定義した連想配列
    + ```tab```: タブ文字
    + ```cr```: キャリッジリターン(Microsoft-style line endings)
    + ```eol```: ```\n``` 文字
    + ```space```: スペースを表現する文字
  + ```normalizeIndentOnPaste```: タブスペース変換の有効・無効
  + ```preferredLineLength```: 一行の文字数(デフォルト ```80```)
  + ```showInvisibles```: 非表示文字を表示するかどうか
  + ```showIndentGuide```: インデントガイドの表示・非表示
  + ```showLineNumbers```: 行番号の表示・非表示
  + ```softWrap```: 行折り返しの有効・無効
  + ```softWrapAtPreferredLineLength```: 指定した文字数で業折り返しの有効・無効
  + ```tabLength```: タブ内おスペース数(デフォルト ```2```)
+ ```fuzzyFinder```
  + ```ignoredNames```: fuzzy-finderで無視するファイル名
+ ```whitespace```
  + ```ensureSingleTrailingNewline```: ファイル末尾の複数改行を無くすかどうか
  + ```removeTrailingWhitespace```: 行末の空白を無くす有効・無効
+ ```wrap-guide```
  + ```columns```: キーが現在のエディタのカラム位置に対応付けられた```pattern``` と ```column``` の連想配列。

#### お手軽パーソナルハック
##### init.coffee
Atomの読み込みが完了した時、_~/.atom_ディレクトリの_init.coffee_ が評価されます。これはあなたが自由にカスタマイズできる[CoffeeScript](http://coffeescript.org/)コードです。ファイル内のコードからAtomのAPIに完全アクセスできます。もしカスタマイズが広範囲になったら[パッケージ作成](https://atom.io/docs/v0.84.0/creating-a-package)も検討してみてください。

_Atom > Open Your Init Script_メニューからこのファイルを開くことができます。

例えば、あなたが音の設定を有効にしたいなら_~/.atom/init.coffee_ファイルに以下のコードを追加してAtom起動時に音がなるようにしてください:
```javascript
atom.beep()
```
このファイルはまたJavaScriptコードで記述された_init.js_でも有効です。

##### styles.less
もしあなたが公開するつもりのないやっつけ仕事のスタイル変更をしたいなら,_~/.atom_のディレクトリに_styles.less_ファイルを追加してください。
このファイルは_Atom > Open Your Stylesheet_メニューから開くことができます。

例えば、あなたがカーソルの色を変えたいなら以下のルールを_~/.atom/styles.less_に適用すること実現できます。

```css
.editor .cursor {
  border-color: pink;
}
```

LESSって何？そんな人は[ココ](http://lesscss.org/)

また、このファイルはCSSで記述された_styles.css_でも有効です。

## <a name="3">パッケージ作成</a>
## <a name="4">テーマ作成</a>
## <a name="5">パッケージ公開</a>

# 参照
[Atom](https://atom.io/)  
[Documentation](https://atom.io/docs/latest/)  
[GitHub Flavored Markdown](https://help.github.com/articles/github-flavored-markdown)
