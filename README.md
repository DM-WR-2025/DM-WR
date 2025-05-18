<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DM Wheelchair Registration Form</title>
    <style>
        /* Same styling as before */

        body {
            font-family: 'Arial', sans-serif;
            background-color: #f4f7fa;
            margin: 0;
            padding: 0;
        }

        .container {
            width: 60%;
            margin: 0 auto;
            background-color: #ffffff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            margin-top: 50px;
        }

        h2 {
            text-align: center;
            color: red;
            font-size: 24px;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7);
        }

        label {
            font-size: 16px;
            margin: 10px 0;
            color: #555;
            display: block;
        }

        input, select, button {
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
            border: 1px solid #ccc;
            font-size: 16px;
        }

        .medium-input {
            width: 50%;
            display: inline-block;
        }

        input[type="radio"] {
            width: auto;
            margin-right: 10px;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .radio-group {
            display: flex;
            align-items: center;
        }

        .radio-group label {
            margin-right: 20px;
        }

        button {
            background-color: #007bff;
            color: white;
            border: none;
            cursor: pointer;
            font-size: 18px;
            transition: background-color 0.3s;
        }

        button:hover {
            background-color: #0056b3;
        }

        .form-group select {
            width: auto;
            display: inline-block;
            width: 50%;
        }

        .form-group input[type="file"] {
            padding: 5px;
        }

        .hidden {
            display: none;
        }

        .form-section {
            margin-bottom: 20px;
        }

        .form-section label {
            font-weight: bold;
        }

        .wheelchair-select {
            display: inline-block;
            width: 100%;
            padding: 10px;
        }

        .wheelchair-select select {
            width: 50%;
        }

        .footer {
            text-align: center;
            font-size: 14px;
            color: #777;
            margin-top: 40px;
        }

        /* Media Queries for Responsiveness */
        @media (max-width: 768px) {
            .container {
                width: 90%;
            }

            h2 {
                font-size: 20px;
            }

            .medium-input {
                width: 100%;
                display: block;
            }

            .form-group select, .form-group input {
                width: 100%;
            }

            button {
                width: 100%;
            }

            .form-group input[type="file"] {
                width: 100%;
            }

            .wheelchair-select select {
                width: 100%;
            }
        }

        @media (max-width: 480px) {
            h2 {
                font-size: 18px;
            }

            label {
                font-size: 14px;
            }

            input, select, button {
                font-size: 14px;
            }

            .medium-input {
                width: 100%;
            }

            .form-group select, .form-group input {
                font-size: 14px;
            }

            .radio-group label {
                font-size: 14px;
            }

            button {
                font-size: 16px;
            }
        }
    </style>
    <script>
        function showWheelchairOptions() {
            var desk = document.getElementById("desk").value;
            var wheelchairSelect = document.getElementById("wheelchair-options");
            wheelchairSelect.innerHTML = ""; // Clear current options

            var wheelchairOptions = {
                "BA": ["1", "2", "3"],
                "F": ["4", "5", "6"],
                "H": ["7", "8", "9"],
                "GA": ["10", "11"],
                "GD": ["12", "13"]
            };

            if (wheelchairOptions[desk]) {
                wheelchairOptions[desk].forEach(function(option) {
                    var optionElement = document.createElement("option");
                    optionElement.value = option;
                    optionElement.textContent = "Wheelchair " + option;
                    wheelchairSelect.appendChild(optionElement);
                });
            }
        }

        function toggleSecurityDepositOptions() {
            var selectedDeposit = document.querySelector('input[name="deposit-type"]:checked').value;
            document.getElementById("id-fields").style.display = "none";
            document.getElementById("cash-fields").style.display = "none";
            document.getElementById("handed-over-fields").style.display = "none";

            if (selectedDeposit === "id-license") {
                document.getElementById("id-fields").style.display = "block";
            } else if (selectedDeposit === "cash") {
                document.getElementById("cash-fields").style.display = "block";
            } else if (selectedDeposit === "security") {
                document.getElementById("handed-over-fields").style.display = "block";
            }
        }

        // Call the functions when the page is loaded to ensure that hidden fields are correctly initialized
        window.onload = function() {
            toggleSecurityDepositOptions();
        };
    </script>
</head>
<body>
    <div class="container">
        <h2>DM Wheelchair Registration Form</h2>
        <form action="https://script.google.com/macros/s/AKfycbzQjq6dI5bcaTYfaFxiyC5YFMMApS6KomOEAWjtQWRl3584QucI1FybQ6camIoGOB3c/exec" method="POST" enctype="multipart/form-data" onsubmit="return confirmSubmission()">
           
            <!-- Customer Name First -->
            <div class="form-group">
                <label for="customer-name">Customer Name:</label>
                <input type="text" id="customer-name" name="customer-name" required class="medium-input">
            </div>

     <title>Searchable Nationality Dropdown</title>
  <link href="https://cdn.jsdelivr.net/npm/select2@4.1.0-rc.0/dist/css/select2.min.css" rel="stylesheet" />
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 20px;
    }
    .form-group {
      margin-bottom: 15px;
    }
  </style>
