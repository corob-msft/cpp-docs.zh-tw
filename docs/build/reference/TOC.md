# [C/C++ 建置參考](c-cpp-building-reference.md)
# [編譯 C/C++ 程式](compiling-a-c-cpp-program.md)
## [設定編譯器選項](setting-compiler-options.md)
### [編譯器命令列語法](compiler-command-line-syntax.md)
#### [CL 檔名語法](cl-filename-syntax.md)
#### [CL 選項的順序](order-of-cl-options.md)
#### [cl.exe 的傳回值](return-value-of-cl-exe.md)
### [CL 環境變數](cl-environment-variables.md)
### [CL 命令檔](cl-command-files.md)
### [快速編譯](fast-compilation.md)
### [CL 叫用連結器](cl-invokes-the-linker.md)
## [編譯器選項](compiler-options.md)
### [依分類排列的編譯器選項](compiler-options-listed-by-category.md)
### [依字母順序排列的編譯器選項](compiler-options-listed-alphabetically.md)
#### [@ (指定編譯器回應檔)](at-specify-a-compiler-response-file.md)
#### [/AI (指定中繼資料目錄)](ai-specify-metadata-directories.md)
#### [/analyze (程式碼分析)](analyze-code-analysis.md)
#### [/arch (最小 CPU 架構)](arch-minimum-cpu-architecture.md)
##### [/arch (x86)](arch-x86.md)
##### [/arch (x64)](arch-x64.md)
##### [/arch (ARM)](arch-arm.md)
#### [/await (啟用協同程式支援)](await-enable-coroutine-support.md)
#### [/bigobj (增加 .Obj 檔中的區段數目)](bigobj-increase-number-of-sections-in-dot-obj-file.md)
#### [/C (前置處理時保留註解)](c-preserve-comments-during-preprocessing.md)
#### [/c (編譯而不連結)](c-compile-without-linking.md)
#### [/cgthreads (程式碼產生執行緒)](cgthreads-code-generation-threads.md)
#### [/clr (通用語言執行平台編譯)](clr-common-language-runtime-compilation.md)
##### [/clr 限制](clr-restrictions.md)
#### [/constexpr (控制 constexpr 評估)](constexpr-control-constexpr-evaluation.md)
#### [/D (前置處理器定義)](d-preprocessor-definitions.md)
#### [/diagnostics (編譯器診斷選項)](diagnostics-compiler-diagnostic-options.md)
#### [/doc (處理文件註解) (C/C++)](doc-process-documentation-comments-c-cpp.md)
#### [/E (前置處理至 stdout)](e-preprocess-to-stdout.md)
#### [/EH (例外狀況處理模型)](eh-exception-handling-model.md)
#### [/EP (前置處理至 stdout 不加 #line 指示詞)](ep-preprocess-to-stdout-without-hash-line-directives.md)
#### [/errorReport (回報編譯器內部錯誤)](errorreport-report-internal-compiler-errors.md)
#### [/execution/charset (設定執行字元集)](execution-charset-set-execution-character-set.md)
#### [/F (設定堆疊大小)](f-set-stack-size.md)
#### [輸出檔 (/F) 選項](output-file-f-options.md)
##### [/FA、/Fa (清單檔)](fa-fa-listing-file.md)
##### [指定路徑名稱](specifying-the-pathname.md)
##### [/FD (IDE 最少重建)](fd-ide-minimal-rebuild.md)
##### [/Fd (程式資料庫檔案名稱)](fd-program-database-file-name.md)
##### [/Fe (命名 EXE 檔案)](fe-name-exe-file.md)
##### [/Fi (前置處理輸出檔名稱)](fi-preprocess-output-file-name.md)
##### [/FI (命名強制的包含檔)](fi-name-forced-include-file.md)
##### [/Fm (命名對應檔)](fm-name-mapfile.md)
##### [/Fo (目的檔名稱)](fo-object-file-name.md)
##### [/Fp (命名 .Pch 檔案)](fp-name-dot-pch-file.md)
##### [/FR、/Fr (建立 .Sbr 檔案)](fr-fr-create-dot-sbr-file.md)
##### [/FU (命名強制的 #using 檔案)](fu-name-forced-hash-using-file.md)
##### [/Fx (合併插入的程式碼)](fx-merge-injected-code.md)
#### [/favor (專為架構最佳化)](favor-optimize-for-architecture-specifics.md)
#### [/FC (診斷中原始程式碼檔的完整路徑)](fc-full-path-of-source-code-file-in-diagnostics.md)
#### [/fp (指定浮點數行為)](fp-specify-floating-point-behavior.md)
##### [Microsoft Visual C++ 浮點最佳化](floating-point-optimization.md)
#### [/FS (強制同步 PDB 寫入)](fs-force-synchronous-pdb-writes.md)
#### [/GA (針對 Windows 應用程式最佳化)](ga-optimize-for-windows-application.md)
#### [/Gd、/Gr、/Gv、/Gz (呼叫慣例)](gd-gr-gv-gz-calling-convention.md)
#### [/Ge (啟用堆疊探查)](ge-enable-stack-probes.md)
#### [/GF (消除重複字串)](gf-eliminate-duplicate-strings.md)
#### [/GH (啟用 _pexit 攔截函式)](gh-enable-pexit-hook-function.md)
#### [/Gh (啟用 _penter 攔截函式)](gh-enable-penter-hook-function.md)
#### [/GL (整個程式最佳化)](gl-whole-program-optimization.md)
#### [/Gm (啟用最少重建)](gm-enable-minimal-rebuild.md)
#### [/GR (啟用執行階段類型資訊)](gr-enable-run-time-type-information.md)
#### [/GS (緩衝區安全性檢查)](gs-buffer-security-check.md)
#### [/Gs (控制堆疊檢查呼叫)](gs-control-stack-checking-calls.md)
#### [/guard (啟用控制流程防護)](guard-enable-control-flow-guard.md)
#### [/GT (支援 Fiber-Safe 執行緒區域儲存區)](gt-support-fiber-safe-thread-local-storage.md)
#### [/Gw (最佳化全域資料)](gw-optimize-global-data.md)
#### [/GX (啟用例外狀況處理)](gx-enable-exception-handling.md)
#### [/Gy (啟用函式階層連結)](gy-enable-function-level-linking.md)
#### [/GZ (啟用堆疊框架執行階段錯誤檢查)](gz-enable-stack-frame-run-time-error-checking.md)
#### [/H (限制外部名稱的長度)](h-restrict-length-of-external-names.md)
#### [/HELP (編譯器命令列說明)](help-compiler-command-line-help.md)
#### [/homeparams (將暫存器參數複製到堆疊)](homeparams-copy-register-parameters-to-stack.md)
#### [/hotpatch (建立可線上修補的映像)](hotpatch-create-hotpatchable-image.md)
#### [/I (其他 Include 目錄)](i-additional-include-directories.md)
#### [/J (預設 char 類型為 unsigned)](j-default-char-type-is-unsigned.md)
#### [/JMC (Just My Code 偵錯)](jmc.md)
#### [/kernel (建立核心模式二進位檔)](kernel-create-kernel-mode-binary.md)
#### [/link (傳遞選項給連結器)](link-pass-options-to-linker.md)
#### [/LN (建立 MSIL 模組)](ln-create-msil-module.md)
#### [/MD、/MT、/LD (使用執行階段程式庫)](md-mt-ld-use-run-time-library.md)
#### [/MP (使用多處理序建置)](mp-build-with-multiple-processes.md)
#### [/nologo (隱藏程式啟始資訊) (C/C++)](nologo-suppress-startup-banner-c-cpp.md)
#### [/O 選項 (最佳化程式碼)](o-options-optimize-code.md)
##### [/O1、/O2 (最小大小、最快速度)](o1-o2-minimize-size-maximize-speed.md)
##### [/Ob (內嵌函式展開)](ob-inline-function-expansion.md)
##### [/Od (停用 (偵錯))](od-disable-debug.md)
##### [/Og (全域最佳化)](og-global-optimizations.md)
##### [/Oi (產生內建函式)](oi-generate-intrinsic-functions.md)
##### [/Os、/Ot (偏好小的程式碼、偏好快的程式碼)](os-ot-favor-small-code-favor-fast-code.md)
##### [/Ox (啟用大多數速度最佳化)](ox-full-optimization.md)
##### [/Oy (框架指標省略)](oy-frame-pointer-omission.md)
#### [/openmp (啟用 OpenMP 2.0 支援)](openmp-enable-openmp-2-0-support.md)
#### [/P (前置處理至檔案)](p-preprocess-to-a-file.md)
#### [/permissive- (標準一致性)](permissive-standards-conformance.md)
#### [/Q 選項 (低階運算)](q-options-low-level-operations.md)
##### [/Qfast_transcendentals (強制快速超越函式)](qfast-transcendentals-force-fast-transcendentals.md)
##### [/QIfist (隱藏 _ftol)](qifist-suppress-ftol.md)
##### [/Qimprecise_fwaits (移除 Try 區域內的 fwaits)](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md)
##### [/Qpar (自動平行化工具)](qpar-auto-parallelizer.md)
##### [/Qpar-report (自動平行化工具報告層級)](qpar-report-auto-parallelizer-reporting-level.md)
##### [/Qsafe_fp_loads](qsafe-fp-loads.md)
##### [/Qspectre](qspectre.md)
##### [/Qvec-report (自動向量化工具報告層級)](qvec-report-auto-vectorizer-reporting-level.md)
#### [/RTC (執行階段錯誤檢查)](rtc-run-time-error-checks.md)
#### [/sdl (啟用其他安全性檢查)](sdl-enable-additional-security-checks.md)
#### [/showIncludes (列示包含檔)](showincludes-list-include-files.md)
#### [/source-charset (設定來源字元集)](source-charset-set-source-character-set.md)
#### [/std (指定語言標準版本)](std-specify-language-standard-version.md)
#### [/Tc、/Tp、/TC、/TP (指定原始程式檔類型)](tc-tp-tc-tp-specify-source-file-type.md)
#### [/U、/u (取消定義符號)](u-u-undefine-symbols.md)
#### [/utf-8 (將來源和可執行檔字元集設定為 UTF-8)](utf-8-set-source-and-executable-character-sets-to-utf-8.md)
#### [/V (版本號碼)](v-version-number.md)
#### [/validate-charset (驗證字元是否相容)](validate-charset-validate-for-compatible-characters.md)
#### [/vd (停用建構替代)](vd-disable-construction-displacements.md)
#### [/vmb、/vmg (表示方法)](vmb-vmg-representation-method.md)
#### [/vmm、/vms、/vmv (一般用途表示)](vmm-vms-vmv-general-purpose-representation.md)
#### [/volatile (volatile 關鍵字轉譯)](volatile-volatile-keyword-interpretation.md)
#### [/w、/W0、/W1、/W2、/W3、/W4、/w1、/w2、/w3、/w4、/Wall、/wd、/we、/wo、/Wv、/WX (警告層級)](compiler-option-warning-level.md)
#### [/WL (啟用一行診斷)](wl-enable-one-line-diagnostics.md)
#### [/Wp64 (偵測 64 位元可移植性問題)](wp64-detect-64-bit-portability-issues.md)
#### [/X (忽略標準 Include 路徑)](x-ignore-standard-include-paths.md)
#### [/Y (先行編譯標頭檔)](y-precompiled-headers.md)
##### [/Y- (忽略先行編譯標頭檔選項)](y-ignore-precompiled-header-options.md)
##### [/Yc (建立先行編譯標頭檔)](yc-create-precompiled-header-file.md)
##### [/Yd (將偵錯資訊置入目的檔)](yd-place-debug-information-in-object-file.md)
##### [/Yl (插入偵錯程式庫的 PCH 參考)](yl-inject-pch-reference-for-debug-library.md)
##### [/Yu (使用先行編譯標頭檔)](yu-use-precompiled-header-file.md)
#### [/Z7、/Zi、/ZI (偵錯資訊格式)](z7-zi-zi-debug-information-format.md)
#### [/Za、/Ze (停用語言延伸模組)](za-ze-disable-language-extensions.md)
##### [Microsoft 對 C 和 C++ 的延伸模組](microsoft-extensions-to-c-and-cpp.md)
#### [/Zc (一致性)](zc-conformance.md)
##### [/Zc:alignedNew (C++17 超越對齊配置)](zc-alignednew.md)
##### [/Zc:auto (推算變數類型)](zc-auto-deduce-variable-type.md)
##### [/Zc:__cplusplus (啟用已更新的 __cplusplus macro)](zc-cplusplus.md)
##### [/Zc:externConstexpr (啟用 extern constexpr 變數)](zc-externconstexpr.md)
##### [/Zc:forScope (強制 for 迴圈範圍中的一致性)](zc-forscope-force-conformance-in-for-loop-scope.md)
##### [/Zc:implicitNoexcept (隱含的例外狀況規範)](zc-implicitnoexcept-implicit-exception-specifiers.md)
##### [/Zc:inline (移除未參考的 COMDAT)](zc-inline-remove-unreferenced-comdat.md)
##### [/Zc:noexceptTypes (C++17 noexcept 規則)](zc-noexcepttypes.md)
##### [/Zc:referenceBinding (強制執行參考繫結規則)](zc-referencebinding-enforce-reference-binding-rules.md)
##### [/Zc:rvalueCast (強制執行類型轉換規則)](zc-rvaluecast-enforce-type-conversion-rules.md)
##### [/Zc:sizedDealloc (啟用調整大小後的全域解除配置函式)](zc-sizeddealloc-enable-global-sized-dealloc-functions.md)
##### [/Zc:strictStrings (停用字串常值類型轉換)](zc-strictstrings-disable-string-literal-type-conversion.md)
##### [/Zc:ternary (強制執行條件運算子規則)](zc-ternary.md)
##### [/Zc:threadSafeInit (安全執行緒區域靜態變數初始設定)](zc-threadsafeinit-thread-safe-local-static-initialization.md)
##### [/Zc:throwingNew (假設擲回運算子 new)](zc-throwingnew-assume-operator-new-throws.md)
##### [/Zc:trigraphs (三併詞替代)](zc-trigraphs-trigraphs-substitution.md)
##### [/Zc:twoPhase- (停用兩階段名稱查閱)](zc-twophase.md)
##### [/Zc:wchar_t (wchar_t 是原生類型)](zc-wchar-t-wchar-t-is-native-type.md)
#### [/Zf (PDB 產生速度加快)](zf.md)
#### [/Zg (產生函式原型)](zg-generate-function-prototypes.md)
#### [/Zl (省略預設程式庫名稱)](zl-omit-default-library-name.md)
#### [/Zm (指定先行編譯標頭檔的記憶體配置上限)](zm-specify-precompiled-header-memory-allocation-limit.md)
#### [/Zo (增強最佳化的偵錯)](zo-enhance-optimized-debugging.md)
#### [/Zp (結構成員對齊)](zp-struct-member-alignment.md)
#### [/Zs (僅檢查語法)](zs-syntax-check-only.md)
#### [/ZW (Windows 執行階段編譯)](zw-windows-runtime-compilation.md)
## [建立先行編譯標頭檔](creating-precompiled-header-files.md)
## [編譯器和連結器中的 Unicode 支援](unicode-support-in-the-compiler-and-linker.md)
# [連結](linking.md)
## [設定連結器選項](setting-linker-options.md)
### [連結器命令列語法](linker-command-line-syntax.md)
### [LINK 命令檔](link-command-files.md)
### [LINK 環境變數](link-environment-variables.md)
## [連結器選項](linker-options.md)
### [編譯器控制的 LINK 選項](compiler-controlled-link-options.md)
### [LINK 輸入檔](link-input-files.md)
#### [.Obj 檔作為連結器輸入](dot-obj-files-as-linker-input.md)
#### [.netmodule 檔作為連結器輸入](netmodule-files-as-linker-input.md)
##### [選擇 .netmodule 輸入檔的格式](choosing-the-format-of-netmodule-input-files.md)
#### [.Lib 檔作為連結器輸入](dot-lib-files-as-linker-input.md)
#### [.Exp 檔作為連結器輸入](dot-exp-files-as-linker-input.md)
#### [.Def 檔作為連結器輸入](dot-def-files-as-linker-input.md)
#### [.Pdb 檔作為連結器輸入](dot-pdb-files-as-linker-input.md)
#### [.Res 檔作為連結器輸入](dot-res-files-as-linker-input.md)
#### [.Exe 檔作為連結器輸入](dot-exe-files-as-linker-input.md)
#### [.Txt 檔作為連結器輸入](dot-txt-files-as-linker-input.md)
#### [.Ilk 檔作為連結器輸入](dot-ilk-files-as-linker-input.md)
### [LINK 輸出](link-output.md)
### [保留字](reserved-words.md)
### [@ (指定連結器回應檔)](at-specify-a-linker-response-file.md)
### [/ALIGN (區段記憶體對齊)](align-section-alignment.md)
### [/ALLOWBIND (防止 DLL 繫結)](allowbind-prevent-dll-binding.md)
### [/ALLOWISOLATION (資訊清單查閱)](allowisolation-manifest-lookup.md)
### [/APPCONTAINER (UWP/Microsoft Store 應用程式)](appcontainer-windows-store-app.md)
### [/ASSEMBLYDEBUG (新增 DebuggableAttribute)](assemblydebug-add-debuggableattribute.md)
### [/ASSEMBLYLINKRESOURCE (連結到 .NET Framework 資源)](assemblylinkresource-link-to-dotnet-framework-resource.md)
### [/ASSEMBLYMODULE (將 MSIL 模組新增至組件)](assemblymodule-add-a-msil-module-to-the-assembly.md)
### [/ASSEMBLYRESOURCE (內嵌 Managed 資源)](assemblyresource-embed-a-managed-resource.md)
### [/BASE (基底位址)](base-base-address.md)
### [/CETCOMPAT (控制流程強制技術相容)](cetcompat.md)
### [/CGTHREADS (編譯器執行緒)](cgthreads-compiler-threads.md)
### [/CLRIMAGETYPE (指定 CLR 映像類型)](clrimagetype-specify-type-of-clr-image.md)
### [/CLRSUPPORTLASTERROR (保留最後的 PInvoke 呼叫錯誤碼)](clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls.md)
### [/CLRTHREADATTRIBUTE (設定 CLR 執行緒屬性)](clrthreadattribute-set-clr-thread-attribute.md)
### [/CLRUNMANAGEDCODECHECK (移除 SuppressUnmanagedCodeSecurityAttribute)](clrunmanagedcodecheck-add-suppressunmanagedcodesecurityattribute.md)
### [/DEBUG (產生偵錯資訊)](debug-generate-debug-info.md)
### [/DEBUGTYPE (偵錯資訊選項)](debugtype-debug-info-options.md)
### [/DEF (指定模組定義檔)](def-specify-module-definition-file.md)
### [/DEFAULTLIB (指定預設程式庫)](defaultlib-specify-default-library.md)
### [/DELAY (延遲載入匯入設定)](delay-delay-load-import-settings.md)
### [/DELAYLOAD (延遲載入匯入)](delayload-delay-load-import.md)
### [/DELAYSIGN (部分簽署組件)](delaysign-partially-sign-an-assembly.md)
### [/DEPENDENTLOADFLAG (設定預設相依負載旗標)](dependentloadflag.md)
### [/DLL (建置 DLL)](dll-build-a-dll.md)
### [/DRIVER (Windows NT 核心模式驅動程式)](driver-windows-nt-kernel-mode-driver.md)
### [/DYNAMICBASE (使用位址空間配置隨機載入)](dynamicbase-use-address-space-layout-randomization.md)
### [/ENTRY (進入點符號)](entry-entry-point-symbol.md)
### [/ERRORREPORT (回報內部連結器錯誤)](errorreport-report-internal-linker-errors.md)
### [/EXPORT (匯出函式)](export-exports-a-function.md)
### [/FILEALIGN (對齊檔案中的區段)](filealign.md)
### [/FIXED (固定基底位址)](fixed-fixed-base-address.md)
### [/FORCE (強制檔案輸出)](force-force-file-output.md)
### [/FUNCTIONPADMIN (建立可線上修補的映像)](functionpadmin-create-hotpatchable-image.md)
### [/GENPROFILE、/FASTGENPROFILE (產生程式碼剖析檢測組建)](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)
### [/GUARD (啟用防護檢查)](guard-enable-guard-checks.md)
### [/HEAP (設定堆積大小)](heap-set-heap-size.md)
### [/HIGHENTROPYVA (支援 64 位元 ASLR)](highentropyva-support-64-bit-aslr.md)
### [/IDLOUT (命名 MIDL 輸出檔)](idlout-name-midl-output-files.md)
### [/IGNORE (忽略特定的警告)](ignore-ignore-specific-warnings.md)
### [/IGNOREIDL (不要將屬性處理至 MIDL 中)](ignoreidl-don-t-process-attributes-into-midl.md)
### [/IMPLIB (命名匯入程式庫)](implib-name-import-library.md)
### [/INCLUDE (強制符號參考)](include-force-symbol-references.md)
### [/INCREMENTAL (以累加方式連結)](incremental-link-incrementally.md)
### [/INTEGRITYCHECK (需要簽章檢查)](integritycheck-require-signature-check.md)
### [/KEYCONTAINER (指定金鑰容器以簽署組件)](keycontainer-specify-a-key-container-to-sign-an-assembly.md)
### [/KEYFILE (指定金鑰或金鑰組以簽署組件)](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)
### [/LARGEADDRESSAWARE (處理大型記憶體位址)](largeaddressaware-handle-large-addresses.md)
### [/LIBPATH (其他 Libpath)](libpath-additional-libpath.md)
### [/LTCG (連結時間產生程式碼)](ltcg-link-time-code-generation.md)
### [/MACHINE (指定目標平台)](machine-specify-target-platform.md)
### [/MANIFEST (建立並存組件資訊清單)](manifest-create-side-by-side-assembly-manifest.md)
### [/MANIFESTDEPENDENCY (指定資訊清單相依性)](manifestdependency-specify-manifest-dependencies.md)
### [/MANIFESTFILE (命名資訊清單檔)](manifestfile-name-manifest-file.md)
### [/MANIFESTINPUT (指定資訊清單輸入)](manifestinput-specify-manifest-input.md)
### [/MANIFESTUAC (將 UAC 資訊內嵌在資訊清單中)](manifestuac-embeds-uac-information-in-manifest.md)
### [/MAP (產生對應檔)](map-generate-mapfile.md)
### [/MAPINFO (將資訊包括在對應檔中)](mapinfo-include-information-in-mapfile.md)
### [/MERGE (結合區段)](merge-combine-sections.md)
### [/MIDL (指定 MIDL 命令列選項)](midl-specify-midl-command-line-options.md)
### [/NATVIS (將 Natvis 加入 PDB)](natvis-add-natvis-to-pdb.md)
### [/NOASSEMBLY (建立 MSIL 模組)](noassembly-create-a-msil-module.md)
### [/NODEFAULTLIB (忽略程式庫)](nodefaultlib-ignore-libraries.md)
### [/NOENTRY (沒有進入點)](noentry-no-entry-point.md)
### [/NOLOGO (隱藏程式啟始資訊) (連結器)](nologo-suppress-startup-banner-linker.md)
### [/NXCOMPAT (與資料執行防止相容)](nxcompat-compatible-with-data-execution-prevention.md)
### [/OPT (最佳化)](opt-optimizations.md)
### [/ORDER (依序置放函式)](order-put-functions-in-order.md)
### [/OUT (輸出檔名稱)](out-output-file-name.md)
### [/PDB (使用程式資料庫)](pdb-use-program-database.md)
### [/PDBALTPATH (使用替代 PDB 路徑)](pdbaltpath-use-alternate-pdb-path.md)
### [/PDBSTRIPPED (移除專用符號)](pdbstripped-strip-private-symbols.md)
### [/PGD (指定特性指引最佳化資訊庫)](pgd-specify-database-for-profile-guided-optimizations.md)
### [/POGOSAFEMODE](../../build/reference/pogosafemode-linker-option.md)
### [/PROFILE (效能工具分析工具)](profile-performance-tools-profiler.md)
### [/RELEASE (設定總和檢查碼)](release-set-the-checksum.md)
### [/SAFESEH (映像擁有安全例外狀況處理常式)](safeseh-image-has-safe-exception-handlers.md)
### [/SECTION (指定區段屬性)](section-specify-section-attributes.md)
### [/SOURCELINK (在 PDB 中納入 Sourcelink 檔案)](sourcelink.md)
### [/STACK (堆疊配置)](stack-stack-allocations.md)
### [/STUB (MS-DOS Stub 檔名稱)](stub-ms-dos-stub-file-name.md)
### [/SUBSYSTEM (指定子系統)](subsystem-specify-subsystem.md)
### [/SWAPRUN (將連結器輸出載入至分頁檔)](swaprun-load-linker-output-to-swap-file.md)
### [/TLBID (指定 TypeLib 的資源識別碼)](tlbid-specify-resource-id-for-typelib.md)
### [/TLBOUT (命名 .TLB 檔)](tlbout-name-dot-tlb-file.md)
### [/TSAWARE (建立終端伺服器感知應用程式)](tsaware-create-terminal-server-aware-application.md)
### [/USEPROFILE](../../build/reference/useprofile.md)
### [/VERBOSE (列印進度訊息)](verbose-print-progress-messages.md)
### [/VERSION (版本資訊)](version-version-information.md)
### [/WHOLEARCHIVE (包括所有程式庫目的檔)](wholearchive-include-all-library-object-files.md)
### [/WINMD (產生 Windows 中繼資料)](winmd-generate-windows-metadata.md)
### [/WINMDFILE (指定 winmd 檔案)](winmdfile-specify-winmd-file.md)
### [/WINMDKEYFILE (指定 winmd 金鑰檔)](winmdkeyfile-specify-winmd-key-file.md)
### [/WINMDKEYCONTAINER (指定金鑰容器)](winmdkeycontainer-specify-key-container.md)
### [/WINMDDELAYSIGN (部分簽署 winmd)](winmddelaysign-partially-sign-a-winmd.md)
### [/WX (將連結器警告視為錯誤)](wx-treat-linker-warnings-as-errors.md)
## [模組定義檔 (.Def)](module-definition-dot-def-files.md)
### [模組定義陳述式的規則](rules-for-module-definition-statements.md)
#### [EXPORTS](exports.md)
#### [LIBRARY](library.md)
#### [HEAPSIZE](heapsize.md)
#### [NAME (C/C++)](name-c-cpp.md)
#### [SECTIONS (C/C++)](sections-c-cpp.md)
#### [STACKSIZE](stacksize.md)
#### [STUB](stub.md)
#### [VERSION (C/C++)](version-c-cpp.md)
## [延遲載入 DLL 的連結器支援](linker-support-for-delay-loaded-dlls.md)
### [指定要延遲載入的 DLL](specifying-dlls-to-delay-load.md)
### [明確卸載延遲載入的 DLL](explicitly-unloading-a-delay-loaded-dll.md)
### [繫結匯入](binding-imports.md)
### [載入延遲載入 DLL 的所有匯入](loading-all-imports-for-a-delay-loaded-dll.md)
### [錯誤處理和通知](error-handling-and-notification.md)
#### [通知攔截](notification-hooks.md)
#### [失敗攔截](failure-hooks.md)
#### [例外狀況 (C/C++)](exceptions-c-cpp.md)
### [傾印延遲載入的匯入](dumping-delay-loaded-imports.md)
### [延遲載入 DLL 的條件約束](constraints-of-delay-loading-dlls.md)
### [了解協助協助程式函式](understanding-the-helper-function.md)
#### [Visual C++ 6.0 之後 DLL 延遲載入協助程式函式的變更](changes-in-the-dll-delayed-loading-helper-function-since-visual-cpp-6-0.md)
#### [呼叫慣例、參數和傳回型別](calling-conventions-parameters-and-return-type.md)
#### [結構和常數定義](structure-and-constant-definitions.md)
#### [計算需要的值](calculating-necessary-values.md)
#### [卸載延遲載入的 DLL](unloading-a-delay-loaded-dll.md)
### [開發您自己的協助程式函式](developing-your-own-helper-function.md)
# [發行組建](release-builds.md)
## [如何：建立發行組建](how-to-create-a-release-build.md)
## [建立發行組建時的常見問題](common-problems-when-creating-a-release-build.md)
## [解決發行組建的問題](fixing-release-build-problems.md)
### [使用 VERIFY 取代 ASSERT](using-verify-instead-of-assert.md)
### [使用偵錯組建檢查記憶體覆寫](using-the-debug-build-to-check-for-memory-overwrite.md)
### [如何：偵錯發行組建](how-to-debug-a-release-build.md)
### [檢查記憶體覆寫](checking-for-memory-overwrites.md)
# [最佳化程式碼](optimizing-your-code.md)
## [最佳化 Pragma 和關鍵字](optimization-pragmas-and-keywords.md)
## [改善編譯器輸送量](improving-compiler-throughput.md)
## [浮點數會失去精確度的原因](why-floating-point-numbers-may-lose-precision.md)
### [IEEE 浮點表示](ieee-floating-point-representation.md)
## [改善時間關鍵程式碼的秘訣](tips-for-improving-time-critical-code.md)
## [使用不帶 () 的函式名稱不會產生程式碼](using-function-name-without-parens-produces-no-code.md)
## [最佳化最佳做法](optimization-best-practices.md)
# [C/C++ 建置工具](c-cpp-build-tools.md)
## [BSCMAKE 參考](bscmake-reference.md)
### [建置瀏覽資訊檔：概觀](building-browse-information-files-overview.md)
### [建置 .Bsc 檔](building-a-dot-bsc-file.md)
#### [建立 .Sbr 檔](creating-an-dot-sbr-file.md)
#### [BSCMAKE 如何建置 .Bsc 檔](how-bscmake-builds-a-dot-bsc-file.md)
### [BSCMAKE 命令列](bscmake-command-line.md)
### [BSCMAKE 命令檔 (回應檔)](bscmake-command-file-response-file.md)
### [BSCMAKE 選項](bscmake-options.md)
### [BSCMAKE 結束代碼](bscmake-exit-codes.md)
## [LIB 參考](lib-reference.md)
### [LIB 概觀](overview-of-lib.md)
#### [如何：在 Visual Studio 開發環境中設定 LIB.EXE 選項](how-to-set-lib-exe-options-in-the-visual-studio-development-environment.md)
#### [LIB 輸入檔](lib-input-files.md)
#### [LIB 輸出檔](lib-output-files.md)
#### [其他 LIB 輸出](other-lib-output.md)
#### [程式庫結構](structure-of-a-library.md)
### [執行 LIB](running-lib.md)
### [管理程式庫](managing-a-library.md)
### [擷取程式庫成員](extracting-a-library-member.md)
### [與匯入程式庫和匯出檔案一起使用](working-with-import-libraries-and-export-files.md)
#### [建置匯入程式庫和匯出檔案](building-an-import-library-and-export-file.md)
#### [使用匯入程式庫和匯出檔案](using-an-import-library-and-export-file.md)
## [EDITBIN 參考](editbin-reference.md)
### [EDITBIN 命令列](editbin-command-line.md)
### [EDITBIN 選項](editbin-options.md)
#### [/ALLOWISOLATION](allowisolation.md)
#### [/ALLOWBIND](allowbind.md)
#### [/APPCONTAINER](appcontainer.md)
#### [/BIND](bind.md)
#### [/DYNAMICBASE](dynamicbase.md)
#### [/ERRORREPORT (editbin.exe)](errorreport-editbin-exe.md)
#### [/HEAP](heap.md)
#### [/HIGHENTROPYVA](highentropyva.md)
#### [/INTEGRITYCHECK](integritycheck.md)
#### [/LARGEADDRESSAWARE](largeaddressaware.md)
#### [/NOLOGO (EDITBIN)](nologo-editbin.md)
#### [/NXCOMPAT](nxcompat.md)
#### [/REBASE](rebase.md)
#### [/RELEASE](release.md)
#### [/SECTION (EDITBIN)](section-editbin.md)
#### [/STACK](stack.md)
#### [/SUBSYSTEM](subsystem.md)
#### [/SWAPRUN](swaprun.md)
#### [/TSAWARE](tsaware.md)
#### [/VERSION](version.md)
## [DUMPBIN 參考](dumpbin-reference.md)
### [DUMPBIN 命令列](dumpbin-command-line.md)
### [DUMPBIN 選項](dumpbin-options.md)
#### [/ALL](all.md)
#### [/ARCHIVEMEMBERS](archivemembers.md)
#### [/CLRHEADER](clrheader.md)
#### [/DEPENDENTS](dependents.md)
#### [/DIRECTIVES](directives.md)
#### [/DISASM](disasm.md)
#### [/ERRORREPORT (dumpbin.exe)](errorreport-dumpbin-exe.md)
#### [/EXPORTS](dash-exports.md)
#### [/FPO](fpo.md)
#### [/HEADERS](headers.md)
#### [/IMPORTS (DUMPBIN)](imports-dumpbin.md)
#### [/LINENUMBERS](linenumbers.md)
#### [/LINKERMEMBER](linkermember.md)
#### [/LOADCONFIG](loadconfig.md)
#### [/OUT (DUMPBIN)](out-dumpbin.md)
#### [/PDATA](pdata.md)
#### [/PDBPATH](pdbpath.md)
#### [/RANGE](range.md)
#### [/RAWDATA](rawdata.md)
#### [/RELOCATIONS](relocations.md)
#### [/SECTION (DUMPBIN)](section-dumpbin.md)
#### [/SUMMARY](summary.md)
#### [/SYMBOLS](symbols.md)
#### [/TLS](tls.md)
## [ERRLOOK 參考](errlook-reference.md)
### [值編輯控制項](value-edit-control.md)
### [錯誤訊息編輯控制項](error-message-edit-control.md)
### [模組按鈕](modules-button.md)
### [查詢按鈕](look-up-button.md)
## [裝飾名稱](decorated-names.md)
## [特性指引最佳化](profile-guided-optimizations.md)
### [特性指引最佳化的環境變數](environment-variables-for-profile-guided-optimizations.md)
### [PgoAutoSweep](pgoautosweep.md)
### [pgomgr](pgomgr.md)
### [pgosweep](pgosweep.md)
### [如何：將多個 PGO 設定檔合併至單一設定檔](how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)
### [效能和診斷中樞中的 Visual Studio 2013 PGO 增益集](profile-guided-optimization-in-the-performance-and-diagnostics-hub.md)
# [編譯器錯誤 C999 到 C2499](../../error-messages/compiler-errors-1/TOC.md)
# [編譯器錯誤 C2500 到 C3999](../../error-messages/compiler-errors-2/TOC.md)
# [編譯器警告](../../error-messages/compiler-warnings/TOC.md)
# [工具錯誤](../../error-messages/tool-errors/TOC.md)