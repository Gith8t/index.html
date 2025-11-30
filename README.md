# Restaurant-13-Week-Cash-Flow-Forecast
index.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>13-Week Restaurant Cash Flow Forecast</title>
    <!-- Load Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Use Inter font -->
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap');
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f4f7f9;
        }
        /* Custom scrollbar for the table container */
        .overflow-x-scroll::-webkit-scrollbar {
            height: 8px;
        }
        .overflow-x-scroll::-webkit-scrollbar-thumb {
            background: #9ca3af;
            border-radius: 4px;
        }
        .overflow-x-scroll::-webkit-scrollbar-track {
            background: #e5e7eb;
        }
        .input-cell {
            text-align: right;
            border: none;
            padding: 4px 8px;
            font-weight: 500;
            background-color: #f3f4f6;
            transition: background-color 0.2s;
            width: 100%;
        }
        .input-cell:focus {
            outline: none;
            background-color: #ffffff;
            box-shadow: 0 0 0 2px #3b82f6;
        }
        .total-cell, .balance-cell {
            background-color: #e5e7eb;
            font-weight: 700;
            color: #1f2937;
            text-align: right;
        }
        .balance-cell {
            background-color: #d1fae5; /* Green light */
            color: #065f46; /* Green dark */
        }
        .crunch-warning {
            background-color: #fee2e2; /* Red light */
            color: #991b1b; /* Red dark */
            animation: pulse-red 1s infinite alternate;
        }
        @keyframes pulse-red {
            from { box-shadow: 0 0 0 0 rgba(239, 68, 68, 0.7); }
            to { box-shadow: 0 0 0 6px rgba(239, 68, 68, 0); }
        }
    </style>
