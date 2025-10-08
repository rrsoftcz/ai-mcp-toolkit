# AI MCP Toolkit

A comprehensive AI-powered text processing toolkit built on the Model Context Protocol (MCP) standard, designed to work seamlessly with local AI models through Ollama.

## 🌟 Features

### Essential AI Agents
- **Text Cleaner** - Remove special characters and normalize text
- **Diacritic Remover** - Remove accents and diacritical marks
- **Text Analyzer** - Comprehensive text statistics and analysis
- **Grammar Checker** - Fix grammar and spelling mistakes
- **Text Summarizer** - Generate concise summaries
- **Language Detector** - Identify text language
- **Sentiment Analyzer** - Analyze emotional tone
- **Text Translator** - Multi-language translation support
- **Format Converter** - Convert between text formats
- **Readability Scorer** - Assess text complexity and readability

### Key Capabilities
- 🔌 **MCP Protocol Support** - Standard interface for AI applications
- 🦙 **Ollama Integration** - Local AI model support with dynamic switching
- 🌐 **Modern Web UI** - Intuitive ChatGPT-like browser interface
- 💬 **Advanced Chat Mode** - Conversational AI with enhanced UX features
- 🖥️ **CLI Support** - Command-line interface for automation
- 🚀 **Easy Deployment** - Docker and native installation options
- 🔒 **Privacy-First** - All processing happens locally

## 💬 Enhanced Chat Interface

The AI MCP Toolkit features a modern, ChatGPT-inspired chat interface with advanced UX capabilities:

### Chat Features
- 🗨️ **Smart Auto-Scroll** - Automatic scrolling to new messages with user scroll detection
- 📋 **Conversation Management** - Create, rename, and organize chat conversations
- 🗑️ **Bulk Operations** - Clear all conversations with confirmation dialog
- 📋 **Message Actions** - Copy messages with one-click functionality
- 🔄 **Response Regeneration** - Re-generate AI responses for better results
- ⏹️ **Request Cancellation** - Cancel ongoing AI requests mid-generation
- 📊 **Performance Metrics** - Real-time response times and token speeds
- 🌙 **Dark/Light Theme** - Automatic theme switching support

### Visual Design
- 🎨 **Modern Layout** - Clean, professional ChatGPT-like appearance
- 📏 **Dynamic Sizing** - Message bubbles adapt to content length
- 🖥️ **Responsive Design** - Optimized for desktop and mobile devices
- 🔍 **Visual Hierarchy** - Clear distinction between user and AI messages
- ⚡ **Smooth Animations** - Fluid transitions and loading indicators
- 💱 **Collapsible Sidebar** - Toggle conversation history visibility

### Conversation Experience
- 📏 **Persistent History** - Conversations saved automatically across sessions
- 🏷️ **Auto-Titling** - Conversations automatically named from first message
- 🔍 **Search & Filter** - Find conversations and messages quickly
- 📅 **Timeline View** - Messages grouped by date (Today, Yesterday, etc.)
- 📊 **Usage Statistics** - Track response times and conversation metrics
- 📥 **Export Options** - Download conversations as text files

## ✨ Production Ready

This AI MCP Toolkit is production-ready with:

- 🧹 **Clean codebase** - No debug logs, test files, or temporary artifacts
- 🔒 **Secure defaults** - Environment-based configuration, no hardcoded secrets
- 📋 **Comprehensive logging** - Structured logging with configurable levels
- 🔧 **Cross-platform support** - Automatic environment detection and optimization
- 🐳 **Container ready** - Docker support with health checks
- 📊 **Monitoring** - Built-in GPU monitoring and performance metrics
- 🔄 **Auto-recovery** - Graceful error handling and fallback mechanisms
- 📖 **Complete documentation** - Comprehensive guides and API documentation
- 🎨 **Modern UI/UX** - ChatGPT-like interface with advanced features

## 🚀 Quick Start

### Prerequisites
- Python 3.13.7 (recommended) or Python 3.11+
- Ollama installed and running
- Git

### Installation

#### Smart Setup (Recommended)
The AI MCP Toolkit includes intelligent environment detection and automatic configuration:

```bash
# Clone the repository
git clone https://github.com/rrsoftcz/ai-mcp-toolkit.git
cd ai-mcp-toolkit

# Run the enhanced setup script (works on Linux, macOS, Windows)
./setup.sh
```

