# SIRIUS-for-KBC
## v4.2.1リリース
データ取得アルゴリズムに関して、約2%ほどの高速化を実装しました。
>last release
>
>**v4.2.0リリース**  
>テーブル形式コンテンツのUXを改善しました。

## 使い方
本アプリケーション(以下、SIRIUS)は、予餞会における大規模映像制作活動の情報共有を担うアプリケーションです。
### トップページ
`TOP`ページでは、
1. 現在時刻表示
2. 撮影状況(撮影済、アポ未取得、撮影待ち)
3. パッチノート
4. 共有用QRコード
5. スプレッドシート出力ボックス

が表示されています。  
- `1. 現在時刻表示`は、アクセスしているデバイスの内部時刻を参照して表示しているため、後述する`オフラインモード`のときでも動作します。  
- `2. 撮影状況`は、現在登録されている撮影状況からそれぞれの人数をカウントし表示しています。詳しい撮影情報は`北コレ > データベース`から確認することができます。
- `3. パッチノート`では、アップデート情報を確認することができます。
- `4. 共有用QRコード`を読み込むことで、SIRIUSを開くことができます。近くにいる人に共有する際などに役立ててください。
- `5. スプレッドシート出力ボックス`は、データベースとなっているスプレッドシートの全シートの中から任意のシートをPDFとして特定のGoogle Driveフォルダに出力することができます。
___
### 北コレ
`北コレ`ページでは、
1. データベース
2. 北コレ撮影アポ取り状況確認

の2つのページへ移動することができます。  
- `1.データベース`では、撮影対象者の各データを確認することができます。`撮影済` `アポ未取得` `撮影待ち` `今日の予定`の4つの条件で絞り込むことができます。`絞り込みリセット`ですべてのデータを表示します。
- `2. 北コレ撮影アポ取り状況確認`では、縦軸が日付・横軸が時間帯の表が表示されています。各セルに`T-01`などの撮影対象者に振られたコード(以下、撮影コード)をセットすることで、その撮影対象者の撮影日程を登録することができます。
  - 1つのセルに2つ以上の撮影コードをセットする場合は、撮影コードを`,(カンマ)`で区切ってください。
  - 撮影コードは以下の条件を満たすものとします。
    - `T-○○`の形式であること
    - `T-01`のように数字を最大の数字(このケースでは2桁の最大の整数値すなわち99)に合わせてゼロ埋めすること
  - 撮影コードが入力され、セルからフォーカスが離れた瞬間に撮影日程登録の処理が開始されます。誤った情報を入力してしまった場合は管理者にお願いして復元作業を行ってください。
  - このテーブルはリアルタイムで書き込むことは可能ですが、リアルタイムで別のユーザーが入力したデータを表示することはできません。`再読み込み`ボタンを押すと、最新の入力値を表示させることができます。
___
### 名簿
`名簿`ページでは、
1. 放送部・写真部
2. 縦割り

の2つの名簿を参照することができます。このページに表示されている名簿情報は、SIRIUS上から書き換えることはできません。書き換える際は管理者がスプレッドシートから書き換えるようにしてください。
___
### ADMIN
`ADMIN`ページは現在構築中です。管理者のみアクセスすることができます。
___
### オフラインモード
SIRIUSは、アクセスしているデバイスのインターネット接続状況を常に監視しています。  
デバイスのインターネット接続が切れると、SIRIUSは自動的に`オフラインモード`へ移行します。この状態では、
- ロゴマークからの再読み込み
- メニューバーおよびハンバーガーメニューの表示
- 他ページへの移動

が禁止されます。オフラインモードでは、前述したとおり現在時刻表示機能のみ動作します。オフラインモードのSIRIUSを再読み込みすると必要な通信ができずにエラーを返します。  
インターネット接続が復帰されると、SIRIUSは自動でオフラインモードをオフにし通常画面へ戻ります。
___
## 諸注意
SIRIUSにアクセスするためには、学校から配布されているGoogleアカウント`(@oks.city-saitama.ed.jp)`にログインする必要があります。
___
>https://script.google.com/a/macros/oks.city-saitama.ed.jp/s/AKfycbzgu85a2oJgZxC8J5CGWDjrTEHlu85w9dcXnJ19tkgHEGfQyFKlnNhlP-IjG_Acf0dC/exec

SIRIUS for KBC v4.2.0  
author name: uyuyuu09  
author email: uyuyu.0301@gmail.com
