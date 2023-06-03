Mempelajari Tentang Router

Cisco memiliki 3 mode
1. user exec mode 
2. privillaged exec mode
3. global exxec mode

untuk ke privillaged exec mode ketik "enable"
untuk ke global exec mode ketik "configure terminal" atau "conf t"
syarat masuk ke global exec mode harus berada di privillaged exec mode terlebih dahulu
untuk kembali ke exec mode sebelumnya ketik "exit"

Pemberian nama pada router 
"hostname nama_router"

juga bisa menerapkan password
password untuk exec mode
terlebih dahulu berada pada global exec mode
ketik "enable password contoh_password"

untuk melihatnya ketik exit dua kali hingga ke user exec mode
kemudian klik "enable" dan masukkan password yg sudah dikonfigurasi sebelumnya

kemudian pemberian password pada privillage exec mode
pertama masuk ke global exec mode "conf t"
ketik "line console 0"
kemudian "password contoh_password"
dan aktifkan dengan ketik "login"
kemudian "exit" dan "exit"
untuk menerapkannya

hanya saja password tersebut disimpan di sebuah file dengan format plaintext
masuk ke privillage mode kemudian tampilkan filenya ketik "show running-config"
maka akan muncul password yang telah kita buat. Password tersebut tampil karena tidak terenskripsi 

tetapi kita akan membuat password terenskripsi 
langkah pertama ialah masuk ke global user dengan "conf t"
kemudian ketik "enable secret passwordnya"
password ini akan menggantikan password yang tidak terenskripsi
tes dengan exit sampai ke user exec mode
kemudian masuk ke privillage exec mode dengan password yang terbaru

kemudian kita bisa lihat password terenskripsi dengan "show running-config"

kemudian kita akan konfigurasi motd(massage of the day)
pertama masuk ke global user
kemudian ketik "banner motd &pesannya&"
penerapannya ada pada user exec mode atau mode paling awal.

running config berisi file konfigurasi yang saat ini berjalan file configurasi
ini berjalan pada ram jadi saat cisco router ini mati maka konfigurasi sebelumnya 
akan hilang maka dari itu.

masuk ke privillage exec mode kemudian copy running config ke startup config
ketik "copy running-config startup-config"


