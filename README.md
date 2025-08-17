<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Help Stray Dogs | Donate Now</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      line-height: 1.6;
      background: #fefefe;
    }
    header {
      background: url('https://images.unsplash.com/photo-1558788353-f76d92427f16') no-repeat center center/cover;
      height: 70vh;
      color: white;
      text-align: center;
      display: flex;
      flex-direction: column;
      justify-content: center;
      padding: 20px;
    }
    header h1 {
      font-size: 3rem;
      margin: 0;
    }
    header p {
      font-size: 1.2rem;
      margin: 10px 0 20px;
    }
    .btn {
      background: #6a0dad;
      color: white;
      padding: 12px 25px;
      text-decoration: none;
      font-size: 1.1rem;
      border-radius: 6px;
      cursor: pointer;
      display: inline-block;
      margin-top: 10px;
    }
    section {
      padding: 40px 20px;
      text-align: center;
    }
    .impact {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 20px;
      margin-top: 20px;
    }
    .card {
      background: #fff;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 4px 6px rgba(0,0,0,0.1);
    }
    .qr-section {
      margin-top: 40px;
    }
    .qr-section img {
      width: 220px;
      border: 5px solid #eee;
      border-radius: 10px;
      margin-top: 15px;
    }
    input[type="number"] {
      padding: 10px;
      font-size: 1rem;
      width: 200px;
      border: 1px solid #ccc;
      border-radius: 6px;
      margin-top: 10px;
    }
    .progress-container {
      margin: 30px auto;
      width: 80%;
      max-width: 600px;
      background: #eee;
      border-radius: 20px;
      overflow: hidden;
      height: 25px;
    }
    .progress-bar {
      height: 100%;
      width: 0%;
      background: #6a0dad;
      text-align: center;
      color: white;
      line-height: 25px;
      transition: width 0.5s ease;
    }
    footer {
      background: #222;
      color: white;
      padding: 20px;
      text-align: center;
    }
    footer a {
      color: #ff6600;
      text-decoration: none;
    }
  </style>
</head>
<body>

  <header>
    <h1>Help Us Save Stray Dogs</h1>
    <p>Your small donation can change a life 🐶</p>

    <!-- Donation Form -->
    <input type="number" id="amount" placeholder="Enter amount (₹)" min="1">
    <br>
    <button class="btn" onclick="donateNow()">Donate with UPI</button>
  </header>

  <section>
    <h2>Our Donation Goal</h2>
    <p>Help us reach our target of <b>₹50,000</b></p>
    <div class="progress-container">
      <div class="progress-bar" id="progressBar">₹0</div>
    </div>

    <h2>Why Your Support Matters</h2>
    <div class="impact">
      <div class="card">
        <h3>🍲 Food</h3>
        <p>Your support helps feed stray dogs daily.</p>
      </div>
      <div class="card">
        <h3>💉 Medical Care</h3>
        <p>Vaccinations and urgent treatments for sick dogs.</p>
      </div>
      <div class="card">
        <h3>🏠 Shelter</h3>
        <p>Safe homes for abandoned dogs.</p>
      </div>
    </div>

    <div class="qr-section">
      <h2>Donate by Scanning QR</h2>
      <p>Scan this QR code with PhonePe, Google Pay, or Paytm.</p>
      <img src="phonepe-qr.png" alt="PhonePe QR Code">
      <p><b>UPI ID:</b> kkindian001@axl</p>
    </div>
  </section>

  <footer>
    <p>Contact us: <a href="mailto:help@dogcare.org">help@dogcare.org</a></p>
    <p>Follow us on <a href="#">Instagram</a> | <a href="#">Facebook</a></p>
  </footer>

  <script>
    let target = 50000;  // Donation Target
    let collected = 0;   // Starting collected amount

    function donateNow() {
      let amount = document.getElementById("amount").value;
      if (amount === "" || amount <= 0) {
        alert("Please enter a valid amount");
        return;
      }

      // Update Progress
      collected += parseInt(amount);
      if (collected > target) collected = target;
      let progressPercent = (collected / target) * 100;
      let progressBar = document.getElementById("progressBar");
      progressBar.style.width = progressPercent + "%";
      progressBar.innerText = "₹" + collected;

      // Open UPI Link
      let upiLink = "upi://pay?pa=kkindian001@axl&pn=DogCare&am=" + amount + "&cu=INR";
      window.location.href = upiLink;
    }
  </script>

</body>
</html>
