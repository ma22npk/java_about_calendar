# java_about_calendar
calendarクラスについて学んだことのアウトプットです
<!-- ここから キャプチャー -+-+-+-+-+-+-+ -->
<!-- キャプチャータイトル -->
## Calendarクラス


<!-- 説明 「〜〜とはなど」-->
### 【説明】

「 *日付や 指定した日時の計算* 」 などを行う場合に使用します。

<!-- 特徴・メリット -->
### 【使用場面】


- *入会してから90日後*
- *今日から１ヶ月と２週間後*

といった、少々ややこしい計算が必要な時に便利です。

<!-- 基本構文 -->
### 【基本構文】

#### java.util.Calendar の インポート
まずは `import java.util.Calendar;` で通常のように[インポート]を行います。

```java
// Calendarクラスのインポート
import java.util.Calendar;
```
#### getInstanceメソッド で オブジェクト の生成(重要)
「 **Calendarクラスでは演算子newではなく、getInstanceメソッドを呼びオブジェクトを生成**」します。
#### getInstanceメソッド 
 getInstanceメソッド は呼び出すごとに
 「*現在の日付と時間に初期化された状態でオブジェクトを返す*」メソッドです。

以上を踏まえて、Calendarクラスの[インスタンス]化( オブジェクト化 )のしかたはこちらです。

 
```java
//Calendarクラスの オブジェクト の生成
Calendar calendar = Calendar.getInstance();
```

### calendarクラスの「主要フィールド」のチートシート

| フィールド        | 用途                   | 
| ----------------- | ---------------------- | 
| YEAR              | 年                     | 
| MONTH             | 月（0 ~ 11）           | 
| DATE,DAY_OF_MONTH | 現在の 月 の 何日目 か | 
| WEEK_OF_MONTH     | 現在の 月 の 何周目 か | 
| DAY_OF_WEEK       | 現在の 週 の 何日目 か | 
| AM_PM             | 午前 か 午後 か        | 
| HOUR              | 午前 / 午後 の 何時 か | 
| HOUR_OF_DAY       | 24時間制 で 何時 か    | 
| MINUTE            | 分                     | 
| SECOND            | 秒                     | 

<!-- ここから キャプチャー -+-+-+-+-+-+-+ -->
<!-- キャプチャータイトル -->
## Calendarクラスに使うメソッド

Calendarクラスで特に使えそうなメソッドである、getTimeメソッド, setメソッド, addメソッド, formatメソッド のまとめです。


### 【使用場面】

- getTimeメソッド (時刻を出力)
- setメソッド (日時を設定する)
- add (日付の加減算を行う)
- format (文字列で日付のフォーマットを指定)

<!-- ここから キャプチャー -+-+-+-+-+-+-+ -->
<!-- キャプチャータイトル -->
## getTime()メソッド

<!-- 説明 「〜〜とはなど」-->
### 【説明】

<!-- 特徴・メリット -->
getTimeメソッドを利用することで、カレンダーから「 *現在の時刻をjava.utilパッケージ の Dateオブジェクト* 」 として取得できます。
### 【使用場面】

- 現在時刻を表示したい時
- setされた時刻を表示したい時

<!-- 基本構文 -->
### 【基本構文】

基本的には **カレンダーの`オブジェクト名`にドットで`getTime()`繋げて呼び出します。**

```
// getTime()
Calendarクラスのオブジェクト名.getTime()
```

<!-- ここから サンプルコード ★☆★☆★☆★☆★ -->
<!-- サンプルコードタイトル -->
### 【サンプルコード】 getTime()メソッドで現在時刻を出力

現在時刻を出力する場合以下のように記述します。

```
System.out.println(Calendarクラスのオブジェクト名.getTime());
```
getTime() メソッドを用いた一連の流れがこちらです。

<!-- サンプルコード -->
```java
package about_java_dateClass;

//Calendarクラスのインポート
import java.util.Calendar;

public class DateMain {

    public static void main(String[] args) {
			
        // Calendarクラスの オブジェクト の生成
        Calendar calendar = Calendar.getInstance();

        // 現在時刻を出力
        System.out.println(calendar.getTime());
    }
}
```
<!-- 実行結果 -->
#### 【実行結果】

