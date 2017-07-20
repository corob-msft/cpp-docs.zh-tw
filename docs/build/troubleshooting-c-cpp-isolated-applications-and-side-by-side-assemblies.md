---
title: "疑難排解 C/C++ 隔離應用程式和並存組件 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "隔離的應用程式疑難排解"
  - "並存組件疑難排解"
  - "Visual C++ 疑難排解"
ms.assetid: 3257257a-1f0b-4ede-8564-9277a7113a35
caps.latest.revision: 28
caps.handback.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 疑難排解 C/C++ 隔離應用程式和並存組件
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

如果找不到相依程式庫，則載入 C\/C\+\+ 應用程式可能會失敗。  本文將說明為什麼無法載入 C\/\+\+ 應用Ｃ程式的一些常見原因，並建議解決問題的步驟。  
  
 如果應用程式無法載入，因為它具有在並存組件上指定相依性的資訊清單，且組件不會在可執行檔所在的相同的資料夾中安裝成私用組件，也不會在 %WINDIR%\\WinSxS\\ 資料夾的原生組件快取中安裝，則可能會顯示下列錯誤訊息，視您嘗試執行應用程式的 Windows 版本而定。  
  
-   無法正確初始化應用程式 \(0xc0000135\)。  
  
-   此應用程式無法啟動，因為應用程式組態不正確。  重新安裝應用程式可能可以解決這個問題。  
  
-   系統無法執行指定的程式。  
  
 如果您的應用程式沒有任何資訊清單，而且相依於 Windows 在一般搜尋位置中找不到的 DLL，可能會顯示以下的類似錯誤訊息：  
  
-   此應用程式無法啟動，因為找不到*所需的 DLL*。  重新安重新安裝應用程式可能可以解決這個問題。  
  
 如果將應用程式部署到沒有 Visual Studio 的電腦，且其損毀並顯示先前的類似錯誤訊息，請檢查這些情況：  
  
1.  請依照[了解 Visual C\+\+ 應用程式的相依性](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)所述的步驟。  相依性查核器可以顯示應用程式或 DLL 的大部分相依性。  如果您觀察到某些 Dll 會遺失，請在嘗試執行應用程式的電腦上安裝它們。  
  
2.  作業系統載入器會使用應用程式資訊清單來載入應用程式所相依的組件。  資訊清單可以內嵌於二進位檔做為資源，或安裝為應用程式資料夾中的個別檔案。  若要檢查資訊清單是否內嵌於二進位檔，請在 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 中開啟二進位檔，並在其資源清單中尋找 RT\_MANIFEST。  如果找不到內嵌的資訊清單，請在應用程式資料夾中尋找具有 \<binary\_name\>.\<extension\>.manifest 之類名稱的檔案。  
  
3.  如果您的應用程式相依於並存組件，並且未出現資訊清單，您必須確定連結器可產生專案的資訊清單。  在專案的 \[**專案屬性**\] 對話方塊中核取連結器選項 \[**產生資訊清單**\]。  
  
