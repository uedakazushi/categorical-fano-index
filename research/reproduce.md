# 再現手順

2026-11-18 / v18。リポジトリのルートで実行する。論文2本と方針・補助ノートの計4つのTeX文書、専用検算6本。

## 必要環境と実行

Python3、SymPy（requirements.txt）、LuaLaTeX、latexmk、luatexja-fontspec、Harano Ajiフォント（フォント自体は配布しない）。

```sh
python3 -m pip install -r requirements.txt
bash scripts/check.sh
latexmk -lualatex papers/fano_root_deformations.tex
latexmk -lualatex papers/normalized_fano_index.tex
latexmk -lualatex research/research_plan.tex
latexmk -lualatex research/fano_index_notes.tex
```

`.latexmkrc` は出力・中間物を build/ に置き、SyncTeXは有効。VS CodeのLaTeX Workshop設定も用意。

検算はPicard整数格子、del Pezzo root、HH²指標、有限群平均、D5二部グラフ、量子PBW/Nakayama、Hesse指標とtriangle rank三格子を扱う。有限検算は圏論的存在定理・代数化・coherent関係の証明ではない。

論文の\input、\label、\ref、\citeの整合を scripts/verify_repository.py で検査する。TeXログとPDF描画は別にチェックする。現行bundleにはソース、必要な計算、可能なら組版した最終PDFだけを含め、旧版・buildログ・中間物を含めない。次数9認識の正本は別の nc-dp9。
