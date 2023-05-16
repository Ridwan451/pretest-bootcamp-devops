# Pre-Test Bootcamp fullstack developer

## Task 1 (Virtualization)

- Buatlah sebuah VM dengan kententuan
  - username: `<github_user>` contoh `dimasm93`
  - hostname: `<email_without_at>` contoh `dimas.tabeldata.com`
  - OS: `ubuntu-20.04` atau `centos-7`
- Install webserver `nginx`
  - Configurasi reverse-proxy ke alamat `https://jsonplaceholder.typicode.com/todos/1` dengan url `/todo`
  - Lakukan curl ke alamat tersebut contoh `<ip-vm-host>:<ip-vm-port-nginx>/todo` (kirimkan hasil screenshotnya simpan dalam folder `screenshot` dengan nama `task1.png`)

## Task 2 (Container)

Jika saya memiliki architecture seperti berikut:

![container-apps](docs/images/01-container.png)

Dimana berikut adalah configurasi docker image:

1. Backend container
  - image: `dimmaryanto93/udemy-springboot-app:latest`
  - port: `8080`
  - env: 
    - `DATABASE_HOST`: `<ip-domain-db>`
    - `DATABASE_PORT`: `5432` 
    - `DATABASE_NAME`: `<db-name>`
    - `DATABASE_PASSWORD`: `<db-password>`
  need:
    - Database PostgreSQL v14.2
2. Frontend container
  - image: `dimmaryanto93/udemy-angular-app:latest`
  - port: `80`
  - env:
    - `APPLICATION_PORT`: `14.15-alpine`
    - `NGINX_ROOT_DOCUMENT`: `/var/www/html`
    - `BACKEND_HOST`: `<ip-backend-apps>`
    - `BACKEND_PORT`: `<port-backend-apps>`
    - `BACKEND_CONTEXT_PATH`: `/`
  - need:
    - Backend container

Silahkan buat docker-compose filenya, kemudian simpan dalam folder `tasks` dengan nama `docker-compose.yaml`

## Task 3 (Orchestration Container System)

1. Apa yang anda ketahui tentang Orchestration Container System?
2. Kenapa Orchestration Container System seperti Kubernetes sangat popular (menurut anda)?

Cara pengerjaan, silahkan update file ini tulis jawabanya di bawah ini

### Jawaban

1. Orchestration Container System adalah sebuah sistem yang membantu mengatur dan mengelola banyak container yang berjalan di server. Container ini berisi aplikasi atau bagian dari aplikasi. Sistem ini berguna untuk menyederhanakan proses pengaturan, penjadwalan, dan pemantauan container-container ini. Dengan menggunakan sistem ini, kita dapat menyebarkan aplikasi dengan mudah, mengetahui kapan container-container tersebut bermasalah, dan meningkatkan kemampuan aplikasi kita untuk menangani lebih banyak pengguna.
2. Kubernetes sangat populer karena kemampuannya untuk mengatur dan mengelola banyak container aplikasi. Ini membantu orang-orang dengan mudah menyebarkan, memantau, dan memperluas aplikasi mereka. Kubernetes dapat mengatur container di banyak komputer atau server sehingga aplikasi tetap berjalan dengan baik. Hal ini membuat pengelolaan aplikasi yang kompleks menjadi lebih mudah dan efisien. Kubernetes juga mendukung berbagai macam platform, termasuk public cloud dan data center lokal, sehingga kita dapat menggunakan kubernetes di manapun aplikasi kita berjalan. Fitur-fiturnya bagus dan komunitasnya juga aktif, Kubernetes jadi pilihan populer bagi para developer dan organisasi dalam mengelola aplikasi mereka.
