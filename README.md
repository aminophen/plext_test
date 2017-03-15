# plext_test
このリポジトリは，pLaTeX 拡張パッケージ plext.sty の挙動を改善する私案を置いたものです．
現在は，array, tabular 環境や \parbox命令の垂直位置（追従できていません）について検討しています．

 * 現在の改善案 (plext-beta.sty) における表組・\parbox 命令の垂直位置
   * 周囲の組方向が横組かつ組方向が \<y>, \<z> 指定の場合
     * \[t] 指定のとき，一行目のベースラインが周囲のそれと一致（罫線の場合は和文ベースラインの位置）
     * \[c] 指定のとき，表組の中心が周囲の数式軸を通る（欧文ベースラインシフトの影響下）
     * \[b] 指定のとき，最終行のベースラインが周囲のそれと一致（罫線の場合は和文ベースラインの位置）
   * 周囲の組方向が横組かつ組方向が \<t> 指定の場合
     * \[t] 指定のとき，表組の上端が周囲の和文ベースラインと一致
     * \[c] 指定のとき，表組の中心が周囲の数式軸を通る（欧文ベースラインシフトの影響下）
     * \[b] 指定のとき，表組の下端が周囲の和文ベースラインと一致
   * 周囲の組方向が縦組かつ組方向が \<y> 指定の場合
     * \[t] 指定のとき，表組の上端が周囲の和文ベースラインと一致
     * \[c] 指定のとき，表組の中心が周囲の数式軸を通る（欧文ベースラインシフトの影響下）
     * \[b] 指定のとき，表組の下端が周囲の和文ベースラインと一致
   * 周囲の組方向が縦組かつ組方向が \<t> 指定の場合
     * \[t] 指定のとき，一行目のベースラインが周囲のそれと一致（罫線の場合は和文ベースラインの位置）
     * \[c] 指定のとき，表組の中心が周囲の数式軸を通る（欧文ベースラインシフトの影響下）†
     * \[b] 指定のとき，最終行のベースラインが周囲のそれと一致（罫線の場合は和文ベースラインの位置）
   * 周囲の組方向が縦組かつ組方向が \<z> 指定の場合
     * \[t] 指定のとき，表組の上端が周囲の和文ベースラインと一致★
     * \[c] 指定のとき，表組の中心が周囲の数式軸を通る（欧文ベースラインシフトの影響下）†
     * \[b] 指定のとき，表組の下端が周囲の和文ベースラインと一致★
 * 別の可能性
   * †: 中心が和文ベースラインを通る
   * ★: 罫線は欧文ベースラインの位置
   * 周囲の組方向が縦数式ディレクションのときは未検討
