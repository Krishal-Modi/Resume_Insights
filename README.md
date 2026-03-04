# 📄 Resume Insights

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Django](https://img.shields.io/badge/Django-5.1+-green.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

**Resume Insights** is a powerful, intelligent web application designed to help job seekers optimize their resumes for Applicant Tracking Systems (ATS). Built with Django, this platform provides comprehensive analysis of resumes and extracts crucial information to ensure your resume gets past automated screening systems.

## ✨ Key Features

### 🔍 **Advanced ATS Compatibility Analysis**
- **Smart Resume Scanning**: Analyzes resumes against 10+ critical keywords including skills, education, certifications, experience, projects, awards, LinkedIn, languages, courses, and portfolio
- **Intelligent Scoring System**: Provides a compatibility score out of 80 points (8 points per keyword)
- **Missing Keywords Detection**: Identifies exactly which sections are missing from your resume
- **Real-time Analysis**: Instant feedback on your resume's ATS-friendliness

### 📧 **Automated Email Notifications**
- **Welcome Emails**: Automatic email dispatch upon successful registration
- **SMTP Integration**: Seamless Gmail SMTP configuration for reliable email delivery
- **Personalized Messages**: Custom email content with user's name and registration details
- **Professional Communication**: Keeps users informed throughout their journey

### 🔐 **Robust User Authentication System**
- **Email-Based Authentication**: Modern authentication using email addresses instead of usernames
- **Secure Password Management**: Django's built-in password hashing and validation
- **Custom User Model**: Extended AbstractUser model with additional fields (birth_date)
- **Session Management**: Secure session handling for file uploads and user data
- **Account Management**: Users can delete their accounts with a single click

### 📤 **Intelligent Resume Upload & Processing**
- **PDF Support**: Automatic PDF resume parsing using PyPDF2
- **Text Extraction**: Advanced text extraction from multi-page PDF documents
- **Information Extraction**:
  - **Email Detection**: Automatically extracts email addresses from resume content
  - **Phone Number Parsing**: Identifies and extracts phone numbers with country codes
- **Secure File Storage**: File uploads stored securely with proper permissions
- **Session-Based Processing**: Maintains upload state across analysis workflow

### 💳 **Payment Integration Ready**
- Dedicated payment page for premium features
- Foundation for monetization strategies
- Scalable payment processing implementation

### 🎨 **Modern & Responsive UI**
- **Bootstrap 5.3+**: Clean, professional, and mobile-responsive design
- **Custom Styling**: Beautiful background images and custom CSS
- **Interactive JavaScript**: Dynamic score animations and form validations
- **User-Friendly Interface**: Intuitive navigation and seamless user experience

### 🛡️ **Security Features**
- CSRF protection enabled
- Clickjacking protection
- Secure password validators
- Login required decorators for protected views
- Email uniqueness validation

## 🚀 Getting Started

### Prerequisites

- Python 3.8 or higher
- pip (Python package manager)
- Git

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/Krishal-Modi/Resume_Insights.git
cd Resume_Insights
```

2. **Create a virtual environment**
```bash
python -m venv venv
```

3. **Activate the virtual environment**

**Windows:**
```bash
venv\Scripts\activate
```

**macOS/Linux:**
```bash
source venv/bin/activate
```

4. **Install required dependencies**
```bash
pip install django
pip install pypdf2
```

5. **Configure Email Settings**

Edit `Resumeinsights/settings.py` and update the email configuration:
```python
EMAIL_HOST_USER = 'your-email@gmail.com'
EMAIL_HOST_PASSWORD = 'your-app-password'  # Use App Password, not your Gmail password
```

**Note**: For Gmail, you need to generate an [App Password](https://support.google.com/accounts/answer/185833)

6. **Apply database migrations**
```bash
cd Resumeinsights
python manage.py makemigrations
python manage.py migrate
```

7. **Create a superuser (optional)**
```bash
python manage.py createsuperuser
```

8. **Run the development server**
```bash
python manage.py runserver
```

9. **Access the application**

Open your browser and navigate to: `http://127.0.0.1:8000/`

## 📁 Project Structure

```
Resume_Insights/
├── Resumeinsights/
│   ├── manage.py
│   ├── db.sqlite3
│   ├── resumedetails/              # Main Django app
│   │   ├── models.py               # Custom Admin user model
│   │   ├── views.py                # All view logic & ATS analysis
│   │   ├── admin.py                # Admin configuration
│   │   ├── static/
│   │   │   ├── css/                # Stylesheets
│   │   │   ├── js/                 # JavaScript files
│   │   │   └── images/             # Static images
│   │   ├── templates/              # HTML templates
│   │   │   ├── index.html          # Landing page
│   │   │   ├── register.html       # User registration
│   │   │   ├── login.html          # User login
│   │   │   ├── upload.html         # Resume upload
│   │   │   ├── ats.html            # Analysis results
│   │   │   └── payment.html        # Payment page
│   │   └── migrations/             # Database migrations
│   └── Resumeinsights/             # Project settings
│       ├── settings.py             # Django settings
│       ├── urls.py                 # URL routing
│       └── wsgi.py                 # WSGI config
├── README.md
└── LICENSE
```

## 🎯 How It Works

1. **User Registration**: New users sign up with email, username, password, and birth date
2. **Email Confirmation**: Automatic welcome email sent via SMTP
3. **Login**: Users authenticate using their email and password
4. **Resume Upload**: Upload PDF resume through secure file upload
5. **ATS Analysis**: System analyzes resume for key sections and keywords
6. **Results Display**: 
   - ATS compatibility score (out of 80)
   - List of missing keywords
   - Extracted email address and phone number
7. **Recommendations**: Suggestions to improve ATS compatibility

## 🔑 Key Technologies

- **Backend Framework**: Django 5.1+
- **Database**: SQLite3 (easily replaceable with PostgreSQL/MySQL)
- **PDF Processing**: PyPDF2
- **Email**: Django Email Backend with SMTP
- **Frontend**: HTML5, CSS3, Bootstrap 5.3, JavaScript
- **Authentication**: Django's built-in auth system with custom user model
- **Session Management**: Django sessions

## 📊 ATS Analysis Algorithm

The system evaluates resumes based on 10 critical keywords:
- ✅ Skills
- ✅ Education
- ✅ Certifications
- ✅ Experience
- ✅ Projects
- ✅ Awards
- ✅ LinkedIn
- ✅ Languages
- ✅ Courses
- ✅ Portfolio

**Scoring**: Each keyword present = 10 points (Maximum: 80 points)

## 🌟 What Makes This Project Special

### 1. **Practical Real-World Application**
Solves a genuine problem faced by job seekers worldwide - getting past ATS filters

### 2. **Intelligent Data Extraction**
Advanced regex patterns to extract contact information automatically

### 3. **Email Automation**
Demonstrates professional email integration - crucial for any modern web application

### 4. **Clean Architecture**
Well-organized Django project structure following best practices

### 5. **Extensible Design**
Easy to add more features like:
- Multiple file format support (DOCX, TXT)
- AI-powered recommendations
- Resume templates
- Job matching algorithms
- Analytics dashboard

### 6. **User-Centric Design**
Focuses on providing actionable insights, not just scores

## 🔒 Security Considerations

- **Email Validation**: Prevents duplicate registrations
- **Password Security**: Uses Django's robust password validation
- **CSRF Protection**: All forms protected against cross-site request forgery
- **Login Required**: Protected routes accessible only to authenticated users
- **File Upload Security**: Proper file handling and permission management

## 🚧 Future Enhancements

- [ ] Add support for DOCX and TXT resume formats
- [ ] Implement AI-powered resume improvement suggestions
- [ ] Add resume template builder
- [ ] Create analytics dashboard for users
- [ ] Implement job matching algorithm
- [ ] Add LinkedIn profile import
- [ ] Multi-language support
- [ ] Export analysis results as PDF
- [ ] Resume version comparison
- [ ] Integration with job boards

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Developer

**Krishal Modi**
- GitHub: [@Krishal-Modi](https://github.com/Krishal-Modi)
- Email: krishalmodi2345@gmail.com

## 🙏 Acknowledgments

- Django Software Foundation for the amazing web framework
- Bootstrap team for the responsive CSS framework
- PyPDF2 contributors for PDF parsing capabilities
- The open-source community for continuous inspiration

## 📧 Support

For support, email krishalmodi2345@gmail.com or open an issue in the GitHub repository.

---

**⭐ If you find this project helpful, please consider giving it a star on GitHub!**

**Made with ❤️ by Krishal Modi**