<body>

    
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0"> <!-- Added for mobile responsiveness -->
  <title>Searchable Nationality Dropdown</title>

  <!-- Select2 CSS -->
  <link href="https://cdn.jsdelivr.net/npm/select2@4.1.0-rc.0/dist/css/select2.min.css" rel="stylesheet" />

  <style>
  body {
    font-family: Arial, sans-serif;
    padding: 20px;
  }
  .form-group {
    margin-bottom: 15px;
  }

  /* Default: Mobile view */
  #nationality {
    width: 100%;
  }

  /* Laptop/Desktop view (768px and above) */
  @media (min-width: 768px) {
    #nationality {
      width: 50%;
    }
  }
</style>

</head>
<body>

  <div class="form-group">
    <label for="nationality">Nationality:</label>
    <select id="nationality" name="nationality" required>
      <option value="" disabled selected>Select Nationality</option>
      <option value="Bahrain">Bahrain</option>
      <option value="Kuwait">Kuwait</option>
      <option value="Oman">Oman</option>
      <option value="Qatar">Qatar</option>
      <option value="Saudi Arabia">Saudi Arabia</option>
      <option value="United Arab Emirates">United Arab Emirates</option>
      <option value="Afghanistan">Afghanistan</option>
      <option value="Albania">Albania</option>
      <option value="Algeria">Algeria</option>
      <option value="Andorra">Andorra</option>
      <option value="Angola">Angola</option>
      <option value="Antigua and Barbuda">Antigua and Barbuda</option>
      <option value="Argentina">Argentina</option>
      <option value="Armenia">Armenia</option>
      <option value="Australia">Australia</option>
      <option value="Austria">Austria</option>
      <option value="Azerbaijan">Azerbaijan</option>
      <option value="Bahamas">Bahamas</option>
      <option value="Bangladesh">Bangladesh</option>
      <option value="Barbados">Barbados</option>
      <option value="Belarus">Belarus</option>
      <option value="Belgium">Belgium</option>
      <option value="Belize">Belize</option>
      <option value="Benin">Benin</option>
      <option value="Bhutan">Bhutan</option>
      <option value="Bolivia">Bolivia</option>
      <option value="Bosnia and Herzegovina">Bosnia and Herzegovina</option>
      <option value="Botswana">Botswana</option>
      <option value="Brazil">Brazil</option>
      <option value="Brunei">Brunei</option>
      <option value="Bulgaria">Bulgaria</option>
      <option value="Burkina Faso">Burkina Faso</option>
      <option value="Burundi">Burundi</option>
      <option value="Cabo Verde">Cabo Verde</option>
      <option value="Cambodia">Cambodia</option>
      <option value="Cameroon">Cameroon</option>
      <option value="Canada">Canada</option>
      <option value="Central African Republic">Central African Republic</option>
      <option value="Chad">Chad</option>
      <option value="Chile">Chile</option>
      <option value="China">China</option>
      <option value="Colombia">Colombia</option>
      <option value="Comoros">Comoros</option>
      <option value="Congo">Congo</option>
      <option value="Congo, Democratic Republic of the">Congo, Democratic Republic of the</option>
      <option value="Costa Rica">Costa Rica</option>
      <option value="Croatia">Croatia</option>
      <option value="Cuba">Cuba</option>
      <option value="Cyprus">Cyprus</option>
      <option value="Czech Republic">Czech Republic</option>
      <option value="Denmark">Denmark</option>
      <option value="Djibouti">Djibouti</option>
      <option value="Dominica">Dominica</option>
      <option value="Dominican Republic">Dominican Republic</option>
      <option value="Ecuador">Ecuador</option>
      <option value="Egypt">Egypt</option>
      <option value="El Salvador">El Salvador</option>
      <option value="Equatorial Guinea">Equatorial Guinea</option>
      <option value="Eritrea">Eritrea</option>
      <option value="Estonia">Estonia</option>
      <option value="Eswatini">Eswatini</option>
      <option value="Ethiopia">Ethiopia</option>
      <option value="Fiji">Fiji</option>
      <option value="Finland">Finland</option>
      <option value="France">France</option>
      <option value="Gabon">Gabon</option>
      <option value="Gambia">Gambia</option>
      <option value="Georgia">Georgia</option>
      <option value="Germany">Germany</option>
      <option value="Ghana">Ghana</option>
      <option value="Greece">Greece</option>
      <option value="Grenada">Grenada</option>
      <option value="Guatemala">Guatemala</option>
      <option value="Guinea">Guinea</option>
      <option value="Guinea-Bissau">Guinea-Bissau</option>
      <option value="Guyana">Guyana</option>
      <option value="Haiti">Haiti</option>
      <option value="Honduras">Honduras</option>
      <option value="Hungary">Hungary</option>
      <option value="Iceland">Iceland</option>
      <option value="India">India</option>
      <option value="Indonesia">Indonesia</option>
      <option value="Iran">Iran</option>
      <option value="Iraq">Iraq</option>
      <option value="Ireland">Ireland</option>
      <option value="Israel">Israel</option>
      <option value="Italy">Italy</option>
      <option value="Jamaica">Jamaica</option>
      <option value="Japan">Japan</option>
      <option value="Jordan">Jordan</option>
      <option value="Kazakhstan">Kazakhstan</option>
      <option value="Kenya">Kenya</option>
      <option value="Kiribati">Kiribati</option>
      <option value="Korea, North">Korea, North</option>
      <option value="Korea, South">Korea, South</option>
      <option value="Kyrgyzstan">Kyrgyzstan</option>
      <option value="Laos">Laos</option>
      <option value="Latvia">Latvia</option>
      <option value="Lebanon">Lebanon</option>
      <option value="Lesotho">Lesotho</option>
      <option value="Liberia">Liberia</option>
      <option value="Libya">Libya</option>
      <option value="Liechtenstein">Liechtenstein</option>
      <option value="Lithuania">Lithuania</option>
      <option value="Luxembourg">Luxembourg</option>
      <option value="Madagascar">Madagascar</option>
      <option value="Malawi">Malawi</option>
      <option value="Malaysia">Malaysia</option>
      <option value="Maldives">Maldives</option>
      <option value="Mali">Mali</option>
      <option value="Malta">Malta</option>
      <option value="Marshall Islands">Marshall Islands</option>
      <option value="Mauritania">Mauritania</option>
      <option value="Mauritius">Mauritius</option>
      <option value="Mexico">Mexico</option>
      <option value="Micronesia">Micronesia</option>
      <option value="Moldova">Moldova</option>
      <option value="Monaco">Monaco</option>
      <option value="Mongolia">Mongolia</option>
      <option value="Montenegro">Montenegro</option>
      <option value="Morocco">Morocco</option>
      <option value="Mozambique">Mozambique</option>
      <option value="Myanmar">Myanmar</option>
      <option value="Namibia">Namibia</option>
      <option value="Nauru">Nauru</option>
      <option value="Nepal">Nepal</option>
      <option value="Netherlands">Netherlands</option>
      <option value="New Zealand">New Zealand</option>
      <option value="Nicaragua">Nicaragua</option>
      <option value="Niger">Niger</option>
      <option value="Nigeria">Nigeria</option>
      <option value="North Macedonia">North Macedonia</option>
      <option value="Norway">Norway</option>
      <option value="Pakistan">Pakistan</option>
      <option value="Palau">Palau</option>
      <option value="Panama">Panama</option>
      <option value="Papua New Guinea">Papua New Guinea</option>
      <option value="Paraguay">Paraguay</option>
      <option value="Peru">Peru</option>
      <option value="Philippines">Philippines</option>
      <option value="Poland">Poland</option>
      <option value="Portugal">Portugal</option>
      <option value="Romania">Romania</option>
      <option value="Russia">Russia</option>
      <option value="Rwanda">Rwanda</option>
      <option value="Saint Kitts and Nevis">Saint Kitts and Nevis</option>
      <option value="Saint Lucia">Saint Lucia</option>
      <option value="Saint Vincent and the Grenadines">Saint Vincent and the Grenadines</option>
      <option value="Samoa">Samoa</option>
      <option value="San Marino">San Marino</option>
      <option value="Sao Tome and Principe">Sao Tome and Principe</option>
      <option value="Senegal">Senegal</option>
      <option value="Serbia">Serbia</option>
      <option value="Seychelles">Seychelles</option>
      <option value="Sierra Leone">Sierra Leone</option>
      <option value="Singapore">Singapore</option>
      <option value="Slovakia">Slovakia</option>
      <option value="Slovenia">Slovenia</option>
      <option value="Solomon Islands">Solomon Islands</option>
      <option value="Somalia">Somalia</option>
      <option value="South Africa">South Africa</option>
      <option value="South Korea">South Korea</option>
      <option value="South Sudan">South Sudan</option>
      <option value="Spain">Spain</option>
      <option value="Sri Lanka">Sri Lanka</option>
      <option value="Sudan">Sudan</option>
      <option value="Suriname">Suriname</option>
      <option value="Sweden">Sweden</option>
      <option value="Switzerland">Switzerland</option>
      <option value="Syria">Syria</option>
      <option value="Taiwan">Taiwan</option>
      <option value="Tajikistan">Tajikistan</option>
      <option value="Tanzania">Tanzania</option>
      <option value="Thailand">Thailand</option>
      <option value="Togo">Togo</option>
      <option value="Tonga">Tonga</option>
      <option value="Trinidad and Tobago">Trinidad and Tobago</option>
      <option value="Tunisia">Tunisia</option>
      <option value="Turkey">Turkey</option>
      <option value="Turkmenistan">Turkmenistan</option>
      <option value="Tuvalu">Tuvalu</option>
      <option value="Uganda">Uganda</option>
      <option value="Ukraine">Ukraine</option>
      <option value="United Kingdom">United Kingdom</option>
      <option value="United States">United States</option>
      <option value="Uruguay">Uruguay</option>
      <option value="Uzbekistan">Uzbekistan</option>
      <option value="Vanuatu">Vanuatu</option>
      <option value="Vatican City">Vatican City</option>
      <option value="Venezuela">Venezuela</option>
      <option value="Vietnam">Vietnam</option>
      <option value="Yemen">Yemen</option>
      <option value="Zambia">Zambia</option>
      <option value="Zimbabwe">Zimbabwe</option>
    </select>
  </div>

  <!-- jQuery -->
  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
  <!-- Select2 JS -->
  <script src="https://cdn.jsdelivr.net/npm/select2@4.1.0-rc.0/dist/js/select2.min.js"></script>

  <script>
    $(document).ready(function() {
      $('#nationality').select2({
        placeholder: "Select Nationality"
      });
    });
  </script>

