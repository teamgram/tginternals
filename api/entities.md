# Styled text with message entities

Telegram supports styled text using message entities.

A client that wants to send styled messages would simply have to integrate a Markdown/HTML parser, and generate an array of message entities by iterating through the parsed tags.

Nested entities are supported.

### Entity length

Special care must be taken to consider the length of strings when generating message entities as the number of UTF-16 code units, even if the message itself must be encoded using UTF-8.

Example implementations: tdlib, MadelineProto.

#### Unicode codepoints and encoding

A Unicode code point is a number ranging from 0x0 to 0x10FFFF, usually represented using U+0000 to U+10FFFF syntax.
Unicode defines a codespace of 1,112,064 assignable code points within the U+0000 to U+10FFFF range.
Each of the assignable codepoints, once assigned by the Unicode consortium, maps to a specific character, emoji or control symbol.

The Unicode codespace is further subdivided into 17 planes:

- Plane 1: U+0000 to U+FFFF: Basic Multilingual Plane (BMP)

- Planes 2-17: U+00000 to U+10FFFF: Multiple supplementary planes as specified by the Unicode standard

Since storing a 21-bit number for each letter would result in a waste of space, the Unicode consortium defines multiple encodings that allow storing a code point into a smaller code unit:

#### UTF-8

UTF-8 » is a Unicode encoding that allows storing a 21-bit Unicode code point into code units as small as 8 bits.
UTF-8 is used by the MTProto and Bot API when transmitting and receiving fields of type string.

#### UTF-16

UTF-16 » is a Unicode encoding that allows storing a 21-bit Unicode code point into one or two 16-bit code units.

UTF-16 is used when computing the length and offsets of entities in the MTProto and bot APIs, by counting the number of UTF-16 code units (not code points).

#### Computing entity length

- Code points in the BMP (U+0000 to U+FFFF) count as 1, because they are encoded into a single UTF-16 code unit

- Code points in all other planes count as 2, because they are encoded into two UTF-16 code units (also called surrogate pairs)

A simple, but not very efficient way of computing the entity length is converting the text to UTF-16, and then taking the byte length divided by 2 (=number of UTF-16 code units).

However, since UTF-8 encodes codepoints in non-BMP planes as a 32-bit code unit starting with 0b11110, a more efficient way to compute the entity length without converting the message to UTF-16 is the following:

- If the byte marks the beginning of a 32-bit UTF-8 code unit (all bytes starting with 0b11110) increment the count by 2, otherwise

- If the byte marks the beginning of a UTF-8 code unit (all bytes not starting with 0b10) increment the count by 1.

Example:

Note: the length of an entity must not include the length of trailing newlines or whitespaces, rtrim entities before computing their length: however, the next offset must include the length of newlines or whitespaces that precede it.

Example implementations: tdlib, MadelineProto.

### Allowed entities

For example the following HTML/Markdown aliases for message entities can be used:

- messageEntityBold => <b>bold</b>, <strong>bold</strong>, **bold**

- messageEntityItalic => <i>italic</i>, <em>italic</em> *italic*

- messageEntityCode => <code>code</code>, `code`

- messageEntityStrike => <s>strike</s>, <strike>strike</strike>, <del>strike</del>, ~~strike~~

- messageEntityUnderline => <u>underline</u>

- messageEntityPre => <pre language="c++">code</pre>,

The following entities can also be used to mention users:

- inputMessageEntityMentionName => Mention a user

- messageEntityMention => @botfather (this mention is generated automatically server-side for @usernames in messages)

Also, messageEntityCustomEmoji entities are used for custom emojis ».

A number of other entities are also available, see the type page for the full list ».

