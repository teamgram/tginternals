# ﻿TL schema for serialization of TL schemas
First, a fragment of the file common.tl with certain required built-in types:
Next, properly, comes tl.tl itself. Note that the declaration for a fairly complex data type required only twenty lines in TL. This demonstrates the expressiveness and compactness of the TL language.
Schema serialization (version 2) always begins with the index number of the tls.schema_v2 constructor for tls.Schema.
Because the CRC32 of the string
is 0x3a2f9be2, this constant is in fact the magic number for tlo files in the current version's format.
If the format is extended in the future (for example, if TL's additional features are supported), then a tls.schema_v3 constructor with a different number will appear.
If one adds declarations for the used built-in types (like int ? = Int;) from the file common.tl before tl.tl and serialize the resulting schema, the following binary data is obtained (tl.tlo):
