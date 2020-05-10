# Microsoft-Applocker-Bypass
Sebuah teknik baru untuk mem-by-by-kan aplikasi microsoft.

# Apa itu AppLocker:
AppLocker adalah fitur baru di Windows 7 dan Windows Server 2008 R2 yang memungkinkan Anda menentukan pengguna atau grup mana yang dapat menjalankan aplikasi tertentu di organisasi Anda berdasarkan pada identitas file yang unik. Jika Anda menggunakan AppLocker, Anda bisa membuat aturan untuk mengizinkan atau menolak aplikasi agar tidak berjalan.

# Penemuan:
Ketika AppLocker dikonfigurasikan untuk berfungsi dalam mode daftar putih (mis: hanya program tertentu yang diizinkan untuk dijalankan) dimungkinkan untuk memotong perlindungan dari 'AppLocker'.
Jika, misalnya hanya [mspaint.exe, notepad.exe, calc.exe] ditandatangani dan diizinkan untuk dijalankan - masih dimungkinkan untuk menjalankan program lain dan bahkan menjalankan kode yang menggunakan WindowsAPI.
Kerentanan terjadi karena tidak mungkin untuk memblokir file EXE 'rundll32.exe' karena diperlukan oleh windows untuk melakukan tugas-tugas penting.
Segala sesuatu yang perlu Anda lakukan untuk memotong applocker adalah menjalankan file biner rundll32.exe dengan argumen berikut (dapat dilakukan dengan membuat shortcut, windows + R, dll):

`` `
rundll32.exe javascript: "\ .. \ mshtml, RunHTMLApplication"; <code>
`` `



Setelah Anda menjalankan ini, jendela internet-explorer akan muncul dengan pesan peringatan (1).
Jika mesin tersebut bukan mesin kios, dan Anda dapat menyalin DLL khusus ke dalam mesin - itu lebih baik =] Tapi seperti yang sudah Anda pahami sekarang, Anda dapat menggunakan ini untuk menjalankan vbscripts untuk melakukan operasi yang lebih maju.

# Tanggapan Microsft
! [alt tag] (http://oi57.tinypic.com/2ns1543.jpg)