</head>
<body class="p-4 md:p-8">

    <div class="max-w-7xl mx-auto">
        <header class="mb-8">
            <h1 class="text-4xl md:text-5xl font-extrabold text-gray-900 mb-2">
                13-Week Cash Flow Forecast
            </h1>
            <p class="text-xl text-gray-600">The essential QBO template & guide for restaurant survival.</p>
        </header>

        <main class="grid grid-cols-1 lg:grid-cols-3 gap-8">
            <!-- 1. Interactive Template (Main Content) -->
            <div class="lg:col-span-2 bg-white p-6 rounded-xl shadow-2xl border border-gray-100">
                <h2 class="text-2xl font-bold mb-4 text-blue-700">Interactive 13-Week Cash Projection</h2>
                <p class="mb-4 text-gray-500 text-sm">Input your estimated figures in the gray cells for Weeks 1-13. The forecast calculates totals and flags potential cash crunches automatically (below \$10,000).</p>

                <!-- Table Container with Horizontal Scroll -->
                <div class="overflow-x-scroll rounded-lg shadow-inner">
                    <table class="min-w-[1400px] w-full border-collapse">
                        <thead>
                            <tr class="bg-gray-800 text-white text-xs uppercase tracking-wider">
                                <th class="sticky left-0 bg-gray-900 p-3 text-left w-48 rounded-tl-lg">Line Item</th>
                                <th class="p-3 text-center w-28">Opening Cash</th>
                                <!-- 13 Week Headers -->
                                <script>
                                    for (let i = 1; i <= 13; i++) {
                                        document.write(`<th class="p-3 text-center w-28">Week ${i}</th>`);
                                    }
                                </script>
                            </tr>
                        </thead>
                        <tbody id="cashFlowBody" class="text-sm">
                            <!-- Rows will be injected by JavaScript -->
                        </tbody>
                    </table>
                </div>
            </div>

            <!-- 2. Guide & Tips Sidebar -->
            <aside class="lg:col-span-1 space-y-6">
                <div class="bg-white p-6 rounded-xl shadow-xl border border-gray-100">
                    <h3 class="text-xl font-bold text-gray-800 mb-3">The Guide: Why This Works</h3>
                    <p class="text-sm text-gray-600 mb-4">Cash flow kills more restaurants than bad food. This template provides a runway view for immediate action.</p>

                    <ul class="space-y-3">
                        <li class="flex items-start">
                            <span class="text-blue-500 font-extrabold mr-2">1.</span>
                            <div>
                                <strong class="text-gray-900">13-Week Projections:</strong> This period balances immediate needs (daily/weekly) with mid-term tactical planning (quarterly purchasing/hiring).
                            </div>
                        </li>
                        <li class="flex items-start">
                            <span class="text-blue-500 font-extrabold mr-2">2.</span>
                            <div>
                                <strong class="text-gray-900">Seasonal Adjustment Factors:</strong> In the template, use the 'Revenue Input' to adjust for holidays, local events, or slow seasons (e.g., reduce revenue input by 20% for Week 6 if a major event ends).
                            </div>
                        </li>
                        <li class="flex items-start">
                            <span class="text-blue-500 font-extrabold mr-2">3.</span>
                            <div>
                                <strong class="text-gray-900">Warning Indicators:</strong> The red cell shading instantly alerts you to an ending cash balance below your $10k safety floor, prompting negotiation or deferred payments.
                            </div>
                        </li>
                        <li class="flex items-start">
                            <span class="text-blue-500 font-extrabold mr-2">4.</span>
                            <div>
                                <strong class="text-gray-900">Actionable Tips:</strong> Scroll down for immediate ways to improve your cash position *before* a crunch hits.
                            </div>
                        </li>
                    </ul>
                </div>

                <div class="bg-white p-6 rounded-xl shadow-xl border border-gray-100">
                    <h3 class="text-xl font-bold text-red-600 mb-3">Tips for Improving Cash Flow</h3>
                    <ol class="list-decimal list-inside text-sm text-gray-700 space-y-2">
                        <li>**Negotiate Payment Terms:** Focus on extending Accounts Payable (inventory, supplier invoices) to 45-60 days and shortening Accounts Receivable (catering, events) to Net-15 or COD.</li>
                        <li>**Daily Cash Position Tracker:** Use your POS data to check daily sales vs. estimated cash expenses. Only deposit cash above a working minimum.</li>
                        <li>**Menu Engineering:** Identify high-margin items and incentivize staff to sell them. Cut low-margin, high-waste items immediately.</li>
                        <li>**Inventory Optimization:** Implement FIFO rigorously. Reduce bulk purchasing if you frequently over-order or experience spoilage.</li>
                        <li>**Quick QBO Check:** Ensure your QBO reconciliation is done daily/weekly. Un-reconciled deposits or delayed bill entry can hide the true cash position.</li>
                    </ol>
                </div>
            </aside>
        </main>
    </div>

    <script>
        // Constants
        const NUM_WEEKS = 13;
        const CASH_CRUNCH_LIMIT = 10000; // The threshold for the warning indicator
        const INPUT_ROWS = [
            // Revenue (Inflow)
            { id: 'sales', label: '1. Food/Drink Sales (Est.)', isInput: true, type: 'inflow', initialValue: 20000 },
            { id: 'catering', label: '2. Catering/Events Receipts', isInput: true, type: 'inflow', initialValue: 2000 },
            { id: 'misc-in', label: '3. Other Cash Inflows', isInput: true, type: 'inflow', initialValue: 500 },
            // Subtotal
            { id: 'total-in', label: 'TOTAL CASH INFLOW', isInput: false, type: 'inflow' },

            // Expenses (Outflow)
            { id: 'food-cost', label: '4. Food/Beverage Payments', isInput: true, type: 'outflow', initialValue: 6000 },
            { id: 'payroll', label: '5. Payroll (incl. taxes)', isInput: true, type: 'outflow', initialValue: 7500 },
            { id: 'rent', label: '6. Rent/Lease Payments', isInput: true, type: 'outflow', initialValue: 1500, recurring: true },
            { id: 'utilities', label: '7. Utilities/Maintenance', isInput: true, type: 'outflow', initialValue: 500 },
            { id: 'debt', label: '8. Loan/Debt Payments', isInput: true, type: 'outflow', initialValue: 750, recurring: true },
            { id: 'misc-out', label: '9. Other Cash Outflows', isInput: true, type: 'outflow', initialValue: 250 },
            // Subtotal
            { id: 'total-out', label: 'TOTAL CASH OUTFLOW', isInput: false, type: 'outflow' },

            // Summary
            { id: 'net-flow', label: 'NET CASH FLOW (In - Out)', isInput: false, type: 'summary' },
            { id: 'opening-cash', label: 'BEGINNING CASH BALANCE', isInput: false, type: 'summary', isOpeningBalance: true },
            { id: 'closing-cash', label: 'ENDING CASH BALANCE', isInput: false, type: 'summary', isClosingBalance: true }
        ];

        let cashData = {}; // Stores all weekly input values

        // Utility to format number as currency
        const formatCurrency = (amount) => {
            return new Intl.NumberFormat('en-US', {
                style: 'currency',
                currency: 'USD',
                minimumFractionDigits: 0
            }).format(amount);
        };

        // --- CORE LOGIC: CALCULATION ---
        const calculateCashFlow = () => {
            let openingCash = parseFloat(document.getElementById('opening-cash-input').value) || 25000; // Get user-set opening cash

            // Loop through each week
            for (let w = 1; w <= NUM_WEEKS; w++) {
                let totalInflow = 0;
                let totalOutflow = 0;

                // 1. Calculate Inflows and Outflows for the current week (w)
                INPUT_ROWS.forEach(row => {
                    if (row.isInput) {
                        const cellId = `${row.id}-${w}`;
                        const inputElement = document.getElementById(cellId);
                        const value = parseFloat(inputElement ? inputElement.value : 0) || 0;

                        if (row.type === 'inflow') {
                            totalInflow += value;
                        } else if (row.type === 'outflow') {
                            totalOutflow += value;
                        }
                        cashData[cellId] = value;
                    }
                });

                // 2. Calculate Summary Rows
                const netFlow = totalInflow - totalOutflow;
                const closingCash = openingCash + netFlow;

                // 3. Update the DOM with calculated values
                document.getElementById(`total-in-${w}`).innerText = formatCurrency(totalInflow);
                document.getElementById(`total-out-${w}`).innerText = formatCurrency(totalOutflow);
                document.getElementById(`net-flow-${w}`).innerText = formatCurrency(netFlow);

                document.getElementById(`opening-cash-${w}`).innerText = formatCurrency(openingCash);

                const closingCell = document.getElementById(`closing-cash-${w}`);
                closingCell.innerText = formatCurrency(closingCash);

                // 4. Apply Cash Crunch Warning Indicator (Red Background)
                closingCell.classList.remove('crunch-warning');
                if (closingCash < CASH_CRUNCH_LIMIT) {
                    closingCell.classList.add('crunch-warning');
                }

                // 5. Set up the Opening Cash for the NEXT week
                if (w < NUM_WEEKS) {
                    openingCash = closingCash;
                }
            }
        };

        // --- DOM MANIPULATION ---
        const initializeTable = () => {
            const tbody = document.getElementById('cashFlowBody');
            tbody.innerHTML = '';

            INPUT_ROWS.forEach(row => {
                const tr = document.createElement('tr');
                tr.className = `border-b hover:bg-gray-50 ${row.type === 'inflow' ? 'bg-green-50' : row.type === 'outflow' ? 'bg-red-50' : 'bg-white'}`;
                if (row.id === 'net-flow') tr.className = 'bg-blue-100 border-t-4 border-blue-400';
                if (row.id === 'closing-cash') tr.className = 'balance-cell border-t-4 border-blue-400';

                // First column (Line Item)
                const th = document.createElement('th');
                th.className = `sticky left-0 p-3 text-left font-semibold ${row.type === 'inflow' ? 'text-green-700 bg-green-100' : row.type === 'outflow' ? 'text-red-700 bg-red-100' : 'text-gray-900 bg-gray-200'}`;
                if (row.id === 'closing-cash') th.className = 'sticky left-0 p-3 text-left font-semibold bg-green-500 text-white';
                th.innerText = row.label;
                tr.appendChild(th);

                // Initial Opening Cash Input (only for the overall starting value)
                if (row.isOpeningBalance) {
                    const td = document.createElement('td');
                    td.className = 'p-2';
                    const input = document.createElement('input');
                    input.type = 'number';
                    input.id = 'opening-cash-input';
                    input.className = 'input-cell text-center font-bold text-gray-800 bg-yellow-100';
                    input.value = 25000;
                    input.addEventListener('input', calculateCashFlow);
                    td.appendChild(input);
                    tr.appendChild(td);
                } else {
                    // Placeholder for other rows in the opening cash column
                    tr.appendChild(document.createElement('td'));
                }

                // Weekly Columns (Week 1 to 13)
                for (let w = 1; w <= NUM_WEEKS; w++) {
                    const td = document.createElement('td');
                    td.className = 'p-2 text-right';

                    if (row.isInput) {
                        // Input cell
                        const input = document.createElement('input');
                        input.type = 'number';
                        input.id = `${row.id}-${w}`;
                        input.className = 'input-cell';

                        // Set default values for demonstration
                        input.value = row.initialValue || (row.recurring ? 1500 : 0);
                        if (row.id === 'rent' && w > 1 && w % 4 !== 1) {
                            // Example: Rent only paid once every 4 weeks
                            input.value = 0;
                        }

                        input.addEventListener('input', calculateCashFlow);
                        td.appendChild(input);

                    } else if (row.isClosingBalance) {
                        // Closing Balance cell (Calculated)
                        td.id = `${row.id}-${w}`;
                        td.className = 'p-2 balance-cell transition-all duration-300';
                    } else if (row.isOpeningBalance) {
                        // Opening Balance cell (Calculated)
                        td.id = `${row.id}-${w}`;
                        td.className = 'p-2 total-cell';
                    } else {
                        // Total In/Out or Net Flow (Calculated)
                        td.id = `${row.id}-${w}`;
                        td.className = 'p-2 total-cell';
                        if (row.id === 'net-flow') td.className = 'p-2 total-cell font-extrabold bg-blue-200 text-blue-800';
                    }
                    tr.appendChild(td);
                }
                tbody.appendChild(tr);
            });

            // Run initial calculation after DOM is ready
            calculateCashFlow();
        };

        // Initialize on page load
        window.onload = initializeTable;

        // Debounce calculation to prevent excessive calls during rapid typing
        let timeout = null;
        document.addEventListener('input', (event) => {
            if (event.target.classList.contains('input-cell')) {
                clearTimeout(timeout);
                timeout = setTimeout(calculateCashFlow, 50);
            }
        });
    </script>
</body>
</html>
