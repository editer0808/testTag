


 - ***blockingQue 失敗時***

| |特殊な値|例外|
|--:|:--|--:|
|要素追加| boolean offer(E e)|blean add(E e)|
|要素の取得|E peek()|E element()|
|要素の削除|E poll()|E remove()|

| |ブロック|タイムアウト|
|--:|:--|--:|
|要素追加| put(E e)|offer(E e)|
|要素の削除|take poll()|poll()|

 - CopyOnWriteArrayList クラス
Copy-On-Write 書き込みに対してコピーを作成するという意味
常にコピーをとっているので、ConcurrentModificationExceptionは発生せず不要。
ただし大量のデータ変更の際には向いていない。

##ReadWriteLock クラス  

 リードライドロック
 常に１つのスレッドだけがロックを取得できる排他ロックを用いている
 - ReentrantReadWriteLock
複数スレッドの読み取りOK
書き込みは単一スレッドのみ


##Callable クラス  
java.util.concurrent.Callable

v call thows Exception

```
 Future<Date> future = executor.submit(new TheadA()); //runと同じ
future.get()


class TheadA implements Callable<Data>{
	public Date call() throws Exception{

	}
}
```



##Executor クラス  
 Executorを利用しているスレッドは自動では終了しない。
  
```
ExecutorService e = Executors.newSingleThreadExector();
e.execute(task);//
```

shoutdown()
タスクキュー
shoutdownNow()


 isTerminated()
 キュのタスクがすべて終了したかを確認する方法



例外
 - ConcurrentModificationException 操作途中でコレクションの内容が変更された際に発生する例外


 半永久的に接続できないことをスタベーション

##DB
executeQuery();
executeQuery();
２回実行される時点で、1回目の閉じられる

スクロール可能
createStatement(定数スクロール可否,定数データ更新の可否);
ResultSet.TYPE.FORWARD_ONLY カーソル順次
」


TYPE_SCROLL_SENSITIVEの場合

スクロール　メソッド
next()
previous()
relative()

absolute(番号)　指定した行番号に移動　0は最初の行より１つ前の空行　数よりお大きい場合は最終行に移動いう


beforeFirst() 最終行の直後
beforeFirst()　最初の行の前
first()最初の行
last()最終行



isAfterLast() 


getErrorCode() ベンダー固有の例外コード
SQLState() 5文字からなるSQLステート　


