# Sistem Terdistribusi

![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/e7dfdf6e-1a15-4e34-a6e6-6af1406b06f9.png)

1. Membuat wadah Linux bernama "microservice3" dengan Debian Buster (versi "buster") untuk arsitektur AMD64.
    
    ```jsx
    sudo lxc-create -n microservice3 -t download -- --dist "debian" --release "buster" –arch amd64
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/34acdaa2-d606-45ba-8869-b97bafcc4163.png)
    
    Memulai (start) wadah Linux dengan nama "microservice3" yang telah dibuat sebelumnya.
    
    ```jsx
    sudo lxc-start -n microservice3
    ```
    
    Melampirkan (attach) terminal dari host ke dalam wadah (container) Linux yang sedang berjalan dengan nama "microservice3".
    
    ```jsx
    sudo lxc-attach microservice3
    ```
    
    Memperbarui indeks paket dari repositori yang terkonfigurasi di sistem Linux, sehingga sistem dapat mengetahui paket-paket terbaru yang tersedia untuk diinstal.
    
    ```jsx
    sudo apt update
    ```
    
    Menginstal perangkat lunak Nginx dan editor teks Nano pada sistem Linux yang telah terkonfigurasi dengan manajer paket APT.
    
    ```jsx
    sudo apt install nginx nano
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/Untitled.png)
    
    Membuka file teks "hosts" di direktori "/etc", yang berisi daftar korespondensi antara alamat IP dan nama domain pada sistem Linux. Dengan mengedit file tergantung Ip masing-masing
    
    ```jsx
    nano /etc/hosts
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/Untitled%201.png)
    
    note : untuk mencatat ip atau diingat 
    
    ```jsx
    ip a
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/Untitled%202.png)
    
2. Membuat wadah Linux bernama "microservice4" dengan Debian Buster (versi "buster") untuk arsitektur AMD64.
    
    ```jsx
    sudo lxc-create -n microservice4 -t download -- --dist "debian" --release "buster" –arch amd64
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/d4187a54-e37b-4896-8f5b-ab44d2790f72.png)
    
    Memulai (start) wadah Linux dengan nama "microservice4" yang telah dibuat sebelumnya.
    
    ```jsx
    sudo lxc-start -n microservice4
    ```
    
    Melampirkan (attach) terminal dari host ke dalam wadah (container) Linux yang sedang berjalan dengan nama "microservice4"
    
    ```jsx
    sudo lxc-attach microservice4
    ```
    
    Memperbarui indeks paket dari repositori yang terkonfigurasi di sistem Linux, sehingga sistem dapat mengetahui paket-paket terbaru yang tersedia untuk diinstal.
    
    ```jsx
    sudo apt update
    ```
    
    Menginstal perangkat lunak Nginx dan editor teks Nano pada sistem Linux yang telah terkonfigurasi dengan manajer paket APT.
    
    ```jsx
    sudo apt install nginx nano
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/Untitled%203.png)
    
    Membuka file teks "hosts" di direktori "/etc", yang berisi daftar korespondensi antara alamat IP dan nama domain pada sistem Linux. Dengan mengedit file tergantung Ip masing-masing
    
    ```jsx
    nano /etc/hosts
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/Untitled%204.png)
    
    Note : untuk mencatat ip atau diingat 
    
    ```jsx
    ip a
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/Untitled%205.png)
    