```
Sun Nov 29 12:58:32 JST 2020
```

<!-- ここまで サンプルコード ★☆★☆★☆★☆★ -->


<!-- 補足 -->


<!-- ここまで  キャプチャー -+-+-+-+-+-+-+ -->





<!-- ここから キャプチャー -+-+-+-+-+-+-+ -->
<!-- キャプチャータイトル -->
## setメソッド (日時を設定する)

<!-- 説明 「〜〜とはなど」-->
### 【説明】
setメソッドは日時を設定するために使用します。

<!-- 特徴・メリット -->
### 【使用場面】

「*2020年を2030年に設定*」といったような、**日付を処理する**ようなプログラムによく使われます。

### 【基本構文】

```
calendar.set(年, 月, 日, 時, 分, 秒);
```

#### 年月日時分をまとめて指定するとき

```java
Calendar calendar = Calendar.getInstance();
calendar.set(2021, 1, 30, 22, 01, 55);
// 現在時刻を出力
System.out.println("現在時刻は" + date);
// setした時刻を出力
System.out.println("setした日時は" + calendar.getTime());
```
出力結果

```
現在時刻はSun Nov 29 12:38:43 JST 2020
setした日時はTue Mar 02 22:01:55 JST 2021
```

#### 特定の日付／時刻要素（たとえば年だけ）を指定するとき

```java
Calendar calendar = Calendar.getInstance();
calendar.set(Calendar.YEAR, 2040);

// 現在時刻を出力
System.out.println("現在時刻は" + date);
// setした時刻を出力
System.out.println("setした日時は" + calendar.getTime());
```

出力結果

```
現在時刻はSun Nov 29 12:40:19 JST 2020
setした日時はThu Nov 29 12:40:19 JST 2040
```

<!-- ここまで  キャプチャー -+-+-+-+-+-+-+ -->

<!-- ここから キャプチャー -+-+-+-+-+-+-+ -->
<!-- キャプチャータイトル -->
## addメソッド (日付の加減算を行う)

<!-- 説明 「〜〜とはなど」-->
### 【説明】
Calendarクラスで
「 *現在時刻を基準に日付の加減算を行うとき* 」には `addメソッド`を使用する
。addメソッドでは、指定された日付／時刻要素（getメソッドの表を参照）に対して、

- 引数の値だけ加算
- 引数が負数の場合には減算

を行います。

### 【使用場面】

現在時刻から何年後、何年前、何日後、何日前といった日にちを計算して表示するなど。

<!-- 基本構文 -->
### 【基本構文】

```
Calendar calendar = Calendar.getInstance();
calendar.add(Calendar.演算する対象, 値);
```

<!-- ここから サンプルコード ★☆★☆★☆★☆★ -->

<!-- サンプルコードタイトル -->
### 【サンプルコード】 現在時刻から３ヶ月前の日付を表示するプログラム

現在 `日本時間で　2020年　11月　29日`ですが、そこから addメソッドを使って日付操作を行ってみます。

```java
//Calendarクラスのインポート
import java.util.Calendar;

public class DateMain {

    public static void main(String[] args) {

        Calendar calendar = Calendar.getInstance();

        // addメソッドで 5年前にする
        calendar.add(Calendar.YEAR, -5);
        // addメソッドで １ヶ月後にする
        calendar.add(Calendar.MONTH, 1);
        // addメソッドで 10日前にする
        calendar.add(Calendar.DATE, -10);
        // 年を表示
        System.out.println(calendar.get(Calendar.YEAR) + "年");
        // 月を表示
        System.out.println(calendar.get(Calendar.MONTH) + "月");
        // 日を表示
        System.out.println(calendar.get(Calendar.DATE) + "日");

    }

}
```
<!-- 実行結果 -->
#### 【実行結果】
以上のプログラムで現在時刻 `日本時間で　2020年　11月　29日`を操作し実行結果が以下になります。

```
2015年
11月
19日
```

<!-- ここまで サンプルコード ★☆★☆★☆★☆★ -->



