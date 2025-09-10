# BIOMIDDLEWARE - Biometric Device Management System

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![Node.js](https://img.shields.io/badge/node.js-v18+-green.svg)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

A comprehensive biometric device management system for enterprise-level multi-device and multi-branch operations. This system provides a unified web-based interface for managing multiple biometric devices, user enrollment, attendance tracking, and comprehensive reporting.

## 🚀 Quick Start

```bash
# Install dependencies
npm install

# Set up environment configuration (first time)
npm run setup

# Validate your configuration
npm run validate

# Start the server
npm start

# Access the application
open http://localhost:5173
```

## 📋 Features

### Core Functionality
- ✅ **Multi-Device Management** - Connect and manage multiple biometric devices
- ✅ **Branch Management** - Organize devices and users by location
- ✅ **User Enrollment** - Face, fingerprint, palm, card, and password enrollment
- ✅ **Attendance Tracking** - Real-time attendance monitoring and reporting
- ✅ **HR Integration** - Complete employee management system
- ✅ **Payroll System** - Attendance-based payroll calculations
- ✅ **API Management** - Secure API key generation and management
- ✅ **Responsive Web UI** - Modern, mobile-friendly interface

### Advanced Features
- 🔄 **Real-time Synchronization** - Automatic device synchronization
- 📊 **Analytics & Reporting** - Comprehensive attendance and performance reports
- 🔒 **Security Features** - API key authentication and secure communication
- 🌐 **Network Scanner** - Automatic device discovery
- 📱 **Device Health Monitoring** - Real-time device status tracking
- 💾 **Data Export** - CSV export for attendance and payroll data

## 🛠 Technology Stack

### Backend
- **Node.js** + **Express.js** - Server runtime and web framework
- **SQLite3** - Lightweight database with full ACID compliance
- **Better-SQLite3** - High-performance database bindings

### Frontend
- **HTML5** + **CSS3** + **Vanilla JavaScript** - Modern web standards
- **CSS Grid** + **Flexbox** - Responsive design
- **Font Awesome** - Icon library

### Key Libraries
```json
{
  "express": "^4.18.2",
  "better-sqlite3": "^8.7.0",
  "cors": "^2.8.5",
  "multer": "^1.4.5",
  "node-cron": "^3.0.2"
}
```

## 📁 Project Structure

```
BIOMIDDLEWARE/
├── server.js              # Main server application
├── package.json           # Dependencies and scripts
├── public/                # Frontend files
│   ├── index.html         # Main application interface
│   ├── styles.css         # Complete stylesheet
│   └── app.js            # Frontend JavaScript
├── data/                 # Database and storage
│   └── biometric.db      # SQLite database
└── docs/                # Documentation
    └── BIOMIDDLEWARE_Documentation.md
```

## 🔧 Configuration

### Environment Setup

BIOMMIDDLEWARE uses a comprehensive environment configuration system:

```bash
# Quick setup with secure defaults
npm run setup

# Interactive setup with prompts for all options
npm run setup:interactive

# Validate current configuration
npm run validate
```

### Configuration Files

- **`.env`** - Your environment configuration (created from template)
- **`.env.example`** - Template with all available options
- **`config/environment.js`** - Configuration loader and validator

### Key Environment Variables

```bash
# Server Configuration
NODE_ENV=development          # Environment (development/production/test)
PORT=5173                     # Server port
HOST=localhost               # Server host

# Security (IMPORTANT: Change in production!)
JWT_SECRET=your-secure-secret # JWT signing secret
CORS_ORIGIN=*                # CORS allowed origins

# Database
DB_PATH=./data/biometric.db  # Database file path
DB_BACKUP_PATH=./data/backups/ # Backup directory
DB_AUTO_BACKUP=true          # Enable automatic backups

# Device Configuration
AUTO_DISCOVERY_ENABLED=true     # Enable device auto-discovery
AUTO_DISCOVERY_NETWORK=192.168.1.0/24 # Network to scan
DEVICE_SYNC_ENABLED=true        # Enable device synchronization

# Feature Flags
FEATURE_BRANCH_MANAGEMENT=true  # Enable branch management
FEATURE_HR_INTEGRATION=true     # Enable HR system
FEATURE_PAYROLL_SYSTEM=true     # Enable payroll calculations
FEATURE_API_RATE_LIMITING=true  # Enable API rate limiting
```

### Production Security Checklist

- ✅ Change `JWT_SECRET` from default value
- ✅ Restrict `CORS_ORIGIN` to specific domains
- ✅ Enable `FEATURE_API_RATE_LIMITING`
- ✅ Set `LOG_LEVEL=warn` or `LOG_LEVEL=error`
- ✅ Enable file logging with `LOG_FILE_ENABLED=true`
- ✅ Configure proper backup retention

### Device Support
- **ZKTeco** devices
- **Hikvision** biometric readers
- **DELI** biometric scanners ✨ (Fully Compatible)
- **Generic HTTP-based** biometric devices
- **Custom protocol** devices (with adapter)

## 📚 API Endpoints

### Branch Management
- `GET /api/branches` - List all branches
- `POST /api/branches` - Create new branch
- `PUT /api/branches/:id` - Update branch
- `DELETE /api/branches/:id` - Delete branch

### Device Management
- `GET /api/devices` - List all devices
- `POST /api/devices/quick-add` - Add device
- `POST /api/devices/:id/connect` - Connect to device
- `DELETE /api/devices/quick-remove` - Remove device

### User Management
- `GET /api/users` - Get users from devices
- `POST /api/users` - Create/update user
- `DELETE /api/users/:id` - Delete user

### Attendance
- `GET /api/attendance/all` - All attendance records
- `GET /api/attendance/today` - Today's attendance
- `POST /api/attendance/uploader` - Configure uploader

## 🔒 Security Features

- **API Key Authentication** - Secure device access
- **CORS Protection** - Cross-origin request security
- **Input Validation** - SQL injection and XSS prevention
- **Usage Tracking** - Monitor API key usage
- **Permission System** - Role-based access control

## 📊 Performance Metrics

- **Devices**: Up to 100 concurrent connections
- **Users**: Up to 10,000 per device
- **Response Time**: < 2 seconds for device operations
- **Concurrent Requests**: 1,000+ simultaneous requests

## 🐛 Troubleshooting

### Common Issues

1. **Device Connection Failed**
   ```bash
   # Check device IP and network connectivity
   ping <device-ip>
   telnet <device-ip> <port>
   ```

2. **Port Already in Use**
   ```bash
   # Kill existing processes
   pkill -f "node server.js"
   # Or use different port
   PORT=8080 npm start
   ```

3. **Database Issues**
   ```bash
   # Check database file permissions
   ls -la data/biometric.db
   # Backup and recreate if needed
   cp data/biometric.db data/biometric.db.backup
   ```

## 📋 Monitoring

### Built-in Monitoring
- Device connection status dashboard
- Real-time performance metrics
- Error logging and reporting
- Usage statistics and analytics

### Log Files
- Application logs in console output
- Database query logs
- Network communication logs
- Error stack traces with timestamps

## 🔄 Maintenance

### Daily Tasks
- Monitor device connectivity
- Review error logs
- Check system performance
- Backup database

### Weekly Tasks
- Review attendance reports
- Update device configurations
- Performance optimization
- Clean up old logs

## 🚀 Deployment

### Local Development
```bash
git clone <repository>
cd BIOMIDDLEWARE
npm install
npm start
```

### Production Deployment
```bash
# Install dependencies
npm ci --only=production

# Set environment
export NODE_ENV=production
export PORT=5173

# Start with process manager
pm2 start server.js --name biomiddleware

# Or use systemd service
sudo systemctl start biomiddleware
```

## 📝 Documentation

For comprehensive documentation, see:
- **[Complete Documentation](./docs/BIOMIDDLEWARE_Documentation.md)** - Full technical documentation
- **API Reference** - Detailed API documentation
- **Database Schema** - Complete database structure
- **Installation Guide** - Step-by-step setup instructions

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 📞 Support

For technical support or questions:
- Create an issue in the repository
- Contact the development team
- Review the troubleshooting guide

---

**Version**: 1.0.0  
**Last Updated**: September 2025  
**Developed by**: BIOMIDDLEWARE Development Team

---

*Transform your biometric device management with BIOMIDDLEWARE - the complete solution for enterprise attendance and access control systems.*
