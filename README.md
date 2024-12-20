# projek-akhir-akhir-os-server
andika hendrawan_23.83.0976_23TK01

# 1. Instal Apache2:
    sudo apt update
    sudo apt install apache2

# membuat direktori untuk menaruh github
    sudo mkdir /var/www/server1

# Clone Repository:
    git clone https://github.com/username/repository.git

# Konfigurasi Apache2: Buat atau edit file konfigurasi virtual host untuk mengarahkan domain ke direktori
    sudo nano /etc/apache2/sites-available/server1.conf
    
    <VirtualHost *:80>
      ServerAdmin admin@192.168.100.62
      DocumentRoot /var/www/server1/AndikaTRavel.github.io
      ServerName 192.168.100.62
      ErrorLog ${APACHE_LOG_DIR}/error.log
      CustomLog ${APACHE_LOG_DIR}/access.log combined
    </VirtualHost>

# Aktifkan Virtual Host: Aktifkan konfigurasi virtual host

    sudo a2ensite server1.conf
    sudo systemctl reload apache2
    
# Buka Port 80 untuk HTTP:

    sudo ufw allow 80/tcp
    sudo ufw enable
    sudo ufw status

# 2. Instal Grafana menggunakan snap:
    sudo snap install grafana
# Mulai Grafana: Setelah instalasi selesai, mulai layanan Grafana:
    sudo systemctl start snap.grafana.grafana
    sudo systemctl enable snap.grafana.grafana
    sudo ufw allow 3000/tcp
akses Grafana: Buka browser dan kunjungi http://192.168.100.62:3000 untuk mengakses Grafana.

