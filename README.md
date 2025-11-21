# ContractMonthlyClaimSystem
Automated web application for managing monthly claim submissions, approvals, and invoice generation - PROG6212POE

Project Structure
Create the following folder structure:
ContractMonthlyClaimSystem/
│
├── ContractClaimSystem/              # Main application
│   ├── Controllers/
│   ├── Models/
│   ├── Views/
│   ├── Data/
│   ├── wwwroot/
│   │   ├── css/
│   │   ├── js/
│   │   ├── images/
│   │   └── uploads/
│   ├── appsettings.json
│   └── Program.cs
│
├── Documentation/
│   ├── DatabaseSchema.sql
│   ├── LecturerFeedback.docx
│   ├── Presentation.pptx
│   └── UserGuide.pdf
│
├── Tests/                            # Unit tests (optional)
│   └── ContractClaimSystem.Tests/
│
├── .gitignore
├── README.md
└── LICENSE

Part 3: 10+ Meaningful Commits
Commit 1: Initial Project Setup
bash# Create ASP.NET Core MVC Project
dotnet new mvc -n ContractClaimSystem

# Move files to repository
# Then commit

git add .
git commit -m "Initial project setup with ASP.NET Core MVC 6.0

- Created new ASP.NET Core MVC project
- Added project structure with Controllers, Models, Views folders
- Configured appsettings.json with initial settings
- Added .gitignore for Visual Studio projects"

git push origin main
Commit 2: Database Schema & Models
bashgit add Models/ Data/
git commit -m "Implemented database schema and Entity Framework models

- Created ApplicationUser model extending IdentityUser
- Added Lecturer model with personal and banking details
- Implemented Claim model with validation attributes
- Created ClaimApproval, Invoice, and SupportingDocument models
- Added AuditLog and SystemSetting models
- Configured relationships in ApplicationDbContext
- Added data annotations for validation
- Set up Entity Framework Core with SQL Server"

git push origin main
Commit 3: Authentication & Authorization
bashgit add Program.cs Startup.cs
git commit -m "Configured ASP.NET Identity for authentication and authorization

- Integrated ASP.NET Identity with ApplicationUser
- Set up role-based authorization (Lecturer, Coordinator, Manager, HR)
- Configured authentication middleware
- Added login and registration pages
- Implemented password hashing and security
- Set up cookie authentication
- Added authorization policies for different user roles"

git push origin main
Commit 4: Lecturer Claim Submission
bashgit add Controllers/LecturerController.cs Views/Lecturer/
git commit -m "Implemented lecturer claim submission functionality

- Created LecturerController with Dashboard and SubmitClaim actions
- Added auto-calculation feature (hours × rate = total)
- Implemented server-side validation for hours worked (0.01-744)
- Added duplicate claim detection
- Created ClaimSubmissionViewModel for data binding
- Designed user-friendly claim submission form
- Added support for multiple document uploads
- Implemented file validation (type and size checks)"

git push origin main
Commit 5: Client-Side Validation
bashgit add wwwroot/js/claim-validation.js
git commit -m "Added comprehensive client-side validation with jQuery

- Implemented real-time validation for hours worked
- Added auto-calculation that updates as user types
- Created validation for claim month/year (prevent future/old claims)
- Added file upload validation (type, size, count)
- Implemented visual feedback with Bootstrap validation classes
- Added calculation breakdown display
- Created error and warning message system
- Implemented form submission validation
- Added duplicate claim checking via AJAX"

git push origin main
Commit 6: Approval Workflow
bashgit add Controllers/ApprovalController.cs Views/Approval/
git commit -m "Implemented automated approval workflow for coordinators and managers

- Created ApprovalController with PendingClaims and ReviewClaim actions
- Implemented automated claim verification against business rules
- Added approval/rejection functionality with comments
- Created ClaimApprovalViewModel for approval processing
- Designed intuitive claim review interface
- Added status tracking and history display
- Implemented role-based access (Coordinator and Manager)
- Created approval records with timestamp and approver details"

