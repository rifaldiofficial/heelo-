<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
   "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html>
<head>
<title>login</title>
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
<meta http-equiv="pragma" content="no-cache" />
<meta http-equiv="expires" content="-1" />
<meta name="viewport" content="width=device-width; initial-scale=1.0; maximum-scale=1.0;"/>
<link rel="stylesheet" type="text/css" href="style.css">
<script src="d3.v3.min.js"></script>
</head>

<body>
<table width="100%" style="margin-top: 10px;">
	<tr>
	
	
</table>
<div class="main">
<table align="center">
	<tr>
		<td>
<!--			<div class?"notice" style="font-size: 14px; padding-top:5px; text-align:center; color:red;">Mohon maaf Internet Telkom dalam perbaikan, jadi koneksi kadang terputus.</div>-->
			<div class?"notice" style="font-size: 25px; padding-top:10px; text-align:center;">HOTSPOT RIFKI</div>
			<!--<div class?"notice" style="font-size: 14px; text-align:center;">Masa Aktif Voucher  <a href="./detail.html">Klik Disini</a></div><br />-->
		</td>
	</tr>
</table>


<div >
$(if chap-id)
	<form name="sendinkv" action="$(link-login-only)" method="post">
		<input type="hidden" name="username" />
		<input type="hidden" name="password" />
		<input type="hidden" name="dst" value="$(link-orig)" />
		<input type="hidden" name="popup" value="true" />
	</form>

	<script type="text/javascript" src="/md5.js"></script>
	<script type="text/javascript">
	<!--
	    function doLoginkv() {
		document.sendinkv.username.value = document.loginkv.usernamekv.value;
		document.sendinkv.password.value = hexMD5('$(chap-id)' + document.loginkv.usernamekv.value + '$(chap-challenge)');
		document.sendinkv.submit();
		return false;
	    }
	//-->
	</script>
$(endif)

<table width="100%">
	<table align="center">
		<tr>
		<td style="font-size: 14px; text-align:center;">Login Kode Voucher<br />$(if trial == 'yes')Coba gratis, <a href="$(link-login-only)?dst=$(link-orig-esc)&amp;username=T-$(mac-esc)">klik disini</a>.$(endif)</td><br />
		</tr>
	</table>
	<table align="center"class="tlogin">
		<tr>
		<td align="center" valign="bottom" height="70" colspan="2">
			<form autocomplete="off" name="loginkv" action="$(link-login-only)" method="post"
			$(if chap-id) onSubmit="return doLoginkv()" $(endif)>
				<input type="hidden" name="dst" value="$(link-orig)" />
				<input type="hidden" name="popup" value="true" />
					<table width="100">
						<tr>
							<td>&nbsp;</td>
						</tr>
						<tr>
							<td colspan=2><input  name="usernamekv" type="text" placeholder="Kode Voucher"  onchange="updateInput(this.value)" value="$(username)"/></td>
						</tr>
						<tr>
						  <td colspan=2><input id="pass" name="passwordkv" placeholder="Password" type="hidden"/></td>
						</tr>
						<td colspan=2 align="center";><input type="submit" class="button" value=" Login | Masuk" /></td>
					</tr>
					$(if error)<br /><div style="color: red; font-size: 14px">kode voucher tidak sesuai atau sudah dipakai!</div>$(endif)
					</table>
			</form>
		</td>
		</tr>
	</table>
</div>

<script>
function openLogin(evt, loginName) {
    var i, tabcontent, tablinks;
    tabcontent = document.getElementsByClassName("tabcontent");
    for (i = 0; i < tabcontent.length; i++) {
        tabcontent[i].style.display = "none";
    }
    tablinks = document.getElementsByClassName("tablinks");
    for (i = 0; i < tablinks.length; i++) {
        tablinks[i].className = tablinks[i].className.replace(" active", "");
    }
    document.getElementById(loginName).style.display = "block";
    evt.currentTarget.className += " active";
}

// Get the element with id="defaultOpen" and click on it
document.getElementById("defaultOpen").click();
</script>
	<table align="center">
		<tr>
			<td align="center">
				<br /><div style="font-size: 14px; color: black;">Biaya Pemasangan Internet Bisa hubungi nomer HP Di bawah ini</div>
				<br /><div style="font-size: 14px; color: black;">082293186344</div>
			</td>
		</tr>
</table>
<script type="text/javascript" charset="utf-8">
            d3.text("paket-wifi.csv", function(data) {
                var parsedCSV = d3.csv.parseRows(data);

                var container = d3.select("table.tpaketwifi")
                    .append("div")

                    .selectAll("tr")
                        .data(parsedCSV).enter()
                        .append("tr")

                    .selectAll("td")
                        .data(function(d) { return d; }).enter()
                        .append("td")
                        .text(function(d) { return d; });
            });
</script>
<script type="text/javascript">
<!--
  document.login.username.focus();
//-->
</script>
</body>
</html>