The setup script will automatically:
- 🔍 Detect your platform (Linux, macOS, Windows) and hardware (NVIDIA, Apple Silicon, AMD, CPU)
- 🧠 Select the optimal AI model for your system
- ⚙️ Generate platform-specific configuration
- 📦 Install all required dependencies
- 🦙 Set up Ollama with the right model

#### Manual Setup Options

##### Option 1: Docker (Alternative for Production)
```bash
# Clone and start with Docker
git clone https://github.com/rrsoftcz/ai-mcp-toolkit.git
cd ai-mcp-toolkit
docker-compose up -d

# Pull AI model (after containers start)
docker-compose exec ollama ollama pull llama3.2:3b
```

#### Option 2: Native Installation
```bash
# Clone and install locally
git clone https://github.com/rrsoftcz/ai-mcp-toolkit.git
cd ai-mcp-toolkit
pip install -e .
```

#### Step 2: Install Ollama (if not already installed)
```bash
# On macOS/Linux
curl -fsSL https://ollama.ai/install.sh | sh

# Pull a recommended model
ollama pull llama3.2:3b
```

#### Step 3: Configure the System
```bash
# Create default configuration
ai-mcp-toolkit config create

# Check system status
ai-mcp-toolkit status
```

#### Step 4: Optional - Customize Settings
```bash
# Copy environment template
cp .env.example .env

# Edit with your preferences (optional)
nano .env
```

### Environment Management

After installation, you can easily switch between different environment configurations:

```bash
# Interactive environment switcher
./switch-environment.sh

# Or manually copy configuration templates
cp configs/templates/.env.cpu .env              # CPU-only
cp configs/templates/.env.linux-nvidia .env     # NVIDIA GPU
cp configs/templates/.env.macos-apple-silicon .env # Apple Silicon
```

**Available Configurations:**
- **linux-nvidia** - Optimized for NVIDIA GPUs (RTX/GTX series)
- **macos-apple-silicon** - Optimized for Apple M1/M2/M3/M4 chips  
- **cpu** - Universal CPU-only fallback

> 📚 **Need more details?** See the comprehensive [Cross-Platform Setup Guide](CROSS_PLATFORM_SETUP.md) for detailed instructions, troubleshooting, and platform-specific optimizations.

### Running the Application

#### Start the MCP Server
```bash
ai-mcp-toolkit serve
```

#### Launch Web UI (in another terminal)
```bash
ai-mcp-toolkit ui
```

#### Access the Application
- **Enhanced Chat UI**: http://localhost:5173 - Modern ChatGPT-like interface
- **MCP Server**: http://localhost:8000 - Backend API server
- **API Documentation**: http://localhost:8000/docs - Interactive API docs
- **GPU Monitoring**: http://localhost:5173/gpu - Real-time system metrics

### Using the Enhanced Chat Interface

1. **Start a Conversation**
   - Navigate to http://localhost:5173
   - Click the "New Conversation" button or start typing
   - Messages automatically save and organize by date

2. **Chat Features**
   - **Auto-scroll**: New messages automatically come into view
   - **Copy messages**: Click the copy icon next to any message
   - **Regenerate**: Click the regenerate button to get alternative AI responses
   - **Cancel requests**: Stop AI mid-response with the cancel button
   - **Real-time metrics**: See response times and token speeds

3. **Conversation Management**
   - **Sidebar**: Toggle with the sidebar button to view conversation history
   - **Rename**: Click the edit icon to rename any conversation
   - **Delete**: Remove individual conversations with confirmation
   - **Clear All**: Bulk delete all conversations (with safety confirmation)
   - **Search**: Find specific conversations or messages

4. **Model Switching**
   - Current model displayed in chat header and message info
   - Switch models via command line: `./switch-model.sh qwen2.5:7b`
   - Or use the GPU monitoring page for model management

### CLI Usage Examples

#### Text Processing Commands
```bash
# Text cleaning and analysis
ai-mcp-toolkit text clean "Your messy text here"
ai-mcp-toolkit text analyze "Sample text for analysis"
ai-mcp-toolkit text summarize "Long text to summarize"
ai-mcp-toolkit text anonymize "John Doe lives in NYC"

# Language and sentiment
ai-mcp-toolkit text detect-language "Bonjour le monde"
ai-mcp-toolkit text sentiment "I love this product!"

# Grammar checking
ai-mcp-toolkit text grammar "This are incorrect grammar"
```

