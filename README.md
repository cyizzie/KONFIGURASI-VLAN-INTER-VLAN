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

![Screenshot 2024-10-10 125955](https://github.com/user-attachments/assets/31bf6c65-2f31-475a-90d8-b315633c01da)
![Screenshot 2024-10-10 125813](https://github.com/user-attachments/assets/04674c4b-3eeb-4c17-ac94-a2542a517038)
![Screenshot 2024-10-10 130110](https://github.com/user-attachments/assets/c7119412-d2bf-4bc3-9d52-7e27f6a6b05b)

**Hasil Tes Koneksi**                             
![image](https://github.com/user-attachments/assets/7c51b5c6-1089-49ab-b1d0-812b41b98860)


## ANALISIS PERCOBAAN

Percobaan ini dilakukan untuk menguji koneksi antar tiga PC yang berada di VLAN dan subnet yang berbeda. Setiap PC dikonfigurasi dengan alamat IP, subnet mask, dan default gateway. Default gateway penting untuk memastikan bahwa setiap PC dapat berkomunikasi dengan jaringan lain di luar subnet lokal melalui router yang sudah dikonfigurasi.

**Analisis Konfigurasi Setiap PC:**

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