</body>


<div class="form-group">
    <label for="customer-type">Customer Type:</label>
    <div class="radio-group">
        <label><input type="radio" name="customer-type" value="Resident" required> Resident</label>
        <label><input type="radio" name="customer-type" value="Visitor" required> Visitor</label>
    </div>
</div>

<!-- Nationality Dropdown with Country Calling Codes -->
<div class="form-group">
    <label for="country_code">Country Calling Code:</label>
    <select id="country_code" name="country_code" required>
        <option value="" disabled selected>Select Country</option>

        <!-- GCC Countries -->
        <option value="+973">Bahrain (+973)</option>
        <option value="+965">Kuwait (+965)</option>
        <option value="+968">Oman (+968)</option>
        <option value="+974">Qatar (+974)</option>
        <option value="+966">Saudi Arabia (+966)</option>
        <option value="+971">United Arab Emirates (+971)</option>

        <!-- Other Countries (A to Z) -->
        <option value="+93">Afghanistan (+93)</option>
        <option value="+355">Albania (+355)</option>
        <option value="+213">Algeria (+213)</option>
        <option value="+376">Andorra (+376)</option>
        <option value="+244">Angola (+244)</option>
        <option value="+1264">Anguilla (+1264)</option>
        <option value="+672">Antarctica (+672)</option>
        <option value="+1268">Antigua and Barbuda (+1268)</option>
        <option value="+54">Argentina (+54)</option>
        <option value="+374">Armenia (+374)</option>
        <option value="+297">Aruba (+297)</option>
        <option value="+61">Australia (+61)</option>
        <option value="+43">Austria (+43)</option>
        <option value="+994">Azerbaijan (+994)</option>
        <option value="+242">Bahamas (+242)</option>
        <option value="+973">Bahrain (+973)</option>
        <option value="+880">Bangladesh (+880)</option>
        <option value="+1246">Barbados (+1246)</option>
        <option value="+375">Belarus (+375)</option>
        <option value="+32">Belgium (+32)</option>
        <option value="+501">Belize (+501)</option>
        <option value="+229">Benin (+229)</option>
        <option value="+975">Bhutan (+975)</option>
        <option value="+591">Bolivia (+591)</option>
        <option value="+387">Bosnia and Herzegovina (+387)</option>
        <option value="+267">Botswana (+267)</option>
        <option value="+55">Brazil (+55)</option>
        <option value="+673">Brunei (+673)</option>
        <option value="+359">Bulgaria (+359)</option>
        <option value="+226">Burkina Faso (+226)</option>
        <option value="+257">Burundi (+257)</option>
        <option value="+855">Cambodia (+855)</option>
        <option value="+237">Cameroon (+237)</option>
        <option value="+1">Canada (+1)</option>
        <option value="+238">Cape Verde (+238)</option>
        <option value="+345">Cayman Islands (+345)</option>
        <option value="+236">Central African Republic (+236)</option>
        <option value="+235">Chad (+235)</option>
        <option value="+56">Chile (+56)</option>
        <option value="+86">China (+86)</option>
        <option value="+57">Colombia (+57)</option>
        <option value="+269">Comoros (+269)</option>
        <option value="+242">Congo (+242)</option>
        <option value="+243">Congo, Democratic Republic of the (+243)</option>
        <option value="+506">Costa Rica (+506)</option>
        <option value="+225">Côte d'Ivoire (+225)</option>
        <option value="+385">Croatia (+385)</option>
        <option value="+53">Cuba (+53)</option>
        <option value="+357">Cyprus (+357)</option>
        <option value="+420">Czech Republic (+420)</option>
        <option value="+45">Denmark (+45)</option>
        <option value="+253">Djibouti (+253)</option>
        <option value="+1">Dominica (+1)</option>
        <option value="+1">Dominican Republic (+1)</option>
        <option value="+593">Ecuador (+593)</option>
        <option value="+20">Egypt (+20)</option>
        <option value="+503">El Salvador (+503)</option>
        <option value="+240">Equatorial Guinea (+240)</option>
        <option value="+291">Eritrea (+291)</option>
        <option value="+372">Estonia (+372)</option>
        <option value="+251">Ethiopia (+251)</option>
        <option value="+679">Fiji (+679)</option>
        <option value="+358">Finland (+358)</option>
        <option value="+33">France (+33)</option>
        <option value="+241">Gabon (+241)</option>
        <option value="+220">Gambia (+220)</option>
        <option value="+995">Georgia (+995)</option>
        <option value="+49">Germany (+49)</option>
        <option value="+233">Ghana (+233)</option>
        <option value="+30">Greece (+30)</option>
        <option value="+1">Grenada (+1)</option>
        <option value="+502">Guatemala (+502)</option>
        <option value="+224">Guinea (+224)</option>
        <option value="+245">Guinea-Bissau (+245)</option>
        <option value="+592">Guyana (+592)</option>
        <option value="+509">Haiti (+509)</option>
        <option value="+504">Honduras (+504)</option>
        <option value="+852">Hong Kong (+852)</option>
        <option value="+36">Hungary (+36)</option>
        <option value="+354">Iceland (+354)</option>
        <option value="+91">India (+91)</option>
        <option value="+62">Indonesia (+62)</option>
        <option value="+98">Iran (+98)</option>
        <option value="+964">Iraq (+964)</option>
        <option value="+353">Ireland (+353)</option>
        <option value="+972">Israel (+972)</option>
        <option value="+39">Italy (+39)</option>
        <option value="+1">Jamaica (+1)</option>
        <option value="+81">Japan (+81)</option>
        <option value="+962">Jordan (+962)</option>
        <option value="+7">Kazakhstan (+7)</option>
        <option value="+254">Kenya (+254)</option>
        <option value="+686">Kiribati (+686)</option>
        <option value="+996">Kyrgyzstan (+996)</option>
        <option value="+856">Laos(+856)</option>
        <option value="+371">Latvia(+371)</option>
    <option value="+961">Lebanon (+961)</option>
    <option value="+266">Lesotho (+266)</option>
    <option value="+231">Liberia (+231)</option>
   <option value="+218">Libya (+218)</option>
