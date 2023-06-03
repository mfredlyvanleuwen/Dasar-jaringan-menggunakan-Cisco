Dari topologi kedua sebelumnya
2 pc akan diubah ip addressnya yaitu pc 2 dan pc 3
pada ip address yang 192.168.1.3 dan 192.168.1.4 akan diubah menjadi 
192.168.2.1 dan 192.168.2.2.


kemudian hapus kable straight yang menghubungkan switch dengan ip address 192.168.2.1 
dan 192.168.2.2.

menentukan Network Address pada pc0 dan pc1 yaitu 192.168.1.0
Network address pada pc2 dan pc3 yaitu 192.168.2.0

ping 192.168.2.1 pada pc0 
maka hasil akan RTO karena dalam jaringan komputer dasar setiap perangkat bisa 
terhubung dengan perangkat lain dengan network address yang sama. Disini pc0 memiliki 
network address yang berbeda pada pc2.

agar perangkat dalam network address yang berbeda dapat berkomunikasi/terhubung
maka memerlukan router. Router pada dasarnya adalah sebuah komputer yang memiliki lebih dari satu network
interface yang dimana setiap network interfacenya akan ditempatkan dibeberapa network addres yang berbeda.
Jadi disini sebuah router berperan untuk menjembatani komunikasi antara perangkat yang memiliki network addres yang berbeda.

Untuk menkonfigurasi interface pada router masuk ke global user mode terlebih dahulu
ketik "enable" kemudian "conf t"
kemudian ketik "interface fa0/0"
selanjutnya konfigurasi ip addres "ip address 192.168.1.254 255.255.255.0"
yang perlu diperhatikan adalah ip addresnya harus satu network addres jika tidak maka 
tidak bisa terhubung
kemudian ketik "no shutdown"
selanjutnya "exit"
dan konfigurasi interface yang disebelahnya 
ketik "interface fa1/0"
kemudian "ip address 192.168.2.254 255.255.255.0"
"no shutdown"

lanjut dengan cek koneksi menggunakan ping dari pc0 ke router "ping 192.168.1.254" yaitu alamat interface sisi kiri router
berikutnya dari router ke pc, masuk ke privillage exec mode kemudian "ping 192.168.1.1" yaitu pc0

kemudian ping dari pc0 ke pc2 yang berbeda network address maka hasil akan RTO 
penyelesainnya adalah konfigurasi default gateway ke setiap pc.

Default gateway nya adalah alamat interface dari router jadi untuk yang pc0 dan pc1 
default gatewaynya : 192.168.1.254
pc2 dan pc3 : 192.168.2.254


