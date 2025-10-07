# Veritas AI - Insurance Claims Fraud Detection Platform

## 🚀 Overview

Veritas AI is an AI-powered insurance claims fraud detection platform that accelerates and authenticates the claim verification process for insurance companies. Built with React, TypeScript, and Tailwind CSS, it provides a comprehensive solution for claim analysis, fraud detection, and investigative workflows.

## ✨ Features

### 🔐 Authentication System
- User registration and login
- JWT token-based authentication
- Persistent user sessions with localStorage
- Personalized user experience

### 📊 Dashboard
- Real-time claims statistics
- Quick action buttons for common tasks
- Recent claims overview
- Personalized welcome interface

### 📋 Claims Management
- **Multi-step claim creation** with detailed form validation
- **Drag-and-drop file upload** with S3 integration
- **Real-time upload progress** tracking
- **Claims listing** with filtering and sorting
- **Detailed claim analysis** pages

### 🤖 AI-Powered Analysis
- **Automated fraud detection** with risk scoring
- **Evidence analysis** including image metadata examination
- **Timeline inconsistency detection**
- **Pattern matching** against historical fraud cases
- **Comprehensive fraud risk reports**

### 🕵️ AI Co-pilot (Investigator's Cockpit)
- **Interactive chat interface** for claim investigation
- **Real-time AI responses** for investigative queries
- **Claim-specific analysis** with contextual insights
- **Quick action buttons** for common investigation tasks

### 🎨 Modern UI/UX
- **Dark theme** with professional design
- **Responsive layout** for all screen sizes
- **Interactive components** with smooth animations
- **Accessibility-compliant** interface

## 🛠️ Tech Stack

### Frontend
- **React 18** - Modern React with hooks
- **TypeScript** - Type-safe development
- **Tailwind CSS** - Utility-first styling
- **Redux Toolkit** - State management
- **React Router** - Client-side routing
- **Chart.js** - Data visualization

### Backend Integration
- **REST API** integration with Python FastAPI backend
- **JWT Authentication** with Bearer tokens
- **AWS S3** file upload with presigned URLs
- **Real-time data** fetching and updates

### AWS Tools Deployed
- **AWS Bedrock** For the smart comprehension of analyzed data and risk score generation
- **AWS S3** For storing claim files ansd contents
- **AWS Q** For AI copilot for further investigation of claims
- **AWS Rekognition** For deep analysis of image content for odd things.

## 📁 Project Structure

```
Veritas_AI/
├── public/                     # Static assets
├── src/
│   ├── components/            # Reusable UI components
│   │   ├── common/           # Shared components (Modal, Icons, etc.)
│   │   └── features/         # Feature-specific components
│   ├── pages/                # Main application pages
│   │   ├── Landing.tsx       # Marketing landing page
│   │   ├── Dashboard.tsx     # Main dashboard
│   │   ├── Claims.tsx        # Claims management
│   │   ├── ClaimDetail.tsx   # Individual claim analysis
│   │   ├── AICopilot.tsx     # AI investigation interface
│   │   ├── Login.tsx         # Authentication
│   │   └── Signup.tsx        # User registration
│   ├── layouts/              # Page layout components
│   │   └── DashboardLayout.tsx
│   ├── services/             # API integration
│   │   └── api.ts            # Centralized API service
│   ├── redux/                # State management
│   │   ├── store.ts          # Redux store configuration
│   │   └── features/         # Redux slices
│   ├── types/                # TypeScript type definitions
│   └── styles/               # Global styles
├── package.json              # Dependencies and scripts
├── tailwind.config.js        # Tailwind CSS configuration
├── tsconfig.json            # TypeScript configuration
└── vite.config.ts           # Vite build configuration
```

## 🚀 Getting Started

### Prerequisites
- Node.js 18+ 
- npm or yarn
- Git

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/your-username/veritas-ai.git
cd veritas-ai
```

2. **Install dependencies**
```bash
npm install
```

3. **Environment Setup**
Create a `.env` file in the root directory:
```env
VITE_API_BASE_URL=https://veritas-ai-backend-db28.onrender.com/api/v1
```

4. **Start development server**
```bash
npm run dev
```

The application will be available at `http://localhost:5173`

### Build for Production

```bash
npm run build
npm run preview
```

## 🔧 Configuration

