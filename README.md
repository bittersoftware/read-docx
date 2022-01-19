# read-docx
Open docx files using the python-docx library and fetches pargraphs and table texts using filters and parameters

## Usage
`pip install -r requirements.txt`

`python3 read_doc.py`

### Filters: By text format
Filter by text format using the FormatFilter dataclass
Returns only paragraphs that matches all the filters
```
class FormatFilter:
    bold: List or str = field(default_factory = lambda: ["None", "True"])
    italic: List or str = field(default_factory = lambda: ["None", "True"])
    text: str or None = None
    font_rgb_color: List or str = "None"
    style_name: List or str = field(default_factory = lambda: ["Normal", "No Spacing"])
```

### Grab chunk of paragraphs
Using `get_segment()` method to pass start and end text of the target block of text.
Parameters allow exact match of if paragraph contains target text

### Read tables
Using `get_table_content()` returns the content of the table as a list of dictionaries. Each item of the list is a row of the table.
Pass table index as a parameter to select the target table
