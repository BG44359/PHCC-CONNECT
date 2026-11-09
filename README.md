
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>PHCC CONNECT</title>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: Arial, sans-serif;
}

body {
  background: #f1f5f9;
  color: #183044;
}

header {
  background: #087f69;
  color: white;
  padding: 25px 18px;
}

header h1 {
  font-size: 25px;
}

header p {
  margin-top: 8px;
}

.container {
  padding: 18px;
}

.welcome {
  margin-bottom: 20px;
}

.welcome h2 {
  margin-bottom: 7px;
}

.cards {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
}

.card {
  background: white;
  padding: 20px 12px;
  border-radius: 12px;
  box-shadow: 0 2px 8px #00000012;
  text-align: center;
}

.card .number {
  font-size: 27px;
  font-weight: bold;
  color: #087f69;
  margin-bottom: 8px;
}

.section {
  background: white;
  padding: 18px;
  border-radius: 12px;
  margin-top: 20px;
}

.section h3 {
  margin-bottom: 14px;
}

.menu button {
  width: 100%;
  padding: 15px;
  margin: 5px 0;
  background: #e8f5f1;
  border: none;
  border-radius: 8px;
  color: #075b4b;
  text-align: left;
  font-size: 16px;
}

button {
  cursor: pointer;
}

footer {
  text-align: center;
  padding: 25px;
  color: #64748b;
  font-size: 13px;
}
</style>
</head>

<body>

<header>
  <h1>🏥 PHCC CONNECT</h1>
  <p>Digital Healthcare Management System</p>
</header>

<div class="container">

  <div class="welcome">
    <h2 id="welcome">Welcome to PHCC CONNECT</h2>
    <p>Manage your healthcare facility in one place.</p>
  </div>

  <div class="cards">
    <div class="card">
      <div class="number">0</div>
      <p>Staff Members</p>
    </div>

    <div class="card">
      <div class="number">0</div>
      <p>Patients</p>
    </div>

    <div class="card">
      <div class="number">0</div>
      <p>Daily Reports</p>
    </div>

    <div class="card">
      <div class="number">3</div>
      <p>PHCC Facilities</p>
    </div>
  </div>

  <div class="section">
    <h3>Healthcare Services</h3>

    <div class="menu">
      <button onclick="showMessage('Staff Registration')">👨‍⚕️ Staff Registration</button>
      <button onclick="showMessage('Patient Records')">📋 Patient Records</button>
      <button onclick="showMessage('ANC Services')">🤰 ANC Services</button>
      <button onclick="showMessage('Immunization')">💉 Immunization</button>
      <button onclick="showMessage('Daily Reports')">📊 Daily Reports</button>
      <button onclick="showMessage('Facility Management')">🏥 Facility Management</button>
    </div>
  </div>

  <div class="section">
    <h3>Language / Harshe</h3>
    <button onclick="setLanguage('en')">English</button>
    <button onclick="setLanguage('ha')">Hausa</button>
  </div>

</div>

<footer>
  PHCC CONNECT © 2026<br>
  Connecting Healthcare Workers and Facilities
</footer>

<script>
function showMessage(service) {
  alert(service + " - Coming Soon!");
}

function setLanguage(language) {
  if (language === "ha") {
    document.getElementById("welcome").innerText =
      "Barka da zuwa PHCC CONNECT";
  } else {
    document.getElementById("welcome").innerText =
      "Welcome to PHCC CONNECT";
  }
}
</script>

</body>
</html>
