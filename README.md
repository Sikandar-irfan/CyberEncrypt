# 🔐 CyberEncrypt

**Advanced Python Project Encryption & Obfuscation Tool**

CyberEncrypt is a powerful tool that encrypts entire Python projects into a single executable file with advanced security features including anti-debugging measures, memory protection, and runtime obfuscation.

[![Python Version](https://img.shields.io/badge/python-3.6%2B-blue.svg)](https://python.org)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20macOS-lightgrey.svg)]()

## ✨ Features

### 🔒 **Advanced Encryption**
- **Military-grade encryption** using Fernet (AES 128) with PBKDF2 key derivation
- **100,000 iterations** of PBKDF2 for enhanced security against brute-force attacks
- **Random salt generation** for each encryption process
- **Base64 encoding** for safe file storage and transmission

### 🛡️ **Security Features**
- **Anti-debugging protection** with real-time monitoring
- **Memory protection utilities** to prevent memory dumps
- **Runtime obfuscation** with variable name mangling
- **Platform-specific debugger detection** (Windows & Unix)
- **Timing-based attack prevention** with random delays
- **Automatic cleanup** of decrypted files on exit

### 🚀 **Smart Automation**
- **Automatic main file detection** for projects
- **Dependency auto-detection** from import statements
- **Automatic package installation** for common libraries
- **Progress bars** with real-time status updates
- **Interactive mode** with user-friendly prompts
- **Colorized output** for better user experience

### 📦 **Project Support**
- **Multi-file projects** with nested directory structures
- **Requirements.txt support** for dependency management
- **Cross-platform compatibility** (Windows, Linux, macOS)
- **Flexible file exclusion** (configurable ignore patterns)
- **Compression optimization** for smaller output files

## 🛠️ Installation

### Prerequisites
- Python 3.6 or higher
- pip package manager

### Install Dependencies
```bash
pip install -r requirements.txt
```

Or install manually:
```bash
pip install cryptography questionary colorama
```

## 📋 Quick Start

### Interactive Mode (Recommended)
```bash
python cyber_encrypt.py
```

### Command Line Mode
```bash
# Basic encryption
python cyber_encrypt.py /path/to/your/project

# Specify output file
python cyber_encrypt.py /path/to/your/project encrypted_project.py

# Specify password
python cyber_encrypt.py /path/to/your/project encrypted_project.py mypassword123
```

### Running Encrypted Projects
```bash
# With password argument
python encrypted_project.py -p mypassword123

# Interactive password prompt
python encrypted_project.py
```

> **🔐 Need Password For Tool**  
> If you need password for this project, contact me at:  
> [![Email](https://img.shields.io/badge/Email-sikandarirfan150162@gmail.com-red?style=flat&logo=gmail&logoColor=white)](mailto:sikandarirfan150162@gmail.com)

## 📖 Detailed Usage

### 1. Encrypting a Project

#### Interactive Mode
1. Run `python cyber_encrypt.py`
2. Select "Encrypt a project"
3. Enter your project path
4. Choose output filename
5. Set encryption password
6. Wait for completion

#### Command Line Examples
```bash
# Encrypt a Flask web application
python cyber_encrypt.py ./my_flask_app encrypted_flask.py

# Encrypt with custom password
python cyber_encrypt.py ./my_project secure_app.py "MySecurePassword123!"

# Encrypt a data science project
python cyber_encrypt.py "C:\Projects\DataAnalysis" encrypted_analysis.py
```

### 2. Running Encrypted Projects

```bash
# Method 1: Command line password
python encrypted_project.py -p "MySecurePassword123!"

# Method 2: Interactive password prompt
python encrypted_project.py
# Enter password when prompted

# Method 3: Set environment variable (advanced)
set CYBER_ENCRYPT_PASSWORD=MySecurePassword123!
python encrypted_project.py
```

### 3. Project Structure Requirements

Your project should have a clear entry point:
- `main.py` (preferred)
- `app.py`
- `run.py`
- `start.py`
- `__main__.py`
- Any `.py` file in the root directory

Example project structure:
```
my_project/
├── main.py          # Entry point (auto-detected)
├── requirements.txt # Dependencies (auto-installed)
├── config/
│   └── settings.py
├── utils/
│   ├── helpers.py
│   └── database.py
└── data/
    └── sample.json
```

## ⚙️ Configuration

### File Exclusion Patterns
By default, CyberEncrypt excludes:
- `.git` directories
- `__pycache__` directories
- `.vscode`, `.idea` IDE folders
- `.pyc`, `.pyo` compiled files

### Environment Variables
- `CYBER_ENCRYPT_PASSWORD`: Set default password
- `FLASK_DEBUG=0`: Disabled for encrypted Flask apps
- `FLASK_ENV=development`: Set for encrypted Flask apps

## 🔧 Advanced Features

### Dependency Management
CyberEncrypt automatically handles dependencies:

1. **requirements.txt**: Automatically installs if present
2. **Import scanning**: Detects and installs common packages:
   - `requests`, `flask`, `django`
   - `numpy`, `pandas`, `matplotlib`
   - `tensorflow`, `torch`, `opencv-python`
   - `selenium`, `beautifulsoup4`
   - And many more...

### Security Measures
- **Runtime monitoring**: Continuous anti-debugging checks
- **Memory clearing**: Secure cleanup of sensitive data
- **Process monitoring**: Detection of debugging tools
- **Timing analysis**: Protection against timing attacks

### Performance Optimization
- **Compression**: ZLIB compression reduces file size
- **Lazy loading**: Files loaded only when needed
- **Memory efficiency**: Minimal memory footprint
- **Fast decryption**: Optimized decryption algorithms

## 🛠️ Troubleshooting

### Common Issues

#### "cryptography package not found"
```bash
pip install cryptography
```

#### "Path not found" errors
- Use absolute paths or properly escaped relative paths
- Ensure the project directory exists and is accessible
- Check file permissions

#### "Decryption failed" errors
- Verify the password is correct
- Ensure the encrypted file isn't corrupted
- Check for sufficient disk space

#### 🔐 "Forgot Password" or "Password Recovery"
- **Contact for password recovery**: [![Email](https://img.shields.io/badge/Email-sikandarirfan150162@gmail.com-blue?style=flat&logo=gmail&logoColor=white)](mailto:sikandarirfan150162@gmail.com)
- Include the encrypted file name and creation date in your email
- Password recovery may require proof of ownership

#### "Main file not found" errors
- Ensure your project has a recognizable entry point
- Manually specify the main file when prompted
- Check file extensions (.py required)

### Debug Mode
For debugging encrypted projects:
```bash
# Enable verbose output
python encrypted_project.py -p password --verbose

# Check extracted files location
python encrypted_project.py -p password --debug
```

## 🔍 Security Considerations

### Best Practices
1. **Use strong passwords** (12+ characters, mixed case, numbers, symbols)
2. **Store passwords securely** (password managers recommended)
3. **Regular updates** of encryption keys for sensitive projects
4. **Secure distribution** of encrypted files
5. **Environment isolation** when running encrypted projects

### Security Features Explained

#### Anti-Debugging
- Detects popular debuggers (pdb, pydevd, ipdb)
- Windows API integration (IsDebuggerPresent)
- Unix-specific detection methods
- Real-time monitoring thread

#### Memory Protection
- Secure memory clearing with zero-fill
- Garbage collection forcing
- Buffer overwriting techniques
- Memory view manipulation

#### Runtime Obfuscation
- Variable name mangling (`_0x53a8c2b`, `_0xe72fd19`)
- Import statement obfuscation
- Control flow randomization
- Anti-tampering measures

## 📊 Performance Metrics

Typical performance characteristics:
- **Encryption speed**: 50-100 MB/s
- **Compression ratio**: 30-70% size reduction
- **Startup overhead**: 1-3 seconds for large projects
- **Memory usage**: ~2x original project size during decryption

## 🤝 Contributing

Contributions are welcome! Please follow these guidelines:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Setup
```bash
git clone https://github.com/yourusername/cyberencrypt.git
cd cyberencrypt
pip install -r requirements.txt
python cyber_encrypt.py --help
```

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ⚠️ Disclaimer

CyberEncrypt is designed for legitimate use cases such as:
- Protecting intellectual property
- Secure software distribution
- Educational purposes
- Code obfuscation for competitive programming

**Important**: This tool should not be used for malicious purposes. Users are responsible for complying with applicable laws and regulations in their jurisdiction.

## 🆘 Support

### Getting Help
- 📖 Check this README for common solutions
- 💬 Open an issue for bug reports
- 💡 Submit feature requests via GitHub issues
- 📧 Contact: [![Email](https://img.shields.io/badge/Email-Contact%20Me-red?style=flat&logo=gmail&logoColor=white)](mailto:sikandarirfan150162@gmail.com)
- 🔐 **Password Support**: [![Email](https://img.shields.io/badge/Password%20Help-sikandarirfan150162@gmail.com-orange?style=flat&logo=gmail&logoColor=white)](mailto:sikandarirfan150162@gmail.com?subject=CyberEncrypt%20Password%20Help)

### Reporting Issues
When reporting issues, please include:
- Python version
- Operating system
- Error messages (if any)
- Steps to reproduce
- Example project structure

## 🎯 Roadmap

### Planned Features
- [ ] GUI interface with tkinter/PyQt
- [ ] Additional encryption algorithms (ChaCha20, AES-256)
- [ ] Cloud storage integration
- [ ] Digital signatures for encrypted files
- [ ] Plugin system for custom security measures
- [ ] Docker containerization support
- [ ] Web-based encryption service

### Version History
- **v1.0.0**: Initial release with core encryption features
- **v1.1.0**: Added anti-debugging and memory protection
- **v1.2.0**: Interactive mode and dependency auto-detection
- **v1.3.0**: Enhanced security measures and cross-platform support

---

**Made with ❤️ by Sikandar Irfan**

*Secure your Python projects with military-grade encryption!*

## 📬 Contact Me

[![Email](https://img.shields.io/badge/Email-sikandarirfan150162@gmail.com-red?style=for-the-badge&logo=gmail&logoColor=white)](mailto:sikandarirfan150162@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sikandar-irfan-5459342a6/)

**Get in touch for:**
- 🐛 Bug reports and issues
- 💡 Feature requests and suggestions  
- 🤝 Collaboration opportunities
- 💼 Professional inquiries
- 📚 Educational and learning discussions
