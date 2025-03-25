# Student-Manage
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Management System</title>
    <style>
        :root {
            --primary-color: #3498db;
            --secondary-color: #2ecc71;
            --accent-color: #e74c3c;
            --dark-color: #2c3e50;
            --light-color: #ecf0f1;
            --warning-color: #f39c12;
            --success-color: #27ae60;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 20px;
            background-color: #f5f7fa;
            color: #333;
            line-height: 1.6;
        }
        .container {
            max-width: 1000px;
            margin: auto;
            background: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        h1, h2, h3 {
            color: var(--dark-color);
        }
        h1 {
            text-align: center;
            color: var(--primary-color);
            margin-bottom: 30px;
            font-size: 2.5em;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.1);
        }
        h2 {
            border-bottom: 2px solid var(--primary-color);
            padding-bottom: 10px;
            margin-top: 30px;
            color: var(--dark-color);
        }
        h3 {
            color: var(--primary-color);
            margin-top: 20px;
        }
        .section {
            margin-bottom: 30px;
            padding: 25px;
            border: 1px solid #e0e0e0;
            border-radius: 8px;
            background: white;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
            transition: all 0.3s ease;
        }
        .section:hover {
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        input[type="text"], 
        input[type="number"], 
        input[type="email"], 
        input[type="tel"],
        input[type="file"], 
        textarea, 
        select {
            width: calc(100% - 24px);
            padding: 12px;
            margin: 8px 0 15px;
            border: 1px solid #ddd;
            border-radius: 6px;
            font-size: 16px;
            transition: border 0.3s;
        }
        input:focus, textarea:focus, select:focus {
            border-color: var(--primary-color);
            outline: none;
            box-shadow: 0 0 5px rgba(52, 152, 219, 0.3);
        }
        button {
            padding: 12px 20px;
            background-color: var(--primary-color);
            color: white;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            font-size: 16px;
            font-weight: 600;
            transition: all 0.3s;
            margin-top: 10px;
        }
        button:hover {
            background-color: #2980b9;
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        button.secondary {
            background-color: var(--secondary-color);
        }
        button.secondary:hover {
            background-color: #27ae60;
        }
        button.warning {
            background-color: var(--warning-color);
        }
        button.warning:hover {
            background-color: #e67e22;
        }
        img {
            margin-top: 15px;
            width: 120px;
            height: 120px;
            border-radius: 8px;
            border: 3px solid var(--light-color);
            object-fit: cover;
        }
        .result {
            color: var(--success-color);
            font-weight: bold;
        }
        .fail {
            color: var(--accent-color);
            font-weight: bold;
        }
        .warning {
            color: var(--warning-color);
            font-weight: bold;
        }
        .hidden {
            display: none;
        }
        .report-card {
            border: 1px solid var(--primary-color);
            padding: 25px;
            border-radius: 10px;
            background: linear-gradient(135deg, #f5f7fa 0%, #e4e8eb 100%);
            margin-top: 30px;
        }
        .subject {
            background-color: #f8f9fa;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 20px;
            border-left: 4px solid var(--primary-color);
        }
        .feedback {
            padding: 10px;
            background-color: #f8f9fa;
            border-radius: 5px;
            margin-top: 10px;
            font-size: 14px;
        }
        .grid-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-bottom: 20px;
        }
        .grid-item {
            background-color: #f8f9fa;
            padding: 15px;
            border-radius: 8px;
        }
        .progress-container {
            background-color: #e0e0e0;
            border-radius: 10px;
            margin: 15px 0;
            height: 20px;
        }
        .progress-bar {
            background-color: var(--secondary-color);
            border-radius: 10px;
            height: 100%;
            width: 0%;
            transition: width 1s ease-in-out;
        }
        .notification {
            padding: 15px;
            background-color: #e3f2fd;
            border-left: 5px solid var(--primary-color);
            margin: 10px 0;
            border-radius: 4px;
        }
        .activity-card {
            background-color: white;
            border: 1px solid #e0e0e0;
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
        }
        .activity-icon {
            font-size: 24px;
            margin-right: 15px;
            color: var(--primary-color);
        }
        .tab-container {
            display: flex;
            margin-bottom: 20px;
        }
        .tab {
            padding: 10px 20px;
            background-color: #f1f1f1;
            cursor: pointer;
            border-radius: 5px 5px 0 0;
            margin-right: 5px;
        }
        .tab.active {
            background-color: var(--primary-color);
            color: white;
        }
        .tab-content {
            display: none;
        }
        .tab-content.active {
            display: block;
        }
        .teacher-feedback {
            background-color: #f0f8ff;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 15px;
            border-left: 4px solid var(--primary-color);
        }
        .teacher-name {
            font-weight: bold;
            color: var(--dark-color);
        }
        .date {
            font-size: 12px;
            color: #7f8c8d;
        }
        .print-button {
            background-color: var(--dark-color);
            display: block;
            margin: 20px auto;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>Student Management System</h1>

    <div id="loginSection" class="section">
        <h2>Login</h2>
        <label>Enter USN:</label>
        <input type="text" id="usnInput" placeholder="e.g. USN001">
        <button id="loginButton">Login</button>
        <div id="errorMessage" style="color:var(--accent-color); display:none;"></div>
    </div>

    <div id="studentSection" class="section hidden">
        <h2>Student Details</h2>
        <div class="grid-container">
            <div class="grid-item">
                <p><strong>Name:</strong> <span id="studentName"></span></p>
                <p><strong>USN:</strong> <span id="studentUSN"></span></p>
                <p><strong>Date of Birth:</strong> <span id="dob"></span></p>
                <p><strong>Blood Group:</strong> <span id="bloodGroup"></span></p>
            </div>
            <div class="grid-item">
                <p><strong>Father's Name:</strong> <span id="fatherName"></span></p>
                <p><strong>Mother's Name:</strong> <span id="motherName"></span></p>
                <p><strong>Class/Grade:</strong> <span id="classGrade"></span></p>
                <p><strong>Section:</strong> <span id="section"></span></p>
            </div>
        </div>
        <p><strong>Photo:</strong></p>
        <img id="photoPreview" alt="Student Photo" style="display:none;">
        <button id="nextButton" class="secondary">Next</button>
    </div>

    <div id="contactInfoSection" class="section hidden">
        <h2>Parent/Guardian Contact Information</h2>
        <div class="grid-container">
            <div class="grid-item">
                <h3>Father's Contact</h3>
                <label>Phone Number:</label>
                <input type="tel" id="fatherPhone" placeholder="+91 XXXXXXXXXX">
                <label>Email:</label>
                <input type="email" id="fatherEmail" placeholder="father@example.com">
            </div>
            <div class="grid-item">
                <h3>Mother's Contact</h3>
                <label>Phone Number:</label>
                <input type="tel" id="motherPhone" placeholder="+91 XXXXXXXXXX">
                <label>Email:</label>
                <input type="email" id="motherEmail" placeholder="mother@example.com">
            </div>
            <div class="grid-item">
                <h3>Guardian's Contact (if applicable)</h3>
                <label>Name:</label>
                <input type="text" id="guardianName" placeholder="Guardian's Name">
                <label>Phone Number:</label>
                <input type="tel" id="guardianPhone" placeholder="+91 XXXXXXXXXX">
                <label>Relationship:</label>
                <input type="text" id="guardianRelation" placeholder="Relationship to student">
            </div>
        </div>
        <button id="saveContactInfo" class="secondary">Save Contact Information</button>
        <button id="nextToBehavior" class="secondary">Next</button>
    </div>

    <div id="behaviorSection" class="section hidden">
        <h2>Behavioral Feedback</h2>
        <label>Class Participation:</label>
        <select id="participationRating">
            <option value="excellent">Excellent - Always participates</option>
            <option value="good">Good - Participates often</option>
            <option value="average">Average - Participates sometimes</option>
            <option value="poor">Poor - Rarely participates</option>
        </select>
        
        <label>Behavior in Class:</label>
        <select id="behaviorRating">
            <option value="excellent">Excellent - Always respectful</option>
            <option value="good">Good - Usually respectful</option>
            <option value="average">Average - Occasionally disruptive</option>
            <option value="poor">Poor - Often disruptive</option>
        </select>
        
        <label>Additional Comments:</label>
        <textarea id="behaviorComments" rows="4" placeholder="Enter any additional behavioral comments..."></textarea>
        
        <button id="saveBehaviorInfo" class="secondary">Save Behavioral Feedback</button>
        <button id="nextToGoals" class="secondary">Next</button>
    </div>

    <div id="goalsSection" class="section hidden">
        <h2>Goal Setting</h2>
        <div id="goalsContainer">
            <div class="goal-item">
                <label>Goal Title:</label>
                <input type="text" class="goal-title" placeholder="e.g. Improve Math scores">
                <label>Goal Description:</label>
                <textarea class="goal-description" rows="2" placeholder="Describe your goal..."></textarea>
                <label>Target Date:</label>
                <input type="date" class="goal-date">
                <label>Progress:</label>
                <div class="progress-container">
                    <div class="progress-bar" style="width: 0%"></div>
                </div>
                <input type="range" class="goal-progress" min="0" max="100" value="0">
                <button class="remove-goal warning">Remove Goal</button>
            </div>
        </div>
        <button id="addGoal" class="secondary">Add Another Goal</button>
        <button id="saveGoals" class="secondary">Save Goals</button>
        <button id="nextToPerformance" class="secondary">Next</button>
    </div>

    <div id="subjectPerformance" class="section hidden">
        <h2>Subject Performance</h2>
        
        <div class="tab-container">
            <div class="tab active" data-tab="current">Current Term</div>
            <div class="tab" data-tab="previous">Previous Terms</div>
            <div class="tab" data-tab="comparison">Progress Comparison</div>
        </div>
        
        <div class="tab-content active" id="current-term">
            <div class="subject">
                <h3>Mathematics</h3>
                <label>Internal Marks (out of 50):</label>
                <input type="number" class="internalMarks" data-subject="Mathematics">
                <label>Exam Marks (out of 100):</label>
                <input type="number" class="examMarks" data-subject="Mathematics">
                <label>Attendance (%):</label>
                <input type="number" class="attendance" data-subject="Mathematics">
                <div class="feedback"></div>
            </div>
            <div class="subject">
                <h3>Chemistry</h3>
                <label>Internal Marks (out of 50):</label>
                <input type="number" class="internalMarks" data-subject="Chemistry">
                <label>Exam Marks (out of 100):</label>
                <input type="number" class="examMarks" data-subject="Chemistry">
                <label>Attendance (%):</label>
                <input type="number" class="attendance" data-subject="Chemistry">
                <div class="feedback"></div>
            </div>
            <div class="subject">
                <h3>Biology</h3>
                <label>Internal Marks (out of 50):</label>
                <input type="number" class="internalMarks" data-subject="Biology">
                <label>Exam Marks (out of 100):</label>
                <input type="number" class="examMarks" data-subject="Biology">
                <label>Attendance (%):</label>
                <input type="number" class="attendance" data-subject="Biology">
                <div class="feedback"></div>
            </div>
            <div class="subject">
                <h3>Physics</h3>
                <label>Internal Marks (out of 50):</label>
                <input type="number" class="internalMarks" data-subject="Physics">
                <label>Exam Marks (out of 100):</label>
                <input type="number" class="examMarks" data-subject="Physics">
                <label>Attendance (%):</label>
                <input type="number" class="attendance" data-subject="Physics">
                <div class="feedback"></div>
            </div>
            <div class="subject">
                <h3>English</h3>
                <label>Internal Marks (out of 50):</label>
                <input type="number" class="internalMarks" data-subject="English">
                <label>Exam Marks (out of 100):</label>
                <input type="number" class="examMarks" data-subject="English">
                <label>Attendance (%):</label>
                <input type="number" class="attendance" data-subject="English">
                <div class="feedback"></div>
            </div>
            <button id="calculatePerformance" class="secondary">Calculate Performance</button>
        </div>
        
        <div class="tab-content" id="previous-terms">
            <h3>Previous Term Results</h3>
            <div id="previousResults">
                <p>No previous term data available yet.</p>
            </div>
        </div>
        
        <div class="tab-content" id="progress-comparison">
            <h3>Progress Comparison</h3>
            <div id="progressChart">
                <p>Progress comparison chart will appear here after multiple terms of data are available.</p>
            </div>
        </div>
    </div>

    <div id="overallPerformance" class="section hidden">
        <h2>Overall Performance</h2>
        <div id="results"></div>
        <div id="overallStatus"></div>
        
        <h3>Teacher Feedback</h3>
        <div id="teacherFeedbackContainer">
            <div class="teacher-feedback">
                <div class="teacher-name">Ms. Math Teacher</div>
                <div class="date">March 15, 2023</div>
                <p>John has shown great improvement in algebra this term. Needs to work on geometry proofs.</p>
            </div>
            <div class="teacher-feedback">
                <div class="teacher-name">Mr. Science Teacher</div>
                <div class="date">March 10, 2023</div>
                <p>Excellent participation in lab experiments. Should focus more on theoretical concepts.</p>
            </div>
        </div>
        
        <label>Add New Teacher Feedback:</label>
        <textarea id="newTeacherFeedback" rows="3" placeholder="Enter your feedback..."></textarea>
        <button id="addTeacherFeedback" class="secondary">Add Feedback</button>
        
        <button id="nextToActivities" class="secondary">Next to Activities</button>
    </div>

    <div id="activitiesSection" class="section hidden">
        <h2>Extra-Curricular Activities</h2>
        
        <h3>Current Activities</h3>
        <div id="currentActivities">
            <div class="activity-card">
                <div class="activity-icon">⚽</div>
                <div>
                    <strong>Football Team</strong>
                    <p>Member of school football team. Practice every Monday and Wednesday.</p>
                </div>
            </div>
            <div class="activity-card">
                <div class="activity-icon">🎭</div>
                <div>
                    <strong>Drama Club</strong>
                    <p>Participating in school play as lead role. Rehearsals on Fridays.</p>
                </div>
            </div>
        </div>
        
        <h3>Add New Activity</h3>
        <label>Activity Type:</label>
        <select id="activityType">
            <option value="sports">Sports</option>
            <option value="arts">Arts</option>
            <option value="academic">Academic Club</option>
            <option value="volunteer">Volunteer Work</option>
            <option value="other">Other</option>
        </select>
        
        <label>Activity Name:</label>
        <input type="text" id="activityName" placeholder="e.g. Basketball Team">
        
        <label>Description:</label>
        <textarea id="activityDescription" rows="3" placeholder="Describe the activity..."></textarea>
        
        <label>Time Commitment:</label>
        <input type="text" id="activityTime" placeholder="e.g. 2 hours/week">
        
        <button id="addActivity" class="secondary">Add Activity</button>
        
        <h3>Scholarship Information</h3>
        <div id="scholarshipInfo">
            <p><strong>Merit Scholarship</strong> - Awarded for academic excellence, 2022-2023</p>
            <p><strong>Sports Scholarship</strong> - Awarded for state-level football performance, 2023</p>
        </div>
        
        <label>Add New Scholarship/Award:</label>
        <input type="text" id="newScholarshipName" placeholder="Scholarship/Award Name">
        <textarea id="newScholarshipDetails" rows="2" placeholder="Details about the scholarship/award..."></textarea>
        <button id="addScholarship" class="secondary">Add Scholarship</button>
        
        <button id="nextToReminders" class="secondary">Next to Reminders</button>
    </div>

    <div id="remindersSection" class="section hidden">
        <h2>Reminders & Notifications</h2>
        
        <h3>Upcoming Events</h3>
        <div class="notification">
            <strong>Math Final Exam</strong> - May 15, 2023
        </div>
        <div class="notification">
            <strong>Science Project Deadline</strong> - May 20, 2023
        </div>
        <div class="notification">
            <strong>Parent-Teacher Meeting</strong> - May 25, 2023
        </div>
        
        <h3>Add New Reminder</h3>
        <label>Reminder Title:</label>
        <input type="text" id="reminderTitle" placeholder="e.g. Submit English Essay">
        
        <label>Date:</label>
        <input type="date" id="reminderDate">
        
        <label>Details:</label>
        <textarea id="reminderDetails" rows="2" placeholder="Additional details..."></textarea>
        
        <button id="addReminder" class="secondary">Add Reminder</button>
        
        <button id="generateReport" class="secondary">Generate Report Card</button>
    </div>

    <div id="reportCard" class="report-card hidden">
        <h2>Student Report Card</h2>
        <div id="reportCardDetails"></div>
        <button id="printReport" class="print-button">Print Report Card</button>
    </div>
</div>

<script>
    // Enhanced student data with more fields
    const students = {
        "USN001": { 
            name: "John Doe", 
            usn: "USN001",
            father: "Michael Doe", 
            mother: "Sarah Doe", 
            bloodGroup: "A+", 
            photo: "https://randomuser.me/api/portraits/men/1.jpg",
            dob: "2005-03-15",
            classGrade: "10",
            section: "A",
            fatherPhone: "+919876543210",
            fatherEmail: "michael.doe@example.com",
            motherPhone: "+919876543211",
            motherEmail: "sarah.doe@example.com"
        },
        "USN002": { 
            name: "Jane Smith", 
            usn: "USN002",
            father: "James Smith", 
            mother: "Laura Smith", 
            bloodGroup: "B+", 
            photo: "https://randomuser.me/api/portraits/women/2.jpg",
            dob: "2005-05-20",
            classGrade: "10",
            section: "B",
            fatherPhone: "+919876543212",
            fatherEmail: "james.smith@example.com",
            motherPhone: "+919876543213",
            motherEmail: "laura.smith@example.com"
        },
        "USN003": { 
            name: "Alice Johnson", 
            usn: "USN003",
            father: "Robert Johnson", 
            mother: "Linda Johnson", 
            bloodGroup: "O-", 
            photo: "https://randomuser.me/api/portraits/women/3.jpg",
            dob: "2005-07-10",
            classGrade: "9",
            section: "A",
            fatherPhone: "+919876543214",
            fatherEmail: "robert.johnson@example.com",
            motherPhone: "+919876543215",
            motherEmail: "linda.johnson@example.com"
        }
    };

    // Login functionality
    document.getElementById('loginButton').addEventListener('click', function() {
        const usn = document.getElementById('usnInput').value.toUpperCase();
        const student = students[usn];

        if (student) {
            // Basic student info
            document.getElementById('studentName').textContent = student.name;
            document.getElementById('studentUSN').textContent = student.usn;
            document.getElementById('fatherName').textContent = student.father;
            document.getElementById('motherName').textContent = student.mother;
            document.getElementById('bloodGroup').textContent = student.bloodGroup;
            document.getElementById('photoPreview').src = student.photo;
            document.getElementById('photoPreview').style.display = 'block';
            document.getElementById('dob').textContent = student.dob;
            document.getElementById('classGrade').textContent = student.classGrade;
            document.getElementById('section').textContent = student.section;
            
            // Contact info
            document.getElementById('fatherPhone').value = student.fatherPhone || '';
            document.getElementById('fatherEmail').value = student.fatherEmail || '';
            document.getElementById('motherPhone').value = student.motherPhone || '';
            document.getElementById('motherEmail').value = student.motherEmail || '';

            document.getElementById('loginSection').classList.add('hidden');
            document.getElementById('studentSection').classList.remove('hidden');
        } else {
            document.getElementById('errorMessage').textContent = "Student not found! Please check your USN.";
            document.getElementById('errorMessage').style.display = 'block';
        }
    });

    // Navigation between sections
    document.getElementById('nextButton').addEventListener('click', function() {
        document.getElementById('studentSection').classList.add('hidden');
        document.getElementById('contactInfoSection').classList.remove('hidden');
    });

    document.getElementById('nextToBehavior').addEventListener('click', function() {
        document.getElementById('contactInfoSection').classList.add('hidden');
        document.getElementById('behaviorSection').classList.remove('hidden');
    });

    document.getElementById('nextToGoals').addEventListener('click', function() {
        document.getElementById('behaviorSection').classList.add('hidden');
        document.getElementById('goalsSection').classList.remove('hidden');
    });

    document.getElementById('nextToPerformance').addEventListener('click', function() {
        document.getElementById('goalsSection').classList.add('hidden');
        document.getElementById('subjectPerformance').classList.remove('hidden');
    });

    document.getElementById('nextToActivities').addEventListener('click', function() {
        document.getElementById('overallPerformance').classList.add('hidden');
        document.getElementById('activitiesSection').classList.remove('hidden');
    });

    document.getElementById('nextToReminders').addEventListener('click', function() {
        document.getElementById('activitiesSection').classList.add('hidden');
        document.getElementById('remindersSection').classList.remove('hidden');
    });

    // Tab functionality for performance section
    document.querySelectorAll('.tab').forEach(tab => {
        tab.addEventListener('click', function() {
            // Remove active class from all tabs and contents
            document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
            document.querySelectorAll('.tab-content').forEach(c => c.classList.remove('active'));
            
            // Add active class to clicked tab and corresponding content
            this.classList.add('active');
            const tabId = this.getAttribute('data-tab');
            document.getElementById(tabId === 'current' ? 'current-term' : 
                                  tabId === 'previous' ? 'previous-terms' : 'progress-comparison').classList.add('active');
        });
    });

    // Goal management
    document.getElementById('addGoal').addEventListener('click', function() {
        const goalItem = document.createElement('div');
        goalItem.className = 'goal-item';
        goalItem.innerHTML = `
            <label>Goal Title:</label>
            <input type="text" class="goal-title" placeholder="e.g. Improve Math scores">
            <label>Goal Description:</label>
            <textarea class="goal-description" rows="2" placeholder="Describe your goal..."></textarea>
            <label>Target Date:</label>
            <input type="date" class="goal-date">
            <label>Progress:</label>
            <div class="progress-container">
                <div class="progress-bar" style="width: 0%"></div>
            </div>
            <input type="range" class="goal-progress" min="0" max="100" value="0">
            <button class="remove-goal warning">Remove Goal</button>
        `;
        document.getElementById('goalsContainer').appendChild(goalItem);
        
        // Add event listener for the progress slider
        goalItem.querySelector('.goal-progress').addEventListener('input', function() {
            const progress = this.value;
            this.previousElementSibling.querySelector('.progress-bar').style.width = progress + '%';
        });
        
        // Add event listener for remove button
        goalItem.querySelector('.remove-goal').addEventListener('click', function() {
            goalItem.remove();
        });
    });

    // Calculate performance
    document.getElementById('calculatePerformance').addEventListener('click', function() {
        const subjects = document.querySelectorAll('.subject');
        let overallResults = '';
        let attendanceWarning = false;
        let failWarning = false;

        subjects.forEach(subject => {
            const subjectName = subject.querySelector('h3').innerText;
            const internalMarks = parseInt(subject.querySelector('.internalMarks').value) || 0;
            const examMarks = parseInt(subject.querySelector('.examMarks').value) || 0;
            const attendance = parseInt(subject.querySelector('.attendance').value) || 0;
            const feedbackDiv = subject.querySelector('.feedback');
            
            // Calculate total marks (internal + exam converted to 50)
            const totalMarks = internalMarks + (examMarks / 2);
            const percentage = (totalMarks / 100) * 100;
            
            // Feedback for Internal Marks
            let feedback = '';
            if (internalMarks < 20) {
                feedback = 'Internal Marks: <span class="fail">Needs significant improvement</span>';
            } else if (internalMarks < 40) {
                feedback = 'Internal Marks: <span class="warning">Needs improvement</span>';
            } else {
                feedback = 'Internal Marks: <span class="result">Excellent</span>';
            }

            // Feedback for Exam Marks
            if (examMarks < 35) {
                feedback += '<br>Exam Marks: <span class="fail">Failed - Needs remedial classes</span>';
                failWarning = true;
            } else if (examMarks < 60) {
                feedback += '<br>Exam Marks: <span class="warning">Passed but needs improvement</span>';
            } else if (examMarks < 90) {
                feedback += '<br>Exam Marks: <span class="result">Good performance</span>';
            } else {
                feedback += '<br>Exam Marks: <span class="result">Outstanding performance</span>';
            }

            // Attendance Warning
            if (attendance < 75) {
                feedback += '<br><span class="warning">Warning: Attendance is below 75%</span>';
                attendanceWarning = true;
            } else if (attendance < 90) {
                feedback += '<br><span class="result">Attendance: Satisfactory</span>';
            } else {
                feedback += '<br><span class="result">Attendance: Excellent</span>';
            }
            
            // Overall subject status
            if (percentage < 40) {
                feedback += '<br><strong>Overall: <span class="fail">Fail</span></strong>';
            } else if (percentage < 60) {
                feedback += '<br><strong>Overall: <span class="warning">Pass</span></strong>';
            } else if (percentage < 80) {
                feedback += '<br><strong>Overall: <span class="result">Good</span></strong>';
            } else {
                feedback += '<br><strong>Overall: <span class="result">Excellent</span></strong>';
            }

            feedbackDiv.innerHTML = feedback;
            
            overallResults += `
                <div class="subject">
                    <h3>${subjectName}</h3>
                    <p>Internal: ${internalMarks}/50 | Exam: ${examMarks}/100 | Total: ${totalMarks.toFixed(1)}/100 (${percentage.toFixed(1)}%)</p>
                    <p>Attendance: ${attendance}%</p>
                </div>
            `;
        });

        document.getElementById('results').innerHTML = overallResults;
        document.getElementById('overallPerformance').classList.remove('hidden');

        let overallStatus = '';
        if (failWarning) {
            overallStatus = '<div class="fail"><h3>Overall Status: Warning</h3><p>Student has failed in one or more subjects. Remedial action required.</p></div>';
        } else if (attendanceWarning) {
            overallStatus = '<div class="warning"><h3>Overall Status: Satisfactory with Concerns</h3><p>Attendance is below 75% in one or more subjects.</p></div>';
        } else {
            overallStatus = '<div class="result"><h3>Overall Status: Good</h3><p>Student is performing well in all subjects.</p></div>';
        }
        
        document.getElementById('overallStatus').innerHTML = overallStatus;
    });

    // Teacher feedback
    document.getElementById('addTeacherFeedback').addEventListener('click', function() {
        const feedback = document.getElementById('newTeacherFeedback').value;
        if (feedback.trim() === '') return;
        
        const feedbackDiv = document.createElement('div');
        feedbackDiv.className = 'teacher-feedback';
        feedbackDiv.innerHTML = `
            <div class="teacher-name">Teacher</div>
            <div class="date">${new Date().toLocaleDateString()}</div>
            <p>${feedback}</p>
        `;
        
        document.getElementById('teacherFeedbackContainer').prepend(feedbackDiv);
        document.getElementById('newTeacherFeedback').value = '';
    });

    // Activities management
    document.getElementById('addActivity').addEventListener('click', function() {
        const type = document.getElementById('activityType').value;
        const name = document.getElementById('activityName').value;
        const description = document.getElementById('activityDescription').value;
        const time = document.getElementById('activityTime').value;
        
        if (!name.trim()) return;
        
        const icons = {
            'sports': '⚽',
            'arts': '🎨',
            'academic': '📚',
            'volunteer': '🤝',
            'other': '🌟'
        };
        
        const activityCard = document.createElement('div');
        activityCard.className = 'activity-card';
        activityCard.innerHTML = `
            <div class="activity-icon">${icons[type]}</div>
            <div>
                <strong>${name}</strong>
                <p>${description || 'No description provided'}</p>
                ${time ? `<small>Time: ${time}</small>` : ''}
            </div>
        `;
        
        document.getElementById('currentActivities').appendChild(activityCard);
        
        // Clear form
        document.getElementById('activityName').value = '';
        document.getElementById('activityDescription').value = '';
        document.getElementById('activityTime').value = '';
    });

    // Scholarship management
    document.getElementById('addScholarship').addEventListener('click', function() {
        const name = document.getElementById('newScholarshipName').value;
        const details = document.getElementById('newScholarshipDetails').value;
        
        if (!name.trim()) return;
        
        const scholarshipItem = document.createElement('p');
        scholarshipItem.innerHTML = `<strong>${name}</strong> - ${details || 'No details provided'}`;
        document.getElementById('scholarshipInfo').appendChild(scholarshipItem);
        
        // Clear form
        document.getElementById('newScholarshipName').value = '';
        document.getElementById('newScholarshipDetails').value = '';
    });

    // Reminders management
    document.getElementById('addReminder').addEventListener('click', function() {
        const title = document.getElementById('reminderTitle').value;
        const date = document.getElementById('reminderDate').value;
        const details = document.getElementById('reminderDetails').value;
        
        if (!title.trim() || !date) return;
        
        const reminderDiv = document.createElement('div');
        reminderDiv.className = 'notification';
        reminderDiv.innerHTML = `
            <strong>${title}</strong> - ${new Date(date).toLocaleDateString()}
            ${details ? `<p>${details}</p>` : ''}
        `;
        
        document.querySelector('#remindersSection .notification:last-of-type').after(reminderDiv);
        
        // Clear form
        document.getElementById('reminderTitle').value = '';
        document.getElementById('reminderDate').value = '';
        document.getElementById('reminderDetails').value = '';
    });

    // Generate report card
    document.getElementById('generateReport').addEventListener('click', function() {
        const reportCardDetails = `
            <div class="grid-container">
                <div class="grid-item">
                    <h3>Student Information</h3>
                    <p><strong>Name:</strong> ${document.getElementById('studentName').textContent}</p>
                    <p><strong>USN:</strong> ${document.getElementById('studentUSN').textContent}</p>
                    <p><strong>Class:</strong> ${document.getElementById('classGrade').textContent} ${document.getElementById('section').textContent}</p>
                    <p><strong>Blood Group:</strong> ${document.getElementById('bloodGroup').textContent}</p>
                    <img src="${document.getElementById('photoPreview').src}" alt="Student Photo" style="width:120px;height:120px;">
                </div>
                <div class="grid-item">
                    <h3>Parent Information</h3>
                    <p><strong>Father:</strong> ${document.getElementById('fatherName').textContent}</p>
                    <p><strong>Phone:</strong> ${document.getElementById('fatherPhone').value || 'N/A'}</p>
                    <p><strong>Mother:</strong> ${document.getElementById('motherName').textContent}</p>
                    <p><strong>Phone:</strong> ${document.getElementById('motherPhone').value || 'N/A'}</p>
                </div>
            </div>
            
            <h3>Academic Performance</h3>
            ${document.getElementById('results').innerHTML}
            
            <h3>Overall Status</h3>
            ${document.getElementById('overallStatus').innerHTML}
            
            <h3>Teacher Feedback</h3>
            ${document.getElementById('teacherFeedbackContainer').innerHTML}
            
            <h3>Activities & Achievements</h3>
            <div class="grid-container">
                <div class="grid-item">
                    <h4>Extra-Curricular Activities</h4>
                    ${document.getElementById('currentActivities').innerHTML}
                </div>
                <div class="grid-item">
                    <h4>Scholarships & Awards</h4>
                    ${document.getElementById('scholarshipInfo').innerHTML}
                </div>
            </div>
            
            <h3>Behavioral Feedback</h3>
            <p><strong>Class Participation:</strong> ${document.getElementById('participationRating').options[document.getElementById('participationRating').selectedIndex].text}</p>
            <p><strong>Behavior in Class:</strong> ${document.getElementById('behaviorRating').options[document.getElementById('behaviorRating').selectedIndex].text}</p>
            <p><strong>Additional Comments:</strong> ${document.getElementById('behaviorComments').value || 'None'}</p>
            
            <h3>Goals</h3>
            ${document.getElementById('goalsContainer').innerHTML}
            
            <h3>Upcoming Reminders</h3>
            ${document.querySelector('#remindersSection').querySelectorAll('.notification').length > 0 ? 
              document.querySelector('#remindersSection').innerHTML : '<p>No upcoming reminders</p>'}
        `;
        
        document.getElementById('reportCardDetails').innerHTML = reportCardDetails;
        document.getElementById('reportCard').classList.remove('hidden');
        
        // Scroll to report card
        document.getElementById('reportCard').scrollIntoView({ behavior: 'smooth' });
    });

    // Print report card
    document.getElementById('printReport').addEventListener('click', function() {
        const printContents = document.getElementById('reportCard').innerHTML;
        const originalContents = document.body.innerHTML;
        
        document.body.innerHTML = `
            <style>
                body { font-family: Arial; padding: 20px; }
                h1, h2, h3 { color: #333; }
                .result { color: green; }
                .fail { color: red; }
                .warning { color: orange; }
                .grid-container { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
                img { width: 120px; height: 120px; border-radius: 8px; }
                .subject, .teacher-feedback, .activity-card { 
                    border: 1px solid #ddd; 
                    padding: 10px; 
                    margin-bottom: 10px; 
                    border-radius: 5px; 
                }
                @page { size: auto; margin: 10mm; }
            </style>
            ${printContents}
        `;
        
        window.print();
        document.body.innerHTML = originalContents;
        window.location.reload();
    });

    // Initialize goal progress sliders
    document.querySelectorAll('.goal-progress').forEach(slider => {
        slider.addEventListener('input', function() {
            this.previousElementSibling.querySelector('.progress-bar').style.width = this.value + '%';
        });
    });

    // Initialize tab functionality
    document.querySelectorAll('.tab').forEach(tab => {
        tab.addEventListener('click', function() {
            document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
            document.querySelectorAll('.tab-content').forEach(c => c.classList.remove('active'));
            
            this.classList.add('active');
            const tabId = this.getAttribute('data-tab');
            document.getElementById(tabId === 'current' ? 'current-term' : 
                                  tabId === 'previous' ? 'previous-terms' : 'progress-comparison').classList.add('active');
        });
    });
</script>

</body>
</html>
