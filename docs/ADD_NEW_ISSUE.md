# 新しい号を追加する手順

1. `data/_template.json` を `data/issue-NN.json` にコピー（NNは号数）。
2. 議会だより・会議録から、各議員の問・答を流し込む。
   - 3問以上の議員は、目次（P.8 一覧表）で**〇の付いた番号だけ** published:true。
   - 未掲載は title だけ書き、published:false（q/a/o は不要）。
   - テーマは config.json の themes の id から選ぶ。
3. `python scripts/validate.py` で検査（キー重複・テーマ名・掲載なのに本文空・一覧表との件数照合）。
4. `python build.py` で docs/ を再生成（または GitHub Actions が自動実行）。
5. 既存の号ファイルには触らない。差分は新ファイルだけ。

> 元データは PDF より会議録・確定テキストの方が正確。可能なら事務局に確定テキスト（または会議録）の提供を依頼する。
