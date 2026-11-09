
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>PHCC CONNECT</title>
<style>
*{box-sizing:border-box}
body{margin:0;font-family:Arial;background:#f1f5f9;color:#183044}
header{background:#087f69;color:white;padding:22px}
main{padding:16px}
.card{background:white;padding:18px;border-radius:12px;margin-bottom:16px}
h2{color:#087f69}
label{display:block;margin-top:13px;font-weight:bold}
input,select{width:100%;padding:12px;margin-top:6px;border:1px solid #ccc;border-radius:7px}
button{background:#087f69;color:white;border:0;padding:13px;border-radius:7px;margin-top:13px;cursor:pointer}
.submit{width:100%}
.record{background:#e8f5f1;padding:12px;border-radius:8px;margin-top:10px;white-space:pre-line}
.count{font-size:30px;color:#087f69;font-weight:bold}
nav{display:flex;gap:8px;flex-wrap:wrap}
nav button{flex:1}
footer{text-align:center;padding:20px;color:#64748b}
</style>
</head>
<body>

<header>
<h1>🏥 PHCC CONNECT</h1>
<p>Digital Healthcare Management System</p>
<p>Connecting Healthcare Facilities</p>
</header>

<main>
<div class="card">
<h2>Dashboard</h2>
<p>Registered Staff</p>
<div class="count" id="staffCount">0</div>
<p>Patient Records (Demo)</p>
<div class="count" id="patientCount">0</div>
</div>

<div class="card">
<h2>Staff Registration</h2>
<form id="staffForm">
<label>Full Name</label>
<input id="staffName" required>
<label>Staff ID</label>
<input id="staffId" required>
<label>Cadre</label>
<select id="cadre" required>
<option value="">Select Cadre</option>
<option>CHEW</option>
<option>JCHEW</option>
<option>Nurse</option>
<option>Midwife</option>
<option>Doctor</option>
<option>Pharmacy Technician</option>
<option>Other</option>
</select>
<label>Facility</label>
<select id="staffFacility" required>
<option value="">Select Facility</option>
<option>PHCC 1</option>
<option>PHCC 2</option>
<option>PHCC 3</option>
</select>
<label>Phone Number</label>
<input id="staffPhone" type="tel" required>
<button class="submit">Register Staff</button>
</form>
</div>

<div class="card">
<h2>Patient Registration (Demo)</h2>
<form id="patientForm">
<label>Age</label>
<input id="age" type="number" min="0" max="120" required>
<label>Gender</label>
<select id="gender" required>
<option value="">Select Gender</option>
<option>Male</option>
<option>Female</option>
</select>
<label>Village / Community</label>
<input id="village" required>
<label>PHCC Facility</label>
<select id="patientFacility" required>
<option value="">Select Facility</option>
<option>PHCC 1</option>
<option>PHCC 2</option>
<option>PHCC 3</option>
</select>
<label>Service Provided</label>
<select id="service" required>
<option value="">Select Service</option>
<option>OPD</option>
<option>ANC</option>
<option>Immunization</option>
<option>Family Planning</option>
<option>Child Health</option>
<option>Health Education</option>
<option>Other</option>
</select>
<label>Date of Visit</label>
<input id="visitDate" type="date" required>
<button class="submit">Register Patient</button>
</form>
</div>

<div class="card">
<h2>Patient Records</h2>
<p>Demo records stored on this device only.</p>
<div id="patientList">No records yet.</div>
</div>

<div class="card">
<h2>Staff Records</h2>
<div id="staffList">No staff yet.</div>
</div>
</main>

<footer>PHCC CONNECT © 2026</footer>

<script>
let staff=JSON.parse(localStorage.getItem("staffDemo")||"[]");
let patients=JSON.parse(localStorage.getItem("patientDemo")||"[]");

function save(){
localStorage.setItem("staffDemo",JSON.stringify(staff));
localStorage.setItem("patientDemo",JSON.stringify(patients));
show();
}

function addText(parent,text){
let p=document.createElement("p");
p.textContent=text;
parent.appendChild(p);
}

function show(){
document.getElementById("staffCount").textContent=staff.length;
document.getElementById("patientCount").textContent=patients.length;

let sl=document.getElementById("staffList");
sl.replaceChildren();
staff.forEach(s=>{
let d=document.createElement("div");
d.className="record";
d.textContent=s.name+" | "+s.id+" | "+s.cadre+" | "+s.facility;
sl.appendChild(d);
});

let pl=document.getElementById("patientList");
pl.replaceChildren();

if(!patients.length){
pl.textContent="No records yet.";
}

patients.forEach(p=>{
let d=document.createElement("div");
d.className="record";
d.textContent=
"Patient ID: "+p.id+
"\nAge: "+p.age+
"\nGender: "+p.gender+
"\nCommunity: "+p.village+
"\nFacility: "+p.facility+
"\nService: "+p.service+
"\nVisit: "+p.date;
pl.appendChild(d);
});
}

document.getElementById("staffForm").onsubmit=function(e){
e.preventDefault();
staff.push({
name:staffName.value,
id:staffId.value,
cadre:cadre.value,
facility:staffFacility.value,
phone:staffPhone.value
});
this.reset();
save();
alert("Staff registered!");
};

document.getElementById("patientForm").onsubmit=function(e){
e.preventDefault();
let id="PHCC-"+Date.now().toString().slice(-8);
patients.push({
id:id,
age:age.value,
gender:gender.value,
village:village.value,
facility:patientFacility.value,
service:service.value,
date:visitDate.value
});
this.reset();
save();
alert("Demo Patient ID: "+id);
};

show();
</script>
</body>
</html>
