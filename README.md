Releases kısmındaki binaryleri veya .so dosyalarını kullnarak çalıştırın. Detaylı bilgi için ana repoya bakabilirsiniz.
https://github.com/nomoresat/DPITunnel-cli

# İSS'lerin çoğu için bu 2 profilden biri yeterli olacaktır:
ca.bundle dosyasını kendiniz oluşturabilirsiniz
```
/etc/ssl/certs/ca-certificates.crt
```
veya releases kısmından indirebilirsiniz.

```bash
--ca-bundle-path=./ca.bundle --desync-attacks=fake,disorder_fake --split-position=2 --auto-ttl=1-4-10 --min-ttl=3 --doh --doh-server=https://dns.google/dns-query --wsize=1 --wsfactor=6
--ca-bundle-path=./ca.bundle --desync-attacks=fake,disorder_fake --split-position=2 --wrong-seq --doh --doh-server=https://dns.google/dns-query --wsize=1 --wsfactor=6
```
Türkiye'de kesin çalışan:
```
sudo ./libdpitunnel-cli-x64.so -doh -doh-server https://dns.google/dns-query -ttl 3 -ca-bundle-path "./ca.bundle" -desync-attacks disorder_fake
```
# Openwrt bağımlılık:
```
opkg install libatomic libstdcpp
```
