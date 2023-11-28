## 2023gsc_TaiyuOzawa-

# 2023年度古橋ゼミ卒論用レポジトリ


2023年度 ゼミ論文/卒業論文

青山学院大学 地球社会共生学部 地球社会共生学科

小澤太佑/Ozawa Taiyu

学生番号 1A120047

指導教員 古橋大地 教授

© Furuhashi Laboratory/Taiyu Ozawa, CC BY 4.0

# Title：画像生成AIによる、ゼミ用画像生成におけるジオワードリストの構築

## Abstract：文章全体の要約

## Introdunction：
画像生成AIの一種である、Midjourneyを用いて、ゼミの様々な場面で活用することができる画像を、精度高く生成できるよう、promptにおける中枢となるジオワードをリスト化し、誰でも簡単に画像を生成できるようにすることが目的である。
画像生成AIとは、ラフスケッチのような画像を、より完成度の高い画像に仕上げる「image to image」と呼ばれるものと、Promptと呼ばれる指示文章から画像を生成する「text to image」と呼ばれるものがあるが、今回は後者の画像生成AIを活用する。「text to image」では、GAN（敵対的生成ネットワーク）と呼ばれる、2つのネットワークを競い合わせることで生成する画像の精度を高める仕組みや、拡散モデルといった、元データに徐々にノイズを加えたり、逆にノイズを消去するプロセスを経て新しいデータを生み出すなど、事前に学習されたモデルを活用し、文字情報からクリエイティビティ豊かな画像を生み出す。
この仕組みを用いて私が作成したいのは、ゼミの紹介動画や、プレゼンテーション、場合によってはゼミのイメージ画像として用いることのできる、バラエティ豊かかつ、さまざまなシチュエーションに可能が画像を生み出すことができる、「ワードリスト」を作成することである。青山学院大学 古橋研究室は、同大学の他ゼミに比べて外部への露出が非常多い。そこで、どんなシチュエーションでも活用可能な画像を、即座に、簡単に生成することができる、中枢ワードリストを作成することで、本ゼミでの活動内容や雰囲気、実績がより他のコミュニティ、人々が認識しやすくなると考えた。また、その内容は完全なる独自的なものではなく、他の分野・業界にも転用可能な普遍的な項目も非常に多いと考えている。

promptではなく「ワードリスト」を作成する理由としては、画像生成AIが日々目まぐるしい変化と成長を遂げる中で、それに呼応してpromptも大きく変化しており、どうしても変数になり得てしまうと考えたからである（a）。一方でワードは、どんなに画像生成AIや最適とされるpromptが変化しようと、必ず必要かつ重要となる定数となりうると考え、今回のこの「ワード」に絞って研究を進めたいと考えた。

研究の方法としては、Discordというチャットサービスプラットフォームを介して画像を生成する「Midjourney」において、自然言語処理AI「ChatGPT-4」でpromptを作成しながら、各シチュエーションにおいて最適なワードを発見し、リスト化を行う。

`どんなシチュエーションの画像が汎用性高いかを質問`
`VAE,GANについては要調べ`
`3.5にするか4にするかも考える`
格納場所：https://docs.google.com/spreadsheets/d/1GLylHkcSu2AUoVp84yU7rH-v1CkUVd7WUmREGl45T1I/edit#gid=804927239


## Methods：（研究に用いた方法、手法、ストラテジーについて記述する。）

`進行過程`

1.先行研究として、画像生成AIや言語処理AIのpromptの「ワード」に着目している研究を調査

2.それに基づき、ワードのリストアップ方法を構築

3.中枢となるジオワードの選定を行う

4.ジオワードをGoogle Sheetsにまとめる
: https://docs.google.com/spreadsheets/d/1GLylHkcSu2AUoVp84yU7rH-v1CkUVd7WUmREGl45T1I/edit#gid=804927239

`別研究の参考制作過程`

1.研究に関する基盤語彙リストを作成

2.語彙にアノテーションを付与

3.学習済みの SVMにワードを記入

`ワードリスト制作過程仮説①`

1.イメージに近い画像を見つける

2.ChatGPTでその画像を読み込み、promptを逆生成する

3.重要なジオワードを抽出する

4.3のワードと類似のワードをリストアップする

5.promptの型にワードを当てはめて検証していく

`ワードリスト制作過程仮説②`

1.古橋研究室でよく使用されるワードを集計する

2.promptの型を作成する

3.1のワードをpromptに当て込む

4.promptの型にワードを当てはめて検証していく

メディウムから、頻出ワードをリストアップ
![スクリーンショット 2023-11-28 11 10 41](https://github.com/furuhashilab/2023gsc_TaiyuOzawa-/assets/87391164/ed130e75-aac7-4a7e-8d2a-9baaf14feb0c)

Google sheetsに順次記載
<img width="819" alt="スクリーンショット 2023-11-28 11 11 39" src="https://github.com/furuhashilab/2023gsc_TaiyuOzawa-/assets/87391164/923d038b-5b78-4d08-94fd-7f18560ed64c">





Midjourneyでは、promptと呼ばれる指示文章によって画像を生成を行うが、その際に画像生成で描写したくないものを「ネガティブprompt」として指定することができる。
よって今回の研究では、「promptに含めるべきワード」と、promptに含まないことでより理想の画像に近づける、「ネガティブprompt」の双方のリスト化を行う。





（実験を伴う研究では、実験方法、実験の原理、装置構成、実験手順、解析手法、実験に用いた試薬、機器などの情報を書く。
調査を行う研究では、調査対象の特徴（例えば「東京都の中学生」等）、標本抽出の方法（例えば、「無作為に100名抽出した」等）、調査の手法（例えば、「アンケート調査」）、「統計処理の手法」に等ついて記載する。
質的研究の場合には、フレームワークとなる考え方や、考察する際の着眼点について説明する。
いずれの場合にも、必要に応じ、「考察に用いるための理論の概略」や、上記の事柄の概説（解説）も書く。
「実験」や「調査」を行う際には、論文の課題を、検証可能なレベルにブレイクダウンする過程、即ち「概念操作化」 (Operationalization) [77][54][55]を行う必要があるが、その過程に関して言及しておいたほうが良い場合には、「概念操作化」の過程を記載する。）

## Results:
研究過程で得られたデータの叙述的な説明を行う。ここで示したデータは、「Introductionで提起した問題への答えとしての仮説」を支える根拠となるものを厳選する。

## Discussion:
Resultsで示したデータがどのような傾向を示しているのか、あるいは、どのような意味を持つのか、それはなぜかを、論証、モデル提示等により説明する。
通常は、「Introductionで提起した問題への答えとしての仮説」（通常は、Discussion・Introduntionの少なくとも片方には明示し、Conclusionには必ず記載する。仮説とはここではデータの傾向等についての見解や要点、推定要因等）を提示した上で、「Resultsで示したデータや、先行研究の結果」（根拠）と「仮説」の間を結ぶ推論過程（論拠）を記述する。必要に応じて、実験自体の妥当性も論証する。

## Conclusion

## 謝辞

## 参考文献
https://docs.google.com/spreadsheets/d/1GLylHkcSu2AUoVp84yU7rH-v1CkUVd7WUmREGl45T1I/edit#gid=0


