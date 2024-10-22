# モーダルサイトの制作手順


## 事前準備

本リポジトリをダウンロードして、outputフォルダ → jsフォルダのscript.jsファイルをエディタ(VisualCodeなど)で開いてください。


## STEP1  HTML要素を取得する

モーダル全体、モーダルの×ボタンの要素を取得します。

script.jsファイルに以下のコードを記載してください。

```
/*STEP1:  HTML要素を取得する*/
const modal = document.querySelector('.js-modal');
const modalClose = document.querySelector('.js-modal-close');
```

## STEP2 Webページをロードしたタイミングで、モーダルを表示させる

Webページをロードした際のイベントリスナーを設定します。

ページロードしたら、モーダル表示させるCSSクラスをモーダル要素に追加します。

script.jsファイルに以下のコードを記載してください。

```
/*STEP2 Webページをロードしたタイミングで、モーダルを表示させる*/
function loadEvent() {
    modal.classList.add('is-open');
}

window.addEventListener('load', loadEvent);
```

## STEP3 ×ボタンをクリックしたタイミングで、モーダルを閉じる

×ボタンをクリックした際のイベントリスナーを設定します。

ボタンクリックしたら、モーダルが消えるように、「モーダル表示させるCSSクラス」をモーダル要素から削除します。

script.jsファイルに以下のコードを記載してください。

```
/*STEP3 ×ボタンをクリックしたタイミングで、モーダルを閉じる*/
function clickEvent() {
    modal.classList.remove('is-open');
}

modalClose.addEventListener('click', clickEvent);
```

## STEP4 プログラムコードの整理

loadEvent()、clickEvent()の2つの関数とイベントリスナーを記述しましたが、関数同士、イベントリスナー同士で綺麗に分けて記述してみましょう。
(関数は関数で、イベントリスナーはイベントリスナーで一箇所にまとめて記述する。)


```
function loadEvent() {
    modal.classList.add('is-open');
}

function clickEvent() {
    modal.classList.remove('is-open');
}

window.addEventListener('load', loadEvent);
modalClose.addEventListener('click', clickEvent);
```