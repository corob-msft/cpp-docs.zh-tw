---
title: "依分類排列的編譯器選項 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "編譯器選項, C++"
ms.assetid: c4750dcf-dba0-4229-99b6-45cdecc11729
caps.latest.revision: 64
caps.handback.revision: 64
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 依分類排列的編譯器選項
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

本文包含編譯器選項的分類清單。 如需依字母順序排列的清單，請參閱 [依字母順序排列的編譯器選項](../../build/reference/compiler-options-listed-alphabetically.md)。  
  
### 最佳化  
  
|選項|用途|  
|--------|--------|  
|[\/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md)|建立小型程式碼。|  
|[\/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)|建立快速程式碼。|  
|[\/Ob](../../build/reference/ob-inline-function-expansion.md)|控制內嵌展開。|  
|[\/Od](../../build/reference/od-disable-debug.md)|停用最佳化。|  
|[\/Og](../../build/reference/og-global-optimizations.md)|已取代。 使用全域最佳化。|  
|[\/Oi](../../build/reference/oi-generate-intrinsic-functions.md)|產生內建函式。|  
|[\/Os](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)|偏好小的程式碼。|  
|[\/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)|偏好快的程式碼。|  
|[\/Ox](../../build/reference/ox-full-optimization.md)|使用最大最佳化 \(\/Ob2gity \/Gs\)。|  
|[\/Oy](../../build/reference/oy-frame-pointer-omission.md)|省略框架指標。 \(僅限 x86\)|  
|[\/favor](../../build/reference/favor-optimize-for-architecture-specifics.md)|產生針對指定之結構或結構範圍進行最佳化的程式碼。|  
  
### 程式碼產生  
  
