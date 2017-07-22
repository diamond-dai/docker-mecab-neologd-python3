# mecab-neologd-alpine
## 概要
python3.5から[mecab-ipadic-neologd](https://github.com/neologd/mecab-ipadic-neologd)を使う

## 使い方

### build方法
```
docker build ./ -t mecab-neologd-python3
```

### 起動
```
docker run -it mecab-neologd-python3
```

### 実行例
```
>>> import MeCab
>>> tagger = MeCab.Tagger('-Ochasen -d /usr/local/lib/mecab/dic/mecab-ipadic-neologd')
>>> str = "10日放送の「中居正広のミになる図書館」（テレビ朝日系）で、SMAPの中居正広が、篠原信一の過去の勘違いを明かす一幕があった。"
>>> print(tagger.parse(str))

10日	トオカ	10日	名詞-固有名詞-一般
放送	ホウソウ	放送	名詞-サ変接続
の	ノ	の	助詞-連体化
「	「	「	記号-括弧開
中居正広のミになる図書館	ナカイマサヒロノミニナルトショカン	中居正広のミになる図書館	名詞-固有名詞-一般
」	」	」	記号-括弧閉
（	（	（	記号-括弧開
テレビ朝日	テレビアサヒ	テレビ朝日	名詞-固有名詞-組織
系	ケイ	系	名詞-接尾-一般
）	）	）	記号-括弧閉
で	デ	で	助詞-格助詞-一般
、	、	、	記号-読点
SMAP	スマップ	SMAP	名詞-固有名詞-一般
の	ノ	の	助詞-連体化
中居正広	ナカイマサヒロ	中居正広	名詞-固有名詞-人名-一般
が	ガ	が	助詞-格助詞-一般
、	、	、	記号-読点
篠原信一	シノハラシンイチ	篠原信一	名詞-固有名詞-人名-一般
の	ノ	の	助詞-連体化
過去	カコ	過去	名詞-副詞可能
の	ノ	の	助詞-連体化
勘違い	カンチガイ	勘違い	名詞-サ変接続
を	ヲ	を	助詞-格助詞-一般
明かす	アカス	明かす	動詞-自立	五段・サ行	基本形
一幕	ヒトマク	一幕	名詞-一般
が	ガ	が	助詞-格助詞-一般
あっ	アッ	ある	動詞-自立	五段・ラ行	連用タ接続
た	タ	た	助動詞	特殊・タ	基本形
。	。	。	記号-句点
EOS
```


## License
MIT
