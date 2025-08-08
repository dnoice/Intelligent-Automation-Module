# Enhanced Intelligent Automation Module (IA) v2.0

> 🤖 AI-powered workflow automation and management system for the command line

[![Version](https://img.shields.io/badge/version-2.0.0-blue.svg)](https://github.com/dnoice/Intelligent-Automation-Module)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](https://github.com/dnoice/Intelligent-Automation-Module/blob/main/LICENSE)
[![Bash](https://img.shields.io/badge/bash-4.0%2B-orange.svg)](https://www.gnu.org/software/bash/)
[![GitHub Stars](https://img.shields.io/github/stars/dnoice/Intelligent-Automation-Module.svg)](https://github.com/dnoice/Intelligent-Automation-Module/stargazers)
[![GitHub Issues](https://img.shields.io/github/issues/dnoice/Intelligent-Automation-Module.svg)](https://github.com/dnoice/Intelligent-Automation-Module/issues)

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Quick Start](#quick-start)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage Guide](#usage-guide)
- [Command Reference](#command-reference)
- [Security](#security)
- [Templates](#templates)
- [Learning System](#learning-system)
- [Advanced Features](#advanced-features)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## 🔍 Overview

The Enhanced Intelligent Automation (IA) module is a sophisticated command-line tool that transforms natural language descriptions into executable workflows. Created by Dennis 'dnoice' Smaltz, it combines AI-powered natural language processing with robust execution management, comprehensive learning analytics, and enterprise-grade security features.

This project is part of a comprehensive .bashrc.d modular system designed to enhance command-line productivity and automation capabilities.

### What it does:
- **Natural Language Processing**: Convert plain English descriptions into structured workflows
- **Smart Execution**: Run workflows with parallel processing, retry logic, and timeout management
- **Learning Analytics**: Track performance, optimize workflows, and provide detailed insights
- **Security First**: Comprehensive command validation and sandboxing capabilities
- **Template System**: Pre-built and customizable workflow templates
- **Monitoring**: Real-time execution monitoring and notifications

### Repository Structure
```
Intelligent-Automation-Module/
├── enhanced-intelligent-automation.sh  # Main script (v2.0)
├── 11-intelligent-automation.sh       # Original script (v1.0) 
├── README.md                          # This documentation
├── LICENSE                            # MIT License
├── docs/                             # Additional documentation
├── examples/                         # Example workflows and templates
└── tests/                           # Test suite (coming soon)
```

## ✨ Features

### 🎯 Core Features
- **AI-Powered Workflow Creation**: Support for local NLP, OpenAI, and Anthropic backends
- **Enhanced Execution Engine**: Parallel processing, smart retries, and timeout management
- **Comprehensive Learning System**: Performance analytics, success tracking, and optimization
- **Security Framework**: Command validation, allowlists/blacklists, and security modes
- **Template Library**: Pre-built templates for common automation tasks
- **Advanced Logging**: Separate logs for execution, errors, performance, and security

### 🛡️ Security Features
- **Command Validation**: Allowlist/blacklist system for safe command execution
- **Input Sanitization**: Prevents injection attacks and validates all inputs
- **Security Modes**: Strict and permissive modes for different environments
- **Pattern Detection**: Automatically blocks dangerous command patterns
- **Audit Logging**: Complete audit trail of all command executions

### 📊 Analytics & Learning
- **Performance Metrics**: Track execution duration, success rates, and trends
- **Category Classification**: Automatically categorize workflows by type
- **Learning Dashboard**: Comprehensive analytics and insights
- **Auto-Optimization**: AI-powered workflow optimization based on execution history
- **Predictive Analytics**: Estimate execution times and success probability

### 🔧 Advanced Capabilities
- **Parallel Execution**: Run multiple tasks simultaneously for faster completion
- **Workflow Scheduling**: Schedule workflows using cron-like syntax
- **Dependency Management**: Define and manage workflow dependencies
- **Backup & Restore**: Comprehensive backup and disaster recovery
- **Plugin Architecture**: Extensible plugin system for custom functionality
- **Notification System**: Integration with Slack, email, and webhook notifications

## 🚀 Quick Start

### 1. Basic Setup
```bash
# Clone the repository
git clone https://github.com/dnoice/Intelligent-Automation-Module.git
cd Intelligent-Automation-Module

# Source the enhanced script in your .bashrc or run directly
source ./enhanced-intelligent-automation.sh

# Or add to your .bashrc.d directory for modular loading
mkdir -p ~/.bashrc.d
cp enhanced-intelligent-automation.sh ~/.bashrc.d/11-intelligent-automation.sh
echo "source ~/.bashrc.d/11-intelligent-automation.sh" >> ~/.bashrc
source ~/.bashrc

# Initialize the system
ia init
```

### 2. Create Your First Workflow
```bash
# Create a simple backup workflow
ia create "backup my documents to the cloud" daily_backup

# Run the workflow
ia run daily_backup

# View execution details
ia show daily_backup
```

### 3. Explore Analytics
```bash
# View system status
ia status

# Check workflow analytics
ia analytics daily_backup

# View execution logs
ia log 50
```

## 📦 Installation

### Prerequisites
- **Bash 4.0+**: Modern bash shell
- **jq**: JSON processing (required)
- **curl**: HTTP client (required)
- **Python 3.6+**: For local NLP processing (optional)
- **cron**: For workflow scheduling (optional)

### System Requirements
- **Operating System**: Linux, macOS, WSL on Windows
- **Memory**: 512MB RAM minimum, 2GB recommended
- **Storage**: 100MB for installation, additional space for workflows and logs
- **Network**: Internet connection for AI backends (OpenAI/Anthropic)

### Installation Steps

#### 1. Download and Install
```bash
# Clone the repository
git clone https://github.com/dnoice/Intelligent-Automation-Module.git
cd Intelligent-Automation-Module

# Or download the script directly
wget https://raw.githubusercontent.com/dnoice/Intelligent-Automation-Module/main/enhanced-intelligent-automation.sh

# Make executable
chmod +x enhanced-intelligent-automation.sh

# Method 1: Add to .bashrc.d modular system (recommended)
mkdir -p ~/.bashrc.d
cp enhanced-intelligent-automation.sh ~/.bashrc.d/11-intelligent-automation.sh
echo "source ~/.bashrc.d/11-intelligent-automation.sh" >> ~/.bashrc

# Method 2: Direct sourcing
echo "source $(pwd)/enhanced-intelligent-automation.sh" >> ~/.bashrc

# Reload shell
source ~/.bashrc
```

> **Note**: This module is designed to work with the .bashrc.d modular system for organized shell customization. The `11-` prefix ensures proper loading order in the modular framework.

#### 2. Install Dependencies
```bash
# Ubuntu/Debian
sudo apt update && sudo apt install -y jq curl python3 python3-pip cron

# CentOS/RHEL/Fedora
sudo yum install -y jq curl python3 python3-pip cronie
# or for newer versions
sudo dnf install -y jq curl python3 python3-pip cronie

# macOS (with Homebrew)
brew install jq curl python3

# Install Python NLP packages (for local processing)
pip3 install spacy nltk
python3 -m spacy download en_core_web_sm
```

#### 3. Initialize the System
```bash
# Run the interactive setup
ia init

# Follow the prompts to configure:
# - AI backend (local/OpenAI/Anthropic)
# - Security settings
# - Learning preferences
# - Logging levels
```

## ⚙️ Configuration

### Configuration File Location
The main configuration file is located at: `~/.bashrc.d/11-intelligent-automation/config.json`

### Basic Configuration
```json
{
    "version": "2.0.0",
    "settings": {
        "api_backend": "local",
        "security_mode": "strict",
        "learning_enabled": true,
        "auto_optimize": false,
        "max_parallel_jobs": 4,
        "execution_timeout": 3600,
        "log_level": "info"
    },
    "api_keys": {
        "openai": "your-openai-api-key",
        "anthropic": "your-anthropic-api-key"
    }
}
```

### Environment Variables
```bash
# Override default settings
export IA_VERBOSE=1                    # Enable verbose output
export IA_SECURITY_MODE="permissive"   # Set security mode
export IA_LOG_LEVEL="debug"           # Set logging level
export IA_MAX_PARALLEL_JOBS=8         # Set parallel execution limit
```

### AI Backend Configuration

#### Local NLP (Default)
- **Pros**: No API costs, privacy, offline operation
- **Cons**: Limited AI capabilities, requires Python dependencies
- **Setup**: Automatic with Python packages installed

#### OpenAI Backend
- **Pros**: Advanced AI capabilities, robust NLP
- **Cons**: API costs, requires internet connection
- **Setup**: 
  ```bash
  # Set API key in config or environment
  export OPENAI_API_KEY="your-api-key"
  ia init  # Reconfigure to use OpenAI
  ```

#### Anthropic Backend
- **Pros**: Advanced AI capabilities, safety-focused
- **Cons**: API costs, requires internet connection
- **Setup**:
  ```bash
  # Set API key in config or environment
  export ANTHROPIC_API_KEY="your-api-key"
  ia init  # Reconfigure to use Anthropic
  ```

## 📖 Usage Guide

### Creating Workflows

#### From Natural Language
```bash
# Basic workflow creation
ia create "backup my home directory to external drive" home_backup

# With specific workflow name
ia create "deploy application to staging server" deploy_staging

# Using templates
ia create "setup development environment" dev_setup deployment
```

#### From Templates
```bash
# List available templates
ia templates list

# Create from template
ia create "backup project files" project_backup backup

# Show template details
ia templates show backup
```

### Running Workflows

#### Basic Execution
```bash
# Run a workflow
ia run workflow_name

# Run with verbose output
IA_VERBOSE=1 ia run workflow_name
```

#### Advanced Execution Options
```bash
# Parallel execution (faster for independent tasks)
ia run workflow_name --parallel

# Schedule for later execution
ia run workflow_name --schedule="2025-08-10 14:30"
ia run workflow_name --schedule="5min"  # Relative time

# Dry run (validate without executing)
ia run workflow_name --dry-run
```

### Managing Workflows

#### Listing and Browsing
```bash
# List all workflows
ia list

# List by category
ia list --category=backup

# Sort by different criteria
ia list --sort=last_run
ia list --sort=success_rate
```

#### Viewing Details
```bash
# Show workflow details
ia show workflow_name

# Show execution history
ia show workflow_name --history

# Show performance metrics
ia show workflow_name --metrics
```

#### Workflow Maintenance
```bash
# Delete a workflow
ia delete workflow_name

# Optimize workflow performance
ia optimize workflow_name

# Export workflow for sharing
ia export workflow_name > my_workflow.json

# Import shared workflow
ia import < shared_workflow.json
```

### Monitoring and Analytics

#### System Status
```bash
# Overall system status
ia status

# Specific workflow status
ia status workflow_name

# Health check
ia status --health
```

#### Analytics Dashboard
```bash
# Global analytics
ia analytics

# Workflow-specific analytics
ia analytics workflow_name

# Performance trends
ia analytics --trends

# Export analytics data
ia analytics --export > analytics_report.json
```

#### Log Management
```bash
# View recent logs
ia log

# View specific number of entries
ia log 100

# View error logs only
ia log --level=error

# View logs for specific workflow
ia log --workflow=workflow_name
```

## 📚 Command Reference

### Core Commands

| Command | Description | Examples |
|---------|-------------|----------|
| `ia create` | Create new workflow | `ia create "backup files" backup_daily` |
| `ia run` | Execute workflow | `ia run backup_daily --parallel` |
| `ia list` | List workflows | `ia list --category=backup` |
| `ia show` | Show workflow details | `ia show backup_daily` |
| `ia delete` | Delete workflow | `ia delete backup_daily` |

### Management Commands

| Command | Description | Examples |
|---------|-------------|----------|
| `ia status` | System/workflow status | `ia status backup_daily` |
| `ia analytics` | View analytics | `ia analytics --trends` |
| `ia log` | View logs | `ia log --level=error` |
| `ia optimize` | Optimize workflow | `ia optimize slow_workflow` |
| `ia backup` | Backup data | `ia backup --auto` |

### Advanced Commands

| Command | Description | Examples |
|---------|-------------|----------|
| `ia watch` | Monitor conditions | `ia watch "disk usage > 80%" do "cleanup"` |
| `ia schedule` | Schedule workflows | `ia schedule daily_backup "0 2 * * *"` |
| `ia templates` | Manage templates | `ia templates create backup_template` |
| `ia export` | Export workflows | `ia export workflow_name` |
| `ia import` | Import workflows | `ia import < workflow.json` |

### Command Options

#### Global Options
- `--verbose, -v`: Enable verbose output
- `--quiet, -q`: Suppress non-essential output
- `--dry-run`: Validate without executing
- `--force`: Force operation without confirmation

#### Execution Options
- `--parallel`: Enable parallel task execution
- `--timeout=SECONDS`: Set execution timeout
- `--retry=COUNT`: Set retry attempts
- `--schedule=TIME`: Schedule execution

#### Filter Options
- `--category=CAT`: Filter by category
- `--status=STATUS`: Filter by status
- `--sort=FIELD`: Sort results
- `--limit=NUM`: Limit results

## 🛡️ Security

### Security Modes

#### Strict Mode (Default)
- Only allowlisted commands are permitted
- All commands are validated against security patterns
- Comprehensive logging of all activities
- Recommended for production environments

```bash
# Enable strict mode
ia config set security_mode strict
```

#### Permissive Mode
- Commands are checked against blacklist only
- More flexible for development environments
- Still logs security-relevant activities
- Use with caution in production

```bash
# Enable permissive mode
ia config set security_mode permissive
```

### Command Validation

#### Allowlist Management
```bash
# View allowed commands
cat ~/.bashrc.d/11-intelligent-automation/allowed_commands.txt

# Add new command
echo "your_command" >> ~/.bashrc.d/11-intelligent-automation/allowed_commands.txt

# Validate command
ia validate "ls -la"
```

#### Blacklist Management
```bash
# View blacklisted commands
cat ~/.bashrc.d/11-intelligent-automation/blacklisted_commands.txt

# Add dangerous command
echo "rm -rf /" >> ~/.bashrc.d/11-intelligent-automation/blacklisted_commands.txt
```

### Security Best Practices

1. **Regular Updates**: Keep the allowlist updated with necessary commands
2. **Principle of Least Privilege**: Only allow commands that are absolutely necessary
3. **Regular Audits**: Review security logs regularly
4. **Sandboxing**: Consider running in containers for additional isolation
5. **Input Validation**: All inputs are automatically sanitized
6. **Monitoring**: Enable security logging and monitoring

### Security Logs
```bash
# View security logs
ia log --type=security

# Monitor security events in real-time
tail -f ~/.bashrc.d/11-intelligent-automation/logs/ia_security.log
```

## 📝 Templates

### Built-in Templates

| Template | Description | Use Case |
|----------|-------------|----------|
| `backup` | File backup operations | Regular data backups |
| `deploy` | Application deployment | CI/CD pipelines |
| `monitor` | System monitoring | Health checks |
| `maintenance` | System maintenance | Cleanup tasks |
| `git_workflow` | Git operations | Version control |
| `data_processing` | Data transformation | ETL workflows |

### Using Templates

#### List Available Templates
```bash
ia templates list
```

#### View Template Details
```bash
ia templates show backup
```

#### Create from Template
```bash
# Create workflow from template
ia create "backup my project" project_backup backup

# Create with custom parameters
ia create "backup database" db_backup backup --target="/var/lib/mysql"
```

### Creating Custom Templates

#### Template Structure
```json
{
    "template": {
        "name": "my_template",
        "description": "Custom template description",
        "version": "1.0.0",
        "parameters": [
            {
                "name": "target",
                "description": "Target for operation",
                "type": "string",
                "required": true
            }
        ],
        "tasks": [
            {
                "id": "0",
                "command": "echo 'Starting ${name} for ${target}'",
                "description": "Initialize workflow",
                "estimated_duration": 1
            }
        ]
    }
}
```

#### Create Template
```bash
# Create new template
ia templates create my_template

# Edit template
ia templates edit my_template

# Test template
ia templates test my_template --target="test_value"
```

## 🧠 Learning System

### How Learning Works

The IA system continuously learns from workflow executions to improve performance and reliability:

1. **Execution Tracking**: Every workflow execution is recorded with metadata
2. **Performance Analysis**: Duration, success rate, and failure patterns are analyzed
3. **Pattern Recognition**: Common issues and optimizations are identified
4. **Auto-Optimization**: Workflows are automatically optimized based on learning data
5. **Predictive Analytics**: Future execution times and success probability are estimated

### Learning Data

#### Execution Records
```bash
# View learning data for a workflow
ia show workflow_name --learning

# View global learning statistics
ia analytics --global
```

#### Performance Metrics
- **Success Rate**: Percentage of successful executions
- **Average Duration**: Mean execution time
- **Failure Patterns**: Common failure points and causes
- **Optimization Opportunities**: Suggested improvements

### Analytics Dashboard

#### Workflow Analytics
```bash
# Detailed workflow analytics
ia analytics workflow_name

# Performance trends over time
ia analytics workflow_name --trends

# Comparison with similar workflows
ia analytics workflow_name --compare
```

#### Global Analytics
```bash
# System-wide analytics
ia analytics --global

# Category-based analysis
ia analytics --by-category

# Performance benchmarks
ia analytics --benchmarks
```

### Learning Configuration

#### Enable/Disable Learning
```bash
# Enable learning (default)
ia config set learning_enabled true

# Disable learning
ia config set learning_enabled false
```

#### Auto-Optimization
```bash
# Enable auto-optimization
ia config set auto_optimize true

# Optimize specific workflow
ia optimize workflow_name

# View optimization suggestions
ia optimize workflow_name --suggestions
```

## 🔬 Advanced Features

### Parallel Execution

#### How It Works
- Tasks are analyzed for dependencies
- Independent tasks are executed simultaneously
- Execution time is significantly reduced for suitable workflows
- Resource usage is optimized based on system capabilities

#### Configuration
```bash
# Set maximum parallel jobs
ia config set max_parallel_jobs 8

# Run workflow in parallel mode
ia run workflow_name --parallel

# Check parallel execution capability
ia analyze workflow_name --parallel-potential
```

### Workflow Dependencies

#### Define Dependencies
```json
{
    "workflow": {
        "dependencies": [
            {
                "workflow": "prerequisite_workflow",
                "condition": "success"
            }
        ]
    }
}
```

#### Dependency Management
```bash
# Check dependencies
ia deps workflow_name

# Run with dependency checking
ia run workflow_name --check-deps

# Visualize dependency graph
ia deps --graph workflow_name
```

### Monitoring and Alerting

#### Real-time Monitoring
```bash
# Monitor workflow execution
ia monitor workflow_name

# Monitor all active workflows
ia monitor --all

# Dashboard view
ia dashboard
```

#### Notifications
```bash
# Configure Slack notifications
ia config set slack_webhook "https://hooks.slack.com/..."

# Configure email notifications
ia config set email_smtp "smtp.example.com"

# Test notifications
ia notify test "Test message"
```

### Backup and Disaster Recovery

#### Automatic Backups
```bash
# Enable automatic backups
ia config set auto_backup true

# Configure backup retention
ia config set backup_retention_days 30

# Manual backup
ia backup --all
```

#### Restore Operations
```bash
# List available backups
ia backup list

# Restore from backup
ia restore backup_file.tar.gz

# Restore specific workflow
ia restore workflow_name backup_file.tar.gz
```

### Plugin System

#### Available Plugins
- **Database Integration**: Connect to MySQL, PostgreSQL, MongoDB
- **Cloud Services**: AWS, GCP, Azure integrations
- **Monitoring Tools**: Prometheus, Grafana, Datadog
- **Communication**: Slack, Teams, Discord
- **Version Control**: Advanced Git operations

#### Plugin Management
```bash
# List available plugins
ia plugins list

# Install plugin
ia plugins install database-mysql

# Configure plugin
ia plugins config database-mysql

# Enable/disable plugin
ia plugins enable database-mysql
ia plugins disable database-mysql
```

## 🔧 Troubleshooting

### Common Issues

#### 1. Command Not Found
```bash
# Problem: 'ia' command not recognized
# Solution: Ensure script is sourced in your shell
source /path/to/enhanced-intelligent-automation.sh
echo "source /path/to/enhanced-intelligent-automation.sh" >> ~/.bashrc
```

#### 2. Permission Denied
```bash
# Problem: Cannot create directories or files
# Solution: Check permissions and ownership
chmod +x enhanced-intelligent-automation.sh
mkdir -p ~/.bashrc.d/11-intelligent-automation
```

#### 3. jq Not Found
```bash
# Problem: jq command not available
# Solution: Install jq package
# Ubuntu/Debian
sudo apt install jq
# CentOS/RHEL
sudo yum install jq
# macOS
brew install jq
```

#### 4. Python Dependencies Missing
```bash
# Problem: Local NLP not working
# Solution: Install Python packages
pip3 install spacy nltk
python3 -m spacy download en_core_web_sm
```

#### 5. Workflow Execution Fails
```bash
# Problem: Workflow tasks fail to execute
# Solution: Check security settings and logs
ia log --level=error
ia config get security_mode
ia validate "your_command"
```

### Debug Mode

#### Enable Debug Logging
```bash
# Set debug log level
ia config set log_level debug

# Run with verbose output
IA_VERBOSE=1 ia run workflow_name

# Check debug logs
ia log --level=debug
```

#### Workflow Debugging
```bash
# Dry run to test workflow
ia run workflow_name --dry-run

# Validate workflow structure
ia validate workflow_name

# Check task commands
ia show workflow_name --tasks
```

### Performance Issues

#### Slow Execution
```bash
# Check system resources
ia status --system

# Analyze workflow performance
ia analytics workflow_name --performance

# Optimize workflow
ia optimize workflow_name
```

#### Memory Usage
```bash
# Monitor memory usage
ia monitor --resources

# Configure limits
ia config set max_parallel_jobs 2
ia config set execution_timeout 1800
```

### Log Analysis

#### Error Investigation
```bash
# View error logs
ia log --level=error --last=50

# Search logs for specific error
ia log --search="error_pattern"

# Export logs for analysis
ia log --export > logs_export.txt
```

#### Performance Analysis
```bash
# View performance logs
ia log --type=performance

# Analyze slow workflows
ia analytics --slow-workflows

# Generate performance report
ia report --performance > performance_report.html
```

### Getting Help

#### Built-in Help
```bash
# General help
ia help

# Command-specific help
ia help create
ia help run

# Configuration help
ia help config
```

#### Community Support
- **GitHub Issues**: Report bugs and request features
- **Documentation**: Comprehensive online documentation
- **Community Forum**: Ask questions and share experiences
- **Stack Overflow**: Tag questions with `intelligent-automation`

## 🤝 Contributing

### Development Setup

#### Prerequisites
- Bash 4.0+
- Git for version control
- Text editor or IDE
- Testing framework (bats recommended)

#### Setting Up Development Environment
```bash
# Clone the repository
git clone https://github.com/dnoice/Intelligent-Automation-Module.git
cd Intelligent-Automation-Module

# Create development branch
git checkout -b feature/your-feature

# Install development dependencies
./scripts/setup-dev.sh

# Run tests
./scripts/test.sh
```

### Code Style Guidelines

#### Bash Style
- Use 4 spaces for indentation
- Follow Google Shell Style Guide
- Use meaningful function and variable names
- Include comprehensive error handling
- Add comments for complex logic

#### Function Naming Convention
```bash
# Public functions (user-facing)
function ia_command_name() { }

# Private functions (internal)
function _internal_function_name() { }

# Utility functions
function _util_function_name() { }
```

#### Error Handling
```bash
function example_function() {
    local param="$1"
    
    # Validate parameters
    if [[ -z "$param" ]]; then
        echo -e "${RED}Error: Parameter required${RESET}" >&2
        return 1
    fi
    
    # Execute with error handling
    if ! some_command "$param" 2>/dev/null; then
        _ia_log "error" "Command failed: some_command $param"
        return 1
    fi
    
    return 0
}
```

### Testing

#### Test Structure
```bash
# Test files location
tests/
├── unit/
│   ├── test_core_functions.bats
│   ├── test_ai_processing.bats
│   └── test_security.bats
├── integration/
│   ├── test_workflow_execution.bats
│   └── test_learning_system.bats
└── fixtures/
    ├── sample_workflows/
    └── test_data/
```

#### Running Tests
```bash
# Run all tests
./scripts/test.sh

# Run specific test suite
./scripts/test.sh unit

# Run with coverage
./scripts/test.sh --coverage

# Run integration tests
./scripts/test.sh integration
```

#### Writing Tests
```bash
#!/usr/bin/env bats

# Test file: tests/unit/test_core_functions.bats

@test "ia create should create workflow from description" {
    run ia create "test workflow" test_workflow
    [ "$status" -eq 0 ]
    [ -f "${IA_WORKFLOWS_DIR}/test_workflow.workflow.json" ]
}

@test "ia run should execute workflow successfully" {
    # Setup
    ia create "echo hello" test_echo
    
    # Execute
    run ia run test_echo
    
    # Assert
    [ "$status" -eq 0 ]
    [[ "$output" == *"hello"* ]]
}
```

### Feature Development

#### Adding New Commands
1. Create function in appropriate section
2. Add command handler in main `ia()` function
3. Update help documentation
4. Add security validation if needed
5. Write tests for new functionality
6. Update README documentation

#### Example: Adding New Command
```bash
# Add function
function _cmd_new_feature() {
    local param="$1"
    
    # Implementation
    echo "New feature with parameter: $param"
    return 0
}

# Add to main function
function ia() {
    case "$command" in
        # ... existing commands ...
        new-feature)
            _cmd_new_feature "$@"
            ;;
        # ... rest of commands ...
    esac
}

# Add help entry
function _cmd_help_enhanced() {
    # ... existing help ...
    echo -e "  ${CYAN}ia new-feature <param>${RESET}"
    echo -e "    Description of new feature"
    # ... rest of help ...
}
```

### Submitting Changes

#### Pull Request Process
1. **Fork the repository**
2. **Create feature branch**: `git checkout -b feature/amazing-feature`
3. **Write code and tests**
4. **Run test suite**: `./scripts/test.sh`
5. **Update documentation**
6. **Commit changes**: `git commit -m "Add amazing feature"`
7. **Push to branch**: `git push origin feature/amazing-feature`
8. **Open pull request**

#### Pull Request Guidelines
- Provide clear description of changes
- Include test cases for new functionality
- Update documentation as needed
- Follow code style guidelines
- Ensure all tests pass
- Include examples of new features

### Code Review Process

#### Review Criteria
- **Functionality**: Does the code work as intended?
- **Security**: Are there any security implications?
- **Performance**: Is the code efficient?
- **Testing**: Are there adequate tests?
- **Documentation**: Is the code well-documented?
- **Style**: Does it follow project conventions?

#### Review Checklist
- [ ] Code follows style guidelines
- [ ] Tests are included and passing
- [ ] Documentation is updated
- [ ] Security considerations addressed
- [ ] Performance impact assessed
- [ ] Backward compatibility maintained

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](https://github.com/dnoice/Intelligent-Automation-Module/blob/main/LICENSE) file for details.

### MIT License Summary
- **Freedom**: Use, modify, and distribute freely
- **Attribution**: Include original license and copyright
- **No Warranty**: Software provided "as is"
- **Commercial Use**: Permitted
- **Private Use**: Permitted
- **Modification**: Permitted
- **Distribution**: Permitted

## 🙏 Acknowledgments

### Contributors
- **Dennis 'dnoice' Smaltz**: Creator and maintainer ([GitHub](https://github.com/dnoice))
- **Community Contributors**: Thank you to all who have contributed code, documentation, and feedback to the [Intelligent Automation Module](https://github.com/dnoice/Intelligent-Automation-Module)

### Technologies Used
- **Bash**: Core scripting language
- **jq**: JSON processing
- **Python**: Natural language processing
- **Various UNIX tools**: Core system utilities

### Inspiration
This project was inspired by the need for intelligent command-line automation that combines the power of AI with the reliability and security requirements of production systems.

---

## 📞 Support and Contact

### Documentation
- **GitHub Repository**: [Complete source code and documentation](https://github.com/dnoice/Intelligent-Automation-Module)
- **README**: [Comprehensive usage guide](https://github.com/dnoice/Intelligent-Automation-Module/blob/main/README.md)
- **Examples**: [Workflow examples and templates](https://github.com/dnoice/Intelligent-Automation-Module/tree/main/examples)
- **Wiki**: [Additional documentation](https://github.com/dnoice/Intelligent-Automation-Module/wiki) (coming soon)

### Community
- **GitHub Repository**: [dnoice/Intelligent-Automation-Module](https://github.com/dnoice/Intelligent-Automation-Module)
- **GitHub Issues**: [Report bugs and request features](https://github.com/dnoice/Intelligent-Automation-Module/issues)
- **GitHub Discussions**: [Community discussions and Q&A](https://github.com/dnoice/Intelligent-Automation-Module/discussions)
- **Pull Requests**: [Contribute code](https://github.com/dnoice/Intelligent-Automation-Module/pulls)
- **Stack Overflow**: Tag questions with `intelligent-automation`

### Professional Support
- **Commercial Support**: Available for enterprise users
- **Training**: Workshops and training sessions
- **Consulting**: Custom implementation and integration services
- **Enterprise Features**: Advanced features for enterprise users

---

*"Automate intelligently, execute securely, learn continuously."*

**Happy Automating! 🚀**
