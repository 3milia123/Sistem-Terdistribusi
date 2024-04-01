# Sistem Terdistribusi

instalasi vm [https://ciperx.com/install-ubuntu-server/](https://ciperx.com/install-ubuntu-server/)

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/23d6b07d-404b-4b7e-8966-bf523dade30d.png)

1. persiapan server host 

```jsx
sudo apt install -y build-essential linux-headers-$(uname -r)
```

2. mengganti sources list ubuntu 

```jsx
sudo nano /etc/apt/sources.list
```

menjadi 

```jsx
deb http://archive.ubuntu.com/ubuntu/ jammy main restricted universe multiverse
deb-src http://archive.ubuntu.com/ubuntu/ jammy main restricted universe multiverse

deb http://archive.ubuntu.com/ubuntu/ jammy-updates main restricted universe multiverse
deb-src http://archive.ubuntu.com/ubuntu/ jammy-updates main restricted universe multiverse

deb http://archive.ubuntu.com/ubuntu/ jammy-security main restricted universe multiverse
deb-src http://archive.ubuntu.com/ubuntu/ jammy-security main restricted universe multiverse

deb http://archive.ubuntu.com/ubuntu/ jammy-backports main restricted universe multiverse
deb-src http://archive.ubuntu.com/ubuntu/ jammy-backports main restricted universe multiverse

deb http://archive.canonical.com/ubuntu/ jammy partner
deb-src http://archive.canonical.com/ubuntu/ jammy partner
```

![Screenshot (106).png](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/e401e93d-3a1e-4a50-8f36-086d2d4420d4.png)

```jsx
sudo apt update
```

```jsx
sudo apt upgrade -y
```

![Screenshot (108).png](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Screenshot_(108).png)

3. install lxc 

```jsx
sudo apt-get install lxc lxctl lxc-templates net-tools  
```

![Screenshot (109).png](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/62812b99-90e3-43cc-a6bb-df602326788e.png)

4. check konfigurasi 

```jsx
sudo lxc-checkconfig
```

![Screenshot (110).png](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/8083eb1f-a0a5-4ce2-9941-4d50a267c269.png)

5. Menampilkan Template container yang tersedia 

```jsx
sudo ls /usr/share/lxc/templates/
```

![Screenshot (111).png](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/af89182f-0cd4-4499-85f1-e8beb7b38d4b.png)

6. Membuat container Ubuntu 
    
    Syntax Command :
    
    ```jsx
    sudo lxc-create -n namakontainer -t template
    ```
    
    ![Screenshot (113).png](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/4a987b8f-fbf6-4c6c-8499-319a905a6133.png)
    
    Sehingga :
    
    ```jsx
    sudo lxc-create -n namakontainer -t template
    ```
    
    ![Screenshot (114).png](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/7ad504af-efce-4c28-a553-02cdc398409a.png)
    
2. Menginstal server web Nginx beserta paket tambahan yang memperluas fungsionalitasnya.
    
    ```jsx
    sudo apt install nginx nginx-extras
    ```
    
    ![Screenshot (115).png](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Screenshot_(115).png)
    
3. Masuk ke direktori di mana konfigurasi Nginx disimpan.
    
    ```jsx
    cd /etc/nginx/
    ```
    
    Masuk ke direktori di mana konfigurasi situs yang aktif (enabled) untuk server web Nginx disimpan.
    
    ```jsx
    cd /etc/nginx/sites-enabled/
    ```
    
    Menampilkan daftar file dan direktori di direktori saat ini.
    
    ```jsx
    ls
    ```
    
    Menampilkan daftar lengkap file dan direktori, termasuk yang tersembunyi, dengan informasi detail seperti hak akses dan pemilik.
    
    ```jsx
    ls -la
    ```
    
    Menyalin berkas bernama **`default`** ke berkas bernama **`sister.local`**.
    
    ```jsx
    sudo cp default sister.local
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/2302cdbc-3cbe-4cb6-8c35-2586aa775998.png)
    
4. Membuka berkas bernama **`sister.local`** dengan menggunakan editor teks Nano.
    
    ```jsx
    sudo nano sister.local
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/d856449c-6ec5-4fe1-9273-6e20eded713f.png)
    
    Menjadi :
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled.png)
    
5. Memeriksa sintaksis konfigurasi Nginx.
    
    ```jsx
    sudo nginx -t
    ```
    
