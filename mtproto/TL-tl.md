# ﻿TL schema for serialization of TL schemas

If necessary, a TL schema can be serialized in binary form. Here, this serialization format is defined by a TL schema (usually stored in the file tl.tl). This can be useful, for example, to make it possible to write a parser one time for converting a TL schema from text form (stored in the file  something.tl) to binary form (stored in the file something.tlo). All other programs (for example, auto-generators of TL-(de)serializers for various programming languages) only need to know how to read .tlo files, which only requires generating an automatic deserializer according to the schema presented below.

First, a fragment of the file common.tl with certain required built-in types:

```
/////
//
// Common Types (source file common.tl, only necessary definitions included)
//
/////

// Built-in types
int ? = Int;
long ? = Long;
double ? = Double;
string ? = String;

// Boolean emulation
boolFalse = Bool;
boolTrue = Bool;

// Vector
vector {t:Type} # [t] = Vector t;
tuple {t:Type} {n:#} [t] = Tuple t n;
vectorTotal {t:Type} total_count:int vector:%(Vector t) = VectorTotal t;

Empty False;
true = True;
```

Next, properly, comes tl.tl itself. Note that the declaration for a fairly complex data type required only twenty lines in TL. This demonstrates the expressiveness and compactness of the TL language.

```
/////
//
// Serialized binary TL-schema in TL format, source file tl.tl
//
/////
tls.schema_v2 version:int date:int types_num:# types:types_num*[tls.Type] 

    constructor_num:# constructors:constructor_num*[tls.Combinator] 
    functions_num:# functions:functions_num*[tls.Combinator] = tls.Schema;
tls.type name:int id:string constructors_num:int flags:int arity:int params_type:long = tls.Type;

tls.combinator name:int id:string type_name:int left:tls.CombinatorLeft right:tls.CombinatorRight = tls.Combinator;
tls.combinatorLeftBuiltin = tls.CombinatorLeft;
tls.combinatorLeft args_num:# args:args_num*[tls.Arg] = tls.CombinatorLeft;
tls.combinatorRight value:tls.TypeExpr = tls.CombinatorRight;

tls.arg id:string flags:# var_num:flags.1?int exist_var_num:flags.2?int exist_var_bit:flags.2?int type:tls.TypeExpr = tls.Arg;

tls.exprType _:tls.TypeExpr = tls.Expr;

tls.exprNat _:tls.NatExpr = tls.Expr;
tls.natConst value:int = tls.NatExpr;

tls.natVar dif:int var_num:int = tls.NatExpr;
tls.typeVar var_num:int flags:int = tls.TypeExpr;

tls.array multiplicity:tls.NatExpr args_num:# args:args_num*[tls.Arg] = tls.TypeExpr;
tls.typeExpr name:int flags:int children_num:# children:children_num*[tls.Expr] = tls.TypeExpr;
```

Schema serialization (version 2) always begins with the index number of the tls.schema_v2 constructor for tls.Schema.
Because the CRC32 of the string

```
tls.schema_v2 version:int date:int types_num:# types:types_num*[ tls.Type ] constructor_num:# constructors:constructor_num*[ tls.Combinator ] functions_num:# functions:functions_num*[ tls.Combinator ] = tls.Schema
```

is 0x3a2f9be2, this constant is in fact the magic number for tlo files in the current version's format.
If the format is extended in the future (for example, if TL's additional features are supported), then a tls.schema_v3 constructor with a different number will appear.

If one adds declarations for the used built-in types (like int ? = Int;) from the file common.tl before tl.tl and serialize the resulting schema, the following binary data is obtained (tl.tlo):