|選項|用途|  
|--------|--------|  
|[\/arch](../../build/reference/arch-x86.md)|在程式碼產生時使用 SSE 或 SSE2 指令。 \(僅限 x86\)|  
|[\/clr](../../build/reference/clr-common-language-runtime-compilation.md)|產生輸出檔案，以便在 Common Language Runtime 上執行。|  
|[\/EH](../../build/reference/eh-exception-handling-model.md)|指定例外狀況處理模型。|  
|[\/fp](../../build/reference/fp-specify-floating-point-behavior.md)|指定浮點行為。|  
|[\/GA](../../build/reference/ga-optimize-for-windows-application.md)|對 Windows 應用程式進行最佳化。|  
|[\/Gd](../../build/reference/gd-gr-gv-gz-calling-convention.md)|使用 `__cdecl` 呼叫慣例。 \(僅限 x86\)|  
|[\/Ge](../../build/reference/ge-enable-stack-probes.md)|已取代。 啟動堆疊探查。|  
|[\/GF](../../build/reference/gf-eliminate-duplicate-strings.md)|啟用字串共用。|  
|[\/Gh](../../build/reference/gh-enable-penter-hook-function.md)|呼叫攔截函式 `_penter`。|  
|[\/GH](../../build/reference/gh-enable-pexit-hook-function.md)|呼叫攔截函式 `_pexit`。|  
|[\/GL](../../build/reference/gl-whole-program-optimization.md)|啟用整個程式最佳化。|  
|[\/Gm](../../build/reference/gm-enable-minimal-rebuild.md)|啟用最少重建。|  
|[\/GR](../../build/reference/gr-enable-run-time-type-information.md)|啟用執行階段類型資訊 \(RTTI\)。|  
|[\/Gr](../../build/reference/gd-gr-gv-gz-calling-convention.md)|使用 `__fastcall` 呼叫慣例。 \(僅限 x86\)|  
|[\/GS](../../build/reference/gs-buffer-security-check.md)|檢查緩衝區安全性。|  
|[\/Gs](../../build/reference/gs-control-stack-checking-calls.md)|控制堆疊探查。|  
|[\/GT](../../build/reference/gt-support-fiber-safe-thread-local-storage.md)|對使用靜態執行緒區域儲存區所配置的資料支援 Fiber 安全性。|  
|[\/guard:cf](../../build/reference/guard-enable-control-flow-guard.md)|加入控制流程防護安全性檢查。|  
|[\/Gv](../../build/reference/gd-gr-gv-gz-calling-convention.md)|使用 `__vectorcall` 呼叫慣例。 \(僅限 x86 和 x64\)|  
|[\/Gw](../../build/reference/gw-optimize-global-data.md)|啟用整個程式全域資料最佳化。|  
|[\/GX](../../build/reference/gx-enable-exception-handling.md)|已取代。 啟用同步例外狀況處理。 改用 [\/EH](../../build/reference/eh-exception-handling-model.md)。|  
|[\/Gy](../../build/reference/gy-enable-function-level-linking.md)|啟用函式階層連結。|  
|[\/GZ](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md)|已取代。 啟用快速檢查。 \(與 [\/RTC1](../../build/reference/rtc-run-time-error-checks.md) 相同\)|  
|[\/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md)|使用 `__stdcall` 呼叫慣例。 \(僅限 x86\)|  
|[\/homeparams](../../build/reference/homeparams-copy-register-parameters-to-stack.md)|在函式進入時，強制暫存器中所傳遞的參數寫入至堆疊上的位置。 這個編譯器選項只適用於 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 編譯器 \(原生和跨平台編譯\)。|  
|[\/hotpatch](../../build/reference/hotpatch-create-hotpatchable-image.md)|建立可線上修補的影像。|  
|[\/Qfast\_transcendentals](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md)|產生快速超越函式。|  
|[QIfist](../../build/reference/qifist-suppress-ftol.md)|已取代。 在必須從浮點類型轉換為整數類型時，抑制對 Helper 函式 `_ftol` 的呼叫。 \(僅限 x86\)|  
|[\/Qimprecise\_fwaits](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md)|移除 `fwait` 區塊內的 `try` 命令。|  
|[\/Qpar](../../build/reference/qpar-auto-parallelizer.md)|啟用迴圈自動平行處理。|  
|[\/Qpar\-report](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md)|啟用自動平行處理的報告層級。|  
|[\/Qsafe\_fp\_loads](../../build/reference/qsafe-fp-loads.md)|使用浮點值的整數移動指令，並停用特定浮點數負載最佳化。|  
|[\/Qvec\-report \(自動向量化工具報告層級\)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md)|啟用自動向量化的報告層級。|  
|[\/RTC](../../build/reference/rtc-run-time-error-checks.md)|啟用執行階段錯誤檢查。|  
|[\/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md)|選取 volatile 關鍵字的解譯方式。|  
  
### 輸出檔  
  
|選項|用途|  
|--------|--------|  
|[\/doc](../../build/reference/doc-process-documentation-comments-c-cpp.md)|將文件註解處理成 XML 檔案。|  
|[\/FA](../../build/reference/fa-fa-listing-file.md)|設定組件清單檔。|  
|[\/Fa](../../build/reference/fa-fa-listing-file.md)|建立組件清單檔。|  
|[\/Fd](../../build/reference/fd-program-database-file-name.md)|重新命名程式資料庫檔案。|  
|[\/Fe](../../build/reference/fe-name-exe-file.md)|重新命名可執行檔。|  
|[\/Fi](../../build/reference/fi-preprocess-output-file-name.md)|指定前置處理過的輸出檔名稱。|  
|[\/Fm](../../build/reference/fm-name-mapfile.md)|建立對應檔 \(Mapfile\)。|  
|[\/Fo](../../build/reference/fo-object-file-name.md)|建立目的檔。|  
|[\/Fp](../../build/reference/fp-name-dot-pch-file.md)|指定先行編譯標頭檔的名稱。|  
|[\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) [\/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md)|產生瀏覽器檔案。|  
  
### 前置處理器  
  