6. Memuat ulang konfigurasi Nginx tanpa menghentikan server.
    
    ```jsx
    sudo nginx -s reload
    ```
    
    Berpindah ke direktori di mana file-file untuk situs web umumnya disimpan pada server Nginx.
    
    ```jsx
    cd /var/www/html/
    ```
    
    Menampilkan daftar file dan direktori di direktori saat ini.
    
    ```jsx
    ls
    ```
    
    Menyalin berkas **`index.nginx-debian.html`** menjadi **`index.html`**.
    
    ```jsx
    sudo cp index.nginx-debian.html index.html
    ```
    
    Untuk membuka berkas **`index.html`** menggunakan editor teks Nano, sehingga Anda dapat mengedit atau membuat perubahan pada berkas tersebut.
    
    ```jsx
    sudo nano index.html
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/62ac1996-da97-4542-9690-3254f3eefd1b.png)
    
    Menjadi : 
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/972cb9ec-5325-42aa-b9df-f853166738e5.png)
    
7. Selanjutnya klik kanan notepad plih jalankan sebagai administrator lalu pilih file masuk ke local disk c - pilih windows - pilih System 32 - pilih drivers - pilih etc - dia pertama pilihanya menggunakan Dokumen txt ganti saja dengan Semua file agar data terlihat - Jika sudah pilih hosts- lalu tambahkan seperti dibawah ini lalu disimpan  :
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/4408e195-ad89-4552-97b7-a92be71dfe54.png)
    
    Selanjutnya masuk ke google ketik : sister.local, jika berhasil akan muncul seperti ini :
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/85ef7752-d2c5-4282-975c-186e9181e004.png)
    

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/237ea8cf-555a-4db3-93fc-6e4114722088.png)

Menampilkan isi berkas **`index.html`** ke terminal.

```jsx
cat index.html
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/da498044-bfa2-44fa-8173-96fe2f9a03ff.png)

1. Menampilkan daftar berkas yang berada dalam direktori **`/usr/share/lxc/templates/`**.
    
    ```jsx
    sudo ls /usr/share/lxc/templates/
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/669abd60-ff85-497a-83b2-1de2e086e8bf.png)
    
2. Membuat kontainer Linux dengan nama **`microservice1`** dan **`microservice2`**menggunakan template download, dengan distribusi Ubuntu Focal Fossa (20.04) untuk arsitektur AMD64, dan menggunakan server image.linuxcontainers.org untuk mengunduh gambar kontainer.
    
    ```jsx
    sudo lxc-create -n microservice1 -t download -- --dist ubuntu --release focal --arch amd64 --force-cache --server image.linuxcontainers.org
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/4c68862b-f548-4247-9daa-4b35b72ff8cd.png)
    
    ```jsx
    sudo lxc-create -n microservice2 -t download -- --dist ubuntu --release focal --arch amd64 --force-cache --server image.linuxcontainers.org
    ```
    