#### System Management
```bash
# Interactive CLI chat
ai-mcp-toolkit chat

# Launch enhanced web UI
ai-mcp-toolkit ui

# List available agents
ai-mcp-toolkit agents

# System status and health check
ai-mcp-toolkit status

# Configuration management
ai-mcp-toolkit config show

# Model switching (for enhanced UI)
./switch-model.sh qwen2.5:7b
```

## ⚙️ Configuration

The AI MCP Toolkit supports flexible configuration through multiple methods to accommodate different use cases.

### Configuration Priority

1. **Command line arguments** (highest priority)
2. **Environment variables** (`.env` file)
3. **Configuration file** (`config.yaml`)
4. **Default values** (lowest priority)

### Quick Configuration Setup

```bash
# Create default configuration
ai-mcp-toolkit config create

# View current settings
ai-mcp-toolkit config show

# Check system health
ai-mcp-toolkit status
```

### Environment Variables Setup

```bash
# Copy the template
cp .env.example .env

# Edit with your settings
nano .env
```

Example `.env` configuration:
```env
# Server Settings
MCP_HOST=localhost
MCP_PORT=8000

# Ollama Integration
OLLAMA_HOST=localhost
OLLAMA_PORT=11434
OLLAMA_MODEL=llama3.2:3b

# Logging
LOG_LEVEL=INFO

# AI Settings
TEMPERATURE=0.1
MAX_TOKENS=2000
MAX_TEXT_LENGTH=100000

# UI Settings
UI_HOST=localhost
UI_PORT=5173

# Caching
ENABLE_CACHE=true
CACHE_TTL=3600
```

### Key Configuration Options

| Category | Setting | Default | Description |
|----------|---------|---------|-------------|
| **Server** | `MCP_HOST` | `localhost` | Server host address |
| **Server** | `MCP_PORT` | `8000` | Server port number |
| **Ollama** | `OLLAMA_HOST` | `localhost` | Ollama server host |
| **Ollama** | `OLLAMA_MODEL` | `llama3.2:3b` | Default AI model |
| **AI** | `TEMPERATURE` | `0.1` | Model creativity (0.0-2.0) |
| **AI** | `MAX_TOKENS` | `2000` | Max response length |
| **Logging** | `LOG_LEVEL` | `INFO` | Logging verbosity |
| **UI** | `UI_PORT` | `5173` | Web UI port |

### Docker Configuration

For Docker deployments, you can customize settings in `docker-compose.yml`:

```yaml
services:
  ai-mcp-toolkit:
    environment:
      - MCP_HOST=0.0.0.0
      - OLLAMA_MODEL=llama3.2:7b  # Use larger model
      - LOG_LEVEL=DEBUG
      - TEMPERATURE=0.05
```

Or create a `.env` file that Docker Compose will automatically use:

```env
MCP_HOST=0.0.0.0
OLLAMA_MODEL=llama3.2:7b
LOG_LEVEL=INFO
TEMPERATURE=0.1
```

For complete configuration documentation, see [docs/CONFIGURATION.md](docs/CONFIGURATION.md).

## 🏗️ Architecture

```
AI MCP Toolkit
├── MCP Server (Core Protocol Implementation)
├── AI Agents (Text Processing Tools)
├── Ollama Integration (Local AI Models)
├── Web UI (Browser Interface)
└── CLI Interface (Command Line Tools)
```

## 📚 Documentation

