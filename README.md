# AWS Exam System

![License](https://img.shields.io/github/license/vanhoangkha/Exam-System?style=flat-square)
![Stars](https://img.shields.io/github/stars/vanhoangkha/Exam-System?style=flat-square)
![Last Commit](https://img.shields.io/github/last-commit/vanhoangkha/Exam-System?style=flat-square)
![Language](https://img.shields.io/github/languages/top/vanhoangkha/Exam-System?style=flat-square)



A production-ready online examination platform built with Next.js 14, featuring real-time exam taking, automated grading, and comprehensive analytics.

## Overview

This system provides a complete solution for creating, managing, and taking online exams. Built with modern web technologies and deployed on AWS infrastructure for scalability and reliability.

**Key Features:**
- User authentication with role-based access control
- Real-time exam taking with auto-save functionality
- Automated grading and instant results
- Progress tracking and analytics
- Responsive design for all devices
- Production-ready AWS deployment

## Tech Stack

**Frontend:**
- Next.js 14 (App Router)
- React 18
- TypeScript
- Tailwind CSS

**Backend:**
- Next.js API Routes
- Prisma ORM
- PostgreSQL (production) / SQLite (development)
- NextAuth.js for authentication

**Testing:**
- Jest for unit and integration tests
- Playwright for end-to-end tests
- Testing Library for component tests

**Infrastructure:**
- AWS ECS (Fargate)
- AWS RDS (PostgreSQL)
- Application Load Balancer
- CloudWatch for monitoring
- Terraform for infrastructure as code

## Getting Started

### Prerequisites

- Node.js 18+ and npm
- PostgreSQL (for production) or SQLite (for development)
- AWS CLI configured (for deployment)

### Installation

```bash
# Clone the repository
git clone https://github.com/vanhoangkha/Exam-System.git
cd Exam-System

# Install dependencies
npm install

# Set up environment variables
cp .env.example .env.local
# Edit .env.local with your configuration

# Initialize database
npm run db:push
npm run db:seed

# Start development server
npm run dev
```

Visit `http://localhost:3000` to see the application.

### Environment Variables

```env
DATABASE_URL="postgresql://user:password@localhost:5432/examdb"
NEXTAUTH_SECRET="your-secret-key"
NEXTAUTH_URL="http://localhost:3000"
```

## Project Structure

```
Exam-System/
├── app/                    # Next.js app directory
│   ├── api/               # API routes
│   ├── auth/              # Authentication pages
│   ├── exams/             # Exam-related pages
│   └── dashboard/         # User dashboard
├── components/            # React components
├── lib/                   # Utility functions and configurations
├── prisma/               # Database schema and migrations
├── __tests__/            # Test files
├── terraform/            # Infrastructure as code
└── docs/                 # Documentation
```

## Usage

### For Students

1. Register and log in to your account
2. Browse available exams from the dashboard
3. Start an exam and answer questions
4. Submit when complete to see instant results
5. View your progress and history in the profile section

### For Administrators

1. Log in with admin credentials
2. Create new exams with questions
3. Manage existing exams and questions
4. View student results and analytics
5. Export reports for analysis

## Testing

```bash
# Run all tests
npm run test:all

# Unit tests only
npm run test:unit

# Integration tests
npm run test:integration

# End-to-end tests
npm run test:e2e

# Watch mode for development
npm run test:watch
```

## Deployment

The application is configured for deployment on AWS using Terraform:

```bash
# Navigate to terraform directory
cd terraform

# Initialize Terraform
terraform init

# Review deployment plan
terraform plan

# Deploy infrastructure
terraform apply

# Deploy application
npm run build
# Follow AWS ECS deployment guide in docs/
```

For detailed deployment instructions, see [DEPLOYMENT_GUIDE.md](docs/DEPLOYMENT_GUIDE.md).

## Architecture

The system follows a clean architecture pattern with clear separation of concerns:

- **Presentation Layer**: Next.js pages and React components
- **Application Layer**: Business logic and use cases
- **Infrastructure Layer**: Database access and external services
- **Domain Layer**: Core business entities and rules

For detailed architecture documentation, see [ARCHITECTURE.md](docs/ARCHITECTURE.md).

## Performance

- Server-side rendering for optimal initial load
- Automatic code splitting and lazy loading
- Optimized database queries with Prisma
- CloudWatch monitoring and alerting
- Auto-scaling based on demand

## Security

- Secure authentication with NextAuth.js
- Password hashing with bcrypt
- SQL injection prevention with Prisma
- CSRF protection
- Rate limiting on API endpoints
- Environment variable management

## Contributing

Contributions are welcome. Please follow these steps:

1. Fork the repository
2. Create a feature branch
3. Make your changes with tests
4. Submit a pull request

## License

MIT License - see [LICENSE](LICENSE) file for details.

## Support

For issues and questions:
- Create an issue in the GitHub repository
- Check existing documentation in the `docs/` folder
- Review the [FAQ](docs/FAQ.md)

## Acknowledgments

Built with modern web technologies and best practices for production deployment on AWS infrastructure.
