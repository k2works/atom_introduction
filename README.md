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
Packages are at the core of Atom. Nearly everything outside of the main editor is handled by a package. That includes "core" pieces like the file tree, status bar, syntax highlighting, and more.

A package can contain a variety of different resource types to change Atom's behavior. The basic package layout is as follows:
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
Not every package will have (or need) all of these directories.

We have a tutorial on creating your first package.

There are also guides for converting TextMate bundles and TextMate themes so they work in Atom.

### package.json

Similar to npm packages, Atom packages contain a package.json file in their top-level directory. This file contains metadata about the package, such as the path to its "main" module, library dependencies, and manifests specifying the order in which its resources should be loaded.

In addition to the regular npm package.json keys available, Atom package.json files have their own additions.

+ ```main``` (Required): the path to the CoffeeScript file that's the entry point to your package
+ ```stylesheets``` (Optional): an Array of Strings identifying the order of the stylesheets your package needs to load. If not specified, stylesheets in the stylesheets directory are added alphabetically.
+ ```keymaps``` (Optional): an Array of Strings identifying the order of the key mappings your package needs to load. If not specified, mappings in the keymaps directory are added alphabetically.
+ ```menus``` (Optional): an Array of Strings identifying the order of the menu mappings your package needs to load. If not specified, mappings in the menus directory are added alphabetically.
+ ```snippets``` (Optional): an Array of Strings identifying the order of the snippets your package needs to load. If not specified, snippets in the snippets directory are added alphabetically.
+ ```activationEvents``` (Optional): an Array of Strings identifying events that trigger your package's activation. You can delay the loading of your package until one of these events is triggered.

### ソースコード

If you want to extend Atom's behavior, your package should contain a single top-level module, which you export from index.coffee (or whichever file is indicated by the main key in your package.json file). The remainder of your code should be placed in the lib directory, and required from your top-level file.

Your package's top-level module is a singleton object that manages the lifecycle of your extensions to Atom. Even if your package creates ten different views and appends them to different parts of the DOM, it's all managed from your top-level object.

Your package's top-level module should implement the following methods:

activate(state): This required method is called when your package is activated. It is passed the state data from the last time the window was serialized if your module implements the serialize() method. Use this to do initialization work when your package is started (like setting up DOM elements or binding events).

serialize(): This optional method is called when the window is shutting down, allowing you to return JSON to represent the state of your component. When the window is later restored, the data you returned is passed to your module's activate method so you can restore your view to where the user left off.

deactivate(): This optional method is called when the window is shutting down. If your package is watching any files or holding external resources in any other way, release them here. If you're just subscribing to things on window, you don't need to worry because that's getting torn down anyway.

### 簡単なパッケージコード

Your directory would look like this:
```
my-package/
  package.json
  index.coffee
  lib/
    my-package.coffee
```
```index.coffee``` might be:
```javascript
module.exports = require "./lib/my-package"
```
```my-package/my-package.coffee``` might start:
```javascript
module.exports =
  activate: (state) -> # ...
  deactivate: -> # ...
  serialize: -> # ...
```
Beyond this simple contract, your package has access to Atom's API. Be aware that since we are early in development, APIs are subject to change and we have not yet established clear boundaries between what is public and what is private. Also, please collaborate with us if you need an API that doesn't exist. Our goal is to build out Atom's API organically based on the needs of package authors like you.

### スタイルシート

Stylesheets for your package should be placed in the stylesheets directory. Any stylesheets in this directory will be loaded and attached to the DOM when your package is activated. Stylesheets can be written as CSS or LESS.

Ideally, you won't need much in the way of styling. We've provided a standard set of components which define both the colors and UI elements for any package that fits into Atom seamlessly. You can view all of Atom's UI components by opening the styleguide: open the command palette (cmd-shift-P) and search for styleguide, or just type cmd-ctrl-shift-G.

If you do need special styling, try to keep only structural styles in the package stylesheets. If you must specify colors and sizing, these should be taken from the active theme's ui-variables.less. For more information, see the theme variables docs. If you follow this guideline, your package will look good out of the box with any theme!

An optional stylesheets array in your package.json can list the stylesheets by name to specify a loading order; otherwise, stylesheets are loaded alphabetically.

### キーマップ

It's recommended that you provide key bindings for commonly used actions for your extension, especially if you're also adding a new command:
```
'.tree-view-scroller':
  'ctrl-V': 'changer:magic'
```
Keymaps are placed in the keymaps subdirectory. By default, all keymaps are loaded in alphabetical order. An optional keymaps array in your package.json can specify which keymaps to load and in what order.

Keybindings are executed by determining which element the keypress occurred on. In the example above, changer:magic command is executed when pressing ctrl-V on the .tree-view-scroller element.

See the main keymaps documentation for more detailed information on how keymaps work.

### メニュー

Menus are placed in the menus subdirectory. By default, all menus are loaded in alphabetical order. An optional menus array in your package.json can specify which menus to load and in what order.

#### アプリケーションメニュー

It's recommended that you create an application menu item for common actions with your package that aren't tied to a specific element:
```
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
To add your own item to the application menu, simply create a top level menu key in any menu configuration file in menus. This can be a JSON or CSON file.

The menu templates you specify are merged with all other templates provided by other packages in the order which they were loaded.

#### コンテクストメニュー

It's recommended to specify a context menu item for commands that are linked to specific parts of the interface, like adding a file in the tree-view:
```
'context-menu':
  '.tree-view':
    'Add file': 'tree-view:add-file'
  '.workspace':
    'Inspect Element': 'core:inspect'
```
To add your own item to the application menu simply create a top level context-menu key in any menu configuration file in menus. This can be a JSON or CSON file.

Context menus are created by determining which element was selected and then adding all of the menu items whose selectors match that element (in the order which they were loaded). The process is then repeated for the elements until reaching the top of the DOM tree.

In the example above, the Add file item will only appear when the focused item or one of its parents has the tree-view class applied to it.

### スニペット

An extension can supply language snippets in the snippets directory which allows the user to enter repetitive text quickly:
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
A snippets file contains scope selectors at its top level (.source.coffee .spec). Each scope selector contains a hash of snippets keyed by their name (Expect, Describe). Each snippet also specifies a prefix and a body key. The prefix represents the first few letters to type before hitting the tab key to autocomplete. The body defines the autofilled text. You can use placeholders like $1, $2, to indicate regions in the body the user can navigate to every time they hit tab.

All files in the directory are automatically loaded, unless the package.json supplies a snippets key. As with all scoped items, snippets loaded later take precedence over earlier snippets when two snippets match a scope with the same specificity.

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

# 参照
[Atom](https://atom.io/)  
[Documentation](https://atom.io/docs/latest/)  
[GitHub Flavored Markdown](https://help.github.com/articles/github-flavored-markdown)
