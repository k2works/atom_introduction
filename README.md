Atom入門
=================

# 目的
GitHub製エディタAtomの操作方法を修得するため公式サイトの[ドキュメントページ](https://atom.io/docs/latest/)を超訳する  
+ Guides
  + [Getting Started](https://atom.io/docs/v0.84.0/getting-started)  
  + [Customizing Atom](https://atom.io/docs/v0.84.0/customizing-atom)  
  + [Creating a Package](https://atom.io/docs/v0.84.0/creating-a-package)  
  + [Creating a Theme](https://atom.io/docs/v0.84.0/creating-a-theme)  
  + [Publishing a Package](https://atom.io/docs/v0.84.0/publishing-a-package)  
  + [Contributing](https://atom.io/docs/v0.84.0/contributing)

# 前提
| ソフトウェア     | バージョン    | 備考         |
|:---------------|:-------------|:------------|
| OS X           |10.8.5        |             |
| Atom           |0.84.0        |             |

# 構成
+ ガイド
  + [はじめに](#1)
  + [カスタマイズ](#2)
  + [パッケージ作成](#3)
  + [テーマ作成](#4)
  + [パッケージ公開](#5)
  + [貢献](#6)

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
パッケージはAtomのコアです。ほとんどすべての主要機能がパッケージによってコントロールされています。"core"部品としては[file tree](https://github.com/atom/tree-view), [status bar](https://github.com/atom/status-bar), [syntax highlighting](https://github.com/atom/language-coffee-script),などが含まれています。

パッケージはAtomの挙動を変えるいろいろな種類のリソースが含まれています。基本パケージのレイアウトは以下:
```
my-package/
  grammars/
  keymaps/
  lib/
  menus/
  spec/
  snippets/
  stylesheets/
  index.coffee
  package.json
```  
パッケージにはこれらディレクトリすべてが必要というわけではありません。

チュートリアルは[こちら](https://atom.io/docs/v0.84.0/your-first-package)です。

また、TexMateのコンバートガイド([TextMate bundles](https://atom.io/docs/v0.84.0/converting-a-text-mate-bundle),[TextMate themes](https://atom.io/docs/v0.84.0/converting-a-text-mate-theme))もあります。

### package.json

[npm packages](http://en.wikipedia.org/wiki/Npm_(software))同様、Atomパッケージは最上位ディレクトリに_package.json_ファイルが含まれています。このファイルにはリソース読み込みに必要な"main"モジュールパス,依存ライブラリそして特定のマニフェストなどパッケージ関するメタ情報が含まれています。

加えて標準の[npm package.json keys](https://www.npmjs.org/doc/json.html)が使えます。Atomのpackage.jsonファイルは追加項目を持っています。

+ ```main``` (必須): パッケージの起点となるCoffeeScriptファイルのパス
+ ```stylesheets``` (オプショナル): パッケージで読み込む必要のあるスタイルシートの順番を特定するための文字列。指定されていない場合は_stylesheets_ディレクトリにアルファベット順にスタイルシートを追加します。
+ ```keymaps``` (オプショナル): パッケージで読み込む必要のあるキーマップを特定するための文字列。指定されていない場合は_keymaps_ディレクトリにアルファベット順にマッピングを追加します。
+ ```menus``` (オプショナル): パッケージで読み込む必要のあるメニューを特定するための文字列。指定されていない場合は_menus_ディレクトリにアルファベット順にマッピングを追加します。
+ ```snippets``` (オプショナル): パッケージで読み込む必要のあるスニペットを特定するための文字列。指定されていない場合は_nippets_ディレクトリにアルファベット順にスニペットを追加します。
+ ```activationEvents``` (オプショナル): パッケージ有効化時にトリガーされるイベントを特定するための文字列。トリガーされるイベントに達するまでパッケージの読み込みを遅らせることができます。

### ソースコード

もしAtomの挙動を_index.conffee_からエクスポート（または_package.json_ファイルの```main```キーで指定されているファイル）できるよう拡張したいならパッケージを単一の上位レベルモジュールに含めなければならない。

あなたの上位レベルモジュールパッケージはAtomの拡張ライフサイクルを管理するシングルトンオブジェクトです。たとえあなたのパッケージが１０種類の異なるビューそして異なるDOMパーツの追加を作成したとしてもそれらはすべて上位オブジェクトから管理されます。

あなたの上位レベルモジュールパッケージは以下のように実装してください:

+ ```activate(state)```: パッケージが有効になった時呼び出されることを要求するメソッド。もし```serialize()```メソッドを実行するモジュールならウインドウが最後にシリアライズされた状態のデータをパスします。

+ ```serialize()```: ウインドウが閉じられた時に呼び出されるオプショナルメソッド。コンポーネントの状態をJSONにして返します。あとでウインドウを開いた時返されるデータは以前のビューの状態を再現するためモジュールの```activate```メソッドが実行されたものです。

+ deactivate(): ウインドウを閉じた時に呼び出されるオプショナルメソッド。もしパッケージがファイルや外部リソースを別の方法で保持しているのを監視しているならばそれらはここで開放します。単にウインドウになにか記述しているだけならそれはいずれ開放されるので心配する必要はありません。

### 簡単なパッケージコード

ディレクトリは以下のようになっています:
```
my-package/
  package.json
  index.coffee
  lib/
    my-package.coffee
```
```index.coffee``` は:
```coffeescript
module.exports = require "./lib/my-package"
```
```my-package/my-package.coffee``` は以下のように始める:
```coffeescript
module.exports =
  activate: (state) -> # ...
  deactivate: -> # ...
  serialize: -> # ...
```
シンプルな規約を通じてあなたのパッケージはAtomのAPIにアクセスします。初期開発の段階なのでAPIが変わったりpublicとprivateの境界をはっきりとしていないことを念頭においていください。また、欲しいAPIがなければ我々と共同で作りましょう。あなたのようなパッケージ作成者のニーズを基板にしたAtomのAPIを作ることが我々のゴールです。

### スタイルシート

あなたのパッケージ用のスタイルシートは_stylesheets_ディレクトリに配置してください。ディレクトリに配置されたスタイルシートはパッケージが有効化された時点で読み込まれDOMにアタッチされます。スタイルシートはCSSまたは[LESS](http://lesscss.org/)で記述できます。

理想的にはあなたはスタイリングの方法を知る必要はない。我々はAtomとシームレスにフィットするパッケージ用の色とUI要素を定義した標準コンポーネントセットを提供しています。コマンドパレット(```cmd-shift-P```)を開いて_styleguide_を検索するまたは```cmd-ctrl-shift-G```を押してスタイルガイドを開けば全てのAtomUIコンポーネントを見ることができます。

特定のスタイリングが必要なら、スタイルシートパッケージ内の構造スタイルのみで続けてください。もし、色とサイズを詳細化しなければならないなら既に有効なテーマである[ui-variables.less](https://github.com/atom/atom-dark-ui/blob/master/stylesheets/ui-variables.less)を使ってください。詳細は[theme variables docs](https://atom.io/docs/v0.84.0/theme-variables)を見てください。もしこのガイドラインに従ったならあなたのパッケージはすぐに使える良いテーマとなるでしょう。

_package.json_ファイル内のオプショナル```stylesheets```文字列は読み込み時スタイルシートを名前順に並べる順番を特定します、それがなければアルファベット順にスタイルシートを読み込みます。

### キーマップ

個別拡張を使ってキーバインディングを共通化することを推奨します、特に既に新しいコマンドを追加しているなら:
```cson
'.tree-view-scroller':
  'ctrl-V': 'changer:magic'
```
キーマップは_keymaps_サブディレクトリに配置されています。デフォルトではキーマップは全てアルファベット順に読み込まれます。_package.json_ファイル内のオプショナル```keymas```文字列は読み込むキーマップと順番を特定することができます。

キーバインディングはどのキー要素が押されたを特定することで実行されます。上記の例では```changer:magic```コマンドは```.tree-view-scroller```要素上で```ctrl-V```を押した時に実行されます。

キーマップがどのように動くかの詳細は[main keymaps documentation](https://atom.io/docs/v0.84.0/advanced/keymaps)を参照してください。

### メニュー

メニューは_menus_サブディレクトリに配置されています。デフォルトでは全てのメニューはアルファベット順に読み込まれます。_package.json_ファイル内のオプショナル```menus```文字列は読み込むメニューと順番を特定することができます。

#### アプリケーションメニュー

パッケージで共通動作を特定の要素に固定化されないようなアプリケーションメニューを作ることを推奨します。
```json
'menu': [
  {
    'label': 'Packages'
    'submenu': [
      {
        'label': 'My Package'
        'submenu': [
          {
            'label': 'Toggle'
            'command': 'my-package:toggle'
          }
        ]
      }
    ]
  }
]
```
あなただけのアプリケーションメニューを追加するには単純に_menus_内の設定ファイルの一番上に```menu```キーを追加するだけです。これはJSONまた[CSON](https://github.com/atom/season)ファイルが使えます。

あなたが設定したテンプレートはその他のパッケージと読み込まれた順番にマージされます。

#### コンテクストメニュー

ツリービューにファイルを追加例のようにインターフェースの特定部分にリンクするコマンドをコンテクストメニューで明確化することを推奨する。
```JSON
'context-menu':
  '.tree-view':
    'Add file': 'tree-view:add-file'
  '.workspace':
    'Inspect Element': 'core:inspect'
```
あなただけのアプリケーションメニューを追加するには単純に_menus_内の設定ファイルの一番上に```context-menu```キーを追加するだけです。これはJSONまた[CSON](https://github.com/atom/season)ファイルが使えます。

コンテクストメニューは選択された要素とセレクターにマッチした要素のメニューアイテム全てを判定して作成します（読み込まれた順番に）。このプロセスはDOMツリーの先頭要素に達するまで繰り返されます。

上記の例では```Add file```アイテムはフォーカスされたアイテムまたは```tree-view```クラスが適用された親アイテムにのみ適用されます。

### スニペット

_snippets_ディレクトリには繰り返し入力するテキストを早く入力するための言語スニペットを配置することができます。
```
".source.coffee .specs":
  "Expect":
    prefix: "ex"
    body: "expect($1).to$2"
  "Describe":
    prefix: "de"
    body: """
      describe "${1:description}", ->
        ${2:body}
    """
```
スニペットファイルには最上位(```.source.coffee .spec```)にスコープセレクタを含んでいます。それぞれのスコープセレクタはそれぞれの名前(```Expect``` ,```Describe```)をキーとしたハッシュを含んでいます。それぞれのスニペットは```prefix```と```body```キーで特定される。```prefix```は```tab```キーを押してオートコンプリートする前に表示される最初の文字を表しています。```body```は自動入力されるテキストです。```$1```,```$2```,のようなプレースホルダを使って自動入力されたテキスト内で```tab```を押して移動するようにできます。

ディレクトリ内のすべてのファイルは_package.json_がスニペットキーを提供していない限り自動的に読み込まれます。スコープアイテム同様、同じ項目のスコープにマッチする２つのスニペットがある場合は後に読み込んだスニペットが上書きします。

### 文法

If you're developing a new language grammar, you'll want to place your file in the grammars directory. Each grammar is a pairing of two keys, match and captures. match is a regular expression identifying the pattern to highlight, while captures is an object representing what to do with each matching group.

For example:
```
{
  'match': '(?:^|\\s)(__[^_]+__)'
  'captures':
    '1': 'name': 'markup.bold.gfm'
}
```
This indicates that the first matching capture ((__[^_]+__)) should have the markup.bold.gfm token applied to it.

To capture a single group, simply use the name key instead:
```
{
  'match': '^#{1,6}\\s+.+$'
  'name': 'markup.heading.gfm'
}
```
This indicates that Markdown header lines (#, ##, ###) should be applied with the markup.heading.gfm token.

More information about the significance of these tokens can be found in section 12.4 of the TextMate Manual.

Your grammar should also include a filetypes array, which is a list of file extensions your grammar supports:
```
'fileTypes': [
  'markdown'
  'md'
  'mkd'
  'mkdown'
  'ron'
]
```
### 外部リソース

It's common to ship external resources like images and fonts in the package, to make it easy to reference the resources in HTML or CSS, you can use the atom protocol URLs to load resources in the package.

The URLs should be in the format of atom://package-name/relative-path-to-package-of-resource, for example, the atom://image-view/images/transparent-background.gif would be equivalent to ~/.atom/packages/image-view/images/transparent-background.gif.

You can also use the atom protocol URLs in themes.

### テスト作成

Your package should have tests, and if they're placed in the spec directory, they can be run by Atom.

Under the hood, Jasmine executes your tests, so you can assume that any DSL available there is also available to your package.

### テスト実行

Once you've got your test suite written, you can run it by pressing cmd-alt-ctrl-p or via the Developer > Run Package Specs menu.

You can also use the apm test command to run them from the command line. It prints the test output and results to the console and returns the proper status code depending on whether the tests passed or failed.

### 公開

Atom bundles a command line utility called apm which can be used to publish Atom packages to the public registry.

Once your package is written and ready for distribution you can run the following to publish your package:
```
cd my-package
apm publish minor
```
This will update your package.json to have a new minor version, commit the change, create a new Git tag, and then upload the package to the registry.

Run apm help publish to see all the available options and apm help to see all the other available commands.
## <a name="4">テーマ作成</a>

## <a name="5">パッケージ公開</a>

## <a name="6">貢献</a>

# 参照
[Atom](https://atom.io/)  
[Documentation](https://atom.io/docs/latest/)  
[GitHub Flavored Markdown](https://help.github.com/articles/github-flavored-markdown)
