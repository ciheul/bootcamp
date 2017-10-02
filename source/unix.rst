UNIX
====

Jika pernah menginstal apache2 dan menjadikan nginx sebagai web server utama, pastikan untuk melakukan hal-hal berikut ini:

- matikan service apache2
- rename file `/var/www/html/index.html` menjadi `/var/www/html/index.html.bak`

Setup `http://localhost` agar mengarah ke web pribadi.

- biasanya secara default, nginx sudah punya initial configuration yang berada di `/etc/nginx/sites-available/default`.
- pastikan konfigurasi di bawah ini:

.. code-block:: c

   server {                                                                        
       listen 80 default_server;                                                   
       listen [::]:80 default_server;

       server_name _;                                                                 
                                                                                          
       location / {                                                                   
           alias       /home/ciheul/Projects/axes/technical-support-docs/build/html/;
       }
   }

- restart nginx `$ sudo nginx -s stop && sudo nginx`
