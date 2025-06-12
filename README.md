<div align="center"> 
  
# Transfermarkt
#### Scraping Data Transfermarkt untuk Analisis Nilai Pasar dan Performa Pemain Sepak Bola
</div>

![alt text](https://github.com/maisasalsabila/mds_scrapping/blob/main/images/transfermarkt.png?raw=true)

<p align="center">
  <a href="#-deskripsi">Deskripsi</a> •
  <a href="#-project">Project</a> •
  <a href="#-data-scrapping">Data Scrapping</a> •
  <a href="#-document-mongodb">Document MongoDb</a> •
  <a href="#-agregasi-dan-visualisasi">Agregasi dan Visualisasi</a> •
  <a href="#-ppt">PPT</a> •
  <a href="#-team">Team</a> 
</p>

## 📝 Deskripsi
<div align="justify">
Transfermarkt adalah sebuah platform data olahraga yang berfokus pada dunia sepak bola, terutama dalam menyediakan informasi mengenai nilai pasar pemain, data transfer, statistik pertandingan, serta profil pemain, pelatih, dan klub. Sebagai salah satu platform terkemuka, Transfermarkt menjadi sumber utama bagi berbagai analisis data dalam dunia sepak bola modern. Dengan ragam statistik yang tersedia, pengguna dapat memantau performa pemain, tren nilai pasar, dan aktivitas transfer secara lebih efisien. Selain itu, pengembang juga dapat memanfaatkan data dari Transfermarkt untuk melakukan analisis mendalam, membangun model prediksi performa atau nilai pasar pemain, hingga merancang aplikasi visualisasi dalam konteks sepak bola profesional.
</div>

## ⚽️ Project
![alt text](https://github.com/maisasalsabila/mds_scrapping/blob/main/images/Premierleague.jpg?raw=true)

<div align="justify">
Proyek ini bertujuan untuk menjelajahi lebih dalam analisis nilai pasar dan performa pemain sepak bola profesional, khususnya yang bermain di English Premier League (EPL), dengan menggunakan teknik web scraping pada website Transfermarkt. Dengan mengakses data langsung dari Transfermarkt, kita dapat memperoleh wawasan yang mendalam mengenai dinamika pasar pemain, riwayat transfer, statistik performa per musim, serta riwayat cedera. Proyek ini tidak hanya memberikan pemahaman lebih baik tentang hubungan antara performa dan nilai pasar pemain, tetapi juga membuka peluang untuk membangun model prediktif atau sistem rekomendasi dalam dunia sepak bola. Scraping data dari Transfermarkt memungkinkan pengembang untuk mengumpulkan informasi penting dan terstruktur sebagai dasar analisis berbasis data.
Data yang diambil meliputi beberapa poin utama berikut:

- Nama dan identitas pemain: mencakup nama lengkap, kewarganegaraan, umur, tinggi badan, kaki dominan, posisi utama, dan klub saat ini.

- Nilai pasar terkini: harga pasar terbaru dalam euro yang menggambarkan estimasi nilai ekonomi pemain saat ini.

- Riwayat nilai pasar (market value history): mencatat perkembangan nilai pasar dari awal karier hingga saat ini, berdasarkan tanggal dan klub tempat pemain berada.

- Riwayat transfer: mencakup perpindahan antar klub dari musim ke musim, disertai tanggal, klub asal dan tujuan, nilai pasar saat itu, serta biaya transfer (jika tersedia).

- Statistik pertandingan: jumlah penampilan (appearances), menit bermain, assist, kartu kuning, dan kartu merah per musim serta per kompetisi.

- Riwayat cedera: jenis cedera yang dialami, tanggal kejadian, durasi absen (dalam hari), serta jumlah pertandingan yang terlewatkan.

- Prestasi/gelar: daftar penghargaan atau trofi yang diraih oleh pemain selama karier profesionalnya, baik di level klub maupun tim nasional.
</div>

## 🗃️ Data Scrapping
Berikut adalah data yang diambil dari scrapping transfermarkt untuk liga inggris musim 2024/2025 dengan format JSON.

| Field          | Subfield       | Deskripsi                                           |
| -------------- | -------------- | --------------------------------------------------- |
| `_id`          | `$oid`         | Object ID unik dokumen MongoDB                      |
| `player_id`    |                | ID pemain unik                                      |
| `profile`      | `updatedAt`    | Tanggal update profil terakhir                      |
|                | `id`           | ID pemain                                           |
|                | `url`          | URL profil pemain di Transfermarkt                  |
|                | `name`         | Nama singkat pemain                                 |
|                | `description`  | Deskripsi singkat pemain                            |
|                | `fullName`     | Nama lengkap pemain                                 |
|                | `imageUrl`     | URL gambar pemain                                   |
|                | `dateOfBirth`  | Tanggal lahir pemain                                |
|                | `placeOfBirth` | Kota dan negara tempat lahir                        |
|                | `age`          | Usia pemain                                         |
|                | `height`       | Tinggi pemain dalam cm                              |
|                | `citizenship`  | Negara kewarganegaraan                              |
|                | `isRetired`    | Status pensiun pemain                               |
|                | `position`     | Posisi utama pemain                                 |
|                | `foot`         | Kaki dominan pemain                                 |
|                | `shirtNumber`  | Nomor punggung pemain                               |
|                | `club`         | Klub saat ini (termasuk masa kontrak)               |
|                | `marketValue`  | Nilai pasar pemain dalam Euro                       |
|                | `agent`        | Agen pemain                                         |
|                | `outfitter`    | Sponsor perlengkapan pemain                         |
|                | `socialMedia`  | Media sosial pemain                                 |
| `market_value` | `updatedAt`    | Tanggal update nilai pasar terakhir                 |
|                | `id`           | ID pemain                                           |
|                | `marketValue`  | Nilai pasar saat ini                                |
|                | `ranking`      | Ranking pemain (global, liga, klub, negara, posisi) |
| `transfers`    |                | Riwayat transfer pemain                             |
| `stats`        |                | Statistik penampilan pemain per kompetisi           |
| `injuries`     |                | Riwayat cedera pemain                               |
| `achievements` |                | Daftar pencapaian atau pengahargaan  pemain         |


## 📄 Document MongoDb

Terdapat sebanyak 543 dokumen yang digunakan berikut salah satu struktur data MongoDB dari dokumen Ederson Santana de Moraes.

```json
{
  "_id": { "$oid": "6825995b09f2b8643605f2d2" },
  "player_id": "238223",
  "profile": {
    "updatedAt": "2025-05-03T11:36:10.861564",
    "id": "238223",
    "url": "https://www.transfermarkt.com/ederson/profil/spieler/238223",
    "name": "Ederson",
    "description": "Ederson, 31, from Brazil ➤ Manchester City, since 2017 ➤ Goalkeeper ➤ Market value: €25.00m ➤ * Aug 17, 1993 in Osasco, Brazil",
    "fullName": "Ederson Santana de Moraes",
    "imageUrl": "https://img.a.transfermarkt.technology/portrait/header/238223-1713391842.jpg?lm=1",
    "dateOfBirth": "1993-08-17",
    "placeOfBirth": { "city": "Osasco", "country": "Brazil" },
    "age": 31,
    "height": 188,
    "citizenship": ["Brazil", "Portugal"],
    "isRetired": false,
    "position": { "main": "Goalkeeper", "other": [] },
    "foot": "left",
    "shirtNumber": "31",
    "club": { "id": "281", "name": "Man City", "joined": "2017-07-01", "contractExpires": "2026-06-30" },
    "marketValue": 25000000,
    "agent": { "name": "Gestifute", "url": "/gestifute/beraterfirma/berater/413" },
    "outfitter": "Puma",
    "socialMedia": [
      "http://twitter.com/edersonmoraes93",
      "http://www.facebook.com/Ederson93/",
      "http://instagram.com/ederson93/"
    ]
  },
  "market_value": {
    "updatedAt": "2025-05-03T11:36:14.538594",
    "id": "238223",
    "marketValue": 25000000,
    "ranking": {
      "Worldwide": 352,
      "Premier League": 165,
      "Man City": 20,
      "Brazil": 27,
      "Goalkeeper": 10,
      "Year 1993": 2
    }
  },
  "transfers": [{
    "clubFrom": { "name": "Benfica" },
    "clubTo": { "name": "Man City" },
    "date": "2017-07-01",
    "marketValue": 22000000,
    "fee": 40000000
  },
  {
    "clubFrom": { "name": "Rio Ave" },
    "clubTo": { "name": "Benfica" },
    "date": "2015-07-01",
    "marketValue": 1200000,
    "fee": 500000
  }],
  "stats": [{
    "competitionName": "Premier League",
    "seasonId": "24/25",
    "appearances": 23,
    "yellowCards": 3,
    "minutesPlayed": 2
  }],
  "injuries": [{
    "season": "24/25",
    "injury": "Hip problems",
    "fromDate": "2025-04-13",
    "days": 21,
    "gamesMissed": 4
  }],
  "achievements": [{
    "title": "Champions League winner",
    "season": "22/23",
    "club": "Manchester City"
  }, {
    "title": "English Champion",
    "count": 6,
    "seasons": ["17/18", "18/19", "20/21", "21/22", "22/23", "23/24"],
    "club": "Manchester City"
  }]
}
```

Struktur ini mencakup informasi terkait profil pemain, nilai pasar, transfer, statistik pertandingan, riwayat cedera, serta penghargaan pemain
## 📈 Agregasi Dan Visualisasi

Berikut link rpubs :
https://rpubs.com/panjiarf/1320064

## 👨‍💻 PPT

Berikut link slides powerpoint terkait project: 
https://drive.google.com/file/d/1g0QZTRP47POHJCy5tUZprhd7X6tHA0ba/view?usp=sharing

## 👭👬 Team 
<a href="https://github.com/mhmmadyusran">Muhammad Yusran</a><br>
<a href="https://github.com/panjiarf4">Panji Loka Jaya Arifa</a><br>
<a href="https://github.com/Lisa-Amelia">Lisa Amelia</a><br>
<a href="https://github.com/maisasalsabila">Maisa Salsabila</a><br>
