
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>PHCC CONNECT</title>

<style>
* {box-sizing:border-box}
body {
  margin:0;
  font-family:Arial,sans-serif;
  background:#f1f5f9;
  color:#183044;
}
header {
  background:#087f69;
  color:white;
  padding:24px 18px;
}
header h1 {margin:0}
.container {padding:18px}
.card {
  background:white;
  padding:18px;
  border-radius:12px;
  margin-bottom:16px;
  box-shadow:0 2px 8px #0001;
}
h2 {color:#087f69}
label {
  display:block;
  margin-top:14px;
  font-weight:bold;
}
input,select {
  width:100%;
  padding:13px;
  margin-top:7px;
  border:1px solid #ccc;
  border-radius:7px;
  font-size:15px;
}
button {
  padding:13px;
  border:0;
  border-radius:7px;
  background:#087f69;
  color:white;
  font-size:15px;
  margin-top:14px;
  cursor:pointer;
}
.submit {width:100%}
.staff {
  background:#e8f5f1;
  padding:12px;
  border-radius:8px;
  margin-top:10px;
  overflow-wrap:anywhere;
}
.delete {background:#b42318}
.count {
  font-size:30px;
  color:#087f69;
  font-weight:bold;
}
footer {
  text-align:center;
  padding:20px;
  color:#64748b;
}
</style>
</head>

<body>

<header>
<h1>🏥 PHCC CONNECT</h1>
<p>Healthcare Management System</p>
<p>Connecting PHCC Workers and Facilities</p>
</header>

<div class="container">

<div class="card">
<h2>Staff Dashboard</h2>
<p>Total Registered Staff</p>
<div class="count" id="total">0</div>
</div>

<div class="card">
<h2>Staff Registration</h2>

<form id="staffForm">

<label>Full Name / Cikakken Suna</label>
<input id="name" required placeholder="Enter full name">

<label>Staff ID</label>
<input id="staffid" required placeholder="Enter staff ID">

<label>Cadre / Matsayin Aiki</label>
<select id="cadre" required>
<option value="">Select Cadre</option>
<option>CHEW</option>
<option>JCHEW</option>
<option>Nurse</option>
<option>Midwife</option>
<option>Doctor</option>
<option>Pharmacy Technician</option>
<option>Medical Laboratory Technician</option>
<option>Other</option>
</select>

<label>Facility / PHCC</label>
<select id="facility" required>
<option value="">Select Facility</option>
<option>PHCC 1</option>
<option>PHCC 2</option>
<option>PHCC 3</option>
</select>

<label>Phone Number</label>
<input id="phone" type="tel" required placeholder="Phone number">

<label>Registration Date</label>
<input id="date" type="date" required>

<button class="submit" type="submit">
Register Staff / Yi Rajista
</button>

</form>
</div>

<div class="card">
<h2>Registered Staff</h2>
<div id="staffList">
No staff registered yet.
</div>
</div>

</div>

<footer>
PHCC CONNECT © 2026
<br>Digital Healthcare Management
</footer>

<script>
let staff = JSON.parse(
 localStorage.getItem("phcc_staff") || "[]"
);

function displayStaff() {
 document.getElementById("total").innerText =
 staff.length;

 const list = document.getElementById("staffList");

 if(staff.length === 0) {
   list.innerHTML = "No staff registered yet.";
   return;
 }

 list.innerHTML = "";

 staff.forEach((person,index) => {
   const item = document.createElement("div");
   item.className = "staff";

   const details = document.createElement("div");
   details.innerText =
    "Name: " + person.name +
    "\nStaff ID: " + person.id +
    "\nCadre: " + person.cadre +
    "\nFacility: " + person.facility +
    "\nPhone: " + person.phone +
    "\nDate: " + person.date;

   const del = document.createElement("button");
   del.className = "delete";
   del.innerText = "Delete";
   del.onclick = function() {
     if(confirm("Delete this staff record?")) {
       staff.splice(index,1);
       saveStaff();
     }
   };

   item.appendChild(details);
   item.appendChild(del);
   list.appendChild(item);
 });
}

function saveStaff() {
 localStorage.setItem(
   "phcc_staff",
   JSON.stringify(staff)
 );
 displayStaff();
}

document.getElementById("staffForm")
.addEventListener("submit",function(e) {
 e.preventDefault();

 const person = {
  name:document.getElementById("name").value,
  id:document.getElementById("staffid").value,
  cadre:document.getElementById("cadre").value,
  facility:document.getElementById("facility").value,
  phone:document.getElementById("phone").value,
  date:document.getElementById("date").value
 };

 staff.push(person);
 saveStaff();
 this.reset();

 alert("Staff registered successfully!");
});

displayStaff();
</script>

</body>
</html>
