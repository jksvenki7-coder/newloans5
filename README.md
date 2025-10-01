# newloans5<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Loans & Insurance</title>
<style>
  body {
    background: #f8fafc;
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    color: #205081;
  }
  .main-title {
    text-align: center;
    font-size: 1.5em;
    font-weight: bold;
    margin: 30px 0 10px 0;
    color: #275db2;
  }
  .display-bar {
    margin: 0 auto 24px auto;
    width: 85%;
    text-align: center;
    border: 2px solid #51baf6;
    border-radius: 7px;
    background: #f6fdfe;
    padding: 17px 0;
    color: #295176;
    font-size: 1.13em;
    font-weight: 500;
  }
  .dashboard-cards {
    display: flex;
    justify-content: center;
    gap: 48px;
    margin: 28px auto;
    flex-wrap: wrap;
    max-width: 900px;
  }
  .card {
    background: #fcfdff;
    border: 2px solid #6eb7e7;
    border-radius: 11px;
    width: 320px;
    padding: 28px 16px 20px 16px;
    box-shadow: 0 2px 14px #daeefd60;
    transition: box-shadow 0.27s;
    cursor: pointer;
    position: relative;
  }
  .card:hover {
    box-shadow: 0 8px 24px #74b4f99a;
  }
  .card-title {
    background: #2890cc;
    color: #fff;
    font-size: 1.15em;
    font-weight: bold;
    padding: 12px 0;
    border-radius: 7px;
    text-align: center;
    margin-bottom: 14px;
  }
  ul {
    margin: 4px 0 0 30px;
    padding: 0;
    color: #273965;
    font-size: 1.09em;
    text-align: left;
  }
  .back-btn {
    background: white;
    color: #0288d1;
    border: 2.5px solid #03a9f4;
    padding: 11px 0;
    font-weight: bold;
    border-radius: 11px;
    text-align: center;
    width: 210px;
    font-size: 1.1em;
    cursor: pointer;
    margin: 25px auto 20px auto;
    display: block;
    transition: background-color 0.3s,color 0.3s;
  }
  .back-btn:hover {
    background: #03a9f4;
    color: white;
  }
  .contact-form {
    max-width: 360px;
    margin: 30px auto 0 auto;
    padding: 16px 18px;
    background: #eef7ff;
    border-radius: 10px;
    border: 1.5px solid #85bbeb;
    font-size: 1.03em;
  }
  .contact-form label {
    font-weight: 600;
    color: #205081;
    display: block;
    margin-bottom: 8px;
    margin-top: 8px;
  }
  .contact-form input, .contact-form textarea {
    width: 100%;
    padding: 9px;
    margin-bottom: 14px;
    border: 2px solid #85bbeb;
    border-radius: 6px;
    font-size: 15px;
    box-sizing: border-box;
  }
  .contact-form input:focus, .contact-form textarea:focus {
    border-color: #3a8ddb;
    outline: none;
  }
  .contact-form button {
    background-color: #275db2;
    color: white;
    border: none;
    padding: 13px 0;
    font-size: 1.07em;
    font-weight: 700;
    border-radius: 7px;
    width: 100%;
    transition: background-color 0.2s;
    cursor: pointer;
    margin-top: 7px;
  }
  .contact-form button:hover {
    background-color: #1371d6;
  }
</style>
<script>
  function showForm(type) {
    document.getElementById('dashboard').style.display = 'none';
    if (type === 'Loans') {
      document.getElementById('loansBox').style.display = 'block';
      document.getElementById('insuranceBox').style.display = 'none';
      document.getElementById('loanFormWrap').style.display = 'block';
      document.getElementById('insuranceFormWrap').style.display = 'none';
    } else {
      document.getElementById('loansBox').style.display = 'none';
      document.getElementById('insuranceBox').style.display = 'block';
      document.getElementById('loanFormWrap').style.display = 'none';
      document.getElementById('insuranceFormWrap').style.display = 'block';
    }
    window.scrollTo(0, 0);
  }

  function showDashboard() {
    document.getElementById('dashboard').style.display = 'flex';
    document.getElementById('loansBox').style.display = 'none';
    document.getElementById('insuranceBox').style.display = 'none';
    document.getElementById('loanFormWrap').style.display = 'none';
    document.getElementById('insuranceFormWrap').style.display = 'none';
  }

  function sendWhatsApp(event, serviceType) {
    event.preventDefault();
    const form = event.target;
    const name = form.name.value.trim();
    const email = form.email.value.trim();
    const phone = form.phone.value.trim();
    const message = form.message.value.trim();
    if (!name || !email || !phone || !message) {
      alert('Please fill all fields.');
      return;
    }
    const whatsapp = "8977143043";
    const text = `Name: ${encodeURIComponent(name)}%0AEmail: ${encodeURIComponent(email)}%0APhone: ${encodeURIComponent(phone)}%0AType: ${serviceType}%0AMessage: ${encodeURIComponent(message)}`;
    window.open(`https://wa.me/${whatsapp}?text=${text}`, '_blank');
    form.reset();
    showDashboard();
  }
</script>
</head>
<body>

<div class="main-title">Loans & Insurance</div>
<div class="display-bar">Add Display</div>

<div id="dashboard" class="dashboard-cards" style="display:flex;">
  <div class="card" id="loansBox" onclick="showForm('Loans')">
    <div class="card-title">Loans</div>
    <ul>
      <li>Loan</li>
      <li>Car</li>
      <li>Bike</li>
      <li>House</li>
      <li>Personal</li>
      <li>Business</li>
      <li>etc</li>
    </ul>
  </div>
  <div class="card" id="insuranceBox" onclick="showForm('Insurance')">
    <div class="card-title">Insurance</div>
    <div style="margin-left:8px; font-size:.99em;">Location based Services</div>
    <ul>
      <li>Health</li>
      <li>Mobile</li>
      <li>Car</li>
      <li>Bike</li>
      <li>etc</li>
    </ul>
  </div>
</div>

<!-- LOANS FORM -->
<div id="loanFormWrap" style="display:none;">
  <form class="contact-form" onsubmit="sendWhatsApp(event, 'Loans')">
    <h3 style="text-align:center;">Loan Enquiry</h3>
    <label for="name-loan">Name:</label>
    <input type="text" id="name-loan" name="name" required />
    <label for="email-loan">Email:</label>
    <input type="email" id="email-loan" name="email" required />
    <label for="phone-loan">Phone:</label>
    <input type="tel" id="phone-loan" name="phone" required />
    <label for="message-loan">Message:</label>
    <textarea id="message-loan" name="message" rows="3" required></textarea>
    <button type="submit">Send via WhatsApp</button>
  </form>
  <button class="back-btn" onclick="showDashboard()">Back to Dashboard</button>
</div>

<!-- INSURANCE FORM -->
<div id="insuranceFormWrap" style="display:none;">
  <form class="contact-form" onsubmit="sendWhatsApp(event, 'Insurance')">
    <h3 style="text-align:center;">Insurance Enquiry</h3>
    <label for="name-ins">Name:</label>
    <input type="text" id="name-ins" name="name" required />
    <label for="email-ins">Email:</label>
    <input type="email" id="email-ins" name="email" required />
    <label for="phone-ins">Phone:</label>
    <input type="tel" id="phone-ins" name="phone" required />
    <label for="message-ins">Message:</label>
    <textarea id="message-ins" name="message" rows="3" required></textarea>
    <button type="submit">Send via WhatsApp</button>
  </form>
  <button class="back-btn" onclick="showDashboard()">Back to Dashboard</button>
</div>

</body>
</html>