3. Memulai kontainer dengan nama "microservice1".
    
    ```jsx
    sudo lxc-start -n microseArvice1
    ```
    
    Menampilkan daftar kontainer yang sedang berjalan beserta informasi detail seperti nama kontainer, status, alamat IP.
    
    ```jsx
    sudo lxc-ls -f 
    ```
    
    Memulai kontainer dengan nama "microservice2".
    
    ```jsx
    sudo lxc-start -n microseArvice2
    ```
    
    Menampilkan daftar kontainer yang sedang berjalan beserta informasi detail seperti nama kontainer, status, alamat IP
    
    ```jsx
    sudo lxc-ls -f 
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/f48dca4b-3051-4d6e-81ec-12ad7d027733.png)
    
1. buka ubuntu baru 
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/7c4d9b85-2080-43db-ab08-05ca696bf1cd.png)
    
    Melampirkan terminal  ke dalam kontainer yang sedang berjalan dengan nama "microservice1", sehingga  dapat berinteraksi dengan lingkungan kontainer tersebut seperti menjalankan perintah di dalamnya.
    
    ```jsx
    sudo lxc-attach -n microservice1
    ```
    
    disini nanti mengisi password dan akan menampilan inet  disitu nanti harus diingat atau disimpan di notepad 
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/82747af7-5e95-4139-9694-574a2fbeacc0.png)
    
    Membuka berkas konfigurasi jaringan dengan nama **`10-lxc.yaml`** menggunakan editor teks Nano, sehingga dapat mengedit atau melihat konfigurasi jaringan tersebut.
    
    ```jsx
    nano /etc/netplan/10-lxc.yaml
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%201.png)
    
    Untuk addresses ini menggunakan inet yang tadi disimpan di notepad atau yang diingat tadi
    
    ```jsx
    sudo nano /etc/netplan/10-lxc.yaml
    ```
    
    ```jsx
    sudo netplan apply
    ```
    
    Mengirim permintaan ICMP Echo Request ke server Google untuk memeriksa koneksi jaringan dan mengukur waktu responsnya.
    
    ```jsx
    ping google.com
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/d88164a1-f5bb-4a2a-ac2c-4404ca58fa44.png)
    
    Memperbarui daftar paket yang tersedia (update) dan menginstal pembaruan paket yang telah diperbarui (upgrade) secara otomatis tanpa perlu konfirmasi tambahan (-y).
    
    ```jsx
    apt update; apt upgrade -y
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%202.png)
    
    Menginstal server web Nginx beserta paket tambahan Nginx-Extras pada sistem operasi Linux menggunakan manajer paket APT
    
    ```jsx
    sudo apt install nginx nginx-extras
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/7e99bd21-72d0-4cec-acf9-9759ae799931.png)
    
    Berpindah ke direktori di mana berkas-berkas yang akan disajikan oleh server web biasanya disimpan pada sistem Linux.
    
    ```jsx
    cd /var/www/html/
    ```
    
    Membuka berkas 
    
    ```jsx
    nano.index.nginx-debian.html
    
    ```
    
    Rubahlah menjadi seperti ini :
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%204.png)
    
    Menginstal perangkat lunak Curl pada sistem Linux. Curl adalah alat baris perintah yang digunakan untuk mentransfer data dengan berbagai protokol seperti HTTP, HTTPS, FTP, dan lainnya.
    
    ```jsx
    apt install curl
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%205.png)
    
    Mengirim permintaan HTTP GET ke server yang berjalan pada localhost (komputer lokal) dan menampilkan respons yang diterima dari server tersebut.
    
    ```jsx
    curl localhost
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%206.png)
    
2. Melampirkan terminal  ke dalam kontainer yang sedang berjalan dengan nama "microservice2", sehingga  dapat berinteraksi dengan lingkungan kontainer tersebut seperti menjalankan perintah di dalamnya.
    
    ```jsx
    sudo lxc-attach -n microservice2
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/4d4ebb63-e7dd-4009-a632-0aa7f25b1045.png)
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%207.png)
    
    Catatan : di bagian inet itu harus disalin di notepad atau di catatan dimanapun terserah biar tidak lupa. 
    
    Membuka berkas konfigurasi jaringan dengan nama **`10-lxc.yaml`** menggunakan editor teks Nano, sehingga dapat mengedit atau melihat konfigurasi jaringan tersebut.
    
    ```jsx
    nano /etc/netplan/10-lxc.yaml
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%208.png)
    
    menjadi :
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%209.png)
    
    Untuk addresses ini menggunakan inet yang tadi disimpan di notepad atau yang diingat tadi
    
    ```jsx
    sudo nano /etc/netplan/10-lxc.yaml
    ```
    
    ```jsx
    sudo netplan apply
    ```
    
    Mengirim permintaan ICMP Echo Request ke server Google untuk memeriksa koneksi jaringan dan mengukur waktu responsnya.
    
    ```jsx
    ping google.com
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%2010.png)
    
    Memperbarui daftar paket yang tersedia (update) dan menginstal pembaruan paket yang telah diperbarui (upgrade) secara otomatis tanpa perlu konfirmasi tambahan (-y).
    
    ```jsx
    apt update; apt upgrade -y
    ```
    
    Menginstal server web Nginx beserta paket tambahan Nginx-Extras pada sistem operasi Linux menggunakan manajer paket APT
    
    ```jsx
    sudo apt install nginx nginx-extras
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%2011.png)
    
    Berpindah ke direktori di mana berkas-berkas yang akan disajikan oleh server web biasanya disimpan pada sistem Linux.
    
    ```jsx
    cd /var/www/html/
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%2012.png)
    
    membuka berkas
    
    ```jsx
    nano.index.nginx-debian.html
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%2013.png)
    
    Menginstal perangkat lunak Curl pada sistem Linux. Curl adalah alat baris perintah yang digunakan untuk mentransfer data dengan berbagai protokol seperti HTTP, HTTPS, FTP, dan lainnya.
    
    ```jsx
    apt install curl
    ```
    
    Mengirim permintaan HTTP GET ke server yang berjalan pada localhost (komputer lokal) dan menampilkan respons yang diterima dari server tersebut.
    
    ```jsx
    curl localhost
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/119f85cc-b521-4220-8587-32b0784c8e05.png)
    
