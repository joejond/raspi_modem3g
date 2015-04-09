# raspi_modem3g

Seting Modem Raspberry dengan Modem 3G Metode WVDIAL

Pasang modem usb ke Rasp

1. install wvdial dengan perintah 

	sudo apt-get install wvdial
	
2. setelah terinstall, lakukan pengecekan Modem Port yang terpakai dengan perintah
	
	sudo wvdialconf

3. perintah diatas membuat setting di /etc/wvdial.conf
	sesuaikan infromasi setting modem dengan provider yang dipakai (setting username dan password)
	untuk edit konfigurasi gunakan perintah
	 
	sudo nano /etc/wvdial.conf

4. koneksikan modem dengan perintah
	
	sudo wvdial
   atau dengan 
	sudo wvdial & 
	
5. apabila koneksi sudah OK, tekan tombol ctrl+C untuk menggunakan terminal


6. cek koneksi internet dengan ping ke alamat internet yang dituju (misal ping google.com)

7. untuk membuat koneksi wvdial otomatis terload saat start up, tambahkan listing kode berikut pada /etc/network/interfaces

	auto ppp0
	iface ppp0 inet wvdial
	
8. restart network dengan peritah 
	
	sudo service networking retart
	
	atau dengan sudo ifup ppp0

selamat mencoba
