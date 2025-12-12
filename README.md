[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/aRvIU2lf)
| Name           | NRP        | Kelas     |
| ---            | ---        | ----------|
| Aqil Syafiq Dzaky | 5025241200 | A |



## Put your topology config image here!

<img width="1536" height="751" alt="Topologi" src="https://github.com/user-attachments/assets/b8931d0c-b8a1-437b-99e8-25757f5ecdd9" />


## Put your GNS3 Project file here!

https://github.com/Praktikum-NETICS-2025/jarkom-modul-final-revisi-Aqilsyafiqdzaky/blob/main/FP.gns3project

<br>

## Soal 1

> Menggunakan metode VLSM, buatlah pembagian subnet untuk masing-masing gedung dengan cara yang seefisien mungkin!

> _Using the VLSM method, create subnets for each building as efficiently as possible!_

**Answer:**

- Screenshot

  <img width="1792" height="267" alt="image" src="https://github.com/user-attachments/assets/b6af3ef0-b2e0-4125-b13c-c04cece753ed" />



- Explanation

  Pada soal ini, saya membagi subnet berdasarkan gedung dan saya memulai subneting dari kebutuhan pc terbanyak.

<br>

## Soal 2

> Konfigurasi semua router agar bisa terhubung ke semua jaringan. Gunakan static routing dan uji dengan melakukan ping dari **Budapest** ke **Alekhine** dan dari **Ponziani** ke **Sicilian**!

> _Configure all routers to connect to all networks. Use static routing and perform testing by pinging from **Budapest** to **Alekhine** and from **Ponziani** to **Sicilian**!_

**Answer:**

- Screenshot

  ping Budapest -> Alekhine
  <img width="981" height="660" alt="ping budapast-alekhine" src="https://github.com/user-attachments/assets/f2a7b6c7-e25b-41e6-9032-2cbeaed07c1d" />

  ping Ponziani -> Sicilian
  <img width="991" height="646" alt="ping ponziani - sicilian" src="https://github.com/user-attachments/assets/f7d7218f-6e28-49d9-a1a7-e1cbc74f9f91" />



- Explanation

  Pada soal ini, saya menerapkan static routing dengan melakukan ip route di tiap subnet

- Budapest/Stafford/Client-Group-1/Client-Group-2 :
```
ip route add 10.62.42.0/30 via 10.62.32.1
ip route add 10.62.41.216/29 via 10.62.32.1
ip route add 10.62.41.208/29 via 10.62.32.1
ip route add 10.62.41.192/28 via 10.62.32.1

ip route add 10.62.41.128/26 via 10.62.32.1

ip route add 10.62.40.0/24 via 10.62.32.1
ip route add 10.62.41.0/25 via 10.62.32.1
ip route add 10.62.0.0/19 via 10.62.32.1

```

- Smith-Morra :
```
ip route add 10.62.41.216/29 via 10.62.42.2

ip route add 10.62.42.2/29 via 10.62.42.2
ip route add 10.62.41.208/29 via 10.62.42.2
ip route add 10.62.41.192/28 via 10.62.42.2

ip route add 10.62.41.128/26 via 10.62.42.2

ip route add 10.62.40.0/24 via 10.62.42.2
ip route add 10.62.41.0/25 via 10.62.42.2

```

- Flanchetto :
```
ip route add 10.62.41.208/29 via 10.62.41.218
ip route add 10.62.41.192/28 via 10.62.41.218
ip route add 10.62.32.0/21 via 10.62.42.1

ip route add 10.62.41.128/26 via 10.62.41.219
ip route add 10.62.40.0/24 via 10.62.41.218
ip route add 10.62.41.0/25 via 10.62.41.218

ip route add 10.62.0.0/19 via 10.62.42.1
ip route add 10.62.32.0/21 via 10.62.42.1
```

- Zwsichenzug :
```
ip route add 10.62.41.192/28 via 10.62.41.211
ip route add 10.62.42.0/30 via 10.62.41.217
ip route add 10.62.32.0/21 via 10.62.41.217

ip route add 10.62.41.0/25 via 10.62.41.211
ip route add 10.62.41.128/26 via 10.62.41.219

ip route add 10.62.40.0/24 via 10.62.41.211
ip route add 10.62.0.0/19 via 10.62.41.217

```

- Zugzwang :
```
ip route add 10.62.41.216/29 via 10.62.41.209
ip route add 10.62.42.0/30 via 10.62.41.209
ip route add 10.62.32.0/21 via 10.62.41.209

ip route add 10.62.41.128/26 via 10.62.41.209
ip route add 10.62.0.0/19 via 10.62.41.209
```

- Alekhine/DNS-Group-1/Koro-Kann :
```
ip route add 10.62.41.208/29 via 10.62.41.193
ip route add 10.62.41.216/29 via 10.62.41.193
ip route add 10.62.42.0/30 via 10.62.41.193

ip route add 10.62.32.0/21 via 10.62.41.193
ip route add 10.62.0.0/19 via 10.62.41.193
ip route add 10.62.40.0/24 via 10.62.41.193
ip route add 10.62.41.0/25 via 10.62.41.193
ip route add 10.62.41.128/26 via 10.62.41.193
```

