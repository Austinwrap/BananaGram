<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>BaNaNa GrAm</title>
  <style>
    /* ---------- GLOBAL STYLES ---------- */
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }
    body {
      font-family: 'Comic Sans MS', cursive, sans-serif;
      background: #fff8d7; /* Banana-ish background color */
      overflow-x: hidden;
      color: #333;
      cursor: url('https://i.ibb.co/J3s8M16/banana-cursor.png'), auto;
      position: relative;
    }

    /* ---------- FLOATING BANANA ANIMATION ---------- */
    @keyframes floatBanana {
      0% {
        transform: translateY(100vh) rotate(0deg);
        opacity: 0;
      }
      10% { opacity: 1; }
      100% {
        transform: translateY(-120vh) rotate(360deg);
        opacity: 0;
      }
    }
    .banana-icon {
      position: fixed;
      width: 50px;
      height: 50px;
      background: url('https://cdn.pixabay.com/photo/2018/04/24/06/46/banana-3345571_1280.png') no-repeat center/contain;
      animation: floatBanana 10s linear infinite;
      z-index: 1;
    }
    /* Adjust how many bananas, speeds, positions, etc. */
    .banana-icon:nth-child(1)  { left: 5%;  animation-duration: 12s; }
    .banana-icon:nth-child(2)  { left: 15%; animation-duration: 14s; }
    .banana-icon:nth-child(3)  { left: 25%; animation-duration: 11s; }
    .banana-icon:nth-child(4)  { left: 35%; animation-duration: 9s;  }
    .banana-icon:nth-child(5)  { left: 45%; animation-duration: 14s; }
    .banana-icon:nth-child(6)  { left: 55%; animation-duration: 10s; }
    .banana-icon:nth-child(7)  { left: 65%; animation-duration: 13s; }
    .banana-icon:nth-child(8)  { left: 75%; animation-duration: 12s; }
    .banana-icon:nth-child(9)  { left: 85%; animation-duration: 11s; }
    .banana-icon:nth-child(10) { left: 20%; animation-duration: 13s; }

    /* ---------- HEADER ---------- */
    h1 {
      font-size: 3.5em;
      color: #ffcc00;
      text-shadow: 2px 2px 4px #ff9900;
      letter-spacing: 0.02em;
      display: inline-block;
      position: relative;
      margin: 20px auto 10px auto;
      text-align: center;
      animation: pulse 3s infinite;
      cursor: pointer;
      z-index: 5; /* above floating bananas */
    }
    h1:hover {
      animation: peel 1s forwards;
    }
    h1::after {
      content: ' 🍌';
      position: absolute;
      right: -50px;
      top: 0;
      animation: bounce 2s infinite;
    }
    @keyframes bounce {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }
    @keyframes pulse {
      0%, 100% { text-shadow: 2px 2px 4px #ff9900; }
      50% { text-shadow: 2px 2px 12px #ff9900; }
    }
    @keyframes peel {
      0% { transform: rotate(0); }
      100% { transform: rotate(-20deg); }
    }

    p.price-info {
      font-size: 1em;
      color: #444;
      text-align: center;
      margin-bottom: 15px;
      z-index: 5;
      position: relative;
    }

    /* ---------- CONTAINERS ---------- */
    .container {
      margin: 20px auto;
      max-width: 600px;
      background-color: rgba(255, 238, 186, 0.9);
      border-radius: 20px;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
      position: relative;
      z-index: 5;
      animation: fadeInUp 1s ease-out;
      padding: 20px;
    }
    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .container h2 {
      margin-top: 0;
      text-align: center;
      margin-bottom: 10px;
    }

    .mini-container {
      margin: 15px auto;
      max-width: 500px;
      background-color: rgba(255, 238, 186, 0.9);
      border-radius: 15px;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
      animation: fadeInUp 1s ease-out;
      padding: 15px 20px;
      position: relative;
      z-index: 5;
    }
    .mini-container h3 {
      margin-top: 0;
      text-align: center;
      margin-bottom: 10px;
    }

    /* ---------- BUTTONS ---------- */
    .button {
      display: inline-block;
      background: linear-gradient(to bottom, #ff9900, #ff7700);
      color: white;
      padding: 12px 25px;
      margin-top: 15px;
      font-size: 1.2em;
      border: none;
      border-radius: 50px;
      cursor: pointer;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
      transition: transform 0.2s, box-shadow 0.2s;
      text-decoration: none;
    }
    .button:hover {
      transform: scale(1.1);
      box-shadow: 0 6px 10px rgba(0, 0, 0, 0.5);
    }
    #showFactBtn {
      background: linear-gradient(to bottom, #ffee33, #ffcc00);
      color: #333;
      font-size: 0.9em;
      margin-left: 10px;
    }

    /* ---------- FORMS ---------- */
    form label {
      display: block;
      text-align: left;
      margin: 12px 0 5px;
      font-weight: bold;
    }
    select, input, textarea {
      width: 100%;
      padding: 12px;
      margin: 5px 0;
      border: 2px solid #ffcc00;
      border-radius: 15px;
      font-size: 1em;
      background-color: #fff7d7;
      color: #333;
      transition: box-shadow 0.3s, transform 0.3s;
    }
    select:focus, input:focus, textarea:focus {
      box-shadow: 0 0 8px #ffcc00;
      transform: scale(1.02);
    }
    .total-price {
      text-align: center;
      margin-top: 10px;
      font-weight: bold;
      font-size: 1.1em;
    }

    /* ---------- FOOTER ---------- */
    .footer {
      margin-top: 30px;
      font-size: 0.9em;
      color: #888;
      text-align: center;
      padding-bottom: 20px;
      position: relative;
      z-index: 5;
    }
    .footer a {
      color: #ff9900;
      text-decoration: none;
    }
    .footer a:hover {
      text-decoration: underline;
    }

    /* ---------- THANK YOU OVERLAY ---------- */
    #thankYouOverlay {
      display: none;
      position: fixed;
      top:0; left:0;
      width:100%; height:100%;
      background: rgba(0,0,0,0.5);
      z-index:10000;
      justify-content:center;
      align-items:center;
      color: #fff;
      text-align:center;
    }
    #thankYouOverlay .content {
      background: #ffcc00;
      color:#333;
      padding: 40px;
      border-radius: 20px;
      max-width: 400px;
      box-shadow:0 4px 12px rgba(0,0,0,0.3);
      position: relative;
    }

    /* ---------- BANANA FACT POPUP (Optional) ---------- */
    #bananaFactPopup {
      display: none;
      position: fixed;
      top: 50px;
      right: 50px;
      background: #ffee99;
      border: 2px solid #ffcc00;
      border-radius: 15px;
      padding: 20px;
      max-width: 250px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.2);
      z-index: 10000;
      animation: fadeInUp 0.8s;
    }
    #bananaFactPopup h3 {
      margin-top: 0;
    }
  </style>
