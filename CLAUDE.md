# CLAUDE.md - AI Assistant Guide for SHARP Documentation

## Project Overview

**Project Name**: SHARP (SRHU Academic Research Projects Portal)
**Organization**: Swami Rama Himalayan University (SRHU)
**Purpose**: Documentation for a research project management system
**Documentation System**: Sphinx (Python documentation generator)
**License**: MIT License
**Copyright**: 2017-2020, SRHU

## Repository Structure

```
/home/user/sharp/
├── conf.py                    # Sphinx configuration file
├── index.rst                  # Main documentation entry point
├── README.md                  # Minimal project readme
├── LICENSE                    # MIT License
├── _config.yml               # Jekyll/GitHub Pages configuration
├── logo.png                  # SRHU logo
├── .gitignore                # Git ignore rules (GitBook-based)
│
├── login/                    # Login documentation
│   ├── index.rst
│   └── modules/              # Login-related modules
│       ├── logon_screen
│       ├── new_user
│       ├── forgot_password
│       ├── first_log_in
│       └── disable_user
│
├── Dashboard/                # Dashboard documentation
│   ├── User_home_page.rst
│   ├── Admin_home_page.rst
│   ├── changelog.rst
│   ├── changes/              # Detailed changelog entries
│   │   └── 100818.rst
│   ├── Admin/                # Admin user documentation
│   │   ├── Dashboard.rst
│   │   ├── User Management.rst
│   │   ├── Projects.rst
│   │   ├── Publication.rst
│   │   ├── Downloads.rst
│   │   ├── Academic Unit.rst
│   │   ├── Create New User.rst
│   │   ├── Edit Update User.rst
│   │   ├── List Users.rst
│   │   ├── List Users Disabled.rst
│   │   ├── Add New Project.rst
│   │   ├── Add New Publication.rst
│   │   ├── Intramural Project.rst
│   │   ├── Extramural Project.rst
│   │   ├── Download Projects.rst
│   │   ├── List of Publication.rst
│   │   ├── Projects due Completion.rst
│   │   ├── edit_project.rst
│   │   ├── Himalayan School Of Engineering and Technology.rst
│   │   ├── Himalayan Institute Of Medical Science.rst
│   │   ├── Himalayan College Of Nursing.rst
│   │   ├── Himalayan School Of Management Studies.rst
│   │   ├── Himalayan School of Bio Science.rst
│   │   └── [image directories: screenshot, Project_Pics, etc.]
│   │
│   └── Faculty/              # Faculty user documentation
│       ├── Faculty Dashboard.rst
│       ├── projects.rst
│       ├── Publications.rst
│       ├── My Project.rst
│       ├── Add New Project.rst
│       ├── Add New Publication.rst
│       ├── Edit_project.rst
│       ├── Edit Publication.rst
│       ├── List of All Projects.rst
│       ├── List of My Projects due completion.rst
│       ├── List of Publications.rst
│       ├── Link to Project.rst
│       ├── Unlink Publication from Project.rst
│       ├── Request_Complaint.rst
│       ├── Help.rst
│       ├── Self Help Docs.rst
│       └── [image directories: Project_Pics, screenshot, etc.]
│
└── _themes/                  # Custom Sphinx themes
    ├── sphinx_rtd_theme/     # Read the Docs theme
    └── sylius_rtd_theme/     # Sylius-based RTD theme (used)
```

## Technology Stack

### Documentation Tools
- **Sphinx**: Python-based documentation generator
- **reStructuredText (RST)**: Markup language for documentation
- **Pygments**: Syntax highlighting (PHP lexer configured)
- **Jekyll**: Static site generator (GitHub Pages support)

### Themes
- **Primary Theme**: `sylius_rtd_theme` (custom Read the Docs theme)
- **Backup Theme**: `sphinx_rtd_theme` (standard Read the Docs theme)

### Build System
- **Sphinx** with Python configuration (`conf.py`)
- No explicit requirements.txt (dependencies should include sphinx, pygments)
- Build output excluded via `.gitignore` (_book, *.pdf, *.epub, *.mobi)

## Documentation Structure

