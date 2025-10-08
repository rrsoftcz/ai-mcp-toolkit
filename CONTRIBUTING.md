# Contributing to AI MCP Toolkit

Thank you for your interest in contributing to the AI MCP Toolkit! This comprehensive guide will help you get started with contributing to this AI-powered text processing toolkit built on the Model Context Protocol (MCP) standard.

## 📋 Table of Contents

- [Getting Started](#-getting-started)
- [Development Environment Setup](#-development-environment-setup)
- [Project Structure](#-project-structure)
- [Coding Standards](#-coding-standards)
- [Testing](#-testing)
- [Submitting Changes](#-submitting-changes)
- [Documentation](#-documentation)
- [Community](#-community)

## 🚀 Getting Started

### Prerequisites

Before contributing, ensure you have the following installed:

- **Python 3.13.7** (recommended) or Python 3.11+
- **Node.js 18+** (for UI development)
- **Git**
- **Ollama** (for AI model integration)

### Quick Setup

1. **Fork and Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/ai-mcp-toolkit.git
   cd ai-mcp-toolkit
   ```

2. **Set Up Development Environment**
   ```bash
   # Run the smart setup script
   ./setup.sh
   
   # Or manually set up Python environment
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   pip install -e ".[dev]"
   ```

3. **Set Up UI Development** (Optional)
   ```bash
   cd ui
   npm install
   ```

4. **Configure Environment**
   ```bash
   cp .env.example .env
   # Edit .env with your preferences
   ```

5. **Verify Installation**
   ```bash
   ai-mcp-toolkit --help
   ai-mcp-toolkit status
   ```

## 🛠 Development Environment Setup

### Python Backend Development

#### Virtual Environment
```bash
# Create and activate virtual environment
python -m venv venv
source venv/bin/activate  # Linux/macOS
# or
venv\Scripts\activate     # Windows

# Install in development mode with all dependencies
pip install -e ".[dev,ui,docker]"
```

#### Development Dependencies
The project includes development tools configured in `pyproject.toml`:
- **pytest** - Testing framework
- **black** - Code formatting
- **flake8** - Linting
- **mypy** - Type checking
- **pre-commit** - Git hooks

### UI Development

#### SvelteKit Frontend
```bash
cd ui
npm install

# Development server
npm run dev

# Build for production
npm run build

# Type checking
npm run check
```

### Ollama Setup

```bash
# Install Ollama
curl -fsSL https://ollama.ai/install.sh | sh

# Pull recommended models
ollama pull llama3.2:3b
ollama pull qwen2.5:7b
```

## 🏗 Project Structure

```
ai-mcp-toolkit/
├── src/ai_mcp_toolkit/          # Main Python package
│   ├── agents/                  # AI text processing agents
│   │   ├── base_agent.py       # Base agent class
│   │   ├── text_cleaner.py     # Text cleaning agent
│   │   ├── text_analyzer.py    # Text analysis agent
│   │   └── ...                 # Other specialized agents
│   ├── server/                  # Server implementations
│   │   ├── mcp_server.py       # MCP protocol server
│   │   └── http_server.py      # HTTP/REST API server
│   ├── models/                  # AI model integrations
│   │   └── ollama_client.py    # Ollama client wrapper
│   ├── utils/                   # Utility modules
│   │   ├── config.py           # Configuration management
│   │   ├── logger.py           # Logging utilities
│   │   └── gpu_monitor.py      # GPU monitoring
│   ├── cli.py                   # Command-line interface
│   └── __init__.py
├── ui/                          # SvelteKit frontend
│   ├── src/
│   │   ├── lib/                 # Shared components
│   │   ├── routes/             # Application routes
│   │   └── app.html            # Main HTML template
│   ├── package.json
│   └── svelte.config.js
├── docs/                        # Documentation
├── configs/                     # Configuration templates
├── tests/                       # Test suite (to be created)
├── pyproject.toml              # Python project configuration
├── docker-compose.yml          # Docker setup
└── README.md
```

### Key Components

#### Agents (`src/ai_mcp_toolkit/agents/`)
- **Base Agent**: Foundation for all text processing agents
- **Specialized Agents**: Text cleaning, analysis, grammar checking, etc.
- **AI Integration**: Ollama model interactions

#### Server (`src/ai_mcp_toolkit/server/`)
- **MCP Server**: Model Context Protocol implementation
- **HTTP Server**: REST API using FastAPI

#### UI (`ui/`)
- **Modern Interface**: ChatGPT-like design using SvelteKit
- **Real-time Features**: Live model switching, GPU monitoring
- **Responsive Design**: Desktop and mobile support

## 📏 Coding Standards

### Python Code Style

We follow PEP 8 with some modifications defined in `pyproject.toml`:

```python
# Good example
from typing import Optional, Dict, Any
import logging

logger = logging.getLogger(__name__)

class TextProcessor:
    """A text processing utility class."""
    
    def __init__(self, config: Dict[str, Any]) -> None:
        self.config = config
        self.logger = logger
    
    def process_text(self, text: str) -> Optional[str]:
        """Process the input text and return cleaned result."""
        try:
            # Processing logic here
            return processed_text
        except Exception as e:
            self.logger.error(f"Text processing failed: {e}")
            return None
```

#### Code Formatting
```bash
# Format code with black
black src/ tests/

# Sort imports
isort src/ tests/

# Lint with flake8
flake8 src/ tests/

# Type check with mypy
mypy src/
```

### TypeScript/JavaScript (UI)

```typescript
// Good example - TypeScript interface
interface ChatMessage {
    id: string;
    content: string;
    role: 'user' | 'assistant';
    timestamp: Date;
    model?: string;
}

// Use async/await for API calls
async function sendMessage(message: string): Promise<ChatMessage> {
    try {
        const response = await fetch('/api/chat', {
            method: 'POST',
            headers: { 'Content-Type': 'application/json' },
            body: JSON.stringify({ message })
        });
        return await response.json();
    } catch (error) {
        console.error('Failed to send message:', error);
        throw error;
    }
}
```

### Documentation Standards

- **Docstrings**: Use Google-style docstrings for Python
- **Comments**: Explain why, not what
- **Type hints**: Always use type hints in Python
- **README updates**: Update documentation for new features

```python
def analyze_text(text: str, options: Dict[str, Any]) -> TextAnalysisResult:
    """Analyze text and return comprehensive statistics.
    
    Args:
        text: The input text to analyze
        options: Configuration options for analysis
        
    Returns:
        TextAnalysisResult containing statistics and metrics
        
    Raises:
        ValueError: If text is empty or invalid
        AIModelError: If AI processing fails
    """
    if not text.strip():
        raise ValueError("Text cannot be empty")
    # Implementation here
```

## 🧪 Testing

### Running Tests

```bash
# Run all tests
pytest

# Run with coverage
pytest --cov=ai_mcp_toolkit --cov-report=html

# Run specific test file
pytest tests/test_agents.py

# Run with verbose output
pytest -v

# Run only fast tests (if markers are set up)
pytest -m "not slow"
```

### Writing Tests

#### Test Structure
Create tests in the `tests/` directory mirroring the `src/` structure:

```
tests/
├── __init__.py
├── conftest.py              # Pytest fixtures
├── test_agents/
│   ├── __init__.py
│   ├── test_text_cleaner.py
│   ├── test_text_analyzer.py
│   └── test_base_agent.py
├── test_server/
│   ├── test_http_server.py
│   └── test_mcp_server.py
└── test_utils/
    ├── test_config.py
    └── test_logger.py
```

#### Example Test
```python
import pytest
from ai_mcp_toolkit.agents.text_cleaner import TextCleanerAgent

class TestTextCleanerAgent:
    """Test cases for TextCleanerAgent."""
    
    @pytest.fixture
    def agent(self):
        """Create a TextCleanerAgent instance for testing."""
        return TextCleanerAgent()
    
    def test_clean_basic_text(self, agent):
        """Test basic text cleaning functionality."""
        dirty_text = "Hello!!! World??? This is... messy."
        clean_text = agent.clean_text(dirty_text)
        
        assert clean_text == "Hello World This is messy"
        assert "!!!" not in clean_text
        assert "???" not in clean_text
    
    def test_clean_empty_text(self, agent):
        """Test cleaning empty text."""
        result = agent.clean_text("")
        assert result == ""
    
    @pytest.mark.asyncio
    async def test_async_clean_text(self, agent):
        """Test asynchronous text cleaning."""
        result = await agent.async_clean_text("Test text!")
        assert isinstance(result, str)
```

#### API Testing
```python
from fastapi.testclient import TestClient
from ai_mcp_toolkit.server.http_server import app

client = TestClient(app)

def test_health_endpoint():
    """Test health check endpoint."""
    response = client.get("/health")
    assert response.status_code == 200
    assert response.json()["status"] == "healthy"

def test_agents_endpoint():
    """Test agents listing endpoint."""
    response = client.get("/agents")
    assert response.status_code == 200
    data = response.json()
    assert "agents" in data
    assert len(data["agents"]) > 0
```

### UI Testing
```bash
cd ui

# Run UI tests
npm run test

# Run with coverage
npm run test:coverage

# E2E testing (if configured)
npm run test:e2e
```

## 📤 Submitting Changes

### Git Workflow

1. **Create a Feature Branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. **Make Your Changes**
   - Follow coding standards
   - Add tests for new functionality
   - Update documentation

3. **Commit Changes**
   ```bash
   # Use conventional commit messages
   git commit -m "feat: add text anonymization agent"
   git commit -m "fix: resolve GPU monitoring memory leak"
   git commit -m "docs: update API documentation"
   ```

4. **Run Pre-commit Checks**
   ```bash
   # Format and lint
   black src/ tests/
   flake8 src/ tests/
   mypy src/
   
   # Run tests
   pytest
   
   # UI checks (if applicable)
   cd ui && npm run check && npm run lint
   ```

5. **Push and Create PR**
   ```bash
   git push origin feature/your-feature-name
   # Create Pull Request on GitHub
   ```

### Commit Message Format

Use [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Formatting changes
- `refactor`: Code refactoring
- `test`: Adding tests
- `chore`: Maintenance tasks

**Examples:**
```
feat(agents): add text translation agent
fix(server): resolve CORS headers issue
docs(api): update endpoint documentation
test(agents): add tests for sentiment analyzer
```

### Pull Request Guidelines

**Before Submitting:**
- [ ] Code follows project style guidelines
- [ ] All tests pass
- [ ] Documentation is updated
- [ ] Commit messages are clear and descriptive
- [ ] No merge conflicts with main branch

**PR Description Template:**
```markdown
## Description
Brief description of changes made.

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation update
- [ ] Performance improvement
- [ ] Refactoring

## Testing
- [ ] Unit tests pass
- [ ] Integration tests pass
- [ ] Manual testing completed

## Documentation
- [ ] Code comments updated
- [ ] API documentation updated
- [ ] User documentation updated

## Screenshots (if applicable)
Add screenshots for UI changes.
```

## 📚 Documentation

### Types of Documentation

1. **Code Documentation**: Docstrings and comments
2. **API Documentation**: Generated from code
3. **User Documentation**: Setup and usage guides
4. **Developer Documentation**: Architecture and contributing guides

### Updating Documentation

```bash
# Generate API docs (if configured)
sphinx-build -b html docs/ docs/_build/html/

# Update README for new features
# Update CHANGELOG.md for releases
# Update configuration documentation
```

### Documentation Standards

- Keep documentation up-to-date with code changes
- Use clear, concise language
- Include examples and code snippets
- Document breaking changes
- Maintain changelog

## 👥 Community

### Getting Help

- **Documentation**: Start with [README.md](README.md) and [docs/](docs/)
- **Issues**: Search existing issues before creating new ones
- **Discussions**: Use GitHub Discussions for questions
- **Discord/Chat**: (Add community chat links if available)

### Reporting Issues

**Bug Reports:**
```markdown
**Describe the bug**
A clear description of the bug.

**To Reproduce**
Steps to reproduce the behavior.

**Expected behavior**
What you expected to happen.

**Environment**
- OS: [e.g. Ubuntu 20.04]
- Python version: [e.g. 3.13.7]
- AI MCP Toolkit version: [e.g. 1.0.0]
- Ollama version: [e.g. 0.1.0]

**Additional context**
Add any other context about the problem.
```

**Feature Requests:**
```markdown
**Is your feature request related to a problem?**
Description of the problem.

**Describe the solution you'd like**
Clear description of desired functionality.

**Describe alternatives considered**
Alternative solutions or features considered.

**Additional context**
Any other context or screenshots.
```

### Code Review Process

1. **Automated Checks**: CI/CD runs tests and checks
2. **Peer Review**: At least one approved review required
3. **Maintainer Review**: Core maintainer final approval
4. **Merge**: Squash and merge after approval

### Recognition

Contributors are recognized in:
- [CONTRIBUTORS.md](CONTRIBUTORS.md) (if it exists)
- Release notes
- GitHub contributors section

## 🔧 Advanced Development

### Custom Agents

To create a new text processing agent:

1. **Create Agent File**
   ```python
   # src/ai_mcp_toolkit/agents/my_agent.py
   from .base_agent import BaseAgent
   from typing import Dict, Any
   
   class MyAgent(BaseAgent):
       def __init__(self):
           super().__init__(
               name="My Agent",
               description="Description of what this agent does"
           )
       
       def process_text(self, text: str, **kwargs) -> str:
           # Your processing logic here
           return processed_text
   ```

2. **Register Agent**
   ```python
   # src/ai_mcp_toolkit/agents/__init__.py
   from .my_agent import MyAgent
   
   # Add to __all__ list
   __all__ = [..., "MyAgent"]
   ```

3. **Add Tests**
   ```python
   # tests/test_agents/test_my_agent.py
   from ai_mcp_toolkit.agents.my_agent import MyAgent
   
   class TestMyAgent:
       def test_process_text(self):
           agent = MyAgent()
           result = agent.process_text("test input")
           assert result == "expected output"
   ```

### Configuration Extensions

Add new configuration options in `src/ai_mcp_toolkit/utils/config.py`:

```python
@dataclass
class Config:
    # Existing fields...
    
    # New configuration option
    my_new_option: str = "default_value"
    
    @classmethod
    def from_env(cls) -> "Config":
        return cls(
            # Existing mappings...
            my_new_option=os.getenv("MY_NEW_OPTION", "default_value")
        )
```

### API Extensions

Add new endpoints in `src/ai_mcp_toolkit/server/http_server.py`:

```python
@app.get("/api/my-endpoint")
async def my_endpoint():
    """My custom endpoint."""
    return {"message": "Hello from my endpoint"}
```

## 📝 License

By contributing to AI MCP Toolkit, you agree that your contributions will be licensed under the MIT License.

## 🙏 Acknowledgments

- Model Context Protocol (MCP) community
- Ollama project for local AI models
- SvelteKit for the modern UI framework
- All contributors and community members

---

**Ready to contribute?** Check out our [good first issues](https://github.com/yourusername/ai-mcp-toolkit/labels/good%20first%20issue) to get started!

For questions about contributing, feel free to open a discussion or contact the maintainers.