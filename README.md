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
Türkiye'de çalıştığı tespit edilenler:
```
sudo ./libdpitunnel-cli-x64.so -doh -doh-server https://dns.google/dns-query -ttl 3 -ca-bundle-path "./ca.bundle" -desync-attacks disorder_fake
sudo ./dpitunnel-cli-amd64 -doh -doh-server https://1.1.1.1/dns-query -wrong-seq -ca-bundle-path "./ca.bundle" -desync-attacks split_fake
```
# Openwrt bağımlılık:
```
opkg install libatomic libstdcpp
```
