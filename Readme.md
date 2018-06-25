【プログラム】
```java
import cv2

capture = cv2.VideoCapture(0)

while(True):
    ret, frame = capture.read()
    cv2.imshow('frame',frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

capture.release()
cv2.destroyAllWindows()
```

以上のプログラムを以下のコードで実行する.
C:\Users\owner\github>python Capture.py

---

【説明】
cv2.VideoCapture()でVideoCaptureオブジェクトを取得.引数にコンピュータに接続されているカメラの番号を指定.コンピュータにカメラが1台だけしか接続されていない場合は"0",複数のカメラが接続されている場合は"1"などの番号を指定.

　カメラから連続的に画像を取得するためwhile文で繰り返し処理を行う.while内の最初でカメラから1コマのデータを取得するため capture.read()をよびだす.取得した1コマの画像データは変数frameに代入される.

　OpenCVにはOSのフレームに画像を表示してくれるcv2.imshow()メソッドがある.第一引数は開くフレームの名前を文字列で指定.そして第二引数にはcapture.read()で取得した画像データを指定.cv2.imshow()メソッドを呼び出すと,自動的にフレームが立ち上がって画像を表示してくれる.終了するにはwhileループを抜ける必要があるため"q"をおすとbreakするようになっている."# kubotask1" 
