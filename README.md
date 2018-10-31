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

# 非技術性風險

裝置閉路監視系統時，應該儘量消除盲點 (blind spots)




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
 Many operating systems, file managers, and other software provide a facility where a file is not immediately deleted when the user requests that action. Instead, the file is moved to a holding area, making it easy for the user to undo a mistake. Similarly, many software products automatically create backup copies of files that are being edited, to allow the user to restore the original version, or to recover from a possible crash (autosave feature).

 Even when an explicit deleted file retention facility i>* s not provided or when the user does not use it, operating systems do not actually remove the contents of a file when it is deleted unless they are aware that explicit erasure commands are required, like on a solid-state drive. (In such cases, the operating system will issue the Serial ATA TRIM command or the SCSI UNMAP command to let the drive know to no longer maintain the deleted data.) Instead, they simply remove the file's entry from the file system directory, because this requires less work and is therefore faster, and the contents of the file—the actual data—remain on the storage medium. The data will remain there until the operating system reuses the space for new data. In some systems, enough filesystem metadata are also left behind to enable easy undeletion by commonly available utility software. Even when undelete has become impossible, the data, until it has been overwritten, can be read by software that reads disk sectors directly. Computer forensics often employs such software.

 Likewise, reformatting, repartitioning, or reimaging a system is unlikely to write to every area of the disk, though all will cause the disk to appear empty or, in the case of reimaging, empty except for the files present in the image, to most software.

 Finally, even when the storage media is overwritten, physical properties of the media may permit recovery of the previous contents. In most cases however, this recovery is not possible by just reading from the storage device in the usual way, but requires using laboratory techniques such as disassembling the device and directly accessing/reading from its components.[citation needed]

 The section on complications gives further explanations for causes of data remanence.
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
# 網路各層的攻擊手法
```
實體層

攻擊方式
搭接線路(網路與電話)進行訊號竊聽
私接線路變成隱匿通道(非控管中的線路)

-----------------------------------
防護建議
機房、機櫃、線路室及管道間進行存取控管
採用不同顏色區隔不同網段(安全區域)
定期的線路盤查
```
# 資料連結層 – 封包監聽

```
ARP flooding、ARP poisoning或ARP Poison Routing
在Broadcast Domain下無法被動監聽其他電腦間連線封包
ARP Spoofing攻擊強迫偽冒其他IP，讓攻擊者有機會監測到其他電腦間的通訊


攻擊手法
攻擊者使用ARP Broadcast封包告訴其他電腦，192.168.1.1的MAC是Attacker的MAC
其他電腦要傳送給192.168.1.1的封包會被送到Attacker
Attacker將封包錄下後轉送到真正的192.168.1.1

```

# 網路層 – Source Route
```
IP封包的路由通常是由Router所決定，啟用Source Route可以讓傳送者指定IP封包的傳送路徑
攻擊者運用Source Route的功能進行來源IP的偽冒(IP Spoofing)
讓偽冒來源IP的封包可照指定路徑送到目的伺服器
FW信任偽冒的來源IP未加以阻擋  (FW:防火牆)

防護建議
在防火牆或路由器上阻擋採用Source Route的封包
```

# IP Spoofing與ARP Spoofing
```
IP Spoofing使用偽造的來源位址來傳送IP封包，可能會採用受信任來源的IP 位址來嘗試規避防火牆
ARP Spoofing是指攻擊者取得區域網路上的資料封包甚至篡改封包，可讓網路上特定電腦或所有電腦無法正常連線
```

# 網路層 – Smurf Attack
```
藉由ICMP封包塞爆受害者網路頻寬的阻斷服務攻擊

攻擊手法
攻擊者(Attacker)偽冒受害者IP(Victim)發送大量Echo Request給B網段的Broadcast IP位址(B.255或B.0)
B網段所有電腦收到Echo Request封包，都回覆Echo Reply封包給Victim
導致Victim端頻寬被大量的Echo Reply封包所占用
```
# 網路層 – Ping of Death
```
攻擊者故意傳送一個大小超過65536位元的Ping封包給受害者(IP協定允許封包大於65536)

```
# 連線層 – SYN Flood
```
攻擊手法
攻擊者傳送大量的TCP SYN請求封包到受害伺服器
受害伺服器為每一個連線請求分配系統記憶體資源，導致系統連線資源被耗用殆盡，正常的連線無法建立
大量惡意的TCP SYN封包，其來源IP通常也都是偽冒的，因此無法以封鎖來源IP阻擋攻擊

防護建議
防火牆限制同來源IP的連線數量
請求ISP協助

```

# 連線層 – 分散式阻斷服務攻擊(1/3)
```
分散式阻斷服務攻擊(Distributed Denial-of-Service，簡稱DDoS)

攻擊者控制多部阻斷服務攻擊主機(DoS Agent)，對受害者發動大規模的阻斷服務攻擊
被攻擊的受害者為主要受害者，被控制的阻斷服務攻擊主機本身也是次要的受害者
其攻擊來源IP太多(數百至數千個)，通常很難透過防火牆封鎖來源IP

防護建議
請求ISP協助

```
# 連線層 – Session Hijacking
```
合法使用者建立連線後，攻擊者從中攔截或取代該連線
可分為兩種類型
主動型：攻擊者取代已建立之有效的連線
被動型：攻擊者攔截連線後只監聽連線內容
攻擊的步驟
追蹤連線過程
連線去同步化
注入攻擊者的封包
防護建議
採用IPSec或SSL雙向認證的加密連線


當攻擊者可以預測到Client下一個封包的序號時，就可以偽冒Client的IP送出封包給Server，達到攔截連線的攻擊
```
# 應用層 – DNS Poisoning
```
攻擊者藉由DNS伺服器的弱點，將錯誤的名稱解析植入DNS伺服器的快取區(Cache)中，導致DNS用戶端解析到錯誤的IP，使網路連線被導到惡意的伺服器

防護建議
修補已知的DNS伺服器弱點
區隔外部與內部DNS伺服器(不要forward到ISP的DNS)
```
# 應用層 – Brute force Login(1/2)
```
攻擊者透過通行碼猜測入侵應用系統的狀況相當常見，例如
TELNET login
SSH login
FTP login
SMTP AUTH
POP3 login
網路上有相當多的工具可自動進行通行碼猜測攻擊
Brutus
THC-Hydra

建議防護
限制同一帳戶連續簽入失敗之次數，若超過次數則延遲簽入一段時間或關閉帳號，發出警告訊息
強制使用者通行碼長度與複雜度
定期更換通行碼
```
















