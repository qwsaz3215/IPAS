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
使用多於磁碟進行資料複製，當一個磁碟損毀時<其他磁碟上的相同資料可以自動替補，使系統運作不會中斷。
```

# 備份
```
冷備份：具備足夠的基礎設施，需要數周的時間復原資訊服務
暖備份: 有部分資訊與辦公設備，需要幾天到數周的時間復原資訊服務
熱備份：隨時堧硬體及人員準備妥當，一旦緊急應變計畫啟動，可在幾小時內復原資訊服務
全備份:(mirrored sites) 平時與主機房完全同步備援，系統完全相同且資訊即時備份，一旦主機房服務中斷，備援系統立即啟動。



```

# 備援
```
RAID 0 把資料按順序平均分布在數個磁碟機上，這種作法或稱為插敘 (interleaving)
RAID 0 並沒有備援 (redundancy) 功能；它主要目的是提高系統對磁碟機的讀取速度。



RAID 1 & 2

RAID 1 將一筆資料忠實地複製 (mirror) 到另一個或多個磁碟機上，它提供 100% 的資料備援，而且裝置很簡單。
另外，在讀資料時，RAID 1 也具備插敘效果，可提升速度。
缺點: 價格高，因為每筆資料都做複製，所需磁碟數量即成倍數。

RAID 2 並沒有在商業上被使用。它做位元級的插敘，並以 Hamming Code 做錯誤更正，所需磁碟陣列太大並不實用。



RAID 3 & 4
RAID 3 類似 RAID 0 將資料按順序平均分布在數個磁碟機上
RAID 3 增加一個磁碟機存放同位元 (parity)，當任一磁碟損毀，它上面的資料可以靠同位元做復原。
RAID 3 兼顧讀取速度與備援功能。

RAID 4 與 RAID 3 類似，但不用位元組插敘，而是使用資料塊 (blocks)。


RAID 5 & 6
RAID 5 與 RAID 4 一樣使用資料塊插敘，並計算後儲存同位元。但是 RAID 5 不是將同位元集中在一個磁碟中，而是平均分散在所有磁碟裡。
RAID 5 有 RAID 3/4 的好處，同時又可避免同位元磁碟被過度使用的缺點。
RAID 6 比 RAID 5 再多加一個同位元，可以容忍兩個磁碟機同時損毀。



RAID 10

又稱為 RAID 1+0，因為它將資料做完全備援 (RAID 1) 如右圖的上兩個磁碟與下兩個磁碟；再將幾個 RAID 1組成 RAID 0 做插敘

同時擁有高讀寫速度與備援功能。它也有機會容忍超過一台磁碟機損毀

「備份」通常指資料的一個靜態副本
「備援」則指動態的、系統持續運作中的救援措施。

資料備份：組織定期的備份資料，為求備份完整，會整個磁碟做複製。
磁碟陣列容錯(RAID)：在運算中維護資料的完整性與可用性。
異地備援[遠端即時備份]：透過網際網路或專線，即時的在遠端建立備份。一旦系統需要復原的話，遠端所儲存的是最新的備份。
備援伺服器：不只備份資料，還有相同的伺服器做故障復原 (failover)。
備援服務：整個系統完整複製 (可能在另一個地方)，一旦主機房主機房因故無法運作，備援服務能在幾分鐘內啟動。





```
