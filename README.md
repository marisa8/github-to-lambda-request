# github-to-lambda-request

## AWS Lambda で Python の requests ライブラりを使う方法

とりあえず動かしてみたい時用

1 lambda_function.py ファイル名と lambda_handler で関数を作成する
2 pip で requests をインストールする

```
pip install --target ./package requests
```

3 package の中身を zip する。

```
cd package
zip -r ../my-deployment-package.zip .
```

4 最初に作成した lambda_function.py も zip する。

```
zip my-deployment-package.zip lambda_function.py
```

5 Zip の中身はこんな感じなれば OK

```
my-deployment-package.zip$
  │ lambda_function.py
  │ __pycache__
  │ certifi/
  │ certifi-2020.6.20.dist-info/
  │ chardet/
  │ chardet-3.0.4.dist-info/
  ...
```

6 コンソールの Lambda Functions から function を選んで右上の Upload from からアップ

## まとめ

とりあえず Lambda でコードが動か試してみたい時用です。ライブライが大きい場合はレイヤーにしたり、requirements.txt とスクリプトをつかって自動に上げたり、いろいろな方法もあるので次は試してみたい。

[参考１](https://github.com/csemanish12/aws-lambda#readme)
