[<< Main](v2Main.md) :: [<< Selectors](v2Selectors.md)

### Offset Range Text Selector ###

Identifies a chunk of text specifying the offset from the beginning of the document and the range - number of characters from the offset.

| **Parameter** | **Description** | **Constraints** |
|:--------------|:----------------|:----------------|
| ao:exact      | The exact match. | Optional        |
| ao:offset     | The number of characters from the beginning of the document to the text span representing the exact match | Mandatory       |
| ao:range      | The number of characters of the text span, in other words the number of characters of the exact match (when defined) |  Mandatory      |
| cnt:characterEncoding | The encoding of the exact match (when defined) | Optional (default utf-8) |
| dc:format     | The format of the exact match (when defined) | Optional (default text/plain) |

**How to make this selector more robust**