<option value="+423">Liechtenstein (+423)</option>
<option value="+370">Lithuania (+370)</option>
<option value="+352">Luxembourg (+352)</option>
<option value="+853">Macao (+853)</option>
<option value="+389">Macedonia (+389)</option>
<option value="+261">Madagascar (+261)</option>
<option value="+265">Malawi (+265)</option>
<option value="+60">Malaysia (+60)</option>
<option value="+960">Maldives (+960)</option>
<option value="+223">Mali (+223)</option>
<option value="+356">Malta (+356)</option>
<option value="+692">Marshall Islands (+692)</option>
<option value="+596">Martinique (+596)</option>
<option value="+222">Mauritania (+222)</option>
<option value="+230">Mauritius (+230)</option>
<option value="+262">Mayotte (+262)</option>
<option value="+52">Mexico (+52)</option>
<option value="+691">Micronesia (+691)</option>
<option value="+373">Moldova (+373)</option>
<option value="+377">Monaco (+377)</option>
<option value="+976">Mongolia (+976)</option>
<option value="+1664">Montserrat (+1664)</option>
<option value="+212">Morocco (+212)</option>
<option value="+258">Mozambique (+258)</option>
<option value="+95">Myanmar (+95)</option>
<option value="+264">Namibia (+264)</option>
<option value="+674">Nauru (+674)</option>
<option value="+977">Nepal (+977)</option>
<option value="+31">Netherlands (+31)</option>
<option value="+599">Netherlands Antilles (+599)</option>
<option value="+687">New Caledonia (+687)</option>
<option value="+64">New Zealand (+64)</option>
<option value="+7370">Turkmenistan (+7370)</option>
<option value="+1649">Turks and Caicos Islands (+1649)</option>
<option value="+688">Tuvalu (+688)</option>
<option value="+256">Uganda (+256)</option>
<option value="+380">Ukraine (+380)</option>
<option value="+971">United Arab Emirates (+971)</option>
<option value="+44">United Kingdom (+44)</option>
<option value="+1">United States (+1)</option>
<option value="+1">United States Minor Outlying Islands (+1)</option>
<option value="+598">Uruguay (+598)</option>
<option value="+998">Uzbekistan (+998)</option>
<option value="+678">Vanuatu (+678)</option>
<option value="+58">Venezuela (+58)</option>
<option value="+84">Vietnam (+84)</option>
<option value="+1284">Virgin Islands, British (+1284)</option>
<option value="+1340">Virgin Islands, U.S. (+1340)</option>
<option value="+681">Wallis and Futuna (+681)</option>
<option value="+212">Western Sahara (+212)</option>
<option value="+967">Yemen (+967)</option>
<option value="+260">Zambia (+260)</option>
<option value="+263">Zimbabwe (+263)</option>

      </select>
