## Time Series Analysis Stack - Flask, TimescaleDB, Docker

1. Inisiasi docker network, sehingga container-container di dalam docker host dapat saling berinteraksi

## docker network create --attachable --driver bridge timescale_network

2. Jalankan lokal timescaleDB menggunakan docker-compose, tetapi sebelum itu inisiasi file baru docker-compose.timescale.yml

3. Buat database configuration file yaitu postgresql_custom.conf

4. buat file .env

5. TimescaleDB siap di running menggunakan docker compose

### docker-compose if docker-compose.timescale.yml up -d

6. periksa container yang berjalan

### docker container ls

7. Menyiapkan PGAdmin untuk postgre, buat file docker-compose.pgadmin.yml

8. Running PGAdmin

### docker-compose -f docker-compose.pgadmin.yml up -d

9. PGAdmin dapat diakses di port 9000

### http://127.0.0.1:9000/login?next=%2F

10. login menggunakan username & password di env

11. Apabila sudah berhasil masuk ke PGAdmin, maka untuk membuat server baru, klik kanan di server + create server

12. Pengaturan untuk connection pada server postgre

    Host: timescale (this is the Docker “Service” hostname defined in the first docker-compose.yml file for the TimescaleDB database container)
    Port: 5432
    Maintenance database: postgres
    Username: postgres
    Password: password

13. Table dapat diakses di:

### “/Databases/postgres/Schemas/public/Tables”

14. Query dapat dilakukan di tools -> query tool
