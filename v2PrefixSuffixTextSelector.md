[<< Main](v2Main.md) :: [<< Selectors](v2Selectors.md)

## Prefix Suffix Text Selector ##

The [PrefixSuffixTextSelector](v2PrefixSuffixTextSelector.md) allows to identify a region of text in a document by specifying the its **prefix** (a reasonable amount of characters before the match), the **exact match** and its **suffix** (a reasonable amount of characters after the match). This selector is particularly important when the annotated content is not immutable. Paragraphs can shift and the approach with offset and range can easily fail.

_**Note**: This selector assumes the content of the prefix, exact match and suffix to be plain text where the HTML has been removed._

| **Parameter** | **Description** | **Constraints** |
|:--------------|:----------------|:----------------|
| ao:exact      | The exact match. |  Mandatory      |
| ao:prefix     | A 'reasonable' amount of characters before the match. | Mandatory       |
| ao:suffix     | A 'reasonable' amount of characters after the match. | Mandatory       |
| cnt:characterEncoding | The encoding of the exact match, prefix and suffix | Optional (default utf-8) |
| dc:format     | The format (MIME type) of the exact match, prefix and suffix  | Optional (default text/plain) |

**How to deal with redundant content**

The Prefix Suffix Text Selector behaves well when the annotated document is not immutable. However, it requires additional work for redundant documents. In fact, if the same span of text prefix+exact+suffix is present multiple times, the detection might not be accurate (according to the implementation it might be that only the first occurrence of the text span is detected).

### Examples ###