</div>

 




      <!-- Phone Number Next -->
            <div class="form-group">
                <label for="phone">Phone Number:</label>
                <input type="tel" id="phone" name="phone" required class="medium-input">
            </div>
            <div class="form-group">
                 <label for="email">Customer Email:</label>
                 <input type="email" id="email" name="email" required class="medium-input">
            </div>

            <!-- Desk Selection -->
            <div class="form-group">
                <label for="desk">Select Desk:</label>
                <select id="desk" name="desk" onchange="showWheelchairOptions()" required>
                    <option value="" disabled selected>Select a desk</option>
                    <option value="BA">BA Desk</option>
                    <option value="F">F Desk</option>
                    <option value="H">H Desk</option>
                    <option value="GA">GA Desk</option>
                    <option value="GD">GD Desk</option>
                </select>
            </div>

            <div class="form-group wheelchair-select">
                <label for="wheelchair-options">Select Wheelchair Number:</label>
                <select id="wheelchair-options" name="wheelchair" required></select>
            </div>

            <!-- Security Deposit Fields -->


<div class="form-section">
  <label>Security Deposit:</label>
  <div class="radio-group">
    <input type="radio" id="id-license" name="deposit-type" value="id-license" onclick="toggleSecurityDepositOptions()" required>
    <label for="id-license">ID and License</label>

    <input type="radio" id="currency" name="deposit-type" value="cash" onclick="toggleSecurityDepositOptions()">
    <label for="currency">Currency</label>

      </div>
