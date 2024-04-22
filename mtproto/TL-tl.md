# ﻿TL schema for serialization of TL schemas

If necessary, a TL schema can be serialized in binary form. Here, this serialization format is defined by a TL schema (usually stored in the file tl.tl). This can be useful, for example, to make it possible to write a parser one time for converting a TL schema from text form (stored in the file  something.tl) to binary form (stored in the file something.tlo). All other programs (for example, auto-generators of TL-(de)serializers for various programming languages) only need to know how to read .tlo files, which only requires generating an automatic deserializer according to the schema presented below.

First, a fragment of the file common.tl with certain required built-in types:

Next, properly, comes tl.tl itself. Note that the declaration for a fairly complex data type required only twenty lines in TL. This demonstrates the expressiveness and compactness of the TL language.

Schema serialization (version 2) always begins with the index number of the tls.schema_v2 constructor for tls.Schema.
Because the CRC32 of the string

is 0x3a2f9be2, this constant is in fact the magic number for tlo files in the current version's format.
If the format is extended in the future (for example, if TL's additional features are supported), then a tls.schema_v3 constructor with a different number will appear.

If one adds declarations for the used built-in types (like int ? = Int;) from the file common.tl before tl.tl and serialize the resulting schema, the following binary data is obtained (tl.tlo):

