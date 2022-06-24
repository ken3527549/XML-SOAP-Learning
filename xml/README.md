# XML Format

## What is

- Extensible Markup Language (XML)
- simple text-based format for representing structured information: documents, data, configuration, books, transactions, invoices, and much more
- XML was designed to carry data - with focus on what data is
- HTML was designed to display data - with focus on how data looks
- XML tags are not predefined like HTML tags are

## Used For

- between programs
- between people
- between computers and people
- both locally and across networks

### Example

```xml
<part number="1976">
  <name>Windscreen Wiper</name>
  <description>The Windscreen wiper
    automatically removes rain
    from your windscreen, if it
    should happen to splash there.
    It has a rubber <ref part="1977">blade</ref>
    which can be ordered separately
    if you need to replace it.
  </description>
</part>
```

`XML tools will not process files that contain errors`, but instead will give you error messages so that you fix them

## The main differences from HTML are

- Empty elements can be closed as normal, `<happiness></happiness>` or you can use a special short-form, `<happiness />` instead.
- attribute values must always be quoted: `<happiness type="joy" />`
- no built-in names (although names starting with `xml` have special meanings)
- five built-in character entities: `&lt;, &gt;, &amp;, &quot; and &apos;` for <, >, &, " and ' respectively. You can define your own entities in a Document Type Definition, or you can use any Unicode character (see next item).

## Syntax

### XML Documents Must Have a Root Element

```xml
<root>
  <child>
    <subchild>.....</subchild>
  </child>
</root>
```

### The XML Prolog

Character encoding can be studied in our [Character Set Tutorial](https://www.w3schools.com/charsets/default.asp).

```xml
<?xml version="1.0" encoding="UTF-8"?>
```

### All XML Elements Must Have a Closing Tag

**Note**: The XML prolog does not have a closing tag! This is not an error. The prolog is not a part of the XML document.

### XML Tags are Case Sensitive

### XML Elements Must be Properly Nested

Wrong:

```xml
<b><i>This text is bold and italic</b></i>
```

Correct:

```xml
<b><i>This text is bold and italic</i></b>
```

### XML Attribute Values Must Always be Quoted

```xml
<note date="12/11/2007">
  <to>Tove</to>
  <from>Jani</from>
</note>
```

### Entity References

To avoid this error, replace the "<" character with an entity reference:

```xml
<message>salary &lt; 1000</message>
```

There are 5 pre-defined entity references in XML:

```charactor
&lt; < less than
&gt; > greater than
&amp; & ampersand
&apos; ' apostrophe
&quot; " quotation mark
```

### Comments in XML

The syntax for writing comments in XML is similar to that of HTML:

```xml
<!-- This is a comment -->
```

Two dashes in the middle of a comment are not allowed:

```xml
<!-- This is an invalid -- comment -->
```

### White-space is Preserved in XML

XML does not truncate multiple white-spaces (HTML truncates multiple white-spaces to one single white-space):

```charactor
XML:  Hello           Tove
HTML: Hello Tove
```

### XML Stores New Line as LF

- Windows applications store a new line as: carriage return and line feed (CR+LF).
- Unix and Mac OSX use LF.
- Old Mac systems use CR.
- XML stores a new line as LF.

## XML Naming Rules

- Element names are case-sensitive
- Element names must start with a letter or underscore
- Element names cannot start with the letters xml (or XML, or Xml, etc)
- Element names can contain letters, digits, hyphens, underscores, and periods
- Element names cannot contain spaces

Any name can be used, no words are reserved (except xml).

### Best Naming Practices

- Create descriptive names, like this: <person>, <firstname>, <lastname>.
- Create short and simple names, like this: <book_title> not like this: <the_title_of_the_book>.
- Avoid "-". If you name something "first-name", some software may think you want to subtract "name" from "first".
- Avoid ".". If you name something "first.name", some software may think that "name" is a property of the object "first".
- Avoid ":". Colons are reserved for namespaces (more later).
- Non-English letters like éòá are perfectly legal in XML, but watch out for problems if your software doesn't support them!

### Naming Conventions

[LINK](https://www.w3schools.com/xml/xml_elements.asp)

### XML Elements vs. Attributes

[LINK](https://www.w3schools.com/xml/xml_attributes.asp)

### Avoid XML Attributes?
- attributes cannot contain multiple values (elements can)
- attributes cannot contain tree structures (elements can)
- attributes are not easily expandable (for future changes)

```charactor
<note day="10" month="01" year="2008"
to="Tove" from="Jani" heading="Reminder"
body="Don't forget me this weekend!">
</note>
```

### XML Attributes for Metadata

```charactor
<messages>
  <note id="501">
    <to>Tove</to>
    <from>Jani</from>
    <heading>Reminder</heading>
    <body>Don't forget me this weekend!</body>
  </note>
  <note id="502">
    <to>Jani</to>
    <from>Tove</from>
    <heading>Re: Reminder</heading>
    <body>I will not</body>
  </note>
</messages>
```

The id attributes above are for identifying the different notes. It is not a part of the note itself.

What I'm trying to say here is that metadata (data about data) should be stored as attributes, and the data itself should be stored as elements.

### XML Namespaces

[LINK](https://www.w3schools.com/xml/xml_namespaces.asp)

## References

- [W3C](https://www.w3schools.com/xml/default.asp)