</head>
<body>
  <!-- Multiple floating bananas -->
  <div class="banana-icon"></div>
  <div class="banana-icon"></div>
  <div class="banana-icon"></div>
  <div class="banana-icon"></div>
  <div class="banana-icon"></div>
  <div class="banana-icon"></div>
  <div class="banana-icon"></div>
  <div class="banana-icon"></div>
  <div class="banana-icon"></div>
  <div class="banana-icon"></div>

  <h1 title="Click me for fun!">BaNaNa GrAm</h1>
  <p class="price-info">Send a Banana Gram right to their door!</p>

  <!-- Banana Gram Details -->
  <div class="container">
    <h2>Craft Your Banana Gram</h2>
    <form id="bananaForm">
      <label for="fruit">Choose your fruit:</label>
      <select id="fruit" name="fruit" required>
        <option value="Banana">Banana</option>
        <option value="Green Apple">Green Apple</option>
        <option value="Cucumber">Cucumber</option>
        <option value="Squash">Squash</option>
        <option value="Eggplant">Eggplant</option>
      </select>

      <label for="quantity">Quantity:</label>
      <input type="number" id="quantity" name="quantity" min="1" value="1" required />

      <label for="message">Write your message (max 140 chars):</label>
      <textarea id="message" name="message" maxlength="140" placeholder="Write your message here..." required></textarea>

      <label for="delivery">Delivery method:</label>
      <select id="delivery" name="delivery" required>
        <option value="Anonymous">Anonymous</option>
        <option value="Include My Name">Include My Name</option>
        <option value="Funny Name">Funny Name</option>
      </select>
      <input type="text" id="funnyName" name="funnyName" placeholder="Enter funny name (if selected)" style="display:none;" />

      <p class="total-price" id="totalPrice">Total Price: $0.00</p>

      <button type="button" class="button" onclick="updateTotalPrice()">Update Price</button>
      <button type="button" class="button" id="showFactBtn" onclick="showBananaFact()">Show Banana Fact</button>
    </form>
  </div>

  <!-- Sender & Recipient Info -->
  <div class="mini-container">
    <h3>Your & Recipient's Info</h3>
    <form id="infoForm">
      <!-- Sender Info -->
      <label for="senderName">Your Name:</label>
      <input type="text" id="senderName" name="senderName" required />

      <label for="senderPhone">Your Phone:</label>
      <input type="text" id="senderPhone" name="senderPhone" required />

      <label for="senderEmail">Your Email:</label>
      <input type="email" id="senderEmail" name="senderEmail" required />

      <label for="venmoHandle">Your Venmo / Payment Handle:</label>
      <input type="text" id="venmoHandle" name="venmoHandle" placeholder="@YourVenmo" required />

      <hr />

      <!-- Recipient Info -->
      <label for="recipientName">Recipient Name:</label>
      <input type="text" id="recipientName" name="recipientName" required />

      <label for="recipientAddress">Recipient Address:</label>
      <textarea id="recipientAddress" name="recipientAddress" placeholder="Street, Apt, City, State..." required></textarea>

      <label for="recipientZip">ZIP Code:</label>
      <input type="text" id="recipientZip" name="recipientZip" required />

      <button type="button" class="button" style="margin-top:20px;" onclick="submitOrder()">Send Email to Austin</button>
    </form>
  </div>

  <div class="container">
    <h2>Contact Us</h2>
    <p><strong>Austin</strong></p>
    <a href="mailto:aytmout@gmail.com" class="button">Email Us</a>
  </div>

  <div class="footer">
    <p>© 2024 Banana Gram. All rights reserved. | <a href="#">Privacy Policy</a></p>
  </div>

  <!-- Banana Fact Popup (optional) -->
  <div id="bananaFactPopup">
    <h3>Banana Fact</h3>
    <p id="bananaFactText"></p>
    <button class="button" onclick="closeBananaFact()">Close</button>
  </div>

  <!-- Thank You Overlay -->
  <div id="thankYouOverlay">
    <div class="content">
      <h2>Thank You!</h2>
      <p>Your Banana Gram is being drafted!</p>
      <button class="button" onclick="closeThankYou()">Close</button>
    </div>
  </div>

  <script>
    /* ------- PRICE CALCULATION ------- */
    const quantityField = document.getElementById("quantity");
    const fruitField = document.getElementById("fruit");
    const deliveryField = document.getElementById("delivery");
    const funnyNameField = document.getElementById("funnyName");
    const totalPriceEl = document.getElementById("totalPrice");

    // Show/hide funnyName field
    deliveryField.addEventListener("change", function () {
      funnyNameField.style.display = (this.value === "Funny Name") ? "block" : "none";
    });

    function updateTotalPrice() {
      const quantity = parseInt(quantityField.value) || 1;
      let total = 0;
      // Pricing logic:
      // 1 fruit => $13
      // 2 fruits => $20
      // 3+ fruits => $20 + $10 for each fruit beyond 2
      if (quantity === 1) {
        total = 13;
      } else if (quantity === 2) {
        total = 20;
      } else if (quantity > 2) {
        total = 20 + (quantity - 2) * 10; // e.g., 3 fruits => $30, 4 => $40, etc.
      }

      totalPriceEl.textContent = "Total Price: $" + total.toFixed(2);
    }

    // Initialize
    updateTotalPrice();
    quantityField.addEventListener("input", updateTotalPrice);
    fruitField.addEventListener("change", updateTotalPrice);

    /* ------- BANANA FACT POPUP ------- */
    const facts = [
      "Bananas are one of the most popular fruits in the world!",
      "Bananas are technically berries!",
      "Over 100 billion bananas are consumed worldwide each year!",
      "Bananas float in water because they are less dense than water!",
      "The scientific name for bananas is 'Musa sapientum', meaning 'fruit of the wise men'!"
    ];
    function showBananaFact() {
      const fact = facts[Math.floor(Math.random() * facts.length)];
      document.getElementById("bananaFactText").textContent = fact;
      document.getElementById("bananaFactPopup").style.display = "block";
    }
    function closeBananaFact() {
      document.getElementById("bananaFactPopup").style.display = "none";
    }

    /* ------- ORDER SUBMISSION (MAILTO) ------- */
    function submitOrder() {
      // Validate required fields
      const requiredIDs = [
        'senderName','senderPhone','senderEmail','venmoHandle',
        'recipientName','recipientAddress','recipientZip',
        'quantity','message'
      ];
      for (let id of requiredIDs) {
        const val = document.getElementById(id).value.trim();
        if (!val) {
          alert("Please fill out all required fields.");
          return;
        }
      }

      // Gather form data
      const senderName       = document.getElementById('senderName').value.trim();
      const senderPhone      = document.getElementById('senderPhone').value.trim();
      const senderEmail      = document.getElementById('senderEmail').value.trim();
      const venmoHandle      = document.getElementById('venmoHandle').value.trim();

      const recipientName    = document.getElementById('recipientName').value.trim();
      const recipientAddress = document.getElementById('recipientAddress').value.trim();
      const recipientZip     = document.getElementById('recipientZip').value.trim();

      const fruit       = document.getElementById('fruit').value;
      const quantity    = document.getElementById('quantity').value;
      const userMessage = document.getElementById('message').value;
      const delivery    = document.getElementById('delivery').value;
      const funnyName   = document.getElementById('funnyName').value;
      const totalPrice  = document.getElementById('totalPrice').textContent;

      // Build the email body
      let emailBody = `Hello Austin,\n\n`;
      emailBody += `I would like to place a Banana Gram order!\n\n`;
      emailBody += `BANANA GRAM ORDER DETAILS:\n`;
      emailBody += `-----------------------------------\n`;
      emailBody += `Fruit: ${fruit}\n`;
      emailBody += `Quantity: ${quantity}\n`;
      emailBody += `Message: ${userMessage}\n`;
      emailBody += `Delivery Method: ${delivery}\n`;
      if (delivery === 'Funny Name') {
        emailBody += `Funny Name: ${funnyName}\n`;
      }
      emailBody += `\n${totalPrice}\n\n`;

      emailBody += `RECIPIENT INFO:\n`;
      emailBody += `Name: ${recipientName}\n`;
      emailBody += `Address: ${recipientAddress}\n`;
      emailBody += `ZIP Code: ${recipientZip}\n`;
      emailBody += `-----------------------------------\n\n`;

      emailBody += `SENDER INFO:\n`;
      emailBody += `Name: ${senderName}\n`;
      emailBody += `Phone: ${senderPhone}\n`;
      emailBody += `Email: ${senderEmail}\n`;
      emailBody += `Venmo: ${venmoHandle}\n\n`;

      emailBody += `Please let me know the final confirmation. Thank you!\n`;

      // Encode the email for mailto
      const subject = encodeURIComponent("New Banana Gram Order");
      const body    = encodeURIComponent(emailBody);
      const mailtoLink = `mailto:aytmout@gmail.com?subject=${subject}&body=${body}`;

      // Show the thank you overlay and open the mail client
      document.getElementById("thankYouOverlay").style.display = "flex";
      window.location.href = mailtoLink;
    }

    function closeThankYou() {
      document.getElementById("thankYouOverlay").style.display = "none";
    }
  </script>
</body>
</html>
