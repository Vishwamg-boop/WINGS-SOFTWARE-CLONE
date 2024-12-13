# WINGS-SOFTWARE-CLONE

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Banking Software</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f9;
        }
        header {
            background-color: #004d99;
            color: #fff;
            padding: 1rem;
            text-align: center;
        }
        nav {
            display: flex;
            justify-content: space-around;
            background-color: #003366;
            padding: 0.5rem;
        }
        nav a {
            color: white;
            text-decoration: none;
            font-weight: bold;
        }
        nav a:hover {
            text-decoration: underline;
        }
        .container {
            max-width: 1200px;
            margin: 2rem auto;
            padding: 1rem;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }
        .hidden {
            display: none;
        }
        label {
            font-weight: bold;
        }
        input, select, button {
            padding: 0.5rem;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        button {
            background-color: #004d99;
            color: white;
            font-size: 1rem;
            cursor: pointer;
        }
        button:hover {
            background-color: #003366;
        }
        footer {
            text-align: center;
            background-color: #004d99;
            color: white;
            padding: 1rem;
            position: fixed;
            bottom: 0;
            width: 100%;
        }
        .back-button {
            display: inline-block;
            margin-top: 1rem;
            padding: 0.5rem 1rem;
            background-color: #ccc;
            color: #000;
            text-align: center;
            border-radius: 4px;
            cursor: pointer;
        }
        .back-button:hover {
            background-color: #bbb;
        }
    </style>
</head>
<body>
    <header>
        <h1>Welcome to Banking Software</h1>
    </header>

    <nav>
        <a href="#dashboard" onclick="showSection('dashboard')">Dashboard</a>
        <a href="#transactions" onclick="showSection('transactions')">Transactions</a>
        <a href="#loans" onclick="showSection('loans')">Loan Queries</a>
        <a href="#support" onclick="showSection('support')">Support</a>
    </nav>

    <div id="dashboard" class="container">
        <h2>Dashboard</h2>
        <p>Welcome to the Banking Software. Use the navigation bar to access features.</p>
    </div>

    <div id="transactions" class="container hidden">
        <h2>Transactions</h2>
        <p>View recent transactions and account summaries here.</p>
    </div>

    <div id="loans" class="container hidden">
        <h2>Loan Queries</h2>
        <form class="form-section" id="loanQueryForm">
            <label for="loanAccount">Loan Account Number:</label>
            <input type="text" id="loanAccount" name="loanAccount" placeholder="Enter the loan account number" required>
            <button type="submit">Search</button>
        </form>

        <div id="loanDetails" class="hidden">
            <h3>Loan Account Details</h3>
            <p id="loanInfo">Fetching loan details...</p>
            <div class="back-button" onclick="returnToLoanForm()">Return</div>
        </div>
    </div>

    <div id="support" class="container hidden">
        <h2>Support</h2>
        <p>Contact support for assistance or issues.</p>
    </div>

    <footer>
        <p>&copy; 2024 Banking Software. All rights reserved.</p>
    </footer>

    <script>
        function showSection(sectionId) {
            document.querySelectorAll('.container').forEach(section => {
                section.classList.add('hidden');
            });
            document.getElementById(sectionId).classList.remove('hidden');
        }

        const loanQueryForm = document.getElementById('loanQueryForm');
        const loanDetails = document.getElementById('loanDetails');

        loanQueryForm.addEventListener('submit', function(event) {
            event.preventDefault();

            const loanAccount = document.getElementById('loanAccount').value;

            if (loanAccount) {
                document.getElementById('loanInfo').textContent = `Details for Loan Account: ${loanAccount}`;
                loanQueryForm.classList.add('hidden');
                loanDetails.classList.remove('hidden');
            } else {
                alert('Please enter a loan account number.');
            }
        });

        function returnToLoanForm() {
            loanDetails.classList.add('hidden');
            loanQueryForm.classList.remove('hidden');
        }
    </script>
</body>
</html>
