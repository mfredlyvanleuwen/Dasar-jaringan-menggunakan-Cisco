Perbedaan antara Router static dan router dinamic
Routing secara static ialah memasukkan network address secara manual ke routing tabel
sedangkan dinamic routing adalah mendata network address mana saja dari 
network address directly connected untuk dipertukarkan antar  router

Topologi disini dari Cisco04 sebelumnya 
hanya saja diubah menjadi routing dinamic menggunakan routing protokol
yaitu RIP(Routing information Protocol).

tapi sebelum itu harus menghapus konfigurasi static routing

pada router1
ketik "sh ip route" untuk menampilkan routing table
kemudian lihat ip static yang mau dihapus
dengan masuk ke privillage mode, command "no ip route N.A_yangmaudihapus subnetmask"
contoh disini "no ip route 192.168.1.0 255.255.255.0"
kemudian cek lagi dengan "sh ip route"
Lakukan hal yang sama pada router0

untuk mengkonfigurasi RIP pada cisco Router
halyang harus dilakukan ialah masuk ke global exec mode 
kemudian ketik "router rip"

pada Router0
yang directly connected adalah 192.168.1.0 dan 192.168.10.0
command "router rip"
kemudian "network 192.168.1.0"
	 "netwok 192.168.10.0"
ketika sudah selesai berarti router0 mulai melakukan pertukaran informasi 
dengan mengenalkan network addressnya ke router ke tetangganya
Kemudian lakukan hal serupa pada Router1.

Dalam kasus ini router0 akan memberitahukan kepada Router1 bahwasannya ia mengcover 2 network address yaitu 
192.168.1.0 dan 192.168.10.0 informasi ini lalu di terima oleh Router1 danakan digunakan untuk
memperbaharui routing tablenya sehingga router1 mengetahui keberadaan network address 192.168.1.0 melalui gateway
192.168.10.1 demikian juga router1 akan menginformasikan routing table nya ke router0.


