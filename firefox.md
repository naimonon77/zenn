# Caution
※ 以下の文章は会話リンクの要約
・会話リンク：https://chatgpt.com/share/66efc32a-3b28-8003-a57d-de70af5b9dd4
・また、Chromeと同じく、スピーカーアイコンを一番右に行かせたかったですが、上手くいきませんでした
・そのため、横に出してます

# やり方

カスタムCSSを使う

Firefoxでは、カスタムCSSを使ってタブやそのアイコンの見た目を変更することができます以下の手順でスピーカーアイコンの位置を調整できます
手順:

1. about:support にアクセスし、 プロファイルフォルダー を開く
1. chrome という名前のフォルダーがない場合は、新しく作る
1. userChrome.css という名前のファイルを chrome フォルダー内に作る
1. 以下のコードを userChrome.css に書く
```
.tab-icon-image {
    display: block !important;   /* 元のアイコンを表示 */
    visibility: visible !important; /* 非表示にならないようにする */
    opacity: 1 !important;       /* 透明にならないようにする */
    z-index: 5 !important;       /* スピーカーアイコンより背面に配置 */
    position: relative !important; /* 相対位置に設定 */
    left: -5px !important;       /* アイコンの位置調整 */
}

/* スピーカーアイコンの調整 */
.tab-icon-overlay {
    left: 15px !important;  /* スピーカーアイコンを少し右にずらす */
    margin-right: 20px !important;
}
```

5. about:config にアクセス
6. 「動作保証外になります」と警告が出ますが、「注意して使用する」をクリック
7. 検索ボックスに toolkit.legacyUserProfileCustomizations.stylesheets と入力し、設定が「true」になっているか確かめる
8. false になっている場合はダブルクリックして true に変える
9. Firefoxを再起動

# 5~8
Firefox 69以降、カスタムCSSを有効にするために必要らしい