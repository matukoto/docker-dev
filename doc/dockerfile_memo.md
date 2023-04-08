---
title: "dcokerfile__"
emoji: "📀"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["docker", "Dockerfile"]
published: false
---
# はじめに

# Dockerfile の効率的かつ保守性の高い書き方
## Dockerfile とは
## Docker image を利用する際の注意点
- 再現性
  - build のタイミングに酔って image の中身が変わらないようにする
- セキュリティ
  - コンテナに不正に侵入された際の影響を限定するために､最小限の権限しか持たせない
- 可搬性
  - image サイズは小さい方が build､配布時間の短縮になる
## 不要な特権を避ける
### rootless
~~~dockerfile
# Create user and set ownership and permissions as required
RUN adduser -D myser && chown -R myuser /myapp-data
# ... copy application files
User myuser

ENTRYPOINT ["/myapp"]
~~~
## 不要なパッケージをインストールしない
Alpine を安易に使うのはやめた方がいいのか?
[軽量Dockerイメージに安易にAlpineを使うのはやめたほうがいいという話 \- inductor's blog](https://blog.inductor.me/entry/alpine-not-recommended)
## 参考
[社内のDockerfileのベストプラクティスを公開します│FORCIA CUBE│フォルシア株式会社](https://www.forcia.com/blog/002273.html)
## 内容

## まとめ
