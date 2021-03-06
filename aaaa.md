#知識処理システム特論20150522
学修番号: 15890515 氏名: 北川善彬

####NTCIRの概要
---
NTCIR（エンティサイル，NII Testbeds and Community for Information access Research）は情報検索，質問応答，要約，テキストマイニング，機械翻訳など膨大な情報のなかから，所望の情報にアクセスし，情報の理解や活用を支援する技術の大規模な評価基盤を国内外の多数の研究者が共有し，その共通基盤の上でそれぞれの研究を進め，検証，比較評価し，相互に学び合うフォーラムを形成するプロジェクトである．このような基盤を作ることで，研究のためのデータ取得，研究成果の比較が容易になる．1997年より日本学術振興会未来開拓研究事業と学術情報センターの支援を受けプロジェクトを開始し，より豊かな情報アクセス技術の実現と未来価値創成を標榜し，活動を進めている．

NTCIR は，TREC(Text Retrieval Conference)や，CLEF(Conferenc and Labs of the Evaluation Forum)に並ぶ世界3大情報検索評価の一つに数えられている．TRECやCLEFと比較したときの大きな特徴は次の２つである．

1. 日本語で書かれたテキストや文書を対象としていること
2. 自然言語処理と密接な関係を保っている

1に関しては，初期には国際会議で日本語検索の論文が採択されることを目指し，大規模なテストコレクション構築に力を入れていた．次第にチャレンジングな実験設計や新たな研究分野の提案へと力点が推移している．最近のNTCIRでは，中国語や韓国語といった東アジアの諸言語も対象となっており，対象言語が拡張されてきている．
2に関しては，実験室内での実利用者を含まない実検であっても，その種の文書データはどのような利用者がどのような業務や目的で利用するのかという観点から実験とデータセット設計を行うという特徴を発揮してきた．

また，NTCIRの目的は大きく分けて3つある

1. 大規模かつ再利用可能なテストコレクションの構築．
2. システム間の比較，研究上のアイディアの交換等に寄与する研究者フォーラムの展開．
3. 情報アクセス技術の評価手法，評価指標に関する研究の推進．
  
1で挙げた評価ワークショップ形式のテストコレクションはデータベース利用者の検索要求を記述した「検索課題」を満たす「正解文書の網羅的なリスト」から構成され，「実験用データセット」としての意味を持つ．
入，すなわちテストコレクションと実験結果を評価するための共通の手順を用意し広く提供する点にある．つまり，NTCIRに参加するグループは，それぞれNTCIR企画グループが用意したデータを用い，さまざまなアプローチで研究・実験を行う．情報検索やテキスト処理の研究において，繰り返し実験に利用できる大規模な標準データセットが重要であることは広く認められているが，NTCIRはそのようなデータと研究上のアイディアや技術の交換・移転のための研究者フォーラムを提供することによって研究の推進を図る．これら共通のデータに基づく多様な研究と実験により，異なるシステム間の相互比較が共通の基板上で可能となることもNTCIRの特徴の一つである．NTCIRでは，初期から

* 「伝統的な実験室型の情報検索システムの評価テスト」
* 「より新しい課題」

という２つの方向を目指してきた．実験室型の評価テストでは，とくに(1)日本語や他のアジア言語文書の検索(IR)と，(2)言語横断検索に充填をおいている．より新しい課題では，(3)文書検索から「情報」検索へという動きと，(4)より現実的な評価法，たとえばテキスト要約の評価手法，多段階の適合性判定に適した評価指標，特定の文書タイプやそのタイプの文書をよく利用する利用者の特性や利用法に適した評価法に関する研究などに力を注いでいる．ワークショップに参加する研究グループを中心とした研究者フォーラムがこれら2つの方向性を持つ活動を支える役割を果たしている．図1にNTCIRのタスクの変遷を示す．

![](http://research.nii.ac.jp/ntcir/outline/image10.jpg)
　　図1. NTCIRのタスクの変遷（NTCIRホームページより引用）


####対話的情報検索に関するタスク
---
NTCIR-9（第９回のNTCIRワークショップ）にて４つのコアタスクと３つのパイロットタスクが採択されている．このパイロットタスクの中にVisEx（Interactive Visual Exploration，情報可視化を用いた対話的探索タスク）が含まれている．VisExは，対話的・探索的な情報アクセス環境の評価方法を検討するための予備的なタスクである．情報可視化技術を利用したアクセス結果表示とそれへの対話的な操作，質問の言い換えや適合性フィードバック等を通じて，アクセス結果や情報要求の精錬とそれを通じた適合情報の蓄積的な取得を行うという環境を評価する．利用者はブラウザを介して，情報アクセス環境核部とエディタを操作し，用意されたタスクを実施する．情報アクセス環境核部は定められたインターフェイスで検索エンジンやその周辺機器にアクセスし，利用者の要求を伝え，結果（文書，スニペット，文書内容）を取得し，利用者に提示する．このようなやりとりが対話的に繰り返される．利用者が実施するタスクは，イベント収集タスクとトレンド要約タスクの２種類である．イベント収集タスクではNTCIR-7高度多言語質問応答ACLIAに
おけるEvent-ListTypeの質問セットを利用し，その質問の回答となるnugget2を所定時間以内にできるだけ多く快適に獲得することを達成すべき目的としている．文書セットは毎日新聞記事1998-2001年分．利用者に与えられる質問は例えば「NATO軍が自ら認めた誤爆」や「アジアでの航空機墜落事故」等がある．トレンド要約タスクでは，NTCIR-5,6,7  MuSTが対象として時系列統計情報について，一定期間の変化とその原因や影響（動向）の要約を作成する．適切な要約を構成する基本情報をnuggetと考え，所定時間以内に出来るだけ多く快適に収集することを達成すべき目的とする．文書セットは毎日新聞記事1998-1999年分．「98年から99年までのガソリン価格の動き」や「98年から99年までの内閣支持率の変化を知りたい」等が利用者に与えられる質問の例である．利用者実験において，収集されるデータは，（１）被験者によって作成されるレポート，（２）ログ記録，（３）被験者へのアンケート結果の３つである．それぞれを独立もしくは総合的に分析することで，情報アクセス行為を総合的に把握し，情報アクセス環境の役割を評価する．利用者実験の結果，提出されたそれぞれのシステムの評価のための有益な情報をそれぞれ取得することができ，VisExの基本的な枠組みの有効性を確認することができたが，収集したデータからその意味が明確な情報を読取るということは思いの外困難であるという知見が得られた．原因として，（１）被験者間のばらつきが大きい割にその数が少なく，システムの違いが被験者の違いの中に埋もれてしまう点，（２）成果物やその過程の質を議論することが難しいという点，（３）行為の意味を記録することが難しく，ログの取得と解析の方法について未だ改善の余地があるという点．の３つの原因が考察されている．

####参考文献
---

* NTCIR: http://research.nii.ac.jp/ntcir/index-ja.html
* TREC: http://trec.nist.gov/

