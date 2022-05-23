# Pemrograman Mobile
# Vrantika Br-Samosir 20190801237
# Pembuatan mobile apps E- Distribusi Agent.

**# Source code form data barang**

<!doctype html>
<html>
    <head>
        <title>Pagination with Boostrap 3 - harviacode.com</title>
       <link rel="stylesheet" href="../bootstrap/css/bootstrap.min.css"/> 
        <script src="../bootstrap/js/jquery.min.js"></script>
        <!-- Include all compiled plugins (below), or include individual files as needed -->
       <script src="../bootstrap/js/bootstrap.min.js"></script>
        <style>
            /*custom css*/
            .pagination, .pager{
                margin-top: 0px
            }
            .table{
                margin-top: 20px;
            }
        </style>




<?php
echo "
<br/>
<h3>Form Tambah Data Barang</h3>
<form method=post action=simpan_barang.php>
 <table style='font-family:sans-serif'; class='table table-bordered'>
   <tr>
   <td>Nama Barang</td>
   <td><input  class=form-control type=text name=nama></td>
  </tr>
  <tr>
   <td>Jenis Barang</td>
   <td><input  class=form-control type=text name=jenis></td>
  </tr>
  <tr>
   <td>Ukuran</td>
   <td><input class=form-control type=text name=ukuran></td>
  </tr>
  <tr>
   <td>Warna</td>
   <td><input class=form-control type=text name=warna></td>
  </tr>
  <tr>
   <td>ID Supplier</td>
   <td><input  class=form-control type=text name=id_supplier></td>
  </tr>
  <tr>
   <td>Harga</td>
   <td><input class=form-control type=text name=harga></td>
  </tr>
  <tr>
   <td>Jumlah</td>
   <td><input class=form-control type=text name=jumlah></td>
  </tr>
  <tr>
   <td><input type=submit  class='btn btn-primary' value='Simpan'></td>
  </tr>
   <tr>
   <td>ID Barang / Barcode</td>
   <td><input class=form-control type=text name=id_barang></td>
  </tr>
 </table>
</form>
";
?>

 
**# Mutakhir Barang**
 
        
 <!doctype html>
<html>
    <head>
        <title>Pagination with Boostrap 3 - harviacode.com</title>
       <link rel="stylesheet" href="../bootstrap/css/bootstrap.min.css"/> 
        <script src="../bootstrap/js/jquery.min.js"></script>
        <!-- Include all compiled plugins (below), or include individual files as needed -->
       <script src="../bootstrap/js/bootstrap.min.js"></script>
        <style>
            /*custom css*/
            .pagination, .pager{
                margin-top: 0px
            }
            .table{
                margin-top: 20px;
            }
        </style>



<?php
$kiriman = $_GET['data'];

include "../../config.php";

$barang=mysql_query("select * from barang where id_barang='$kiriman'");

$data_barang = mysql_fetch_array($barang);

echo "

<br/><br/><br/><br/>
<center>
<form action=simpan_mutakhir_barang.php method=post>
 <table style='font-family:sans-serif'; class='table table-bordered'>
  <tr>
   <td>ID Barang</td><td>:</td>
   <td><input <input class=form-control type=text name=id_barang value='$data_barang[0]' readonly></td> 
  </tr>
  <tr>
   <td>Nama Barang</td> <td>:</td>
   <td><input  class=form-control type=text name=nama value='$data_barang[1]'></td>
  </tr>
  <tr>
   <td>Jenis Barang</td><td>:</td>
   <td><input class=form-control type=text name=jenis value='$data_barang[2]'></td>
  </tr>
  <tr>
   <td>Ukuran</td><td>:</td>
   <td><input class=form-control type=text name=ukuran value='$data_barang[3]'></td>
  </tr>
  <tr>
   <td>Warna</td><td>:</td>
   <td><input class=form-control type=text name=warna value='$data_barang[4]'></td>
  </tr>
  <tr>
   <td>ID Supplier</td><td>:</td>
   <td><input class=form-control type=text name=id_supplier value='$data_barang[5]'></td>
  </tr>
  <tr>
   <td>Harga</td><td>:</td>
   <td><input class=form-control type=text name=harga value='$data_barang[6]'></td>
  </tr>
  <tr>
   <td>Jumlah</td><td>:</td>
   <td><input class=form-control type=text name=jumlah value='$data_barang[7]'></td>
  </tr>
  <tr>
   <td><input type=submit  class='btn btn-primary' value='Simpan Mutakhir'></td>
   <td><a href=index.php><input   class='btn btn-primary' type=button value=Batal></a></td>
  </tr>
 </table>
