# SoolPrimary
[index.html](https://github.com/user-attachments/files/25039162/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no"/>
  <title>Sool Primary</title>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
    body {
      font-family: 'Segoe UI', system-ui, sans-serif;
      background: linear-gradient(135deg, #f0f9ff, #e0f2fe);
      min-height: 100vh;
      padding: 16px;
      color: #1e293b;
    }
    .container { max-width: 520px; margin: 0 auto; }
    .card {
      background: white;
      border-radius: 16px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.08);
      padding: 20px;
      margin-bottom: 20px;
    }
    .header { text-align: center; margin-bottom: 20px; }
    .header h1 { color: #0c4a6e; font-size: 24px; font-weight: 700; }
    .user-tag { font-size: 14px; color: #64748b; margin-top: 6px; }
    
    /* Tabs */
    .tabs { display: flex; gap: 6px; margin-bottom: 20px; flex-wrap: wrap; }
    .tab-btn {
      padding: 10px 12px;
      background: #f1f5f9;
      border: none;
      border-radius: 10px;
      font-weight: 600;
      font-size: 15px;
      cursor: pointer;
      transition: all 0.2s;
      flex: 1;
      min-width: 90px;
      text-align: center;
    }
    .tab-btn.active { background: #3b82f6; color: white; }
    .tab-btn:active { transform: scale(0.98); }

    /* Date Field */
    .date-field {
      display: flex;
      gap: 10px;
      margin-bottom: 20px;
    }
    .date-field input {
      flex: 1;
      padding: 12px;
      border: 1px solid #cbd5e1;
      border-radius: 12px;
      font-size: 16px;
    }
    .btn-today {
      background: #10b981;
      color: white;
      border: none;
      padding: 12px 16px;
      border-radius: 12px;
      font-weight: 600;
      cursor: pointer;
    }
    .btn-today:hover { background: #059669; }

    /* Session Buttons */
    .session-buttons {
      display: flex;
      gap: 10px;
      margin-bottom: 20px;
    }
    .session-btn {
      flex: 1;
      padding: 14px;
      border: none;
      border-radius: 12px;
      font-weight: 600;
      font-size: 16px;
      cursor: pointer;
      transition: all 0.2s;
    }
    .session-btn.active {
      background: #3b82f6;
      color: white;
    }
    .session-btn:not(.active) {
      background: #f1f5f9;
      color: #475569;
    }

    /* Status Buttons */
    .status-buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
      margin-bottom: 20px;
    }
    .status-btn {
      padding: 12px;
      border: none;
      border-radius: 12px;
      font-weight: 600;
      font-size: 14px;
      cursor: pointer;
      transition: all 0.2s;
    }
    .status-btn.present { background: #dcfce7; color: #166534; }
    .status-btn.absent { background: #fee2e2; color: #b91c1c; }
    .status-btn.late { background: #fef3c7; color: #92400e; }
    .status-btn.sick { background: #ede9fe; color: #5b21b6; }
    .status-btn.active {
      transform: scale(0.97);
      box-shadow: 0 2px 6px rgba(0,0,0,0.15);
    }

    /* Save Button */
    .btn-save {
      background: #0ea5e9;
      color: white;
      border: none;
      width: 100%;
      padding: 16px;
      border-radius: 12px;
      font-size: 18px;
      font-weight: 700;
      cursor: pointer;
      margin-bottom: 15px;
    }
    .btn-save:hover { background: #0284c7; }

    /* Logout Button */
    .btn-logout {
      background: #ef4444;
      color: white;
      border: none;
      width: 100%;
      padding: 16px;
      border-radius: 12px;
      font-size: 18px;
      font-weight: 700;
      cursor: pointer;
    }
    .btn-logout:hover { background: #dc2626; }

    /* Form groups */
    .form-group {
      margin-bottom: 16px;
    }
    label {
      display: block;
      margin-bottom: 8px;
      font-weight: 600;
      font-size: 15px;
    }
    input, select {
      width: 100%;
      padding: 14px;
      border: 1px solid #cbd5e1;
      border-radius: 12px;
      font-size: 16px;
      background: white;
    }
    input:focus, select:focus {
      outline: none;
      border-color: #3b82f6;
      box-shadow: 0 0 0 3px rgba(59,130,246,0.2);
    }

    .message {
      padding: 12px;
      border-radius: 12px;
      text-align: center;
      margin-top: 16px;
      font-weight: 600;
    }
    .success { background: #dcfce7; color: #166534; display: none; }
    .error { background: #fee2e2; color: #b91c1c; display: none; }

    #loginContainer { display: block; }
    #appContainer { display: none; }
  </style>
</head>
<body>
  <!-- LOGIN -->
  <div class="container" id="loginContainer">
    <div class="card">
      <div class="header">
        <h1>🏫 Sool Primary</h1>
        <p style="color:#64748b;margin-top:6px;">Staff Login</p>
      </div>
      <form id="loginForm">
        <div class="form-group">
          <label>Username</label>
          <input type="text" id="username" autocomplete="off" required />
        </div>
        <div class="form-group">
          <label>Password</label>
          <input type="password" id="password" required />
        </div>
        <button type="submit" class="btn-primary" style="width:100%;background:#0ea5e9;color:white;border:none;padding:14px;border-radius:12px;font-weight:600;">
          Sign In
        </button>
        <div id="loginError" class="message error"></div>
      </form>
    </div>
  </div>

  <!-- MAIN APP -->
  <div class="container" id="appContainer">
    <div class="card">
      <div class="header">
        <h1>📚 Sool Primary</h1>
        <div class="user-tag" id="userDisplay"></div>
      </div>

      <!-- TABS -->
      <div class="tabs" id="mainTabs">
        <button class="tab-btn active" onclick="showTab('attendance')">Attendance</button>
      </div>

      <!-- ATTENDANCE -->
      <div id="attendanceTab">
        <div class="form-group">
          <label>Date *</label>
          <div class="date-field">
            <input type="date" id="attDate" required />
            <button type="button" class="btn-today" onclick="setToday()">Today</button>
          </div>
        </div>

        <div class="form-group">
          <label>Session *</label>
          <div class="session-buttons">
            <button type="button" class="session-btn active" data-session="morning">Morning</button>
            <button type="button" class="session-btn" data-session="after_break">After Break</button>
          </div>
        </div>

        <div class="form-group">
          <label>Class *</label>
          <select id="attClass" required>
            <option value="">-- Select --</option>
            <option value="1aad">Grade 1</option>
            <option value="2aad">Grade 2</option>
            <option value="3aad">Grade 3</option>
            <option value="4aad">Grade 4</option>
            <option value="5aad">Grade 5</option>
            <option value="6aad">Grade 6</option>
            <option value="7aad">Grade 7</option>
            <option value="8aad">Grade 8</option>
          </select>
        </div>

        <div class="form-group">
          <label>Roll Number *</label>
          <input type="number" id="attRoll" min="1" required placeholder="Type roll number" />
        </div>

        <div class="form-group">
          <label>Student Name (Optional)</label>
          <input type="text" id="attName" placeholder="Auto-filled or type manually" />
        </div>

        <div class="form-group">
          <label>Status *</label>
          <div class="status-buttons">
            <button type="button" class="status-btn present active" data-status="present">Present</button>
            <button type="button" class="status-btn absent" data-status="absent">Absent</button>
            <button type="button" class="status-btn late" data-status="late">Late</button>
            <button type="button" class="status-btn sick" data-status="sick">Sick</button>
          </div>
        </div>

        <button type="button" class="btn-save" onclick="saveAttendance()">Save Attendance</button>
        <button type="button" class="btn-logout" onclick="logout()">Logout</button>
      </div>

      <!-- REGISTRATION (ADMIN ONLY) -->
      <div id="registerTab" style="display:none;">
        <h3 style="margin-bottom:20px;">📝 Register Student</h3>
        <div class="form-group">
          <label>Student Name *</label>
          <input type="text" id="regName" required />
        </div>
        <div class="form-group">
          <label>Mother's Name *</label>
          <input type="text" id="regMother" required />
        </div>
        <div class="form-group">
          <label>Date of Birth *</label>
          <input type="date" id="regDOB" required />
        </div>
        <div class="form-group">
          <label>Place of Birth *</label>
          <input type="text" id="regPOB" placeholder="e.g., Garowe" required />
        </div>
        <div class="form-group">
          <label>School Transferred From</label>
          <input type="text" id="regSchool" placeholder="Optional" />
        </div>
        <div class="form-group">
          <label>Contact Info *</label>
          <input type="text" id="regContact" placeholder="+252 61 2345678" required />
        </div>
        <div class="form-group">
          <label>Class *</label>
          <select id="regClass" required>
            <option value="">-- Select --</option>
            <option value="1aad">Grade 1</option>
            <option value="2aad">Grade 2</option>
            <option value="3aad">Grade 3</option>
            <option value="4aad">Grade 4</option>
            <option value="5aad">Grade 5</option>
            <option value="6aad">Grade 6</option>
            <option value="7aad">Grade 7</option>
            <option value="8aad">Grade 8</option>
          </select>
        </div>
        <button type="button" class="btn-primary" style="width:100%;background:#0ea5e9;color:white;padding:14px;border-radius:12px;font-weight:600;" onclick="registerStudent()">
          Register Student
        </button>
        <button type="button" class="btn-logout" style="margin-top:10px;" onclick="logout()">Logout</button>
      </div>

      <!-- FEE MANAGEMENT (ADMIN ONLY) -->
      <div id="feeTab" style="display:none;">
        <h3 style="margin-bottom:20px;">💰 Fee Payment</h3>
        <div class="form-group">
          <label>Student Name *</label>
          <input type="text" id="feeName" required />
        </div>
        <div class="form-group">
          <label>Roll Number *</label>
          <input type="text" id="feeRoll" required />
        </div>
        <div class="form-group">
          <label>Class *</label>
          <select id="feeClass" required>
            <option value="">-- Select --</option>
            <option value="1aad">Grade 1</option>
            <option value="2aad">Grade 2</option>
            <option value="3aad">Grade 3</option>
            <option value="4aad">Grade 4</option>
            <option value="5aad">Grade 5</option>
            <option value="6aad">Grade 6</option>
            <option value="7aad">Grade 7</option>
            <option value="8aad">Grade 8</option>
          </select>
        </div>
        <div class="form-group">
          <label>Month/Year (YYYY-MM) *</label>
          <input type="text" id="feeMonth" placeholder="e.g. 2026-02" required />
        </div>
        <div class="form-group">
          <label>Monthly Fee (USD)</label>
          <input type="number" id="feeMonthly" value="5" step="0.01" />
        </div>
        <div class="form-group">
          <label>Exam Fee (USD)</label>
          <input type="number" id="feeExam" value="0" step="0.01" />
        </div>
        <div class="form-group">
          <label>Paid Amount (USD) *</label>
          <input type="number" id="feePaid" step="0.01" required />
        </div>
        <div class="form-group">
          <label>Payment Date *</label>
          <input type="date" id="feeDate" required />
        </div>
        <button type="button" class="btn-primary" style="width:100%;background:#0ea5e9;color:white;padding:14px;border-radius:12px;font-weight:600;" onclick="recordFee()">
          Record Payment
        </button>
        <button type="button" class="btn-logout" style="margin-top:10px;" onclick="logout()">Logout</button>
      </div>

      <!-- STUDENT MANAGEMENT (ADMIN ONLY) -->
      <div id="studentTab" style="display:none;">
        <h3 style="margin-bottom:20px;">🎓 Student Status</h3>
        <div class="form-group">
          <label>Class *</label>
          <select id="stuClass" required>
            <option value="">-- Select --</option>
            <option value="1aad">Grade 1</option>
            <option value="2aad">Grade 2</option>
            <option value="3aad">Grade 3</option>
            <option value="4aad">Grade 4</option>
            <option value="5aad">Grade 5</option>
            <option value="6aad">Grade 6</option>
            <option value="7aad">Grade 7</option>
            <option value="8aad">Grade 8</option>
          </select>
        </div>
        <div class="form-group">
          <label>Roll Number *</label>
          <input type="number" id="stuRoll" min="1" required />
        </div>
        <div class="form-group">
          <label>Status *</label>
          <select id="stuStatus" required>
            <option value="active">Active</option>
            <option value="dropout">Dropout</option>
            <option value="not_active">Not Active</option>
          </select>
        </div>
        <button type="button" class="btn-primary" style="width:100%;background:#0ea5e9;color:white;padding:14px;border-radius:12px;font-weight:600;" onclick="updateStudentStatus()">
          Update Status
        </button>
        <button type="button" class="btn-logout" style="margin-top:10px;" onclick="logout()">Logout</button>
      </div>

      <!-- USER MANAGEMENT (ADMIN ONLY) -->
      <div id="userTab" style="display:none;">
        <h3 style="margin-bottom:20px;">👥 Add New User</h3>
        <div class="form-group">
          <label>Username *</label>
          <input type="text" id="newUser" required />
        </div>
        <div class="form-group">
          <label>Password *</label>
          <input type="password" id="newPass" required />
        </div>
        <div class="form-group">
          <label>Role</label>
          <select id="newRole">
            <option value="teacher">Teacher</option>
            <option value="admin">Admin</option>
          </select>
        </div>
        <button type="button" class="btn-primary" style="width:100%;background:#0ea5e9;color:white;padding:14px;border-radius:12px;font-weight:600;" onclick="addUser()">
          Add User
        </button>

        <h3 style="margin-top:30px;margin-bottom:20px;">🔑 Change Password</h3>
        <div class="form-group">
          <label>Username *</label>
          <input type="text" id="cpUser" required />
        </div>
        <div class="form-group">
          <label>New Password *</label>
          <input type="password" id="cpPass" required />
        </div>
        <button type="button" class="btn-primary" style="width:100%;background:#0ea5e9;color:white;padding:14px;border-radius:12px;font-weight:600;" onclick="changePassword()">
          Change Password
        </button>
        <button type="button" class="btn-logout" style="margin-top:10px;" onclick="logout()">Logout</button>
      </div>
    </div>
  </div>

  <script>
    // 🔗 YOUR NEW GOOGLE APPS SCRIPT URL (WITH doGet)
    const SCRIPT_URL = 'https://script.google.com/macros/s/AKfycbwloLCsXF7mQ8PcRM5dB5pAOK2pEyPPqWkNpg29ZXl7e_lVcC-Idnqm0297RJE9UGaGpQ/exec';
    
    let currentUser = '';
    let userRole = '';
    let studentCache = []; // Stores active students for auto-fill

    function setToday() {
      document.getElementById('attDate').value = new Date().toISOString().split('T')[0];
      document.getElementById('feeDate').value = new Date().toISOString().split('T')[0];
    }

    function showTab(tabName) {
      document.getElementById('attendanceTab').style.display = 'none';
      document.getElementById('registerTab').style.display = 'none';
      document.getElementById('feeTab').style.display = 'none';
      document.getElementById('studentTab').style.display = 'none';
      document.getElementById('userTab').style.display = 'none';
      
      if (tabName === 'attendance') document.getElementById('attendanceTab').style.display = 'block';
      if (tabName === 'register') document.getElementById('registerTab').style.display = 'block';
      if (tabName === 'fee') document.getElementById('feeTab').style.display = 'block';
      if (tabName === 'students') document.getElementById('studentTab').style.display = 'block';
      if (tabName === 'users') document.getElementById('userTab').style.display = 'block';
      
      document.querySelectorAll('.tab-btn').forEach(btn => btn.classList.remove('active'));
      event.target.classList.add('active');
    }

    // Session selection
    document.querySelectorAll('.session-btn').forEach(btn => {
      btn.addEventListener('click', () => {
        document.querySelectorAll('.session-btn').forEach(b => b.classList.remove('active'));
        btn.classList.add('active');
      });
    });

    // Status selection
    document.querySelectorAll('.status-btn').forEach(btn => {
      btn.addEventListener('click', () => {
        document.querySelectorAll('.status-btn').forEach(b => b.classList.remove('active'));
        btn.classList.add('active');
      });
    });

    // Auto-fill name when roll number changes
    document.getElementById('attRoll').addEventListener('input', function() {
      const roll = this.value.trim();
      const cls = document.getElementById('attClass').value;
      
      if (roll && cls) {
        const student = studentCache.find(s => 
          String(s.roll_number) === roll && s.class === cls
        );
        document.getElementById('attName').value = student ? student.student_name : '';
      } else {
        document.getElementById('attName').value = '';
      }
    });

    // Also update when class changes
    document.getElementById('attClass').addEventListener('change', function() {
      const roll = document.getElementById('attRoll').value;
      if (roll) {
        document.getElementById('attRoll').dispatchEvent(new Event('input'));
      }
    });

    // Login
    document.getElementById('loginForm').addEventListener('submit', async function(e) {
      e.preventDefault();
      const u = document.getElementById('username').value.trim();
      const p = document.getElementById('password').value;
      
      if (u === 'AHMED' && p === '6884433@@') {
        currentUser = u;
        userRole = 'admin';
        document.getElementById('userDisplay').textContent = `Logged in as: ${u} (Admin)`;
        document.getElementById('loginContainer').style.display = 'none';
        document.getElementById('appContainer').style.display = 'block';
        
        // Load student data for auto-fill
        await loadStudentData();
        
        document.getElementById('mainTabs').innerHTML = `
          <button class="tab-btn" onclick="showTab('register')">Register</button>
          <button class="tab-btn active" onclick="showTab('attendance')">Attendance</button>
          <button class="tab-btn" onclick="showTab('fee')">Fees</button>
          <button class="tab-btn" onclick="showTab('students')">Students</button>
          <button class="tab-btn" onclick="showTab('users')">Users</button>
        `;
      } else {
        currentUser = u;
        userRole = 'teacher';
        document.getElementById('userDisplay').textContent = `Logged in as: ${u} (Teacher)`;
        document.getElementById('loginContainer').style.display = 'none';
        document.getElementById('appContainer').style.display = 'block';
        
        // Load student data for teachers too
        await loadStudentData();
        
        document.getElementById('mainTabs').innerHTML = `
          <button class="tab-btn active" onclick="showTab('attendance')">Attendance</button>
        `;
      }
    });

    // Fetch active students from Google Sheet
    async function loadStudentData() {
      try {
        const url = SCRIPT_URL.replace('/exec', '') + '?action=getStudents';
        const response = await fetch(url);
        if (response.ok) {
          studentCache = await response.json();
        }
      } catch (err) {
        console.error('Failed to load student data:', err);
      }
    }

    // Register Student (admin only)
    function registerStudent() {
      if (userRole !== 'admin') { alert('Access denied'); return; }
      const formData = new FormData();
      formData.append('form_type', 'registration');
      formData.append('student_name', document.getElementById('regName').value);
      formData.append('mother_name', document.getElementById('regMother').value);
      formData.append('date_of_birth', document.getElementById('regDOB').value);
      formData.append('place_of_birth', document.getElementById('regPOB').value);
      formData.append('school_transferred_from', document.getElementById('regSchool').value);
      formData.append('contact_info', document.getElementById('regContact').value);
      formData.append('class', document.getElementById('regClass').value);
      formData.append('timestamp', new Date().toISOString());
      submitToGoogle(formData, 'Registration');
    }

    // Save Attendance (all users)
    function saveAttendance() {
      const formData = new FormData();
      formData.append('form_type', 'attendance');
      formData.append('date', document.getElementById('attDate').value);
      formData.append('class', document.getElementById('attClass').value);
      formData.append('roll_number', document.getElementById('attRoll').value);
      formData.append('student_name', document.getElementById('attName').value);
      formData.append('attendance_status', document.querySelector('.status-btn.active').dataset.status);
      formData.append('session', document.querySelector('.session-btn.active').dataset.session);
      formData.append('recorded_by', currentUser);
      formData.append('timestamp', new Date().toISOString());
      submitToGoogle(formData, 'Attendance');
    }

    // Record Fee (admin only)
    function recordFee() {
      if (userRole !== 'admin') { alert('Access denied'); return; }
      const formData = new FormData();
      formData.append('form_type', 'fee_payment');
      formData.append('student_name', document.getElementById('feeName').value);
      formData.append('roll_number', document.getElementById('feeRoll').value);
      formData.append('class', document.getElementById('feeClass').value);
      formData.append('month_year', document.getElementById('feeMonth').value);
      formData.append('monthly_fee', document.getElementById('feeMonthly').value);
      formData.append('exam_fee', document.getElementById('feeExam').value);
      formData.append('paid_amount', document.getElementById('feePaid').value);
      formData.append('payment_date', document.getElementById('feeDate').value);
      formData.append('recorded_by', currentUser);
      formData.append('timestamp', new Date().toISOString());
      submitToGoogle(formData, 'Fee Payment');
    }

    // Update Student Status (admin only)
    function updateStudentStatus() {
      if (userRole !== 'admin') { alert('Access denied'); return; }
      const formData = new FormData();
      formData.append('form_type', 'update_status');
      formData.append('roll_number', document.getElementById('stuRoll').value);
      formData.append('class', document.getElementById('stuClass').value);
      formData.append('status', document.getElementById('stuStatus').value);
      formData.append('timestamp', new Date().toISOString());
      submitToGoogle(formData, 'Student Status Updated');
    }

    // Add User (admin only)
    function addUser() {
      if (userRole !== 'admin') { alert('Access denied'); return; }
      const formData = new FormData();
      formData.append('form_type', 'add_user');
      formData.append('username', document.getElementById('newUser').value);
      formData.append('password', document.getElementById('newPass').value);
      formData.append('role', document.getElementById('newRole').value);
      submitToGoogle(formData, 'User Added');
    }

    // Change Password (admin only)
    function changePassword() {
      if (userRole !== 'admin') { alert('Access denied'); return; }
      const formData = new FormData();
      formData.append('form_type', 'change_password');
      formData.append('username', document.getElementById('cpUser').value);
      formData.append('new_password', document.getElementById('cpPass').value);
      submitToGoogle(formData, 'Password Changed');
    }

    // Generic submit
    function submitToGoogle(formData, action) {
      const params = new URLSearchParams();
      for (let [key, value] of formData.entries()) {
        params.append(key, value);
      }

      const img = new Image();
      img.src = SCRIPT_URL + '?' + params.toString();

      const msgEl = document.querySelector('.message');
      msgEl.textContent = `✅ ${action} successful!`;
      msgEl.className = 'message success';
      msgEl.style.display = 'block';
      
      setTimeout(() => {
        msgEl.style.display = 'none';
      }, 2000);
    }

    function logout() {
      currentUser = '';
      userRole = '';
      studentCache = [];
      document.getElementById('appContainer').style.display = 'none';
      document.getElementById('loginContainer').style.display = 'block';
      document.getElementById('loginForm').reset();
      document.getElementById('loginError').style.display = 'none';
      document.getElementById('mainTabs').innerHTML = '<button class="tab-btn active" onclick="showTab(\'attendance\')">Attendance</button>';
    }

    setToday();
  </script>
</body>
</html>
