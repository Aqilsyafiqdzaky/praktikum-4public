[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/oYnIPZ_t)
|        Name       |     NRP    |   Kelas   |
| ------------------| ---------- | --------- |
| Aqil Syafiq Dzaky | 5025241200 |     A     |



## Put your topology config image here! 

<img width="1760" height="788" alt="image" src="https://github.com/user-attachments/assets/9e0b8ab5-87b3-40ba-ad8c-b884d0a579d1" />


## Put your GNS3 Project file here!

https://github.com/Praktikum-NETICS-2025/jarkom-modul-4-revisi-Aqilsyafiqdzaky/blob/main/praktikum-4%20(1).gns3project

<br>

## Soal 1

> Lakukan subnetting pada topologi diatas menggunakan metode VLSM: [Referensi](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/tree/master/Modul-4/Subnetting#2-vlsm-variable-length-subnet-masking)  
*Cantumkan juga tabel dan diagram pembagian subnet pada laporan praktikum*.


> _Subnet the topology above using the VLSM method: [Reference](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/tree/master/Modul-4/Subnetting#2-vlsm-variable-length-subnet-masking)_  
_Also include the subnet table and diagram in the lab report._

**Answer:**

- Screenshot

  <img width="1397" height="392" alt="image" src="https://github.com/user-attachments/assets/6d379f76-efaa-4498-a95b-d549e89ac1fd" />



- Explanation

  Subneting dengan metode VLSM berfokus pada banyaknya PC yang ada (semakin banyak, semakin di prioritaskan). Subneting diurutkan berdasarkan banyaknya PC dengan IP yang terus berurutan sampai PC terakhir (termasuk router)

<br>

## Soal 2

> Buatlah agar router-2 dapat melakukan koneksi ke internet. [Dapat menggunakan static routing].

> _Make sure router-2 can connect to the internet. [Can use static routing]._

**Answer:**

- Screenshot

  <img width="886" height="588" alt="image" src="https://github.com/user-attachments/assets/1e7635ce-137a-4a5d-95ce-bc25ad46759d" />


- Explanation

  Pada soal ini pertama saya memastikan iptables terinstal di router 3 agar dapat meneruskan internet ke router 2. Lalu untuk mengetes apakah router 2 sudah terhubung ke internet saya melakukan ping ke google.com.

<br>

## Soal 3

> Setelah mengimplementasi subnetting, buatlah agar seluruh topologi dapat terhubung. Lakukan Dynamic Routing pada topologi tersebut.
*Pastikan seluruh node yang ada dapat mengakses internet*.

> _After implementing subnetting, ensure the entire topology is connected. Perform dynamic routing on the topology._  
_Ensure all existing nodes can access the internet._

**Answer:**

- Screenshot

  router-1 :
  
  <img width="800" height="528" alt="image" src="https://github.com/user-attachments/assets/1d4ec17a-298b-4296-9c34-1eff2e1727d2" />

  router-2 :
  
  <img width="800" height="532" alt="image" src="https://github.com/user-attachments/assets/11eb9cdd-022c-47b6-908d-661f19b9f7e6" />

  router-3 :
  
  <img width="795" height="538" alt="image" src="https://github.com/user-attachments/assets/d62425e3-62c2-4f8d-adb9-2f118388c55d" />

  router-4 :
  
  <img width="802" height="531" alt="image" src="https://github.com/user-attachments/assets/5963f4f9-2cdb-46cc-b1cb-f2b6a2fa7da5" />

  router-5 :
  
  <img width="800" height="527" alt="image" src="https://github.com/user-attachments/assets/1b4d541e-2d56-476d-8c9d-26ba85953580" />

  IT-PC-1 :
  
  <img width="792" height="535" alt="image" src="https://github.com/user-attachments/assets/a978174b-05f0-42a9-a100-13554de141b5" />

  IT-PC-2 :
  
  <img width="795" height="530" alt="image" src="https://github.com/user-attachments/assets/47830a12-3da1-4166-ae40-4da7d72b2404" />

  IT-PC-3 :
  
  <img width="807" height="527" alt="image" src="https://github.com/user-attachments/assets/08249127-a1ec-42b5-bf8d-a9a5c3f2fb1c" />

  DB-Server-1 :
  
  <img width="806" height="536" alt="image" src="https://github.com/user-attachments/assets/e6fc62a1-761a-492e-a87c-d4e30013123b" />

  DB-Server-2 :
  
  <img width="807" height="530" alt="image" src="https://github.com/user-attachments/assets/a49c3acb-17d4-480c-b70d-caa84102a84c" />

  Web-Server-1 :
  
  <img width="803" height="530" alt="image" src="https://github.com/user-attachments/assets/951eb9b3-7cb9-46ff-a72b-75c5c3320587" />

  Web-Server-2 :
  
  <img width="788" height="526" alt="image" src="https://github.com/user-attachments/assets/d40fd3d0-71c0-47ed-8a54-e51dd7af9980" />

  HR-PC-1 :
  
  <img width="807" height="532" alt="image" src="https://github.com/user-attachments/assets/28004181-82ef-460d-ab9f-991a5f976045" />

  HR-PC-2 :
  
  <img width="803" height="532" alt="image" src="https://github.com/user-attachments/assets/abb652ce-0e51-4f88-8d0d-6e207ce38d35" />

- Explanation

  Untuk mengerjakan soal ini, saya hanya mengikuti modul.

  untuk semua router :
  ```
  cd /usr/lib/frr
  ./zebra -d
  ./ripd -d
  ./mgmtd -d
  
  vtysh

  conf t
  router rip
  ```

  hanya berbeda di network saja :
  router-1 :
  ```
  network 10.62.2.240/30
  network 10.62.2.0/23
  ```

  router-2 :
  ```
  network 10.62.2.244/30
  network 10.62.2.128/28
  network 10.62.2.144/27
  ```
  router-3 :
  ```
  network 10.62.2.240/30
  network 10.62.2.244/30
  network 10.62.2.248/30
  ```
  router-4 :
  ```
  network 10.62.2.248/30
  network 10.62.2.176/27
  network 10.62.2.208/27
  network 10.62.2.252/30
  ```
  router-5 :
  ```
  network 10.62.2.252/30
  network 10.62.0.0/23
  ```
  
<br>

## Soal 4

> Lakukan setup web server dengan file html di attachment berikut: [ Attachment ](https://drive.google.com/file/d/199qwfTNJCkxDV7mdO-MsaDdApkmKsnAG/view?usp=sharing)  menggunakan nginx pada “Web-Server-1” dan “Web-Server-2”.  
*Config dibebaskan kepada praktikkan dengan catatan menggunakan port 80*.

> _Set up a web server with the HTML file in the following attachment: [ Attachment ](https://drive.google.com/file/d/199qwfTNJCkxDV7mdO-MsaDdApkmKsnAG/view?usp=sharing) using nginx on “Web-Server-1” and “Web-Server-2”._
_Configuration is free to practice, but note that it uses port 80._

**Answer:**

- Screenshot

  Web-Server-1 :

  <img width="820" height="538" alt="image" src="https://github.com/user-attachments/assets/28fa191e-2de0-4e5d-8b6c-450e6294123f" />


  Web-Server-2 :

  <img width="800" height="542" alt="image" src="https://github.com/user-attachments/assets/5d184cce-8d4a-481f-9512-b8e89d321666" />


- Explanation

  Pada soal ini saya hanya menginstall nginx pada Web-Server dan mengcopy file yang ada di soal :

  ```
  apt-get update
  apt-get install ngingx

  nano /var/www/html/index.html
  ```

  lalu isi sesuai di soal

  ```
  service nginx restart
  ```

  test curl di node lain
  ```
  curl 10.62.2.178
  curl 10.62.2.210
  ```

  
<br>

## Soal 5

> Kalian diminta untuk melakukan drop semua paket TCP yang masuk  ke subnet HR dengan port 1337 dan 4444. Lakukan testing dengan netcat.

> _You are asked to drop all incoming TCP packets to the HR subnet with ports 1337 and 4444. Test with netcat._

**Answer:**

- Screenshot

  <img width="1918" height="435" alt="image" src="https://github.com/user-attachments/assets/52ea8c84-3c45-42bc-b20a-b64191329667" />


- Explanation

  Pada soal ini saya menginstall iptables router 5 untuk menambah aturan pada firewall

  di router 5 :

  ```
  pt-get update
  apt-get install iptables

  iptables -A FORWARD -p tcp --dport 1337 -d 10.62.0.0/23 -j DROP
  iptables -A FORWARD -p tcp --dport 4444 -d 10.62.0.0/23 -j DROP
  ```

  lakukan test dengan
  ```
  nc -l -p [PORT] (untuk di HR-PC)
  nc [IP Receiver] [PORT] (untuk diluar HR-PC)
  ```
  
<br>

## Soal 6

> Lakukan pembatasan sehingga koneksi SSH pada semua Web Server hanya dapat dilakukan oleh user yang berada pada node IT-PC-1, IT-PC-2, dan IT-PC-3. 

> _Implement restrictions so that SSH connections to all Web Servers can only be made by users on nodes IT-PC-1, IT-PC-2, and IT-PC-3._

**Answer:**

- Screenshot

  IT-PC :

  <img width="1918" height="987" alt="image" src="https://github.com/user-attachments/assets/95cf5fa5-eec9-419a-ba02-4140ed751268" />

  Bukan IT-PC :

  <img width="1918" height="1007" alt="image" src="https://github.com/user-attachments/assets/c4cc2e43-423a-4b64-9c69-c0a83e2c0586" />


- Explanation

  Pada soal ini saya melakukannya seperti nomor 5 namun saya mengubah pengetesan menjadi dengan ncat karena saat mencoba dengan ssh saya saya selalu di refuse bahkan sebelum aturan dipasang.

  Install iptables
  ```
  apt-get update
  apt-get install iptables
  ```

  Terapkan aturan dimana ncat hanya bisa di terima dari ip IT-PC lalu drop semua selain IT-PC(IT-PC masih di terima karena aturannya sudah diterapkan dahulu)
  ``` 
  iptables -A FORWARD -p tcp --dport 22 -s 10.62.2.2/25 -d 10.62.2.178/27 -j ACCEPT
  iptables -A FORWARD -p tcp --dport 22 -s 10.62.2.52/25 -d 10.62.2.178/27 -j ACCEPT
  iptables -A FORWARD -p tcp --dport 22 -s 10.62.2.77/25 -d 10.62.2.178/27 -j ACCEPT
  iptables -A FORWARD -p tcp --dport 22 -d 10.62.2.178/27 -j DROP
  
  iptables -A FORWARD -p tcp --dport 22 -s 10.62.2.2/25 -d 10.62.2.210/27 -j ACCEPT
  iptables -A FORWARD -p tcp --dport 22 -s 10.62.2.52/25 -d 10.62.2.210/27 -j ACCEPT
  iptables -A FORWARD -p tcp --dport 22 -s 10.62.2.77/25 -d 10.62.2.210/27 -j ACCEPT
  iptables -A FORWARD -p tcp --dport 22 -d 10.62.2.210/27 -j DROP
  ```
  
  test dengan natcat :
  ```
  nc -l -p [PORT] (untuk di Web-Server)
  nc [IP Receiver] [PORT] (untuk diluar Web-Server)
  ```

<br>

## Soal 7

> Semua subnet hanya dapat mengakses semua DB-Server pada port 80 dan 443 (DB-Server-1 dan DB-Server-2) pada hari Senin-Sabtu, pukul 07:00- 22:00.

> _All subnets can only access all DB-Servers on ports 80 and 443 (DB-Server-1 and DB-Server-2) on Monday-Saturday, 07:00-22:00._

**Answer:**

- Screenshot

  Sesuai waktu :
  <img width="1918" height="1020" alt="image" src="https://github.com/user-attachments/assets/356ff16c-1ad7-49d6-97c5-ec1d4bd07e38" />

  salah waktu :
  <img width="1918" height="1007" alt="image" src="https://github.com/user-attachments/assets/1a0d71a0-e322-4666-8ffe-3b269c4ca604" />



- Explanation

  Untuk megnerjakan soal ini saya melakukannya seperti sebelumnya namun menambah aturan terkait waktu, dimana jika melakukan ncat di luar hari yang ditentukan maka pesan tidak akan masuk.

  di router-2 :

  Install iptables :
  ```
  apt-get update
  apt-get install iptables
  ```

  tambah aturan :
  ```
  iptables -A FORWARD -p tcp --dport 80 -d 10.62.2.130/28 \
  -m time --timestart 07:00 --timestop 22:00 \
  --weekdays Mon,Tue,Wed,Thu,Fri,Sat -j ACCEPT
  
  iptables -A FORWARD -p tcp --dport 80 -d 10.62.2.146/27 \
  -m time --timestart 07:00 --timestop 22:00 \
  --weekdays Mon,Tue,Wed,Thu,Fri,Sat -j ACCEPT
  
  iptables -A FORWARD -p tcp --dport 443 -d 10.62.2.130/28 \
  -m time --timestart 07:00 --timestop 22:00 \
  --weekdays Mon,Tue,Wed,Thu,Fri,Sat -j ACCEPT
  
  iptables -A FORWARD -p tcp --dport 443 -d 10.62.2.146/27 \
  -m time --timestart 07:00 --timestop 22:00 \
  --weekdays Mon,Tue,Wed,Thu,Fri,Sat -j ACCEPT
  
  iptables -A FORWARD -p tcp --dport 80 -d 10.62.2.130/28 -j DROP
  iptables -A FORWARD -p tcp --dport 80 -d 10.62.2.146/27 -j DROP
  
  iptables -A FORWARD -p tcp --dport 443 -d 10.62.2.130/28 -j DROP
  iptables -A FORWARD -p tcp --dport 443 -d 10.62.2.146/27 -j DROP
  ```
  
  test dengan :
  ```
  nc -l -p [PORT] (untuk di DB-Server)
  nc [IP Receiver] [PORT] (untuk diluar DB-Server)
  ```


<br>

## Soal 8

> Kemudian, buat agar “Web-Server-1” dan “Web-Server-2” hanya memperbolehkan traffic bertipe HTTP.

> _Then, make sure that “Web-Server-1” and “Web-Server-2” only allow HTTP type traffic._

**Answer:**

- Screenshot

  http :
  <img width="803" height="532" alt="image" src="https://github.com/user-attachments/assets/6ebf62f8-69fd-4e09-b127-b0175201d460" />

  non http :
  <img width="817" height="540" alt="image" src="https://github.com/user-attachments/assets/56431841-ec18-4948-acaf-e71214a2d02f" />



- Explanation

  Untuk mengerjakan soal ini pertama saya menghapu semua autran dari nomor 6 dahulu dengan :
  ```
  iptables -F
  iptables -X
  ```

  lalu menambahkan aturan baru yang hanya memperbolehkan http :
  ```
  iptables -A INPUT -i lo -j ACCEPT
  iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
  iptables -A INPUT -p tcp --dport 80 -j ACCEPT
  iptables -A INPUT -j DROP
  ```

  test harus berhasil dengan :
  ```
  curl http://10.62.2.178      
  curl http://10.62.2.210
  ```

  test harus gagal dengan :
  ```
  ncat -vz 10.62.2.178 22 (hanya contoh)
  ```
  
<br>

## Soal 9

> Pilih salah satu Subnet dan lakukan blokir terhadap semua request protokol ICMP (ping) dari luar subnet terhadap subnet tersebut.

> _Select one of the Subnets and block all ICMP protocol requests (ping) from outside the subnet to that subnet._

**Answer:**

- Screenshot

  Ping di luar subnet :
  Web-Server
  <img width="802" height="515" alt="image" src="https://github.com/user-attachments/assets/7149bfb5-9706-4cfb-b3fd-fd6b936ca3d8" />

  HR-PC
  <img width="811" height="531" alt="image" src="https://github.com/user-attachments/assets/84fa9d5c-0fd9-46c4-8fac-f4098b4b5b15" />

  
  DB-Server
  <img width="812" height="532" alt="image" src="https://github.com/user-attachments/assets/ac09a98e-13c9-442c-89ef-fcf4af9ae5a1" />

  ping didalam subnet :
  <img width="800" height="523" alt="image" src="https://github.com/user-attachments/assets/bad75f3e-6b13-4b60-9a84-7bd8e16f541a" />



- Explanation

  Pada soal ini saya hanya menerapkan aturan untuk memblokir semua ping yang masuk ke router satu, dan karena itu ping didalam subnet tidak akan diblokir karena tidak melwati router 1

  pada router-1 :

  install iptables 
  ```
  apt-get update
  apt-get install iptables
  ```

  terapkan aturan :
  ```
  iptables -A FORWARD -p icmp -d 10.62.2.0/25 ! -s 10.62.2.0/25 -j DROP
  ```

<br>

## Soal 10

> Konfigurasikan fitur logging untuk melakukan log terhadap seluruh paket yang di-DROP pada lalu lintas setiap node.

> _Configure the logging feature to log all dropped packets on each node's traffic._

**Answer:**

- Screenshot

  router-1 :
  <img width="807" height="543" alt="image" src="https://github.com/user-attachments/assets/de5c635a-cafa-4ed3-b947-cb5003e05855" />
  <img width="800" height="540" alt="image" src="https://github.com/user-attachments/assets/a7732637-5826-4a64-924e-22bba071cf82" />


  router-2 :
  <img width="807" height="537" alt="image" src="https://github.com/user-attachments/assets/84a0ea5b-1fff-457d-91a3-7374e7dddc9b" />
  <img width="806" height="537" alt="image" src="https://github.com/user-attachments/assets/40255c60-2b1c-4a25-a724-4ce31bd9f8e2" />


  router-3 :
  <img width="806" height="535" alt="image" src="https://github.com/user-attachments/assets/8270d935-375b-4a64-88be-d69af437637c" />
  <img width="800" height="541" alt="image" src="https://github.com/user-attachments/assets/cb9f5ec6-2588-4f73-9f50-b902da8a2546" />


  router-4 :
  <img width="800" height="532" alt="image" src="https://github.com/user-attachments/assets/9a32b810-2772-45b8-a85f-c6f5ae2430c9" />
  <img width="797" height="537" alt="image" src="https://github.com/user-attachments/assets/44c2d79a-6344-4261-91a0-3d2c0c99a016" />


  router-5 :
  <img width="802" height="535" alt="image" src="https://github.com/user-attachments/assets/e4a12c4e-b561-4c4a-bbb0-0b8ac4396957" />
  <img width="803" height="525" alt="image" src="https://github.com/user-attachments/assets/7e801e9c-12c5-42c6-961d-42f2b81b7c52" />


- Explanation

  Pada soal ini saya hanya menambah perintah berikut di semua router :

  ```
  iptables -A INPUT   -j LOG --log-prefix "DROP INPUT: "
  iptables -A FORWARD -j LOG --log-prefix "DROP FORWARD: "
  ```

  lalu menambahkan DROP :
  ```
  iptables -A INPUT -j DROP
  iptables -A FORWARD -j DROP
  ```

  lalu saya cek dengna :
  ```
  dmesg -w
  ```


<br>
  
## Problems

## Revisions (if any)