- Ponziani/DHCP-Group-1/RuyLopez :
```
ip route add 10.62.41.216/29 via 10.62.41.129
ip route add 10.62.41.208/29 via 10.62.41.129
ip route add 10.62.41.0/25 via 10.62.41.129

ip route add 10.62.42.0/30 via 10.62.41.129
ip route add 10.62.32.0/21 via 10.62.41.129
ip route add 10.62.0.0/19 via 10.62.41.129

ip route add 10.62.40.0/24 via 10.62.41.129
ip route add 10.62.41.192/28 via 10.62.41.129
```

- Lucena :
```
ip route add 10.62.41.208/29 via 10.62.41.218
ip route add 10.62.41.0/25 via 10.62.41.218

ip route add 10.62.42.0/30 via 10.62.41.217
ip route add 10.62.32.0/21 via 10.62.41.217
ip route add 10.62.0.0/19 via 10.62.41.217

ip route add 10.62.40.0/24 via 10.62.41.218
ip route add 10.62.41.192/28 via 10.62.41.218
```

- Sicilian/Webserver-Group-1 :
```
ip route add 10.62.41.208/29 via 10.62.41.1
ip route add 10.62.41.216/29 via 10.62.41.1
ip route add 10.62.41.128/26 via 10.62.41.1 

ip route add 10.62.42.0/30 via 10.62.41.1
ip route add 10.62.0.0/19 via 10.62.41.1
ip route add 10.62.32.0/21 via 10.62.41.1
ip route add 10.62.40.0/24 via 10.62.41.1
ip route add 10.62.41.192/28 via 10.62.41.1
```

- Client-Group-3/Blackmar-Diemer

```
ip route add 10.62.32.0/21 via 10.62.0.1
ip route add 10.62.42.0/30 via 10.62.0.1
ip route add 10.62.41.216/29 via 10.62.0.1
ip route add 10.62.41.128/26 via 10.62.0.1

ip route add 10.62.40.0/24 via 10.62.0.1
ip route add 10.62.41.0/25 via 10.62.0.1
ip route add 10.62.41.192/28 via 10.62.0.1
ip route add 10.62.41.208/29 via 10.62.0.1
```

- Slave/Web-Server-2
```
ip route add 10.62.41.0/25 via 10.62.40.1
ip route add 10.62.41.208/29 via 10.62.40.1
ip route add 10.62.41.216/29 via 10.62.40.1
ip route add 10.62.41.128/26 via 10.62.40.1
ip route add 10.62.42.0/30 via 10.62.40.1

ip route add 10.62.0.0/19 via 10.62.40.1
ip route add 10.62.32.0/21 via 10.62.40.1
ip route add 10.62.41.192/28 via 10.62.40.1
```

- petrov 
```

ip route add 10.62.0.0/19 via 10.62.41.209
ip route add 10.62.32.0/21 via 10.62.41.209
ip route add 10.62.42.0/30 via 10.62.41.209
ip route add 10.62.41.216/29 via 10.62.41.209
ip route add 10.62.41.128/26 via 10.62.41.209

ip route add 10.62.41.0/25 via 10.62.41.211
ip route add 10.62.41.192/28 via 10.62.41.211
ip route add 10.62.40.0/24 via 10.62.41.211
```

<br>

## Soal 3

> Berikan seluruh client (**Blackmar-Diemer, Budapest,** dan **Stafford**) IP secara dinamis dari DHCP. Range IP dibebaskan, namun tunjukkan bahwa mereka mendapatkan IP secara dinamis!

> _Assign all clients (**Blackmar-Diemer, Budapest,** and **Stafford**) dynamic IP addresses via DHCP. You may use any IP range you would like, but prove that they receive IP addresses dynamically!_

**Answer:**

- Screenshot

  Black-Diemer
  <img width="968" height="648" alt="image" src="https://github.com/user-attachments/assets/5f76e079-d5e1-45f2-8eee-3c24aaabcc26" />

  Budapest
  <img width="987" height="645" alt="image" src="https://github.com/user-attachments/assets/d4b38c40-a1df-4fb0-9865-c6b94ddd838b" />

  Stafford
  <img width="990" height="647" alt="image" src="https://github.com/user-attachments/assets/5c3ea6c5-bada-43ac-823f-97758867f546" />


