# 🔐 Failed Login Analyzer

A Python-based security tool that analyzes server log files to detect and report suspicious failed login attempts by tracking IP addresses.

## 📋 Features

- ✅ Parses log files for failed login attempts
- ✅ Extracts and counts IP addresses
- ✅ Identifies most suspicious IP addresses
- ✅ Generates detailed security reports
- ✅ Sorted output by attempt frequency
- ✅ Error handling for missing files

## 🚀 Quick Start

### Prerequisites

- Python 3.6 or higher
- A log file containing failed login attempts

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/failed-login-analyzer.git
cd failed-login-analyzer
```

2. Create the required directory structure:
```bash
mkdir "Python File Handling"
```

3. Place your log file in the `Python File Handling` directory as `log.txt`

### Usage

Run the script:
```bash
python analyzer.py
```

The script will:
- Analyze the log file
- Display results in the console
- Generate a `report.txt` file with detailed findings

## 📁 Project Structure

```
failed-login-analyzer/
│
├── analyzer.py              # Main script
├── Python File Handling/
│   └── log.txt             # Your log file (sample included)
├── report.txt              # Generated report (auto-created)
└── README.md               # This file
```

## 📝 Log File Format

The script expects log entries in the following format:

```
Failed login from 192.168.1.100
Failed login attempt from 10.0.0.5
Failed login for user admin from 172.16.0.1
```

Any line containing "Failed login" followed by an IP address will be parsed.

## 📊 Sample Output

### Console Output
```
Failed Login Attempts:
========================================
192.168.1.100 => 15 attempts
10.0.0.5 => 8 attempts
172.16.0.1 => 3 attempts

Most suspicious IP: 192.168.1.100 => 15 attempts

✓ Report saved to report.txt
```

### Report File (report.txt)
```
Failed Login Report
========================================

192.168.1.100 => 15 attempts
10.0.0.5 => 8 attempts
172.16.0.1 => 3 attempts

Most suspicious IP:
192.168.1.100 => 15 attempts
```

## 🛠️ Technical Details

### Regular Expression Pattern
```python
r'Failed login.*(\d+\.\d+\.\d+\.\d+)'
```
This pattern matches any line containing "Failed login" followed by an IPv4 address.

### Key Components

- **IP Tracking**: Dictionary-based counting for efficient lookup
- **Sorting**: Results sorted by attempt count (descending)
- **File Handling**: UTF-8 encoding support for international characters
- **Error Handling**: Graceful handling of missing files

## 🔧 Customization

### Change Log File Path
Edit the `LOG_FILE` constant in `analyzer.py`:
```python
LOG_FILE = "your/custom/path/log.txt"
```

### Change Report File Path
Edit the `REPORT_FILE` constant:
```python
REPORT_FILE = "custom_report.txt"
```

### Modify Regex Pattern
For different log formats, update the pattern:
```python
pattern = re.compile(r'your_custom_pattern')
```

## 📈 Use Cases

- 🔒 **Security Auditing**: Identify brute force attack attempts
- 📊 **Traffic Analysis**: Monitor failed authentication patterns
- 🚨 **Intrusion Detection**: Detect suspicious IP addresses
- 📝 **Compliance Reporting**: Generate security incident reports

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Your Name**
- GitHub: [@yourusername](https://github.com/yourusername)
- Email: your.email@example.com

## 🙏 Acknowledgments

- Built with Python's powerful `re` module
- Inspired by real-world security monitoring needs
- Thanks to the open-source community

## 📞 Support

If you encounter any issues or have questions:
- Open an [Issue](https://github.com/yourusername/failed-login-analyzer/issues)
- Start a [Discussion](https://github.com/yourusername/failed-login-analyzer/discussions)

## 🔄 Future Enhancements

- [ ] Add geolocation lookup for IP addresses
- [ ] Export reports in JSON/CSV format
- [ ] Real-time log monitoring
- [ ] Email alerts for suspicious activity
- [ ] Web dashboard for visualization
- [ ] Support for multiple log formats

---

⭐ **If you find this project helpful, please consider giving it a star!** ⭐
