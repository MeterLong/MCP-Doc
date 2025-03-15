# Docx MCP Service

[![smithery badge](https://smithery.ai/badge/@MeterLong/mcp-doc)](https://smithery.ai/proto/@MeterLong/mcp-doc)
[English](README.md) | [中文](README_ZH.md)

[![smithery badge](https://smithery.ai/badge/@MeterLong/mcp-doc)](https://smithery.ai/server/@MeterLong/mcp-doc)

A Docx document processing service based on the FastMCP library, supporting the creation, editing, and management of Word documents using AI assistants in Cursor.

## Features

- **Complete Document Operations**: Support for creating, opening, saving documents, as well as adding, editing, and deleting content
- **Formatting**: Support for setting fonts, colors, sizes, alignment, and other formatting options
- **Table Processing**: Support for creating, editing, merging, and splitting table cells
- **Image Insertion**: Support for inserting images and setting their sizes
- **Layout Control**: Support for setting page margins, adding page breaks, and other layout elements
- **Query Functions**: Support for retrieving document information, paragraph content, and table data
- **Convenient Editing**: Support for find and replace functionality
- **Section Editing**: Support for replacing content in specific sections while preserving original formatting and styles

## Installation

### Installing via Smithery

To install mcp-doc for Claude Desktop automatically via [Smithery](https://smithery.ai/proto/@MeterLong/mcp-doc):

```bash
npx -y @smithery/cli install @MeterLong/mcp-doc --client claude
```

### Installation Dependencies

Ensure Python 3.10+ is installed, then install the following dependencies:

```bash
pip3 install python-docx mcp
```

## Usage

### Using as an MCP Service in Cursor

1. Open Cursor and go to Settings
2. Find the `Features > MCP Servers` section
3. Click `Add new MCP server`
4. Fill in the following information:
   - Name: MCP_DOCX
   - Type: Command
   - Command: `python3 /path/to/MCP_dox/server.py` (replace with the actual path to your `server.py`)
5. Click `Add` to add the service

After adding, you can use natural language to operate Word documents in Cursor's AI assistant, for example:

- "Create a new Word document and save it to the desktop"
- "Add a level 3 heading"
- "Insert a 3x4 table and fill it with data"
- "Set the second paragraph to bold and center-aligned"

## Supported Operations

The service supports the following operations:

- **Document Management**: `create_document`, `open_document`, `save_document`
- **Content Addition**: `add_paragraph`, `add_heading`, `add_table`, `add_picture`
- **Content Editing**: `edit_paragraph`, `delete_paragraph`, `delete_text`
- **Table Operations**: `add_table_row`, `delete_table_row`, `edit_table_cell`, `merge_table_cells`, `split_table`
- **Layout Control**: `add_page_break`, `set_page_margins`
- **Query Functions**: `get_document_info`, `get_paragraphs`, `get_tables`, `search_text`
- **File Operations**: `create_document`, `open_document`, `save_document`, `save_as_document`, `create_document_copy`
- **Section Editing**: `replace_section`, `edit_section_by_keyword`
- **Other Functions**: `find_and_replace`, `search_and_replace` (with preview functionality)

## How It Works

1. The service uses the Python-docx library to process Word documents
2. It implements the MCP protocol through the FastMCP library to communicate with AI assistants
3. It processes requests and returns formatted responses
4. It supports complete error handling and status reporting

## Typography Capabilities

The service has good typography understanding capabilities:

- **Text Hierarchy**: Support for heading levels (1-9) and paragraph organization
- **Page Layout**: Support for page margin settings
- **Visual Elements**: Support for font styles (bold, italic, underline, color) and alignment
- **Table Layout**: Support for creating tables, merging cells, splitting tables, and setting table formats
- **Pagination Control**: Support for adding page breaks

## Development Notes

- `server.py` - Core implementation of the MCP service using the FastMCP library

## Troubleshooting

If you encounter problems in Cursor, try the following steps:

1. Ensure Python 3.10+ is correctly installed
2. Ensure the python-docx and mcp libraries are correctly installed
3. Check if the server path is correct
4. Restart the Cursor application

## Notes

- Ensure the python-docx and mcp libraries are correctly installed
- Ensure Chinese characters in paths can be correctly processed
- Using absolute paths can avoid path parsing issues

## License

MIT License
