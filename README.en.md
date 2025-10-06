# 🔠 Chuleta de SGML (Standard Generalized Markup Language)
SGML is a standard for defining generalized markup languages for documents. HTML and XML are applications of SGML.
---
<br>

## 📝 Basic Structure of an SGML Document
```JavaScript
<!DOCTYPE name_doc [
  <!ELEMENT element (content)>
  <!ATTLIST element
    attribute type value_for_defect>
]>
<name_doc>
  <element attribute="valor">content</element>
</name_doc>
```
<br>

## 🔍 SGML Declarations
| DECLARATION | DESCRIPTION | EXAMPLE |
| --- | --- | --- |
| DOCTYPE | Defines the document type | `<!DOCTYPE html>` |
| ELEMENT | Defines an element | `<!ELEMENT p (#PCDATA)>` |
| ATTLIST | Defines attributes for an element | `<!ATTLIST img src CDATA #REQUIRED>` |
| ENTITY | Defines an entity | `<!ENTITY copy "&#169;">` |
| NOTATION | Defines a notation | `<!NOTATION gif SYSTEM "image/gif">` |

<br>

## 🧩 Content Types for Elements
| TYPE | DESCRIPTION | EXAMPLE |
| --- | --- | --- |
| EMPTY | The element has no content | `<!ELEMENT br EMPTY>` |
| ANY | The element can have any content | `<!ELEMENT div ANY>` |
| #PCDATA | The element can contain text | `<!ELEMENT p (#PCDATA)>` |
| Sequence | Elements must appear in the specified order | `<!ELEMENT article (title,para+)>` |
| Option | Optional elements | `<!ELEMENT person (name,(phone\|email))>` |

<br>

## ⚙️ Occurrence Indicators
| INDICATOR | MEANING | EXAMPLE |
| --- | --- | --- |
| ? | Zero or one occurrence | `<!ELEMENT título (subtítulo?)>` |
| * | Zero or more occurrences | `<!ELEMENT libro (capítulo*)>` |
| + | One or more occurrences | `<!ELEMENT lista (item+)>` |
| No indicator | Exactly one occurrence | `<!ELEMENT persona (nombre)>` |

<br>

## 🏷️ Attribute Types
| TYPE | DESCRIPTION | EXAMPLE |
| --- | --- | --- |
| CDATA | Character data | `<!ATTLIST img src CDATA #REQUIRED>` |
| ID | Unique identifier | `<!ATTLIST div id ID #IMPLIED>` |
| IDREF | Reference to an ID | `<!ATTLIST a href IDREF #IMPLIED>` |
| IDREFS | References to multiple IDs | `<!ATTLIST form fields IDREFS #IMPLIED>` |
| NMTOKEN | Name token | `<!ATTLIST input type NMTOKEN #REQUIRED>` |
| NMTOKENS | Name tokens | `<!ATTLIST p class NMTOKENS #IMPLIED>` |
| Enumeration | List of possible values | `<!ATTLIST align type (left\|center\|right) "left">` |

<br>

## ⚓ Default Values for Attributes
| VALUE | MEANING | EXAMPLE |
| --- | --- | --- |
| #REQUIRED | Mandatory attribute | `<!ATTLIST img src CDATA #REQUIRED>` |
| #IMPLIED | Optional attribute | `<!ATTLIST p class CDATA #IMPLIED>` |
| #FIXED "value" | Fixed value | `<!ATTLIST meta charset CDATA #FIXED "UTF-8">` |
| "value" | Default value | `<!ATTLIST input type CDATA "text">` |

<br>

## 🔣 Entidades predefinidas
| ENTITY | CHARACTER | DESCRIPTION |
| --- | --- | --- |
| < | < | Less than |
| > | > | Greater than |
| & | & | Ampersand |
| " | " | Double quotes |
| ' | ' | Single quote (apostrophe) |

<br>

## 📦 Entity Types
| TYPE | DESCRIPTION | EXAMPLE |
| --- | --- | --- |
| General entity | Referenced in the document | `<!ENTITY copy "&#169;">` |
| Parameter entity | Used in the DTD | `<!ENTITY % attrs "id ID #IMPLIED class CDATA #IMPLIED">` |
| External entity | Reference to an external resource | `<!ENTITY footer SYSTEM "footer.xml">` |

<br>

## 🔀 Secciones condicionales en DTDs
```JavaScript
<!ENTITY % DEBUG "INCLUDE">

<![%DEBUG;[
  <!-- Code included in debud mode -->
  <!ELEMENT debug (#PCDATA)>
]]>

<!ENTITY % RELEASE "IGNORE">

<![%RELEASE;[
  <!-- Code ignored in debud mode -->
  <!ELEMENT release (#PCDATA)>
]]>
```

<br>

## 🔄 Key Differences Between SGML, HTML, and XML
| FEATURE | SGML | HTML | XML |
| --- | --- | --- | --- |
| Closing tags | Optional in some circumstances | Some optional (p, li, etc.) | Mandatory |
| Case sensitivity | Configurable | Not sensitive (case-insensitive) | Sensitive (case-sensitive) |
| Empty tags | Defined in DTD | Predefined (br, hr, img) | Special syntax with /> |
| Quotes in attributes | Optional in some circumstances | Optional | Mandatory |
| DTD | Mandatory | Optional (but typical) | Optional |

<br>

## 📚 Glossary
- **Attribute**: additional information associated with an element, typically represented as name-value pairs.
- **CDATA**: Character Data. Text that will be analyzed by the SGML processor (entities are not interpreted).
- **Conditional section**: part of a DTD that can be included or excluded based on conditions.
- **Declaration**: instructions that define aspects of the SGML language, such as elements, attributes, and entities.
- **DTD**: Document Type Definition. Defines the structure and valid elements in an SGML document.
- **Element**: basic unit of an SGML document, defined by opening and closing tags.
- **Empty element**: element that contains no content (for example, in HTML).
- **Entity**: abbreviation or reference that represents text or external content in SGML.
- **HTML**: HyperText Markup Language. Specific application of SGML used to create web pages.
- **Markup**: system of annotations inserted in the text to indicate how it should be processed or presented.
- **Notation**: mechanism to identify the format of external non-SGML data (such as images).
- **PCDATA**: Parsed Character Data. Text that will be analyzed by the SGML processor, interpreting entities.
- **SGML**: Standard Generalized Markup Language. International standard for defining structured markup languages.
- **SGML processor**: software that analyzes and processes SGML documents according to the rules defined in its DTD.
- **Validation**: process of verifying if a document complies with the rules defined in its DTD.
- **XML**: eXtensible Markup Language. Simplified subset of SGML designed to facilitate its implementation and use.