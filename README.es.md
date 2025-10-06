# 🔠 Chuleta de SGML (Standard Generalized Markup Language)
SGML es un estándar para definir lenguajes de marcado generalizados para documentos. HTML y XML son aplicaciones de SGML.

---
<br>

## 📝 Estructura básica de un documento SGML
```JavaScript
<!DOCTYPE nombre_doc [
  <!ELEMENT elemento (contenido)>
  <!ATTLIST elemento
    atributo tipo valor_por_defecto>
]>
<nombre_doc>
  <elemento atributo="valor">contenido</elemento>
</nombre_doc>
```
<br>

## 🔍 Declaraciones SGML
| DECLARACIÓN | DESCRIPCIÓN | EJEMPLO |
| --- | --- | --- |
| DOCTYPE | Define el tipo de documento | `<!DOCTYPE html>` |
| ELEMENT | Define un elemento | `<!ELEMENT p (#PCDATA)>` |
| ATTLIST | Define atributos para un elemento | `<!ATTLIST img src CDATA #REQUIRED>` |
| ENTITY | Define una entidad | `<!ENTITY copy "&#169;">` |
| NOTATION | Define una notación | `<!NOTATION gif SYSTEM "image/gif">` |

<br>

## 🧩 Tipos de contenido para elementos
| TIPO | DESCRIPCIÓN | EJEMPLO |
| --- | --- | --- |
| EMPTY | El elemento no tiene contenido | `<!ELEMENT br EMPTY>` |
| ANY | El elemento puede tener cualquier contenido | `<!ELEMENT div ANY>` |
| #PCDATA | El elemento puede contener texto | `<!ELEMENT p (#PCDATA)>` |
| Secuencia | Los elementos deben aparecer en el orden especificado | `<!ELEMENT article (title,para+)>` |
| Opción | Elementos opcionales | `<!ELEMENT person (name,(phone\|email))>` |

<br>

## ⚙️ Indicadores de ocurrencia
| INDICADOR | SIGNIFICADO | EJEMPLO |
| --- | --- | --- |
| ? | Cero o una ocurrencia | `<!ELEMENT título (subtítulo?)>` |
| * | Cero o más ocurrencias | `<!ELEMENT libro (capítulo*)>` |
| + | Una o más ocurrencias | `<!ELEMENT lista (item+)>` |
| Sin indicador | Exactamente una ocurrencia | `<!ELEMENT persona (nombre)>` |

<br>

## 🏷️ Tipos de atributos
| TIPO | DESCRIPCIÓN | EJEMPLO |
| --- | --- | --- |
| CDATA | Datos de caracteres | `<!ATTLIST img src CDATA #REQUIRED>` |
| ID | Identificador único | `<!ATTLIST div id ID #IMPLIED>` |
| IDREF | Referencia a un ID | `<!ATTLIST a href IDREF #IMPLIED>` |
| IDREFS | Referencias a múltiples IDs | `<!ATTLIST form fields IDREFS #IMPLIED>` |
| NMTOKEN | Token de nombre | `<!ATTLIST input type NMTOKEN #REQUIRED>` |
| NMTOKENS | Tokens de nombres | `<!ATTLIST p class NMTOKENS #IMPLIED>` |
| Enumeración | Lista de valores posibles | `<!ATTLIST align type (left\|center\|right) "left">` |

<br>

## ⚓ Valores por defecto para atributos
| VALOR | SIGNIFICADO | EJEMPLO |
| --- | --- | --- |
| #REQUIRED | Atributo obligatorio | `<!ATTLIST img src CDATA #REQUIRED>` |
| #IMPLIED | Atributo opcional | `<!ATTLIST p class CDATA #IMPLIED>` |
| #FIXED "valor" | Valor fijo | `<!ATTLIST meta charset CDATA #FIXED "UTF-8">` |
| "valor" | Valor por defecto | `<!ATTLIST input type CDATA "text">` |

<br>

## 🔣 Entidades predefinidas
| ENTIDAD | CARÁCTER | DESCRIPCIÓN |
| --- | --- | --- |
| < | < | Menor que |
| > | > | Mayor que |
| & | & | Ampersand |
| " | " | Comillas dobles |
| ' | ' | Comilla simple (apóstrofo) |

<br>

## 📦 Tipos de entidades
| TIPO | DESCRIPCIÓN | EJEMPLO |
| --- | --- | --- |
| Entidad general | Referenciada en el documento | `<!ENTITY copy "&#169;">` |
| Entidad de parámetro | Usada en la DTD | `<!ENTITY % attrs "id ID #IMPLIED class CDATA #IMPLIED">` |
| Entidad externa | Referencia a un recurso externo | `<!ENTITY footer SYSTEM "footer.xml">` |

<br>

## 🔀 Secciones condicionales en DTDs
```JavaScript
<!ENTITY % DEBUG "INCLUDE">

<![%DEBUG;[
  <!-- Código incluido en modo debug -->
  <!ELEMENT debug (#PCDATA)>
]]>

<!ENTITY % RELEASE "IGNORE">

<![%RELEASE;[
  <!-- Código ignorado en modo debug -->
  <!ELEMENT release (#PCDATA)>
]]>
```

<br>

## 🔄 Diferencias clave entre SGML, HTML y XML
| CARACTERÍSTICAS | SGML | HTML | XML |
| --- | --- | --- | --- |
| Etiquetas de cierre | Opcionales en algunas circunstancias | Algunas opcionales (p, li, etc.) | Obligatorias |
| Case sensitivity | Configurable | No sensible (case-insensitive) | Sensible (case-sensitive) |
| Etiquetas vacías | Definidas en DTD | Predefinidas (br, hr, img) | Sintaxis especial con /> |
| Comillas en atributos | Opcionales en algunas circunstancias | Opcionales | Obligatorias |
| DTD | Obligatorio | Opcional (pero típico) | Opcional |

<br>

## 📚 Glosario
- **Atributo**: información adicional asociada a un elemento, normalmente representada como pares nombre-valor.
- **CDATA**: Character Data. Texto que no será analizado por el procesador SGML, interpretando entidades.
- **Declaración**: instrucciones que definen aspectos del lenguaje SGML, como elementos, atributos y entidades.
- **DTD**: Document Type Definition. Define la estructura y los elementos válidos en un documento SGML.
- **Elemento**: unidad básica de un documento SGML, definida mediante etiquetas de apertura y cierre.
- **Elemento vacío**: elemento que no contiene ningún contenido (por ejemplo, en HTML).
- **Entidad**: abreviatura o referencia que representa texto o contenido externo en SGML.
- **HTML**: HyperText Markup Language. Aplicación específica de SGML utilizada para crear páginas web.
- **Marcado**: sistema de anotaciones insertadas en el texto para indicar cómo debe ser procesado o presentado.
- **Notación**: mecanismo para identificar el formato de datos externos no SGML (como imágenes).
- **PCDATA**: Parsed Character Data. Texto que será analizado por el procesador SGML, interpretando entidades.
- **Procesador SGML**: software que analiza y procesa documentos SGML según las reglas definidas en su DTD.
- **Sección condicional**: parte de una DTD que puede incluirse o excluirse basándose en condiciones.
- **SGML**: Standard Generalized Markup Language. Estándar internacional para la definición de lenguajes de marcado estructurado.
- **Validación**: proceso de verificar si un documento cumple con las reglas definidas en su DTD.
- **XML**: eXtensible Markup Language. Subconjunto simplificado de SGML diseñado para facilitar su implementación y uso.