### Main Entry Point
The documentation hierarchy starts at `index.rst`:
```rst
SRHU Academic Research Projects Portal [SHARP]
├── Login to Portal (login/index)
├── Faculty User (Dashboard/User_home_page)
├── Admin User (Dashboard/Admin_home_page)
└── Change Log (Dashboard/changelog)
```

### Content Organization

#### 1. Login Module (`login/`)
- Logon screen
- New user registration
- Forgot password workflow
- First login process
- User disable functionality

#### 2. Faculty Dashboard (`Dashboard/Faculty/`)
Documentation for faculty users covering:
- Dashboard overview and navigation
- Project management (add, edit, list, link)
- Publication management (add, edit, list)
- Project-publication linking
- Request/complaint submission
- Self-help documentation

#### 3. Admin Dashboard (`Dashboard/Admin/`)
Documentation for administrative users covering:
- User management (create, edit, list, disable)
- Project oversight (intramural, extramural)
- Publication management
- Downloads and reports
- Academic unit management (HSET, HIMS, HCN, HSMS, HSB)
- Project completion tracking

#### 4. Changelog (`Dashboard/changes/`)
Documented changes with:
- Date-based change logs (format: DDMMYY.rst)
- Feature modifications
- Module updates
- Screenshots of changes

## File Naming Conventions

### RST Files
- **Case Sensitivity**: File names use title case with spaces (e.g., "Faculty Dashboard.rst")
- **Underscores**: Sometimes used for multi-word files (e.g., "Edit_project.rst", "User_home_page.rst")
- **Consistency**: No strict convention - mix of spaces and underscores

### Directory Names
- **Camel Case**: Some directories use camel case (e.g., "Acadmic_unit_pic")
- **Title Case**: Others use title case with spaces (e.g., "Project_Pics")
- **Image Directories**: Often suffixed with "_pics" or "_Pics"

### Image Files
- Screenshots stored in dedicated directories
- Common formats: .JPG, .jpg, .png
- Referenced in RST files using relative paths

## Documentation Style Guide

### RST Formatting Patterns

#### Section Headers
```rst
Main Title
==========

Subsection
----------

Sub-subsection
~~~~~~~~~~~~~~
```

#### Common Directives

**Notes**:
```rst
.. note::

   Important information for users
```

**Images**:
```rst
.. image:: path/to/image.JPG
   :width: 100px
   :height: 50px
   :align: center
   :alt: Description
```

**Table of Contents**:
```rst
.. toctree::
   :maxdepth: 3
   :caption: Section Title

   path/to/document
   another/document
```

### Content Patterns
- User-focused documentation with screenshots
- Step-by-step instructions with visual aids
- Notes and warnings for important information
- Hierarchical organization with toctree directives

## Sphinx Configuration (`conf.py`)

### Key Settings
```python
project = 'Documentation for Research Projects Portal'
copyright = u'2017-2020, SRHU'
version = '0.1'
release = '0.1'

source_suffix = '.rst'
master_doc = 'index'
html_theme = 'sylius_rtd_theme'
html_theme_path = ["_themes"]

# Exclude patterns
exclude_patterns = [
    '_includes/*.rst',
    '_developement/*.*',
    '_production/*.*',
    '_test/*.*',
]
```

### Extensions
Currently commented out, but previously included:
- sphinx.ext.autodoc
- sphinx.ext.doctest
- sphinx.ext.todo
- sphinx.ext.coverage
- sphinx.ext.imgmath
- sphinx.ext.ifconfig

### PHP Syntax Highlighting
PHP lexer configured for syntax highlighting with `startinline=True`

## Development Workflows

### Adding New Documentation

#### 1. Create RST File
```bash
# Navigate to appropriate directory
cd Dashboard/Faculty/  # or Dashboard/Admin/

# Create new RST file
touch "New Feature.rst"
```

#### 2. Write Content
```rst
Feature Title
=============

.. note::

   Brief description of the feature

**Section Heading**

Content with screenshots...

.. image:: screenshot/feature.JPG
```

#### 3. Add to Table of Contents
Update the parent `index.rst` or section file:
```rst
.. toctree::
   :maxdepth: 3
   :caption: Content

   existing/document
   New Feature
```

