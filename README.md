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

もし、新しい言語の文法を開発しているならファイルを_grammars_ディレクトリに配置したいと思うでしょう。それぞれの文法は```match```と```captures```の２つのキーで構成されています。```match```は強調したいパターンを認識するための正規表現です。一方、```captures```はそれぞれのマッチングするグループで何をするかを表すオブジェクトです。

例:
```
{
  'match': '(?:^|\\s)(__[^_]+__)'
  'captures':
    '1': 'name': 'markup.bold.gfm'
}
```
これは```((__[^_]+__))```にマッチしたものはそれに適用されるトークン```markup.bold.gfm```を持っていることを意味します。

シングルグループを取得するにはシンプルに```name```キーを代用するだけ:
```
{
  'match': '^#{1,6}\\s+.+$'
  'name': 'markup.heading.gfm'
}
```
これはマークダウンのヘッダー行(```#```,```##```,```###```)が```markup.heading.gfm```トークンで適用されることを指しています。

これらトークンの意味に関しては[section 12.4 of the TextMate Manual](http://manual.macromates.com/en/language_grammars.html)にさらなる情報があります。

また、あなたの文法は拡張サポートファイル一覧を表す```filetypes```文字列を含めることができる。
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

パッケージ内のイメージやフォントといった外部リソースを出すのもの共通です。HTMLやCSS内のリソースを参照するのを簡単にするのにパッケージ内の```atom```プロトコルURLsを使うことができます。

URLsのフォーマットは```atom://package-name/relative-path-to-package-of-resource```, 例えば, ```atom://image-view/images/transparent-background.gif```は ```~/.atom/packages/image-view/images/transparent-background.gif```と等価です。

またテーマの中でも```atom```プロトコルは使えます。

### テスト作成

パッケージにはテストがなければならない、そしてそれらは_spec_ディレクトリに配置されている。テストはAtomで実行できる。

実際には[Jasmin](http://jasmine.github.io/)がテストを実行します。なのでパッケージ内で有効なDSLを扱うとができる。

### テスト実行

テストスイートを書いたら、```cmd-alt-ctrl-p```を押す,
または_Developer > Run Package Specs_メニューからテストを実行させることができます。

またコマンドラインから```apm test```コマンドを実行してテストをすることもできます。テスト出力と結果がコンソールに出力されテストが成功したか失敗したかの詳細コードを返します。

### 公開

AtomにはapmというAtomパッケージを公開するために使うコマンドラインユーティリティがバンドルされています。

パッケージを作成して配布する準備ができたら以下の操作でパッケージを公開できます。
```
cd my-package
apm publish minor
```
これは```package.json```を新しいマイナー```version```にアップデートします。変更をコミットして新しい[Git tag](http://git-scm.com/book/en/Git-Basics-Tagging)をつけてパッケージをアップロード登録してください。

```amp help publish```を実行すれば有効なオプションを確認できます。そして、```apm help```でその他の有効なコマンドを確認できます。

## <a name="4">テーマ作成</a>

AtomのインターフェースはHTMLで描画され[LESS](http://lesscss.org)を経由して整形されます。LESSを知らなくてくても心配しないでください、CSSみたいなものです、しかしいくつかの拡張があります。

Atomは２種類のテーマをサポートしています:UIとシンタックスです。UIテーマはツリービュー、タブ、ドロップダウンリストそしてステータスバーなどの要素を整形します。シンタックステーマはエディタ内のコードを整形します。

_Atom > Preference..._メニューを選択制して表示される画面左側の_Themes_セクションの設定画面からテーマのインストールと変更ができます。

### はじめに

テーマはとてもわかり易いのですが始める前にいくつかのことに親しんでおけば助けになります:

+ LESSはCSSをサポートします、それ以外に変数など便利な機能があります。もしシンタックスに親しみたいなら[ここ](https://speakerdeck.com/danmatthews/less-css)でしばし時間を使ってください。
+ 同様に_[package.json](https://atom.io/docs/v0.85.0/creating-a-package)_のコンセプトも復習したいでしょう。このファイルはあなたのテーマをAtomユーザーに配布することを手助けするために使われます。
+ あなたのテーマである_package.json_にはAtomにテーマとして認識させて読み込むための```"theme"```キーと```"ui"```または```"syntax"```バリューを含めなければならない。
+ 存在するテーマをインストールとしたり[atom.io](https://atom.io)からフォークできます。

### シンタックステーマ作成

Let's create your first theme.
あなたの最初のテーマを作ってみましょう。

始めるにあたって、```cmd-shift-P```を押して新しいテーマパッケージを作るために"Generate Sytax Theme"と入力してください。"Generate Syntax Theme"と選択するとテーマを作成する場所になるパスを質問されます。我々の_motif-syntax_を呼び出してみましょう。**Tip:**シンタックステーマは_-syntax_で終わります。

Atomは作成用のフォルダとファイルのデフォルトセットを新しいウインドウを表示します、_motif-syntax_テーマが表示されているでしょう。もし設定ビューを開いて(```cmd-,```)左側のテーマセクションを選択したなら_Syntax　Theme_ドロップダウンリストの中に_Motif_テーマを見つけることができるでしょう。それを選択して有効化してください、そうすればエディタを開いた時に新しい_motif-syntax_が確認できます。

_stylesheets/colors.less_を開いて既に定義されている色項目を編集してください。例えば```@red```を```#f4c2c1```に変更する。

_stylesheets/base.less_を開いて既に定義されているセレクター項目を編集してください。これらセレクタはコメント、文字列そして画面左の行番号など複数のコードで整形されます。

例として、```.gutter``` ```background-color```を```@red```に変えてみましょう

Atomウインドウ内で変更が反映されたか確認するため```cmd-alt-ctrl-l```を押してAtomをリロードしてしください。すごくいいね！

**Tip:**開発モードでatomウインドウを開いて変更を確認するリロード操作を回避することができます。開発モードでAtomウインドウを開いてターミナルから```atom --dev .```を```cmd-shift-o```を使って実行してくださいまたは開発モードメニューの_View > Developer > Open in Dev Mode_を使って。あたなテーマを編集した時に変更がすぐに反映されます！

### インターフェーステーマ作成

インターフェーステーマは[core themes](https://atom.io/docs/v0.85.0/theme-variables)で提供される変数をすべて含んできいる```ui-variables.less```ファイルで提供しなければならい。

インターフェースUIテーマを作るには以下の手順:

1. Fork one of the following repositories:
1. 以下のレポジトリをフォークする:  
  + [atom-dark-ui](https://github.com/atom/atom-dark-ui)
  + [atom-light-ui](https://github.com/atom/atom-light-ui)
1. ローカルにフォークしたレポジトリをクローンする
1. フォークしたテーマのディレクトリをターミナルで開く
1. ターミナルから```atom --dev .```を実行して開発モードで新しいテーマを開くまたは_View > Developer > Open in Dev Mode_メニューを使う。
1. テーマ内の```package.json```ファイルのテーマ名を変える
1. Name your theme end with a -ui. i.e. super-white-ui
1. 最後を```-ui```にして名前をつける。すなわち```super-white-ui```
1. ```apm link```を実行して```~/.atom/packages```へレポジトリのシンボルリンクをはる
1. ```cmd-alt-ctrl-L```を使ってAtomをリロードする
1. 設定ビューの_Themes section_内の_UI Theme_ドロップダウンリストからテーマを有効化する
1. 完了！開発モードでテーマを開いているなら、変更はリロードしなくてもすぐに反映される

### 開発フロー

テーマ開発を早く簡単に手助けをするツールがいくつかあります。

#### ライブリロード

いちいちテーマを変更した後に```cmd-alt-ctrl-L```を押すのは理想的ではない。Atomは開発モードウインドウでの[live updating](https://github.com/atom/dev-live-reload)をサポートしている。

開発モードウインドウを有効にするには:

1. **_View > Developer > Open in Dev Mode_**メニューまたは```cmd-shift-o```ショートカットから開発ウインドウのテーマディレクトリを開く。
1. Make a change to your theme file and save it. Your change should be immediately applied!
1. テーマを変更して保存する。変更はすぐに適用される！

もし全てのテーマをいつでもリロードしたいなら```cmd-ctrl-shift-r```ショートカットが使えます。

#### 開発ツール

AtomはChrome browserをベースにしています。そしてChrome's Developer Toolsをサポートしている。_View > Toggle Developer Tools_メニューまたは```cmd-alt-i```ショートカットから開発画面を開くことができます。

開発ツールは要素を詳細に確認できCSSプロパティを見ることができるようにしてくれます。

![devtools-img](https://f.cloud.github.com/assets/69169/1347391/2d51f91c-36af-11e3-806f-f7b334af43e9.png)

短い解説がグーグルの[拡張ガイド](https://developers.google.com/chrome-developer-tools/docs/elements)にあります。

#### Atomスタイルガイド

もしインターフェステーマを作っているなら、作成したテーマがシステム内のコンポーネントをどのように変更したかを確認する方法を知りたいと思うだろう。[styleguide](https://github.com/atom/styleguide)はAtomがサポートする全てのコンポーネントを描画するページです。

styleguideを開くには、コマンドパレットを開き(```cmd-shift-P```)_styleguide_を検索するか```cmd-ctrl-shift-g```ショートカットを使ってください。

![](https://f.cloud.github.com/assets/69169/1347390/2d431d98-36af-11e3-8f8e-3f4ce1e67adb.png)
## <a name="5">パッケージ公開</a>

このガイドはパッケージやテーマを[atom.io](https://atom.io/)の登録パッケージに公開する方法を説明します。

パッケージを公開することで他の人もAtomにインストールして使うことができるようになります。あなたが作ったものを共有しフィードバックを得て他の人に貢献することは素晴らしいことです。

このガイドではあなたのパッケージ名を```my-package```と仮定していますがもっといい名前をつけることができます。

### apmインストール

Atomに同梱されている```apm```コマンドラインユーティリティはatom.io登録パッケージに公開する手助けをしてくれます。

ターミナルから以下のコマンドを実行して```apm```がインストールされているかを確認して下さい:

```
apm help publish
```
```apm publish```コマンドの詳細を確認することができます。

もし動作しないのであればAtomを起動して_Atom > Install Shell Commmands_メニューから```apm```と```atom```コマンドをインストールしてください。

### パッケージを準備

もし[your first package](https://atom.io/docs/v0.85.0/your-first-package)を済ませているならもう公開の準備はできているので次のステップは省略することができます。

If not, there are a few things you should check before publishing:
もしそうでなければ公開前にいくつかチェックする項目があります:

+ _package.json_ファイルは```name```,```description```そして```repository```フィールドを持っています
+ _package.json_ファイルは```"0.0.0"の値をもつ```version```フィールドを持っています
+ _package.json_ファイルは```"eingines":{"atom":>=0.50.0"}```のような形でAtomに含まれている```engines```フィールドを持っています
+ パッケージはルートに```README.md```ファイルを持っています
+ Gitレポジトリ内のパッケージは[GitHub](https://github.com/)にプッシュされます。まだパッケージをGitHubに登録していないなら[このガイド](https://guides.github.com/overviews/desktop/)に従ってください。

### パッケージを公開

パッケージを公開する前にすでに同じ名前のパッケージがatom.ioの公開されていないかチェックする時間を取るのは良い考えです。```http://atom.io/packages/my-package```を訪れてパッケージが既に存在するか確認することができます。

さあ、```apm publish```コマンドがすることを復習しましょう:

1. 初めての公開ならばatom.ioにパッケージ名を登録する
1. _package.json_ファイルの```version```フィールドを更新してコミットする
1. 公開されるバージョンの[Gitタグ](http://git-scm.com/book/en/Git-Basics-Tagging)を作る
1. タグと現在のブランチをGitHubにプッシュする
1. 公開されたバージョンでatom.ioを更新する

さあ、以下のコマンドを実行してパッケージを公開しましょう:

```
cd ~/github/my-package
apm publish minor
```
もしこれが最初の公開パッケージなら、```apm publish```コマンドはあなたのGitHubユーザー名とパスワードを確認してきます。これは公開する上で必須ですそして公開する最初の１回だけ入力する必要があります。いちどログインすれば証明は安全にあなたの[keychain](http://en.wikipedia.org/wiki/Keychain_(Apple))に保存されます。

:tada: あなたのパッケージは公開されatom.io内で使うことができるようになりました。```http://atom.io/packages/my-package```にアクセスすればあなたのパッケージページが確認できるはずです。

公開コマンドの```minor```オプションは公開前にバージョンの２番めの番号を加算します。なので公開されるバージョンは```0.1.0```となり```v0.1.0```のGitタグが作られるでしょう。

将来あなたは```1.0.0```バージョンを公開するため```apm publish major```コマンドを実行するでしょう。しかし、すでに最初のバージョンを公開しているのだからマイナーリリースから始めるのは良い考えでしょう。

### さらに詳しく

パッケージリリースのバージョンに関してもっと学びたいのであれば[semantic versioning](http://semver.org/)を参照してください。

## <a name="6">貢献</a>
The following is a set of guidelines for contributing to Atom packages, which are hosted in the Atom Organization on GitHub. If you're unsure which package is causing your problem or if you're having an issue with Atom core, please use the feedback form in the application or email atom@github.com.

### イシューをあげる

+ Include screenshots and animated GIFs whenever possible; they are immensely helpful.
+ Include the behavior you expected and other places you've seen that behavior such as Emacs, vi, Xcode, etc.
+ Check the dev tools (alt-cmd-i) for errors and stack traces to include.
+ Check Console.app for stack traces to include if reporting a crash.
+ Perform a cursory search to see if a similar issue has already been submitted.

### パッケージをハッキングする

#### クローン

The first step is creating your own clone. You can of course do this manually with git, or you can use the apm develop command to create a clone based on the package's repository field in the package.json.

For example, if you want to make changes to the tree-view package, run the following command:
```
> apm develop tree-view
Cloning https://github.com/atom/tree-view ✓
Installing modules ✓
~/.atom/dev/packages/tree-view -> ~/github/tree-view
```
This clones the tree-view repository to ~/github. If you prefer a different path, specify it via the ATOM_REPOS_HOME environment variable.

#### 開発モード実行

Editing a package in Atom is a bit of a circular experience: you're using Atom to modify itself. What happens if you temporarily break something? You don't want the version of Atom you're using to edit to become useless in the process. For this reason, you'll only want to load packages in development mode while you are working on them. You'll perform your editing in stable mode, only switching to development mode to test your changes.

To open a development mode window, use the "Application: Open Dev" command, which is normally bound to cmd-shift-o. You can also run dev mode from the command line with atom --dev.

To load your package in development mode, create a symlink to it in ~/.atom/dev/packages. This occurs automatically when you clone the package with apm develop. You can also run apm link --dev and apm unlink --dev from the package directory to create and remove dev-mode symlinks.

#### 依存関係

Finally, you need to install the cloned package's dependencies by running apm install within the package directory. This step is also performed automatically the first time you run apm develop, but you'll want to keep dependencies up to date by running apm update after pulling upstream changes.

### プルリクエストを送る

#### コードガイドライン

+ Include screenshots and animated GIFs in your pull request whenever possible.
+ Follow the CoffeeScript, JavaScript, and CSS styleguides.
+ Include thoughtfully-worded, well-structured Jasmine specs.
+ Document new code based on the Documentation Styleguide
+ End files with a newline.
+ Place requires in the following order:
  + Built in Node Modules (such as path)
  + Built in Atom and Atom Shell Modules (such as atom, shell)
  + Local Modules (using relative paths)
+ Place class properties in the following order:
  + Class methods and properties (methods starting with a @)
  + Instance methods and properties
+ Avoid platform-dependent code:
  + Use require('atom').fs.getHomeDirectory() to get the home directory.
  + Use path.join() to concatenate filenames.
  + Use os.tmpdir() rather than /tmp when you need to reference the temporary directory.

#### コミットメッセージガイドライン

+ Use the present tense ("Add feature" not "Added feature")
+ Use the imperative mood ("Move cursor to..." not "Moves cursor to...")
+ Limit the first line to 72 characters or less
+ Reference issues and pull requests liberally
+ Consider starting the commit message with an applicable emoji:
  + :lipstick: when improving the format/structure of the code
  + :racehorse: when improving performance
  + :non-potable_water: when plugging memory leaks
  + :memo: when writing docs
  + :bulb: Check out the Emoji Cheat Sheet for more ideas.

### CoffeeScriptスタイルガイド

+ Use parentheses if it improves code clarity.
+ Prefer alphabetic keywords to symbolic keywords:
  + a is b instead of a == b
+ Avoid spaces inside the curly-braces of hash literals:
  + {a: 1, b: 2} instead of { a: 1, b: 2 }
+ Set parameter defaults without spaces around the equal sign:
  + clear = (count=1) -> instead of clear = (count = 1) ->
+ Include a single line of whitespace between methods.

### ドキュメントスタイルガイド

+ Use TomDoc.
+ Use Markdown.
+ Reference methods and classes in markdown with the custom {} notation:
  + Reference classes with {ClassName}
  + Reference instance methods with {ClassName::methodName}
  + Reference class methods with {ClassName.methodName}

#### 例

```coffeescript
# Public: Disable the package with the given name.

# This method emits multiple events:
#
# * `package-will-be-disabled` - before the package is disabled.
# * `package-disabled`         - after the package is disabled.
#
# name     - The {String} name of the package to disable.
# options  - The {Object} with disable options (default: {}):
#   :trackTime - `true` to track the amount of time disabling took.
#   :ignoreErrors - `true` to catch and ignore errors thrown.
# callback - The {Function} to call after the package has been disabled.
#
# Returns `undefined`.
disablePackage: (name, options, callback) ->
```
# 参照
[Atom](https://atom.io/)  
[Documentation](https://atom.io/docs/latest/)  
[GitHub Flavored Markdown](https://help.github.com/articles/github-flavored-markdown)