- Explanation

  Pada soal ini pertama saya melakukan set up pada DHCP server :

  install DHCP-Server
  ```
  apt-get update
  apt-get install isc-dhcp-server -y
  ```
  isi interfaces pada  "/etc/default/isc-dhcp-server"
  ```
  INTERFACESv4="eth0"
  ```

  isi subnet untuk DHCP pada "/etc/dhcp/dhcpd.conf"
  ```
  subnet 10.62.41.128 netmask 255.255.255.192 {
    range 10.62.41.140 10.62.141.50;
    option routers 10.62.41.129;
    option broadcast-address 10.62.41.191;
    option domain-name-servers 8.8.8.8;
    default-lease-time 300;
    max-lease-time 6900;
  }
  
  subnet 10.62.0.0 netmask 255.255.224.0 {
      range 10.62.0.10 10.62.0.20;
      option routers 10.62.0.1;
      option broadcast-address 10.62.31.255;
      option domain-name-servers 8.8.8.8;
      default-lease-time 300;
      max-lease-time 6900;
  }
  
  subnet 10.62.32.0 netmask 255.255.248.0 {
      range 10.62.32.10 10.62.32.20;
      option routers 10.62.32.1;
      option broadcast-address 10.62.39.255;
      option domain-name-servers 8.8.8.8;
      default-lease-time 300;
      max-lease-time 6900;
  }
  ```

  Lalu set up DHCP-Relay di semua router yang terhubung dengan DHCP dan client yang dituju

  install DHCP-Relay
  ```
  apt-get update
  apt-get install isc-dhcp-relay -y
  ```
  
  edit "/etc/default/isc-dhcp-relay" dengan
  ```
  SERVERS="10.62.41.130"
  INTERFACES="eth0 eth1 eth2" #eth menyesuaikan router
  OPTIONS=
  ```

  edit "/etc/sysctl.conf" dengan
  ```
  net.ipv4.ip_forward=1
  ```

  lalu restart DHCP-Relay
  ```
  service isc-dhcp-relay start
  ```

  lalu restart DHCP-Server 
  ```
  service isc-dhcp-server restart
  ```

  setelah DHCP berjalan ubah configurasi pada 3 client menjadi seperti berikut
  ```
  auto eth0
  iface eth0 inet dhcp
  ```

<br>

## Soal 4

> Berikan web server **Slav** dan **Sicilian** IP address yang tetap/fixed dari DHCP. 

> _Assign **Slav** and **Sicilian** web servers fixed IP addresses via DHCP._

**Answer:**

- Screenshot

  Sicilian
  <img width="992" height="647" alt="fix DHCP Sicilian" src="https://github.com/user-attachments/assets/caf406a3-8a84-4820-ac1b-53711130d449" />


  Slav
  <img width="981" height="655" alt="image" src="https://github.com/user-attachments/assets/abc3b008-792b-454f-9fcb-fd4a37790a67" />

- Explanation

  Pada saol ini saya menambah konfigurasi tambahan di DHCP-Server di "/etc/dhcp/dhcpd.conf", yaitu sebagai berikut :
  ```
  subnet 10.62.41.128 netmask 255.255.255.192 {
    range 10.62.41.140 10.62.141.50;
    option routers 10.62.41.129;
    option broadcast-address 10.62.41.191;
    option domain-name-servers 8.8.8.8;
    default-lease-time 300;
    max-lease-time 6900;
    }
    
    subnet 10.62.0.0 netmask 255.255.224.0 {
        range 10.62.0.10 10.62.0.20;
        option routers 10.62.0.1;
        option broadcast-address 10.62.31.255;
        option domain-name-servers 8.8.8.8;
        default-lease-time 300;
        max-lease-time 6900;
    }
    
    subnet 10.62.32.0 netmask 255.255.248.0 {
        range 10.62.32.10 10.62.32.20;
        option routers 10.62.32.1;
        option broadcast-address 10.62.39.255;
        option domain-name-servers 8.8.8.8;
        default-lease-time 300;
        max-lease-time 6900;
    }
    
    subnet 10.62.41.0 netmask 255.255.255.128 {
        range 10.62.41.10 10.62.41.20;
        option routers 10.62.41.1;
        option broadcast-address 10.62.41.127;
        option domain-name-servers 8.8.8.8;
        default-lease-time 300;
        max-lease-time 6900;
    }
    
    subnet 10.62.40.0 netmask 255.255.255.0 {
        range 10.62.40.10 10.62.40.20;
        option routers 10.62.40.1;
        option broadcast-address 10.62.40.255;
        option domain-name-servers 8.8.8.8;
        default-lease-time 300;
        max-lease-time 6900;
    }
    
    host Sicilian {
        hardware ethernet 02:42:91:b8:6f:00;
        fixed-address 10.62.41.13;
    }
    
    host Slav {
        hardware ethernet 02:42:c0:96:af:01;
        fixed-address 10.62.40.19;
    }
    
    ```

  setalhnya saya mengonfigurasi Sicilian dan Slav agar mau menerima DHCP

  - Sicilian
    <img width="1062" height="671" alt="image" src="https://github.com/user-attachments/assets/d0b2f808-9b81-4cfa-8eaf-b71e2bf09d2e" />

  - Slav
    <img width="1072" height="672" alt="image" src="https://github.com/user-attachments/assets/fea213d6-d009-4b4a-ade3-2a0503f3673e" />

  Setelahnya saya melakukan restart pada DHCP-Server
  ```
  service isc-dhcp-server start
  ```

<br>

## Soal 5