3. buka ubuntu baru 
    
    Menampilkan daftar semua kontainer yang ada pada sistem.
    
    ```jsx
    sudo lxc-ls
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/0a8ed71e-dfcd-4908-8d34-f5ce5eee7677.png)
    
    Masuk ke direktori di mana konfigurasi situs web yang aktif (enabled) untuk server Nginx disimpan.
    
    ```jsx
    cd /etc/nginx/sites-enabled/
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/65d92a65-4f14-49ef-9337-1f483a43bf77.png)
    
    Menampilkan daftar file dan direktori di direktori saat ini.
    
    ```jsx
    ls
    ```
    
    Membuka berkas **`sister.local`** menggunakan editor teks Nano, sehingga memungkinkan Anda untuk mengedit atau melihat isi berkas tersebut.
    
    ```jsx
    sudo nano sister.local
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/e216a1c7-26fa-4b9c-a7f5-946861ae0d2a.png)
    
    Memeriksa sintaksis dari konfigurasi Nginx.
    
    ```jsx
    sudo nginx -t
    ```
    
    ![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/b2f73c6c-f9df-44db-8002-39d1eb1a613c.png)
    
    Memuat ulang konfigurasi Nginx tanpa harus menghentikan server, sehingga perubahan konfigurasi baru bisa diterapkan tanpa memengaruhi layanan web yang sedang berjalan.
    
    ```jsx
    sudo nginx -s reload
    ```
    
    Menghentikan dan memulai kembali layanan Nginx, sehingga memuat ulang konfigurasi dan menerapkan perubahan baru pada server web Nginx.
    
    ```jsx
    sudo service nginx restart
    ```
    

Di microservice1

Berpindah ke direktori rumah pengguna saat ini.

```jsx
cd
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%2015.png)

Pindah ke direktori di mana konfigurasi untuk server web Nginx disimpan.

```jsx
cd /etc/nginx/
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%2016.png)

Memindahkan direktori saat ini ke direktori **`sites-enabled`** yang berada di dalam direktori **`/etc/nginx/`**.

```jsx
/etc/nginx# cd sites-enabled/
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/768aaa88-c864-4e22-985f-23ff74a1d3ff.png)

Menyalin berkas **`default`** menjadi **`mcsv1.local`**.

```jsx
cp default mcsv1.local
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%2017.png)

Membuka berkas **`mcsv1.local`** menggunakan editor teks Nano, sehingga memungkinkan Anda untuk mengedit atau melihat isi berkas tersebut.

```jsx
nano mcsv1.local
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/b1d74396-5595-4e27-af42-a5baf97de614.png)

Memeriksa sintaksis dari konfigurasi Nginx.

```jsx
sudo nginx-t
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%2018.png)

Memuat ulang konfigurasi Nginx tanpa perlu menghentikan server, sehingga perubahan konfigurasi baru bisa diterapkan tanpa mengganggu layanan web yang sedang berjalan.

```jsx
sudo nginx -s reload
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/b6d7709c-8c81-4880-8405-e8f413134f6f.png)

```jsx
cd /var/www/html/
```

```jsx
ls
```

```jsx
cp index.nginx-debian.html index.html
```

```jsx
sudo nano /etc/hosts
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/01aa51c9-2c6d-4016-85f1-93d1757fbbd7.png)

```jsx
curl mcsv1.local
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/d58bed80-855b-40b5-bc7c-11ff25d9b942.png)

Di microservice2

Berpindah ke direktori di mana konfigurasi situs web yang aktif (enabled) untuk server Nginx disimpan.

```jsx
cd /etc/nginx/sites-enabled/
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/db1f0d1c-f964-40e9-a83f-8d0374459fc1.png)

```jsx
ls
```

Menyalin berkas **`default`** menjadi **`mcsv2.local`**.

```jsx
cp default mcsv2.local
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%2019.png)

