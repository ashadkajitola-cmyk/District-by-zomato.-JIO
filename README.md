<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cricket Schedule & Betting Platform Pro Max</title>
    <style>
        :root {
            --primary: #1e3c72;
            --secondary: #2a5298;
            --accent: #ff9800;
            --bg: #f0f4f8;
            --white: #ffffff;
            --text: #222222;
            --danger: #e74c3c;
            --success: #2ecc71;
            --border: #dcdcdc;
        }
        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
        body { background-color: var(--bg); color: var(--text); padding-bottom: 60px; font-size: 16px; }
        
        header { background: linear-gradient(135deg, var(--primary), var(--secondary)); color: var(--white); padding: 20px 25px; display: flex; justify-content: space-between; align-items: center; box-shadow: 0 4px 20px rgba(0,0,0,0.2); }
        header h1 { font-size: 1.5rem; font-weight: 800; letter-spacing: 0.5px; }
        .user-info { display: flex; gap: 15px; align-items: center; font-size: 1rem; }
        .wallet-badge { background: var(--accent); color: #000; padding: 8px 16px; border-radius: 30px; font-weight: bold; font-size: 1.05rem; box-shadow: 0 3px 6px rgba(0,0,0,0.15); }
        
        .container { max-width: 950px; margin: 25px auto; padding: 0 15px; display: flex; flex-direction: column; gap: 20px; }
        .card { background: var(--white); border-radius: 14px; padding: 25px; box-shadow: 0 6px 18px rgba(0,0,0,0.06); }
        
        h2 { font-size: 1.5rem; margin-bottom: 12px; color: var(--primary); font-weight: 700; }
        h3 { font-size: 1.25rem; margin-bottom: 10px; color: #333; font-weight: 700; }
        
        .btn { background: var(--secondary); color: var(--white); border: none; padding: 14px 20px; border-radius: 8px; cursor: pointer; font-weight: bold; font-size: 1.05rem; transition: 0.2s; box-shadow: 0 3px 6px rgba(0,0,0,0.1); width: 100%; text-align: center; display: inline-block; }
        .btn:hover { opacity: 0.92; transform: translateY(-2px); }
        .btn-danger { background: var(--danger); }
        .btn-success { background: var(--success); }
        .btn-warning { background: var(--accent); color: #000; }
        .btn-primary { background: var(--secondary); color: var(--white); }
        
        input, select, textarea { width: 100%; padding: 14px 16px; margin: 8px 0 18px 0; border: 2px solid var(--border); border-radius: 8px; font-size: 1.05rem; background: #fff; }
        input:focus, select:focus { border-color: var(--secondary); outline: none; }
        label { font-weight: 700; font-size: 0.95rem; color: #444; display: block; margin-top: 5px; }
        
        .tabs { display: flex; gap: 8px; margin-bottom: 15px; background: #e2e8f0; padding: 6px; border-radius: 10px; flex-wrap: wrap; }
        .tab-btn { flex: 1; min-width: 140px; padding: 12px; background: transparent; border: none; border-radius: 8px; cursor: pointer; font-weight: bold; color: #555; transition: 0.2s; font-size: 0.95rem; text-align: center; }
        .tab-btn.active { background: var(--white); color: var(--primary); box-shadow: 0 3px 8px rgba(0,0,0,0.1); }
        
        .match-card { border: 2px solid var(--border); border-radius: 12px; padding: 20px; margin-bottom: 18px; background: var(--white); box-shadow: 0 3px 8px rgba(0,0,0,0.03); }
        .series-title-bar { background: #e8f4fd; color: #1a5276; padding: 10px 15px; border-radius: 8px; font-weight: bold; font-size: 1.05rem; margin-bottom: 15px; display: flex; justify-content: space-between; align-items: center; }
        .match-row { display: flex; justify-content: space-between; align-items: center; margin: 15px 0; }
        .team-box { font-size: 1.25rem; font-weight: 800; display: flex; align-items: center; gap: 10px; color: var(--primary); }
        .vs-text { font-weight: 800; color: #777; font-size: 1.1rem; text-align: center; display: flex; flex-direction: column; align-items: center; gap: 4px; }
        .match-format-green { background: var(--success); color: #fff; padding: 3px 10px; border-radius: 20px; font-size: 0.8rem; font-weight: bold; letter-spacing: 0.5px; }
        
        .plan-card-item {
            background: #fff;
            border: 2px solid var(--border);
            border-radius: 12px;
            padding: 16px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 12px;
            box-shadow: 0 2px 6px rgba(0,0,0,0.03);
            transition: 0.2s;
            flex-wrap: wrap;
            gap: 15px;
        }
        .plan-card-item:hover { border-color: var(--secondary); }
        .plan-info-group { display: flex; gap: 25px; align-items: center; flex-wrap: wrap; }
        .plan-price-tag { font-size: 1.6rem; font-weight: 900; color: var(--primary); letter-spacing: -0.5px; }
        .plan-meta-col { display: flex; flex-direction: column; }
        .plan-meta-label { font-size: 0.75rem; color: #777; font-weight: bold; letter-spacing: 0.5px; }
        .plan-meta-val { font-size: 1.05rem; color: #333; font-weight: 700; }

        .physical-ticket {
            background: linear-gradient(135deg, #1e3c72 0%, #2a5298 50%, #ff9800 100%);
            color: #fff;
            border-radius: 16px;
            padding: 22px;
            margin-bottom: 24px;
            box-shadow: 0 8px 25px rgba(0,0,0,0.25);
            border: 2px dashed rgba(255,255,255,0.7);
        }
        .ticket-header { display: flex; justify-content: space-between; align-items: center; font-size: 0.95rem; text-transform: uppercase; letter-spacing: 1px; border-bottom: 1px solid rgba(255,255,255,0.4); padding-bottom: 10px; margin-bottom: 14px; font-weight: bold; }
        .ticket-teams-title { font-size: 1.8rem; font-weight: 900; letter-spacing: 1px; text-align: center; margin: 12px 0; text-shadow: 2px 2px 6px rgba(0,0,0,0.3); }
        .ticket-format-badge { background: #fff; color: #1e3c72; padding: 6px 12px; border-radius: 6px; font-size: 0.9rem; font-weight: bold; display: inline-block; }
        .ticket-datetime { text-align: center; font-size: 1.1rem; font-weight: bold; background: rgba(0,0,0,0.25); padding: 8px; border-radius: 8px; margin: 12px 0; color: #ffeb3b; }
        .ticket-venue { text-align: center; font-size: 1rem; opacity: 0.95; margin-bottom: 10px; font-weight: 600; }
        .ticket-gate { text-align: center; font-size: 0.95rem; background: rgba(255,255,255,0.25); padding: 6px; border-radius: 6px; margin-bottom: 12px; font-weight: bold; }
        .ticket-footer { display: flex; justify-content: space-between; align-items: center; background: rgba(255,255,255,0.95); color: #333; padding: 12px 16px; border-radius: 8px; font-size: 0.95rem; font-weight: bold; }

        .hidden { display: none !important; }
        .flex-row { display: flex; gap: 12px; }
        .flex-row > * { flex: 1; }
        
        .modal { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.7); display: flex; justify-content: center; align-items: center; z-index: 1000; overflow-y: auto; padding: 20px; }
        .modal-content { background: var(--white); padding: 30px; border-radius: 16px; width: 100%; max-width: 650px; position: relative; max-height: 90vh; overflow-y: auto; box-shadow: 0 10px 30px rgba(0,0,0,0.3); }
        .close-modal { position: absolute; top: 15px; right: 20px; font-size: 1.8rem; cursor: pointer; color: #666; font-weight: bold; }
    </style>
</head>
<body>

    <header>
        <h1>🏏 Cricket Schedule & Betting Pro</h1>
        <div class="user-info">
            <span id="displayNumber" style="font-weight: 700;">Login करें</span>
            <span class="wallet-badge">Wallet: ₹<span id="displayWallet">0</span></span>
            <button class="btn btn-danger" onclick="logout()" style="padding: 8px 16px; font-size: 0.9rem; width: auto;">Logout</button>
        </div>
    </header>

    <div class="container">
        <!-- 1. Login Section -->
        <div id="loginSection" class="card">
            <h2>🔐 Login / Register</h2>
            <p id="deviceLimitInfo" style="font-size:0.95rem; color:#555; margin-bottom:15px;"></p>
            <label>Mobile Number:</label>
            <input type="text" id="loginMobileInput" placeholder="Enter 10-digit mobile number">
            <button class="btn" onclick="handleLogin()">Login to Dashboard</button>
        </div>

        <!-- Main Dashboard -->
        <div id="mainDashboard" class="hidden">
            
            <div id="activeSubStatusBox" class="card" style="border-left: 6px solid var(--primary); background: #f8fafc;">
                <h3>✨ Active Subscription Status</h3>
                <div id="subStatusContent" style="margin-top: 10px; font-size: 1.05rem; font-weight: 600; color: #1e3c72;">No Plan</div>
            </div>

            <!-- Subscription Hub Card -->
            <div class="card" style="border-left: 6px solid var(--accent); background: #fffbeb;">
                <h3>📦 Subscription Plans Hub</h3>
                <p style="font-size: 0.95rem; color: #555; margin-bottom: 15px;">Apna match schedule create karne ke liye ya discount/cashback paane ke liye niche diye gaye plans mein se koi plan select karke <b>Buy</b> karein:</p>
                <div id="subPlansList" style="margin-bottom: 5px;"></div>
            </div>

            <div class="card" style="border-left: 6px solid var(--success);">
                <h3>💳 Instant Wallet Recharge (Transaction ID / UTR)</h3>
                <p style="font-size: 0.95rem; color: #555; margin-bottom: 12px;">Payment ki Transaction ID / UTR number yahan dalein. <b>(Note: Sim card par active mobile recharge hona zaroori hai, Wi-Fi users allow nahi hain. Har 29 din me sirf 1 baar reward milega).</b></p>
                <label>Full Transaction ID / UTR:</label>
                <input type="text" id="txFullInput" placeholder="Enter transaction reference ID">
                <button class="btn btn-success" onclick="submitInstantRecharge()">Confirm & Get ₹210 Instantly</button>
            </div>

            <div class="card" style="border-left: 6px solid var(--secondary);">
                <h3>📂 Creator & Schedule Panel</h3>
                <p style="font-size: 0.95rem; color: #555; margin-bottom: 12px;">Apna match schedule create karne ke liye panel open karein (Active subscription zaroori hai).</p>
                <button class="btn" onclick="openCreatorDashboard()">Open Creator Panel</button>
            </div>

            <div id="adminMainControlCard" class="card hidden" style="border-left: 6px solid var(--danger); background: #fdfefe;">
                <h3 style="color: var(--danger);">👑 Master Website Admin Control Center</h3>
                <p style="font-size: 0.95rem; color: #555; margin-bottom: 15px;">Yahan se aap saare matches, tickets aur subscription plans ko manage kar sakte hain.</p>
                <div>
                    <button class="btn btn-danger" style="width: 100%;" onclick="openMasterAdminPanel()">⚙️ Manage Matches, Tickets & Plans</button>
                </div>
            </div>

            <div class="card">
                <h3>🔍 6-Digit Code Verification</h3>
                <div class="flex-row">
                    <input type="text" id="verifyCodeInput" maxlength="6" placeholder="Enter 6-digit match code">
                    <button class="btn" onclick="verifyMatchCode()" style="height: 52px; margin-top: 8px;">Check Code</button>
                </div>
                <div id="verifyResult" style="margin-top: 12px;"></div>
            </div>

            <!-- Top Navigation Tabs -->
            <div class="tabs">
                <button class="tab-btn active" onclick="switchTab('international', event)">🌍 International</button>
                <button class="tab-btn" onclick="switchTab('apna', event)">👤 Apna Schedule</button>
                <button class="tab-btn" onclick="switchTab('activeTickets', event)">🎟️ Active Tickets & Store</button>
                <button class="tab-btn" onclick="switchTab('myPurchased', event)">📦 Purchased History</button>
            </div>

            <!-- Tab Content Sections -->
            <div id="internationalTabContent" class="tab-content card">
                <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 15px; flex-wrap: wrap; gap: 10px;">
                    <h2>International Matches</h2>
                    <button id="adminCreateMatchBtn" class="btn btn-success hidden" style="width: auto;" onclick="openInternationalMatchModal()">+ Create International Match</button>
                </div>
                <div id="internationalMatchesList" style="margin-top: 15px;"></div>
            </div>

            <div id="apnaTabContent" class="tab-content card hidden">
                <h2>Apna Schedule (User Created)</h2>
                <div id="apnaMatchesList" style="margin-top: 15px;"></div>
            </div>

            <div id="activeTicketsTabContent" class="tab-content card hidden">
                <h2>Active Ticket District & Store</h2>
                <div id="activeTicketsList" style="margin-top: 15px;"></div>
            </div>

            <div id="myPurchasedTabContent" class="tab-content card hidden">
                <h2>All Purchased Tickets History</h2>
                <div id="myPurchasedList" style="margin-top: 15px;"></div>
            </div>

        </div>
    </div>

    <!-- Modals -->
    <div id="creatorModal" class="modal hidden">
        <div class="modal-content">
            <span class="close-modal" onclick="closeCreatorModal()">&times;</span>
            <div id="subscriptionRequiredView">
                <h3 style="color: var(--danger);">📢 Subscription Required</h3>
                <p style="font-size:0.95rem; color:#555; margin-bottom:15px;">Apna match schedule create karne ke liye pehle subscription plan active karein.</p>
            </div>
            <div id="creatorActionView" class="hidden">
                <h3 style="color: var(--success);">👤 Creator Panel (Schedule Only)</h3>
                <p style="font-size: 1rem; color: #333; margin-bottom: 15px; font-weight: bold;">✔ Aapke paas active subscription hai. Aap match schedule create kar sakte hain:</p>
                <button class="btn" onclick="openMatchModal()">🏏 Create Match Schedule Only</button>
            </div>
        </div>
    </div>

    <div id="matchModal" class="modal hidden">
        <div class="modal-content">
            <span class="close-modal" onclick="closeMatchModal()">&times;</span>
            <h2>🏏 Create Match Schedule</h2>
            
            <label>Series Type:</label>
            <select id="matchSeriesType" onchange="toggleSeriesInput('match')">
                <option value="existing">Existing Series (Auto-select)</option>
                <option value="new">New Series (Enter Name)</option>
            </select>

            <div id="matchExistingSeriesContainer">
                <label>Select Existing Series:</label>
                <select id="matchExistingSeriesSelect"></select>
            </div>

            <div id="matchNewSeriesContainer" class="hidden">
                <label>New Series Name:</label>
                <input type="text" id="matchSeriesName" placeholder="e.g., Local League 2026">
            </div>

            <div class="flex-row">
                <div><label>Team 1 Name:</label><input type="text" id="matchTeam1" placeholder="Team A"></div>
                <div><label>Team 2 Name:</label><input type="text" id="matchTeam2" placeholder="Team B"></div>
            </div>

            <div class="flex-row">
                <div><label>Match Format:</label><input type="text" id="matchFormat" placeholder="4TH T20I"></div>
                <div><label>Date & Time:</label><input type="text" id="matchDateTime" placeholder="WED, 17 DEC, 2026 | 7 PM"></div>
            </div>

            <label>Venue (Stadium Name):</label>
            <input type="text" id="matchVenue" placeholder="EKANA STADIUM, LUCKNOW">

            <label>Gate Open Time:</label>
            <input type="text" id="matchGateTime" placeholder="Gate Opens: 2 Hours Before">

            <label>6-Digit Security Code:</label>
            <input type="text" id="matchCode6" maxlength="6" placeholder="6 digit code">

            <label>Result / Winner Status:</label>
            <select id="matchResultStatus">
                <option value="Upcoming">Upcoming / Live</option>
                <option value="Team 1 Won">Team 1 Won (Double Payout)</option>
                <option value="Team 2 Won">Team 2 Won (Double Payout)</option>
                <option value="Draw / Abandoned">Draw / Refund</option>
            </select>

            <button class="btn btn-success" style="margin-top:10px;" onclick="saveMatchSchedule(false)">Save & Publish Match</button>
        </div>
    </div>

    <div id="internationalMatchModal" class="modal hidden">
        <div class="modal-content">
            <span class="close-modal" onclick="closeInternationalMatchModal()">&times;</span>
            <h2>🌍 Create International Match (Admin Only)</h2>
            
            <label>Series Type:</label>
            <select id="intSeriesType" onchange="toggleSeriesInput('int')">
                <option value="existing">Existing Series (Auto-select)</option>
                <option value="new">New Series (Enter Name)</option>
            </select>

            <div id="intExistingSeriesContainer">
                <label>Select Existing Series:</label>
                <select id="intExistingSeriesSelect"></select>
            </div>

            <div id="intNewSeriesContainer" class="hidden">
                <label>New Series Name:</label>
                <input type="text" id="intSeriesName" placeholder="IND vs SA Series">
            </div>

            <div class="flex-row">
                <div><label>Team 1:</label><input type="text" id="intTeam1" placeholder="IND"></div>
                <div><label>Team 2:</label><input type="text" id="intTeam2" placeholder="SA"></div>
            </div>

            <div class="flex-row">
                <div><label>Match Format:</label><input type="text" id="intFormat" placeholder="4TH T20I"></div>
                <div><label>Date & Time:</label><input type="text" id="intDateTime" placeholder="WED, 17 DEC, 2026 | 7 PM"></div>
            </div>

            <label>Venue:</label>
            <input type="text" id="intVenue" placeholder="Stadium Name">

            <label>Gate Open Time:</label>
            <input type="text" id="intGateTime" placeholder="Gate Opens info">

            <div class="flex-row">
                <div><label>Ticket Price (₹):</label><input type="number" id="intPrice" placeholder="200"></div>
                <div><label>Ticket Limit:</label><input type="number" id="intLimit" placeholder="100"></div>
            </div>

            <label>6-Digit Security Code:</label>
            <input type="text" id="intCode6" maxlength="6" placeholder="6 digit code">

            <label>Result Status:</label>
            <select id="intResultStatus">
                <option value="Upcoming">Upcoming / Live</option>
                <option value="Team 1 Won">Team 1 Won (Double Payout)</option>
                <option value="Team 2 Won">Team 2 Won (Double Payout)</option>
                <option value="Draw / Abandoned">Draw / Refund</option>
            </select>

            <button class="btn btn-success" style="margin-top:10px;" onclick="saveMatchSchedule(true)">Publish International Match</button>
        </div>
    </div>

    <div id="masterAdminModal" class="modal hidden">
        <div class="modal-content" style="max-width: 750px;">
            <span class="close-modal" onclick="closeMasterAdminPanel()">&times;</span>
            <h2>⚙️ Master Admin Panel</h2>
            
            <div class="tabs" style="margin-bottom:15px;">
                <button class="tab-btn active" onclick="switchAdminSubTab('matches', event)">Matches</button>
                <button class="tab-btn" onclick="switchAdminSubTab('tickets', event)">All Tickets</button>
                <button class="tab-btn" onclick="switchAdminSubTab('plans', event)">Subscriptions</button>
            </div>

            <div id="adminTabMatches" class="admin-sub-tab"><div id="adminAllMatchesList"></div></div>
            <div id="adminTabTickets" class="admin-sub-tab hidden"><div id="adminAllTicketsList"></div></div>
            <div id="adminTabPlans" class="admin-sub-tab hidden">
                <div id="adminPlansList" style="margin-bottom: 15px;"></div>
                <hr style="margin: 15px 0;">
                <h3>Add New Subscription Plan</h3>
                <label>Plan ID:</label><input type="text" id="newPlanId" placeholder="e.g., special_pro">
                <label>Plan Name:</label><input type="text" id="newPlanName" placeholder="e.g., Pro Elite Plan">
                <div class="flex-row">
                    <div><label>Price (₹):</label><input type="number" id="newPlanPrice" placeholder="399"></div>
                    <div><label>Duration Days:</label><input type="number" id="newPlanDays" placeholder="28"></div>
                </div>
                <div class="flex-row">
                    <div><label>Free Tickets Count:</label><input type="number" id="newPlanFreeTickets" placeholder="4"></div>
                    <div><label>Ticket Discount (%):</label><input type="number" id="newPlanDiscount" placeholder="35"></div>
                </div>
                <div>
                    <label>Betting Cashback/Commission (%):</label>
                    <input type="number" id="newPlanCashback" placeholder="e.g., 3 (for 3% cash on betting)">
                </div>
                <button class="btn btn-success" onclick="addNewSubscriptionPlan()">Add New Plan</button>
            </div>
        </div>
    </div>

    <div id="editSingleMatchModal" class="modal hidden">
        <div class="modal-content">
            <span class="close-modal" onclick="closeEditSingleMatchModal()">&times;</span>
            <h2>✏️ Edit Match & Winner Status</h2>
            <input type="hidden" id="editMatchId">

            <label>Series Name:</label><input type="text" id="editSeriesName">
            <div class="flex-row">
                <div><label>Team 1:</label><input type="text" id="editTeam1"></div>
                <div><label>Team 2:</label><input type="text" id="editTeam2"></div>
            </div>
            <div class="flex-row">
                <div><label>Format:</label><input type="text" id="editMatchFormat"></div>
                <div><label>Date & Time:</label><input type="text" id="editMatchDateTime"></div>
            </div>
            <label>Venue:</label><input type="text" id="editMatchVenue">
            <label>Gate Time:</label><input type="text" id="editMatchGateTime">
            <div class="flex-row">
                <div><label>Ticket Price (₹):</label><input type="number" id="editMatchPrice"></div>
                <div><label>Ticket Limit:</label><input type="number" id="editMatchLimit"></div>
            </div>
            <label>Result / Winner Status:</label>
            <select id="editResultStatus">
                <option value="Upcoming">Upcoming / Live</option>
                <option value="Team 1 Won">Team 1 Won (Double Payout)</option>
                <option value="Team 2 Won">Team 2 Won (Double Payout)</option>
                <option value="Draw / Abandoned">Draw / Refund</option>
            </select>
            <button class="btn btn-success" style="margin-top:10px;" onclick="saveEditedMatch()">Update Match Settings</button>
        </div>
    </div>

    <script>
        const DEFAULT_ADMIN = "7355055313";
        
        let db = JSON.parse(localStorage.getItem('cricket_pro_db')) || {
            users: {},
            matches: [],
            tickets: [],
            usedTransactions: [],
            userRechargeTimestamps: {}, 
            settings: {
                adminNumber: DEFAULT_ADMIN,
                maxDevices: 15,
                plans: [
                    { id: '28days_plan', name: '28 Days Pro Plan', price: 299, durationDays: 28, freeTickets: 4, discountPercent: 35, cashbackPercent: 3 }
                ]
            },
            deviceSessions: {}
        };

        db.settings.adminNumber = DEFAULT_ADMIN;
        db.settings.maxDevices = 15;
        if (!db.userRechargeTimestamps) db.userRechargeTimestamps = {};

        let currentMobile = localStorage.getItem('cricket_pro_current_mobile') || null;
        let deviceId = localStorage.getItem('cricket_pro_device_id') || 'dev_' + Math.random().toString(36).substring(2,9);
        localStorage.setItem('cricket_pro_device_id', deviceId);

        function saveDB() {
            localStorage.setItem('cricket_pro_db', JSON.stringify(db));
        }

        window.onload = function() {
            if (!db.users[db.settings.adminNumber]) {
                db.users[db.settings.adminNumber] = { wallet: 0, subscription: null, freeTicketsLeft: 0 };
            }
            if (currentMobile && db.users[currentMobile]) {
                showDashboard();
            } else {
                currentMobile = null;
                showLogin();
            }
        };

        function showLogin() {
            document.getElementById('loginSection').classList.remove('hidden');
            document.getElementById('mainDashboard').classList.add('hidden');
            let infoEl = document.getElementById('deviceLimitInfo');
            if(infoEl) infoEl.innerText = `(Max ${db.settings.maxDevices} numbers allowed per device)`;
        }

        function showDashboard() {
            document.getElementById('loginSection').classList.add('hidden');
            document.getElementById('mainDashboard').classList.remove('hidden');
            
            let isAdmin = (currentMobile === db.settings.adminNumber);
            if (isAdmin) {
                document.getElementById('adminCreateMatchBtn').classList.remove('hidden');
                document.getElementById('adminMainControlCard').classList.remove('hidden');
            } else {
                document.getElementById('adminCreateMatchBtn').classList.add('hidden');
                document.getElementById('adminMainControlCard').classList.add('hidden');
            }

            updateHeader();
            renderSubscriptionStatusBox();
            renderSubscriptionPlansHub();
            renderMatches();
            renderActiveTickets();
            renderMyPurchasedTickets();
        }

        function handleLogin() {
            let mobile = document.getElementById('loginMobileInput').value.trim();
            if (!mobile || mobile.length < 10) { alert("Kripya sahi 10-digit mobile number enter karein!"); return; }

            if (!db.deviceSessions[deviceId]) db.deviceSessions[deviceId] = [];
            let activeNumbers = db.deviceSessions[deviceId];
            
            if (!activeNumbers.includes(mobile)) {
                if (activeNumbers.length >= db.settings.maxDevices) {
                    alert(`Is device par maximum ${db.settings.maxDevices} numbers hi allow hain!`);
                    return;
                }
                activeNumbers.push(mobile);
            }

            if (!db.users[mobile]) {
                let initialWallet = (mobile === db.settings.adminNumber) ? 0 : 200;
                db.users[mobile] = { wallet: initialWallet, subscription: null, freeTicketsLeft: 0 };
            }

            currentMobile = mobile;
            localStorage.setItem('cricket_pro_current_mobile', currentMobile);
            saveDB();
            showDashboard();
        }

        function logout() {
            currentMobile = null;
            localStorage.removeItem('cricket_pro_current_mobile');
            showLogin();
        }

        function updateHeader() {
            document.getElementById('displayNumber').innerText = currentMobile;
            let user = db.users[currentMobile];
            document.getElementById('displayWallet').innerText = user ? user.wallet : 0;
        }

        function submitInstantRecharge() {
            let txInput = document.getElementById('txFullInput').value.trim();
            if (!txInput || txInput.length < 6) { alert("Kripya valid Transaction ID / UTR enter karein!"); return; }

            let hasCarrierRecharge = confirm("System verification check: Kya aapke is mobile number (" + currentMobile + ") par sim card mein active mobile recharge (Airtel/Jio/Vi/BSNL etc.) maujood hai? (OK = Haan, Cancel = Nahi / Wi-Fi user)");
            if (!hasCarrierRecharge) {
                alert("Recharge failed! Aapka mobile number active carrier recharge ke bina verified nahi ho saka. Wi-Fi users ke liye yeh allow nahi hai.");
                return;
            }

            if (!db.usedTransactions) db.usedTransactions = [];
            if (db.usedTransactions.includes(txInput)) { alert("Yeh Transaction ID pehle hi use ki ja chuki hai!"); return; }

            let now = new Date().getTime();
            let lastRechargeTime = db.userRechargeTimestamps[currentMobile] || 0;
            let twentyNineDaysInMs = 29 * 24 * 60 * 60 * 1000;

            if (now - lastRechargeTime < twentyNineDaysInMs) {
                let remainingDays = Math.ceil((twentyNineDaysInMs - (now - lastRechargeTime)) / (1000 * 60 * 60 * 24));
                alert(`Aap pichle 29 dino me recharge kar chuke hain. Aap agla recharge ${remainingDays} dino ke baad kar sakte hain.`);
                return;
            }

            db.usedTransactions.push(txInput);
            db.userRechargeTimestamps[currentMobile] = now;

            if (!db.users[currentMobile]) db.users[currentMobile] = { wallet: 0, subscription: null, freeTicketsLeft: 0 };
            db.users[currentMobile].wallet += 210;

            saveDB();
            updateHeader();
            document.getElementById('txFullInput').value = '';
            alert("Transaction successfully confirm ho gayi! Aapke wallet mein ₹210 turant add kar diye gaye hain.");
        }

        function checkUserHasActiveSub() {
            let isAdmin = (currentMobile === db.settings.adminNumber);
            if (isAdmin) return true;
            let user = db.users[currentMobile];
            if (user && user.subscription) {
                return new Date().getTime() < user.subscription.expiresAt;
            }
            return false;
        }

        function renderSubscriptionStatusBox() {
            let content = document.getElementById('subStatusContent');
            let user = db.users[currentMobile];
            let isAdmin = (currentMobile === db.settings.adminNumber);

            if (isAdmin) {
                content.innerHTML = `Role: Master Website Admin (Full Unlimited Access)`;
                return;
            }

            if (user && user.subscription && checkUserHasActiveSub()) {
                let sub = user.subscription;
                let now = new Date().getTime();
                let diffMs = sub.expiresAt - now;
                let diffHrs = Math.floor(diffMs / (1000 * 60 * 60));
                let diffDays = Math.floor(diffHrs / 24);
                
                let timeLeftText = diffDays > 0 ? `${diffDays} Days` : `${diffHrs} Hours`;
                let cashbackInfo = sub.cashbackPercent ? ` | Betting Cashback: <b>${sub.cashbackPercent}%</b>` : '';
                content.innerHTML = `Plan: <b>${sub.planName}</b> &nbsp;|&nbsp; Remaining: <b>${timeLeftText}</b> &nbsp;|&nbsp; Free Tickets: <b>${user.freeTicketsLeft || 0}</b>${cashbackInfo}`;
            } else {
                content.innerHTML = `No Plan`;
            }
        }

        function renderSubscriptionPlansHub() {
            let listHTML = '';
            db.settings.plans.forEach((plan) => {
                let validityText = plan.durationDays ? `${plan.durationDays} Days` : 'Active';
                let perkText = [];
                if (plan.freeTickets) perkText.push(`${plan.freeTickets} Tickets Free`);
                if (plan.discountPercent) perkText.push(`${plan.discountPercent}% Off`);
                if (plan.cashbackPercent) perkText.push(`${plan.cashbackPercent}% Betting Cash`);
                let perksDesc = perkText.length > 0 ? ` | Perks: ${perkText.join(', ')}` : '';

                listHTML += `
                    <div class="plan-card-item">
                        <div class="plan-info-group">
                            <div class="plan-price-tag">₹${plan.price}</div>
                            <div class="plan-meta-col">
                                <span class="plan-meta-label">Plan Details</span>
                                <span class="plan-meta-val">${plan.name}${perksDesc}</span>
                            </div>
                            <div class="plan-meta-col">
                                <span class="plan-meta-label">Validity</span>
                                <span class="plan-meta-val">${validityText}</span>
                            </div>
                        </div>
                        <button class="btn btn-primary" style="width: auto; padding: 10px 24px; font-size: 1rem;" onclick="buySpecificPlan('${plan.id}')">Buy</button>
                    </div>
                `;
            });
            document.getElementById('subPlansList').innerHTML = listHTML;
        }

        function buySpecificPlan(planId) {
            let planObj = db.settings.plans.find(p => p.id === planId);
            if (!planObj) return;

            let user = db.users[currentMobile];
            if (user.wallet < planObj.price) { alert("Wallet me balance kam hai! Pehle Transaction ID daal kar ₹210 add karein."); return; }

            user.wallet -= planObj.price;
            let adminMob = db.settings.adminNumber;
            if (!db.users[adminMob]) db.users[adminMob] = { wallet: 0, subscription: null, freeTicketsLeft: 0 };
            db.users[adminMob].wallet += planObj.price;

            let now = new Date().getTime();
            let expiresAt = now + ((planObj.durationDays || 28) * 24 * 3600 * 1000);

            user.subscription = {
                planId: planObj.id,
                planName: planObj.name,
                expiresAt: expiresAt,
                discountPercent: planObj.discountPercent || 0,
                cashbackPercent: planObj.cashbackPercent || 0
            };
            user.freeTicketsLeft = (user.freeTicketsLeft || 0) + (planObj.freeTickets || 0);

            saveDB();
            updateHeader();
            renderSubscriptionStatusBox();
            alert("Subscription successfully buy ho gaya aur saare perks add kar diye gaye hain!");
        }

        function openCreatorDashboard() {
            let modal = document.getElementById('creatorModal');
            let reqView = document.getElementById('subscriptionRequiredView');
            let actView = document.getElementById('creatorActionView');

            if (checkUserHasActiveSub()) {
                reqView.classList.add('hidden');
                actView.classList.remove('hidden');
            } else {
                reqView.classList.remove('hidden');
                actView.classList.add('hidden');
            }
            modal.classList.remove('hidden');
        }

        function closeCreatorModal() { document.getElementById('creatorModal').classList.add('hidden'); }
        
        function openMatchModal() { 
            closeCreatorModal(); 
            populateExistingSeriesDropdown('match');
            toggleSeriesInput('match');
            document.getElementById('matchModal').classList.remove('hidden'); 
        }
        function closeMatchModal() { document.getElementById('matchModal').classList.add('hidden'); }
        
        function openInternationalMatchModal() { 
            if (currentMobile !== db.settings.adminNumber) return;
            populateExistingSeriesDropdown('int');
            toggleSeriesInput('int');
            document.getElementById('internationalMatchModal').classList.remove('hidden'); 
        }
        function closeInternationalMatchModal() { document.getElementById('internationalMatchModal').classList.add('hidden'); }

        function toggleSeriesInput(prefix) {
            let type = document.getElementById(`${prefix}SeriesType`).value;
            let existingContainer = document.getElementById(`${prefix}ExistingSeriesContainer`);
            let newContainer = document.getElementById(`${prefix}NewSeriesContainer`);

            if (type === 'existing') {
                existingContainer.classList.remove('hidden');
                newContainer.classList.add('hidden');
            } else {
                existingContainer.classList.add('hidden');
                newContainer.classList.remove('hidden');
            }
        }

        function populateExistingSeriesDropdown(prefix) {
            let selectEl = document.getElementById(`${prefix}ExistingSeriesSelect`);
            let seriesList = [];
            db.matches.forEach(m => {
                if (m.seriesName && !seriesList.includes(m.seriesName)) {
                    seriesList.push(m.seriesName);
                }
            });

            if (seriesList.length === 0) {
                selectEl.innerHTML = '<option value="">Koi existing series nahi hai (New select karein)</option>';
                document.getElementById(`${prefix}SeriesType`).value = 'new';
                toggleSeriesInput(prefix);
            } else {
                let html = '';
                seriesList.forEach(s => {
                    html += `<option value="${s}">${s}</option>`;
                });
                selectEl.innerHTML = html;
            }
        }

        function saveMatchSchedule(isInternational) {
            if (isInternational && currentMobile !== db.settings.adminNumber) {
                alert("International match sirf Admin create kar sakta hai!");
                return;
            }

            let prefix = isInternational ? 'int' : 'match';
            let seriesType = document.getElementById(`${prefix}SeriesType`).value;
            let seriesName = seriesType === 'existing' ? document.getElementById(`${prefix}ExistingSeriesSelect`).value : document.getElementById(`${prefix}SeriesName`).value.trim();

            let matchObj = {
                id: 'match_' + Date.now(),
                creator: currentMobile,
                isInternational: isInternational,
                seriesName: seriesName,
                team1: document.getElementById(`${prefix}Team1`).value.trim(),
                team2: document.getElementById(`${prefix}Team2`).value.trim(),
                matchFormat: document.getElementById(`${prefix}Format`).value.trim() || "T20I",
                dateTime: document.getElementById(`${prefix}DateTime`).value.trim() || "WED, 17 DEC, 2026 | 7 PM",
                venue: document.getElementById(`${prefix}Venue`).value.trim() || "STADIUM, LUCKNOW",
                gateTime: document.getElementById(`${prefix}GateTime`).value.trim() || "Gate Opens: 2 Hours Before",
                price: isInternational ? (Number(document.getElementById(`${prefix}Price`).value) || 0) : 0,
                limit: isInternational ? (Number(document.getElementById(`${prefix}Limit`).value) || 0) : 0,
                soldCount: 0,
                code6: document.getElementById(`${prefix}Code6`).value.trim(),
                resultStatus: document.getElementById(`${prefix}ResultStatus`).value
            };

            db.matches.push(matchObj);
            saveDB();
            if (isInternational) closeInternationalMatchModal();
            else closeMatchModal();
            renderMatches();
            renderActiveTickets();
            alert("Match successfully publish ho gaya!");
        }

        function verifyMatchCode() {
            let code = document.getElementById('verifyCodeInput').value.trim();
            let resDiv = document.getElementById('verifyResult');
            let match = db.matches.find(m => m.code6 === code);

            if (!match) {
                resDiv.innerHTML = `<div class="alert-box" style="background:#fadbd8; color:#78281f; padding:12px; border-radius:8px;">Invalid 6-Digit Code!</div>`;
                return;
            }

            resDiv.innerHTML = `
                <div class="alert-box" style="background:#d4efdf; color:#145a32; padding:12px; border-radius:8px;">
                    <strong>Series:</strong> ${match.seriesName}<br>
                    <strong>Match:</strong> ${match.team1} vs ${match.team2} (${match.matchFormat})<br>
                    <strong>Venue:</strong> ${match.venue}<br>
                    <strong>Date:</strong> ${match.dateTime}
                </div>
            `;
        }

        function renderMatches() {
            let intList = document.getElementById('internationalMatchesList');
            let apnaList = document.getElementById('apnaMatchesList');

            let groupMatches = (matchesArr) => {
                let grouped = {};
                matchesArr.forEach(m => {
                    let sName = m.seriesName || 'Other Matches';
                    if (!grouped[sName]) grouped[sName] = [];
                    grouped[sName].push(m);
                });
                return grouped;
            };

            let intGrouped = groupMatches(db.matches.filter(m => m.isInternational));
            let apnaGrouped = groupMatches(db.matches.filter(m => !m.isInternational));

            let buildGroupHTML = (groupedObj) => {
                let finalHTML = '';
                for (let sName in groupedObj) {
                    finalHTML += `<div class="match-card" style="background:#f8fafc; border-left: 6px solid var(--primary); margin-bottom: 25px;"><div class="series-title-bar"><span>🏆 Series: ${sName}</span></div>`;
                    groupedObj[sName].forEach(match => {
                        finalHTML += `
                            <div style="background:#fff; border: 1px solid var(--border); border-radius: 10px; padding: 15px; margin-bottom: 12px;">
                                <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 8px;">
                                    <span style="font-size:0.85rem; background:#e2e8f0; padding:2px 8px; border-radius:4px;">Code: ${match.code6}</span>
                                    <span style="font-size:0.85rem; color:#666;">Creator: ${match.creator}</span>
                                </div>
                                <div class="match-row">
                                    <div class="team-box">🏏 ${match.team1}</div>
                                    <div class="vs-text"><span>VS</span><span class="match-format-green">${match.matchFormat || 'T20I'}</span></div>
                                    <div class="team-box">${match.team2} 🏏</div>
                                </div>
                                <div style="font-size:0.95rem; color:#444; margin-bottom:6px;">📍 <strong>Venue:</strong> ${match.venue}</div>
                                <div style="font-size:0.95rem; color:#444; margin-bottom:10px;">📅 <strong>Date/Time:</strong> ${match.dateTime}</div>
                            </div>
                        `;
                    });
                    finalHTML += `</div>`;
                }
                return finalHTML;
            };

            intList.innerHTML = buildGroupHTML(intGrouped) || '<p>Koi International match nahi hai.</p>';
            apnaList.innerHTML = buildGroupHTML(apnaGrouped) || '<p>Koi apna schedule create nahi kiya gaya hai.</p>';
        }

        function buyTicket(matchId) {
            let match = db.matches.find(m => m.id === matchId);
            let user = db.users[currentMobile];

            let finalPrice = match.price;
            let hasSub = checkUserHasActiveSub();

            if (hasSub && user.freeTicketsLeft && user.freeTicketsLeft > 0) {
                user.freeTicketsLeft -= 1;
                finalPrice = 0;
            } else if (hasSub && user.subscription && user.subscription.discountPercent) {
                let disc = user.subscription.discountPercent;
                finalPrice = Math.round(match.price * (100 - disc) / 100);
            }

            if (user.wallet < finalPrice) { alert("Wallet balance kam hai!"); return; }

            user.wallet -= finalPrice;
            match.soldCount += 1;
            db.tickets.push({
                id: 'tkt_' + Date.now(),
                matchId: match.id,
                mobile: currentMobile,
                pricePaid: finalPrice,
                status: 'Active'
            });

            saveDB();
            updateHeader();
            renderActiveTickets();
            renderMyPurchasedTickets();
            alert(finalPrice === 0 ? "Free ticket successfully claim ho gayi!" : "Ticket successfully buy ho gayi!");
        }

        function renderActiveTickets() {
            let listDiv = document.getElementById('activeTicketsList');
            let userActiveTickets = db.tickets.filter(t => t.mobile === currentMobile && t.status === 'Active');

            let storeHTML = '<h3>🛍️ Available Matches Store (Buy Tickets)</h3>';
            let storeMatches = db.matches.filter(m => m.isInternational && m.price > 0 && m.resultStatus === 'Upcoming');

            if (storeMatches.length === 0) {
                storeHTML += '<p style="color:#666; margin-bottom:15px;">Filhal store mein koi ticket available nahi hai.</p>';
            } else {
                let hasSub = checkUserHasActiveSub();
                let user = db.users[currentMobile];
                storeMatches.forEach(m => {
                    let displayPrice = m.price;
                    let priceLabel = `₹${m.price}`;
                    let discPercent = (hasSub && user.subscription) ? user.subscription.discountPercent : 0;

                    if (hasSub && user.freeTicketsLeft > 0) {
                        priceLabel = `<b style="color:var(--success);">FREE (${user.freeTicketsLeft} left)</b>`;
                    } else if (hasSub && discPercent > 0) {
                        displayPrice = Math.round(m.price * (100 - discPercent) / 100);
                        priceLabel = `<span style="text-decoration: line-through; color: #888;">₹${m.price}</span> <b style="color:var(--success);">₹${displayPrice} (${discPercent}% Off)</b>`;
                    }
                    storeHTML += `
                        <div style="background:#fff; padding:18px; margin-bottom:14px; border-radius:10px; border:2px solid var(--border); display:flex; justify-content:space-between; align-items:center; flex-wrap:wrap; gap:12px;">
                            <div>
                                <strong style="font-size:1.1rem; color:var(--primary);">${m.seriesName}</strong><br>
                                <span style="font-size:1.05rem; font-weight:bold;">${m.team1} vs ${m.team2}</span><br>
                                <small style="color:#666;">${m.matchFormat} | 📍 ${m.venue}</small>
                            </div>
                            <div><button class="btn btn-success" style="padding:10px 18px; width:auto;" onclick="buyTicket('${m.id}')">Buy - ${priceLabel}</button></div>
                        </div>
                    `;
                });
            }

            let ticketsHTML = '<h3 style="margin-top:25px;">🎟️ Your Active Tickets</h3>';
            userActiveTickets.forEach(tkt => {
                let match = db.matches.find(m => m.id === tkt.matchId);
                if (!match) return;
                ticketsHTML += `
                    <div class="physical-ticket">
                        <div class="ticket-header"><span>🎫 ${match.seriesName}</span><span>${match.matchFormat}</span></div>
                        <div class="ticket-teams-title">${match.team1} VS ${match.team2}</div>
                        <div class="ticket-venue">📍 ${match.venue}</div>
                        <div class="ticket-footer"><span>ID: ${tkt.id}</span><span>Paid: ₹${tkt.pricePaid}</span></div>
                    </div>
                `;
            });

            listDiv.innerHTML = storeHTML + '<hr style="margin:25px 0;">' + ticketsHTML;
        }

        function renderMyPurchasedTickets() {
            let listDiv = document.getElementById('myPurchasedList');
            let userTickets = db.tickets.filter(t => t.mobile === currentMobile);
            let html = '';
            userTickets.forEach(tkt => {
                let match = db.matches.find(m => m.id === tkt.matchId);
                let matchName = match ? `${match.team1} vs ${match.team2}` : 'Match';
                html += `<div class="physical-ticket" style="opacity:0.95;"><div class="ticket-header"><span>Ticket ID: ${tkt.id}</span><span>${matchName}</span></div><div class="ticket-footer"><span>Paid: ₹${tkt.pricePaid}</span><span>${tkt.status}</span></div></div>`;
            });
            listDiv.innerHTML = html || '<p>Koi ticket history nahi hai.</p>';
        }

        function openMasterAdminPanel() {
            if (currentMobile !== db.settings.adminNumber) return;
            renderAdminAllMatches();
            renderAdminAllTickets();
            renderAdminPlansList();
            document.getElementById('masterAdminModal').classList.remove('hidden');
        }

        function closeMasterAdminPanel() { document.getElementById('masterAdminModal').classList.add('hidden'); }

        function switchAdminSubTab(tabName, evt) {
            document.querySelectorAll('.admin-sub-tab').forEach(el => el.classList.add('hidden'));
            if (tabName === 'matches') document.getElementById('adminTabMatches').classList.remove('hidden');
            if (tabName === 'tickets') document.getElementById('adminTabTickets').classList.remove('hidden');
            if (tabName === 'plans') document.getElementById('adminTabPlans').classList.remove('hidden');
            
            if(evt && evt.target) {
                let parent = evt.target.parentElement;
                parent.querySelectorAll('.tab-btn').forEach(el => el.classList.remove('active'));
                evt.target.classList.add('active');
            }
        }

        function renderAdminAllMatches() {
            let container = document.getElementById('adminAllMatchesList');
            let html = '';
            db.matches.forEach(match => {
                html += `<div class="match-card"><p><strong>${match.seriesName}</strong> (${match.team1} vs ${match.team2})</p></div>`;
            });
            container.innerHTML = html || '<p>Koi match nahi hai.</p>';
        }

        function renderAdminAllTickets() {
            let container = document.getElementById('adminAllTicketsList');
            let html = '';
            db.tickets.forEach(tkt => {
                html += `<div class="match-card"><p><strong>Ticket ID:</strong> ${tkt.id} | User: ${tkt.mobile}</p></div>`;
            });
            container.innerHTML = html || '<p>Koi ticket nahi hai.</p>';
        }

        function renderAdminPlansList() {
            let container = document.getElementById('adminPlansList');
            let html = '';
            db.settings.plans.forEach(plan => {
                html += `<div class="match-card" style="padding:12px; margin-bottom:10px;"><p><strong>${plan.name}</strong> - ₹${plan.price} (${plan.freeTickets || 0} Free Tickets, ${plan.discountPercent || 0}% Off, ${plan.cashbackPercent || 0}% Cashback)</p></div>`;
            });
            container.innerHTML = html;
        }

        function addNewSubscriptionPlan() {
            let id = document.getElementById('newPlanId').value.trim();
            let name = document.getElementById('newPlanName').value.trim();
            let price = Number(document.getElementById('newPlanPrice').value);
            let days = Number(document.getElementById('newPlanDays').value);
            let freeTkt = Number(document.getElementById('newPlanFreeTickets').value) || 0;
            let disc = Number(document.getElementById('newPlanDiscount').value) || 0;
            let cashback = Number(document.getElementById('newPlanCashback').value) || 0;

            if (!id || !name || !price) { alert("Saari zaroori details bharein!"); return; }

            db.settings.plans.push({
                id: id,
                name: name,
                price: price,
                durationDays: days || 28,
                freeTickets: freeTkt,
                discountPercent: disc,
                cashbackPercent: cashback
            });
            saveDB();
            renderSubscriptionPlansHub();
            renderAdminPlansList();
            alert("Naya subscription plan successfully add ho gaya!");
        }

        function switchTab(tabName, evt) {
            document.querySelectorAll('.tab-content').forEach(el => el.classList.add('hidden'));
            if (tabName === 'international') document.getElementById('internationalTabContent').classList.remove('hidden');
            if (tabName === 'apna') document.getElementById('apnaTabContent').classList.remove('hidden');
            if (tabName === 'activeTickets') document.getElementById('activeTicketsTabContent').classList.remove('hidden');
            if (tabName === 'myPurchased') document.getElementById('myPurchasedTabContent').classList.remove('hidden');

            if(evt && evt.target) {
                document.querySelectorAll('.tabs .tab-btn').forEach(el => el.classList.remove('active'));
                evt.target.classList.add('active');
            }
        }
    </script>
</body>
</html>
 Is code me ye system he bina recharge ke paise nahi le paaye ga