> Buatlah konfigurasi untuk domain:  
**parkov.com** → IP Node **Slav**  
**paskarov.com** → IP Node **Sicilian** 
Pada **DNS Master Caro-Kann.** Tambahkan juga subdomain www untuk kedua domain tersebut.

> _Configure the domains:  
**parkov.com** → **Slav** Node IP  
**paskarov.com** → **Sicilian** Node IP  
On the **Caro-Kann DNS Master,** then add the www subdomain for both domains._

**Answer:**

- Screenshot

  parkov.com dan www.parkov.com
  <img width="883" height="597" alt="ping parkov com dan www parkov com" src="https://github.com/user-attachments/assets/9f5de95a-ba42-4f68-9254-a63d0d698d95" />

  paskarov.com dan www.paskarov.com
  <img width="911" height="590" alt="ping paskarov com dan www paskarov com" src="https://github.com/user-attachments/assets/37306f66-6a2d-4af1-8249-95dca1129687" />



- Explanation

  pada soal ini, pertama saya menginstal bund9 di Koro-Kan
  ```
  apt-get update
  apt-get install bind9 -y
  ```

  lalu mengedit /etc/bind/named.conf.local dan mengisinya dengan hal seperti berikut
  ```
  zone "parkov.com" {
	type master;
	file "/etc/bind/parkov/parkov.com";
  };
  
  zone "paskarov.com" {
  	type master;
  	file "/etc/bind/paskarov/paskarov.com";
  };
  ```

  setelahnya saya emmbuat file untuk dns
  ```
  mkdir /etc/bind/parkov
  mkdir /etc/bind/paskarov
  ```

  lalu mengedit file /etc/bind/paskarov/paskarov.com dan /etc/bind/parkov/parkov.com

  /etc/bind/parkov/parkov.com
  ```
  $TTL 604800
  @   IN  SOA parkov.com. root.parkov.com. (
          2025102901 ; Serial
          604800      ; Refresh
          86400       ; Retry
          2419200     ; Expire
          604800 )    ; Negative Cache TTL
  ;
  @       IN  NS      parkov.com.
  @       IN  A       10.62.40.19
  www  	IN  CNAME   parkov.com.
  @       IN  AAAA    ::1
  ```

  /etc/bind/paskarov/paskarov.com
  ```
  $TTL 604800
  @   IN  SOA paskarov.com. root.paskarov.com. (
          2025102901 ; Serial
          604800      ; Refresh
          86400       ; Retry
          2419200     ; Expire
          604800 )    ; Negative Cache TTL
  ;
  @       IN  NS      paskarov.com.
  @       IN  A       10.62.41.13
  www  	IN  CNAME   paskarov.com.
  @       IN  AAAA    ::1
  ```

  setelahnya saya menjalankan bind9 dengan
  ```
  named -g
  ```

  kemudai saya mengedit /etc/resolv.conf di Stafford
  ```
  nameserver 10.62.41193
  ```
  
  kemudian test ping di node Stafford
  ```
  ping parkov.com
  ping www.parkov.com
  ping paskarov.com
  ping www.paskarov.com
  ```
<br>

## Soal 6

> Konfigurasikan juga **Alekhine** sebagai **DNS Slave** yang bekerja untuk membantu **Caro-Kann.** Lakukan pengujian dengan **mematikan Caro-Kann** lalu coba ping ke domain dan subdomain tersebut (pilih salah satu saja).

> _Configure **Alekhine** as a **DNS Slave** to assist **Caro-Kann**. Perform testing by **disabling Caro-Kann** and then pinging the domain and subdomain (choose only one)._

**Answer:**

- Screenshot

	Bukti Slav hidup dan Master mati
	<img width="1918" height="1010" alt="bukti slave hidup dan master mati" src="https://github.com/user-attachments/assets/217f5884-b549-43ec-9a8c-53abc2158186" />

	Ping parkov dan paskarov
	<img width="1907" height="870" alt="ping paskaroc dan parkov setelah slav" src="https://github.com/user-attachments/assets/1488e889-fb7e-4816-956b-af4355191fc4" />


- Explanation

  Pada soal ini saya mengubah sedikit konfigurasi pada file /etc/bind/named.conf.local yang ada di koro-kan menjadi seperti berikut
  ```
  zone "parkov.com" {
	type master;
	also-notify { 10.62.41.196; }; 
    	allow-transfer { 10.62.41.196; }; 
	file "/etc/bind/parkov/parkov.com";
	};
	
	zone "paskarov.com" {
		type master;
		also-notify { 10.62.41.196; }; 
	    	allow-transfer { 10.62.41.196; }; 
		file "/etc/bind/paskarov/paskarov.com";
	};
	```

  lalu melakukan setup di Alkehine

  install bind9
  ```
  apt-get update
  apt-get install bind9 -y
  ```

  edit /etc/bind/named.conf.local
  	```  
	zone "parkov.com" {
	    type slave;
	    masters { 10.62.41.194; }; 
	    file "/var/lib/bind/parkov.com";
	};
	
	zone "paskarov.com" {
	    type slave;
	    masters { 10.62.41.194; }; 
	    file "/var/lib/bind/paskarov.com";
	};
	```

   lalu saya melakukan bind9 start dengan
  	```
   	named -g
	```

	setelahnya salah mematikan bind9 pada koro-kan dan mengubah file /etc/resolv.conf
	```
 	nameserver 10.62.41.196 #ip DNS-Slave
 	```
