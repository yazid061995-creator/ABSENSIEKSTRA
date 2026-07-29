<!DOCTYPE html>

<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Absensi Ekstrakurikuler SDI Lukman Al Hakim Bojonegoro</title>

<style>

body{
font-family:Arial, sans-serif;
background:#f1f5f9;
margin:0;
padding:15px;
}

.container{
max-width:900px;
margin:auto;
background:white;
padding:20px;
border-radius:15px;
box-shadow:0 0 10px #aaa;
}

h2{
text-align:center;
}
label{
font-weight:bold;
}

input,select,button{
width:100%;
padding:10px;
margin:6px 0;
border-radius:8px;
border:1px solid #ccc;
font-size:16px;
}
button{
background:#2563eb;
color:white;
cursor:pointer;
}

table{
width:100%;
border-collapse:collapse;
margin-top:15px;
}

th,td{
border:1px solid #999;
padding:8px;
text-align:center;
}

th{
background:#e2e8f0;
}


@media(max-width:600px){

table{
font-size:12px;
}

input,select,button{
font-size:14px;
}

}

@media print{

button{
display:none;
}

body{
background:white;
}

.container{
box-shadow:none;
}

}

</style>

</head>


<body>

<div class="container">


<h2>
ABSENSI PENGAMPU EKSTRAKURIKULER<br>
SDI LUKMAN AL HAKIM BOJONEGORO
</h2>


<label>Ekstrakurikuler</label>

<select id="ekstra">

<option>KALIGRAFI</option>
<option>TAHFIDZ</option>
<option>BAHASA INGGRIS/STORY TELLING</option>
<option>KRIYA ANYAM</option>
<option>MATEMATIKA</option>
<option>TILAWAH</option>
<option>MUHADOROH</option>
<option>CALISTUNG</option>
<option>MEWARNAI</option>
<option>MENGAJI/HAFALAN</option>
</select>


<label>Nama Pengampu</label>

<input id="guru" placeholder="Masukkan nama pengampu">


<label>Tanggal Pertemuan</label>

<input type="date" id="tanggal" onchange="hariOtomatis()">



<label>Hari</label>

<input id="hari" readonly>
<tr>
 <td><tb>Kelas</tb></td> 
 <td>
    <label><input>
    
 </td>  
</tr>



<table>

<tr>
<th>No</th>
<th>Keterangan</th>
<th>Jumlah</th>
</tr>


<tr>
<td>1</td>
<td>Hadir</td>
<td>
<input type="number" id="hadir" value="0">
</td>
</tr>


<tr>
<td>2</td>
<td>Izin</td>
<td>
<input type="number" id="izin" value="0">
</td>
</tr>


<tr>
<td>3</td>
<td>Sakit</td>
<td>
<input type="number" id="sakit" value="0">
</td>
</tr>
<tr>
<td>4</td>
<td>Alfa</td>
<td>
<input type="number" id="alfa" value="0">
</td>
</tr>


</table>



<br>


<button onclick="window.print()">
🖨️ Cetak
</button>


<button onclick="simpanPDF()">
📄 Simpan PDF
</button>


<button onclick="kirimWA()">
📱 Kirim WhatsApp
</button>


</div>
<script>


function hariOtomatis(){

let tgl=document.getElementById("tanggal").value;

if(tgl){

let hari=
[
"Minggu",
"Senin",
"Selasa",
"Rabu",
"Kamis",
"Jumat",
"Sabtu"
];

let tanggal=new Date(tgl);

document.getElementById("hari").value=
hari[tanggal.getDay()];

}

}



function simpanPDF(){

window.print();

}



function kirimWA(){


let nomor="6285790331230"; 
// GANTI DENGAN NOMOR TUJUAN


let pesan=
"ABSENSI EKSTRAKURIKULER SDI LUKMAN AL HAKIM BOJONEGORO\n\n"+
"Ekstrakurikuler : "+
document.getElementById("ekstra").value+
"\n"+
"Pengampu : "+
document.getElementById("guru").value+
"\n"+
"Hari : "+
document.getElementById("hari").value+
"\n"+
"Tanggal : "+
document.getElementById("tanggal").value+
"\n\n"+
"Hadir : "+
document.getElementById("hadir").value+
"\nIzin : "+
document.getElementById("izin").value+
"\nSakit : "+
document.getElementById("sakit").value+
"\nAlfa : "+
document.getElementById("alfa").value;


let url=
"https://wa.me/"+nomor+
"?text="+
encodeURIComponent(pesan);


window.open(url,"_blank");


}



</script>


</body>
</html>
