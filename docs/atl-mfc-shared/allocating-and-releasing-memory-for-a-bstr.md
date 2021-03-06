---
title: 針對 BSTR 配置及釋放記憶體
ms.date: 11/04/2016
f1_keywords:
- bstr
helpviewer_keywords:
- BSTRs, memory allocation
- memory deallocation, string memory
- memory [C++], releasing
- memory allocation, BSTRs
- memory deallocation, BSTR memory
- strings [C++], releasing
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
ms.openlocfilehash: cfa921758122dfadb7b008740a14e352456a180f
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518186"
---
# <a name="allocating-and-releasing-memory-for-a-bstr"></a>針對 BSTR 配置及釋放記憶體

當您建立`BSTR`s 和 COM 物件之間傳遞這些，您必須特別小心並將它們使用，以避免記憶體流失的記憶體。 當`BSTR`保持在介面內，使用它完成時，必須釋放其記憶體。 不過，當`BSTR`從介面的傳遞，接收的物件會負責其記憶體管理。

配置及釋放記憶體的規則一般來說，配置給`BSTR`s 如下所示：

- 當您呼叫的函式必須要有`BSTR`引數，您必須配置的記憶體`BSTR`呼叫之前和之後釋放它。 例如: 

   [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_1.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_2.cpp)]

- 當您呼叫的函式會傳回`BSTR`，您必須自行釋放字串。 例如: 

   [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_3.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_4.cpp)]

- 當您實作傳回的函式`BSTR`、 配置字串，但請勿釋放它。 接收函式會釋放記憶體。 例如: 

   [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_5.cpp)]

## <a name="see-also"></a>另請參閱

[字串 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)<br/>
[SysAllocString](/windows/desktop/api/oleauto/nf-oleauto-sysallocstring)<br/>
[SysFreeString](/windows/desktop/api/oleauto/nf-oleauto-sysfreestring)

