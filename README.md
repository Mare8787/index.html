<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Buffet Restaurant and Date Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #e0f7fa;
            margin: 0;
            padding: 0;
        }

        header {
            background-color: #333;
            color: #fff;
            padding: 10px 0;
            text-align: center;
        }

        header h1 {
            margin: 0;
            font-size: 2.5em;
        }

        .container {
            padding: 20px;
            padding-bottom: 80px;
        }

        .intro {
            text-align: center;
            margin-bottom: 20px;
        }

        .intro p {
            font-size: 1.2em;
        }

        .button {
            margin: 5px;
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
            display: inline-block;
            text-align: center;
            background-color: #333;
            color: #fff;
            border: none;
            border-radius: 5px;
            width: 200px; /* Fixed width for all buttons */
        }

        .button:hover {
            background-color: #555;
        }

        .button .date,
        .button .amount,
        .button .label {
            display: block;
            text-align: center; /* Center text within each block */
        }

        .button .date {
            font-size: 14px;
            color: yellow;
        }

        .button .amount {
            font-size: 18px;
            color: #fff;
        }

        .button .label {
            font-size: 16px;
            margin-top: 5px;
            color: lightblue;
        }

        h2 {
            color: #333;
        }

        #selectedAmounts,
        #totalAmount {
            font-size: 1.2em;
            color: #333;
        }

        .images {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin-top: 20px;
        }

        .images img {
            max-width: 90%;
            margin: 10px 0;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        .header-img {
            display: block;
            margin: 20px auto;
            max-width: 300px;
        }

        .date-buttons-container {
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            margin-top: 20px;
        }

        .date-buttons {
            display: flex;
            flex-direction: column;
            margin-bottom: 10px;
            display: none; /* Initially hidden */
        }

        .opening-hours {
            position: fixed;
            bottom: 10px;
            right: 10px;
            background-color: #ffffff;
            color: #333;
            padding: 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
            font-size: 14px;
            z-index: 1000;
        }

        .opening-hours h2 {
            margin: 0 0 10px 0;
            font-size: 16px;
        }

        .opening-hours p {
            margin: 5px 0;
        }

        .opening-hours p strong {
            display: block;
            margin-bottom: 5px;
        }

        footer {
            background-color: #333;
            color: #fff;
            padding: 20px;
            text-align: center;
            position: relative;
            bottom: 0;
            width: 100%;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
        }

        .contact-info p {
            margin: 5px 0;
        }

        .contact-info a {
            color: #ffeb3b;
            text-decoration: none;
        }

        .footer-links a {
            color: #ffeb3b;
            text-decoration: none;
            margin: 0 10px;
        }

        .footer-links a:hover {
            text-decoration: underline;
        }

        .pax-buttons {
            display: flex;
            flex-direction: column;
            margin-left: 20px;
            margin-top: 20px;
        }

        .pax-button {
            background-color: #00796b; /* Different color for Pax buttons */
            margin-bottom: 10px;
            color: #fff;
        }

        .pax-button:hover {
            background-color: #004d40;
        }
    </style>
</head>

<body>
    <header>
        <h1>Upgrade Calculator</h1>
    </header>

    <img src="https://cdn.skylinewebcams.com/as/img/hosts/754.jpg" alt="Top Left Image" class="header-img">

    <div class="container">
        <div class="intro">
            <h1>Welcome to Our Il-Merill Buffet Restaurant</h1>
            <p>Enjoy a variety of dishes and calculate your dining expenses!</p>
        </div>

        <div class="images">
            <img src="https://www.paradisebayresortmalta.com/storage/app/media/Hotel%20Photos/Il-Merill/merill%201%20.jpg" alt="Buffet Restaurant Image">
        </div>

        <div class="date-buttons-container">
            <button class="button" onclick="showDates('augustDates')">
                <span class="date">BREAKFAST</span>
                <span class="label">Show More</span>
            </button>
            <div id="augustDates" class="date-buttons">
                <button class="button" onclick="toggleAmount(10, '01-08-24')">
                    <span class="date">Adults</span>
                    <span class="amount">10</span>
                    <span class="label">BREAKFAST</span>
                </button>
                <button class="button" onclick="toggleAmount(6, '02-08-24')">
                    <span class="date">Kids 6-11</span>
                    <span class="amount">6</span>
                    <span class="label">BREAKFAST</span>
                </button>
            </div>

            <button class="button" onclick="showDates('septemberDates')">
                <span class="date">DINNER</span>
                <span class="label">Show Dates</span>
            </button>
            <div id="septemberDates" class="date-buttons">
                <button class="button" onclick="toggleAmount(22.5, '01-09-24')">
                    <span class="date">Adults</span>
                    <span class="amount">22.5</span>
                    <span class="label">DINNER</span>
                </button>
                <button class="button" onclick="toggleAmount(13.5, '02-09-24')">
                    <span class="date">Kids 6-11</span>
                    <span class="amount">13.5</span>
                    <span class="label">DINNER</span>
                </button>
               
            </div>

            <button class="button" onclick="showDates('octoberDates')">
                <span class="date">HALF BOARD</span>
                <span class="label">Show Dates</span>
            </button>
            <div id="octoberDates" class="date-buttons">
                <button class="button" onclick="toggleAmount(30, '01-10-24')">
                    <span class="date">Adults</span>
                    <span class="amount">30</span>
                    <span class="label">HALF BOARD</span>
                </button>
                <button class="button" onclick="toggleAmount(17.5, '02-10-24')">
                    <span class="date">Kids 6-11</span>
                    <span class="amount">17.5</span>
                    <span class="label">HALF BOARD</span>
                </button>
            </div>
        </div>

        <div style="display: flex;">
            <!-- Pax Buttons -->
            <div class="pax-buttons">
                <button class="button pax-button" onclick="applyPaxMultiplier(2)">
                    2 Pax
                </button>
                <button class="button pax-button" onclick="applyPaxMultiplier(3)">
                    3 Pax
                </button>
                <button class="button pax-button" onclick="applyPaxMultiplier(4)">
                    4 Pax
                </button>
            </div>
        </div>

        <div>
            <h2>Selected Amounts:</h2>
            <p id="selectedAmounts"></p>
        </div>
        <div>
            <h2>Total Amount:</h2>
            <p id="totalAmount"></p>
        </div>

        <div>
            <button class="button" onclick="applyDiscount()">
                <span class="label">20% Discount</span>
            </button>
        </div>

        <div>
            <button class="button" onclick="clearAll()">
                <span class="label">Delete All</span>
            </button>
        </div>
    </div>

    <div class="opening-hours">
        <h2>Restaurant Opening Hours</h2>
        <p><strong>Breakfast:</strong></p>
        <p>Monday - Sunday: 07:00 am - 10:00 am</p>
        <p><strong>Lunch:</strong></p>
        <p>Monday - Sunday: 12:30 pm - 02:00 pm</p>
        <p><strong>Dinner:</strong></p>
        <p>Monday - Sunday: 06:30 pm - 09:30 pm</p>
    </div>

    <div style="text-align:center; margin-top: 20px; font-size: 12px; color: #333;">
        © 2024 By Marko Stojanovic. mare.stojanovic87@gmail.com
    </div>

    <footer>
        <div class="footer-content">
            <div class="contact-info">
                <p>Paradise Bay Resort</p>
                <p>Marfa Road, MLH 9068 Cirkewwa</p>
                <p>22895000, VAT: MT11612537 LICENSE NO: H/0008</p>
                <p>Email: <a href="mailto:info@paradise-bay.com">info@paradise-bay.com</a></p>
            </div>
            <div class="footer-links">
                <a href="#">Contact Us</a> |
                <a href="#">Privacy Policy</a> |
                <a href="#">Groups</a> |
                <a href="#">Tour Operator</a> |
                <a href="#">Careers</a> |
                <a href="#">Expression of Interest</a>
            </div>
        </div>
    </footer>

    <script>
        let selectedAmounts = [];
        let totalAmount = 0;
        let discountApplied = false;

        function showDates(monthId) {
            const months = ['augustDates', 'septemberDates', 'octoberDates'];
            months.forEach(id => {
                if (id === monthId) {
                    document.getElementById(id).style.display = 'block';
                }
            });
        }

        function toggleAmount(amount, date) {
            const existingItemIndex = selectedAmounts.findIndex(item => item.amount === amount && item.date === date);
            if (existingItemIndex === -1) {
                selectedAmounts.push({ amount: amount, date: date, count: 1 });
            } else {
                selectedAmounts[existingItemIndex].count += 1;
            }
            updateDisplay();
        }

        function updateDisplay() {
            const displayText = selectedAmounts.map(item => `${item.amount} (${item.count})`).join(" + ");
            totalAmount = selectedAmounts.reduce((a, b) => a + (b.amount * b.count), 0);

            document.getElementById('selectedAmounts').innerText = displayText;
            document.getElementById('totalAmount').innerText = discountApplied ? (totalAmount * 0.8).toFixed(2) : totalAmount.toFixed(2);
        }

        function applyPaxMultiplier(multiplier) {
            selectedAmounts = selectedAmounts.map(item => ({
                ...item,
                count: item.count * multiplier
            }));
            updateDisplay();
        }

        function applyDiscount() {
            if (!discountApplied) {
                discountApplied = true;
                updateDisplay();
            }
        }

        function clearAll() {
            selectedAmounts = [];
            totalAmount = 0;
            discountApplied = false;
            updateDisplay();
        }
    </script>
</body>

</html>