4.  如果資訊清單內嵌於二進位檔，請確定 RT\_MANIFEST 的識別碼對這種類型的二進位檔是正確的。  如需要使用的資源識別碼的詳細資訊，請參閱 [將並排組件做為資源 \(Windows\)](http://msdn.microsoft.com/library/windows/desktop/aa376617.aspx) \(英文\)。  如果資訊清單位於不同的檔案，請在 XML 編輯器或文字編輯器中開啟它。  如需有關資訊清單和部署的規則的詳細資訊，請參閱[資訊清單](http://msdn.microsoft.com/library/aa375365)。  
  
    > [!NOTE]
    >  如果出現內嵌資訊清單和個別的資訊清單檔案，作業系統載入器會使用內嵌資訊清單，並忽略個別的檔案。  不過，在 Windows XP 上的情況則相反，會使用不同的資訊清單檔案，而且會忽略內嵌資訊清單。  
  
5.  我們建議您在每個 DLL 中內嵌資訊清單，因為在透過`LoadLibrary` 呼叫載入 DLL 時，會忽略外部資訊清單。  如需詳細資訊，請參閱 [組件資訊清單](http://msdn.microsoft.com/library/aa374219)。  
  
6.  請檢查資訊清單中列舉的所有組件都會正確安裝在電腦上。  每個組件是依其名稱、版本號碼和處理器架構，在資訊清單中指定。  如果您的應用程式相依並存組件，請檢查這些組件是正確安裝在電腦上，讓作業系統載入器可以找到它們，如[組件搜尋序列](http://msdn.microsoft.com/library/aa374224)中所述。  請記住，64 位元組件無法在 32 位元處理序中載入，而且無法在 32 位元作業系統上執行。  
  
## 範例  
 假設我們有使用 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 建立的應用程式 appl.exe。  應用程式資訊清單可能會內嵌在 appl.exe 做為二進位資源 RT\_MANIFEST \(具有等於 1 的識別碼\)，或儲存為個別檔案 appl.exe.manifest。  此資訊清單的內容看起來像這樣：  
  
```  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <dependency>  
    <dependentAssembly>  
      <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"></assemblyIdentity>  
    </dependentAssembly>  
  </dependency>  
</assembly>  
```  
  
 對於作業系統載入器，此資訊清單假設 appl.exe 相依於名為 Fabrikam.SxS.Library 的組件，其版本為 2.0.20121.0，為針對 32 位元 x86 處理器架構所建置。  可將相依的並存組件安裝為共用組件或私用組件。  
  
 共用組件的組件資訊清單會安裝在 %WINDIR%\\WinSxS\\Manifests\\ 資料夾中。  它會識別組件並列出其內容—也就是屬於組件的 DLL：  
  
```  
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
   <noInheritable/>  
   <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>  
   <file name="Fabrikam.Main.dll" hash="3ca5156e8212449db6c622c3d10f37d9adb1ab12" hashalg="SHA1"/>  
   <file name="Fabrikam.Helper.dll" hash="92cf8a9bb066aea821d324ca4695c69e55b2d1c2" hashalg="SHA1"/>  
</assembly>  
```  
  
 並存組件也可以使用 [發行者組態檔](http://msdn.microsoft.com/library/aa375682) \(也就是原則檔案\)，將應用程式和組件全域地重新導向到使用一個版本的並存組件，而不是另一個版本的相同組件。  您可以在 %WINDIR%\\WinSxS\\Policies\\ 資料夾中檢查共用組件的原則。  以下是範例原則檔案：  
  
```  
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  
   <assemblyIdentity type="win32-policy" name="policy.2.0.Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>  
   <dependency>  
      <dependentAssembly>  
         <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>  
         <bindingRedirect oldVersion="2.0.10000.0-2.0.20120.99" newVersion="2.0.20121.0"/>  
      </dependentAssembly>  
   </dependency>  
</assembly>  
```  
  
 這個原則檔案會指定要求此組件的 2.0.10000.0 版的任何應用程式或組件，改為使用 2.0.20121.0 版本，這是安裝在系統的目前版本。  若是在原則檔案中指定應用程式資訊清單所提及的組件版本，載入器會在 %WINDIR%\\WinSxS\\ 資料夾中，尋找資訊清單中指定的此組件版本，如果未安裝此版本，載入就會失敗。  而如果未安裝組件版本 2.0.20121.0，要求組件版本 2.0.10000.0 的應用程式載入會失敗。  
  
 不過，組件也可以安裝為安裝的應用程式資料夾中的私用並存組件。  如果作業系統找不到做為共用組件的組件，它會按下列順序，以私用組件方式尋找它：  
  
1.  檢查具有名稱 \< assemblyName \>.manifest 的資訊清單檔案的應用程式資料夾。  在此範例中，載入器會嘗試在 appl.exe 所在的資料夾中尋找 Fabrikam.SxS.Library.manifest。  如果找到資訊清單，則載入器會從應用程式資料夾載入組件。  如果找不到組件，載入就會失敗。  
  
2.  嘗試在包含 appl.exe 的資料夾中開啟 \\\<assemblyName\>\\ 資料夾，如果存在 \\\<assemblyName\>\\，請試著從這個資料夾中載入具有名稱 \<assemblyName\>.manifest 的資訊清單檔案。  如果找到資訊清單，則載入器會從 \\\<assemblyName\>\\ 資料夾中載入組件。  如果找不到組件，載入就會失敗。  
  
 如需載入器如何搜尋相依組件的詳細資訊，請參閱[組件搜尋序列](http://msdn.microsoft.com/library/aa374224)。  如果載入器找不到做為私用組件的相依組件，載入會失敗並出現「系統無法執行指定的程式」訊息。  若要解決這個錯誤，請確定相依組件和屬於這些組件的 Dll，都做為私用或共用組件安裝在電腦上。  
  
## 請參閱  
 [隔離應用程式和並存組件的概念](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [建置 C\/C\+\+ 隔離應用程式和並存組件](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)