<br>

## Soal 7

> Konfigurasikan **Sicilian** agar berfungsi sebagai **web server nginx** yang akan menyajikan [halaman berikut](https://drive.google.com/file/d/1eX0ZjRKprx8T34XFAssrpc7ZE1j6Jv0j/view). Konfigurasikan juga agar **Sicilian** bisa menyimpan custom access log ke file **/tmp/access.log** dan error log ke file **/tmp/error.log.**

> _Configure **Sicilian** to function as an **nginx web server**that will serve [this page](https://drive.google.com/file/d/1eX0ZjRKprx8T34XFAssrpc7ZE1j6Jv0j/view). Also, configure **Sicilian** to save custom access logs to **/tmp/access.log** and error logs to **/tmp/error.log.**_

**Answer:**

- Screenshot

  <img width="887" height="596" alt="CURL ke Sicilian" src="https://github.com/user-attachments/assets/52f882d9-9bd2-4423-8e52-20b66679cdf4" />


- Explanation

  Pada soal ini pertama saya menginstal nginx di Sicilian
  ```
  	apt-get update
	apt-get install nginx -y
  ```

  Kemudian saya mengdit nano /var/www/html/index.html dan di isi file yang di berikan soal, setelahnya saya melakukan restart nginx di sicilian
  ```
  service nginx restart
  ```

  untuk mengecek saya menggunakan curl di client
  ```
  curl 10.62.41.13
  ```
  
  

<br>

## Soal 8

> Buatlah custom access log ke file **/tmp/access.log.** Untuk keperluan logging, gunakan format log seperti di bawah:
> - Tanggal dan waktu akses dalam format standar log.
> - Nama node yang sedang diakses.
> - Alamat IP klien yang mengakses website.
> - Metode HTTP dan URI yang diakses oleh klien.
> - Status respons HTTP yang diberikan oleh server.
> - Jumlah byte yang dikirimkan dalam respons.
> - Waktu yang dihabiskan oleh server untuk menangani permintaan.> 
> - Contoh format log yang sesuai:  
[01/Oct/2024:11:30:45 +0000] Jarkom Node Sicilian Access from 192.168.1.15 using method "GET /resep/bayam HTTP/1.1" returned status 200 with 2567 bytes sent in 0.038 seconds

> _Webserver: Create a custom access log to the file **/tmp/access.log.** For logging purposes, use the log format shown below:_
> - _The date and time of access in standard log format._
> - _The name of the node being accessed._
> - _The IP address of the client accessing the website._
> - _The HTTP method and URI accessed by the client._
> - _The HTTP response status returned by the server._
> - _The number of bytes sent in the response._
> - _The time spent by the server processing the request._
> - _Example of appropriate log format:  
[01/Oct/2024:11:30:45 +0000] Jarkom Node Sicilian Access from 192.168.1.15 using method "GET /resep/bayam HTTP/1.1" returned status 200 with 2567 bytes sent in 0.038 seconds_

**Answer:**

- Screenshot

  <img width="881" height="585" alt="image" src="https://github.com/user-attachments/assets/1aebdfda-2b3e-4ae8-b4ae-12cc6b8b17aa" />


- Explanation

	Pada soal ini saya mengedit file /etc/nginx/sites-available/paskarov.com yang diisi dengan 
	```
	 	server {
	  listen 80;
	  server_name paskarov.com www.paskarov.com;
	
	  root /var/www/html;
	  index index.html;
	
	  access_log /tmp/access.log custom_access_log;
	  error_log  /tmp/error.log;
	}
 	```

	lalu edit /etc/nginx/nginx.conf dan tambahkan 
 
	```
		server {
		
		
		g_format custom_access_log '[$time_local] Jarkom Node Sicilian '
									 'Access from $remote_addr using method "$request" '
									 'returned status $status with $body_bytes_sent bytes 
	
		Konfigurasi lain
		}
	```

 	Setekahnya test dengan
  	```
	curl htttp://paskarov.com
   	```

	

	


<br>

## Soal 9

> Konfigurasikan juga **Slav** agar berfungsi sebagai **web server nginx** yang menyajikan [halaman berikut](https://drive.google.com/file/d/1h8ik1Zcubntp0dvHt9NHYqSZLSTG6FuZ/view) dan **hanya** bisa diakses melalui port **8000** dan **8888.**

> _Configure **Slav** to function as an **nginx web server** that serves [this page](https://drive.google.com/file/d/1h8ik1Zcubntp0dvHt9NHYqSZLSTG6FuZ/view?usp=drive_link) and is **only** accessible via ports **8000** and **8888.**_

**Answer:**

- Screenshot

  port 8000 dan 80
  <img width="878" height="577" alt="curl parkov (hanya mendengan 8000" src="https://github.com/user-attachments/assets/a2b40a8b-3920-4e79-a826-5869f00ea119" />

  porth 8080
  <img width="878" height="577" alt="curl parkov (hanya mendengan 8000" src="https://github.com/user-attachments/assets/3be5bfbf-5ec9-4a79-99b0-2476d1cb2e22" />


- Explanation

  pada soal ini pertama saya melakukan set up untuk web server(slav)
  ```
  apt-get update
  apt-get install nginx -y
  ```

  lalu mengedit index.html dan mengisinya sesuai soal
  ```
  nano /var/www/html/index.html
  ```

  setelahnya saya mengedit /etc/nginx/sites-available/parkov.com dan mengisinya dengan
  ```
  server {
  listen 8080;
  listen 8000;
  server_name parkov.com www.parkov.com;

  root /var/www/html;
  index index.html;
  }
  ```

  lalu saya juga mengedit /etc/nginx/sites-available/default dan mengubah baris pada server
  ```
  server {
	
	listen 8000 default_server;
	listen [::]:8000 default_server;
	
	listen 8080 default_server;
	listen [::]:8080 default_server;
  ...Konfigurasi lain
  }
  ```

  lalu test di node lain
  ```
  curl parkov.com:80 (gagal)
  curl parkov.com:8080 (berhasil)
  curl parjov.com:8000 (berhasil)
  ```


<br>

## Soal 10

> Untuk memudahkan akses, buatlah satu domain lagi dengan nama **openings.com** yang mengarah ke **Petrov.** Lalu, konfigurasikan juga **Petrov** sebagai **Reverse Proxy** yang akan melakukan forward request ke server yang sesuai berdasarkan URL profile yang diminta oleh klien dengan ketentuan sebagai berikut:
> - Request untuk “openings.com/**sicilian**” harus dialihkan ke web server **Sicilian.**
> - Request untuk “openings.com/**slav**” harus dialihkan ke web server **Slav.**

> _To facilitate access, create another domain with the name **openings.com** that points to **Petrov.** Then, configure **Petrov** as a **Reverse Proxy** that will forward requests to the appropriate server based on the profile URL requested by the client with the following conditions:_
> - _Requests for “openings.com/**sicilian**” must be forwarded to web server **Sicilian.**_
> - _Request for “openings.com/**slav**” must be forwarded to web server **Slav.**_

**Answer:**

- Screenshot

  Ke Sicilian :
  <img width="897" height="605" alt="image" src="https://github.com/user-attachments/assets/5c0778bc-1d23-4490-ab5e-1befec5ea389" />

  Ke Slav :
  <img width="893" height="592" alt="image" src="https://github.com/user-attachments/assets/ca3317f1-555f-4b14-bdb9-420fa1739db3" />



- Explanation

  Pada soal ini pertama saya mengbah sedikit configurasi di Koro-Kann
  ```
  nano /etc/bind/paskarov/paskarov.com
  nano /etc/bind/parkov/parkov.com
  ```

  tambahkan :
  ```
  openings.com	IN	A	10.62.41.210
  ```
  lalu aktifkan kembali
  ```
  named -g
  ```


  setlah itu saya melakukan konfigurasi di Petrof :

  instal nginx
  ```
  apt-get update
  apt-get install nginx
  ```

  edit file openings.com
  ```
  nano /etc/nginx/sites-available/openings.com
  ```

  isi :
  ```
   listen 80;
  server_name openings.com;

  # Redirect tanpa trailing slash (opsional, biar konsisten)
  location = /sicilian { return 301 /sicilian/; }
  location = /slav     { return 301 /slav/; }

  location /sicilian/ {
      proxy_pass http://10.62.41.13/;
  }

  location /slav/ {
      proxy_pass http://10.62.40.19:8000/;
  }
  }
  ```

  lalu restart
  ```
  service nginx restart
  ```

  lalu test curl dari client
  ```
  curl -i -H "Host: openings.com" http://10.62.41.210/sicilian/
  curl -i -H "Host: openings.com" http://10.62.41.210/slav/
  ```
<br>

## Soal 11

> Tambahkan juga konfigurasi agar request untuk “openings.com/**random**” akan mengalihkan request ke webserver **Sicilian** dan **Slav** dengan algoritma _round-robin_.

> _Additionally, configure requests for "openings.com/**random**" to be redirected to the **Sicilian** and **Slav** web servers using a round-robin algorithm._

**Answer:**

- Screenshot

  <img width="885" height="597" alt="image" src="https://github.com/user-attachments/assets/4c4a8213-b7bd-4a26-91c1-137bc77d5616" />


- Explanation

  Pada soal ini, saya sedikit mengubah file /etc/nginx/sites-available/openings.com pda Petrov dan menambahkan isian berikut
  ```
	upstream openings_pool {
	    server 10.62.41.13:80;     # Sicilian (sesuaikan port yang aktif)
	    server 10.62.40.19:8000;   # Slav (sesuaikan port yang aktif)
	}
	
	server {
	  listen 80;
	  server_name openings.com www.openings.com;
	
	  location = /sicilian { return 301 /sicilian/; }
	  location = /slav     { return 301 /slav/; }
	
	  location /sicilian/ { proxy_pass http://10.62.41.13/; }
	  location /slav/     { proxy_pass http://10.62.40.19:8000/; }
	
	  # === Round‑robin sederhana ===
	  location /random/ {
	      proxy_pass http://openings_pool/; 
	  }
	}
  ```

  lalu restart nginx
  ```
  service nginx restart
  ```

  test dengan
  ```
  curl -i -H "Host: openings.com" http://10.62.41.210/random/
  ```

<br>

## Soal 12

> Anatoly Parkov berencana untuk melakukan ekspansi secara besar-besaran. Maka dari itu, hapus seluruh konfigurasi Static Routing dan ubah agar seluruh router menggunakan Dynamic Routing. Gunakan protokol RIP!

> _Anatoly Parkov plans to perform a great expansion. Therefore, remove all Static Routing configurations and configure all routers to use Dynamic Routing. Use the RIP protocol!_

**Answer:**

- Screenshot

  Smith-Morra

  <img width="882" height="594" alt="image" src="https://github.com/user-attachments/assets/02304328-0c93-47ec-96c7-d1f4f1f99398" />


  Flanchetto

  <img width="885" height="594" alt="image" src="https://github.com/user-attachments/assets/77dac65a-19c1-4e7b-b9cb-3f707dbf9ffb" />


  Lucena

  <img width="893" height="598" alt="image" src="https://github.com/user-attachments/assets/ada03dc2-7305-491f-8d90-61e78d56ad9a" />


  Zwischenzug

  <img width="880" height="600" alt="image" src="https://github.com/user-attachments/assets/3322b246-2440-4210-9dff-1d60a10b5368" />


  Zugzwang

  <img width="888" height="589" alt="image" src="https://github.com/user-attachments/assets/96639dbd-5985-4533-9eec-7b3d05cb4818" />






- Explanation

  Untuk mengerjakan soal ini pertama saya melakukan set up awal untuk dynamic routing di semua router
  ```
  cd /usr/lib/frr
  ./zebra -d
  ./ripd -d
  ./mgmtd -d

  vtysh

  conf t
  router rip
  ```

  Lalu saya melakukan setup network di tiap router

	- Smith Morra :
	```
	network 10.62.41.0.0/19
	network 10.62.41.32.0/21
	network 10.62.42.0/30
	```
	
	- Flanchetto :
	```
	network 10.62.42.0/30
	network 10.62.41.216/29
	```
	
	- Lucena :
	```
	network 10.62.41.216/29
	network 10.62.41.128/26
	```
	
	- Zwischenzug :
	```
	network 10.62.41.216/29
	network 10.62.41.208/29
	```

- Zugzwang :
```
network 10.62.41.208/29
network 10.62.41.0/25
network 10.62.41.192/28
network 10.62.40.0/24
```

Untuk mengeceknya saya menggunakan
```
show ip rip
```

<br>

## Soal 13

> Untuk meningkatkan keamanan, konfigurasikan firewall **Smith-Morra** untuk melakukan pembatasan koneksi SSH ke server DNS. Drop semua packet SSH yang berasal dari seluruh client yang memiliki tujuan ke **Caro-Kann** atau **Alekhine.**

> _To increase security, configure the **Smith-Morra** firewall to restrict SSH connections to the **DNS server.** Drop all SSH packets from all clients destined for **Caro-Kann** or **Alekhine.**_

**Answer:**

- Screenshot

  <img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/a037e46d-a2bd-471c-9963-1d60e8c702fc" />

- Explanation

  Pada soal ini saya hanya menambah aturan pada smtih-morra yang akan memblokir paket dari client ke dns-server
  ```
  iptables -A FORWARD -s 10.62.0.0/19 -d 10.62.41.194 -p tcp --dport 22 -j DROP
  iptables -A FORWARD -s 10.62.32.0/21 -d 10.62.41.194 -p tcp --dport 22 -j DROP

  iptables -A FORWARD -s 10.62.0.0/19 -d 10.62.41.196 -p tcp --dport 22 -j DROP
  iptables -A FORWARD -s 10.62.32.0/21 -d 10.62.41.196 -p tcp --dport 22 -j DROP
  ```

  lalu saya mengetes dengan ncat di client dan dns server
  ```
  nc -l -p [PORT] (untuk penerima)
  nc [IP Receiver] [PORT] (untuk pengirim paket)
  ```




<br>

## Soal 14

> Nampaknya, web server juga manusia sehingga hanya ingin bekerja di hari kerja. Maka dari itu, semua client hanya bisa mengakses **Sicilian** dan **Slav** pada hari Senin-Jumat pada pukul 09:00-17:00.

> _Apparently, web servers are humans too, so they only want to work on weekdays. Therefore, all clients can only access **Sicilian** and **Slav** on Monday through Friday, 9:00 AM to 5:00 PM._

**Answer:**

- Screenshot

  Berhasil
  <img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/b8ef6e8b-995c-4408-8906-80ca446b8ab1" />

  Gagal
  <img width="1917" height="1079" alt="image" src="https://github.com/user-attachments/assets/e20f745d-8676-4547-beeb-1a9cdd748000" />


- Explanation

  Pada soal ini saya menambahkan aturan berikut di Smith-Morra
  	```
  	# Izinkan  dari klien ke Sicilian (10.62.41.2)
	tables -A FORWARD -p tcp -s 10.62.0.0/19 -d 10.62.41.2 --dport 80  -m time --timestart 09:00 --timestop 17:00 --weekdays Mon,Tue,Wed,Thu,Fri -j ACCEPT
	
	iptables -A FORWARD -p tcp -s 10.62.32.0/21 -d 10.62.41.2 --dport 80  -m time --timestart 09:00 --timestop 17:00 --weekdays Mon,Tue,Wed,Thu,Fri -j ACCEPT
	
	iptables -A FORWARD -p tcp -s 10.62.0.0/19 -d 10.62.41.2 --dport 443 -m time --timestart 09:00 --timestop 17:00 --weekdays Mon,Tue,Wed,Thu,Fri -j ACCEPT
	
	iptables -A FORWARD -p tcp -s 10.62.32.0/21 -d 10.62.41.2 --dport 443 -m time --timestart 09:00 --timestop 17:00 --weekdays Mon,Tue,Wed,Thu,Fri -j ACCEPT
	
	# Izinkan dari klien ke Slav (10.62.40.2)
	iptables -A FORWARD -p tcp -s 10.62.0.0/19 -d 10.62.40.2 --dport 80  -m time --timestart 09:00 --timestop 17:00 --weekdays Mon,Tue,Wed,Thu,Fri -j ACCEPT
	
	iptables -A FORWARD -p tcp -s 10.62.32.0/21 -d 10.62.40.2 --dport 80  -m time --timestart 09:00 --timestop 17:00 --weekdays Mon,Tue,Wed,Thu,Fri -j ACCEPT
	
	iptables -A FORWARD -p tcp -s 10.62.0.0/19 -d 10.62.40.2 --dport 443 -m time --timestart 09:00 --timestop 17:00 --weekdays Mon,Tue,Wed,Thu,Fri -j ACCEPT
	
	iptables -A FORWARD -p tcp -s 10.62.32.0/21 -d 10.62.40.2 --dport 443 -m time --timestart 09:00 --timestop 17:00 --weekdays Mon,Tue,Wed,Thu,Fri -j ACCEPT
	
	# Drop klien ke Sicilian di luar jam yg diizinkan
	iptables -A FORWARD -p tcp -s 10.62.0.0/19 -d 10.62.41.2 -m multiport --dports 80,443 -j DROP
	iptables -A FORWARD -p tcp -s 10.62.32.0/21 -d 10.62.41.2 -m multiport --dports 80,443 -j DROP
	
	# Drop klien ke Slav di luar jam yg diizinkan
	iptables -A FORWARD -p tcp -s 10.62.0.0/19 -d 10.62.40.2 -m multiport --dports 80,443 -j DROP
	iptables -A FORWARD -p tcp -s 10.62.32.0/21 -d 10.62.40.2 -m multiport --dports 80,443 -j DROP
	```

   test dengan mengubah waktu :
	Contoh berhasil
  	```
   	date -s "Mon 11:00"
   	```

   	Contoh gagal
  	```
   	date -s "Sat 18:00"
   	```

   	Test ncat
  	```
   	nc -l -p [PORT] (untuk penerima)
	nc [IP Receiver] [PORT] (untuk pengerim)
   	```
<br>

## Soal 15

> Terakhir, Gerry Paskarov berpesan untuk selalu melakukan logging, sehingga konfigurasikan fitur logging untuk melakukan log terhadap seluruh paket yang di-DROP pada firewall **Smith-Morra.**
> _Finally, Gerry Paskarov advises to always perform logging, so configure a logging feature to log all packets dropped on the **Smith-Morra** firewall._

**Answer:**

- Screenshot

  <img width="898" height="600" alt="image" src="https://github.com/user-attachments/assets/a60b3ba4-477c-47cf-93ea-3d46b728402a" />


- Explanation

  Pada soal ini, saya hanya menambahkan aturan berikut
  ```
  iptables -A INPUT   -j LOG --log-prefix "DROP INPUT: "
	iptables -A FORWARD -j LOG --log-prefix "DROP FORWARD: "

	iptables -A INPUT -j DROP
	iptables -A FORWARD -j DROP
  ```

  cek dengan
  ```
  dmesg -w
  ```

<br>
  
## Problems
Saya tidak tahu mengapa namun client yang saya gunakan selalu mereset nameserver ke 8.8.8.8 setiap beberapa detik, sehingga saya tidak bisa mengikuti modul untuk melakukan curl dan semacamnya. 

curl yang saya gunakan seperti berikut :
```
curl -i -H "Host: openings.com" http://10.62.41.210/random/
```

## Revisions (if any)