|選項|用途|  
|--------|--------|  
|[\/AI](../../build/reference/ai-specify-metadata-directories.md)|指定一個要搜尋的目錄，以解析傳遞給 [\#using](../../preprocessor/hash-using-directive-cpp.md) 指示詞的檔案參考。|  
|[\/C](../../build/reference/c-preserve-comments-during-preprocessing.md)|在前置處理過程中保留註解。|  
|[\/D](../../build/reference/d-preprocessor-definitions.md)|定義常數和巨集。|  
|[\/E](../../build/reference/e-preprocess-to-stdout.md)|複製前置處理器輸出至標準輸出。|  
|[\/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)|複製前置處理器輸出至標準輸出。|  
|[\/FI](../../build/reference/fi-name-forced-include-file.md)|前置處理指定的包含檔。|  
|[\/FU](../../build/reference/fu-name-forced-hash-using-file.md)|強制使用某個檔案名稱，就如同其已傳遞給 [\#using](../../preprocessor/hash-using-directive-cpp.md) 指示詞一般。|  
|[\/Fx](../../build/reference/fx-merge-injected-code.md)|將插入的程式碼與原始程式檔合併。|  
|[\/I](../../build/reference/i-additional-include-directories.md)|搜尋包含檔的目錄。|  
|[\/P](../../build/reference/p-preprocess-to-a-file.md)|將前置處理器輸出寫入檔案。|  
|[\/U](../../build/reference/u-u-undefine-symbols.md)|移除某個預先定義巨集。|  
|[\/u](../../build/reference/u-u-undefine-symbols.md)|移除所有預先定義巨集。|  
|[\/X](../../build/reference/x-ignore-standard-include-paths.md)|忽略標準 Include 目錄。|  
  
### 語言  
  
|選項|用途|  
|--------|--------|  
|[\/openmp](../../build/reference/openmp-enable-openmp-2-0-support.md)|在原始程式碼中啟用 [\#pragma omp](../../preprocessor/omp.md)。|  
|[\/vd](../../build/reference/vd-disable-construction-displacements.md)|抑制或啟用隱藏的 `vtordisp` 類別成員。|  
|[\/vmb](../../build/reference/vmb-vmg-representation-method.md)|對指向成員的指標使用最佳基底。|  
|[\/vmg](../../build/reference/vmb-vmg-representation-method.md)|對指向成員的指標使用完整一般性。|  
|[\/vmm](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)|宣告多重繼承。|  
|[\/vms](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)|宣告單一繼承。|  
|[\/vmv](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)|宣告虛擬繼承。|  
|[\/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)|產生 C 7.0 相容的偵錯資訊。|  
|[\/Za](../../build/reference/za-ze-disable-language-extensions.md)|停用語言擴充功能。|  
|[\/Zc](../../build/reference/zc-conformance.md)|指定 [\/Ze](../../build/reference/za-ze-disable-language-extensions.md) 下的標準行為。|  
|[\/Ze](../../build/reference/za-ze-disable-language-extensions.md)|已取代。 啟用語言擴充功能。|  
|[\/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)|將偵錯資訊包括在與「編輯後繼續」相容的程式資料庫中。 \(僅限 x86\)|  
|[\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)|產生完整偵錯資訊。|  
|[\/Zl](../../build/reference/zl-omit-default-library-name.md)|從 .obj 檔案移除預設程式庫名稱。|  
|[\/Zp](../../build/reference/zp-struct-member-alignment.md) *n*|封裝結構成員。|  
|[\/Zs](../../build/reference/zs-syntax-check-only.md)|僅檢查語法。|  
|[\/ZW](../../build/reference/zw-windows-runtime-compilation.md)|產生要在 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]上執行的輸出檔案。|  
  
### 連結  
  
|選項|用途|  
|--------|--------|  
|[\/F](../../build/reference/f-set-stack-size.md)|設定堆疊大小。|  
|[\/LD](../../build/reference/md-mt-ld-use-run-time-library.md)|建立動態連結程式庫。|  
|[\/LDd](../../build/reference/md-mt-ld-use-run-time-library.md)|建立偵錯動態連結程式庫。|  
|[\/link](../../build/reference/link-pass-options-to-linker.md)|傳遞指定的選項給 LINK。|  
|[\/LN](../../build/reference/ln-create-msil-module.md)|建立 MSIL 模組。|  
|[\/MD](../../build/reference/md-mt-ld-use-run-time-library.md)|使用 MSVCRT.lib 編譯以建立多執行緒 DLL。|  
|[\/MDd](../../build/reference/md-mt-ld-use-run-time-library.md)|使用 MSVCRTD.lib 編譯以建立偵錯多執行緒 DLL。|  
|[\/MT](../../build/reference/md-mt-ld-use-run-time-library.md)|使用 LIBCMT.lib 編譯以建立多執行緒可執行檔。|  
|[\/MTd](../../build/reference/md-mt-ld-use-run-time-library.md)|使用 LIBCMTD.lib 編譯以建立偵錯多執行緒可執行檔。|  
  
### 先行編譯標頭  
  
|選項|用途|  
|--------|--------|  
|[\/Y\-](../../build/reference/y-ignore-precompiled-header-options.md)|忽略目前組建中所有其他先行編譯標頭編譯器選項。|  
|[\/Yc](../../build/reference/yc-create-precompiled-header-file.md)|建立先行編譯標頭檔。|  
|[\/Yd](../../build/reference/yd-place-debug-information-in-object-file.md)|將完整的偵錯資訊置於所有目的檔中。|  
|[\/Yu](../../build/reference/yu-use-precompiled-header-file.md)|在建置時使用先行編譯標頭檔。|  
  
### 其他  
  
|選項|用途|  
|--------|--------|  
|[\/?](../../build/reference/help-compiler-command-line-help.md)|列出編譯器選項。|  
|[@](../../build/reference/at-specify-a-compiler-response-file.md)|指定回應檔。|  
|[\/analyze](../../build/reference/analyze-code-analysis.md)|啟用程式碼分析。|  
|[\/bigobj](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md)|增加 .obj 檔案中可定址區段的數目。|  
|[\/c](../../build/reference/c-compile-without-linking.md)|編譯而不連結。|  
|[\/cgthreads](../../build/reference/cgthreads-code-generation-threads.md)|指定 cl.exe 執行緒的數目，以用於最佳化及程式碼產生。|  
|[\/errorReport](../../build/reference/errorreport-report-internal-compiler-errors.md)|可讓您直接提供內部編譯器錯誤 \(ICE\) 資訊給 Visual C\+\+ 團隊。|  
|[\/FC](../../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md)|在診斷文字中顯示傳遞給 cl.exe 的原始程式檔完整路徑。|  
|[\/FS](../../build/reference/fs-force-synchronous-pdb-writes.md)|強制寫入要透過 MSPDBSRV.EXE 序列化的程式資料庫 \(PDB\) 檔案。|  
|[\/H](../../build/reference/h-restrict-length-of-external-names.md)|已取代。 限制外部 \(公用\) 名稱的長度。|  
|[\/HELP](../../build/reference/help-compiler-command-line-help.md)|列出編譯器選項。|  
|[\/J](../../build/reference/j-default-char-type-is-unsigned.md)|變更預設 `char` 類型。|  
|[\/kernel](../../build/reference/kernel-create-kernel-mode-binary.md)|編譯器和連結器將會建立可以在 Windows 核心中執行的二進位檔。|  
|[\/MP](../../build/reference/mp-build-with-multiple-processes.md)|同時建置多重原始程式檔。|  
|[\/nologo](../../build/reference/nologo-suppress-startup-banner-c-cpp.md)|隱藏登入程式的啟始資訊。|  
|[\/sdl](../../build/reference/sdl-enable-additional-security-checks.md)|啟用其他安全性功能及警告。|  
|[\/showIncludes](../../build/reference/showincludes-list-include-files.md)|在編譯時顯示所有 Include 檔的清單。|  
|[\/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) [\/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)|指定 C 原始程式檔。|  
|[\/Tp](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) [\/TP](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)|指定 C\+\+ 原始程式檔。|  
|[\/V](../../build/reference/v-version-number.md)|已取代。 設定版本字串。|  
|[\/w](../../build/reference/compiler-option-warning-level.md)|停用所有警告。|  
|[\/W0, \/W1, \/W2, \/W3, \/W4](../../build/reference/compiler-option-warning-level.md)|設定輸出警告層級。|  
|[\/w1, \/w2, \/w3, \/w4](../../build/reference/compiler-option-warning-level.md)|為指定的警告設定警告層級。|  
|[\/Wall](../../build/reference/compiler-option-warning-level.md)|啟用所有警告，包括預設停用的警告。|  
|[\/wd](../../build/reference/compiler-option-warning-level.md)|停用指定的警告。|  
|[\/we](../../build/reference/compiler-option-warning-level.md)|將指定的警告視為錯誤。|  
|[\/WL](../../build/reference/wl-enable-one-line-diagnostics.md)|從命令列編譯 C\+\+ 原始程式碼時啟用一行錯誤和警告訊息診斷。|  
|[\/wo](../../build/reference/compiler-option-warning-level.md)|只顯示指定的警告一次。|  
|[\/Wp64](../../build/reference/wp64-detect-64-bit-portability-issues.md)|已過時。 偵測 64 位元可移植性問題。|  
|[\/Wv](../../build/reference/compiler-option-warning-level.md)|停用較新版編譯器所引入的警告。|  
|[\/WX](../../build/reference/compiler-option-warning-level.md)|將警告視為錯誤。|  
|[\/Yd](../../build/reference/yd-place-debug-information-in-object-file.md)|已取代。 將完整的偵錯資訊置於所有目的檔中。 改用 [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)。|  
|[\/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md)|在建立偵錯程式庫時插入 PCH 參考。|  
|[\/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)|指定先行編譯標頭的記憶體配置上限。|  
  
### 已取代及移除的編譯器選項  
  
|選項|用途|  
|--------|--------|  
|[\/clr:noAssembly](../../build/reference/clr-common-language-runtime-compilation.md)|已取代。 請改用 [\/LN \(建立 MSIL 模組\)](../../build/reference/ln-create-msil-module.md)。|  
|[\/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md)|已取代。 建立不包含本機變數的瀏覽資訊檔。|  
|[\/Ge](../../build/reference/ge-enable-stack-probes.md)|已取代。 啟動堆疊探查。 預設為開啟。|  
|[\/GX](../../build/reference/gx-enable-exception-handling.md)|已取代。 啟用同步例外狀況處理。 改用 [\/EH](../../build/reference/eh-exception-handling-model.md)。|  
|[\/GZ](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md)|已取代。 啟用快速檢查。 改用 [\/RTC1](../../build/reference/rtc-run-time-error-checks.md)。|  
|[\/H](../../build/reference/h-restrict-length-of-external-names.md)|已取代。 限制外部 \(公用\) 名稱的長度。|  
|[\/Og](../../build/reference/og-global-optimizations.md)|已取代。 使用全域最佳化。|  
|[QIfist](../../build/reference/qifist-suppress-ftol.md)|已取代。 曾用以指定如何從浮點型別轉換為整數型別。|  
|[\/V](../../build/reference/v-version-number.md)|已取代。 設定 obj 檔案版本字串。|  
|[\/Yd](../../build/reference/yd-place-debug-information-in-object-file.md)|已取代。 將完整的偵錯資訊置於所有目的檔中。 改用 [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)。|  
|[\/Zc:forScope\-](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)|已取代。 停用 For 迴圈範圍中的一致性。|  
|[\/Ze](../../build/reference/za-ze-disable-language-extensions.md)|已取代。 啟用語言擴充功能。|  
|[\/Zg](../../build/reference/zg-generate-function-prototypes.md)|已從 Visual C\+\+ 2015 移除。 產生函式原型。|  
  
## 請參閱  
 [C\/C\+\+ 建置參考](../../build/reference/c-cpp-building-reference.md)   
 [編譯器選項](../../build/reference/compiler-options.md)   
 [設定編譯器選項](../../build/reference/setting-compiler-options.md)