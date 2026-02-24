# nanhu-print-java-skills

A collection of Claude skills for the [nanhu-print-java](https://github.com/hongjinqiu/nanhu-print-java) framework.

## About nanhu-print-java

nanhu-print-java is an XML-to-PDF generation framework for Java. Users write an XML template, prepare JSON business data, then call the `NanhuprintInterpreter` API to produce a PDF. The framework is built on top of [OpenPDF](https://github.com/LibrePDF/OpenPDF).

### Key Features

- **Fixed headers and footers** — fixed title/header on every page, fixed summary/signature area at the bottom of the last page
- **Page numbers** — display current/total page numbers at any position on each page
- **Template printing (套打)** — use an image as background for forms like shipping labels
- **Watermarks** — text or image watermarks with configurable opacity, rotation, and position
- **Alternating row backgrounds** — alternate row colors in long tables via dynamic tags
- **Table pagination border control** — fine-grained border styles for first/last rows per page or per tbody
- **Dynamic tags** — `if`, `forEach`, `set`, `macro`, `macroRef` for complex display logic
- **Auto-shrink text** — scale font down to fit fixed-width cells (`scaleToFitContentByPdf`)
- **Dynamic cell width** — cell width expands to fit content (`calcWidth`)
- **Number formatting** — built-in `format` attribute for quantity, unit price, and amount fields
- **JS expressions** — all dynamic values and conditions use JavaScript syntax

### Deployment

**Embedded** — add as a Maven dependency:

```xml
<dependency>
    <groupId>io.github.hongjinqiu</groupId>
    <artifactId>nanhu-print-java</artifactId>
    <version>1.0.6</version>
</dependency>
```

**Microservice** — wrap as a Spring Boot service and expose a web endpoint. A ready-made demo is available via Docker:

```
docker pull hjq20021984/nanhu-print-java-demo:1.0.6
docker run -d -p 8891:8891 --name my-nanhu-print-java-demo hjq20021984/nanhu-print-java-demo:1.0.6
```

Visit `http://localhost:8891` after starting.

---

## Skills

### claude/nanhu-pdf

Helps Claude generate PDF files using the nanhu-print-java framework. Covers:

- Writing XML templates
- Preparing JSON business data
- Calling the Java API (`NanhuprintInterpreter`)
- Integrating nanhu-print-java into a Spring Boot service

**Location:** `claude/nanhu-pdf/`

**Trigger phrases:**
- "generate a PDF with nanhu-print-java"
- "write an XML template for nanhu-print-java"
- "how do I call NanhuprintInterpreter"
- "create a PDF invoice/report using nanhu-print-java"

## Directory Structure

```
claude/
└── nanhu-pdf/
    ├── SKILL.md                    # nanhu-pdf skill definition
    └── references/
        ├── xml-template.md         # XML template syntax, tags, CSS, dynamic tags
        ├── java-api.md             # Java API methods and integration patterns
        ├── examples.md             # Example templates and usage
        └── nanhuprint.xsd          # Official XSD schema for XML template validation
```