Membuka berkas **`mcsv2.local`** menggunakan editor teks Nano, sehingga Anda dapat mengedit atau melihat isi berkas tersebut.

```jsx
nano mcsv2.local
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%2020.png)

Memeriksa sintaksis dari konfigurasi Nginx.

```jsx
sudo nginx-t
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%2021.png)

```jsx
sudo nginx -s reload
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%2022.png)

```jsx
cd var/www/html
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%2012.png)

Membuka berkas **`hosts`** menggunakan editor teks Nano dengan izin superuser (sudo), sehingga memungkinkan Anda untuk mengedit atau melihat isi berkas tersebut. Berkas **`hosts`** digunakan untuk memetakan alamat IP ke nama domain yang sesuai, dan sering digunakan untuk mengatur resolusi nama di sistem operasi Linux

```jsx
sudo nano /etc/hosts
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/17f3d665-dbca-4c19-b47f-ee3949ec47f0.png)

```jsx
cd /var/www/html
```

```jsx
ls
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%2023.png)

buka ubuntu yang di langkah 6 :

Nginx, sehingga memuat ulang konfigurasi dan menerapkan perubahan baru pada server web Nginx.

```jsx
sudo service nginx restart
```

Membuka berkas **`hosts`** menggunakan editor teks Nano dengan izin superuser (sudo), memungkinkan Anda untuk mengedit atau melihat isi berkas tersebut. Berkas **`hosts`** digunakan untuk memetakan alamat IP ke nama domain yang sesuai.

```jsx
sudo nano /etc/hosts
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/aa3213e2-3125-41f7-bc58-8ead11189f0d.png)

Mengirimkan permintaan HTTP GET ke server yang diakses melalui alamat URL **`mcsv1.local`** menggunakan perangkat cURL. Ini akan mengambil konten yang disajikan oleh server web di alamat URL tersebut dan menampilkannya dalam terminal.

```jsx
curl mcsv1.local
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/d07b85bb-9057-40b5-8544-2b7f88c96d27.png)

mengirimkan permintaan HTTP GET ke server yang diakses melalui alamat URL **`mcsv2.local`** menggunakan perangkat cURL. Ini akan mengambil konten yang disajikan oleh server web di alamat URL tersebut dan menampilkannya dalam terminal.

```jsx
curl mcsv2.local
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/3372a36d-2fac-4c54-be9d-9b2c96ac5183.png)

```jsx
sudo nano sister.local
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/c0d993da-b813-469d-bf3b-59fc526e5534.png)

```jsx
sudo nginx -t
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/2ca22560-b6ae-4aeb-b942-3a1240951918.png)

```jsx
sudo nginx -s reload
```

```jsx
sudo nano sister.local
```

Rubahlah menjadi seperti ini :

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%2024.png)

Memeriksa sintaksis dari konfigurasi Nginx. Ini akan menguji apakah konfigurasi yang ada dalam file konfigurasi Nginx benar atau tidak, dan menampilkan pesan kesalahan jika ada masalah dengan sintaksisnya.

```jsx
sudo nginx -t
```

![Untitled](Sistem%20Terdistribusi%20634119b65f484863ad20ab8e1653d51f/b2f73c6c-f9df-44db-8002-39d1eb1a613c.png)

Memuat ulang konfigurasi Nginx tanpa perlu menghentikan server. Ini memungkinkan perubahan konfigurasi baru diterapkan tanpa mengganggu layanan web yang sedang berjalan.

```jsx
sudo nginx -s reload
```

Mengirim permintaan HTTP GET ke alamat URL **`sister.local/blog`** menggunakan perangkat cURL. Ini akan mengambil konten yang disajikan oleh server web di alamat URL tersebut dan menampilkannya dalam terminal.

```jsx
curl sister.local/blog
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/3e33482a-4931-4247-a6e5-91c2367f01ac.png)

Mengirimkan permintaan HTTP GET ke alamat URL **`sister.local/aboutus`** menggunakan perangkat cURL. Ini akan mengambil konten yang disajikan oleh server web di alamat URL tersebut dan menampilkannya dalam terminal.

```jsx
curl sister.local/aboutus
```

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/8822c43b-c60e-403e-8cbb-e97b7ee624ca.png)

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%2025.png)

![Untitled](https://github.com/3milia123/Sistem-Terdistribusi/blob/main/Tugas1/Image/Untitled%2026.png)
