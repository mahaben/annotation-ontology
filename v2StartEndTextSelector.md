[<< Main](v2Main.md) :: [<< Selectors](v2Selectors.md)

### Start End Text Selector ###

Identifies a fragment of text specifying the position of the start and end characters of the exact match - counting from the beginning of the document.

| **Parameter** | **Description** | **Constraints** |
|:--------------|:----------------|:----------------|
| ao:exact      | The exact match. | Optional        |
| ao:start      | The position of the first character of the exact match counting from the beginning of the document | Mandatory       |
| ao:end        | The position of the last character of the exact match counting from the beginning of the document  |  Mandatory      |
| cnt:characterEncoding | The encoding of the exact match (when defined) | Optional (default utf-8) |
| dc:format     | The format of the exact match (when defined) | Optional (default text/plain) |