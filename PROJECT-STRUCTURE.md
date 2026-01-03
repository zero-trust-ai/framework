# Project Structure

```
zero-trust-framework/
│
├── README.md                    # Main project documentation
├── LICENSE                      # AGPL-3.0 license
├── ROADMAP.md                   # Development roadmap
├── CONTRIBUTING.md              # Contribution guidelines
├── setup.py                     # Package installation config
├── requirements.txt             # Production dependencies
├── requirements-dev.txt         # Development dependencies
├── pytest.ini                   # Pytest configuration
├── .gitignore                   # Git ignore rules
│
├── .github/
│   └── workflows/
│       └── ci.yml              # GitHub Actions CI/CD
│
├── src/
│   └── zero_trust/
│       ├── __init__.py         # Package initialization
│       ├── core.py             # [Stage 1] Guardian core
│       ├── detectors/          # [Stage 1] Threat detectors
│       ├── policies/           # [Stage 1] Security policies
│       ├── monitors/           # [Stage 1] Behavioral monitoring
│       ├── mcp/                # [Stage 2] MCP security
│       ├── rag/                # [Stage 3] RAG integration
│       ├── multi_agent/        # [Stage 4] Multi-agent security
│       └── utils/              # Shared utilities
│
├── tests/
│   ├── test_framework.py       # Basic framework tests
│   ├── test_guardian.py        # [Stage 1] Guardian tests
│   ├── test_detectors.py       # [Stage 1] Detector tests
│   ├── test_mcp.py             # [Stage 2] MCP tests
│   └── test_integration.py     # Integration tests
│
├── docs/
│   ├── ARCHITECTURE.md         # System architecture
│   ├── THREAT-MODEL.md         # Threat analysis
│   ├── ZERO-TRUST-PRINCIPLES.md # Security principles
│   ├── API.md                  # [Stage 1+] API documentation
│   ├── DEPLOYMENT.md           # [Stage 5] Deployment guide
│   └── tutorials/              # Step-by-step guides
│
└── examples/
    ├── basic_usage.py          # Basic Guardian usage
    ├── mcp_security.py         # [Stage 2] MCP examples
    ├── rag_policies.py         # [Stage 3] RAG examples
    └── multi_agent.py          # [Stage 4] Multi-agent examples
```

## Directory Descriptions

### Root Files

- **README.md**: Project overview, quick start, and links to documentation
- **LICENSE**: AGPL-3.0 license with dual-licensing information
- **ROADMAP.md**: Staged development plan with timelines and milestones
- **CONTRIBUTING.md**: Guidelines for contributing to the project
- **setup.py**: Python package configuration for pip installation
- **requirements.txt**: Production dependencies
- **requirements-dev.txt**: Development and testing dependencies
- **pytest.ini**: Test configuration and settings
- **.gitignore**: Files and directories to exclude from git

### src/zero_trust/

Main package source code. Organized by development stage:

- **Stage 0 (Current)**: `__init__.py` only
- **Stage 1**: `core.py`, `detectors/`, `policies/`, `monitors/`
- **Stage 2**: `mcp/` for MCP security
- **Stage 3**: `rag/` for RAG integration
- **Stage 4**: `multi_agent/` for multi-agent security

### tests/

Test suite using pytest:

- Unit tests for individual components
- Integration tests for component interaction
- Security tests for threat detection
- Performance tests for scalability

### docs/

Comprehensive documentation:

- **ARCHITECTURE.md**: System design and component overview
- **THREAT-MODEL.md**: Threat landscape and attack vectors
- **ZERO-TRUST-PRINCIPLES.md**: Security principles and best practices
- **API.md**: API reference (added in Stage 1+)
- **tutorials/**: Step-by-step guides for common use cases

### examples/

Working examples demonstrating framework usage:

- Basic Guardian initialization and usage
- MCP security implementation
- RAG-based policy management
- Multi-agent security scenarios

### .github/workflows/

CI/CD automation:

- **ci.yml**: Continuous integration workflow
  - Run tests on multiple Python versions
  - Code quality checks (black, flake8, mypy)
  - Security scanning (bandit, safety)
  - Coverage reporting

## Development Workflow

### Stage 0 (Current)
1. Documentation and planning
2. Repository setup
3. Community feedback

### Stage 1+
1. Create feature branch
2. Implement functionality
3. Write tests (TDD encouraged)
4. Update documentation
5. Submit pull request
6. Code review
7. Merge to main

## File Naming Conventions

- **Python files**: `lowercase_with_underscores.py`
- **Test files**: `test_*.py`
- **Documentation**: `UPPERCASE.md` for main docs, `lowercase.md` for specific guides
- **Classes**: `PascalCase`
- **Functions**: `snake_case`
- **Constants**: `UPPER_SNAKE_CASE`

## Import Organization

```python
# Standard library imports
import os
import sys

# Third-party imports
import pydantic
import structlog

# Local application imports
from zero_trust.core import Guardian
from zero_trust.detectors import PromptInjectionDetector
```

## Adding New Components

When adding new features:

1. **Create module** in appropriate directory
2. **Add tests** in parallel test directory
3. **Update __init__.py** to expose public API
4. **Document in docs/** with examples
5. **Add example** in examples/ directory
6. **Update ROADMAP.md** if applicable

## Stage-Based Organization

The project structure grows with each stage:

**Stage 0**: Foundation (documentation, setup)
**Stage 1**: Core directory structure populated
**Stage 2**: MCP modules added
**Stage 3**: RAG modules added
**Stage 4**: Multi-agent modules added
**Stage 5**: Production/deployment artifacts added

This allows the project to scale organically while maintaining organization.

---

**Last Updated**: January 2025
**Current Stage**: Stage 0 - Foundation