</div>

<div id="id-fields" class="form-group hidden">
  <label for="id-number">ID Number:</label>
  <input type="text" id="id-number" name="id-number">
</div>

<div id="cash-fields" class="form-group hidden">
  <label for="cash-amount">Cash Amount:</label>
  <input type="number" id="cash-amount" name="cash-amount">

  <label for="currency-type" class="currency-label">Currency:</label>
  <select id="currency-type" name="currency-type" class="currency-select">
    <option value="usd">USD (Dollar)</option>
    <option value="aed">AED (Dirham)</option>
    <option value="sar">SAR (Riyal)</option>
    <option value="bhd">BHD (Dinar)</option>
    <option value="kwd">KWD (Dinar)</option>
    <option value="omr">OMR (Rial)</option>
    <option value="qat">QAR (Riyal)</option>
    <option value="jod">JOD (Jordanian Dinar)</option>
    <option value="eur">EUR (Euro)</option>
    <option value="other">Other</option>
  </select>
</div>

<div id="handed-over-fields" class="form-group hidden">
  <div class="two-fields">
    <div class="field-container">
      <label for="security-id">Security ID:</label>
      <input type="text" id="security-id" name="security-id">
    </div>
    <div class="field-container">
      <label for="customer-id">Customer ID:</label>
      <input type="text" id="customer-id" name="customer-id">
    </div>
  </div>
