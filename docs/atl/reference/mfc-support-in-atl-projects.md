---
title: ATL 專案中的 MFC 支援
ms.date: 11/04/2016
f1_keywords:
- vc.atl.addmfc
helpviewer_keywords:
- ATL projects, MFC support
ms.assetid: f90b4276-cb98-4c11-902c-9ebcfe6f954b
ms.openlocfilehash: 21e3305ce2d2968a3809793eb487317e224351f4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50489384"
---
# <a name="mfc-support-in-atl-projects"></a>ATL 專案中的 MFC 支援

如果您選取**支援 MFC** ATL 專案精靈 中，您的專案會宣告為 MFC 應用程式物件 （類別） 的應用程式。 初始化 MFC 程式庫專案，並具現化類別 (類別*ProjName*) 衍生自[CWinApp](../../mfc/reference/cwinapp-class.md)。

此選項適用於僅限非屬性化 ATL DLL 專案。

```
class CProjNameApp : public CWinApp
{
public:

// Overrides
    virtual BOOL InitInstance();
virtual int ExitInstance();
DECLARE_MESSAGE_MAP()
};

BEGIN_MESSAGE_MAP(CProjNameApp, CWinApp)
END_MESSAGE_MAP()

CProjNameApp theApp;

BOOL CProjNameApp::InitInstance()
{
    return CWinApp::InitInstance();

}

int CProjNameApp::ExitInstance()
{
    return CWinApp::ExitInstance();

}
```

您可以檢視應用程式的物件類別及其`InitInstance`和`ExitInstance`類別檢視 中的函式。

## <a name="see-also"></a>另請參閱

[新增類別](../../ide/adding-a-class-visual-cpp.md)<br/>
[建立 ATL 專案](../../atl/reference/creating-an-atl-project.md)<br/>
[預設 ATL 專案組態](../../atl/reference/default-atl-project-configurations.md)

