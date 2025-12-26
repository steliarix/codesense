# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Planned
- Chunk-based parsing (functions/classes separately) - v0.2
- Incremental index updates - v0.3
- Django/FastAPI specific features - v0.4
- Python API for programmatic use - v0.5
- MCP integration for AI tools - v0.6

## [0.1.1] - 2025-12-26

### Improved
- Enhanced error handling in `storage.py`:
  - Added validation for missing `metadata.json` file
  - Added JSON parse error handling with descriptive messages
  - Added validation for required metadata fields
  - Added default values for missing metadata fields
- Enhanced search reliability in `searcher.py`:
  - Added empty query validation
  - Added `top_k` parameter validation (must be > 0)
  - Added empty index check to prevent errors
  - Auto-adjust `top_k` if it exceeds available vectors
  - Added handling for invalid FAISS indices (negative values)
- Enhanced CLI validation in `cli.py`:
  - Added empty search query validation at CLI level
  - Improved error messages for better user experience

### Fixed
- Fixed potential crash when searching with `top_k` larger than index size
- Fixed potential crash when loading corrupted metadata files
- Fixed edge case with empty search queries

### Technical
- Added comprehensive error handling throughout the codebase
- Improved input validation for all user-facing commands
- Better error messages for debugging

## [0.1.0] - 2025-12-26

### Added
- Basic indexing for Python files
- Embedding creation via sentence-transformers (all-MiniLM-L6-v2)
- Local FAISS index storage
- Semantic code search
- CLI interface with commands:
  - `index` - index a project directory
  - `search` - search within an index
  - `list` - list all available indexes
  - `info` - show detailed information about an index
  - `delete` - delete an index
- Automatic ignoring of service directories (.git, venv, __pycache__)
- Metadata storage in JSON format
- Python 3.9+ support

### Technical
- src-layout project structure
- pyproject.toml for modern Python packaging
- FAISS for vector similarity search
- sentence-transformers for embeddings
- Click for CLI framework
- Comprehensive testing on sample Python codebase

### Features Demonstrated
- Semantic understanding of code concepts
- Natural language queries support
- Synonym and concept recognition
- Relevance-based result ranking
- Superior to grep for conceptual searches

---

[unreleased]: https://github.com/steliarix/semantic-search/compare/v0.1.1...HEAD
[0.1.1]: https://github.com/steliarix/semantic-search/compare/v0.1.0...v0.1.1
[0.1.0]: https://github.com/steliarix/semantic-search/releases/tag/v0.1.0
