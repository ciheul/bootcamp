vi
==

Konten:

- Instalasi
- Plugin
- Shortcut
- Advanced


Instalasi
---------

vim yang terinstal secara default biasanya belum enhanced vim. Disarankan untuk menginstal terlebih dahulu.

.. code-block:: python

   $ sudo apt-get install vim


Plugin
------

Untuk menginstal plugin, gunakan vim-pathogen.

Plugin-plugin yang disarankan untuk diinstal:

- NerdTree
- EasyMotion
- tcomment
- YouCompleteMe


Shortcut
--------

vim memiliki 2 mode. ??? mode dan Insert mode. ??? mode untuk bekerja dengan shortcut mode. Insert mode untuk melakukan pengetikan seperti biasa.

Untuk berpindah dari ??? mode ke Insert mode, gunakan shortcut sesuai kebutuhan:

======== =========
shortcut Deskripsi
======== =========
a        append. Kursor pindah satu karakter setelah posisi kursor sekarang.
A        Kursor pindah ke akhir baris.
i        insert. Kursor tetap berada di posisi kursor sekarang
I        Kursor pindah ke awal baris.
o        Buat baris baru sesudah posisi kursor di baris sekarang
O        Buat baris baru sebelum posisi kursor di baris sekarang
s        substitute. Hapus karakter di posisi kursor dan kursor tetap berada di posisi kursor sekarang.
S        Kursor menghapus satu line dan kursor berada di awal baris kosong.
======== =========

Untuk berpindah dari Insert mode ke ??? mode, dapat menggunakan shortcut `Esc` dan `Ctrl+c`.

Gunakan `Ctrl+c` untuk mengetik karena lebih cepat. Shortcut ini adalah yang paling sering digunakan.

Namun ada kalanya untuk menggunakan `Esc` seperti ketika ingin melakukan kombinasi shortcut yang berurutan. Misal untuk menulis teks yang sama di beberapa baris berbeda secara bersamaan . `Ctrl+v`, `[jk]`, `Esc`, `Shift+i`.

.. ======== =========
.. shortcut Deskripsi
.. ======== =========
..
.. ======== =========
