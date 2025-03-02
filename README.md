<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>BaNaNa GrAm 🍌</title>
  <style>
    /* ---------- GLOBAL STYLES ---------- */
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }
    body {
      font-family: 'Comic Sans MS', 'Chalkboard SE', cursive, sans-serif;
      background: linear-gradient(135deg, #fff8d7 0%, #ffeb99 100%);
      overflow-x: hidden;
      color: #222;
      cursor: url('https://i.ibb.co/J3s8M16/banana-cursor.png'), auto;
      position: relative;
      -webkit-tap-highlight-color: transparent;
      animation: bgPulse 15s infinite;
    }
    @keyframes bgPulse {
      0%, 100% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
    }

    /* ---------- FLOATING BANANA ANIMATION ---------- */
    @keyframes floatBanana {
      0% {
        transform: translateY(100vh) rotate(0deg) scale(0.8);
        opacity: 0;
      }
      10% { opacity: 0.8; }
      50% { transform: translateY(50vh) rotate(180deg) scale(1.2); }
      100% {
        transform: translateY(-20vh) rotate(360deg) scale(0.8);
        opacity: 0;
      }
    }
    .banana-icon {
      position: fixed;
      width: 60px;
      height: 60px;
      background: url('https://cdn.pixabay.com/photo/2018/04/24/06/46/banana-3345571_1280.png') no-repeat center/contain;
      animation: floatBanana 8s ease-in-out infinite;
      z-index: 1;
      filter: drop-shadow(0 2px 4px rgba(0,0,0,0.2));
    }
    .banana-icon:nth-child(odd) { animation-duration: 10s; }
    .banana-icon:nth-child(even) { animation-duration: 12s; }
    .banana-icon:nth-child(1)  { left: 5%; }
    .banana-icon:nth-child(2)  { left: 15%; }
    .banana-icon:nth-child(3)  { left: 25%; }
    .banana-icon:nth-child(4)  { left: 35%; }
    .banana-icon:nth-child(5)  { left: 45%; }
    .banana-icon:nth-child(6)  { left: 55%; }
    .banana-icon:nth-child(7)  { left: 65%; }
    .banana-icon:nth-child(8)  { left: 75%; }
    .banana-icon:nth-child(9)  { left: 85%; }
    .banana-icon:nth-child(10) { left: 20%; }

    /* ---------- HEADER ---------- */
    h1 {
      font-size: 4em;
      color: #39ff14;
      text-shadow: 0 0 15px #39ff14, 0 0 30px #ff00ff, 0 0 45px #00ffff;
      letter-spacing: 0.05em;
      display: block;
      margin: 30px auto;
      text-align: center;
      animation: neonFlicker 2s infinite;
      cursor: pointer;
      z-index: 10;
      position: relative;
    }
    h1:hover {
      animation: peel 0.5s forwards, neonFlicker 0.1s infinite;
    }
    h1::before {
      content: '🍌';
      position: absolute;
      left: -60px;
      top: -10px;
      font-size: 1.2em;
      animation: spin 2s infinite linear;
    }
    h1::after {
      content: '🍌';
      position: absolute;
      right: -60px;
      top: -10px;
      font-size: 1.2em;
      animation: spin 2s infinite linear reverse;
    }
    @keyframes spin {
      100% { transform: rotate(360deg); }
    }
    @keyframes neonFlicker {
      0%, 100% { text-shadow: 0 0 15px #39ff14, 0 0 30px #ff00ff, 0 0 45px #00ffff; }
      50% { text-shadow: 0 0 20px #39ff14, 0 0 40px #ff00ff, 0 0 60px #00ffff; }
    }
    @keyframes peel {
      0% { transform: rotate(0); }
      50% { transform: rotate(-15deg); }
      100% { transform: rotate(0); }
    }
    p.price-info {
      font-size: 1.2em;
      color: #ffcc00;
      text-align: center;
      margin-bottom: 20px;
      text-shadow: 0 2px 4px rgba(0,0,0,0.2);
      z-index: 5;
    }

    /* ---------- CONTAINERS ---------- */
    .container {
      margin: 25px auto;
      max-width: 650px;
      background: rgba(255, 238, 186, 0.95);
      border-radius: 25px;
      box-shadow: 0 6px 20px rgba(0, 0, 0, 0.3);
      position: relative;
      z-index: 5;
      padding: 25px;
      animation: bounceIn 1s ease-out;
      border: 2px dashed #ffcc00;
    }
    @keyframes bounceIn {
      0% { opacity: 0; transform: scale(0.9); }
      60% { opacity: 1; transform: scale(1.05); }
      100% { transform: scale(1); }
    }
    .container h2 {
      margin: 0 0 15px;
      text-align: center;
      color: #ff00ff;
      text-shadow: 0 2px 6px rgba(255, 0, 255, 0.5);
    }
    .mini-container {
      margin: 20px auto;
      max-width: 550px;
      background: rgba(255, 238, 186, 0.95);
      border-radius: 20px;
      box-shadow: 0 6px 20px rgba(0, 0, 0, 0.3);
      padding: 20px;
      animation: bounceIn 1s ease-out;
      border: 2px dashed #ffcc00;
      z-index: 5;
    }
    .mini-container h3 {
      margin: 0 0 15px;
      text-align: center;
      color: #00ffff;
      text-shadow: 0 2px 6px rgba(0, 255, 255, 0.5);
    }

    /* ---------- BUTTONS (Neon Overdrive) ---------- */
    .button {
      display: inline-block;
      background: linear-gradient(45deg, #ff00ff, #00ffff, #39ff14);
      color: #fff;
      padding: 14px 30px;
      margin: 15px auto;
      font-size: 1.3em;
      border: none;
      border-radius: 50px;
      cursor: pointer;
      box-shadow: 0 0 15px rgba(255, 0, 255, 0.8), 0 0 25px rgba(0, 255, 255, 0.8);
      transition: all 0.3s ease;
      text-decoration: none;
      position: relative;
      overflow: hidden;
    }
    .button::after {
      content: '';
      position: absolute;
      top: 50%;
      left: 50%;
      width: 0;
      height: 0;
      background: rgba(255, 255, 255, 0.3);
      border-radius: 50%;
      transform: translate(-50%, -50%);
      transition: width 0.6s, height 0.6s;
    }
    .button:hover::after {
      width: 300px;
      height: 300px;
    }
    .button:hover {
      transform: scale(1.15) rotate(5deg);
      box-shadow: 0 0 20px rgba(255, 0, 255, 1), 0 0 40px rgba(0, 255, 255, 1);
    }
    #showFactBtn {
      background: linear-gradient(45deg, #ffcc00, #ff00ff);
      font-size: 1em;
      margin-left: 15px;
    }

    /* ---------- FORMS ---------- */
    form label {
      display: block;
      margin: 15px 0 6px;
      font-weight: bold;
      color: #333;
      text-shadow: 0 1px 2px rgba(0,0,0,0.1);
    }
    select, input, textarea {
      width: 100%;
      padding: 14px;
      margin: 6px 0;
      border: 3px solid #ffcc00;
      border-radius: 20px;
      font-size: 1.1em;
      background: linear-gradient(135deg, #fff7d7, #ffee99);
      color: #222;
      transition: all 0.3s ease;
    }
    select:focus, input:focus, textarea:focus {
      box-shadow: 0 0 12px #39ff14, 0 0 20px #ff00ff;
      transform: scale(1.03);
      border-color: #39ff14;
    }
    .total-price {
      text-align: center;
      margin: 15px 0;
      font-weight: bold;
      font-size: 1.3em;
      color: #ff00ff;
      text-shadow: 0 2px 4px rgba(255, 0, 255, 0.5);
    }

    /* ---------- ORDER LIST STYLES ---------- */
    #orderList {
      margin: 15px 0;
      list-style-type: none;
      padding: 0;
    }
    #orderList li {
      background: rgba(255, 255, 255, 0.8);
      margin: 8px 0;
      padding: 10px 15px;
      border-radius: 12px;
      box-shadow: 0 2px 6px rgba(0,0,0,0.1);
      transition: transform 0.2s;
    }
    #orderList li:hover {
      transform: scale(1.05);
    }

    /* ---------- FOOTER ---------- */
    .footer {
      margin-top: 40px;
      font-size: 1em;
      color: #666;
      text-align: center;
      padding: 20px;
      background: rgba(255, 238, 186, 0.8);
      box-shadow: 0 -4px 12px rgba(0,0,0,0.2);
      z-index: 5;
    }
    .footer a {
      color: #39ff14;
      text-decoration: none;
      transition: all 0.3s;
    }
    .footer a:hover {
      color: #ff00ff;
      text-shadow: 0 0 10px #ff00ff;
    }

    /* ---------- BUBBLE OVERLAY ---------- */
    #bubbleOverlay {
      display: none;
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: rgba(0,0,0,0.7);
      z-index: 20000;
      justify-content: center;
      align-items: center;
      backdrop-filter: blur(4px);
    }
    #bubbleOverlay .content {
      background: linear-gradient(135deg, #222, #333);
      color: #39ff14;
      padding: 50px;
      border: 4px solid #39ff14;
      border-radius: 70px;
      max-width: 550px;
      box-shadow: 0 8px 25px rgba(0,0,0,0.5);
      animation: popIn 0.5s ease-out;
      text-shadow: 0 1px 2px rgba(0,0,0,0.3);
    }
    @keyframes popIn {
      0% { transform: scale(0.5); opacity: 0; }
      100% { transform: scale(1); opacity: 1; }
    }

    /* ---------- THANK YOU OVERLAY ---------- */
    #thankYouOverlay {
      display: none;
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: rgba(0,0,0,0.7);
      z-index: 10000;
      justify-content: center;
      align-items: center;
      backdrop-filter: blur(4px);
    }
    #thankYouOverlay .content {
      background: linear-gradient(135deg, #222, #333);
      color: #39ff14;
      padding: 50px;
      border: 4px solid #39ff14;
      border-radius: 30px;
      max-width: 450px;
      box-shadow: 0 8px 25px rgba(0,0,0,0.5);
      animation: popIn 0.5s ease-out;
      text-align: center;
    }
    #thankYouOverlay h2 {
      margin: 0 0 25px;
      font-size: 2.5em;
      text-shadow: 0 0 15px #39ff14;
    }

    /* ---------- BANANA FACT POPUP ---------- */
    #bananaFactPopup {
      display: none;
      position: fixed;
      top: 60px;
      right: 60px;
      background: linear-gradient(135deg, #ffee99, #ffcc00);
      border: 3px solid #ff00ff;
      border-radius: 20px;
      padding: 25px;
      max-width: 300px;
      box-shadow: 0 6px 20px rgba(0,0,0,0.3);
      z-index: 10000;
      animation: slideIn 0.5s ease-out;
    }
    @keyframes slideIn {
      0% { transform: translateX(100%); opacity: 0; }
      100% { transform: translateX(0); opacity: 1; }
    }
    #bananaFactPopup h3 {
      color: #ff00ff;
      text-shadow: 0 2px 4px rgba(255, 0, 255, 0.5);
    }

    /* ---------- MOBILE OPTIMIZATIONS ---------- */
    @media (max-width: 600px) {
      .banana-icon { width: 45px; height: 45px; }
      h1 { font-size: 2.8em; margin: 15px auto; }
      h1::before, h1::after { font-size: 1em; left: -40px; right: -40px; }
      .container, .mini-container { max-width: 90%; padding: 15px; }
      .button { font-size: 1.1em; padding: 12px 25px; }
      select, input, textarea { font-size: 1em; padding: 12px; }
      #bubbleOverlay .content, #thankYouOverlay .content { padding: 30px; max-width: 90%; }
      #bananaFactPopup { top: 20px; right: 20px; max-width: 80%; }
    }
  </style>
