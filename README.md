<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Daraz QA Project - Comprehensive Testing Suite</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #333;
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Header Section */
        .header {
            background: white;
            border-radius: 20px;
            padding: 40px;
            margin-bottom: 30px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
            text-align: center;
        }

        .logo-container {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 30px;
            margin-bottom: 20px;
            flex-wrap: wrap;
        }

        .daraz-logo {
            width: 150px;
            height: auto;
        }

        .qa-badge {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 10px 20px;
            border-radius: 50px;
            font-weight: bold;
            font-size: 1.2em;
        }

        h1 {
            font-size: 2.5em;
            margin: 20px 0;
            color: #333;
        }

        .subtitle {
            font-size: 1.2em;
            color: #666;
            margin-bottom: 20px;
        }

        /* Stats Bar */
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .stat-card {
            background: white;
            padding: 20px;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }

        .stat-card:hover {
            transform: translateY(-5px);
        }

        .stat-number {
            font-size: 2em;
            font-weight: bold;
            color: #667eea;
        }

        .stat-label {
            color: #666;
            margin-top: 10px;
        }

        /* Navigation Tabs */
        .tabs {
            display: flex;
            gap: 10px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }

        .tab-btn {
            background: white;
            border: none;
            padding: 12px 24px;
            border-radius: 10px;
            cursor: pointer;
            font-size: 1em;
            transition: all 0.3s;
            font-weight: 500;
        }

        .tab-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        .tab-btn.active {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }

        /* Content Sections */
        .content-section {
            display: none;
            background: white;
            border-radius: 20px;
            padding: 40px;
            margin-bottom: 30px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
            animation: fadeIn 0.5s;
        }

        .content-section.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Test Cases Table */
        .test-table {
            overflow-x: auto;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }

        th, td {
            padding: 12px;
            text-align: left;
            border-bottom: 1px solid #ddd;
        }

        th {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            font-weight: 600;
        }

        tr:hover {
            background: #f5f5f5;
        }

        .badge {
            display: inline-block;
            padding: 4px 12px;
            border-radius: 12px;
            font-size: 0.85em;
            font-weight: 500;
        }

        .badge-pass {
            background: #4caf50;
            color: white;
        }

        .badge-fail {
            background: #f44336;
            color: white;
        }

        .badge-pending {
            background: #ff9800;
            color: white;
        }

        /* Gallery Grid */
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .gallery-item {
            background: #f5f5f5;
            border-radius: 10px;
            overflow: hidden;
            cursor: pointer;
            transition: transform 0.3s;
        }

        .gallery-item:hover {
            transform: scale(1.05);
        }

        .gallery-item img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .gallery-caption {
            padding: 10px;
            font-size: 0.9em;
            text-align: center;
        }

        /* Modal for Image Viewing */
        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.9);
            cursor: pointer;
        }

        .modal-content {
            margin: auto;
            display: block;
            max-width: 90%;
            max-height: 90%;
            margin-top: 50px;
        }

        .close {
            position: absolute;
            top: 20px;
            right: 40px;
            color: white;
            font-size: 40px;
            cursor: pointer;
        }

        /* Footer */
        .footer {
            text-align: center;
            padding: 20px;
            color: white;
        }

        .github-link {
            color: white;
            text-decoration: none;
            border-bottom: 2px solid white;
        }

        @media (max-width: 768px) {
            .header {
                padding: 20px;
            }
            
            h1 {
                font-size: 1.8em;
            }
            
            .content-section {
                padding: 20px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header -->
        <div class="header">
            <div class="logo-container">
                <svg class="daraz-logo" viewBox="0 0 200 60" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <rect width="200" height="60" rx="10" fill="#F57224"/>
                    <text x="20" y="38" font-family="Arial" font-size="24" font-weight="bold" fill="white">Daraz</text>
                    <text x="100" y="38" font-family="Arial" font-size="16" fill="white">QA Project</text>
                </svg>
                <div class="qa-badge">⭐ Quality Assurance Excellence</div>
            </div>
            <h1>Daraz E-commerce Platform Testing</h1>
            <div class="subtitle">
                Comprehensive Manual Testing Suite | Bug Tracking | Test Case Management
            </div>
        </div>

        <!-- Stats -->
        <div class="stats">
            <div class="stat-card">
                <div class="stat-number">25+</div>
                <div class="stat-label">Test Cases</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">6</div>
                <div class="stat-label">Defects Found</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">8</div>
                <div class="stat-label">Test Screenshots</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">100%</div>
                <div class="stat-label">Test Coverage</div>
            </div>
        </div>

        <!-- Tabs -->
        <div class="tabs">
            <button class="tab-btn active" onclick="showTab('overview')">📋 Overview</button>
            <button class="tab-btn" onclick="showTab('testcases')">📊 Test Cases</button>
            <button class="tab-btn" onclick="showTab('defects')">🐛 Defects & Bugs</button>
            <button class="tab-btn" onclick="showTab('gallery')">🖼️ Screenshot Gallery</button>
            <button class="tab-btn" onclick="showTab('setup')">🚀 How to Use</button>
        </div>

        <!-- Overview Section -->
        <div id="overview" class="content-section active">
            <h2>📋 Project Overview</h2>
            <p>This project is a comprehensive Quality Assurance initiative for the <strong>Daraz</strong> e-commerce platform. The testing focuses on validating core functionalities including user authentication, product search, cart operations, and password recovery mechanisms.</p>
            
            <h3>🎯 Testing Objectives</h3>
            <ul>
                <li>✅ Validate all critical user journeys (Login, Signup, Search, Add to Cart)</li>
                <li>✅ Identify and document defects with severity levels</li>
                <li>✅ Ensure proper error handling and user feedback</li>
                <li>✅ Test cross-browser compatibility</li>
                <li>✅ Verify responsive design on mobile devices</li>
            </ul>

            <h3>🛠️ Tools & Technologies</h3>
            <ul>
                <li><strong>Jira</strong> - Bug tracking and project management</li>
                <li><strong>Excel</strong> - Test case design and execution tracking</li>
                <li><strong>Daraz Platform</strong> - System Under Test (SUT)</li>
                <li><strong>GitHub</strong> - Version control and documentation</li>
            </ul>

            <h3>📈 Testing Metrics</h3>
            <ul>
                <li>Total Test Cases Executed: 25+</li>
                <li>Defects Found: 6 (3 Critical, 2 Major, 1 Minor)</li>
                <li>Test Pass Rate: 76%</li>
                <li>Test Coverage: Authentication, Search, Cart, Checkout flows</li>
            </ul>
        </div>

        <!-- Test Cases Section -->
        <div id="testcases" class="content-section">
            <h2>📊 Test Case Summary</h2>
            <p>Complete test suite available in <strong>Daraz_Test_Cases.xlsx</strong></p>
            <div class="test-table">
                <table>
                    <thead>
                        <tr><th>Test Case ID</th><th>Module</th><th>Description</th><th>Status</th></tr>
                    </thead>
                    <tbody>
                        <tr><td>TC-001</td><td>Signup</td><td>Valid user registration with correct data</td><td><span class="badge badge-pass">PASS</span></td></tr>
                        <tr><td>TC-002</td><td>Signup</td><td>Registration with mismatched passwords</td><td><span class="badge badge-fail">FAIL</span></td></tr>
                        <tr><td>TC-003</td><td>Signup</td><td>Registration with existing email</td><td><span class="badge badge-pass">PASS</span></td></tr>
                        <tr><td>TC-004</td><td>Login</td><td>Valid credentials login</td><td><span class="badge badge-pass">PASS</span></td></tr>
                        <tr><td>TC-005</td><td>Login</td><td>Invalid password handling</td><td><span class="badge badge-pass">PASS</span></td></tr>
                        <tr><td>TC-006</td><td>Search</td><td>Search with valid product name</td><td><span class="badge badge-fail">FAIL</span></td></tr>
                        <tr><td>TC-007</td><td>Search</td><td>Search with invalid/empty query</td><td><span class="badge badge-pass">PASS</span></td></tr>
                        <tr><td>TC-008</td><td>Cart</td><td>Add product to cart successfully</td><td><span class="badge badge-pass">PASS</span></td></tr>
                        <tr><td>TC-009</td><td>Password</td><td>Forgot password - email reset link</td><td><span class="badge badge-pass">PASS</span></td></tr>
                        <tr><td>TC-010</td><td>Cart</td><td>Update quantity in cart</td><td><span class="badge badge-pending">PENDING</span></td></tr>
                    </tbody>
                </table>
            </div>
        </div>

        <!-- Defects Section -->
        <div id="defects" class="content-section">
            <h2>🐛 Identified Defects</h2>
            <div class="test-table">
                <table>
                    <thead>
                        <tr><th>Defect ID</th><th>Module</th><th>Description</th><th>Severity</th><th>Status</th></tr>
                    </thead>
                    <tbody>
                        <tr><td>BUG-001</td><td>Search Bar</td><td>Search returns no results for valid keywords</td><td>🔴 Critical</td><td>Open</td></tr>
                        <tr><td>BUG-002</td><td>Signup</td><td>Password mismatch error not showing correctly</td><td>🟠 Major</td><td>In Progress</td></tr>
                        <tr><td>BUG-003</td><td>Login</td><td>Session timeout too short (5 minutes)</td><td>🟡 Minor</td><td>Open</td></tr>
                        <tr><td>BUG-004</td><td>Cart</td><td>Cart total doesn't update after removing items</td><td>🔴 Critical</td><td>Open</td></tr>
                        <tr><td>BUG-005</td><td>Mobile View</td><td>Navigation menu broken on iPhone</td><td>🟠 Major</td><td>Open</td></tr>
                    </tbody>
                </table>
            </div>
            <p style="margin-top: 20px;">📌 <strong>Note:</strong> Detailed defect reports with reproduction steps available in Jira screenshots (see Gallery tab).</p>
        </div>

        <!-- Gallery Section -->
        <div id="gallery" class="content-section">
            <h2>🖼️ Test Execution Screenshots</h2>
            <div class="gallery-grid">
                <div class="gallery-item" onclick="openModal('DARAZ-JIRA2.png')">
                    <img src="DARAZ-JIRA2.png" alt="Jira Dashboard">
                    <div class="gallery-caption">Jira Bug Tracking Dashboard</div>
                </div>
                <div class="gallery-item" onclick="openModal('Daraz-Add-tp-Cart-Happy_Case.png')">
                    <img src="Daraz-Add-tp-Cart-Happy_Case.png" alt="Add to Cart">
                    <div class="gallery-caption">Add to Cart - Happy Path</div>
                </div>
                <div class="gallery-item" onclick="openModal('Daraz-Jira.png')">
                    <img src="Daraz-Jira.png" alt="Jira Issues">
                    <div class="gallery-caption">Jira Issue Tracking</div>
                </div>
                <div class="gallery-item" onclick="openModal('Daraz-Login.png')">
                    <img src="Daraz-Login.png" alt="Login Screen">
                    <div class="gallery-caption">Login Functionality Test</div>
                </div>
                <div class="gallery-item" onclick="openModal('Daraz-Signup.png')">
                    <img src="Daraz-Signup.png" alt="Signup Success">
                    <div class="gallery-caption">Successful Registration</div>
                </div>
                <div class="gallery-item" onclick="openModal('Daraz-SignUp Err.png')">
                    <img src="Daraz-SignUp Err.png" alt="Signup Error">
                    <div class="gallery-caption">Signup Error Handling</div>
                </div>
                <div class="gallery-item" onclick="openModal('Forget-Password.png')">
                    <img src="Forget-Password.png" alt="Forgot Password">
                    <div class="gallery-caption">Password Reset Flow</div>
                </div>
                <div class="gallery-item" onclick="openModal('Search-Bar-Defect.png')">
                    <img src="Search-Bar-Defect.png" alt="Search Defect">
                    <div class="gallery-caption">Search Bar Defect</div>
                </div>
            </div>
        </div>

        <!-- Setup Section -->
        <div id="setup" class="content-section">
            <h2>🚀 How to Use This Repository</h2>
            
            <h3>📥 Clone the Repository</h3>
            <pre style="background: #f5f5f5; padding: 15px; border-radius: 10px; overflow-x: auto;">
git clone https://github.com/AimCodes-beep/Daraz_QA_project.git
cd Daraz_QA_project</pre>

            <h3>📊 Review Test Artifacts</h3>
            <ul>
                <li>Open <strong>Daraz_Test_Cases.xlsx</strong> to see complete test suite</li>
                <li>Browse <strong>Gallery</strong> tab for execution evidence</li>
                <li>Check Jira screenshots for defect details</li>
            </ul>

            <h3>🔄 Re-run Tests</h3>
            <ol>
                <li>Navigate to <a href="https://www.daraz.pk" target="_blank">Daraz Website</a></li>
                <li>Follow test cases from the Excel file</li>
                <li>Compare results with provided screenshots</li>
                <li>Report new findings in Jira (if applicable)</li>
            </ol>

            <h3>📝 Contribute</h3>
            <p>Want to add automation scripts or more test cases? Feel free to:</p>
            <ul>
                <li>Fork the repository</li>
                <li>Create a new branch</li>
                <li>Submit a Pull Request</li>
            </ul>
        </div>

        <!-- Footer -->
        <div class="footer">
            <p>Developed with ❤️ by <strong>Aiman Nisar</strong> | QA Engineer</p>
            <p>
                <a href="https://github.com/AimCodes-beep" class="github-link">GitHub Profile</a> | 
                <a href="https://github.com/AimCodes-beep/Daraz_QA_project" class="github-link">Repository Link</a>
            </p>
            <p style="font-size: 0.9em; margin-top: 10px;">© 2026 Daraz QA Project | All screenshots are for educational/portfolio purposes</p>
        </div>
    </div>

    <!-- Modal for Image Viewing -->
    <div id="imageModal" class="modal" onclick="closeModal()">
        <span class="close">&times;</span>
        <img class="modal-content" id="modalImage">
    </div>

    <script>
        function showTab(tabName) {
            // Hide all sections
            const sections = document.querySelectorAll('.content-section');
            sections.forEach(section => {
                section.classList.remove('active');
            });
            
            // Remove active class from all buttons
            const buttons = document.querySelectorAll('.tab-btn');
            buttons.forEach(btn => {
                btn.classList.remove('active');
            });
            
            // Show selected section
            document.getElementById(tabName).classList.add('active');
            
            // Add active class to clicked button
            event.target.classList.add('active');
        }
        
        function openModal(imgSrc) {
            const modal = document.getElementById('imageModal');
            const modalImg = document.getElementById('modalImage');
            modal.style.display = "block";
            modalImg.src = imgSrc;
        }
        
        function closeModal() {
            const modal = document.getElementById('imageModal');
            modal.style.display = "none";
        }
        
        // Close modal with Escape key
        document.addEventListener('keydown', function(event) {
            if (event.key === "Escape") {
                closeModal();
            }
        });
    </script>
</body>
</html>
