# IPAS
readme.md

# network model

Layer-finctionties-protoco1-hardware-data format

# OSI

## layer-7:Application
>* 不安全的協定 telent(23) ftp(20/21) http(80) DNS(53)
>* 安全的協定 ssh(22) sftp(33?) https(443) DNSsec()
>*HUb


###Layer 6:Presentation
>* 格式轉換format 加解密
>*



### Layer-5 session
>*
>*

### Layer-4 Transport
>* TCP VS UDP
>* port address
### Layer-3 network
>* IP address
>* router(動態路由)RIP BGP
### Layer-2 Data link
>* MAC address
>* swith
### Layer-1 Physical
>* frame
>* HUb


# 資料存取控制
```
>* 強制存取控制(mandatory access control，MAC）
在電腦資安領域指一種由作業系統約束的存取控制，目標是限制主體或發起者存取或對物件或目標執行某種操作的能力。

>* 任意存取控制(discretionary access control，DAC)
根據主體（如用戶、進程或 I/O 設備等）的身份和他所屬的組限制對客體的訪問。所謂的自主，是因為擁有訪問權限的主體，
可以直接（或間接）地將訪問權限賦予其他主體（除非受到強制存取控制的限制）。

>* 存取控制目錄(access control list，ACL)
當使用者嘗試存取時，作業系統會使用與物件關聯的 ACL，來查看使用者是否具有存取權。
這些 ACL 以及相關的存取檢查即構成 AIX® 支援的「任意存取控制」(DAC) 機制核心。
作業系統支援數種系統物件類型，可讓使用者處理程序儲存或傳遞資訊。以下是最重要的存取控制物件類型：
1.檔案與目錄
2.具名管線
3.IPC 物件，如訊息佇列、共用記憶體區段及信號

>* 規則基準存取控制(rule-based access control)
一種開放源碼的存取控制機制，用於Linux核心，其會依據系統安全策略的選擇，提供所能允許的權限。


>* 角色基準存取控制(role-based access control)
不同於強制存取控制以及任意存取控制直接賦予使用者權限，而是將權限賦予角色。
```