</head>
<body>
  <!-- Floating Bananas -->
  <div class="banana-icon"></div><div class="banana-icon"></div><div class="banana-icon"></div><div class="banana-icon"></div>
  <div class="banana-icon"></div><div class="banana-icon"></div><div class="banana-icon"></div><div class="banana-icon"></div>
  <div class="banana-icon"></div><div class="banana-icon"></div>

  <!-- Bubble Overlay -->
  <div id="bubbleOverlay">
    <div class="content">
      <h2 style="margin-bottom: 20px;">WE SHIP REAL FRUIT, BABY!</h2>
      <p>
        Get ready to send a REAL banana (or other wild fruit) straight to someone's doorstep with YOUR custom message scrawled on it! 
        <br><br>
        Go <strong>ANONYMOUS</strong>, sign your name, or get weird with it—your call! 
        <br><br>
        Let’s make some fruity chaos!
      </p>
      <button class="button" onclick="closeBubbleOverlay()">LET’S FUCKIN’ GO!</button>
    </div>
  </div>

  <h1 title="Click me, I dare ya!">BaNaNa GrAm</h1>
  <p class="price-info">Mail a Banana Gram anywhere in the USA!</p>

  <!-- Banana Gram Form -->
  <div class="container">
    <h2>Build Your BananaGram</h2>
    <form id="bananaForm">
      <label for="fruitSelect">Pick Your Weapon:</label>
      <select id="fruitSelect" name="fruitSelect" required>
        <option value="Banana">Banana 🍌</option>
        <option value="Apple">Apple 🍎</option>
        <option value="Potato">Potato 🥔</option>
        <option value="Eggplant">Eggplant 🍆</option>
        <option value="Squash">Squash 🎃</option>
      </select>

      <label for="fruitQuantity">How Many:</label>
      <input type="number" id="fruitQuantity" name="fruitQuantity" min="1" value="1" required />

      <button type="button" class="button" onclick="addFruit()">Add to Arsenal</button>

      <ul id="orderList"></ul>

      <label for="message">Your Epic Message (140 chars max):</label>
      <textarea id="message" name="message" maxlength="140" placeholder="Scrawl something epic..." required></textarea>

      <label for="delivery">Delivery Vibes:</label>
      <select id="delivery" name="delivery" required>
        <option value="Anonymous">Anonymous 🤫</option>
        <option value="Include My Name">Include My Name ✍️</option>
        <option value="Funny Name">Funny Name 😂</option>
      </select>
      <input type="text" id="funnyName" name="funnyName" placeholder="Drop a hilarious name..." style="display:none;" />

      <p class="total-price" id="totalPrice">Total Price: $0.00</p>

      <button type="button" class="button" id="showFactBtn" onclick="showBananaFact()">Drop a Fruit Fact!</button>
    </form>
  </div>

  <!-- Sender & Recipient Info -->
  <div class="mini-container">
    <h3>Your & Their Deets</h3>
    <form id="infoForm">
      <label for="senderName">Your Name:</label>
      <input type="text" id="senderName" name="senderName" required />

      <label for="senderPhone">Your Phone:</label>
      <input type="text" id="senderPhone" name="senderPhone" required />

      <label for="senderEmail">Your Email:</label>
      <input type="email" id="senderEmail" name="senderEmail" required />

      <label for="venmoHandle">Your Venmo/Payment:</label>
      <input type="text" id="venmoHandle" name="venmoHandle" placeholder="@YourVenmo" required />

      <hr style="border: 1px dashed #ffcc00; margin: 20px 0;" />

      <label for="recipientName">Target Name:</label>
      <input type="text" id="recipientName" name="recipientName" required />

      <label for="recipientAddress">Target Address:</label>
      <textarea id="recipientAddress" name="recipientAddress" placeholder="Street, Apt, City, State..." required></textarea>

      <label for="recipientZip">ZIP Code:</label>
      <input type="text" id="recipientZip" name="recipientZip" required />

      <button type="button" class="button" onclick="submitOrder()">Launch Banana Gram!</button>
    </form>
  </div>

  <!-- Contact Section -->
  <div class="container">
    <h2>Hit Us Up</h2>
    <p><strong>Austin, The Banana Boss</strong></p>
    <a href="mailto:aytmout@gmail.com" class="button">Drop an Email</a>
  </div>

  <div class="footer">
    <p>© 2024 Banana Gram | <a href="#">Privacy Policy</a> | Powered by 🍌 Madness</p>
  </div>

  <!-- Banana Fact Popup -->
  <div id="bananaFactPopup">
    <h3>Fruit Fact Blast</h3>
    <p id="bananaFactText"></p>
    <button class="button" onclick="closeBananaFact()">Shut It</button>
  </div>

  <!-- Thank You Overlay -->
  <div id="thankYouOverlay">
    <div class="content">
      <h2>BOOM! SENT!</h2>
      <p>Your Banana Gram is locked and loaded!</p>
      <button class="button" onclick="closeThankYou()">Send Another!</button>
    </div>
  </div>

  <script>
    let orderItems = [];

    window.onload = () => document.getElementById("bubbleOverlay").style.display = "flex";
    function closeBubbleOverlay() { document.getElementById("bubbleOverlay").style.display = "none"; }

    const fruitSelect   = document.getElementById("fruitSelect");
    const fruitQuantity = document.getElementById("fruitQuantity");
    const orderList     = document.getElementById("orderList");
    const totalPriceEl  = document.getElementById("totalPrice");
    const deliveryField = document.getElementById("delivery");
    const funnyNameField= document.getElementById("funnyName");

    deliveryField.addEventListener("change", function () {
      funnyNameField.style.display = this.value === "Funny Name" ? "block" : "none";
    });

    function addFruit() {
      const fruit = fruitSelect.value;
      const qty   = parseInt(fruitQuantity.value) || 1;
      if (qty < 1) { alert("Gimme at least 1, fam!"); return; }
      orderItems.push({ fruit, qty });
      renderOrderList();
      calculatePrice();
    }

    function renderOrderList() {
      orderList.innerHTML = "";
      orderItems.forEach(item => {
        const li = document.createElement("li");
        li.textContent = `${item.fruit} x ${item.qty}`;
        orderList.appendChild(li);
      });
    }

    function calculatePrice() {
      let totalFruits = orderItems.reduce((sum, item) => sum + item.qty, 0);
      let total = totalFruits === 1 ? 13 : totalFruits === 2 ? 20 : totalFruits > 2 ? 20 + (totalFruits - 2) * 10 : 0;
      totalPriceEl.textContent = `Total Price: $${total.toFixed(2)}`;
    }

    const facts = [
      "Bananas are berries, bitches!",
      "Over 100 BILLION bananas get eaten yearly!",
      "Bananas float—drown your sorrows elsewhere!",
      "We’re 60% banana DNA—embrace your inner fruit!",
      "India’s the banana king, bow down!",
      "Banana plants are giant herbs, not trees!",
      "Potassium in bananas = stress bye-bye!",
      "Banana peels whiten teeth—chew on that!",
      "Mosquito bite? Banana peel it, fam!",
      "Bananas started in Southeast Asia, OG fruit!",
      "1,000 banana types, but Cavendish rules!",
      "Freeze ‘em for instant ice cream vibes!",
      "Banana fibers make paper—write that down!",
      "Alexander the Great was banana-curious in 327 B.C.!"
    ];

    function showBananaFact() {
      const fact = facts[Math.floor(Math.random() * facts.length)];
      document.getElementById("bananaFactText").textContent = fact;
      document.getElementById("bananaFactPopup").style.display = "block";
    }
    function closeBananaFact() { document.getElementById("bananaFactPopup").style.display = "none"; }

    function submitOrder() {
      const requiredIDs = ['senderName','senderPhone','senderEmail','venmoHandle','recipientName','recipientAddress','recipientZip','message'];
      for (let id of requiredIDs) {
        if (!document.getElementById(id)?.value.trim()) {
          alert("Fill it all out, ya fruitcake!");
          return;
        }
      }
      if (orderItems.length === 0) { alert("Add some damn fruit first!"); return; }

      const senderName     = document.getElementById('senderName').value.trim();
      const senderPhone    = document.getElementById('senderPhone').value.trim();
      const senderEmail    = document.getElementById('senderEmail').value.trim();
      const venmoHandle    = document.getElementById('venmoHandle').value.trim();
      const recipientName  = document.getElementById('recipientName').value.trim();
      const recipientAddress = document.getElementById('recipientAddress').value.trim();
      const recipientZip   = document.getElementById('recipientZip').value.trim();
      const userMessage    = document.getElementById('message').value.trim();
      const delivery       = document.getElementById('delivery').value;
      const funnyName      = document.getElementById('funnyName').value;
      const totalPrice     = document.getElementById('totalPrice').textContent;

      let fruitSummary = orderItems.map(item => `${item.fruit} x ${item.qty}`).join('\n');
      let emailBody = `Yo Austin,\n\nI’m droppin’ a Banana Gram order!\n\n`;
      emailBody += `ORDER DEETS:\n-------------\n${fruitSummary}\nMessage: ${userMessage}\nDelivery: ${delivery}\n`;
      if (delivery === 'Funny Name') emailBody += `Funny Name: ${funnyName}\n`;
      emailBody += `\n${totalPrice}\n\n`;
      emailBody += `TARGET:\nName: ${recipientName}\nAddress: ${recipientAddress}\nZIP: ${recipientZip}\n-------------\n\n`;
      emailBody += `SENDER:\nName: ${senderName}\nPhone: ${senderPhone}\nEmail: ${senderEmail}\nVenmo: ${venmoHandle}\n\n`;
      emailBody += `Hook me up with the final word, boss!\n`;

      const subject = encodeURIComponent("New Banana Gram Order");
      const body    = encodeURIComponent(emailBody);
      const mailtoLink = `mailto:aytmout@gmail.com?subject=${subject}&body=${body}`;

      document.getElementById("thankYouOverlay").style.display = "flex";
      setTimeout(() => window.location.href = mailtoLink, 500);
    }

    function closeThankYou() {
      document.getElementById("thankYouOverlay").style.display = "none";
      window.location.reload();
    }
  </script>
</body>
</html>
