[<< Main](v2Main.md) :: [<< Selectors](v2Selectors.md)

## Rectangular Image Selector ##

This Selector has been introduced in order to have a simple mechanism for detecting a portion of an image. For more complex shapes you should take a look at the [SvgSelector Image/Video Selector](SvgSelector.md).

| **Parameter** | **Description** | **Constraints** |
|:--------------|:----------------|:----------------|
| ao:start      | The position of the first character of the exact match counting from the beginning of the document | Mandatory       |
| ao:end        | The position of the last character of the exact match counting from the beginning of the document  |  Mandatory      |
| ao:unit       | The unit of the start and end points. Usually pixels or percentage. | Mandatory (default: percentage) |