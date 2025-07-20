# Interior Design Management System

A comprehensive internal digital system for interior design companies to manage projects, designs, approvals, and client interactions.

## 🏗️ System Overview

This system provides a complete solution for interior design project management with role-based access control, dual manager approval workflows, change tracking, and client collaboration features.

### Key Features

- **Role-Based Access Control**: Admin, Manager, Designer, and Client roles with appropriate permissions
- **Project Management**: Create, track, and manage interior design projects
- **Design Workflow**: Upload designs, request approvals, and track revisions
- **Dual Manager Approval**: Mandatory dual approval system for design decisions
- **Change Log System**: Track all project changes with detailed audit trails
- **Client Portal**: Allow clients to view projects, provide feedback, and approve designs
- **Task Management**: Assign and track tasks across team members
- **Feedback System**: Collect and manage client feedback throughout projects
- **Dashboard & Analytics**: Comprehensive overview with KPIs and reporting

## 🛠️ Technology Stack

### Backend
- **Node.js** with Express.js framework
- **PostgreSQL** database
- **JWT** authentication
- **Multer** for file uploads
- **bcryptjs** for password hashing

### Frontend
- **React.js** with modern hooks
- **TailwindCSS** for styling
- **shadcn/ui** component library
- **React Router** for navigation
- **Axios** for API communication

## 📁 Project Structure

```
interior-design-system/
├── backend/                 # Node.js backend application
│   ├── src/
│   │   ├── controllers/     # API route handlers
│   │   ├── middleware/      # Authentication & validation
│   │   ├── models/          # Database models
│   │   ├── routes/          # API routes
│   │   ├── services/        # Business logic
│   │   ├── utils/           # Utilities & database setup
│   │   └── app.js          # Main application file
│   ├── uploads/            # File upload directory
│   ├── package.json
│   └── .env               # Environment configuration
├── frontend/               # React frontend application
│   └── interior-design-frontend/
│       ├── src/
│       │   ├── components/  # React components
│       │   ├── contexts/    # React contexts
│       │   ├── lib/         # API utilities
│       │   ├── pages/       # Page components
│       │   └── App.jsx     # Main app component
│       ├── public/
│       └── package.json
├── docs/                   # Documentation
├── project_plan.md         # Detailed project plan
└── README.md              # This file
```

## 🚀 Quick Start

### Prerequisites

- Node.js (v18 or higher)
- PostgreSQL (v12 or higher)
- npm or pnpm package manager

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd interior-design-system
   ```

2. **Set up the database**
   ```bash
   # Install PostgreSQL (Ubuntu/Debian)
   sudo apt update
   sudo apt install postgresql postgresql-contrib
   
   # Start PostgreSQL service
   sudo systemctl start postgresql
   sudo systemctl enable postgresql
   
   # Create database
   sudo -u postgres psql -c "CREATE DATABASE interior_design_db;"
   sudo -u postgres psql -c "ALTER USER postgres PASSWORD 'password';"
   ```

3. **Set up the backend**
   ```bash
   cd backend
   npm install
   
   # Initialize database tables
   node -e "const { initializeDatabase } = require('./src/utils/database'); initializeDatabase().then(() => console.log('Database initialized')).catch(console.error);"
   
   # Seed with dummy data
   node src/utils/seedData.js
   
   # Start the backend server
   npm start
   ```

4. **Set up the frontend**
   ```bash
   cd frontend/interior-design-frontend
   pnpm install
   
   # Start the development server
   pnpm run dev --host
   ```

5. **Access the application**
   - Frontend: http://localhost:5173
   - Backend API: http://localhost:5000

## 👥 Demo Credentials

The system comes with pre-configured demo accounts:

| Role | Email | Password |
|------|-------|----------|
| Admin | admin@company.com | password123 |
| Manager | manager@company.com | password123 |
| Designer | designer@company.com | password123 |
| Client | client@company.com | password123 |

## 📖 User Roles & Permissions

### Admin
- Full system access
- User management
- System configuration
- Override approvals
- Generate reports

### Manager
- Project creation and management
- User role assignment
- Approval workflows
- Team oversight
- Analytics access

### Designer
- Design creation and upload
- Task management
- Change log entries
- Client communication
- Project collaboration

### Client
- View assigned projects
- Provide feedback
- Approve/reject designs
- Track project progress
- Access project history

## 🔧 Configuration

### Environment Variables

Backend (`.env`):
```env
PORT=5000
NODE_ENV=development
JWT_SECRET=your-super-secret-jwt-key-here
JWT_EXPIRES_IN=7d

# Database Configuration
DB_HOST=localhost
DB_PORT=5432
DB_NAME=interior_design_db
DB_USER=postgres
DB_PASSWORD=password

# CORS Configuration
CORS_ORIGIN=http://localhost:5173

# File Upload Configuration
UPLOAD_DIR=uploads
MAX_FILE_SIZE=10485760
```

## 📊 Database Schema

The system uses PostgreSQL with the following main tables:

- **users**: User accounts and authentication
- **projects**: Interior design projects
- **designs**: Design files and metadata
- **approvals**: Dual manager approval workflow
- **changelogs**: Change tracking and audit trail
- **tasks**: Task assignment and tracking
- **feedback**: Client feedback and comments

## 🔒 Security Features

- JWT-based authentication
- Role-based access control
- Password hashing with bcrypt
- CORS protection
- Input validation and sanitization
- Audit logging for all changes
- Secure file upload handling

## 🚀 Deployment

### Production Deployment

1. **Environment Setup**
   - Set `NODE_ENV=production`
   - Use strong JWT secrets
   - Configure production database
   - Set up SSL certificates

2. **Backend Deployment**
   ```bash
   cd backend
   npm install --production
   npm start
   ```

3. **Frontend Build**
   ```bash
   cd frontend/interior-design-frontend
   pnpm build
   # Serve the dist/ folder with a web server
   ```

### Docker Deployment (Optional)

Docker configurations can be added for containerized deployment.

## 📚 API Documentation

The backend provides RESTful APIs for all system functionality:

- **Authentication**: `/api/auth/*`
- **Users**: `/api/users/*`
- **Projects**: `/api/projects/*`
- **Designs**: `/api/designs/*`
- **Approvals**: `/api/approvals/*`
- **Change Logs**: `/api/changelogs/*`
- **Tasks**: `/api/tasks/*`
- **Feedback**: `/api/feedback/*`

## 🐛 Troubleshooting

### Common Issues

1. **Database Connection Error**
   - Ensure PostgreSQL is running
   - Check database credentials in `.env`
   - Verify database exists

2. **CORS Errors**
   - Check `CORS_ORIGIN` in backend `.env`
   - Ensure frontend and backend ports match

3. **File Upload Issues**
   - Check `uploads/` directory permissions
   - Verify `MAX_FILE_SIZE` setting

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📄 License

This project is proprietary software developed for internal use.

## 📞 Support

For technical support or questions, please contact the development team.

---

**Version**: 1.0.0  
**Last Updated**: July 2025  
**Developed by**: Interior Design System Team

