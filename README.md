[Financial Calender.html](https://github.com/user-attachments/files/25509890/Financial.Calender.html)# Financial-Calculator
The official financial calculator for ESM in company finances, particularly dealing with company expenditures and payables
[Upload<!DOCTYPE html>
<html>
<head>
    <title>ESM Financial Dashboard</title>
    <style>
        body {
            margin: 0;
            font-family: 'Segoe UI', sans-serif;
            background-color: #0d1b2a;
            color: white;
        }

        .header {
            background-color: #1b263b;
            padding: 20px;
            text-align: center;
            font-size: 24px;
            font-weight: bold;
            letter-spacing: 1px;
        }

        .container {
            max-width: 1000px;
            margin: 40px auto;
            padding: 30px;
            background-color: #1e2a38;
            border-radius: 12px;
            box-shadow: 0px 0px 25px rgba(0,0,0,0.4);
        }

        .input-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }

        label {
            font-size: 14px;
            color: #cbd5e1;
        }

        input, select {
            width: 100%;
            padding: 10px;
            margin-top: 5px;
            background-color: #324a5f;
            border: none;
            border-radius: 6px;
            color: white;
        }

        input::placeholder {
            color: #9ca3af;
        }

        .button {
            margin-top: 30px;
            padding: 14px;
            background-color: #415a77;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: bold;
            color: white;
            cursor: pointer;
            width: 100%;
        }

        .button:hover {
            background-color: #577590;
        }

        .results {
            margin-top: 40px;
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
        }

        .card {
            background-color: #2c3e50;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
        }

        .card h3 {
            margin: 0;
            font-size: 14px;
            color: #cbd5e1;
        }

        .card p {
            margin-top: 10px;
            font-size: 22px;
            font-weight: bold;
        }

        .footer {
            text-align: center;
            margin-top: 30px;
            color: #9ca3af;
            font-size: 12px;
        }
    </style>
</head>
<body>

<div class="header">
    ECHELON SPORTS MARKETING — Financial Dashboard
</div>

<div class="container">

    <div class="input-grid">
        <div>
            <label>Package Type</label>
            <input type="text" id="packageType" placeholder="Ex: Platinum NIL Package">
        </div>

        <div>
            <label>Base Brand Payment ($)</label>
            <input type="number" id="baseAmount" placeholder="Ex: 7500">
        </div>

        <div>
            <label>ESM Percentage (%)</label>
            <input type="number" id="esmPercent" placeholder="Ex: 20">
        </div>

        <div>
            <label>Player Percentage (%)</label>
            <input type="number" id="playerPercent" placeholder="Ex: 80">
        </div>

        <div>
            <label>Transaction Fee (%)</label>
            <input type="number" id="transactionFee" placeholder="Ex: 2.9">
        </div>
    </div>

    <button class="button" onclick="calculate()">Calculate Breakdown</button>

    <div class="results">
        <div class="card">
            <h3>Total Brand Spend</h3>
            <p id="brandSpend">$0.00</p>
        </div>

        <div class="card">
            <h3>Transaction Fees Lost</h3>
            <p id="feesLost">$0.00</p>
        </div>

        <div class="card">
            <h3>ESM Revenue</h3>
            <p id="esmRevenue">$0.00</p>
        </div>

        <div class="card">
            <h3>Player Earnings</h3>
            <p id="playerRevenue">$0.00</p>
        </div>
    </div>

    <div class="footer">
        Internal Use Only — ESM Financial Intelligence System
    </div>

</div>

<script>
function calculate() {
    const baseAmount = parseFloat(document.getElementById("baseAmount").value) || 0;
    const esmPercent = (parseFloat(document.getElementById("esmPercent").value) || 0) / 100;
    const playerPercent = (parseFloat(document.getElementById("playerPercent").value) || 0) / 100;
    const transactionFeePercent = (parseFloat(document.getElementById("transactionFee").value) || 0) / 100;

    const transactionCost = baseAmount * transactionFeePercent;
    const netAfterFees = baseAmount - transactionCost;

    const esmReceives = netAfterFees * esmPercent;
    const playerReceives = netAfterFees * playerPercent;

    document.getElementById("brandSpend").innerText = "$" + baseAmount.toFixed(2);
    document.getElementById("feesLost").innerText = "$" + transactionCost.toFixed(2);
    document.getElementById("esmRevenue").innerText = "$" + esmReceives.toFixed(2);
    document.getElementById("playerRevenue").innerText = "$" + playerReceives.toFixed(2);
}
</script>

</body>
</html>
ing Financial Calender.html…]()
