<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Customer Feedback Form - Dragon Mart</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet" />
  <style>
    /* Reset */
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell,
        'Open Sans', 'Helvetica Neue', sans-serif;
    }

    body {
      background: linear-gradient(135deg, #f0f4ff, #d9e6ff);
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      padding: 20px;
      color: #1e1e2f;
    }

    .form-container {
      background: #ffffffdd;
      backdrop-filter: saturate(180%) blur(20px);
      border-radius: 24px;
      padding: 48px 36px;
      max-width: 600px;
      width: 100%;
      box-shadow: 0 20px 40px rgb(0 0 0 / 0.1);
      transition: box-shadow 0.3s ease;
    }

    .form-container:hover {
      box-shadow: 0 30px 50px rgb(0 0 0 / 0.15);
    }

    .form-container img {
  display: inline-block;
  margin: 0 0 32px 0;
  width: 140px;
  filter: drop-shadow(0 0 3px rgba(0, 0, 0, 0.1));
}


    h1 {
      text-align: center;
      font-weight: 700;
      font-size: 2.25rem;
      margin-bottom: 32px;
      letter-spacing: 0.02em;
      color: #0f1c68;
    }

    .form-group {
      margin-bottom: 24px;
    }

    label {
      font-weight: 600;
      font-size: 1rem;
      margin-bottom: 8px;
      display: block;
      color: #333658;
      user-select: none;
    }

    input[type="text"],
    input[type="tel"],
    input[type="email"],
    select,
    input[type="datetime-local"],
    textarea {
      width: 100%;
      padding: 14px 18px;
      font-size: 1rem;
      border-radius: 16px;
      border: none;
      background: #f0f4ff;
      box-shadow:
        inset 6px 6px 8px #c9d7ff,
        inset -6px -6px 8px #ffffff;
      color: #222244;
      transition: box-shadow 0.25s ease, background 0.3s ease;
      font-weight: 500;
      resize: vertical;
      min-height: 44px;
      outline-offset: 3px;
    }

    input[type="text"]:focus,
    input[type="tel"]:focus,
    input[type="email"]:focus,
    select:focus,
    input[type="datetime-local"]:focus,
    textarea:focus {
      box-shadow:
        inset 6px 6px 10px #b1c3ff,
        inset -6px -6px 10px #e2ebff,
        0 0 0 3px #4a67ff;
      background: #e2eaff;
      color: #0b1a8f;
      outline: none;
    }

    textarea {
      min-height: 80px;
    }

    /* Row styling for inputs side by side */
    .row {
      display: flex;
      gap: 20px;
      flex-wrap: wrap;
    }

    .row > div {
      flex: 1 1 48%;
      min-width: 180px;
    }

    button[type="submit"] {
      width: 100%;
      background: linear-gradient(90deg, #4a67ff, #5a7dff);
      border: none;
      border-radius: 16px;
      padding: 16px 0;
      font-size: 1.125rem;
      font-weight: 700;
      color: white;
      cursor: pointer;
      box-shadow: 0 8px 16px rgba(74, 103, 255, 0.4);
      transition: background 0.3s ease, box-shadow 0.3s ease, transform 0.15s ease;
      user-select: none;
    }

    button[type="submit"]:hover {
      background: linear-gradient(90deg, #5a7dff, #728eff);
      box-shadow: 0 12px 22px rgba(90, 125, 255, 0.6);
      transform: translateY(-2px);
    }

    button[type="submit"]:disabled {
      background: #aab8ff;
      cursor: not-allowed;
      box-shadow: none;
      transform: none;
    }

    #thank-you-message {
      display: none;
      font-size: 1.25rem;
      font-weight: 600;
      text-align: center;
      padding: 36px 24px;
      color: #2b7a0b;
      background: #e6f4ea;
      border-radius: 20px;
      box-shadow: 0 0 15px rgba(43, 122, 11, 0.3);
      user-select: none;
    }

    /* Responsive tweaks */
    @media (max-width: 640px) {
      .row > div {
        flex: 1 1 100%;
      }
      .form-container {
        padding: 32px 24px;
      }
    }
  </style>
</head>

<body>
  <div class="form-container" role="main" aria-label="Customer Feedback Form">
    <img src="https://github.com/DM-WR-2025/DragonMart-WR-2025/raw/afa44c0b53fea055232ed100a0c1afedae83c149/1990.png"
      alt="DragonMart Logo" />
    <h1>Customer Feedback</h1>

    <form id="feedbackForm" novalidate>
      <div class="form-group">
        <label for="customer-name">Customer Name<span aria-hidden="true" style="color:#f44336;"> *</span></label>
        <input type="text" id="customer-name" name="name" required placeholder="Enter your name" aria-required="true" />
      </div>

      <div class="form-group row">
        <div>
          <label for="mobile-number">Mobile Number<span aria-hidden="true" style="color:#f44336;"> *</span></label>
          <input type="tel" id="mobile-number" name="mobile" required placeholder="Enter your 10-digit mobile number"
            pattern="[0-9]{10}" title="Enter a 10-digit phone number" aria-required="true" />
        </div>
        <div>
          <label for="email">Email <small>(optional)</small></label>
          <input type="email" id="email" name="email" placeholder="Enter your email" aria-required="false" />
        </div>
      </div>

      <div class="form-group">
        <label for="csa-name">CSA Name<span aria-hidden="true" style="color:#f44336;"> *</span></label>
        <select id="csa-name" name="csa" required aria-required="true" aria-describedby="ratingHelp">
          <option value="" disabled selected>Select CSA Name</option>
          <option value="Marie">Marie</option>
          <option value="Varun">Varun</option>
          <option value="Allaine">Allaine</option>
        <option value="Iswary">Iswary</option>
        <option value="Aqil">Aqil</option>
        <option value="Kim">Kim</option>
        <option value="Aahaan">Aahaan</option>
        <option value="Wasan">Wasan</option>
        <option value="Flora">Flora</option>
        <option value="Abdelrahman">Abdelrahman</option>
        <option value="April">April</option>
        <option value="Amine">Amine</option>
        <option value="Saber">Saber</option>
        <option value="Sadaf">Sadaf</option>
        <option value="Alameen">Alameen</option>
        <option value="Anjum">Anjum</option>
        <option value="Nourhan">Nourhan</option>
        <option value="Yasmine">Yasmine</option>
        <option value="Afrith">Afrith</option>
        <option value="Alnoor">Alnoor</option>
 </select>
      </div>

      <div id="rating-section" class="form-group" style="display: none;">
        <label for="rating">Rating <small aria-hidden="true">(1 = Bad, 5 = Excellent)</small></label>
        <select id="rating" name="rating" aria-describedby="ratingHelp" required>
          <option value="" disabled selected>Select Rating</option>
          <option value="1">1 😞</option>
          <option value="2">2 😕</option>
          <option value="3">3 😐</option>
          <option value="4">4 🙂</option>
          <option value="5">5 😄</option>
        </select>
      </div>

      <div class="form-group">
        <label for="desk-type">Desk Type<span aria-hidden="true" style="color:#f44336;"> *</span></label>
        <select id="desk-type" name="desk" required aria-required="true">
          <option value="" disabled selected>Select Desk Type</option>
          <option value="Mall Reception">Mall Reception</option>
          <option value="BA Desk">BA Desk</option>
          <option value="F Desk">F Desk</option>
          <option value="H Desk">H Desk</option>
          <option value="GA Desk">GA Desk</option>
          <option value="GD Desk">GD Desk</option>
        </select>
      </div>

      <div class="form-group">
        <label for="interaction-time">Date and Time of Interaction<span aria-hidden="true" style="color:#f44336;"> *</span></label>
        <input type="datetime-local" id="interaction-time" name="interactionTime" required aria-required="true" />
      </div>

      <div class="form-group">
        <label for="purpose">Purpose of Interaction<span aria-hidden="true" style="color:#f44336;"> *</span></label>
        <select id="purpose" name="purpose" required aria-required="true">
          <option value="" disabled selected>Select Purpose</option>
          <option value="Product Purchase">Product Purchase</option>
          <option value="Complaint Handling">Complaint Handling</option>
          <option value="Customer Support">Customer Support</option>
          <option value="Other">Other</option>
        </select>
      </div>

      <div class="form-group">
        <label for="rating-reason">Reason for this Rating<span aria-hidden="true" style="color:#f44336;"> *</span></label>
        <textarea id="rating-reason" name="ratingReason" rows="3" placeholder="Please tell us why you gave this rating..."
          required aria-required="true"></textarea>
      </div>

      <div class="form-group">
        <label for="improvement-suggestions">Suggestions to improve our staff and mall<span
            aria-hidden="true" style="color:#f44336;"> *</span></label>
        <textarea id="improvement-suggestions" name="improvement" rows="3"
          placeholder="How can we improve our staff and mall?" required aria-required="true"></textarea>
      </div>

      <div class="form-group">
        <button type="submit" aria-label="Submit feedback form">Submit Feedback</button>
      </div>
    </form>

    <div id="thank-you-message" role="alert" aria-live="polite">
      Thanks for visiting Dragon Mart and your feedback! We will escalate it to mall management.
    </div>
  </div>

  <script>
    const form = document.getElementById('feedbackForm');
    const thankYouMessage = document.getElementById('thank-you-message');
    const ratingSection = document.getElementById('rating-section');
    const csaSelect = document.getElementById('csa-name');
    const ratingSelect = document.getElementById('rating');

    const scriptURL = "https://script.google.com/macros/s/AKfycbxXSOlNv-7ZzAo5BigXAphBUrjLNNxuPXVVUp1TXB5BSJxQD4oVtQREwx0TwVFU0S-BXg/exec";

    csaSelect.addEventListener('change', () => {
      if (csaSelect.value) {
        ratingSection.style.display = 'block';
        ratingSelect.setAttribute('required', 'true');
      } else {
        ratingSection.style.display = 'none';
        ratingSelect.removeAttribute('required');
        ratingSelect.value = "";
      }
    });

 form.addEventListener('submit', e => {
  e.preventDefault();

  if (!form.checkValidity()) {
    form.reportValidity();
    return;
  }

  const formData = new URLSearchParams(new FormData(form)); // 👈 FIXED HERE

  const submitBtn = form.querySelector('button[type="submit"]');
  submitBtn.disabled = true;
  submitBtn.textContent = "Submitting...";

  fetch(scriptURL, {
    method: 'POST',
    headers: {
      'Content-Type': 'application/x-www-form-urlencoded' // 👈 Added
    },
    body: formData
  })
    .then(response => {
      if (!response.ok) throw new Error('Network response was not ok');
      return response.text();
    })
    .then(responseText => {
      console.log('Success:', responseText);
      form.style.display = 'none';
      thankYouMessage.style.display = 'block';
    })
    .catch(error => {
      console.error('Error!', error.message);
      alert('Oops! Something went wrong. Please try again.');
    })
    .finally(() => {
      submitBtn.disabled = false;
      submitBtn.textContent = "Submit Feedback";
    });
});

  </script>
</body>

</html>