</form>
</center>
";
?>

        
        
**# Hapus data barang**
        
        
<?php
$kiriman = $_GET["data"];

echo $kiriman;
 
include "../../config.php";
 
$hapus = mysql_query("DELETE FROM `barang` WHERE id_barang = '".$kiriman."'");
 
if ($hapus)
 {
?>

<script type=text/javascript>
 alert ('Data Berhasil di Hapus');
 window.location='index.php';
</script>

<?php
}
else
{
?>
<script type=text/javascript>
 alert ('Data Gagal di Hapus');
 window.location='index.php';
</script>
<?php
}
?>

        
        
**# Indek admin.php**
        
        
<script type=text/javascript>
	
 function pesan_hapus(dt)
	{
		var pesan = confirm('Anda yakin akan menghapus data?');
		if (pesan)
		{
	      window.location='hapus_barang.php?data='+dt;
		}
		else
		{
			window.location='index.php';
		}
	}
</script>

<doctype html>
<html>
    <head>
        <title></title>
        <link rel="stylesheet" href="../bootstrap/css/bootstrap.min.css"/> 
        <script src="../bootstrap/js/jquery.min.js"></script>
        <!-- Include all compiled plugins (below), or include individual files as needed -->
       <script src="../bootstrap/js/bootstrap.min.js"></script>
        <style>
            /*custom css*/
            .pagination, .pager{
                margin-top: 0px
            }
            .table{
                margin-top: 20px;
            }
                      .th{ background-color:#00D9FF; font-size: 0.875em; font-weight: bold; }
                      .tr{font-size: 0.675em;}
                      
        </style>
    </head>
    <body>
        <?php
//        includekan fungsi paginasi
//        silahkan di komen atau di hapus saja baris yang tidak ingin digunakan
        include 'pagination.php';
        include '../../barcode/barcode_generator/barcode128.php';
        //include 'paging/pagination2.php';
        //include 'paging/pagination3.php';
       // include 'paging/pagination4.php';
       // include 'paging/pagination5.php';

//        pagination config start
        $q = isset($_REQUEST['q']) ? urldecode($_REQUEST['q']) : ''; // untuk keyword pencarian
        $page = isset($_GET['page']) ? intval($_GET['page']) : 1; // untuk nomor halaman
        $adjacents = isset($_GET['adjacents']) ? intval($_GET['adjacents']) : 3; // khusus style pagination 2 dan 3
        $rpp = 15; // jumlah record per halaman

        $db_link = mysqli_connect('localhost', 'root', '', 'toko'); // sesuaikan username dan password mysqli anda
        $sql = "SELECT * FROM barang WHERE nama_brg LIKE '%$q%' OR id_barang LIKE '%$q%' ORDER BY nama_brg"; // query silahkan disesuaikan
        $result = mysqli_query($db_link, $sql); // eksekusi query

        $tcount = mysqli_num_rows($result); // jumlah total baris
        $tpages = isset($tcount) ? ceil($tcount / $rpp) : 1; // jumlah total halaman
        $count = 0; // untuk paginasi
        $i = ($page - 1) * $rpp; // batas paginasi
        $no_urut = ($page - 1) * $rpp; // nomor urut
        $reload = $_SERVER['PHP_SELF'] . "?q=" . $q . "&amp;adjacents=" . $adjacents; // untuk link ke halaman lain
//        pagination config end
        ?>
        <div>

            <!--judul -->
            <div class="row">
                <div class="col-md-12">
                    <h1>Tabel Barang</h1>
                </div>
            </div>

            <!--form pencarian-->
            <div class="row">
                <div class="col-md-8">
                </div>
                <div class="col-md-4">
                    <form action="<?php echo $_SERVER['PHP_SELF'] ?>" method="GET">
                        <div class="input-group">
                            <input type="text" class="form-control" placeholder="Search for..." name="q" value="<?php echo $q ?>">
                            <span class="input-group-btn">
                                <?php
                                if ($q <> '')
                                {
                                    ?>
                                    <a class="btn btn-default" href="<?php echo $_SERVER['PHP_SELF'] ?>">Reset</a>
                                    <?php
                                }
                                ?>
                                <button class="btn btn-primary" type="submit">Go!</button>
                            </span>
                        </div>
                    </form>
                </div>
            </div>

            <!--tabel-->
            <div class="row">
                <div class="col-md-12">
                    <table class="table table-bordered">
                         <thead>
                            <tr>
								<th class="th">No</th>
                                <th class="th">ID Barang</th>
                                <th class="th">Nama Barang</th>
                                <th class="th">Jenis Barang</th>
                                <th class="th">Ukuran</th>
                                <th class="th">Warna</th>
                                <th class="th">ID Supplier</th>
                                <th class="th">Harga</th>
                                <th class="th">Jumlah</th>
                                <th class="th">Aksi</th>
                            </tr>
                        </thead>
                        <tbody>
                            <?php
                            while (($count < $rpp) && ($i < $tcount)) {
                                mysqli_data_seek($result, $i);
                                $data = mysqli_fetch_array($result);
                                ?>
                                <tr class="tr">
                                    <td width="40px">
                                        <?php echo ++$no_urut; ?> 
                                    </td>
                                    <td>
                                        <?php echo $data ['id_barang']; ?> 
                                    </td>
                                     <td>
                                        <?php echo $data ['nama_brg']; ?> 
                                    </td>
                                     <td>
                                        <?php echo $data ['jenis_barang']; ?> 
                                    </td>
                                     <td>
                                        <?php echo $data ['ukuran']; ?> 
                                    </td>
                                     <td>
                                        <?php echo $data ['warna']; ?> 
                                    </td>
                                     <td>
                                        <?php echo $data ['id_suplier']; ?> 
                                    </td>
                                     <td>
                                        <?php echo $data ['harga']; ?> 
                                    </td>
                                     <td>
                                        <?php echo $data ['jumlah']; ?>
                                    </td>
                                    <td width="150px" class="text-center">
									<div class="btn-group btn-group-justified">
										<a href=cetak_barcode.php?data=<?php echo $data ['id_barang']; ?>><button type="button" class="btn btn-default" > <span class="glyphicon glyphicon-barcode"></span></button></a>
                                        <a href=mutakhir_barang.php?data=<?php echo $data ['id_barang']; ?>><button type="button" class="btn btn-info" > <span class="glyphicon glyphicon-pencil"></span></button></a>
                                        <a  href=hapus_barang.php?data=<?php echo $data ['id_barang']; ?>><button type="button" class="btn btn-danger" onClick="return confirm('Apakah anda akan menghapus barang ini?');"  ><span class="glyphicon glyphicon-trash"></span></button></a>
                                    </div>
                                    </td>
                                </tr>
                                <?php
                                $i++;
                                $count++;
                            }
                            ?>
                        </tbody>
                    </table>
                </div>
            </div>

            <!--pagination-->
            <div class="row">
                <div class="col-md-12">
                    <!--silahkan di komen atau di hapus saja baris yang tidak ingin digunakan-->
                    <?php echo paginate_one($reload, $page, $tpages); ?>
                    <a href=form_barang.php> <input class="btn btn-primary" type=button value="+ Tambah Data Barang"></a>
                </div>
            </div>
        </div> <!-- container -->       
    </body>
</html>




**# Simpan data Barang**

<?php
$a 	= $_POST['id_barang'];
$b 	= $_POST['nama'];
$c	= $_POST['jenis'];
$d	= $_POST['ukuran'];
$e	= $_POST['warna'];
$f	= $_POST['id_supplier'];
$g	= $_POST['harga'];
$h	= $_POST['jumlah'];

include "../../config.php";

$barang = mysql_query("select * from barang where id_barang='$a'");

$jm_baris_query = mysql_num_rows($barang);

if($jm_baris_query==1)
{
	echo "Data Sudah Ada";
	exit;
	}
	else
	{
  
  $simpan = mysql_query("INSERT INTO `barang`(`id_barang`, `nama_brg`, `jenis_barang`, `ukuran`, `warna`, `id_suplier`, `harga`, `jumlah`) VALUES ('$a','$b','$c','$d','$e','$f','$g','$h')");					

?>		
<script type=text/javascript>
  window.location='index.php';
</script>
<?php
}
?>


**# pagination.php**

<?php
/*************************************************************************
php easy :: pagination scripts set - Version One
==========================================================================
Author:      php easy code, www.phpeasycode.com
Web Site:    http://www.phpeasycode.com
Contact:     webmaster@phpeasycode.com
*************************************************************************/
function paginate_one($reload, $page, $tpages) {
	
	$firstlabel = "First";
	$prevlabel  = "Prev";
	$nextlabel  = "Next";
	$lastlabel  = "Last";
	
	$out = "<nav><ul class=\"pagination\">\n";
	
	// first
	if($page>1) {
		$out.= "<li><a href=\"" . $reload . "\">" . $firstlabel . "</a></li>\n";
	}
	else {
		$out.= "<li class=\"disabled\"><a href=\"#\">" . $firstlabel . "</a></li>\n";
	}
	
	// previous
	if($page==1) {
		$out.= "<li class=\"disabled\"><a href=\"#\">" . $prevlabel . "</a></li>\n";
	}
	elseif($page==2) {
		$out.= "<li><a href=\"" . $reload . "\">" . $prevlabel . "</a></li>\n";
	}
	else {
		$out.= "<li><a href=\"" . $reload . "&amp;page=" . ($page-1) . "\">" . $prevlabel . "</a></li>\n";
	}
	
	// current
	$out.= "<li class=\"active\"><a href=\"#\">Page " . $page . " of " . $tpages . "</a></li>\n";
	
	// next
	if($page<$tpages) {
		$out.= "<li><a href=\"" . $reload . "&amp;page=" .($page+1) . "\">" . $nextlabel . "</a></li>\n";
	}
	else {
		$out.= "<li class=\"disabled\"><a href=\"#\">" . $nextlabel . "</a></li>\n";
	}
	
	// last
	if($page<$tpages) {
		$out.= "<li><a href=\"" . $reload . "&amp;page=" . $tpages . "\">" . $lastlabel . "</a></li>\n";
	}
	else {
		$out.= "<li class=\"disabled\"><a href=\"#\">" . $lastlabel . "</a></li>\n";
	}
	
	$out.= "</ul></nav>";
	
	return $out;
}
?>


**# Simpan Mutakhir data barang**

<?php
$a 	= $_POST['id_barang'];
$b 	= $_POST['nama'];
$c	= $_POST['jenis'];
$d	= $_POST['ukuran'];
$e	= $_POST['warna'];
$f	= $_POST['id_supplier'];
$g	= $_POST['harga'];
$h	= $_POST['jumlah'];

include "../../config.php";

$mutakhir = mysql_query("UPDATE `barang` SET `nama_brg`='$b',`jenis_barang`='$c',`ukuran`='$d',`warna`='$e',`id_suplier`='$f',`harga`='$g',`jumlah`='$h' WHERE `id_barang`='$a'");					

if ($mutakhir)
 {
?>
<script type=text/javascript>
 alert ('Data Berhasil di Mutakhirkan');
 window.location='index.php';
</script>
<?php
}
?>


**# Source code cetak barcode**

<?php
 include '../../barcode/barcode_generator/barcode128.php';
$kiriman = $_GET['data'];

?>


  <style>
            .table{
                margin: 2cm 4cm 3cm 4cm;
             }
            
  </style>
<center>
  <table class="table"  >
      <tr> <td> <?php echo bar128(stripslashes($kiriman)); ?></td> </tr>
  </table>
  </center>