### Tailwind CSS v4
The project uses Tailwind CSS v4 with the new configuration:
- Import: `@import "tailwindcss"` in CSS files
- PostCSS plugin: `@tailwindcss/postcss`

### API Integration
All API calls are centralized in `src/services/api.ts`:
- Authentication endpoints
- Claims CRUD operations
- File upload to S3
- AI investigation queries

## 📱 User Workflows

### 1. Claim Submission Flow
1. **Login/Register** - User authentication
2. **Create Claim** - Multi-step form with evidence upload
3. **File Upload** - Drag-and-drop with progress tracking
4. **Analysis Trigger** - Immediate "Run Analysis" button
5. **Results Display** - Fraud risk score and detailed report

### 2. Investigation Workflow
1. **Claims Dashboard** - Overview of all claims
2. **Claim Selection** - Choose specific claim for analysis
3. **AI Co-pilot** - Interactive investigation interface
4. **Evidence Analysis** - AI-powered insights and recommendations

## 🔐 Authentication Flow

The application uses JWT-based authentication:
- **Login**: OAuth2 password flow with form data
- **Token Storage**: Secure localStorage persistence
- **Auto-refresh**: Automatic token validation
- **Protected Routes**: Route-level authentication guards

## 📊 State Management

Redux Toolkit is used for state management:
- **Auth Slice**: User authentication and profile data
- **Modal Slice**: UI state for modals and forms
- **Persistent Storage**: User data persistence across sessions

## 🎨 Design System

### Color Palette
- **Background**: `slate-900` (Dark theme)
- **Surfaces**: `slate-800`, `slate-700`
- **Primary**: `emerald-500/600` (Actions and highlights)
- **Text**: `white`, `slate-300`, `slate-400`
- **Status Colors**: `red-400` (High risk), `yellow-400` (Medium), `green-400` (Low)

### Typography
- **Headers**: Bold, large text for page titles
- **Body**: Clean, readable text with proper contrast
- **Code**: Monospace font for claim IDs and technical data

## 🚀 Deployment

### Vercel Deployment
The project is configured for Vercel deployment:
- **Build Command**: `npm run build`
- **Output Directory**: `dist`
- **Node Version**: 18+

### Environment Variables
Set the following in your deployment platform:
```
VITE_API_BASE_URL=your_backend_url
```

## 🧪 Testing

### Manual Testing
- Use the provided HTML test client for API validation
- Test all user workflows end-to-end
- Verify file upload functionality with various file types

### Key Test Scenarios
1. **Authentication**: Login/logout/registration flows
2. **Claim Creation**: Multi-step form with file uploads
3. **Analysis**: Trigger analysis and view results
4. **AI Co-pilot**: Interactive investigation queries

## 🔧 API Endpoints

### Authentication
- `POST /auth/signup` - User registration
- `POST /auth/token` - User login (OAuth2 form data)

### Claims Management
- `GET /claims/` - List all claims
- `POST /claims/` - Create new claim
- `GET /claims/{id}` - Get specific claim
- `POST /claims/{id}/trigger-analysis` - Run fraud analysis

### AI Investigation
- `POST /investigate/{claim_id}/query` - AI investigation queries

## 🐛 Troubleshooting

### Common Issues

1. **Build Errors**
   - Ensure all dependencies are in `dependencies` (not `devDependencies`)
   - Check for case-sensitive import paths

2. **File Upload Issues**
   - Verify S3 presigned URL format
   - Check file upload order (fields first, then file)

3. **Authentication Problems**
   - Clear localStorage and retry login
   - Verify API endpoint URLs

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Commit changes: `git commit -m "Add your feature"`
4. Push to branch: `git push origin feature/your-feature`
5. Open a Pull Request

### Coding Standards
- Use TypeScript for type safety
- Follow React hooks patterns
- Maintain consistent component structure
- Write descriptive commit messages

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Backend API**: FastAPI Python backend with AI/ML integration
- **UI Framework**: React with TypeScript for robust development
- **Styling**: Tailwind CSS for rapid, consistent styling
- **State Management**: Redux Toolkit for predictable state updates
- **File Storage**: AWS S3 for secure file handling

## 📞 Support

For support and questions:
- Create an issue in the GitHub repository
- Contact the development team
- Check the troubleshooting section above

---

**Veritas AI** - Transforming insurance fraud detection with AI-powered analysis and investigation tools.