<!-- ここまで  キャプチャー -+-+-+-+-+-+-+ -->

<!-- ここから キャプチャー -+-+-+-+-+-+-+ -->
<!-- キャプチャータイトル -->
## formatメソッド


<!-- 説明 「〜〜とはなど」-->
### 【説明】
文字列で日付のフォーマットを指定することができるメソッドです。

### 【使用場面】

"〇〇〇〇年〇〇月〇〇日"といったような、馴染みのあるフォーマットに変えたい時に使用する。

<!-- 基本構文 -->
### 日時の書式について
こちらが日時のフォーマットの書式をまとめたものになります。
こちらのアルファベットを用いてフォーマットを作成していきます。

| 書式 | 概要                | パターン          | 表示               | 
| ---- | ------------------- | ----------------- | ------------------ | 
| G    | 紀元                | G                 | AD                 | 
| y    | year, 年            | yyyy<br>yyy       | 2020<br>20         | 
| M    | Month, 月           | MM<br>MMM<br>MMMM | 03<br>Mar<br>March | 
| d    | day, 日             | d<br>dd           | 1<br>01            | 
| H    | 時(0-23)            | H<br>HH           | 0<br>00            | 
| K    | 午前/午後の時(0-11) | K<br>KK           | 0<br>00            | 
| h    | 午前/午後の時(1-12) | h<br>hh           | 1<br>01            | 
| m    | 分                  | m<br>mm           | 0<br>00            | 
| s    | 秒                  | s<br>ss           | 0<br>00            | 
| S    | ミリ秒              | S<br>SSS          | 1<br>001           | 

### 【基本構文】

まずはパッケージ指定後、Calendarクラスといっしょに`java.text.SimpleDateFormat;`をインポートします。

```java
// java.text.SimpleDateFormat をインポート。
import java.text.SimpleDateFormat;

import java.util.Calendar;
```
[インポート]後インスタンス化を行います。SimpleDateFormatの略で「sdf」とする場合が多いかもしれません。
そして、時刻表示する場合のフォーマットを作成します。
以下の例場合の実行結果も添えます。

```java
// Calendarクラスの オブジェクト の生成
        Calendar calendar = Calendar.getInstance();
        //日付のフォーマットを設定
        SimpleDateFormat sdf = new SimpleDateFormat("yyyy年 MM月 dd日 E曜日 HH時(hh時) mm分 ss秒 SSSミリ秒");
```

```java
// フォーマットを適用し現在時刻を表示
System.out.println(sdf.format(calendar.getTime())); 
```

実行結果

```
2020年 11月 29日 日曜日 15時(03時) 04分 36秒 845ミリ秒
```

## あとがき
最近だとjava.utilでの日付操作はモダンではないようですが、今の所現場で現役だそうなので、習得しておきたい。


## 参考資料

