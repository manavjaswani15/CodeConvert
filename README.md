
# CodeConvert - AI-Powered Code Translation & Performance Analysis
An intelligent code translation tool that converts code between multiple programming languages with complexity analysis and real-time performance testing.

## 🚀 Features

### Code Translation
- **Multi-Language Support**: Translate between C++, Python, Java, and JavaScript
- **AI-Powered**: Uses Google Gemini AI for accurate translations
- **Smart Adaptation**: Converts code while maintaining functionality and following language best practices
- **Detailed Explanations**: Get insights into translation decisions and changes made

### Performance Analysis
- **Complexity Analysis**: Automatic Big O notation analysis for time and space complexity
- **Theoretical Comparison**: Compare algorithmic efficiency between original and translated code
- **Practical Testing**: Real-time CPU usage and execution time measurements
- **Memory Monitoring**: Track memory consumption during code execution
- **Performance Visualization**: Compare code execution metrics side-by-side

## 📋 Prerequisites

### Required
- Node.js (v16 or higher)
- npm or yarn

### For Code Execution & Performance Testing
To enable full functionality including CPU performance analysis, install:
- **Python** - For Python code execution
- **Node.js** - For JavaScript code execution  
- **g++ (MinGW)** - For C++ code compilation and execution
- **Java JDK** - For Java code compilation and execution
See [COMPILER_SETUP.md](./COMPILER_SETUP.md) for detailed installation instructions.

## 🛠️ Installation
1. **Clone the repository**
```bash
git clone <your-repo-url>
cd CodeConvert
```
2. **Install dependencies**
```bash
npm install
```
3. **Set up environment variables**
Create a `.env` file in the root directory:
```env
GEMINI_API_KEY_1=your_gemini_api_key_1
GEMINI_API_KEY_2=your_gemini_api_key_2
GEMINI_API_KEY_3=your_gemini_api_key_3
GEMINI_API_KEY_4=your_gemini_api_key_4
GEMINI_API_KEY_5=your_gemini_api_key_5
NODE_ENV=development
```
Get your Gemini API keys from: https://makersuite.google.com/app/apikey

4. **Start the development server**
```bash
npm run dev
```
The application will be available at:
- Frontend: http://localhost:3000
- Backend API: http://localhost:4000

## 🎯 Usage

### Basic Translation
1. Select source language (C++, Python, Java, or JavaScript)
2. Enter or paste your code in the source editor
3. Select target language
4. Click "Translate Code"
5. View translated code with explanations and complexity analysis

### Performance Testing
1. After translating code, scroll to "CPU & Performance Analysis"
2. Click "Run CPU Performance Test"
3. View real-time comparison of:
   - CPU usage for both codes
   - Execution time
   - Memory consumption
   - Practical winner determination

### Understanding Results
- **Green indicators**: Better performance/lower usage
- **Orange indicators**: Similar performance
- **Red indicators**: Higher resource usage
- **Error messages**: Check that required compilers are installed

## 🏗️ Project Structure
```
CodeConvert/
├── client/               # Frontend React application
│   ├── src/
│   │   ├── components/  # UI components
│   │   ├── pages/       # Page components
│   │   ├── hooks/       # Custom React hooks
│   │   └── lib/         # Utilities and API client
├── server/              # Backend Express server
│   ├── services/        # Business logic services
│   │   ├── gemini-provider.ts    # AI translation service
│   │   ├── code-executor.ts      # Code execution engine
│   │   └── system-monitor.ts     # System metrics monitoring
│   ├── routes.ts        # API endpoints
│   └── index.ts         # Server entry point
└── shared/              # Shared types and schemas
```

## 🔧 API Endpoints

### POST /api/translate
Translate code between languages
```json
{
  "sourceCode": "def hello():\n    print('Hello')",
  "sourceLanguage": "python",
  "targetLanguage": "cpp"
}
```

### POST /api/performance/test
Run performance comparison test
```json
{
  "originalCode": "...",
  "originalLanguage": "python",
  "translatedCode": "...",
  "translatedLanguage": "cpp"
}
```

### GET /api/system/metrics
Get current system metrics (CPU, memory)

### GET /api/translations/recent
Get recent translations history

## ⚙️ Configuration

### Multiple API Keys
The system supports multiple Gemini API keys for better rate limiting:
- Automatically rotates between keys when one hits rate limits
- Tracks retry delays for each key
- Falls back to alternative models when primary is overloaded

### Supported Models
- `gemini-2.5-flash` (default - fastest)
- `gemini-2.0-flash`
- `gemini-flash-latest`
- `gemini-2.5-pro`
- `gemini-pro-latest`

## 🐛 Troubleshooting

### Code Execution Fails
1. **"spawn ENOENT" or "not recognized"**: Compiler not installed or not in PATH
   - See [COMPILER_SETUP.md](./COMPILER_SETUP.md)
   - Restart terminal after installation
   
2. **Rate limit errors**: Add more API keys to `.env`

3. **Model overloaded**: System automatically tries alternative models

### Translation Errors
1. Ensure GEMINI_API_KEY is valid
2. Check internet connection
3. Verify source code syntax is correct

## 📝 Development

### Running Tests
```bash
# Test code executor
npx tsx server/test-executor.ts
# Test Gemini API
npx tsx server/test-gemini.ts
# Test translation service
npx tsx server/test-translate.ts
```

### Build for Production
```bash
npm run build
```

## 🤝 Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License
This project is licensed under the MIT License.

## 🙏 Acknowledgments
- Google Gemini AI for powering the translation engine
- The open-source community for various tools and libraries used in this project

## 📞 Support
For issues and questions:
1. Check [COMPILER_SETUP.md](./COMPILER_SETUP.md) for compiler installation
2. Review error messages in the browser console
3. Check server logs for API errors
4. Open an issue on GitHub
---

Made with using Google Gemini API by SRT :)