# Correcting the approach to handle paragraphs, tables, and images

# Initialize markdown content
markdown_content = ""

# Extract and convert paragraphs to markdown
for paragraph in doc.paragraphs:
    markdown_content += paragraph.text + "\n\n"

# Extract and convert tables to markdown
for table in doc.tables:
    for row in table.rows:
        row_content = "| "
        for cell in row.cells:
            row_content += cell.text + " | "
        markdown_content += row_content + "\n"

# Extract images (will save them and provide links)
image_files = []
for idx, shape in enumerate(doc.inline_shapes):
    image_path = f"/mnt/data/extracted_image_{idx}.png"
    shape.image.save(image_path)
    image_files.append(image_path)

# Return the first few lines of markdown for review
markdown_content[:500], image_files  # Displaying only the first few lines and the list of extracted images
