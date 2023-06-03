Pada Konfigurasi ini kedua router dihubungkan dengan kabel cross over
agar setiap pc dapat terhubung maka router harus memiliki Network interface yang berbeda
misal 192.168.10.0 
jadi 
router0 : 192.168.10.1
router1 : 192.168.10.2
kemudian mengkonfigurasi agar setiap pc dapat terhubung.
pada router0
masuk ke global exec mode kemudian 
ketik "ip route network_address_pc_padarouter1 subnetmask default_gateway_router1"
jadi "ip route 192.168.2.0 255.255.255.0 192.168.10.2"
untuk cek, masuk ke privillage exec mode kemudian ketik "show ip route" 

pada router1
lakukan hal sama tapi sebaliknya