3. Membuat wadah Linux bernama "microservice5" dengan Debian Buster (versi "buster") untuk arsitektur AMD64.
    
    ```jsx
    sudo lxc-create -n microservice5 -t download -- --dist "debian" --release "buster" –arch amd64
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/435e823f-dbde-4fe4-abaa-dccbf351ae93.png)
    
    Memulai (start) wadah Linux dengan nama "microservice5" yang telah dibuat sebelumnya.\
    
    ```jsx
    sudo lxc-start -n microservice5
    ```
    
    Melampirkan (attach) terminal dari host ke dalam wadah (container) Linux yang sedang berjalan dengan nama "microservice5"
    
    ```jsx
    sudo lxc-attach microservice5
    ```
    
    Memperbarui indeks paket dari repositori yang terkonfigurasi di sistem Linux, sehingga sistem dapat mengetahui paket-paket terbaru yang tersedia untuk diinstal.
    
    ```jsx
    sudo apt update
    ```
    
    Menginstal perangkat lunak Nginx dan editor teks Nano pada sistem Linux yang telah terkonfigurasi dengan manajer paket APT.
    
    ```jsx
    sudo apt install nginx nano
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/Untitled%206.png)
    
    Membuka file teks "hosts" di direktori "/etc", yang berisi daftar korespondensi antara alamat IP dan nama domain pada sistem Linux. Dengan mengedit file tergantung Ip masing-masing
    
    ```jsx
    nano /etc/hosts
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/Untitled%207.png)
    
    Note : untuk mencatat ip atau diingat 
    
    ```jsx
    ip a
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/Untitled%208.png)
    
4. Memulai (start) wadah Linux dengan nama "microservice1 dan microservice2" yang telah dibuat sebelumnya.
    
    ```jsx
    sudo lxc-start -n microservice1
    ```
    
    ```jsx
    sudo lxc-start -n microservice2
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/Untitled%209.png)
    
5. Menampilkan daftar kontainer Linux yang sedang berjalan beserta informasi detail, seperti nama, status, PID, IP, dan lainnya
    
    ```jsx
    sudo lxc-ls-f
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/378ff30e-a917-4796-99a5-948090efaecf.png)
    
6. Membuka file "hosts" di direktori "/etc" menggunakan editor Nano.
    
    ```jsx
    nano /etc/hosts
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/Untitled%2010.png)
    
7.  Membuka file konfigurasi Nginx yang terletak di direktori **`/etc/nginx/sites-available/`** dengan nama **`sister.local`** menggunakan editor teks Nano.
    
    ```jsx
    sudo nano /etc/nginx/sites-available/sister.local
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/64e54a25-1491-420b-84e0-50b49db791a9.png)
    
    Berpindah ke direktori "sites-available" yang berada di dalam direktori konfigurasi Nginx (/etc/nginx)
    
    ```jsx
    cd /etc/nginx/sites-available
    ```
    
    ```jsx
    ls
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/086ce4f5-2e9a-4a24-adda-99a708602ab5.png)
    
    Melakukan permintaan HTTP GET ke URL "sister.local" menggunakan perangkat lunak curl. Dengan demikian, ini akan menampilkan informasi respons HTTP yang dikembalikan oleh server yang menghost "sister.local".
    
    ```jsx
    curl -i sister.local
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/197325e3-59c0-41a0-82a0-acd0debf16d4.png)
    
    ```jsx
    curl -i sister.local/blog
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/189815b2-fe9b-46b7-8c13-ee187b037389.png)
    
    ```jsx
    curl -i sister.local/aboutus
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/de36e5ce-d33f-4bb0-879f-7b3b2fe3cf97.png)
    
    ```jsx
    sudo nano /etc/nginx/sites-available/sister.local
    ```
    
    ```jsx
    curl -i microservices5.dev
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/f876a584-143f-454f-a552-005fd3ac36e3.png)
    
    ```jsx
    sudo apt install network-manager
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/Untitled%2011.png)
    
    coba sampai 3 kali jika sudah 3 kali langsung tahap berikutnya
    
    ```jsx
    sudo curl-i app.sister.local
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/61b393cb-23a1-48f5-89ff-1c614042be80.png)
    
    Menampilkan secara langsung (real-time) isi dari file log akses Nginx yang berada di direktori **`/var/log/nginx/`** dengan nama **`app.sister.local.access.log`**. Dengan menggunakan opsi **`-f`**, perintah ini akan terus memantau file log, menampilkan baris-baris baru yang ditambahkan ke file tersebut saat server menerima permintaan akses.
    
    ```jsx
    tail -f /var/log/nginx/app.sister.local.access.log
    ```
    
    ![Untitled](Sistem%20Terdistribusi%2053535daa45cb4735bab52fc66a9ce0b1/46eaa90e-9576-414b-b119-3901cbc09833.png)