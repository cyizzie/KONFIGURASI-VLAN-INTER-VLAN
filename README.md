# LAPORAN KONFIGURASI VLAN & INTER-VLAN

**Nama**: Cisa Livia Virnandyka  
**NIM**: 09010182327016  
**Kelas**: MI3A  
**MK**: Praktikum Jaringan Komputer  

## PERCOBAAN

### 1. Topologi

![Screenshot 2024-10-11 000023](https://github.com/user-attachments/assets/f9701175-5db6-42d4-83ef-b5e024e60e9e)

### 2. Pengalamatan di PC

![Screenshot 2024-10-10 235317](https://github.com/user-attachments/assets/ce714446-a5fa-4e30-bc1c-ee5dc6395ef3)

### 3. Konfigurasi Switch

![Screenshot 2024-10-11 002010](https://github.com/user-attachments/assets/4a83b59f-6472-4ef4-9d50-3a7296e0fad0)

Melihat Daftar Vlan          
![image](https://github.com/user-attachments/assets/e30736b2-4650-41f1-98d1-beac2cf36c0e)

### 4. Konfigurasi Router

![Screenshot 2024-10-09 232322](https://github.com/user-attachments/assets/45c5cf3f-53a5-48cf-bf2c-2f72e5514357)
![Screenshot 2024-10-09 232354](https://github.com/user-attachments/assets/4864d245-f5c6-4d25-a07b-5398714d4ba3)

### 5. Tes Koneksi Menggunakan ICMP

![Screenshot 2024-10-11 084136](https://github.com/user-attachments/assets/f9250edf-9750-43c1-8362-d0f9f7fe4af4)
![Screenshot 2024-10-11 084324](https://github.com/user-attachments/assets/e26783d9-f178-42f5-94ea-de42ffa031e3)
![Screenshot 2024-10-11 084324](https://github.com/user-attachments/assets/c3f08e6e-ebae-415e-8c30-771553a5ff38)


**Hasil Tes Koneksi**                             
![image](https://github.com/user-attachments/assets/7c51b5c6-1089-49ab-b1d0-812b41b98860)


## ANALISIS PERCOBAAN

Percobaan ini dilakukan untuk menguji konektivitas antar tiga PC yang berada di VLAN dan subnet yang berbeda. Setiap PC dikonfigurasi dengan alamat IP, subnet mask, dan default gateway yang dirancang untuk memungkinkan komunikasi antar subnet melalui sebuah router. Default gateway sangat penting dalam jaringan komputer karena memungkinkan perangkat di satu subnet untuk berkomunikasi dengan perangkat lain di subnet yang berbeda melalui router.

**Dalam percobaan ini, ditemukan bahwa dua dari tiga PC memiliki konfigurasi default gateway yang tidak sesuai, sehingga menyebabkan kegagalan komunikasi. Berikut analisis konfigurasi masing-masing PC:**

1. **PC1**:  
   - **Masalah**: Gateway yang digunakan berada di subnet 192.168.200.0/24, sementara PC1 berada di subnet 192.168.100.0/24. Hal ini menyebabkan paket tidak dapat diteruskan ke router yang benar.  
   - **Solusi**: Ubah gateway menjadi 192.168.100.1 yang sesuai dengan subnet 192.168.100.0/24 (VLAN 3).  

2. **PC2**:  
   - **Masalah**: Gateway yang digunakan berada di subnet 192.168.100.0/24, padahal PC2 berada di subnet 192.168.200.0/24. Pengaturan ini salah dan menyebabkan kegagalan komunikasi.  
   - **Solusi**: Ubah gateway menjadi 192.168.200.1 yang sesuai dengan subnet 192.168.200.0/24 (VLAN 2).  

3. **PC3**:  
   - **Kesimpulan**: Konfigurasi PC3 sudah benar karena gateway sesuai dengan subnet yang digunakan, yaitu 192.168.150.0/24 (VLAN 4).  

## KESIMPULAN PERCOBAAN

Percobaan menunjukkan bahwa kesalahan pengaturan gateway pada PC1 dan PC2 menyebabkan kegagalan komunikasi antar subnet. PC1 dan PC2 tidak dapat saling ping karena menggunakan gateway yang tidak sesuai dengan subnet mereka. Setelah melakukan perubahan pada konfigurasi gateway yang benar, setiap PC dapat berkomunikasi dengan baik, baik di dalam subnet maupun antar subnet melalui router yang dikonfigurasi.