</div>


<div class="form-group">
    <label for="last-date">Last Date:</label>
    <input type="date" id="last-date" name="last-date" class="medium-input" required>
</div>

<script>
    function toggleSecurityDepositOptions() {
      const idFields = document.getElementById('id-fields');
      const cashFields = document.getElementById('cash-fields');
      const handedOverFields = document.getElementById('handed-over-fields');

      const idNumber = document.getElementById('id-number');
      const cashAmount = document.getElementById('cash-amount');
      const currencyType = document.getElementById('currency-type');
      const securityId = document.getElementById('security-id');
      const customerId = document.getElementById('customer-id');

      const selectedType = document.querySelector('input[name="deposit-type"]:checked')?.value;

      // Hide and disable all first
      idFields.classList.add('hidden');
      idNumber.disabled = true;

      cashFields.classList.add('hidden');
      cashAmount.disabled = true;
      currencyType.disabled = true;

      handedOverFields.classList.add('hidden');
      securityId.disabled = true;
      customerId.disabled = true;

      // Show and enable based on selection
      if (selectedType === 'id-license') {
        idFields.classList.remove('hidden');
        idNumber.disabled = false;
      } else if (selectedType === 'cash') {
        cashFields.classList.remove('hidden');
        cashAmount.disabled = false;
        currencyType.disabled = false;
      } else if (selectedType === 'security') {
        handedOverFields.classList.remove('hidden');
        securityId.disabled = false;
        customerId.disabled = false;
      }
    }
  </script>



            <button type="submit">Submit</button>
  
</html>