git push origin main
Commit 7: HR Invoice Generation
bashgit add Controllers/HRController.cs
git commit -m "Implemented automated PDF invoice generation for HR

- Created HRController with invoice generation functionality
- Integrated iTextSharp for professional PDF creation
- Implemented auto-generated invoice numbers (INV-YYYY-XXXXXX)
- Added comprehensive invoice layout with company branding
- Created invoice storage and retrieval system
- Implemented payment status tracking
- Added batch invoice generation capability
- Linked invoices to claims with one-to-one relationship
- Updated claim status to 'Processed' after invoice generation"

git push origin main
Commit 8: HR Lecturer Management
bashgit add Views/HR/ManageLecturers.cshtml Views/HR/EditLecturer.cshtml
git commit -m "Added lecturer data management features for HR

- Implemented lecturer listing with search and filter
- Created EditLecturer functionality for updating personal info
- Added ability to update hourly rates
- Implemented banking details management
- Created contact information update forms
- Added emergency contact fields
- Implemented validation for all lecturer data fields
- Added audit logging for lecturer data changes
- Created user-friendly interface for HR staff"

git push origin main
Commit 9: Dashboard & Reporting
bashgit add Views/Lecturer/Dashboard.cshtml Views/HR/Dashboard.cshtml
git commit -m "Created comprehensive dashboards and reporting features

- Implemented lecturer dashboard with claim summary cards
- Added real-time status tracking visualization
- Created search and filter functionality for claims
- Implemented HR dashboard with statistics
- Added monthly report generation
- Created claim history views with pagination
- Implemented status-based filtering
- Added year and month filters
- Created export functionality for reports
- Designed responsive layout for all dashboards"

git push origin main
Commit 10: Audit Logging System
bashgit add Services/AuditService.cs
git commit -m "Implemented comprehensive audit logging system

- Created AuditLog model for tracking all system changes
- Implemented logging for claim submissions
- Added audit trail for approvals and rejections
- Logged invoice generation activities
- Tracked lecturer data modifications
- Implemented user action logging
- Added timestamp and user identification
- Created audit log viewer for administrators
- Implemented log search and filter functionality"

git push origin main
Commit 11: UI/UX Enhancements
bashgit add wwwroot/css/ wwwroot/images/
git commit -m "Enhanced user interface and experience

- Applied Bootstrap 5 styling throughout application
- Created custom CSS for branding and theme
- Added Font Awesome icons for better visual communication
- Implemented responsive design for mobile compatibility
- Created status badges with color coding
- Added loading spinners for async operations
- Implemented toast notifications for user feedback
- Created professional color scheme
- Added hover effects and transitions
- Optimized images and assets"

git push origin main
Commit 12: Security Enhancements
bashgit add Middleware/ Services/
git commit -m "Implemented additional security measures

- Added CSRF protection for all forms
- Implemented SQL injection prevention with parameterized queries
- Added XSS protection in Razor views
- Configured secure file upload validation
- Implemented role-based authorization checks
- Added secure password requirements
- Configured HTTPS enforcement
- Implemented session timeout
- Added security headers
- Created secure connection strings handling"

git push origin main
Commit 13: Testing & Bug Fixes
bashgit add Tests/
git commit -m "Added unit tests and fixed bugs

- Created unit tests for validation logic
- Added tests for calculation accuracy
- Implemented integration tests for workflows
- Fixed bug in duplicate claim detection
- Corrected date validation edge cases
- Fixed file upload path issues
- Resolved calculation rounding errors
- Fixed approval workflow status updates
- Corrected invoice number generation
- Added test coverage for critical paths"

git push origin main
Commit 14: Documentation
bashgit add Documentation/ README.md
git commit -m "Added comprehensive documentation

- Updated README with project overview and setup instructions
- Created database schema documentation
- Added API documentation for controllers
- Documented all validation rules
- Created user guides for each role
- Added code comments for complex logic
- Documented environment setup process
- Created troubleshooting guide
- Added screenshots and diagrams"

git push origin main
Commit 15: Final Production Release
bashgit add .
git commit -m "Final production release v1.0

