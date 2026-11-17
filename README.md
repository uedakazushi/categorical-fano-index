# 圏論的Fano指数・Serre根・非可換変形

**2026-11-18 / v18。最初に[研究方針](00_research_plan.md)を読む。** このリポジトリは古典的・数値的・heart-exactな圏論的Fano指数と、Serre根が保つ非可換変形の研究正本である。次数9認識問題は別リポジトリ [nc-dp9](https://github.com/uedakazushi/nc-dp9) に分離した。

## 論文

- [Fano圏のSerre根と非可換変形](papers/fano_root_deformations.tex)：tilting bundle と HH¹=HH³=0 の下での全Artin根付き変形、有限反Serre商の同時持上げ、次数4の二部グラフ判定と形式的可換性、Hesse–Sklyaninの2方向の明示代数化、奇閉路のrank三平行移動格子。一般代数化・coherent群作用・独立新規性は未確定。
- [正規化された圏論的Fano指数](papers/normalized_fano_index.tex)：古典的Fano指数との比較、normとPicard巡回障害、surface-like数値格子、del Pezzo曲面の非正規化exact指数、数値根の非持上げ、三次元の整数値障害。数値根の存在を圏の実現や認識と混同しない。

## 研究継続資料

[詳細研究方針](research/research_plan.tex)、[補助研究ノート](research/fano_index_notes.tex)、[先行研究・接続と検証境界](research/fano_index_connections.md)、[再現手順](research/reproduce.md)。専用の6本の検算コードを収める。

現在の優先課題は、(1) Hesse–Sklyanin根付きmoduliの慣性とパラメータの同一視、(2) 次数4三角形の無限反Serre商の高次障害、(3) 次数4/Fermat三次の具体的代数化である。証明済み・条件付き・未完成・計算観察の区別は[研究方針](00_research_plan.md)に従う。

## 再現

```sh
python3 -m pip install -r requirements.txt
bash scripts/check.sh
latexmk -lualatex papers/fano_root_deformations.tex
latexmk -lualatex papers/normalized_fano_index.tex
latexmk -lualatex research/research_plan.tex
latexmk -lualatex research/fano_index_notes.tex
```

LuaLaTeX、latexmk、luatexja、Harano Aji、Python3、SymPyを使用。PDF/SyncTeX/中間物は `build/`、Gitはソースのみ追跡する。有限検算と抽象的存在定理の証明を区別する。

GitHub `main` を正本とし、旧版を含めない現行研究bundleは研究区切りに追加承諾なくLibraryへ保存してよい。既存Libraryファイルは明示指示なしには削除しない。
