# GitHub OAuth Authentication App

A Node.js web application that demonstrates OAuth authentication using GitHub's OAuth service. This project allows users to sign in with their GitHub accounts and access protected routes.

## 🚀 Features

- **GitHub OAuth Integration**: Secure authentication using GitHub OAuth 2.0
- **Session Management**: Persistent user sessions with express-session
- **Protected Routes**: Middleware to protect authenticated-only routes
- **Responsive UI**: Clean and responsive design using Skeleton CSS framework
- **EJS Templates**: Dynamic server-side rendering with EJS

## 📋 Prerequisites

Before running this application, make sure you have the following installed:

- [Node.js](https://nodejs.org/) (v12 or higher)
- [npm](https://www.npmjs.com/) (comes with Node.js)
- A GitHub account

## 🛠️ Installation & Setup

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd github-OAuth
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Create a GitHub OAuth App

1. Go to [GitHub Developer Settings](https://github.com/settings/developers)
2. Click "New OAuth App"
3. Fill in the application details:
   - **Application name**: Your app name
   - **Homepage URL**: `http://localhost:3000`
   - **Authorization callback URL**: `http://localhost:3000/auth/github/callback`
4. Click "Register application"
5. Copy the **Client ID** and **Client Secret**

### 4. Environment Configuration

Create a `.env` file in the root directory:

```env
GITHUB_CLIENT_ID=your_github_client_id_here
GITHUB_CLIENT_SECRET=your_github_client_secret_here
```

**⚠️ Important**: Never commit your `.env` file to version control. Add it to `.gitignore`.

### 5. Create .gitignore (if not exists)

```gitignore
node_modules/
.env
*.log
.DS_Store
```

## 🚀 Running the Application

### Development Mode (with auto-restart)
```bash
npm run dev
```

### Production Mode
```bash
npm start
```

The application will be available at `http://localhost:3000`

## 📱 How to Use

1. **Home Page**: Navigate to `http://localhost:3000` to see the welcome page
2. **Login**: Click "Login with GitHub" or go to `/login`
3. **GitHub Authorization**: You'll be redirected to GitHub to authorize the app
4. **Account Page**: After successful login, access your account information at `/account`
5. **Logout**: Click the logout button to end your session

## 🛣️ Routes

| Route | Method | Description | Authentication |
|-------|---------|-------------|----------------|
| `/` | GET | Home page | Public |
| `/login` | GET | Login page | Public |
| `/logout` | GET | Logout and redirect to home | Authenticated |
| `/account` | GET | User account information | Protected |
| `/auth/github` | GET | Initiate GitHub OAuth flow | Public |
| `/auth/github/callback` | GET | GitHub OAuth callback | Public |

## 🏗️ Project Structure

```
├── app.js                 # Main application file
├── package.json           # Project dependencies and scripts
├── .env                   # Environment variables (create this)
├── public/                # Static files
│   └── css/
│       ├── normalize.css  # CSS reset
│       ├── skeleton.css   # CSS framework
│       └── style.css      # Custom styles
└── views/                 # EJS templates
    ├── layout.ejs         # Layout template
    ├── index.ejs          # Home page
    ├── login.ejs          # Login page
    └── account.ejs        # Account page
```

## 🔧 Technologies Used

- **Backend**: Node.js, Express.js
- **Authentication**: Passport.js with GitHub Strategy
- **Templating**: EJS (Embedded JavaScript)
- **Session Management**: express-session
- **CSS Framework**: Skeleton CSS
- **Environment Variables**: dotenv

## 🔐 Security Features

- **Session Security**: Secure session configuration
- **OAuth 2.0**: Industry-standard authentication protocol
- **Route Protection**: Middleware to protect sensitive routes
- **Environment Variables**: Secure storage of sensitive credentials

## 🐛 Troubleshooting

### Common Issues:

1. **"Cannot GET /auth/github/callback"**
   - Check that your GitHub OAuth callback URL matches exactly: `http://localhost:3000/auth/github/callback`

2. **"Missing credentials"**
   - Ensure your `.env` file exists and contains valid GitHub Client ID and Secret
   - Restart the server after creating/modifying the `.env` file

3. **"Port already in use"**
   - Change the PORT variable in `app.js` or kill the process using port 3000

4. **Authentication fails**
   - Verify your GitHub OAuth app settings
   - Check that the callback URL is correctly configured

## 📝 Development Notes

- The app uses `express-session` for session management
- Sessions are stored in memory (not suitable for production)
- For production deployment, consider using a session store like Redis
- The app currently runs on port 3000 by default

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the ISC License.

## 🆘 Support

If you encounter any issues or have questions, please:

1. Check the troubleshooting section above
2. Review the GitHub OAuth documentation
3. Open an issue in the repository

---

**Happy Coding! 🎉**