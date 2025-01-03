<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Olympicoin Game</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            color: #333;
            text-align: center;
            margin: 0;
            padding: 0;
        }
        header {
            background: #0077b6;
            color: white;
            padding: 20px 0;
        }
        button {
            background-color: #0077b6;
            color: white;
            border: none;
            padding: 10px 20px;
            margin: 10px;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: #005f8a;
        }
        .social-icons img {
            width: 50px;
            margin: 10px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <header>
        <h1>🏅 Olympicoin Mining Game</h1>
        <p>Mine, Earn, and Connect with the TON Wallet</p>
    </header>

    <main>
        <section>
            <h2>⛏️ Mine Olympicoin</h2>
            <button onclick="mineOlympicoin()">Start Mining</button>
            <p id="miningMessage"></p>
        </section>

        <section>
            <h2>💼 Check Balance</h2>
            <button onclick="checkBalance()">Show Balance</button>
            <p id="balanceMessage"></p>
        </section>

        <section>
            <h2>🔗 Referral Link</h2>
            <button onclick="generateReferral()">Get Referral Link</button>
            <p id="referralMessage"></p>
        </section>

        <section>
            <h2>🔗 Connect TON Wallet</h2>
            <button onclick="connectWallet()">Connect Wallet</button>
            <p id="walletMessage"></p>
        </section>

        <section>
            <h2>📲 Social Media Tasks</h2>
            <div class="social-icons">
                <a href="https://x.com/Aitools25?t=qTP6xfEr4vmt1ssVGkw_vA&s=08" target="_blank">
                    <img src="https://upload.wikimedia.org/wikipedia/en/thumb/6/60/Twitter_Logo_as_of_2021.svg/1200px-Twitter_Logo_as_of_2021.svg.png" alt="Twitter">
                </a>
                <a href="https://youtube.com/@aitoolsupdate2025?si=pbFsTkq_U_Yt_BcQ" target="_blank">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/4/42/YouTube_icon_%282013-2017%29.png" alt="YouTube">
                </a>
                <a href="https://t.me/AItoolsAItools" target="_blank">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/8/82/Telegram_logo.svg" alt="Telegram">
                </a>
            </div>
        </section>
    </main>

    <script>
        const botToken = "7715375393:AAEYdHYHIGo315m2qyZchCEPM8KS2xB4lFw";

        // Mining function
        function mineOlympicoin() {
            fetch(`https://api.telegram.org/bot${botToken}/sendMessage`, {
                method: "POST",
                headers: { "Content-Type": "application/json" },
                body: JSON.stringify({
                    chat_id: "<YOUR_CHAT_ID>", // Replace with user-specific chat ID
                    text: "⛏️ You started mining Olympicoin! Come back in 5 hours.",
                }),
            })
            .then(() => {
                document.getElementById("miningMessage").innerText = "Mining started! Check back later.";
            })
            .catch((error) => {
                console.error(error);
            });
        }

        // Check balance
        function checkBalance() {
            document.getElementById("balanceMessage").innerText = "💼 Your balance is being fetched...";
            // Backend logic for checking balance should be implemented here.
        }

        // Generate referral link
        function generateReferral() {
            const referralLink = `https://t.me/OlympicoinBot?start=ref12345`; // Replace 'ref12345' with user-specific data
            document.getElementById("referralMessage").innerText = `🔗 Your referral link: ${referralLink}`;
        }

        // Connect TON wallet
        function connectWallet() {
            document.getElementById("walletMessage").innerText = "🔗 Wallet connection is coming soon!";
            // Add backend wallet connection logic here.
        }
    </script>
</body>
</html>
