# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This repository contains comprehensive documentation for the Simply Schedule Appointments WordPress plugin. It organizes documentation from the website into a structured format for easy reference. The documentation is converted from HTML to Markdown format and organized into logical categories.

## Documentation Structure

Documentation is organized into these main categories:

- **getting-started/**: Installation, setup, and basic configuration
- **features/**: Core functionality and features documentation
- **developers/**: API documentation, hooks, filters, and developer tools
- **integrations/**: Connect with Google Calendar, payment processors, and other services
- **customization/**: Styling, CSS, and customization guides
- **troubleshooting/**: Common issues and their solutions

## Scripts and Tools

### Python Scripts

The repository includes Python scripts for scraping and processing documentation:

```
python scripts/scraper.py <csv_path> [--output <dir>] [--delay <seconds>] [--dev-only]
```
- Scrapes URLs listed in a CSV file and converts the content to Markdown
- `--output`: Specify the output directory (default: 'knowledge_base')
- `--delay`: Time delay between requests (default: 1 second)
- `--dev-only`: Filter for developer-oriented documentation only

```
python scripts/batch_scraper.py <csv_path> [--output <dir>] [--delay <seconds>] [--workers <num>]
```
- Parallel version of the scraper for processing multiple URLs simultaneously
- `--workers`: Number of parallel workers (default: 5)

```
python scripts/combine_docs.py <output_dir> <source_dir1> [<source_dir2> ...]
```
- Combines documentation from multiple source directories into one

```
python scripts/check_missing.py <csv_path> <docs_dir>
```
- Checks for missing documents by comparing URLs in the CSV with existing files

```
python scripts/scrape_missing.py <csv_path> <docs_dir> [--delay <seconds>]
```
- Identifies and scrapes only missing documents

```
python scripts/finish_scraping.py <csv_path> <output_dir> [--delay <seconds>]
```
- Completes any unfinished scraping jobs

```
python scripts/filter_help_center.py <input_csv> <output_csv>
```
- Filters help center URLs from a larger CSV dataset

### Bash Scripts

```
bash scripts/organize_docs.sh
```
- Organizes scraped documentation into a GitHub-friendly structure
- Creates category folders with README files
- Improves filenames for better readability

```
bash scripts/improve_docs.sh
```
- Improves document formatting and structure

```
bash scripts/enhanced_cleanup.sh
```
- Performs advanced cleanup of documentation files

```
bash scripts/final_cleanup.sh
```
- Final pass of cleanup before documentation is completed

```
bash scripts/fix_titles.sh
```
- Ensures consistent title formatting across documentation files

## Dependencies

The Python scripts require the following dependencies (from requirements.txt):

- beautifulsoup4 - For HTML parsing
- requests - For HTTP requests
- pandas - For data manipulation and CSV handling
- tqdm - For progress bars
- Other standard libraries (datetime, json, etc.)

Install dependencies with:
```
pip install -r requirements.txt
```

## Documentation Style Guidelines

1. **Folder Structure**:
   - Each category folder must contain a README.md file
   - README.md should serve as an index for that category
   - List and link to all documents within that folder
   - Include brief descriptions of each document's purpose

2. **Root README.md Requirements**:
   - Include a linked directory tree structure
   - Every item in the directory structure should be clickable
   - Use proper nesting to reflect the actual directory hierarchy
   - Example format:
     ```
     - [📁 getting-started/](getting-started/)
       - [📄 README.md](getting-started/README.md)
       - [📄 installation.md](getting-started/installation.md)
       - [📄 first-appointment.md](getting-started/first-appointment.md)
     - [📁 features/](features/)
       - [📄 README.md](features/README.md)
       - ...
     ```

3. **Document Cross-Linking**:
   - Link related topics across documents
   - Use relative paths for all internal links
   - Ensure navigation paths are intuitive

## Best Practices When Working with This Repository

1. **Working with Documentation**:
   - Keep the hierarchical structure intact
   - Maintain consistent formatting across docs
   - Use proper Markdown syntax for headings, lists, and code blocks
   - Update index files (README.md) when adding new documents

2. **Running Scripts**:
   - Run scripts from the repository root
   - Use appropriate delay parameters to be considerate to web servers
   - Use the batch versions for large-scale scraping

3. **Creating New Documentation**:
   - Follow the established naming conventions
   - Include appropriate headers and metadata
   - Organize content into the appropriate category
   - Add new documents to the relevant index/README file
   - Update the root README.md directory tree

4. **File Naming Convention**:
   - Use kebab-case for filenames (e.g., `custom-fields-guide.md`)
   - Include relevant prefixes for categorization
   - Avoid duplicating category names in filenames