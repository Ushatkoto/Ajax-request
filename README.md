# Ajax-request
<!DOCTYPE html>
<html>
<style>
table,th,td {
  border : 1px solid black;
  border-collapse: collapse;
}
th,td {
  padding: 5px;
}
</style>
<body>

<h1>Clients Niki</h1>

<form action=""> 
<select name="customers" onchange="showCustomer(this.value)">
<option value="">Select a customer:</option>
<option value="1ajax">Don icaka</option>
<option value="2ajax">Don Garda</option>
<option value="3ajax">Don Anton</option>
</select>
</form>
<br>
<div id="txtHint">Customer info </div>
<script src="test.js"></script>
<script>
function showCustomer(str) {
  var xhttp;    
  if (str == "") {
    document.getElementById("txtHint").innerHTML = "";
    return;
  }
  xhttp = new XMLHttpRequest();
  xhttp.onreadystatechange = function() {
    if (this.readyState == 4 && this.status == 200) {
      document.getElementById("txtHint").innerHTML = this.responseText;
    }
  };
  xhttp.open("GET", "getcustomer.php?q="+str, true);
  xhttp.send();
}
</script>


</body>
</html>
