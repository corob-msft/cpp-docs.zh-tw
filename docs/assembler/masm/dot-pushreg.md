---
title: .PUSHREG
ms.date: 08/30/2018
f1_keywords:
- .PUSHREG
helpviewer_keywords:
- .PUSHREG directive
ms.assetid: e0c83758-dfed-40ea-afe6-cb833c8d2d30
ms.openlocfilehash: 19e36f1c0b073c5b174ea9acb0f1eaac7d771c46
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501760"
---
# <a name="pushreg"></a>.PUSHREG

會產生`UWOP_PUSH_NONVOL`針對指定的暫存器號碼使用目前的位移在序言回溯程式碼項目。

## <a name="syntax"></a>語法

> .PUSHREG 暫存器

## <a name="remarks"></a>備註

.PUSHREG 允許 ml64.exe 使用者指定框架函式的回溯時，如何，而且只允許在序言，始[PROC](../../assembler/masm/proc.md)框架宣告[。ENDPROLOG](../../assembler/masm/dot-endprolog.md)指示詞。 這些指示詞不會產生程式碼路徑。它們只會產生`.xdata`和`.pdata`。 .PUSHREG 之前應該加實際實作要回溯動作的指示。 它是個不錯的做法，包裝的回溯程式指示詞和它們以確保協議要在巨集中的回溯程式碼。

如需詳細資訊，請參閱 < [MASM (ml64.exe) x64 的](../../assembler/masm/masm-for-x64-ml64-exe.md)。

## <a name="sample"></a>範例

### <a name="description"></a>描述

下列範例示範如何將推送靜態 tegisters。

### <a name="code"></a>程式碼

```asm
; ml64 ex1.asm /link /entry:Example1 /SUBSYSTEM:CONSOLE
_text SEGMENT
Example1 PROC FRAME
   push r10
.pushreg r10
   push r15
.pushreg r15
   push rbx
.pushreg rbx
   push rsi
.pushreg rsi
.endprolog
   ; rest of function ...
   ret
Example1 ENDP
_text ENDS
END
```

## <a name="see-also"></a>另請參閱

[指示詞參考](../../assembler/masm/directives-reference.md)<br/>