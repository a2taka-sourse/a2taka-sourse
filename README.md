# a2taka

機械学習モデルの学習・移植・評価、シミュレーション、制作ツールの開発をしています。動作だけでなく、比較実験や計測で採否を確かめる工程を大切にしています。

> **In English** — I train, port, and evaluate ML models, and I decide what to keep by measurement. Highlights: LoRA fine-tuning of the π0.5 vision-language-action model for the PARC2026 robot-learning competition (qualifier score 0.36363 vs. 0.0633 for the organizers' reference example, 0.40556 at rank 100, top 200 advanced; final-round Track 1 score 0.4059; with a written retrospective of what failed); an NNUE evaluator ported to the YaneuraOu shogi engine, verified bit-exact against the reference on 9,112 positions; skia-frames, a parallel Skia renderer for transparent PNG sequences; and a file-manager-style explorer for any MediaWiki. Interested in ML engineering, model evaluation, and infrastructure internships.

## [新訳Wikiの3Dビューア](https://shikabaton.miraheze.org/wiki/3D%E3%83%93%E3%83%A5%E3%83%BC%E3%82%A2?view=globe&layer=elev)

共同制作の架空世界「下腦（geno）」を、球体を回しながら見られるデモです。標高・植生・人口などの層を切り替えられます。環境決定で得たデータをThree.jsで可視化し、MediaWikiの記事内に組み込みました。

## 機械学習・ロボティクス

- **[PARC2026](https://weblab.t.u-tokyo.ac.jp/physical-ai-competition/)** — ロボット基盤モデル π0.5 のLoRA適応と評価。予選Track 1で **0.36363** を記録して本選に進み（配布された学習例の参考スコアは 0.0633、予選終了時の100位は 0.40556、通過は上位200名）、本選第1ラウンドでは Track 1 で 0.4059 まで伸ばしました。[ノートブック・試した手法・Track 3 の反省](https://github.com/a2taka-sourse/parc2026-vla)
- **[禮天将棋（raiten）](https://github.com/a2taka-sourse/raiten-shogi)** — 独自ルールのブラウザ対局を実装。別のエンジン実装でNNUEをやねうら王に移植し、参照実装と **9,112局面** で評価値が一致。v6はv5との比較対局300局で189勝でした。
- **音声合成の学習と評価**（非公開） — 6,989クリップ・約7.08時間の単一話者データでStyle-Bert-VITS2を学習。チェックポイント、推論設定、実聴サンプルを比較しました。
- **GCI データ分析**（非公開：講座の規約による） — 表形式データの予測コンペに参加し、複数モデルのアンサンブルを比較。最終課題では離職予測に取り組みました。

## シミュレーション・開発基盤

- **下腦（geno）｜環境決定** — 共同制作の架空世界で、設定を物理条件に落とす条件アトラスと気候計算の設計・検証を担当。2次元のエネルギー収支モデルとExoPlaSimを使い、地形・気候・食料・人口の計算をつなぎました。[領土変遷と歴史の映像](https://www.youtube.com/watch?v=ybAFa3ah-os)
- **[Wiki Explorer](https://github.com/a2taka-sourse/geno-wiki-explorer)** — MediaWiki のカテゴリと記事をフォルダーのように歩けるブラウザUI。Wikipedia を含む任意の Wiki に向けられます。同じ共同制作で、MediaWikiへの1,334記事の移行にも関わりました。
- **下腦（geno）の設定検索**（非公開・休止中） — Wiki の記事を800字ごとに分けて埋め込みベクトル化し、pgvector で類似検索する仕組み（カテゴリで絞り込み可）と、架空言語の資料だけを根拠に答え、資料にないことは「記載なし」と返す質問応答アプリを作りました。検索結果を生成に渡す一続きの RAG にはまだつないでいません。
- **エージェント用ゲートウェイ**（非公開） — ツール呼び出しとセッション間通信をつなぐローカルゲートウェイを構築し、動作を確認しました。
- **ローカルAI環境**（非公開） — LinuxのGPU機を構築し、Windowsから学習・推論・3D生成を実行する作業環境を整えました。

## 映像・音楽・3D

- **[skia-frames](https://github.com/a2taka-sourse/skia-frames)** — 描画関数を一つ書けば、Skia で透過PNG連番を並列に描き出す Node.js ツール。長尺映像の図表 8,858枚を、メモリ8 GBのPCで4分57秒で描画した実績があります。
- **[骨粉史](https://www.youtube.com/watch?v=yG7qadPqosU)** — 約86分の歴史映像の共同制作。長尺を章ごとにレンダリングし、エンコードと出力の検証を進めました。
- **UNSLITHER**（制作中・非公開） — 楽曲制作でローカルAIの **YuE2** を使用。音源分離、ピッチ・ビート検出、MIDI化、楽器の差し替えも制作工程に組み込みました。
- **ローカル3D生成とBlender**（制作中・非公開） — 画像から生成した3Dメッシュをローカルで扱い、Blenderで編集するワークフローを整備。PC教室のレイアウトの3D再現にも取り組んでいます。


機械学習エンジニアリング、モデル評価、開発基盤のインターンに関心があります。

連絡先: muse-3h7j@muse.ai
