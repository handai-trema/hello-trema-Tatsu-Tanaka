#情報ネットワーク学演習II 10/5 レポート課題
===========
提出者 田中 達也

##課題
仮想スイッチを停止したら、コントローラで次のメッセージを表示するようにしてみよう:

```
Bye 0xabc
```
###解答
以下を追加した

```
  def switch_disconnected(datapath_id)
    logger.info "Bye #{datapath_id.to_hex}"
  end
```
切断を捕捉するswitch_disconnectedを定義し、そこでメソッドlogger.infoを用いてログの出力を記述した。
これにより、別のターミナルウィンドウで
```
trema stop 0xabc
```
と実行した時に、
```
Bye 0xabc
```
と表示された．

また、ソースコードに以下の記述をした。
```
  def stop()
    logger.info ""
  end
```
これにより、別ターミナル上で仮想スイッチを切断する前に、元のターミナル上でCtrl+Cを入力してtremaを終了した場合でも、
```
Bye 0xabc
```
と表示される。
##参考文献
デビッド・トーマス+アンドリュー・ハント(2001)「プログラミング Ruby」ピアソン・エデュケーション.


