# 🚀 EBX Workflow Connector - Production Releases

> **DEPLOYMENT PACKAGES ONLY** - This repository contains production-ready deployment artifacts without source code.

## 📦 What's Here

This repository provides **production deployment packages** for the EBX Workflow Connector:

- ✅ **WAR Files** - Ready-to-deploy Tomcat applications
- ✅ **Configuration Templates** - Complete config.properties with all settings
- ✅ **Documentation** - User guides, release notes, quick references
- ✅ **Deployment Scripts** - Verification and installation tools

## 🚫 What's NOT Here

- ❌ **Source Code** - Not included for security and IP protection
- ❌ **Build Tools** - Maven configurations and build scripts
- ❌ **Development Tools** - IDE configurations and development utilities
- ❌ **Test Code** - Unit tests and development test files

## 🎯 Current Release: v1.1.0

### Key Features
- **Zero Hardcoded Values**: Complete configuration-driven architecture
- **Non-Technical Test Interface**: Simple `/test/` endpoint for easy testing
- **EBX Workflow Integration**: Script tasks for automated MCP tool execution
- **Production Ready**: 16MB WAR deployment with comprehensive documentation

### Download Files
Navigate to the `v1.1.0/` folder or GitHub Releases section to download:
- `ebx-workflow-connector.war` (16MB) - Main application
- `config.properties` (9KB) - Configuration template
- `RELEASE_NOTES_v1.1.0.md` - Complete release documentation
- `NON_TECHNICAL_USER_GUIDE.md` - User-friendly guide
- `QUICK_REFERENCE_CARD.md` - Printable reference
- `verify_deployment.sh` - Deployment verification

## 🚀 Quick Deploy

### 1. Download Release Package
```bash
# Download from this repository
git clone https://github.com/Poppy1972/EBXWorkflowConnector-Releases.git
cd EBXWorkflowConnector-Releases/v1.1.0/
```

### 2. Deploy to Tomcat
```bash
# Copy WAR to Tomcat
cp ebx-workflow-connector.war $TOMCAT_HOME/webapps/

# Customize configuration
cp config.properties $TOMCAT_HOME/conf/
# Edit config.properties with your settings

# Start Tomcat
$TOMCAT_HOME/bin/startup.sh
```

### 3. Test Installation
```bash
# Verify deployment
./verify_deployment.sh

# Test web interface
curl -X POST http://localhost:8080/ebx-workflow-connector/test/execute \
  -H "Content-Type: application/json" \
  -d '{"task": "verify address", "data": "{\"address\": \"123 Main St\"}"}'

# Or open browser to:
# http://localhost:8080/ebx-workflow-connector/test/
```

## 📋 System Requirements

- **Java Runtime**: JRE 17+
- **Application Server**: Tomcat 9.0+, WebSphere Liberty, JBoss EAP
- **Memory**: Minimum 512MB, Recommended 1GB
- **Disk Space**: 50MB for application
- **EBX Version**: Tibco EBX 6+

## 🧪 Testing Options

### 1. Non-Technical Web Interface
- Open: `http://localhost:8080/ebx-workflow-connector/test/`
- Use template buttons for Address, Company, IBAN verification
- Real-time results with execution times

### 2. REST API Testing
```bash
curl -X POST http://localhost:8080/ebx-workflow-connector/test/execute \
  -H "Content-Type: application/json" \
  -d '{"task": "verify address", "data": "{\"address\": \"123 Main St\"}", "guide": "use multiple providers"}'
```

### 3. EBX Workflow Integration
- Script Task Beans: `mcpExecutor` and `mcpBatchExecutor`
- Automatic parameter handling from workflow context
- Configurable MCP server selection

## 📚 Documentation

All documentation is included in each release folder:

### User Documentation
- **NON_TECHNICAL_USER_GUIDE.md** - Complete guide for end users
- **QUICK_REFERENCE_CARD.md** - Printable quick reference
- **RELEASE_NOTES_v1.1.0.md** - Complete technical release notes

### Deployment Documentation
- **verify_deployment.sh** - Automated deployment verification
- **config.properties** - Fully documented configuration template

## 🔒 Security & Compliance

- **No Source Code Exposure**: Only deployment artifacts provided
- **Configuration Security**: Sensitive values via environment variables
- **Production Hardened**: Tested deployment packages
- **Enterprise Ready**: Compatible with corporate environments

## 🆘 Support

### Self-Help Resources
1. **Run verification script**: `./verify_deployment.sh`
2. **Check documentation**: Read the user guides in the release folder
3. **Test with templates**: Use the web interface with example data
4. **Review configuration**: Verify all settings in `config.properties`

### Troubleshooting
- **Deployment Issues**: Check Java 17+ requirement and Tomcat logs
- **Configuration Problems**: Verify `config.properties` syntax and values
- **Performance Issues**: Review memory allocation and connection settings

---

**🔒 Production Deployment Repository - No Source Code**

**🚀 Generated with [Claude Code](https://claude.ai/code)**

**📅 Last Updated**: June 2025 | **📦 Latest Release**: v1.1.0