#### 4. Add Images (if needed)
- Place images in appropriate subdirectory (e.g., `screenshot/`, `Project_Pics/`)
- Use relative paths in RST files
- Common formats: .JPG, .jpg, .png

### Building Documentation

#### Local Build (Sphinx)
```bash
# From repository root
sphinx-build -b html . _build/html

# Or using make (if Makefile exists)
make html
```

#### Clean Build
```bash
# Remove previous build artifacts
rm -rf _build/

# Rebuild
sphinx-build -b html . _build/html
```

### Publishing
The repository includes `_config.yml` for GitHub Pages deployment:
- Theme: jekyll-theme-cayman
- Likely published at: `https://[username].github.io/sharp/`

## Changelog Management

### Adding a Changelog Entry

#### 1. Create New Changelog File
```bash
cd Dashboard/changes/
touch "DDMMYY.rst"  # e.g., 150119.rst for Jan 15, 2019
```

#### 2. Document Changes
```rst
==========================
Change Log #N - DD-MM-YYYY
==========================

Change #N.1
===========
Brief description

1. Specific change point 1
2. Specific change point 2

Change #N.2
===========
Another module change

Screenshots:

.. image:: filename.jpg
```

#### 3. Update Changelog Index
Edit `Dashboard/changelog.rst`:
```rst
.. toctree::
   :maxdepth: 3
   :caption: content

   changes/100818
   changes/DDMMYY  # Add new entry
```

