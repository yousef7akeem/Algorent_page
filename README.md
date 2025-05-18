<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Algorent | Rental Platform</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css">
    <style>
        :root {
            --primary: #4361ee;
            --secondary: #3f37c9;
            --accent: #4895ef;
            --light: #f8f9fa;
            --dark: #212529;
            --success: #4cc9f0;
            --danger: #f72585;
            --warning: #f8961e;
            --info: #560bad;
            --white: #ffffff;
            --gray: #6c757d;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            min-height: 100vh;
            color: var(--dark);
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }

        /* Card styling */
        .card {
            background: var(--white);
            border-radius: 16px;
            box-shadow: 0 8px 32px rgba(31, 38, 135, 0.15);
            backdrop-filter: blur(4px);
            -webkit-backdrop-filter: blur(4px);
            border: 1px solid rgba(255, 255, 255, 0.18);
            padding: 2rem;
            margin-bottom: 2rem;
            transition: all 0.3s ease;
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 40px rgba(31, 38, 135, 0.2);
        }

        /* Header styling */
        .header {
            text-align: center;
            margin-bottom: 2rem;
        }

        .header h1 {
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 0.5rem;
            background: linear-gradient(to right, #4361ee, #3f37c9, #4895ef);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .header p {
            color: var(--gray);
            font-size: 1.1rem;
        }

        /* Form styling */
        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
            color: var(--dark);
        }

        .form-control {
            width: 100%;
            padding: 0.75rem 1rem;
            font-size: 1rem;
            line-height: 1.5;
            color: var(--dark);
            background-color: var(--white);
            background-clip: padding-box;
            border: 1px solid #ced4da;
            border-radius: 8px;
            transition: border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
        }

        .form-control:focus {
            border-color: var(--accent);
            outline: 0;
            box-shadow: 0 0 0 0.2rem rgba(72, 149, 239, 0.25);
        }

        select.form-control {
            appearance: none;
            background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill='none' stroke='%23343a40' stroke-linecap='round' stroke-linejoin='round' stroke-width='2' d='M2 5l6 6 6-6'/%3e%3c/svg%3e");
            background-repeat: no-repeat;
            background-position: right 0.75rem center;
            background-size: 16px 12px;
        }

        /* Button styling */
        .btn {
            display: inline-block;
            font-weight: 500;
            text-align: center;
            white-space: nowrap;
            vertical-align: middle;
            user-select: none;
            border: 1px solid transparent;
            padding: 0.75rem 1.5rem;
            font-size: 1rem;
            line-height: 1.5;
            border-radius: 8px;
            transition: all 0.3s ease;
            cursor: pointer;
            margin-right: 0.5rem;
            margin-bottom: 0.5rem;
        }

        .btn-primary {
            color: var(--white);
            background-color: var(--primary);
            border-color: var(--primary);
        }

        .btn-primary:hover {
            background-color: var(--secondary);
            border-color: var(--secondary);
            transform: translateY(-2px);
        }

        .btn-secondary {
            color: var(--white);
            background-color: var(--gray);
            border-color: var(--gray);
        }

        .btn-secondary:hover {
            background-color: #5a6268;
            border-color: #545b62;
            transform: translateY(-2px);
        }

        .btn-danger {
            color: var(--white);
            background-color: var(--danger);
            border-color: var(--danger);
        }

        .btn-danger:hover {
            background-color: #e1176e;
            border-color: #d91668;
            transform: translateY(-2px);
        }

        .btn-success {
            color: var(--white);
            background-color: var(--success);
            border-color: var(--success);
        }

        .btn-success:hover {
            background-color: #3ab4d9;
            border-color: #34a9cc;
            transform: translateY(-2px);
        }

        /* File upload styling */
        .file-upload {
            position: relative;
            overflow: hidden;
            display: inline-block;
            width: 100%;
        }

        .file-upload-input {
            position: absolute;
            left: 0;
            top: 0;
            opacity: 0;
            width: 100%;
            height: 100%;
            cursor: pointer;
        }

        .file-upload-label {
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 1rem;
            border: 2px dashed #ced4da;
            border-radius: 8px;
            background-color: #f8f9fa;
            color: var(--gray);
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .file-upload-label:hover {
            border-color: var(--accent);
            background-color: rgba(72, 149, 239, 0.05);
        }

        .file-upload-label i {
            margin-right: 0.5rem;
            font-size: 1.25rem;
            color: var(--primary);
        }

        /* Image preview styling */
        .image-preview {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-top: 1rem;
        }

        .preview-image {
            position: relative;
            width: 100px;
            height: 100px;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }

        .preview-image:hover {
            transform: scale(1.05);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
        }

        .preview-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .preview-image .remove-image {
            position: absolute;
            top: 0.25rem;
            right: 0.25rem;
            background-color: var(--danger);
            color: white;
            width: 20px;
            height: 20px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.75rem;
            cursor: pointer;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .preview-image:hover .remove-image {
            opacity: 1;
        }

        /* Table styling */
        .table-responsive {
            overflow-x: auto;
        }

        .table {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: 1rem;
            background-color: transparent;
        }

        .table th,
        .table td {
            padding: 1rem;
            vertical-align: top;
            border-top: 1px solid #dee2e6;
        }

        .table thead th {
            vertical-align: bottom;
            border-bottom: 2px solid #dee2e6;
            background-color: rgba(67, 97, 238, 0.1);
            color: var(--primary);
            font-weight: 600;
        }

        .table tbody tr {
            transition: all 0.3s ease;
        }

        .table tbody tr:hover {
            background-color: rgba(67, 97, 238, 0.05);
            transform: translateX(5px);
        }

        .table tbody tr:nth-child(even) {
            background-color: rgba(248, 249, 250, 0.5);
        }

        .table tbody tr:nth-child(even):hover {
            background-color: rgba(67, 97, 238, 0.05);
        }

        /* Badge styling */
        .badge {
            display: inline-block;
            padding: 0.35em 0.65em;
            font-size: 0.75em;
            font-weight: 700;
            line-height: 1;
            text-align: center;
            white-space: nowrap;
            vertical-align: baseline;
            border-radius: 10rem;
            transition: all 0.3s ease;
        }

        .badge-primary {
            color: var(--white);
            background-color: var(--primary);
        }

        .badge-success {
            color: var(--white);
            background-color: var(--success);
        }

        .badge-warning {
            color: var(--dark);
            background-color: var(--warning);
        }

        .badge-danger {
            color: var(--white);
            background-color: var(--danger);
        }

        /* Link styling */
        .link {
            color: var(--primary);
            text-decoration: none;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .link:hover {
            color: var(--secondary);
            text-decoration: underline;
        }

        /* Modal styling */
        .modal {
            display: none;
            position: fixed;
            z-index: 1050;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            outline: 0;
            background-color: rgba(0, 0, 0, 0.5);
            animation: fadeIn 0.3s ease;
        }

        .modal-dialog {
            position: relative;
            width: auto;
            margin: 1.75rem auto;
            max-width: 800px;
            pointer-events: none;
            animation: slideInDown 0.3s ease;
        }

        .modal-content {
            position: relative;
            display: flex;
            flex-direction: column;
            width: 100%;
            pointer-events: auto;
            background-color: var(--white);
            background-clip: padding-box;
            border: none;
            border-radius: 16px;
            outline: 0;
            box-shadow: 0 12px 40px rgba(31, 38, 135, 0.2);
        }

        .modal-header {
            display: flex;
            align-items: flex-start;
            justify-content: space-between;
            padding: 1.5rem;
            border-bottom: 1px solid #dee2e6;
            border-top-left-radius: 16px;
            border-top-right-radius: 16px;
            background-color: rgba(67, 97, 238, 0.05);
        }

        .modal-title {
            margin-bottom: 0;
            line-height: 1.5;
            font-size: 1.5rem;
            font-weight: 600;
            color: var(--primary);
        }

        .modal-body {
            position: relative;
            flex: 1 1 auto;
            padding: 1.5rem;
        }

        .modal-footer {
            display: flex;
            align-items: center;
            justify-content: flex-end;
            padding: 1.5rem;
            border-top: 1px solid #dee2e6;
            border-bottom-right-radius: 16px;
            border-bottom-left-radius: 16px;
        }

        .close {
            float: right;
            font-size: 1.5rem;
            font-weight: 700;
            line-height: 1;
            color: #000;
            text-shadow: 0 1px 0 var(--white);
            opacity: 0.5;
            background: none;
            border: none;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .close:hover {
            opacity: 1;
            transform: rotate(90deg);
        }

        /* Image gallery styling */
        .image-gallery {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 1.5rem;
            margin-top: 1.5rem;
        }

        .gallery-item {
            position: relative;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }

        .gallery-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 15px rgba(0, 0, 0, 0.15);
        }

        .gallery-item img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .gallery-caption {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            padding: 0.5rem;
            background-color: rgba(0, 0, 0, 0.7);
            color: var(--white);
            font-size: 0.875rem;
            text-align: center;
        }

        /* Utility classes */
        .text-center {
            text-align: center;
        }

        .text-right {
            text-align: right;
        }

        .text-primary {
            color: var(--primary);
        }

        .mb-3 {
            margin-bottom: 1rem;
        }

        .mb-4 {
            margin-bottom: 1.5rem;
        }

        .mt-3 {
            margin-top: 1rem;
        }

        .mt-4 {
            margin-top: 1.5rem;
        }

        .hidden {
            display: none;
        }

        .fade-in {
            animation: fadeIn 0.5s ease;
        }

        .slide-in {
            animation: slideInRight 0.5s ease;
        }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes slideInDown {
            from {
                transform: translateY(-50px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        @keyframes slideInRight {
            from {
                transform: translateX(50px);
                opacity: 0;
            }
            to {
                transform: translateX(0);
                opacity: 1;
            }
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        .pulse {
            animation: pulse 2s infinite;
        }

        /* Responsive adjustments */
        @media (max-width: 768px) {
            .container {
                padding: 1rem;
            }
            
            .card {
                padding: 1.5rem;
            }
            
            .header h1 {
                font-size: 2rem;
            }
            
            .btn {
                padding: 0.5rem 1rem;
                font-size: 0.875rem;
            }
            
            .table th,
            .table td {
                padding: 0.75rem;
            }
            
            .image-gallery {
                grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            }
            
            .gallery-item img {
                height: 150px;
            }
        }

        @media (max-width: 576px) {
            .header h1 {
                font-size: 1.75rem;
            }
            
            .modal-dialog {
                margin: 0.5rem auto;
            }
            
            .image-gallery {
                grid-template-columns: 1fr;
            }
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    <div class="container">
        <!-- Login Section -->
        <div id="loginSection" class="hidden">
            <div class="card animate_animated animate_fadeIn">
                <div class="header">
                    <h1>Welcome Back!</h1>
                    <p>Please login to access the admin dashboard</p>
                </div>
                <div class="form-group">
                    <label for="adminUsername">Username</label>
                    <input type="text" id="adminUsername" class="form-control" placeholder="Enter your username" required>
                </div>
                <div class="form-group">
                    <label for="adminPassword">Password</label>
                    <input type="password" id="adminPassword" class="form-control" placeholder="Enter your password" required>
                </div>
                <div class="text-center">
                    <button id="loginBtn" class="btn btn-primary">
                        <i class="fas fa-sign-in-alt"></i> Login
                    </button>
                    <button id="showRegisterBtn" class="btn btn-secondary">
                        <i class="fas fa-user-plus"></i> Go to Registration
                    </button>
                </div>
            </div>
        </div>

        <!-- Registration Section -->
        <div id="registrationSection" class="animate_animated animate_fadeIn">
            <div class="card">
                <div class="header">
                    <h1>Algorent Registration</h1>
                    <p>Join our platform and start your rental journey today</p>
                </div>
                <form id="registrationForm">
                    <div class="form-group">
                        <label for="username">Full Name</label>
                        <input type="text" id="username" class="form-control" placeholder="Enter your full name" required>
                    </div>
                    <div class="form-group">
                        <label for="userId">National ID</label>
                        <input type="text" id="userId" class="form-control" placeholder="Enter your national ID" required>
                    </div>
                    <div class="form-group">
                        <label for="userType">User Type</label>
                        <select id="userType" class="form-control" required>
                            <option value="">Select your type</option>
                            <option value="apartment">Apartment Owner</option>
                            <option value="shop">Shop Owner</option>
                            <option value="fitter">Fitter</option>
                        </select>
                    </div>

                    <!-- Dynamic file upload fields -->
                    <div id="fileUploadFields"></div>

                    <div class="text-center mt-4">
                        <button type="submit" class="btn btn-primary pulse">
                            <i class="fas fa-paper-plane"></i> Submit Registration
                        </button>
                        <button type="button" id="showAdminLoginBtn" class="btn btn-success">
                            <i class="fas fa-lock"></i> Admin Login
                        </button>
                    </div>
                </form>
            </div>
        </div>

        <!-- Admin Section -->
        <div id="adminSection" class="hidden">
            <div class="card animate_animated animate_slideIn">
                <div class="header">
                    <h1>Admin Dashboard</h1>
                    <p>Manage all registered users and their documents</p>
                    <button id="logoutBtn" class="btn btn-danger">
                        <i class="fas fa-sign-out-alt"></i> Logout
                    </button>
                </div>

                <div id="adminContent" class="mt-4">
                    <h2 class="text-primary mb-4">Registered Users</h2>
                    <div class="table-responsive">
                        <table class="table">
                            <thead>
                                <tr>
                                    <th>ID</th>
                                    <th>Name</th>
                                    <th>National ID</th>
                                    <th>Type</th>
                                    <th>Registration Date</th>
                                    <th>Actions</th>
                                </tr>
                            </thead>
                            <tbody id="userTableBody">
                                <!-- User data will be loaded here -->
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Image Modal -->
    <div id="imageModal" class="modal">
        <div class="modal-dialog modal-lg">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" id="modalTitle">User Documents</h5>
                    <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                        <span aria-hidden="true">&times;</span>
                    </button>
                </div>
                <div class="modal-body">
                    <div class="image-gallery" id="modalImageGallery">
                        <!-- Images will be loaded here -->
                    </div>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-secondary" data-dismiss="modal">
                        <i class="fas fa-times"></i> Close
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- Success Toast -->
    <div id="successToast" class="hidden" style="position: fixed; bottom: 20px; right: 20px; z-index: 1100;">
        <div class="card" style="background-color: var(--success); color: white; padding: 1rem; border-radius: 8px; box-shadow: 0 4px 6px rgba(0,0,0,0.1); min-width: 250px;">
            <div class="d-flex align-items-center">
                <i class="fas fa-check-circle" style="font-size: 1.5rem; margin-right: 0.75rem;"></i>
                <div>
                    <strong id="toastTitle">Success!</strong>
                    <div id="toastMessage">Operation completed successfully</div>
                </div>
            </div>
        </div>
    </div>

    <script>
        // DOM elements
        const loginSection = document.getElementById('loginSection');
        const registrationSection = document.getElementById('registrationSection');
        const adminSection = document.getElementById('adminSection');
        const fileUploadFields = document.getElementById('fileUploadFields');
        const userTypeSelect = document.getElementById('userType');
        const registrationForm = document.getElementById('registrationForm');
        const showAdminLoginBtn = document.getElementById('showAdminLoginBtn');
        const showRegisterBtn = document.getElementById('showRegisterBtn');
        const loginBtn = document.getElementById('loginBtn');
        const logoutBtn = document.getElementById('logoutBtn');
        const adminUsername = document.getElementById('adminUsername');
        const adminPassword = document.getElementById('adminPassword');
        const userTableBody = document.getElementById('userTableBody');
        const imageModal = document.getElementById('imageModal');
        const modalImageGallery = document.getElementById('modalImageGallery');
        const modalTitle = document.getElementById('modalTitle');
        const closeModal = document.querySelector('[data-dismiss="modal"]');
        const successToast = document.getElementById('successToast');
        const toastTitle = document.getElementById('toastTitle');
        const toastMessage = document.getElementById('toastMessage');

        // Sample database (in a real app, this would be server-side)
        let users = JSON.parse(localStorage.getItem('algorent_users')) || [];
        let currentUser = null;

        // Initialize the page
        function init() {
            // Check if admin is already logged in
            const isAdmin = localStorage.getItem('algorent_adminLoggedIn') === 'true';
            if (isAdmin) {
                showAdminSection();
            } else {
                showRegistrationSection();
            }

            // Set up event listeners
            userTypeSelect.addEventListener('change', updateFileUploadFields);
            showAdminLoginBtn.addEventListener('click', showLoginSection);
            showRegisterBtn.addEventListener('click', showRegistrationSection);
            loginBtn.addEventListener('click', handleAdminLogin);
            logoutBtn.addEventListener('click', handleAdminLogout);
            registrationForm.addEventListener('submit', handleRegistrationSubmit);
            closeModal.addEventListener('click', () => hideModal());
            window.addEventListener('click', (event) => {
                if (event.target === imageModal) {
                    hideModal();
                }
            });

            // Initialize file upload fields
            updateFileUploadFields();
        }

        // Show/hide sections with animations
        function showLoginSection() {
            loginSection.classList.remove('hidden');
            loginSection.classList.add('animate__fadeIn');
            registrationSection.classList.add('hidden');
            adminSection.classList.add('hidden');
        }

        function showRegistrationSection() {
            registrationSection.classList.remove('hidden');
            registrationSection.classList.add('animate__fadeIn');
            loginSection.classList.add('hidden');
            adminSection.classList.add('hidden');
        }

        function showAdminSection() {
            adminSection.classList.remove('hidden');
            adminSection.classList.add('animate__slideIn');
            loginSection.classList.add('hidden');
            registrationSection.classList.add('hidden');
            loadUserData();
        }

        // Update file upload fields based on user type
        function updateFileUploadFields() {
            const userType = userTypeSelect.value;
            fileUploadFields.innerHTML = '';

            if (!userType) return;

            if (userType === 'apartment') {
                addFileUploadField('proofOfOwnership', 'Proof of Ownership', 'Upload document proving ownership (PDF or image)', true);
                addFileUploadField('nationalId', 'National ID Card', 'Upload a clear copy of your national ID', true);
                addFileUploadField('receipt', 'Receipt', 'Upload a recent receipt (PDF or image)', true);
                addFileUploadField('apartmentPhotos', 'Apartment Photos', 'Upload photos of your apartment (multiple allowed)', true, true);
            } else if (userType === 'shop') {
                addFileUploadField('proofOfOwnership', 'Proof of Ownership', 'Upload document proving ownership (PDF or image)', true);
                addFileUploadField('nationalId', 'National ID Card', 'Upload a clear copy of your national ID', true);
                addFileUploadField('productImages', 'Product Images', 'Upload images of your products (multiple allowed)', true, true);
            } else if (userType === 'fitter') {
                addFileUploadField('nationalId', 'National ID Card', 'Upload a clear copy of your national ID', true);
                addFileUploadField('certificate', 'Certificate', 'Upload your professional certificate (PDF or image)', true);
            }
        }

        function addFileUploadField(name, label, placeholder, required = false, multiple = false) {
            const div = document.createElement('div');
            div.className = 'form-group';
            
            const labelEl = document.createElement('label');
            labelEl.textContent = label;
            
            const uploadContainer = document.createElement('div');
            uploadContainer.className = 'file-upload';
            
            const input = document.createElement('input');
            input.type = 'file';
            input.className = 'file-upload-input';
            input.id = name;
            input.name = name;
            input.required = required;
            input.multiple = multiple;
            input.accept = 'image/*,.pdf';
            
            const labelUpload = document.createElement('label');
            labelUpload.className = 'file-upload-label';
            labelUpload.htmlFor = name;
            labelUpload.innerHTML = `
                <i class="fas fa-cloud-upload-alt"></i>
                <span>${placeholder}</span>
            `;
            
            const preview = document.createElement('div');
            preview.className = 'image-preview';
            preview.id = ${name}Preview;
            
            input.addEventListener('change', function() {
                updateImagePreview(this, preview.id);
            });
            
            uploadContainer.appendChild(input);
            uploadContainer.appendChild(labelUpload);
            
            div.appendChild(labelEl);
            div.appendChild(uploadContainer);
            div.appendChild(preview);
            fileUploadFields.appendChild(div);
        }

        function updateImagePreview(input, previewId) {
            const preview = document.getElementById(previewId);
            preview.innerHTML = '';
            
            if (input.files) {
                for (let i = 0; i < input.files.length; i++) {
                    const reader = new FileReader();
                    reader.onload = function(e) {
                        const previewDiv = document.createElement('div');
                        previewDiv.className = 'preview-image';
                        
                        const img = document.createElement('img');
                        img.src = e.target.result;
                        
                        const removeBtn = document.createElement('div');
                        removeBtn.className = 'remove-image';
                        removeBtn.innerHTML = '<i class="fas fa-times"></i>';
                        removeBtn.addEventListener('click', () => {
                            previewDiv.remove();
                            // Create new FileList without the removed file
                            const dataTransfer = new DataTransfer();
                            for (let j = 0; j < input.files.length; j++) {
                                if (j !== i) {
                                    dataTransfer.items.add(input.files[j]);
                                }
                            }
                            input.files = dataTransfer.files;
                        });
                        
                        previewDiv.appendChild(img);
                        previewDiv.appendChild(removeBtn);
                        preview.appendChild(previewDiv);
                    }
                    reader.readAsDataURL(input.files[i]);
                }
            }
        }

       function handleRegistrationSubmit(e) {
    e.preventDefault();
    
    const formData = {
        id: Date.now().toString(),
        username: document.getElementById('username').value,
        userId: document.getElementById('userId').value,
        userType: userTypeSelect.value,
        registrationDate: new Date().toISOString(),
        images: {}
    };
    
    // Collect file names and preview data
    const fileInputs = registrationForm.querySelectorAll('input[type="file"]');
    const promises = [];
    
    fileInputs.forEach(input => {
        if (input.files.length > 0) {
            formData.images[input.name] = [];
            for (let i = 0; i < input.files.length; i++) {
                const file = input.files[i];
                const promise = new Promise((resolve) => {
                    const reader = new FileReader();
                    reader.onload = function(e) {
                        resolve({
                            name: file.name,
                            type: file.type,
                            size: file.size,
                            lastModified: file.lastModified,
                            data: e.target.result // Store Base64 data
                        });
                    };
                    reader.readAsDataURL(file);
                });
                promises.push(promise);
            }
        }
    });
    
    // Wait for all images to be processed
    Promise.all(promises).then(results => {
        let resultIndex = 0;
        fileInputs.forEach(input => {
            if (input.files.length > 0) {
                formData.images[input.name] = [];
                for (let i = 0; i < input.files.length; i++) {
                    formData.images[input.name].push(results[resultIndex]);
                    resultIndex++;
                }
            }
        });
        
        // Save to "database"
        users.push(formData);
        localStorage.setItem('algorent_users', JSON.stringify(users));
        
        // Show success message
        showToast('Registration Successful', 'Your information has been submitted successfully!');
        
        // Reset form
        registrationForm.reset();
        fileUploadFields.innerHTML = '';
        updateFileUploadFields();
    });
}

        // Admin functions
        function handleAdminLogin() {
            if (adminUsername.value === 'yousef' && adminPassword.value === '123') {
                localStorage.setItem('algorent_adminLoggedIn', 'true');
                showAdminSection();
                showToast('Login Successful', 'Welcome to the Admin Dashboard!');
            } else {
                showToast('Login Failed', 'Invalid username or password', 'error');
            }
        }

        function handleAdminLogout() {
            localStorage.removeItem('algorent_adminLoggedIn');
            showLoginSection();
            adminUsername.value = '';
            adminPassword.value = '';
            showToast('Logged Out', 'You have been successfully logged out');
        }

        function loadUserData() {
            userTableBody.innerHTML = '';
            
            if (users.length === 0) {
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td colspan="6" class="text-center">No registered users found</td>
                `;
                userTableBody.appendChild(row);
                return;
            }
            
            users.forEach((user, index) => {
                const row = document.createElement('tr');
                row.classList.add('animate_animated', 'animate_fadeIn');
                row.style.animationDelay = ${index * 0.1}s;
                
                row.innerHTML = `
                    <td>${index + 1}</td>
                    <td>${user.username}</td>
                    <td>${user.userId}</td>
                    <td><span class="badge ${getBadgeClass(user.userType)}">${getUserTypeLabel(user.userType)}</span></td>
                    <td>${new Date(user.registrationDate).toLocaleString()}</td>
                    <td>
                        <button class="btn btn-primary btn-sm view-images" data-id="${user.id}">
                            <i class="fas fa-images"></i> View Documents
                        </button>
                    </td>
                `;
                
                userTableBody.appendChild(row);
            });
            
            // Add event listeners to view image buttons
            document.querySelectorAll('.view-images').forEach(button => {
                button.addEventListener('click', function() {
                    const id = this.getAttribute('data-id');
                    showUserImages(id);
                });
            });
        }

        function getBadgeClass(type) {
            switch(type) {
                case 'apartment': return 'badge-primary';
                case 'shop': return 'badge-success';
                case 'fitter': return 'badge-warning';
                default: return 'badge-secondary';
            }
        }

        function getUserTypeLabel(type) {
            switch(type) {
                case 'apartment': return 'Apartment Owner';
                case 'shop': return 'Shop Owner';
                case 'fitter': return 'Fitter';
                default: return type;
            }
        }

       function showUserImages(id) {
    const user = users.find(u => u.id === id);
    if (!user) return;
    
    modalImageGallery.innerHTML = '';
    modalTitle.textContent = `Documents for ${user.username}`;
    
    for (const [key, images] of Object.entries(user.images)) {
        images.forEach(image => {
            const galleryItem = document.createElement('div');
            galleryItem.className = 'gallery-item';
            
            if (image.type.includes('image')) {
                galleryItem.innerHTML = `
                    <img src="${image.data}" alt="${image.name}">
                    <div class="gallery-caption">${key}: ${image.name}</div>
                `;
            } else {
                // For PDFs, show a document icon
                galleryItem.innerHTML = `
                    <div style="height: 200px; display: flex; flex-direction: column; align-items: center; justify-content: center; background: #f8f9fa;">
                        <i class="fas fa-file-pdf" style="font-size: 3rem; color: var(--danger);"></i>
                        <div style="margin-top: 1rem; text-align: center; padding: 0.5rem;">
                            ${key}: ${image.name}
                        </div>
                        <a href="${image.data}" download="${image.name}" class="btn btn-primary btn-sm mt-2">
                            <i class="fas fa-download"></i> Download PDF
                        </a>
                    </div>
                `;
            }
            
            modalImageGallery.appendChild(galleryItem);
        });
    }
    
    showModal();
}
        // Modal functions
        function showModal() {
            imageModal.style.display = 'block';
            document.body.style.overflow = 'hidden';
        }

        function hideModal() {
            imageModal.style.display = 'none';
            document.body.style.overflow = 'auto';
        }

        // Toast notification
        function showToast(title, message, type = 'success') {
            toastTitle.textContent = title;
            toastMessage.textContent = message;
            
            // Set background color based on type
            const toastCard = successToast.querySelector('.card');
            if (type === 'error') {
                toastCard.style.backgroundColor = 'var(--danger)';
            } else if (type === 'warning') {
                toastCard.style.backgroundColor = 'var(--warning)';
            } else {
                toastCard.style.backgroundColor = 'var(--success)';
            }
            
            successToast.classList.remove('hidden');
            successToast.classList.add('animate_animated', 'animate_fadeInRight');
            
            // Hide after 3 seconds
            setTimeout(() => {
                successToast.classList.add('animate__fadeOutRight');
                setTimeout(() => {
                    successToast.classList.add('hidden');
                    successToast.classList.remove('animate_fadeInRight', 'animate_fadeOutRight');
                }, 500);
            }, 3000);
        }

        // Initialize the application
        document.addEventListener('DOMContentLoaded', init);
    </script>
</body>
</html>
