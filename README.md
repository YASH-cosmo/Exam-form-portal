# Exam Form Submission Portal

## Project Overview
This is a comprehensive online portal for exam form submission designed to digitize and streamline the traditional paper-based exam form submission process at our college.

## Problem Statement
The current exam form submission process involves:
1. Students filling exam forms online on the university website
2. Taking printouts of the filled form
3. Getting signatures from class teachers
4. Submitting the physical form to the accounts section
5. Paying exam fees in person

This manual process is time-consuming and inefficient for both students and staff.

## Solution
Our online portal automates the entire workflow:
- **Student Portal**: Online form submission and payment
- **Teacher Portal**: Digital verification and approval
- **Accounts Portal**: Payment verification and final approval
- **Automated Notifications**: Email updates at each stage

## Features

### For Students
- Secure login using college official email
- Online exam form filling and submission
- Document upload functionality
- Payment receipt upload
- Real-time status tracking
- Email notifications

### For Teachers
- Dedicated teacher login portal
- View submitted forms from students
- Digital verification and approval system
- Add comments/feedback on forms
- Bulk approval options

### For Accounts Section
- Comprehensive dashboard for form management
- Payment verification tools
- Final approval workflow
- Report generation
- Student records management

## Technology Stack

### Frontend
- HTML5, CSS3, JavaScript
- Bootstrap for responsive design
- jQuery for DOM manipulation

### Backend
- Node.js with Express.js framework
- RESTful API design
- JWT for authentication

### Database
- MySQL for relational data storage
- Tables for users, forms, payments, approvals

### Additional Tools
- Nodemailer for email notifications
- Multer for file uploads
- bcrypt for password hashing

## Project Structure
```
exam-form-portal/
├── backend/
│   ├── routes/
│   ├── controllers/
│   ├── models/
│   └── middleware/
├── frontend/
│   ├── css/
│   ├── js/
│   └── images/
├── database/
│   └── schema.sql
├── config/
│   └── .env
├── docs/
└── README.md
```

## Workflow

### Student Workflow
1. Register/Login using college email
2. Fill exam form online
3. Upload required documents
4. Make payment and upload receipt
5. Submit form for teacher approval
6. Track status through dashboard
7. Receive email confirmation

### Teacher Workflow
1. Login to teacher portal
2. View pending forms
3. Verify student details
4. Approve/Reject with comments
5. Forward approved forms to accounts

### Accounts Workflow
1. Login to accounts portal
2. Review teacher-approved forms
3. Verify payment details
4. Final approval
5. Send confirmation email to student

## Installation

### Prerequisites
- Node.js (v14 or higher)
- MySQL (v8.0 or higher)
- npm or yarn package manager

### Setup Instructions
1. Clone the repository
2. Install dependencies:
   ```bash
   npm install
   ```
3. Set up MySQL database:
   ```bash
   mysql -u root -p < database/schema.sql
   ```
4. Configure environment variables in `config/.env`
5. Start the server:
   ```bash
   npm start
   ```

## Environment Variables
Create a `.env` file in the config folder with:
```
PORT=3000
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=yourpassword
DB_NAME=exam_portal
JWT_SECRET=your_jwt_secret
EMAIL_HOST=smtp.gmail.com
EMAIL_USER=your_email@gmail.com
EMAIL_PASSWORD=your_app_password
```

## API Endpoints

### Authentication
- `POST /api/auth/register` - Student registration
- `POST /api/auth/login` - User login
- `POST /api/auth/logout` - User logout

### Student Routes
- `GET /api/student/profile` - Get student profile
- `POST /api/student/form` - Submit exam form
- `POST /api/student/upload` - Upload documents
- `GET /api/student/status` - Check form status

### Teacher Routes
- `GET /api/teacher/forms` - View pending forms
- `PUT /api/teacher/approve/:id` - Approve form
- `PUT /api/teacher/reject/:id` - Reject form

### Accounts Routes
- `GET /api/accounts/forms` - View approved forms
- `PUT /api/accounts/verify/:id` - Verify payment
- `GET /api/accounts/reports` - Generate reports

## Database Schema

### Users Table
- user_id (Primary Key)
- email (Unique)
- password (Hashed)
- role (student/teacher/accounts)
- name
- department
- created_at

### Forms Table
- form_id (Primary Key)
- student_id (Foreign Key)
- exam_type
- semester
- subjects
- status
- submitted_at

### Approvals Table
- approval_id (Primary Key)
- form_id (Foreign Key)
- approver_id (Foreign Key)
- approval_type
- comments
- approved_at

### Payments Table
- payment_id (Primary Key)
- form_id (Foreign Key)
- amount
- receipt_url
- verified
- payment_date

## Security Features
- Password hashing using bcrypt
- JWT token authentication
- Role-based access control
- Input validation and sanitization
- File upload restrictions
- HTTPS enforcement in production

## Team Members
- [Add team member names here]

## License
This project is developed for educational purposes as part of our college project.

## Future Enhancements
- Mobile application
- SMS notifications
- Online payment gateway integration
- Bulk form processing
- Advanced analytics dashboard
- Multi-language support

## Contact
For any queries or support, please contact the development team.