### Changelog Format (from 100818.rst)
- **Date**: DD-MM-YYYY format in title
- **Changes**: Numbered sections (Change #N.1, #N.2, etc.)
- **Content**:
  - Module name
  - Numbered list of specific changes
  - Sub-numbered details where applicable
- **Images**: Screenshots showing visual changes

## Git Workflow

### Branch Strategy
- **Development Branch**: `claude/claude-md-mi0k4q5vfsurw5wf-014XW3QdwBexppZsy6DW6B3Q`
- All changes should be committed to this branch
- Never push directly to main/master without permission

### Commit Message Style
Based on recent commits:
```
Update [filename].rst
Add files via upload
Update changelog.rst
```

**Recommended format**:
- Concise, descriptive messages
- Reference specific files or features
- Use present tense ("Update" not "Updated")

### Standard Git Operations
```bash
# Check status
git status

# Stage changes
git add CLAUDE.md

# Commit
git commit -m "Add CLAUDE.md documentation guide"

# Push to feature branch
git push -u origin claude/claude-md-mi0k4q5vfsurw5wf-014XW3QdwBexppZsy6DW6B3Q
```

## AI Assistant Guidelines

### When Modifying Documentation

1. **Maintain Consistency**
   - Follow existing RST formatting patterns
   - Use similar note/warning directive styles
   - Match existing header hierarchy

2. **Image Management**
   - Place images in appropriate subdirectories
   - Use descriptive filenames
   - Reference with relative paths
   - Include alt text for accessibility

3. **Navigation Updates**
   - Always update parent toctree when adding new files
   - Maintain :maxdepth: 3 consistency
   - Use descriptive :caption: labels

4. **Content Quality**
   - User-focused language
   - Step-by-step instructions
   - Visual aids (screenshots)
   - Notes for important information

### When Analyzing the Codebase

1. **Documentation Structure**
   - This is a **documentation-only** repository
   - No application code (PHP/backend) is present
   - Focus is on user-facing documentation

2. **User Roles**
   - Faculty users (researchers)
   - Admin users (administrators)
   - Each role has separate documentation sections

3. **Key Features Documented**
   - User authentication and management
   - Research project tracking
   - Publication management
   - Project-publication linking
   - Reporting and downloads
   - Academic unit organization

### When Adding Features

1. **New Documentation Page**
   - Create in appropriate directory (Admin/ or Faculty/)
   - Follow RST formatting conventions
   - Add to parent toctree
   - Include screenshots if describing UI

2. **New Module/Section**
   - Create subdirectory if needed
   - Create index.rst for the section
   - Document in hierarchical structure
   - Update main index.rst

3. **Changelog Entry**
   - Document all significant changes
   - Use consistent numbering
   - Include screenshots of visual changes
   - Update changelog index

### Common Tasks

#### Task: Add new admin feature documentation
```bash
# 1. Create RST file
cd Dashboard/Admin/
touch "New Admin Feature.rst"

# 2. Create content with screenshots
# [Edit file with RST content]

# 3. Update Admin_home_page.rst toctree
# [Add reference to new file]

# 4. Commit changes
git add Dashboard/Admin/
git commit -m "Document new admin feature"
```

#### Task: Update existing documentation
```bash
# 1. Locate the RST file
# 2. Edit content maintaining RST formatting
# 3. Update images if needed
# 4. Verify toctree references
# 5. Commit with descriptive message
```

#### Task: Add changelog entry
```bash
# 1. Create dated changelog file
cd Dashboard/changes/
touch "151124.rst"  # DDMMYY format

# 2. Document changes
# [Edit with changelog content]

# 3. Update Dashboard/changelog.rst
# [Add toctree entry]

# 4. Commit
git add Dashboard/
git commit -m "Add changelog for November 15, 2024 updates"
```

## Academic Units Reference

The SHARP system manages research across these academic units:
- **HSET**: Himalayan School of Engineering and Technology
- **HIMS**: Himalayan Institute of Medical Science
- **HCN**: Himalayan College of Nursing
- **HSMS**: Himalayan School of Management Studies
- **HSB**: Himalayan School of Bio Science

Each unit has dedicated documentation in `Dashboard/Admin/`.

## Best Practices for AI Assistants

### DO:
✓ Follow existing RST formatting patterns
✓ Update toctree when adding new files
✓ Use descriptive commit messages
✓ Include screenshots for UI documentation
✓ Maintain hierarchical organization
✓ Test documentation builds locally
✓ Keep changelog updated for significant changes
✓ Use relative paths for images
✓ Match existing naming conventions (even if inconsistent)

### DON'T:
✗ Mix different header styles in same document
✗ Forget to update parent toctree references
✗ Use absolute paths for images
✗ Create orphan documentation files
✗ Change existing file naming patterns
✗ Push to main branch without permission
✗ Ignore existing documentation structure
✗ Add files without proper RST formatting
✗ Commit without testing documentation builds

## Build Dependencies (Inferred)

While not explicitly documented in requirements.txt, the project requires:
```
sphinx>=1.8.0
pygments>=2.0.0
```

Optional for full functionality:
```
sphinx-rtd-theme
```

## Troubleshooting

### Common Issues

**Issue**: Toctree warnings
- **Cause**: File referenced in toctree doesn't exist or path is wrong
- **Fix**: Verify file paths and ensure files exist

**Issue**: Images not displaying
- **Cause**: Incorrect relative path or missing image file
- **Fix**: Check image path relative to RST file location

**Issue**: Build errors
- **Cause**: Invalid RST syntax
- **Fix**: Validate RST syntax, check indentation

**Issue**: Theme not loading
- **Cause**: Theme path incorrect in conf.py
- **Fix**: Verify _themes/ directory structure and html_theme_path

## Quick Reference

### RST Syntax Cheat Sheet
```rst
Title
=====

Section
-------

**Bold text**
*Italic text*

.. note::

   Note content

.. image:: path.jpg

.. toctree::
   :maxdepth: 3

   path/to/doc

1. Numbered list
2. Item 2

- Bullet list
- Item 2
```

### File Path Patterns
- Login docs: `login/modules/[feature].rst`
- Admin docs: `Dashboard/Admin/[feature].rst`
- Faculty docs: `Dashboard/Faculty/[feature].rst`
- Changelogs: `Dashboard/changes/DDMMYY.rst`
- Images: `[section]/screenshot/` or `[section]/Project_Pics/`

## Version History

- **Version**: 0.1
- **Copyright**: 2017-2020, SRHU
- **Last Major Update**: October 8, 2018 (based on changelog)
- **CLAUDE.md Created**: November 15, 2024

---

**Note**: This documentation guide is for AI assistants working with the SHARP documentation repository. Always verify changes by building the documentation locally before committing.
