---
title: Attributes (F#)
description: Attributes (F#)
keywords: visual f#, f#, functional programming
author: dend
manager: danielfe
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: visual-studio-dev14
ms.assetid: 95c001e6-3708-4d04-a850-d855f78eb51e 
---

# Attributes (F#)

Attributes enable metadata to be applied to a programming construct.

## Syntax

```fsharp
[<target:attribute-name(arguments)>]
```

## Remarks

In the previous syntax, the *target* is optional and, if present, specifies the kind of program entity that the attribute applies to. Valid values for *target* are shown in the table that appears later in this document.

The *attribute-name* refers to the name (possibly qualified with namespaces) of a valid attribute type, with or without the suffix **Attribute** that is usually used in attribute type names. For example, the type **ObsoleteAttribute** can be shortened to just **Obsolete** in this context.

The *arguments* are the arguments to the constructor for the attribute type. If an attribute has a default constructor, the argument list and parentheses can be omitted. Attributes support both positional arguments and named arguments. *Positional arguments* are arguments that are used in the order in which they appear. Named arguments can be used if the attribute has public properties. You can set these by using the following syntax in the argument list.

*property-name* = *property-value*

Such property initializations can be in any order, but they must follow any positional arguments. Following is an example of an attribute that uses positional arguments and property initializations.

[!code-fsharp[Main](snippets/fslangref2/snippet6202.fs)]

In this example, the attribute is **DllImportAttribute**, here used in shortened form. The first argument is a positional parameter and the second is a property.

Attributes are a .NET programming construct that enables an object known as an *attribute* to be associated with a type or other program element. The program element to which an attribute is applied is known as the *attribute target*. The attribute usually contains metadata about its target. In this context, metadata could be any data about the type other than its fields and members.

Attributes in F# can be applied to the following programming constructs: functions, methods, assemblies, modules, types (classes, records, structures, interfaces, delegates, enumerations, unions, and so on), constructors, properties, fields, parameters, type parameters, and return values. Attributes are not allowed on **let** bindings inside classes, expressions, or workflow expressions.

Typically, the attribute declaration appears directly before the declaration of the attribute target. Multiple attribute declarations can be used together, as follows.

[!code-fsharp[Main](snippets/fslangref2/snippet6603.fs)]

You can query attributes at run time by using .NET reflection.

You can declare multiple attributes individually, as in the previous code example, or you can declare them in one set of brackets if you use a semicolon to separate the individual attributes and constructors, as shown here.

[!code-fsharp[Main](snippets/fslangref2/snippet6604.fs)]

Typically encountered attributes include the **Obsolete** attribute, attributes for security considerations, attributes for COM support, attributes that relate to ownership of code, and attributes indicating whether a type can be serialized. The following example demonstrates the use of the **Obsolete** attribute.

[!code-fsharp[Main](snippets/fslangref2/snippet6605.fs)]

For the attribute targets **assembly** and **module**, you apply the attributes to a top-level **do** binding in your assembly. You can include the word **assembly** or **module** in the attribute declaration, as follows.

[!code-fsharp[Main](snippets/fslangref2/snippet6606.fs)]

If you omit the attribute target for an attribute applied to a **do** binding, the F# compiler attempts to determine the attribute target that makes sense for that attribute. Many attribute classes have an attribute of type **System.AttributeUsageAttribute** that includes information about the possible targets supported for that attribute. If the **System.AttributeUsageAttribute** indicates that the attribute supports functions as targets, the attribute is taken to apply to the main entry point of the program. If the **System.AttributeUsageAttribute** indicates that the attribute supports assemblies as targets, the compiler takes the attribute to apply to the assembly. Most attributes do not apply to both functions and assemblies, but in cases where they do, the attribute is taken to apply to the program's main function. If the attribute target is specified explicitly, the attribute is applied to the specified target.

Although you do not usually need to specify the attribute target explicitly, valid values for *target* in an attribute are shown in the following table, along with examples of usage.

|Attribute target|Example|
|----------------|-------|
|assembly|**[&lt;assembly: AssemblyVersionAttribute("1.0.0.0")&gt;]**|
|return|**let function1 x : [&lt;return: Obsolete&gt;] int = x + 1**|
|field|**[&lt;field: DefaultValue&gt;] val mutable x: int**|
|property|**[&lt;property: Obsolete&gt;] this.MyProperty = x**|
|param|**member this.MyMethod([&lt;param: Out&gt;] x : ref&lt;int&gt;) = x := 10**|
|type|**[&lt;type: StructLayout(Sequential)&gt;]**<br />**type MyStruct =**<br />**struct**<br />**x : byte**<br />**y : int**<br />**end**|

## See Also

[F&#35; Language Reference](FSharp-Language-Reference.md)

