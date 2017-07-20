---
title: "IAxWinAmbientDispatch 介面 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAxWinAmbientDispatch
- No header/ATL::IAxWinAmbientDispatch
- No header/ATL::get_AllowContextMenu
- No header/ATL::get_AllowShowUI
- No header/ATL::get_AllowWindowlessActivation
- No header/ATL::get_BackColor
- No header/ATL::get_DisplayAsDefault
- No header/ATL::get_DocHostDoubleClickFlags
- No header/ATL::get_DocHostFlags
- No header/ATL::get_Font
- No header/ATL::get_ForeColor
- No header/ATL::get_LocaleID
- No header/ATL::get_MessageReflect
- No header/ATL::get_OptionKeyPath
- No header/ATL::get_ShowGrabHandles
- No header/ATL::get_ShowHatching
- No header/ATL::get_UserMode
- No header/ATL::put_AllowContextMenu
- No header/ATL::put_AllowShowUI
- No header/ATL::put_AllowWindowlessActivation
- No header/ATL::put_BackColor
- No header/ATL::put_DisplayAsDefault
- No header/ATL::put_DocHostDoubleClickFlags
- No header/ATL::put_DocHostFlags
- No header/ATL::put_Font
- No header/ATL::put_ForeColor
- No header/ATL::put_LocaleID
- No header/ATL::put_MessageReflect
- No header/ATL::put_OptionKeyPath
- No header/ATL::put_UserMode
dev_langs:
- C++
helpviewer_keywords:
- IAxWinAmbientDispatch interface
ms.assetid: 55ba6f7b-7a3c-4792-ae47-c8a84b683ca9
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 3dd34ffec68e4503aebe7b8d0e72ec1f711dca03
ms.contentlocale: zh-tw
ms.lasthandoff: 03/31/2017

---
# <a name="iaxwinambientdispatch-interface"></a>IAxWinAmbientDispatch 介面
這個介面會提供方法來指定裝載的控制項或容器的特性。  
  
> [!IMPORTANT]
>  這個類別及其成員無法在 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]中執行的應用程式內使用。  
  
## <a name="syntax"></a>語法  
  
```
interface IAxWinAmbientDispatch : IDispatch
```  
  
## <a name="members"></a>Members  
  
### <a name="methods"></a>方法  
  
