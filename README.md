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
 強制存取控制(mandatory access control，MAC）
在電腦資安領域指一種由作業系統約束的存取控制，目標是限制主體或發起者存取或對物件或目標執行某種操作的能力。

 任意存取控制(discretionary access control，DAC)
根據主體（如用戶、進程或 I/O 設備等）的身份和他所屬的組限制對客體的訪問。所謂的自主，是因為擁有訪問權限的主體，
可以直接（或間接）地將訪問權限賦予其他主體（除非受到強制存取控制的限制）。

 存取控制目錄(access control list，ACL)
當使用者嘗試存取時，作業系統會使用與物件關聯的 ACL，來查看使用者是否具有存取權。
這些 ACL 以及相關的存取檢查即構成 AIX® 支援的「任意存取控制」(DAC) 機制核心。
作業系統支援數種系統物件類型，可讓使用者處理程序儲存或傳遞資訊。以下是最重要的存取控制物件類型：
1.檔案與目錄
2.具名管線
3.IPC 物件，如訊息佇列、共用記憶體區段及信號

 規則基準存取控制(rule-based access control)
一種開放源碼的存取控制機制，用於Linux核心，其會依據系統安全策略的選擇，提供所能允許的權限。


 角色基準存取控制(role-based access control)
不同於強制存取控制以及任意存取控制直接賦予使用者權限，而是將權限賦予角色。
```
# Data remanence
```
>* Many operating systems, file managers, and other software provide a facility where a file is not immediately deleted when the user requests that action. Instead, the file is moved to a holding area, making it easy for the user to undo a mistake. Similarly, many software products automatically create backup copies of files that are being edited, to allow the user to restore the original version, or to recover from a possible crash (autosave feature).

>* Even when an explicit deleted file retention facility i>* s not provided or when the user does not use it, operating systems do not actually remove the contents of a file when it is deleted unless they are aware that explicit erasure commands are required, like on a solid-state drive. (In such cases, the operating system will issue the Serial ATA TRIM command or the SCSI UNMAP command to let the drive know to no longer maintain the deleted data.) Instead, they simply remove the file's entry from the file system directory, because this requires less work and is therefore faster, and the contents of the file—the actual data—remain on the storage medium. The data will remain there until the operating system reuses the space for new data. In some systems, enough filesystem metadata are also left behind to enable easy undeletion by commonly available utility software. Even when undelete has become impossible, the data, until it has been overwritten, can be read by software that reads disk sectors directly. Computer forensics often employs such software.

>* Likewise, reformatting, repartitioning, or reimaging a system is unlikely to write to every area of the disk, though all will cause the disk to appear empty or, in the case of reimaging, empty except for the files present in the image, to most software.

>* Finally, even when the storage media is overwritten, physical properties of the media may permit recovery of the previous contents. In most cases however, this recovery is not possible by just reading from the storage device in the usual way, but requires using laboratory techniques such as disassembling the device and directly accessing/reading from its components.[citation needed]

>* The section on complications gives further explanations for causes of data remanence.
```
# 磁碟陣列。
```
其基本思想就是把多個相對便宜的硬碟組合起來，成為一個硬碟陣列組，使效能達到甚至超過一個價格昂貴、
容量巨大的硬碟。根據選擇的版本不同，RAID比單顆硬碟有以下一個或多個方面的好處：
增強資料整合度，增強容錯功能，增加處理量或容量。另外，磁碟陣列對於電腦來說，看起來就像一個單獨的硬碟或邏輯存儲單元。
```

# 備份
```
全部備份（Full Backup），即把硬碟或資料庫內的所有檔案、資料夾或資料作一次性的複製。
增量備份（Incremental Backup），指對上一次全部備份或增量備份後更新的資料進行備份。
差異備份 (Differential backup) 差異備份提供執行完整備份後變更的檔案的備份
選擇式備份，對系統的一部分進行備份。
冷備份：系統處於停機或維護狀態下的備份。這種情況下，備份的資料與系統中此時段的資料完全一致。
熱備份：系統處於正常運轉狀態下的備份。這種情況下，由於系統中的資料可能隨時在更新，備份的資料相對於系統的真實資料可有一定滯後。



```