- [Configuration Guide](docs/CONFIGURATION.md) - Complete configuration documentation
- [Enhanced Chat Interface](#-enhanced-chat-interface) - Modern UI features and capabilities
- [Model Management](#-model-management) - AI model switching and monitoring
- [API Reference](http://localhost:8000/docs) - Interactive API documentation
- [Cross-Platform Setup](CROSS_PLATFORM_SETUP.md) - Platform-specific installation guides
- [Contributing Guidelines](CONTRIBUTING.md) - How to contribute to the project
- [License](LICENSE) - MIT License terms

## 🔍 Troubleshooting

### Common Issues

#### Configuration Issues
```bash
# Check system status
ai-mcp-toolkit status

# Verify configuration
ai-mcp-toolkit config show

# Recreate default config
ai-mcp-toolkit config create
```

#### Ollama Connection Issues
```bash
# Check if Ollama is running
ollama list

# Start Ollama service (if needed)
ollama serve

# Pull required model
ollama pull llama3.2:3b
```

#### Port Conflicts
```bash
# Use different ports
ai-mcp-toolkit serve --port 8001
ai-mcp-toolkit ui --port 5174
```

#### Permission Issues
```bash
# Check directory permissions
ls -la ~/.ai-mcp-toolkit/

# Fix permissions (if needed)
chmod 755 ~/.ai-mcp-toolkit/
```

### Getting Help

- Check the [Configuration Guide](docs/CONFIGURATION.md)
- Run `ai-mcp-toolkit --help` for command help
- Check system status with `ai-mcp-toolkit status`
- Review logs for error messages

## 🔧 Development

### Setup Development Environment
```bash
git clone https://github.com/yourusername/ai-mcp-toolkit.git
cd ai-mcp-toolkit
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -e ".[dev]"
```

### Run Tests
```bash
pytest tests/
```

### Code Quality
```bash
black src/
flake8 src/
mypy src/
```

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guide](docs/contributing.md) for details.

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Model Context Protocol](https://modelcontextprotocol.io/) for the standard
- [Ollama](https://ollama.ai/) for local AI model support
- The open-source AI community

## 🤖 Model Management

The AI MCP Toolkit provides comprehensive model management capabilities, allowing you to easily switch between different AI models and monitor their status in real-time.

### 📋 Getting Current Model Information

#### Check Currently Active Model
```bash
# Check what models are currently running
ollama ps

# Get model via the toolkit's API
curl -s http://localhost:5173/api/gpu/health | jq -r '.ollama_model'

# List all available models
ollama list

# Using the model management script
cd /home/roza/ai-mcp-toolkit
./switch-model.sh
```

#### Example Output
```bash
$ ollama ps
NAME           ID              SIZE     PROCESSOR          CONTEXT    UNTIL              
qwen2.5:14b    7cdf5a0187d5    10 GB    31%/69% CPU/GPU    4096       4 minutes from now

$ curl -s http://localhost:5173/api/gpu/health | jq -r '.ollama_model'
qwen2.5:14b
```

### 🔄 Switching Models

#### Method 1: Using the Model Management Script (Recommended)
The toolkit includes a convenient script for easy model switching:

```bash
cd /home/roza/ai-mcp-toolkit

# View current status and available models
./switch-model.sh

# Switch to a specific model
./switch-model.sh qwen2.5:7b     # Switch to Qwen 2.5 7B
./switch-model.sh qwen2.5:14b    # Switch to Qwen 2.5 14B
./switch-model.sh llama3.1:8b    # Switch to Llama 3.1 8B
./switch-model.sh llama3.2:3b    # Switch to Llama 3.2 3B
```

#### Method 2: Manual Command Line
```bash
# Stop current model
ollama stop qwen2.5:14b

# Start new model
echo "Hello" | ollama run qwen2.5:7b > /dev/null 2>&1 &

# Verify the switch
ollama ps
```

#### Method 3: Enhanced Chat Interface
1. **View Current Model**: Current model is displayed in the chat header and message labels
2. **Real-time Detection**: Model changes are automatically detected and updated in the UI
3. **GPU Monitoring**: Visit http://localhost:5173/gpu for detailed model and GPU metrics
4. **Status Integration**: Chat interface shows connection status and model information

### 🌐 Model Management API

The toolkit provides RESTful API endpoints for programmatic model management:

#### List Available Models
```bash
GET /api/models/switch
```

**Example Request:**
```bash
curl -s http://localhost:5173/api/models/switch | jq
```

**Example Response:**
```json
{
  "success": true,
  "available": [
    {
      "name": "qwen2.5:7b",
      "id": "845dbda0ea48",
      "size": "4.7",
      "modified": "GB 2 hours ago"
    },
    {
      "name": "qwen2.5:14b",
      "id": "7cdf5a0187d5",
      "size": "9.0",
      "modified": "GB 2 hours ago"
    },
    {
      "name": "llama3.1:8b",
      "id": "46e0c10c039e",
      "size": "4.9",
      "modified": "GB 25 hours ago"
    }
  ],
  "current": "qwen2.5:14b"
}
```

#### Switch Model
```bash
POST /api/models/switch
Content-Type: application/json
```

**Example Request:**
```bash
curl -X POST http://localhost:5173/api/models/switch \
  -H "Content-Type: application/json" \
  -d '{"model":"qwen2.5:7b"}'
```

**Success Response:**
```json
{
  "success": true,
  "message": "Successfully switched to model: qwen2.5:7b",
  "model": "qwen2.5:7b"
}
```

**Error Response:**
```json
{
  "success": false,
  "error": "Model 'invalid-model' not found. Available models: qwen2.5:7b, qwen2.5:14b, llama3.1:8b"
}
```

#### Get GPU/Model Health Status
```bash
GET /api/gpu/health
```

**Example Request:**
```bash
curl -s http://localhost:5173/api/gpu/health | jq
```

**Example Response:**
```json
{
  "gpu_name": "NVIDIA GeForce RTX 3070 Ti",
  "gpu_utilization": 45,
  "gpu_memory_used": 8192,
  "gpu_memory_total": 8192,
  "gpu_temperature": 65,
  "ollama_model": "qwen2.5:14b",
  "ollama_gpu_accelerated": true,
  "system_load": 2.1,
  "inference_speed": 12.5
}
```

### 📊 GPU Metrics API

Monitor real-time GPU performance and model metrics:

#### Get Current GPU Metrics
```bash
GET /api/gpu/metrics
```

**Example Request:**
```bash
curl -s http://localhost:5173/api/gpu/metrics | jq
```

**Example Response:**
```json
{
  "timestamp": "2025-01-18T15:59:27.123Z",
  "gpu_utilization": 65,
  "gpu_memory_used": 7340,
  "gpu_memory_total": 8192,
  "gpu_temperature": 68,
  "power_usage": 180,
  "inference_speed": 15.2,
  "tokens_per_second": 25.8
}
```

### 🖥️ Real-Time Model Status

The enhanced chat interface automatically detects model changes and updates the UI in real-time:

- **Chat Header**: Displays current model name with connection status indicator
- **Message Labels**: Shows which model generated each AI response
- **Performance Metrics**: Real-time response times and token speeds per message
- **GPU Monitoring Page**: Comprehensive system metrics at http://localhost:5173/gpu
- **Auto-Detection**: Model changes are detected automatically without refresh
- **Connection Status**: Live indicators show when AI services are available

### 📝 Model Management Script Features

The included `switch-model.sh` script provides:

- ✅ **Current Status Display**: Shows running models and app detection
- ✅ **Available Models List**: Lists all downloaded models with sizes
- ✅ **Automatic Validation**: Verifies model exists before switching
- ✅ **Progress Feedback**: Shows switching progress and completion status
- ✅ **Error Handling**: Provides clear error messages and suggestions
- ✅ **Usage Examples**: Built-in help with command examples

#### Script Usage Examples
```bash
# Make script executable (first time only)
chmod +x /home/roza/ai-mcp-toolkit/switch-model.sh

# Show current status and help
./switch-model.sh

# Switch to different models
./switch-model.sh qwen2.5:7b
./switch-model.sh llama3.1:8b
./switch-model.sh llama3.2:3b
```

### 🔧 Troubleshooting Model Management

#### Model Won't Switch
```bash
# Check if Ollama is running
sudo systemctl status ollama

# Restart Ollama service
sudo systemctl restart ollama

# Check model availability
ollama list

# Force stop all models
ollama ps | grep -v "NAME" | awk '{print $1}' | xargs -I {} ollama stop {}
```

#### Model Not Appearing in UI
```bash
# Refresh the browser page
# Or check browser console for errors

# Verify API endpoints
curl -s http://localhost:5173/api/gpu/health
curl -s http://localhost:5173/api/models/switch
```

#### Performance Issues
```bash
# Check GPU memory usage
nvidia-smi

# Monitor system resources
htop

# Check model size vs available memory
ollama list
```

### 📚 API Quick Reference

| Endpoint | Method | Description | Example |
|----------|---------|-------------|---------|
| `/api/gpu/health` | GET | Get current GPU and model status | `curl -s http://localhost:5173/api/gpu/health` |
| `/api/gpu/metrics` | GET | Get real-time GPU performance metrics | `curl -s http://localhost:5173/api/gpu/metrics` |
| `/api/models/switch` | GET | List all available models and current model | `curl -s http://localhost:5173/api/models/switch` |
| `/api/models/switch` | POST | Switch to a different model | `curl -X POST http://localhost:5173/api/models/switch -d '{"model":"qwen2.5:7b"}'` |

### 💴 Model Management Commands Cheat Sheet

```bash
# Quick Status Check
ollama ps                                    # Show running models
curl -s localhost:5173/api/gpu/health | jq  # Get model via API
./switch-model.sh                           # Show status with script

# Model Switching
./switch-model.sh qwen2.5:7b                # Switch using script (recommended)
ollama stop current_model && ollama run new_model  # Manual switch
curl -X POST localhost:5173/api/models/switch -d '{"model":"qwen2.5:7b"}'  # API switch

# Monitoring
watch -n 2 ollama ps                         # Monitor model status
watch -n 5 "curl -s localhost:5173/api/gpu/metrics | jq"  # Monitor GPU metrics
nvidia-smi -l 5                             # Monitor GPU usage
```

## 🆕 Recent Updates

### Enhanced Chat Interface (Latest)
- ✨ **ChatGPT-like Design** - Modern, professional chat interface
- 🗨️ **Smart Auto-Scroll** - Intelligent message scrolling with user detection
- 📋 **Advanced Conversation Management** - Create, rename, delete, and bulk operations
- 🔄 **Response Regeneration** - Get alternative AI responses with one click
- ⏹️ **Request Cancellation** - Cancel AI requests mid-generation
- 📊 **Real-time Metrics** - Live response times and performance data
- 💱 **Collapsible Sidebar** - Toggle conversation history visibility
- 🎨 **Dynamic Message Styling** - Adaptive message bubbles and clean typography
- 🔍 **Improved Visual Hierarchy** - Clear distinction between user and AI content
- 🌙 **Dark/Light Theme Support** - Automatic theme switching

### System Improvements
- 🔄 **Dynamic Model Detection** - Real-time model switching without restart
- 📊 **Enhanced GPU Monitoring** - Comprehensive system metrics dashboard
- ⚡ **Performance Optimizations** - Faster response times and better resource usage
- 🔒 **Improved Security** - Enhanced error handling and input validation
- 📱 **Mobile Responsiveness** - Optimized for all device sizes

## 🔒 Privacy & Data Protection

The AI MCP Toolkit is designed with **privacy-first principles** and **complete local processing** to ensure your data remains secure and private.

### 🏠 Complete Local Processing

**All AI processing happens locally on your machine:**
- ✅ **No Cloud Dependencies** - All AI models run locally via Ollama
- ✅ **No Data Transmission** - Your text never leaves your computer
- ✅ **No External API Calls** - No communication with third-party AI services
- ✅ **No Internet Required** - Works completely offline after initial setup
- ✅ **No Telemetry** - No usage data or analytics collected

### 🛡️ Data Security Guarantees

#### What We DON'T Collect
- ❌ **No Personal Data** - We don't collect, store, or transmit personal information
- ❌ **No Text Content** - Your processed text never leaves your local environment
- ❌ **No Usage Analytics** - No tracking of what you process or how you use the toolkit
- ❌ **No Conversation Logs** - Chat conversations are stored only locally
- ❌ **No Model Queries** - AI model interactions remain on your system
- ❌ **No Network Monitoring** - No monitoring of your network activity

#### What Stays Local
- 🏠 **All Processing** - Text cleaning, analysis, summarization, translation
- 🏠 **AI Model Inference** - All AI responses generated locally
- 🏠 **Configuration Data** - Settings and preferences stored locally
- 🏠 **Cache Files** - Temporary files for performance optimization
- 🏠 **Conversation History** - Chat logs saved to your local storage
- 🏠 **GPU Metrics** - Hardware monitoring data never transmitted

### 📁 Local Data Storage

#### Where Your Data is Stored
```bash
# Default data directories (configurable)
~/.ai-mcp-toolkit/          # Main data directory
├── cache/                  # Processing cache (temporary)
├── conversations/          # Chat history (JSON files)
├── config.yaml            # Your configuration settings
└── logs/                   # Application logs (optional)
```

#### Data Control
- 🗂️ **Full Control** - You own and control all your data
- 🗑️ **Easy Deletion** - Delete any data files directly from your system
- 💾 **Backup Control** - Back up your data as needed
- 🔧 **Configuration Control** - Change storage locations in settings

### 🔐 Security Features

#### Network Security
- 🌐 **Local Servers Only** - Web UI and API run on localhost (127.0.0.1)
- 🚫 **No External Connections** - No outbound internet connections for AI processing
- 🔒 **CORS Protection** - Configurable Cross-Origin Resource Sharing settings
- 🛡️ **Input Validation** - All inputs sanitized and validated

#### Process Security
- 🔒 **Isolated Processing** - Each text processing operation is isolated
- 💾 **Memory Management** - Secure memory handling and cleanup
- 📝 **Logging Control** - Configurable logging levels (no sensitive data logged)
- 🗃️ **Temporary Files** - Automatic cleanup of temporary processing files

### 🏢 Enterprise & Compliance

#### Compliance Friendly
- ✅ **GDPR Compliant** - No personal data processing or storage
- ✅ **HIPAA Friendly** - Suitable for healthcare environments (local processing)
- ✅ **SOC 2 Compatible** - No data transmission or third-party dependencies
- ✅ **PCI DSS Safe** - No payment or sensitive data handling

#### Enterprise Features
- 🏢 **Air-Gapped Deployment** - Works in completely isolated networks
- 🔒 **On-Premises Only** - No cloud components required
- 📋 **Audit Trail** - Local logging for compliance requirements
- 🛡️ **Data Sovereignty** - Your data never crosses jurisdictional boundaries

### 🔧 Privacy Configuration

#### Minimal Data Collection (Optional)
You can configure the toolkit to collect even less data:

```bash
# Disable all logging
export LOG_LEVEL=CRITICAL

# Disable caching
export ENABLE_CACHE=false

# Use memory-only processing
export DATA_DIR=/tmp/ai-mcp-toolkit
```

#### Privacy Settings
```yaml
# config.yaml - Privacy-focused configuration
privacy:
  disable_logging: true          # No log files created
  memory_only_cache: true        # Cache in RAM only
  auto_cleanup: true             # Automatic cleanup of temp files
  conversation_retention: 0      # Don't save conversations
```

### 🔍 Transparency & Verification

#### Open Source Verification
- 📖 **Open Source Code** - Complete source code available for inspection
- 🔍 **Security Audit Ready** - Code structure supports security audits
- 🧪 **Testable Claims** - All privacy claims can be verified through testing
- 📊 **Network Monitoring** - Use network monitoring tools to verify no external calls

#### Verification Commands
```bash
# Monitor network connections (no external AI service calls)
netstat -an | grep :8000    # Only local connections

# Check data directory contents
ls -la ~/.ai-mcp-toolkit/   # See what data is stored

# Verify Ollama local operation
ollama ps                   # Shows local models only
```

### 🔄 Data Portability

#### Export Your Data
```bash
# Export conversations
cp ~/.ai-mcp-toolkit/conversations/* /path/to/backup/

# Export configuration
cp ~/.ai-mcp-toolkit/config.yaml /path/to/backup/

# Full data export
tar -czf ai-mcp-toolkit-backup.tar.gz ~/.ai-mcp-toolkit/
```

#### Data Migration
- 📦 **Easy Migration** - Move your data between systems
- 🔄 **Format Independence** - Standard file formats (JSON, YAML)
- 💾 **Backup Friendly** - Simple file-based storage

### 🏷️ Privacy Labels

| Data Type | Collection | Storage | Transmission | Third Party Access |
|-----------|------------|---------|--------------|--------------------|
| Text Content | ❌ No | 🏠 Local Only | ❌ Never | ❌ Never |
| Conversations | 🏠 Local | 🏠 Local Only | ❌ Never | ❌ Never |
| Configuration | 🏠 Local | 🏠 Local Only | ❌ Never | ❌ Never |
| Usage Analytics | ❌ No | ❌ No | ❌ Never | ❌ Never |
| Personal Info | ❌ No | ❌ No | ❌ Never | ❌ Never |
| AI Model Data | 🏠 Local | 🏠 Local Only | ❌ Never | ❌ Never |

### 📞 Privacy Questions?

If you have questions about privacy or data handling:

- 📚 Review the [source code](src/) - Complete transparency
- 🔍 Run network monitoring tools - Verify no external connections
- 💬 [Open a Discussion](https://github.com/yourusername/ai-mcp-toolkit/discussions) - Ask privacy questions
- 🐛 [Report Privacy Concerns](https://github.com/yourusername/ai-mcp-toolkit/issues) - Security issue reporting

---

**Summary**: The AI MCP Toolkit processes all your data locally using your own AI models. Nothing is transmitted to external servers, collected for analytics, or shared with third parties. Your privacy is protected by design.

## 📢 Support

- 📚 [Documentation](docs/)
- 🐛 [Issue Tracker](https://github.com/yourusername/ai-mcp-toolkit/issues)
- 💬 [Discussions](https://github.com/yourusername/ai-mcp-toolkit/discussions)