|||  
|-|-|  
|[get_AllowContextMenu](#get_allowcontextmenu)|**AllowContextMenu**屬性會指定是否允許裝載的控制項顯示操作功能表。|  
|[get_AllowShowUI](#get_allowshowui)|**AllowShowUI**屬性會指定是否允許裝載的控制項顯示自己的使用者介面。|  
|[get_AllowWindowlessActivation](#get_allowwindowlessactivation)|**AllowWindowlessActivation**屬性中指定容器是否允許無視窗啟用。|  
|[get_BackColor](#get_backcolor)|`BackColor`屬性會指定容器的環境背景色彩。|  
|[get_DisplayAsDefault](#get_displayasdefault)|**DisplayAsDefault**是環境的屬性，可讓您了解如果是預設控制項的控制。|  
|[get_DocHostDoubleClickFlags](#get_dochostdoubleclickflags)|**DocHostDoubleClickFlags**屬性會指定應該發生在回應按兩下滑鼠的作業。|  
|[get_DocHostFlags](#get_dochostflags)|**DocHostFlags**屬性會指定主機物件的使用者介面功能。|  
|[get_Font](#get_font)|**字型**屬性會指定容器的環境字型。|  
|[get_ForeColor](#get_forecolor)|`ForeColor`屬性會指定容器的環境前景色彩。|  
|[get_LocaleID](#get_localeid)|**LocaleID**屬性會指定容器的環境的地區設定識別碼。|  
|[get_MessageReflect](#get_messagereflect)|**MessageReflect**環境屬性可讓您指定容器是否會反映在裝載控制項的訊息。|  
|[get_OptionKeyPath](#get_optionkeypath)|**OptionKeyPath**屬性會指定使用者設定登錄機碼路徑。|  
|[get_ShowGrabHandles](#get_showgrabhandles)|**ShowGrabHandles**環境屬性可讓控制項以了解是否它應該繪製本身具有抓取控點。|  
|[get_ShowHatching](#get_showhatching)|**ShowHatching**環境屬性可讓要了解是否它應該繪製本身影線的控制項。|  
|[get_UserMode](#get_usermode)|**UserMode**屬性會指定容器的環境的使用者模式。|  
|[put_AllowContextMenu](#put_allowcontextmenu)|**AllowContextMenu**屬性會指定是否允許裝載的控制項顯示操作功能表。|  
|[put_AllowShowUI](#put_allowshowui)|**AllowShowUI**屬性會指定是否允許裝載的控制項顯示自己的使用者介面。|  
|[put_AllowWindowlessActivation](#put_allowwindowlessactivation)|**AllowWindowlessActivation**屬性中指定容器是否允許無視窗啟用。|  
|[put_BackColor](#put_backcolor)|`BackColor`屬性會指定容器的環境背景色彩。|  
|[put_DisplayAsDefault](#put_displayasdefault)|**DisplayAsDefault**是環境的屬性，可讓您了解如果是預設控制項的控制。|  
|[put_DocHostDoubleClickFlags](#put_dochostdoubleclickflags)|**DocHostDoubleClickFlags**屬性會指定應該發生在回應按兩下滑鼠的作業。|  
|[put_DocHostFlags](#put_dochostflags)|**DocHostFlags**屬性會指定主機物件的使用者介面功能。|  
|[put_Font](#put_font)|**字型**屬性會指定容器的環境字型。|  
|[put_ForeColor](#put_forecolor)|`ForeColor`屬性會指定容器的環境前景色彩。|  
|[put_LocaleID](#put_localeid)|**LocaleID**屬性會指定容器的環境的地區設定識別碼。|  
|[put_MessageReflect](#put_messagereflect)|**MessageReflect**環境屬性可讓您指定容器是否會反映在裝載控制項的訊息。|  
|[put_OptionKeyPath](#put_optionkeypath)|**OptionKeyPath**屬性會指定使用者設定登錄機碼路徑。|  
|[put_UserMode](#put_usermode)|**UserMode**屬性會指定容器的環境的使用者模式。|  
  
## <a name="remarks"></a>備註  
 這個介面是 ATL 的 ActiveX 控制項裝載物件所公開的。 若要設定裝載的控制項所提供的環境屬性，或指定容器的行為的其他層面，此介面上呼叫的方法。 所提供的屬性外，再補`IAxWinAmbientDispatch`，使用[IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md)。  
  
 [AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx)會嘗試載入型別資訊有關`IAxWinAmbientDispatch`和`IAxWinAmbientDispatchEx`從 typelib 包含程式碼。  
  
 如果您要連結至 ATL90.dll， **AXHost**會從型別程式庫 DLL 中載入的型別資訊。  
  
 請參閱[裝載 ActiveX 控制項使用 ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md)以取得詳細資料。  
  
## <a name="requirements"></a>需求  
 下表所示使用數種格式，此介面的定義。  
  
|定義類型|檔案|  
|---------------------|----------|  
|IDL|atliface.idl|  
|類型程式庫|ATL.dll|  
|C++|atliface.h （也包含在 ATLBase.h）|  
  
##  <a name="get_allowcontextmenu"></a>IAxWinAmbientDispatch::get_AllowContextMenu  
 **AllowContextMenu**屬性會指定是否允許裝載的控制項顯示操作功能表。  
  
```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```  
  
### <a name="parameters"></a>參數  
 *pbAllowContextMenu*  
 [out]要接收這個屬性的目前值之變數的位址。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用`VARIANT_TRUE`作為預設值，這個屬性。  
  
##  <a name="get_allowshowui"></a>IAxWinAmbientDispatch::get_AllowShowUI  
 **AllowShowUI**屬性會指定是否允許裝載的控制項顯示自己的使用者介面。  
  
```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```  
  
### <a name="parameters"></a>參數  
 *pbAllowShowUI*  
 [out]要接收這個屬性的目前值之變數的位址。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用**VARIANT_FALSE**作為預設值，這個屬性。  
  
##  <a name="get_allowwindowlessactivation"></a>IAxWinAmbientDispatch::get_AllowWindowlessActivation  
 **AllowWindowlessActivation**屬性中指定容器是否允許無視窗啟用。  
  
```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```  
  
### <a name="parameters"></a>參數  
 *pbAllowWindowless*  
 [out]要接收這個屬性的目前值之變數的位址。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用`VARIANT_TRUE`作為預設值，這個屬性。  
  
##  <a name="get_backcolor"></a>IAxWinAmbientDispatch::get_BackColor  
 `BackColor`屬性會指定容器的環境背景色彩。  
  
```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```  
  
### <a name="parameters"></a>參數  
 *pclrBackground*  
 [out]要接收這個屬性的目前值之變數的位址。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用**COLOR_BTNFACE**或**COLOR_WINDOW**作為預設值，這個屬性 （取決於是否主控視窗的父代為對話方塊）。  
  
##  <a name="get_displayasdefault"></a>IAxWinAmbientDispatch::get_DisplayAsDefault  
 **DisplayAsDefault**是環境的屬性，可讓您了解如果是預設控制項的控制。  
  
```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```  
  
### <a name="parameters"></a>參數  
 *pbDisplayAsDefault*  
 [out]要接收這個屬性的目前值之變數的位址。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用**VARIANT_FALSE**作為預設值，這個屬性。  
  
##  <a name="get_dochostdoubleclickflags"></a>IAxWinAmbientDispatch::get_DocHostDoubleClickFlags  
 **DocHostDoubleClickFlags**屬性會指定應該發生在回應按兩下滑鼠的作業。  
  
```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```  
  
### <a name="parameters"></a>參數  
 *pdwDocHostDoubleClickFlags*  
 [out]要接收這個屬性的目前值之變數的位址。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用**DOCHOSTUIDBLCLK_DEFAULT**作為預設值，這個屬性。  
  
##  <a name="get_dochostflags"></a>IAxWinAmbientDispatch::get_DocHostFlags  
 **DocHostFlags**屬性會指定主機物件的使用者介面功能。  
  
```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```  
  
### <a name="parameters"></a>參數  
 *pdwDocHostFlags*  
 [out]要接收這個屬性的目前值之變數的位址。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用**DOCHOSTUIFLAG_NO3DBORDER**作為預設值，這個屬性。  
  
##  <a name="get_font"></a>IAxWinAmbientDispatch::get_Font  
 **字型**屬性會指定容器的環境字型。  
  
```
STDMETHOD(get_Font)(IFontDisp** pFont);
```  
  
### <a name="parameters"></a>參數  
 `pFont`  
 [out]位址**IFontDisp**用來接收此屬性的目前值的介面指標。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用做為預設值，這個屬性的預設 GUI 字型或系統字型。  
  
##  <a name="get_forecolor"></a>IAxWinAmbientDispatch::get_ForeColor  
 `ForeColor`屬性會指定容器的環境前景色彩。  
  
```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```  
  
### <a name="parameters"></a>參數  
 *pclrForeground*  
 [out]要接收這個屬性的目前值之變數的位址。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用這個屬性的預設值為系統視窗文字色彩。  
  
##  <a name="get_localeid"></a>IAxWinAmbientDispatch::get_LocaleID  
 **LocaleID**屬性會指定容器的環境的地區設定識別碼。  
  
```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```  
  
### <a name="parameters"></a>參數  
 *plcidLocaleID*  
 [out]要接收這個屬性的目前值之變數的位址。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用使用者的預設地區設定為預設值，這個屬性。  
  
 使用此方法中，您可以探索環境 LocalID，也就是程式的地區設定識別碼控制項使用中。 一旦您知道地區設定識別碼，您可以呼叫程式碼載入地區設定特定標題，錯誤訊息文字，依此類推從資源檔或附屬 DLL。  
  
##  <a name="get_messagereflect"></a>IAxWinAmbientDispatch::get_MessageReflect  
 **MessageReflect**環境屬性可讓您指定容器是否會反映在裝載控制項的訊息。  
  
```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```  
  
### <a name="parameters"></a>參數  
 *pbMessageReflect*  
 [out]要接收這個屬性的目前值之變數的位址。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用`VARIANT_TRUE`作為預設值，這個屬性。  
  
##  <a name="get_optionkeypath"></a>IAxWinAmbientDispatch::get_OptionKeyPath  
 **OptionKeyPath**屬性會指定使用者設定登錄機碼路徑。  
  
```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```  
  
### <a name="parameters"></a>參數  
 *pbstrOptionKeyPath*  
 [out]要接收這個屬性的目前值之變數的位址。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
##  <a name="get_showgrabhandles"></a>IAxWinAmbientDispatch::get_ShowGrabHandles  
 **ShowGrabHandles**環境屬性可讓控制項以了解是否它應該繪製本身具有抓取控點。  
  
```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```  
  
### <a name="parameters"></a>參數  
 *pbShowGrabHandles*  
 [out]要接收這個屬性的目前值之變數的位址。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作一律會傳回**VARIANT_FALSE**做為這個屬性的值。  
  
##  <a name="get_showhatching"></a>IAxWinAmbientDispatch::get_ShowHatching  
 **ShowHatching**環境屬性可讓要了解是否它應該繪製本身影線的控制項。  
  
```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```  
  
### <a name="parameters"></a>參數  
 *pbShowHatching*  
 [out]要接收這個屬性的目前值之變數的位址。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作一律會傳回**VARIANT_FALSE**做為這個屬性的值。  
  
##  <a name="get_usermode"></a>IAxWinAmbientDispatch::get_UserMode  
 **UserMode**屬性會指定容器的環境的使用者模式。  
  
```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```  
  
### <a name="parameters"></a>參數  
 *pbUserMode*  
 [out]要接收這個屬性的目前值之變數的位址。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用`VARIANT_TRUE`作為預設值，這個屬性。  
  
##  <a name="put_allowcontextmenu"></a>IAxWinAmbientDispatch::put_AllowContextMenu  
 **AllowContextMenu**屬性會指定是否允許裝載的控制項顯示操作功能表。  
  
```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```  
  
### <a name="parameters"></a>參數  
 *bAllowContextMenu*  
 [in]這個屬性的新值。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用`VARIANT_TRUE`作為預設值，這個屬性。  
  
##  <a name="put_allowshowui"></a>IAxWinAmbientDispatch::put_AllowShowUI  
 **AllowShowUI**屬性會指定是否允許裝載的控制項顯示自己的使用者介面。  
  
```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```  
  
### <a name="parameters"></a>參數  
 *bAllowShowUI*  
 [in]這個屬性的新值。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用**VARIANT_FALSE**作為預設值，這個屬性。  
  
##  <a name="put_allowwindowlessactivation"></a>IAxWinAmbientDispatch::put_AllowWindowlessActivation  
 **AllowWindowlessActivation**屬性中指定容器是否允許無視窗啟用。  
  
```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```  
  
### <a name="parameters"></a>參數  
 *bAllowWindowless*  
 [in]這個屬性的新值。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用`VARIANT_TRUE`作為預設值，這個屬性。  
  
##  <a name="put_backcolor"></a>IAxWinAmbientDispatch::put_BackColor  
 `BackColor`屬性會指定容器的環境背景色彩。  
  
```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```  
  
### <a name="parameters"></a>參數  
 *clrBackground*  
 [in]這個屬性的新值。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用**COLOR_BTNFACE**或**COLOR_WINDOW**作為預設值，這個屬性 （取決於是否主控視窗的父代為對話方塊）。  
  
##  <a name="put_displayasdefault"></a>IAxWinAmbientDispatch::put_DisplayAsDefault  
 **DisplayAsDefault**是環境的屬性，可讓您了解如果是預設控制項的控制。  
  
```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```  
  
### <a name="parameters"></a>參數  
 `bDisplayAsDefault`  
 [in]這個屬性的新值。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用**VARIANT_FALSE**作為預設值，這個屬性。  
  
##  <a name="put_dochostdoubleclickflags"></a>IAxWinAmbientDispatch::put_DocHostDoubleClickFlags  
 **DocHostDoubleClickFlags**屬性會指定應該發生在回應按兩下滑鼠的作業。  
  
```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```  
  
### <a name="parameters"></a>參數  
 *dwDocHostDoubleClickFlags*  
 [in]這個屬性的新值。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用**DOCHOSTUIDBLCLK_DEFAULT**作為預設值，這個屬性。  
  
##  <a name="put_dochostflags"></a>IAxWinAmbientDispatch::put_DocHostFlags  
 **DocHostFlags**屬性會指定主機物件的使用者介面功能。  
  
```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```  
  
### <a name="parameters"></a>參數  
 *dwDocHostFlags*  
 [in]這個屬性的新值。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用**DOCHOSTUIFLAG_NO3DBORDER**作為預設值，這個屬性。  
  
##  <a name="put_font"></a>IAxWinAmbientDispatch::put_Font  
 **字型**屬性會指定容器的環境字型。  
  
```
STDMETHOD(put_Font)(IFontDisp* pFont);
```  
  
### <a name="parameters"></a>參數  
 `pFont`  
 [in]這個屬性的新值。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用做為預設值，這個屬性的預設 GUI 字型或系統字型。  
  
##  <a name="put_forecolor"></a>IAxWinAmbientDispatch::put_ForeColor  
 `ForeColor`屬性會指定容器的環境前景色彩。  
  
```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```  
  
### <a name="parameters"></a>參數  
 *clrForeground*  
 [in]這個屬性的新值。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用這個屬性的預設值為系統視窗文字色彩。  
  
##  <a name="put_localeid"></a>IAxWinAmbientDispatch::put_LocaleID  
 **LocaleID**屬性會指定容器的環境的地區設定識別碼。  
  
```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```  
  
### <a name="parameters"></a>參數  
 *lcidLocaleID*  
 [in]這個屬性的新值。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用使用者的預設地區設定為預設值，這個屬性。  
  
##  <a name="put_messagereflect"></a>IAxWinAmbientDispatch::put_MessageReflect  
 **MessageReflect**環境屬性可讓您指定容器是否會反映在裝載控制項的訊息。  
  
```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```  
  
### <a name="parameters"></a>參數  
 `bMessageReflect`  
 [in]這個屬性的新值。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用`VARIANT_TRUE`作為預設值，這個屬性。  
  
##  <a name="put_optionkeypath"></a>IAxWinAmbientDispatch::put_OptionKeyPath  
 **OptionKeyPath**屬性會指定使用者設定登錄機碼路徑。  
  
```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```  
  
### <a name="parameters"></a>參數  
 *bstrOptionKeyPath*  
 [in]這個屬性的新值。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
##  <a name="put_usermode"></a>IAxWinAmbientDispatch::put_UserMode  
 **UserMode**屬性會指定容器的環境的使用者模式。  
  
```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```  
  
### <a name="parameters"></a>參數  
 `bUserMode`  
 [in]這個屬性的新值。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 ATL 主機物件實作會使用`VARIANT_TRUE`作為預設值，這個屬性。  
  
## <a name="see-also"></a>另請參閱  
 [IAxWinAmbientDispatchEx 介面](../../atl/reference/iaxwinambientdispatchex-interface.md)   
 [IAxWinHostWindow 介面](../../atl/reference/iaxwinhostwindow-interface.md)   
 [CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)   
 [AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)









