# Файловые хранилища - NFS, SMB, FTP


Создаем файл в директории /mnt/upload, предварительно авторизовываясь:
![alt-текст](https://github.com/awesomenmi/nfs/blob/master/Screenshot%20from%202020-07-12%2020-36-57.png)

Содержимое лога /var/log/krb5kdc.log на сервере:
```
[root@ns vagrant]# tail -f /var/log/krb5kdc.log 
Jul 12 20:30:38 ns.otus.test krb5kdc[800](info): set up 4 sockets
Jul 12 20:30:38 ns.otus.test krb5kdc[812](info): commencing operation
Jul 12 20:36:08 ns.otus.test krb5kdc[812](info): AS_REQ (6 etypes {16 23 20 18 19 17}) 192.168.50.100: NEEDED_PREAUTH: nfs/client.otus.test@OTUS.TEST for krbtgt/OTUS.TEST@OTUS.TEST, Additional pre-authentication required
Jul 12 20:36:08 ns.otus.test krb5kdc[812](info): AS_REQ (6 etypes {16 23 20 18 19 17}) 192.168.50.100: ISSUE: authtime 1594575368, etypes {rep=16 tkt=16 ses=16}, nfs/client.otus.test@OTUS.TEST for krbtgt/OTUS.TEST@OTUS.TEST
Jul 12 20:36:08 ns.otus.test krb5kdc[812](info): AS_REQ (6 etypes {16 23 20 18 19 17}) 192.168.50.100: NEEDED_PREAUTH: host/client.otus.test@OTUS.TEST for krbtgt/OTUS.TEST@OTUS.TEST, Additional pre-authentication required
Jul 12 20:36:08 ns.otus.test krb5kdc[812](info): AS_REQ (6 etypes {16 23 20 18 19 17}) 192.168.50.100: ISSUE: authtime 1594575368, etypes {rep=16 tkt=16 ses=16}, host/client.otus.test@OTUS.TEST for krbtgt/OTUS.TEST@OTUS.TEST
Jul 12 20:36:08 ns.otus.test krb5kdc[812](info): TGS_REQ (6 etypes {20 18 19 17 16 23}) 192.168.50.100: ISSUE: authtime 1594575368, etypes {rep=16 tkt=16 ses=16}, host/client.otus.test@OTUS.TEST for nfs/ns.otus.test@OTUS.TEST
Jul 12 20:36:15 ns.otus.test krb5kdc[812](info): AS_REQ (6 etypes {20 18 19 17 16 23}) 192.168.50.100: NEEDED_PREAUTH: vagrant@OTUS.TEST for krbtgt/OTUS.TEST@OTUS.TEST, Additional pre-authentication required
Jul 12 20:36:29 ns.otus.test krb5kdc[812](info): AS_REQ (6 etypes {20 18 19 17 16 23}) 192.168.50.100: ISSUE: authtime 1594575389, etypes {rep=16 tkt=16 ses=16}, vagrant@OTUS.TEST for krbtgt/OTUS.TEST@OTUS.TEST
Jul 12 20:36:33 ns.otus.test krb5kdc[812](info): TGS_REQ (6 etypes {20 18 19 17 16 23}) 192.168.50.100: ISSUE: authtime 1594575389, etypes {rep=16 tkt=16 ses=16}, vagrant@OTUS.TEST for nfs/ns.otus.test@OTUS.TEST
```