- [setメソッド](https://java-code.jp/219)
- [getTimeメソッド](https://java-code.jp/222)
- [format](https://java-code.jp/173)




[Progate]:https://prog-8.com/
[ドットインストール]:https://dotinstall.com/
[インスタンス]:https://qiita.com/takahirocook/items/ec01cdcbb440cf0d1cc4
[インスタンス化]:https://qiita.com/takahirocook/items/ec01cdcbb440cf0d1cc4
[アクセス修飾子]:https://qiita.com/takahirocook/items/e51b0b9d37d95ad587fe
[フィールド]:https://qiita.com/takahirocook/items/28df75a133049a74ece1
[フィールド変数]:https://qiita.com/takahirocook/items/28df75a133049a74ece1
[new演算子]:https://qiita.com/takahirocook/items/00f9f97592bf50831d39
[new]:https://qiita.com/takahirocook/items/00f9f97592bf50831d39
[カプセル化]:https://qiita.com/takahirocook/items/e469a7c0539a0012868e
[クラス]:https://qiita.com/takahirocook/items/50cbbdca8e21539170e9
[メソッド]:https://qiita.com/takahirocook/items/5bfe43576d87a2a4006c
[mainメソッド]:https://qiita.com/takahirocook/items/f4635915337303de338c
[メソッドの呼び出し]:https://qiita.com/takahirocook/items/f4635915337303de338c
[コンストラクタ]:https://qiita.com/takahirocook/items/fa1822f2f22c3786593e
[引数]:https://qiita.com/takahirocook/items/5e5b0ba79e869f4a592e
[戻り値]:https://qiita.com/takahirocook/items/3b6fa670a1d6dd4a9386
[this]:https://qiita.com/takahirocook/items/d251ec4693c68f6b9538
[getter・setter]:https://qiita.com/takahirocook/items/27828bc8477735612021
[setter]:https://qiita.com/takahirocook/items/27828bc8477735612021
[getter]:https://qiita.com/takahirocook/items/27828bc8477735612021
[オブジェクト指向]:https://qiita.com/takahirocook/items/041ba7a096b71ab8ffd4
[継承]:https://qiita.com/takahirocook/items/6c84ea66a6e2ad536a37
[オーバーライド]:https://qiita.com/takahirocook/items/09dd8e5f56d6617ce45a
[オーバーロード]:https://qiita.com/takahirocook/items/b937c3c07126fe7e02a4
[this]:https://qiita.com/takahirocook/items/d251ec4693c68f6b9538
[super]:https://qiita.com/takahirocook/items/75a07131e7e791c8442c
[スーパークラス]:https://qiita.com/takahirocook/items/75a07131e7e791c8442c
[final]:https://qiita.com/takahirocook/items/5e0916d9bf28bcf68d0c
[final修飾子]:https://qiita.com/takahirocook/items/5e0916d9bf28bcf68d0c
[定数]:https://qiita.com/takahirocook/items/5e0916d9bf28bcf68d0c
[static修飾子]:https://qiita.com/takahirocook/items/cf527f85d17a5af86735
[static]:https://qiita.com/takahirocook/items/cf527f85d17a5af86735
[インスタンスフィールド]:https://qiita.com/takahirocook/items/cf527f85d17a5af86735
[インスタンス変数]:https://qiita.com/takahirocook/items/cf527f85d17a5af86735
[動的メソッド]:https://qiita.com/takahirocook/items/cf527f85d17a5af86735
[インスタンス変数]:https://qiita.com/takahirocook/items/cf527f85d17a5af86735
[静的メソッド]:https://qiita.com/takahirocook/items/cf527f85d17a5af86735
[クラスメソッド]:https://qiita.com/takahirocook/items/cf527f85d17a5af86735
[静的メソッド]:https://qiita.com/takahirocook/items/cf527f85d17a5af86735
[クラスフィールド]:https://qiita.com/takahirocook/items/cf527f85d17a5af86735
[クラス変数]:https://qiita.com/takahirocook/items/cf527f85d17a5af86735
[静的変数]:https://qiita.com/takahirocook/items/cf527f85d17a5af86735
[インターフェイス]:https://qiita.com/takahirocook/items/ca84be8dfef664b19194
[インターフェース]:https://qiita.com/takahirocook/items/ca84be8dfef664b19194
[パッケージ]:https://qiita.com/takahirocook/items/39b58d17abcb159ef5c1
[インポート]:https://qiita.com/takahirocook/items/59a8a09cab6a98d3bca2
[import]:https://qiita.com/takahirocook/items/59a8a09cab6a98d3bca2
[配列]:https://qiita.com/takahirocook/items/16a123fb73b30869053b
[配列操作]:https://qiita.com/takahirocook/items/16a123fb73b30869053b
[List]:https://qiita.com/takahirocook/items/4d622fc6f271569783b5
[list]:https://qiita.com/takahirocook/items/4d622fc6f271569783b5
[Map]:https://qiita.com/takahirocook/items/49f46151ecb5e332db32
[map]:https://qiita.com/takahirocook/items/49f46151ecb5e332db32
[set]:https://qiita.com/takahirocook/items/d498329cd26e1500f476
[Set]:https://qiita.com/takahirocook/items/d498329cd26e1500f476
[拡張for文]:https://qiita.com/takahirocook/items/470b2858de1a4f99b334

