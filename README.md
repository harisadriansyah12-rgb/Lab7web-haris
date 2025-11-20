# Praktikum 7
# Haris Adriansyah
# 3123410286
# Pemograman Web 1
# Agung Nugroho, S.Kom., M.Kom.

### Persiapan
Install XAMPP dari https://www.apachefriends.org

Jalankan Apache dan MySQL melalui XAMPP Control Panel.

Buat folder baru bernama lab7_php_dasar di direktori:
`
C:\xampp\htdocs\
`

Buka folder tersebut di VS Code atau text editor pilihanmu.
Langkah-langkah Praktikum
### 1. Membuat File PHP Dasar
File:` php_dasar.php`
```python
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>PHP Dasar</title>
</head>
<body>
    <h1>Belajar PHP Dasar</h1>
    <?php
        echo "Hello World";
    ?>
</body>
</html>
```
Hasil: Tampilkan di browser melalui URL: `php_dasar.php`
<img width="1358" height="764" alt="Cuplikan layar 2025-11-17 122631" src="https://github.com/user-attachments/assets/4a329624-6c77-4685-a0f5-a000e0955ee8" />
### 2. Menambahkan Variabel PHP
File: `http://localhost/lab7_php_dasar/php_dasar.php`
```python
<?php
$nim = "312410286";
$nama = "Haris adriansyah";
echo "NIM: $nim <br>";
echo "Nama: $nama";
?>
```
Hasil: Tampilkan di browser melalui URL: `http://localhost/lab7_php_dasar/php_dasar.php`
<img width="1906" height="1127" alt="Cuplikan layar 2025-11-17 124347" src="https://github.com/user-attachments/assets/2e71a753-9c50-48ab-bfd5-adc10883535a" />

### 3. Predefine Variable $_GET
File:` latihan2.php`
```python
<?php
echo 'Selamat Datang ' . $_GET['nama'];
?>
```
Akses dengan URL:`http://localhost/Pemograman Web/latihan2.php?nama=MufidaZulfi`
<img width="1919" height="1062" alt="Cuplikan layar 2025-11-17 125953" src="https://github.com/user-attachments/assets/8dbcb0b6-0aa8-42de-8494-2c363d72201e" />

### 4. form input

```python
<!DOCTYPE html>
<html>
<head><title>Form Input</title></head>
<body>
<h2>Form Input</h2>
<form method="post">
    <label>Nama: </label>
    <input type="text" name="nama">
    <input type="submit" value="Kirim">
</form>

<?php
echo 'Selamat Datang ' . $_POST['nama'];
?>
</body>
</html>
```
### hasilnya
<img width="1911" height="1045" alt="Cuplikan layar 2025-11-17 132108" src="https://github.com/user-attachments/assets/2a57c77c-30ba-4206-9092-c7ca20dd4144" />

###  5. operator

```python
<?php
$gaji = 1000000;
$pajak = 0.1;
$thp = $gaji - ($gaji * $pajak);
echo "Gaji Sebelum Pajak = Rp. $gaji <br>";
echo "Gaji Bersih = Rp. $thp";
?>
```
<img width="491" height="373" alt="image" src="https://github.com/user-attachments/assets/b53d4488-d92f-4dd3-8483-aae337667350" />

### Struktur Kondisi 
### IF ELSE
```python
<?php
$hari = date("l");
if ($hari == "Sunday") echo "Minggu";
elseif ($hari == "Monday") echo "Senin";
else echo "Hari lainnya";
?>
```
### hasil tampilanya
<img width="460" height="145" alt="image" src="https://github.com/user-attachments/assets/da6f9970-b738-4043-a0e9-93fbadd8d2f5" />

### ForLoop
```python
<?php
for ($i=1; $i<=10; $i++) {
    echo "Perulangan ke-$i <br>";
}
?>
```
### hasilnya
<img width="952" height="244" alt="image" src="https://github.com/user-attachments/assets/e069b91b-d570-4431-a62a-b910b9e9301f" />

# Tugas
<img width="587" height="291" alt="image" src="https://github.com/user-attachments/assets/7b04ee4e-d4a7-4c8a-8929-3157280ee18a" />

file: `biodata.php`
```python
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Form Biodata</title>
</head>
<body>
<h2>Form Biodata</h2>
<form method="post">
    Nama: <input type="text" name="nama"><br>
    Tanggal Lahir: <input type="date" name="tgl_lahir"><br>
    Pekerjaan:
    <select name="pekerjaan">
        <option value="Programmer">Programmer</option>
        <option value="Designer">Designer</option>
        <option value="Manager">Manager</option>
    </select><br><br>
    <input type="submit" value="Kirim">
</form>

<?php
if ($_POST) {
    $nama = $_POST['nama'];
    $tgl = $_POST['tgl_lahir'];
    $pekerjaan = $_POST['pekerjaan'];

    $umur = date_diff(date_create($tgl), date_create('today'))->y;

    switch ($pekerjaan) {
        case 'Programmer': $gaji = 8000000; break;
        case 'Designer': $gaji = 6000000; break;
        case 'Manager': $gaji = 10000000; break;
        default: $gaji = 0; break;
    }

    echo "<h3>Hasil Output:</h3>";
    echo "Nama: $nama <br>";
    echo "Umur: $umur tahun <br>";
    echo "Pekerjaan: $pekerjaan <br>";
    echo "Gaji: Rp. " . number_format($gaji, 0, ',', '.');
}
?>
</body>
</html>
```
### Hasilnya
<img width="955" height="367" alt="image" src="https://github.com/user-attachments/assets/95cad2e6-c4fb-4293-aab5-cd0d5c99218a" />

