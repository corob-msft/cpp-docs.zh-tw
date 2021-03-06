---
title: CSocketAddr 類別
ms.date: 10/22/2018
f1_keywords:
- CSocketAddr
- ATLSOCKET/ATL::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::FindAddr
- ATLSOCKET/ATL::CSocketAddr::FindINET4Addr
- ATLSOCKET/ATL::CSocketAddr::FindINET6Addr
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfo
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfoList
helpviewer_keywords:
- CSocketAddr class
ms.assetid: 2fb2d8a7-899e-4a36-a342-cc9f4fcdd68c
ms.openlocfilehash: cc0c5f0abc125138c5068682c828a3438dec5102
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/24/2019
ms.locfileid: "54893349"
---
# <a name="csocketaddr-class"></a>CSocketAddr 類別

這個類別會提供將主控件名稱轉換為主機位址，支援 IPv4 和 IPV6 格式的方法。

## <a name="syntax"></a>語法

```
class CSocketAddr
```

## <a name="members"></a>成員

### <a name="public-constructors"></a>公用建構函式

|名稱|描述|
|----------|-----------------|
|[CSocketAddr::CSocketAddr](#csocketaddr)|建構函式。|

### <a name="public-methods"></a>公用方法

|名稱|描述|
|----------|-----------------|
|[CSocketAddr::FindAddr](#findaddr)|呼叫此方法，將提供的主機名稱轉換為主機位址。|
|[CSocketAddr::FindINET4Addr](#findinet4addr)|呼叫此方法，將 IPv4 主機名稱轉換為主機位址。|
|[CSocketAddr::FindINET6Addr](#findinet6addr)|呼叫此方法，將 IPv6 主機名稱轉換為主機位址。|
|[CSocketAddr::GetAddrInfo](#getaddrinfo)|呼叫這個方法來傳回特定的項目中的指標`addrinfo`清單。|
|[CSocketAddr::GetAddrInfoList](#getaddrinfolist)|呼叫此方法以傳回的指標`addrinfo`清單。|

## <a name="remarks"></a>備註

這個類別會提供 IP 版本無關的方法，來查閱與 Windows 搭配使用的網路位址的通訊端 API 函式和程式庫中的通訊端包裝函式。

這個類別的成員，顯示用來查詢網路位址使用的 Win32 API 函式[getaddrinfo](/windows/desktop/api/ws2tcpip/nf-ws2tcpip-getaddrinfo)。 根據您的程式碼會編譯為 ANSI 或 UNICODE，會呼叫函式的 ANSI 或 UNICODE 版本。

此類別支援這兩個 IPv4 andIPv6 網路位址。

## <a name="requirements"></a>需求

**標頭：** atlsocket.h

##  <a name="csocketaddr"></a>  CSocketAddr::CSocketAddr

建構函式。

```
CSocketAddr();
```

### <a name="remarks"></a>備註

建立新`CSocketAddr`物件，並初始化包含主應用程式的回應資訊的連結的清單。

##  <a name="findaddr"></a>  CSocketAddr::FindAddr

呼叫此方法，將提供的主機名稱轉換為主機位址。

```
int FindAddr(
    const TCHAR *szHost,
    const TCHAR *szPortOrServiceName,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);

int FindAddr(
    const TCHAR *szHost,
    int nPortNo,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);
```

### <a name="parameters"></a>參數

*szHost*<br/>
主機名稱或點線的 IP 位址。

*szPortOrServiceName*<br/>
連接埠號碼的主機上的服務名稱。

*nPortNo*<br/>
連接埠號碼。

*flags*<br/>
0 或 AI_PASSIVE、 AI_CANONNAME 或 AI_NUMERICHOST 的組合。

*addr_family*<br/>
位址家族 （例如 PF_INET)。

*sock_type*<br/>
通訊端類型 （例如 SOCK_STREAM)。

*ai_proto*<br/>
通訊協定 （例如 IPPROTO_IP 或 IPPROTO_IPV6）。

### <a name="return-value"></a>傳回值

如果成功計算出位址，則傳回零。 在失敗時傳回非零的 Windows 通訊端錯誤碼。 如果成功，導出的地址會儲存在可能使用參考連結串列`CSocketAddr::GetAddrInfoList`和`CSocketAddr::GetAddrInfo`。

### <a name="remarks"></a>備註

主機名稱參數可能是 IPv4 或 IPv6 格式。 這個方法會呼叫 Win32 API 函式[getaddrinfo](/windows/desktop/api/ws2tcpip/nf-ws2tcpip-getaddrinfo)來執行轉換。

##  <a name="findinet4addr"></a>  CSocketAddr::FindINET4Addr

呼叫此方法，將 IPv4 主機名稱轉換為主機位址。

```
int FindINET4Addr(
    const TCHAR *szHost,
    int nPortNo,
    int flags = 0,
    int sock_type = SOCK_STREAM);
```

### <a name="parameters"></a>參數

*szHost*<br/>
主機名稱或點線的 IP 位址。

*nPortNo*<br/>
連接埠號碼。

*flags*<br/>
0 或 AI_PASSIVE、 AI_CANONNAME 或 AI_NUMERICHOST 的組合。

*sock_type*<br/>
通訊端類型 （例如 SOCK_STREAM)。

### <a name="return-value"></a>傳回值

如果成功計算出位址，則傳回零。 在失敗時傳回非零的 Windows 通訊端錯誤碼。 如果成功，導出的地址會儲存在可能使用參考連結串列`CSocketAddr::GetAddrInfoList`和`CSocketAddr::GetAddrInfo`。

### <a name="remarks"></a>備註

這個方法會呼叫 Win32 API 函式[getaddrinfo](/windows/desktop/api/ws2tcpip/nf-ws2tcpip-getaddrinfo)來執行轉換。

##  <a name="findinet6addr"></a>  CSocketAddr::FindINET6Addr

呼叫此方法，將 IPv6 主機名稱轉換為主機位址。

```
int FindINET6Addr(
    const TCHAR *szHost,
    int nPortNo,
    int flags = 0,
    int sock_type = SOCK_STREAM);
```

### <a name="parameters"></a>參數

*szHost*<br/>
主機名稱或點線的 IP 位址。

*nPortNo*<br/>
連接埠號碼。

*flags*<br/>
0 或 AI_PASSIVE、 AI_CANONNAME 或 AI_NUMERICHOST 的組合。

*sock_type*<br/>
通訊端類型 （例如 SOCK_STREAM)。

### <a name="return-value"></a>傳回值

如果成功計算出位址，則傳回零。 在失敗時傳回非零的 Windows 通訊端錯誤碼。 如果成功，導出的地址會儲存在可能使用參考連結串列`CSocketAddr::GetAddrInfoList`和`CSocketAddr::GetAddrInfo`。

### <a name="remarks"></a>備註

這個方法會呼叫 Win32 API 函式[getaddrinfo](/windows/desktop/api/ws2tcpip/nf-ws2tcpip-getaddrinfo)來執行轉換。

##  <a name="getaddrinfo"></a>  CSocketAddr::GetAddrInfo

呼叫這個方法來傳回特定的項目中的指標`addrinfo`清單。

```
addrinfo* const GetAddrInfo(int nIndex = 0) const;
```

### <a name="parameters"></a>參數

*nIndex*<br/>
中的特定項目的參考[addrinfo](/windows/desktop/api/ws2def/ns-ws2def-addrinfoa)清單。

### <a name="return-value"></a>傳回值

將指標傳回至`addrinfo`所參考的結構*nIndex*包含主應用程式的回應資訊的連結清單中。

##  <a name="getaddrinfolist"></a>  CSocketAddr::GetAddrInfoList

呼叫此方法以傳回的指標`addrinfo`清單。

```
addrinfo* const GetAddrInfoList() const;
```

### <a name="return-value"></a>傳回值

連結清單的一或多個指標`addrinfo`結構，其中包含主機的回應資訊。 如需詳細資訊，請參閱 < [addrinfo 結構](/windows/desktop/api/ws2def/ns-ws2def-addrinfoa)。

## <a name="see-also"></a>另請參閱

[類別概觀](../../atl/atl-class-overview.md)
