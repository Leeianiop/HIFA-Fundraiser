<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width,initial-scale=1"/>
  <title>Support Our Cause</title>
  <style>
    body {
      background: #f7f9fc;
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
    }
    .widget {
      background: white;
      padding: 25px;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
      width: 360px;
      text-align: center;
    }
    .logo {
      max-width: 100px;
      margin-bottom: 15px;
    }
    h2 {
      font-size: 22px;
      color: #0000;
      margin: 10px 0;
    }
    p {
      font-size: 14px;
      color: #555;
      margin-bottom: 20px;
    }
    .qr-code {
      width: 180px;
      height: 180px;
      object-fit: contain;
      margin-bottom: 10px;
      border: 1px solid #ccc;
      border-radius: 10px;
    }
    .progress-section {
      margin-bottom: 20px;
    }
    .progress-text {
      font-size: 14px;
      color: #333;
      margin-bottom: 8px;
    }
    .progress-bar-container {
      width: 100%;
      height: 20px;
      background: #eee;
      border-radius: 10px;
      overflow: hidden;
    }
    .progress-bar {
      height: 100%;
      width: 0%;
      background: #007aff;
      transition: width 1s ease;
    }
    .top-donors {
      text-align: left;
      margin-top: 20px;
    }
    .top-donors h3 {
      font-size: 16px;
      color: #007aff;
      margin-bottom: 10px;
    }
    .top-donors ul {
      list-style: none;
      padding: 0;
      margin: 0;
    }
    .top-donors li {
      font-size: 14px;
      margin-bottom: 6px;
    }
  </style>
</head>
<body>
  <div class="widget">
    <img src="file:///C:/Users/Ian/Downloads/WhatsApp_Image_2025-07-26_at_10.25.02_AM-removebg-preview.png" alt="Logo" class="logo">
    <h1> HIFA Official Donation Page</h1>
    <h2>Help Us Reach RM 17.50!</h2>
    <p>Support our cause of Repairing and Purchasing Highlighters by donating through Touch 'n Go. Every cent helps!</p>
    <img src="file:///C:/Users/Ian/Downloads/qr-removebg-preview.png" alt="TNG QR Code" class="qr-code">

    <div class="progress-section">
      <div class="progress-text">Raised: RM <span id="raised">0.00</span> / RM <span id="goal">17.50</span></div>
      <div class="progress-bar-container"><div class="progress-bar" id="bar"></div></div>
    </div>

    <div class="top-donors">
      <h3>Top Donors</h3>
      <ul id="donorList"></ul>
    </div>
  </div>

  <script>
    const goalAmt = 17.50;

    // Simulated donor data
    const donors = [
      { name: '', amount:  },
      { name: '', amount:  },
      { name: '', amount:  },
      { name: '', amount: },
      { name: '', amount:  }
    ];

    // Sort donors by amount descending
    donors.sort((a, b) => b.amount - a.amount);

    // Calculate total raised
    const raisedAmt = donors.reduce((sum, d) => sum + d.amount, 0);

    // Update numbers in UI
    document.getElementById('raised').innerText = raisedAmt.toFixed(2);
    document.getElementById('goal').innerText = goalAmt.toFixed(2);

    const percent = Math.min(100, (raisedAmt / goalAmt) * 100);
    document.getElementById('bar').style.width = percent + '%';

    // Add top donors to list
    const donorList = document.getElementById('donorList');
    donors.forEach(d => {
      const li = document.createElement('li');
      li.textContent = `${d.name} — RM ${d.amount.toFixed(2)}`;
      donorList.appendChild(li);
    });
  </script>
</body>
</html>
