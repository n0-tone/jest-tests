# JavaScript Mini Tests

An interactive platform to learn and test JavaScript, with an admin dashboard to track student progress. Built with **Node.js**, **Express**, **Jest**, and **Tailwind CSS**.

**Live demo:** Currently Unavailable

---

## Features

### **For Students:**

- Modern, responsive UI with Tailwind CSS
- Authentication system using student ID
- 3 interactive JavaScript exercises:
  - Celsius ↔ Fahrenheit conversion
  - Palindrome checking
  - Array sum
- Safe code execution in the browser
- Local progress tracking (localStorage)
- Real-time visual feedback

### **For Administrators:**

- Dashboard protected with HTTP Basic authentication
- View all student submissions
- Real-time statistics (progress, success rate)
- View the code submitted by each student
- Modern admin interface
- Automatic auto-refresh

### **Test Suite:**

- **77 comprehensive Jest tests**
- Integration tests with Supertest
- Full coverage of APIs and features
- Performance and security tests
- Data validation and edge cases

---

## Project Structure

```
eqs/
├── public/                  # Served static assets
│   ├── index.html           # Main exercises page
│   ├── admin.html           # Admin dashboard
│   ├── admin.js             # Dashboard JavaScript
│   ├── exercises.js         # Exercises JavaScript (copied)
│   └── tailwind.css         # Compiled CSS
├── src/                     # Source code
│   ├── app.js               # Express configuration + API routes
│   ├── server.js            # HTTP server
│   ├── frontend/            # Frontend JavaScript
│   │   └── exercises.js     # Exercise logic (source)
│   └── styles/              # CSS styles
│       └── tailwind.css     # Tailwind source
├── tests/                   # 71 Jest tests
│   ├── app.test.js          # Integration tests
│   ├── utils.test.js        # Utility tests
│   ├── validation.test.js   # Validation tests
│   ├── frontend.test.js     # Frontend tests
│   └── integration.test.js  # Performance tests
├── .env                     # Environment variables (local)
├── .env.example             # Environment variables template
├── jest.config.js           # Jest configuration
├── tailwind.config.js       # Tailwind configuration
├── render.yaml              # Render deployment config
└── package.json             # Dependencies and scripts
```

---

## Local Installation and Run

### 1. **Clone the repository:**

```bash
git clone https://github.com/n0-tone/jest-tests
cd jest-tests
```

### 2. **Install dependencies:**

```bash
npm install
```

### 3. **Configure environment variables:**

```bash
cp .env.example .env
# Edit .env with your admin credentials
```

**`.env` contents:**

```env
ADMIN_USERNAME=some_username
ADMIN_PASSWORD=some_password
PORT=3000
```

### 4. **Build CSS:**

```bash
npm run build:css     # Compile Tailwind CSS
```

### 5. **Run tests:**

```bash
npm test            # 77 Jest tests
```

### 6. **Run in development:**

```bash
npm run dev         # Server + CSS watch
# or
npm start           # Server only
```

**Local access:**

- **Students:** http://localhost:3000
- **Admin:** http://localhost:3000/admin

---

## Available APIs

### **Public:**

- `GET /` - Main exercises page
- `POST /api/submissions` - Submit exercise (students)
- `GET /api/submissions/:studentId` - Submissions for a specific student

### **Protected (HTTP Basic Auth):**

- `GET /admin` - Admin dashboard
- `GET /api/admin/submissions` - All submissions (admin)

**Usage example:**

```bash
# Without authentication (401 Unauthorized)
curl https://gh.no-tone.com/jest-tests/api/admin/submissions

# With authentication (200 OK)
curl -u admin:password https://gh.no-tone.com/jest-tests/api/admin/submissions
```

---

## Test Suite

### **Test coverage (71 total):**

- **`app.test.js`** - Express integration tests (14 tests)
- **`utils.test.js`** - Utility functions (15 tests)
- **`validation.test.js`** - Validation and business logic (17 tests)
- **`frontend.test.js`** - Frontend logic (12 tests)
- **`integration.test.js`** - Performance and integration (17 tests)

**Run tests:**

```bash
npm test                    # All tests
npm test -- app.test.js    # Specific test file
npm test -- --verbose      # Detailed output
```

---

## How to Use (Students)

1. **Access the application**
2. **Enter student ID** (5 digits)
3. **Choose an exercise** to solve
4. **Write JavaScript code**
5. **Run** and see results in real time
6. **Progress is saved** automatically

### **Available exercises:**

1. **Celsius ↔ Fahrenheit** - Temperature conversion
2. **Palindromes** - String checking
3. **Array Sum** - Math operations

---

## Admin Dashboard

**Path:** `/admin` (authentication required)

**Features:**

- Real-time statistics
- List of all students
- Code submitted per exercise
- Exercise status (complete/pending)
- Auto-refresh (30 seconds)
- Global success rate

---

## Security

- HTTP Basic authentication for admin routes
- Input validation on exercises
- Sanitization of executed code
- Hidden Express headers
- Environment variables for credentials
- Protection against XSS and code injection

---

## Available Scripts

```bash
npm start             # Production
npm run dev           # Development (nodemon)
npm test              # Run Jest tests
npm run build:css     # Compile Tailwind CSS
npm run dev:css       # CSS watch mode
npm run render-build  # Full build for Render
```

---

## Technologies

- **Backend:** Node.js, Express.js, dotenv
- **Frontend:** Vanilla JavaScript, Tailwind CSS
- **Testing:** Jest, Supertest
- **Deploy:** Render.com
- **Security:** HTTP Basic Authentication

---

## Authors

- [no-tone](https://github.com/n0-tone)
- [Renaxpto](https://github.com/Renaxpto)
