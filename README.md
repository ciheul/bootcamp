Instalasi

[optional]
$ cd ~/Projects

$ git clone https://github.com/ciheul/bootcamp

$ cd ~/Projects/bootcamp

Disarankan menggunakan Python 2.7. Nama folder `denv` sudah diset untuk diabaikan di `.gitignore`.
$ virtualenv denv -p python2.7
$ source denv/bin/activate
$ pip install -r requirements.txt

Untuk menghasilkan file html dari format restructured text (reST) yang digunakan Sphinx:
$ make html 

Hasilnya dapat dicek di folder `build/html`

Setup nginx (versi yang digunakan ketika menulis dokumen ini adalah 1.10.3)

Untuk mengecek versi nginx package yang akan diinstal:
$ sudo apt-cache policy nginx
nginx:
  Installed: 1.10.3-0ubuntu0.16.04.2
  Candidate: 1.10.3-0ubuntu0.16.04.2
  Version table:
     1.10.3-0ubuntu0.16.04.2 500
        500 http://id.archive.ubuntu.com/ubuntu xenial-updates/main i386 Packages
        500 http://security.ubuntu.com/ubuntu xenial-security/main i386 Packages
        100 /var/lib/dpkg/status
     1.9.15-0ubuntu1 500
        500 http://id.archive.ubuntu.com/ubuntu xenial/main i386 Packages

$ sudo apt-get install nginx

Buka file nginx.conf
$ sudo vi /etc/nginx/nginx.conf

Dan tambahkan konfigurasi berikut ke `nginx.conf`:
    server {                                                                    
        listen 55555;                                                           
                                                                                
        access_log      /home/ciheul/Projects/bootcamp/log/nginx-access.log;       
        error_log       /home/ciheul/Projects/bootcamp/log/nginx-error.log;        
                                                                                   
        location / {                                                            
            alias       /home/ciheul/Projects/bootcamp/build/html/;                
        }                                                                          
    }

Jangan lupa untuk mengganti user `www-data` menjadi user `ciheul` agar tidak mendapat permission denied.
    user ciheul;

Update konfigurasi
$ sudo nginx -s stop && sudo nginx

Cek jika dokumentasi Bootcamp bisa diakses melalui browser dengan memasukkan url berikut:

http://localhost:55555