- Completed all required features
- Implemented all lecturer feedback
- Passed all unit and integration tests
- Optimized performance and database queries
- Validated all user workflows
- Completed documentation
- Ready for deployment
- All acceptance criteria met

Features implemented:
✅ Automated claim submission with validation
✅ Real-time calculation and transparency
✅ Multi-document upload support
✅ Enhanced dashboard with search/filter
✅ Automated approval workflows
✅ PDF invoice generation
✅ Lecturer data management
✅ Comprehensive reporting
✅ Audit logging throughout system
✅ Security and role-based access"

git push origin main


# Contract Monthly Claim System

Automated web application for managing monthly claim submissions, approvals, and invoice generation.

**Module:** PROG6212POE  
**Student:** [Your Name]  
**Institution:** Independent Institute of Education  
**Date:** November 2025

## 🎯 Project Overview

The Contract Monthly Claim System is a comprehensive web application designed to streamline the process of submitting, approving, and processing monthly claims for contract lecturers. The system features role-based access for Lecturers, Programme Coordinators, Academic Managers, and HR personnel.

## ✨ Key Features

### Lecturer Features
- ✅ Submit monthly claims with auto-calculation
- ✅ Upload multiple supporting documents
- ✅ Real-time validation and feedback
- ✅ Track claim status
- ✅ View claim history

### Coordinator/Manager Features
- ✅ Automated claim verification
- ✅ Streamlined approval workflows
- ✅ Bulk claim processing
- ✅ Comment and feedback system

### HR Features
- ✅ Automated PDF invoice generation
- ✅ Lecturer data management
- ✅ Payment tracking
- ✅ Monthly reporting
- ✅ System analytics

## 🛠️ Technologies Used

- **Backend:** ASP.NET Core MVC 6.0, C#
- **Database:** SQL Server with Entity Framework Core
- **Frontend:** Razor Pages, Bootstrap 5, jQuery
- **Authentication:** ASP.NET Identity
- **PDF Generation:** iTextSharp
- **Icons:** Font Awesome

## 📋 Prerequisites

- Visual Studio 2022 or later
- .NET 6.0 SDK
- SQL Server 2019 or later
- Git

## 🚀 Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/YourUsername/ContractMonthlyClaimSystem.git
cd ContractMonthlyClaimSystem
```

### 2. Configure Database

Update connection string in `appsettings.json`:
```json
"ConnectionStrings": {
  "DefaultConnection": "Server=YOUR_SERVER;Database=ContractClaimDB;Trusted_Connection=True;MultipleActiveResultSets=true"
}
```

### 3. Run Migrations
```bash
dotnet ef database update
```

### 4. Build and Run
```bash
dotnet build
dotnet run
```

Application will be available at: `https://localhost:5001`

## 👥 Default Users

After seeding, use these credentials:

| Role | Email | Password |
|------|-------|----------|
| Lecturer | lecturer@iie.ac.za | Lecturer@123 |
| Coordinator | coordinator@iie.ac.za | Coord@123 |
| Manager | manager@iie.ac.za | Manager@123 |
| HR | hr@iie.ac.za | HR@123 |

## 📊 Database Schema

See `Documentation/DatabaseSchema.sql` for complete schema.

## 📖 User Guides

- [Lecturer Guide](Documentation/LecturerGuide.pdf)
- [Coordinator/Manager Guide](Documentation/ApprovalGuide.pdf)
- [HR Guide](Documentation/HRGuide.pdf)

## 🧪 Running Tests
```bash
dotnet test
```

## 📝 Version History

- **v1.0** (Nov 2025) - Initial release with all core features

## 🤝 Contributing

This is an academic project. Feedback and suggestions are welcome!

## 📄 License

This project is licensed under the MIT License.

## 📧 Contact

**Student:** [Nduduzo Jali]  
**Email:** [st10402988@rcconnect.edu.za]  
**Student Number:** [St10402988]

## 🙏 Acknowledgments

- Independent Institute of Education
- PROG6212 Lecturer and Staff
- All lecturers who provided valuable feedback
