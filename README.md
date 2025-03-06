# w5-db-voting-Private
# Poll DB 1 - Queries

## Learning Competencies

- Mampu untuk menggunakan statement SQL untuk populate data

## Summary

Silakan mempelajari terlebih dahulu lebih lanjut mengenai SQL dan PostgreSQL.

## Levels

### Level 0 : Create Table

Dari schema `Poll DB` yang telah kamu kerjakan kemarin, Implementasikanlah menjadi table pada postgreSQL

Kerjakan pada file setup.js yang telah disediakan

### Level 1 : Seed Data

Setelah tabel-tabel dari schema `Poll DB` telah kamu buat, lakukan insert data ke tabel `Politicians`, `Voters` dan `Votes`menggunakan data yang telah disediakan pada file politicians.csv, voters.csv, votes.csv.

Baca file-file tersebut menggunakan fungsi readFileSync kemudian lakukan perulangan untuk insert data-data tersebut ke tabel yang telah kamu buat.

**NOTE** Data di-input harus sesuai dengan urutan pada file csv

### Level 2 : Create, Update, and Delete Data

Buatlah function untuk:

- Insert data ke tabel yang diinginkan
- Update data yang diinginkan berdasarkan id data
- Delete data yang diinginkan berdasarkan id data

**NOTE** Jangan melakukan update/delete untuk data-data yang di-mention pada file-file csv yang diberikan

### Level 3 :

Mari kita mulai dengan query-query sederhana.

1. Tampilkan nama politician, partai dan grade_current politician tersebut yang berada di partai `R` dan memiliki grade_current range 9 s/d 11

   ```bash
   // Output:
       [ { name: 'Bill Cassidy',
           party: 'R',
           grade_current: 9.285165569 },
         { name: 'Dana Rohrabacher',
           party: 'R',
           grade_current: 10.64634133 },
         { name: 'Frank Guinta',
           party: 'R',
           grade_current: 10.94131093 }
       ]
   ```

2. Hitung jumlah vote untuk politician yang bernama `Olympia Snowe`.

   ```bash
   // Output:
        [ { totalVote: 4, name: 'Olympia Snowe' } ]
   ```

3. Hitung jumlah vote untuk politician yang nama-nya mengandung kata `Adam`.

   ```bash
   // Output:
        [ { name: 'Adam Kinzinger', totalVote: 6 },
          { name: 'Adam Schiff', totalVote: 7 },
          { name: 'Adam Smith', totalVote: 11 }
        ]
   ```

4. Tampilkan 3 Politician beserta nama partai dan lokasi Politician tersebut, yang memiliki suara terbanyak.

   ```bash
   // Output:
        [ { totalVote: 51,
            name: 'Candice Miller',
            party: 'R',
            location: 'WA' },
          { totalVote: 11,
            name: 'Adam Smith',
            party: 'D',
            location: 'WA' },
          { totalVote: 11,
            name: 'Anna Eshoo',
            party: 'D',
            location: 'WA' }
        ]
   ```

5. Tampilkan siapa saja yang melakukan voting ke politician yang bernama `Olympia Snowe`

   ```bash
   // Output:
       [ { first_name: 'Aaliyah',
           last_name: 'Langworth',
           gender: 'male',
           age: 61 },
         { first_name: 'Prudence',
           last_name: 'Kilback',
           gender: 'female',
           age: 88 },
         { first_name: 'Ricardo',
           last_name: 'Koss',
           gender: 'female',
           age: 65 },
         { first_name: 'Zechariah',
           last_name: 'Wolff',
           gender: 'female',
           age: 60 }
      ]
   ```

**NOTE**

Gunakanlah library [cli-table](https://github.com/Automattic/cli-table) / `console.table()` jika kamu ingin ber-eksperimen membuat hasil query kamu berada dalam tabel.

```bash
Example Output:

╔════════════════════╤══════════╤════════════════════╗
║ Name               │ Party    │ Grade Current      ║
╟────────────────────┼──────────┼────────────────────╢
║ Bill Cassidy       │ R        │ 9.285165569        ║
╟────────────────────┼──────────┼────────────────────╢
║ Dana Rohrabacher   │ R        │ 10.64634133        ║
╟────────────────────┼──────────┼────────────────────╢
║ Frank Guinta       │ R        │ 10.94131093        ║
╚════════════════════╧══════════╧════════════════════╝
```