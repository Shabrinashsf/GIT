# Version Control System (Git)

## Apa itu Version Control System
Version control adalah sistem yang melacak semua perubahan yang dilakukan didalam file.

## Apa itu Git
Git adalah version control system versi terdistribusi. Git membuat developer dapat mengerjakan salinan project lokal mereka sendiri tanpa harus mengirim perubahannya ke repositori bersama. Git membantu mengelola dan melacak perubahan pada kode dengan cara yang terdesentralisasi. Simpelnya kita gak butuh server pusat untuk menyimpan seluruh riwayat perubahan pada kode project kita, setiap developer yang terlibat dalam project memiliki salinan lengkap tentang riwayat perubahan project. Hal ini membuat git sangat useful apabila ada masalah server yang down.

## Hal-hal yang dapat dilakukan Git
### 1. Menyimpan dan melacak perubahan atau modifikasi yang dibuat pada kode

### 2. Mengembalikan kode ke versi sebelumnya
Jika ada sesuatu yang error atau ada fitur yang tidak berfungsi dari apa yang diharapkan, maka kita dapat mengembalikan kodenya ke kondisi awal sebelum fitur itu ditambahkan.

### 3. Memungkinkan kita berkolaborasi/ bekerja dalam tim
Satu project besar biasanya akan dikerjakan oleh beberapa developer yang pastinya akan mengerjakan bagian dan tugasnya masing-masing, dengan menggunakan git kita dapat menggabungkan/ menimpa fitur atau tugas yang dibebankan ke kita satu sama lain. Simpelnya kita dapat nimpa kerjaan kita ke kerjaan teman kita.

### 4. Percabangan dan penggabungan
Saat ada fitur yang ingin ditambahkan ke dalam project dan kita ragu apakah fitur ini akan diperlukan atau tidak, ketika ragu kita bisa membuat percabangan dalam kode kita dengan menggunakan percabangan. lalu kita dapat mengerjakan fiturnya dalam percabangan. Apabila dirasa fitur tersebut nantinya diperlukan dan dapat berfungsi dengan baik dan kita ingin menambahkan fitur ini ke main project kita, maka kita bisa menggunakan penggabungan agar fitur yang tadi kita kerjakan dapat digabung dengan main project kita.

## Basic tentang git yang wajib kita ketahui (Dasar banget)
Sebelum masuk dan belajar tentang command git, ada baiknya kita instal git dulu yak.

### Configure Git
Ini dilakukan supaya git dapat mengetahui siapa kamu
```
git config --global user.name "(username kamu)"
git config --global user.email "(email kamu)"
```
Note:
Global digunakan untuk ngeset username dan email yang sama ke semua repository yang ada di komputer kamu. jika kamu cuma mau nge set username dan email di satu repo atau repo tertentu saja, kamu bisa hilangkan global.

## Creating Git Folder
```
mkdir <nama-project-kamu>
cd <nama-project-kamu>
```
mkdir artinya buat sebuah direktori baru bernama <nama-project-kamu>
cd artinya pindah dari direktori ... ke direktori <nama-project-kamu>

## Initialize Git
1. Masuk ke foder project yang sedang dikerjakan di terminal.
2. Inisialisasi git di project tersebut dengan menjalankan
   ```
   git init
   ```
Ini akan membuat suatu folder .git yang tersembunyi yang nantinya akan ngetrack segala perubahan pada project kita.

## Adding New Files
Repo git yang udah dibuat tadi kan masih kosongan, jadi kita harus nambahin file kode kita yang udah kita tulis dan kita save ke folder yang tadi kita buat <nama-project-kamu>. misal kita mau nyimpan file bernama index.html

Kita cek statusnya dulu
```
git status
```
outputnya:
```
On branch master

No commits yet

Untracked files:
  (use "git add ..." to include in what will be committed)
    index.html

nothing added to commit but untracked files present (use "git add" to track)
```

Artinya git sudah tahu filenya ada, tapi filenya belum ditambahkan ke repositori kita.

File dalam repositori git bisa memiliki 2 status:
- tracked => file yang dikenali git dan sudah ditambahkan kedalam repositori.
- untracked => file yang ada di direktori yang sedang bekerja, tapi belum ditambahkan kedalam repositori.

Ketika kita pertama kali menambahkan file kedalam repositori yang kosong, mereka semua berada dalam status untracked. Agar dapat membuat git dapat nge track mereka, kita perlu untuk membuat stage atau menambahkan mereka ke staging environment.

command untuk nambahin file index.html kedalam repo
```
git add index.html
```

kalau berhasil
```
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached ..." to unstage)
    new file: index.html
```

Untuk menambahkan semua file yang ada di direktori kedalam repo
```
git add --all
```

## Git Commit
Menambahkan commit akan mentrack semua perubahan yang kita lakukan Ketika sedang mengerjakan suatu project. Git akan memandang commit sebagai save point. Save point ini yang nantinya akan memungkinkan kita untuk kembali ke savepoint sebelmnya ketika kita punya bug atau sesuatu yang ingin kita ubah.

Ketika kita melakukan commit, kita sebaiknya selalu menambahkan pesan, untuk memudahkan kita atau rekan tim untuk melihat perubahan apa yang telah dilakukan.

```
git commit -m "<pesan-yang-akan-ditampilkan>"
```
-m == message

## Git Commit Log
Untuk melihat history dari commits yang ada di repositori
```
git log
```

## Git Branch
Branch itu simpelnya kayak cabang dari main repository. Biasanya dipake ketika sedang mengerjakan project besar dan kamu mau update sesuatu dalam project itu. Branch memungkinkan kita untuk bekerja di part project yang berbeda tanpa perlu menghawatirkan apakah perubahan yang dilakukan berdampak pada cabang utama. Ketika sudah selesai branch nantinya dapat di merge.

Kamu dapat membuat lebih dari 1 cabang dan mengerjakannya dengan isi yg berbeda tanpa menghawatikan apakah satu cabang berdampak pada cabang lain.

Membuat branch baru
```
git branch <nama-branch>
```
Membuat branch baru dan berpindah ke branch itu
```
git checkout -b <nama-brach>
```
Untuk kembali ke branch tertentu
```
git checkout <nama-branch>
```

## Git Branch Merge
1. kita harus kembali ke branch Utama
2. Kita merge branch utama dengan brach x
   ```
   git merge x
   ```
3. hapus branch x karena udh di merge kan tadi
```
git branch -d x
```
