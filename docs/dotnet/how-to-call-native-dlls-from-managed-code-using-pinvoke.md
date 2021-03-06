---
title: 如何：使用 PInvoke 從 Managed 程式碼呼叫原生 DLL
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- platform invoke [C++], calling native DLLs
- interop [C++], calling native DLLs
- marshaling [C++], calling native DLLs
- data marshaling [C++], calling native DLLs
ms.assetid: 3273eb4b-38d1-4619-92a6-71bda542be72
ms.openlocfilehash: 921a3504bd4fcb3f8dfe3d6c1a80c69d00298fb4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50444404"
---
# <a name="how-to-call-native-dlls-from-managed-code-using-pinvoke"></a>如何：使用 PInvoke 從 Managed 程式碼呼叫原生 DLL

從 managed 程式碼使用平台叫用 (P/Invoke) 的功能，可以呼叫 unmanaged Dll 中實作的函式。 如果無法使用 DLL 的原始程式碼，P/Invoke 是交互操作的唯一選項。 不過，不同於其他.NET 語言，Visual c + + 提供 P/Invoke 的替代方案。 如需詳細資訊，請參閱 <<c0> [ 使用 c + + Interop (隱含 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)。

## <a name="example"></a>範例

下列程式碼範例會使用 Win32 [GetSystemMetrics](/windows/desktop/api/winuser/nf-winuser-getsystemmetrics)函式來擷取目前像素為單位的螢幕解析度。

對於使用內建的型別做為引數和傳回值的函式，不則需要任何額外的工作。 其他資料類型，例如函式指標、 陣列和結構，需要額外的屬性，以確保適當的資料封送處理。

雖然並非必要，它會是很好的做法是 P/Invoke 宣告靜態成員的實值類別，讓它們不存在於全域命名空間中，在此範例中所示。

```
// pinvoke_basic.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

value class Win32 {
public:
   [DllImport("User32.dll")]
   static int GetSystemMetrics(int);

   enum class SystemMetricIndex {
      // Same values as those defined in winuser.h.
      SM_CXSCREEN = 0,
      SM_CYSCREEN = 1
   };
};

int main() {
   int hRes = Win32::GetSystemMetrics( safe_cast<int>(Win32::SystemMetricIndex::SM_CXSCREEN) );
   int vRes = Win32::GetSystemMetrics( safe_cast<int>(Win32::SystemMetricIndex::SM_CYSCREEN) );
   Console::WriteLine("screen resolution: {0},{1}", hRes, vRes);
}
```

## <a name="see-also"></a>另請參閱

[在 C++ 中使用明確的 PInvoke (DllImport 屬性)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)