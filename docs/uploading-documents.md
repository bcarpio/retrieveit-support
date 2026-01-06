# Uploading Documents to RetrieveIt.AI

This guide covers how to add documents to your workspaces for AI-powered search.

## Supported File Types

RetrieveIt.AI supports these document formats:

| Format | Extensions | Notes |
|--------|------------|-------|
| Markdown | `.md` | Excellent for structured docs |
| Plain Text | `.txt` | Simple text files |
| PDF | `.pdf` | Scanned PDFs may have limited text |
| Word | `.docx` | Microsoft Word documents |
| Excel | `.xlsx` | Spreadsheets (text content extracted) |
| PowerPoint | `.pptx` | Presentations |
| CSV | `.csv` | Comma-separated data |
| HTML | `.html`, `.htm` | Web pages |
| YAML/JSON | `.yaml`, `.yml`, `.json` | Config and data files |

## How to Upload

### Manual Upload
1. Go to **Dashboard** > **Workspaces**
2. Select the target workspace
3. Click **Upload Documents**
4. Drag and drop files or click to browse
5. Documents are processed and indexed automatically

### GitHub Integration
For teams using GitHub:
1. Connect your GitHub repository to a workspace
2. Documents sync automatically when you push
3. Great for documentation that lives in repos

## Best Practices

### Document Organization
- Use clear, descriptive file names
- Organize with folders when possible
- Keep related documents together

### Content Quality
- Ensure text is selectable (not scanned images)
- Use headings and structure in documents
- Remove duplicate content

### File Size
- Individual files should be under 50MB
- Very large files may take longer to process
- Consider splitting massive documents

## After Upload

Once uploaded, documents are:
1. **Parsed** - Text extracted from the file
2. **Chunked** - Split into searchable segments
3. **Embedded** - Converted to vectors for semantic search
4. **Indexed** - Made available for queries

This process typically takes 1-2 minutes per document.

## Troubleshooting

### Document Not Searchable
- Wait a few minutes for processing to complete
- Check if the file format is supported
- Ensure the document contains actual text (not just images)

### Poor Search Results
- Check if document content is what you expected
- Try more specific queries
- Ensure the right workspace is selected

### Upload Fails
- Check file size (under 50MB)
- Verify file format is supported
- Try refreshing and uploading again
