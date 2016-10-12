#情報ネットワーク学演習II 10/5 レポート課題
===========
提出者 田中 達也

##課題
HelloTrema が起動したら次のメッセージを表示するようにしてみよう:

```
HelloTrema started.
```

ただし、次の回答ではダメ (なぜダメか？も考察しよう)

```ruby
class HelloTrema < Trema::Controller
  def start(_args)
    logger.info 'HelloTrema started.'
  end
  ...
```
###解答
上記の解答ではHelloTremaを2回記述している。
正しくメッセージは表示されるが、例えばクラス名が変更になった場合、HelloTremaを2つとも記述変更を行う必要があり、作業効率が悪くなったり、変更忘れの可能性が高くなる。
そのため、最初に定義されているクラス名をそのまま用いることが望ましい。
そこでstart関数内で以下のように記述した。

```
logger.info "#{self.class.name} started."
```

クラス名を取得するために、self.class.name を用いた。
selfは現在のメソッドのオブジェクトを返す．
classはそのオブジェクトのクラスを返す．
nameはモジュールの名前を返す．
したがって、self.class.nameによって現在のクラス名HelloTremaを取得できる。
また、エスケープシーケンスが利用できるダブルクォート内で#{式}というシーケンスを使用することで文字列内にRubyの式の値を挿入することができる。

###ソースコードのリンク
* [hello_trema.rb](https://github.com/handai-trema/hello-trema-Tatsu-Tanaka/blob/master/lib/hello_trema.rb) (本課題のソースコード)

##参考文献
デビッド・トーマス+アンドリュー・ハント(2001)「プログラミング Ruby」ピアソン・エデュケーション.


