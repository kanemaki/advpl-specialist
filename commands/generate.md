---
description: Generate ADVPL/TLPP code - functions, classes, MVC structures, REST APIs, Web Services, and entry points for TOTVS Protheus
allowed-tools: Read, Write, Edit, Glob, Grep, Bash, Agent, WebSearch, WebFetch
argument-hint: "<type> [name] [--module module]"
---

# /advpl-specialist:generate

Generate new ADVPL or TLPP code following Protheus conventions and best practices.

## Usage

```bash
/advpl-specialist:generate <type> [name] [--module <module>]
```

## Types

| Type | Description | Output |
|------|------------|--------|
| `function` | User Function | .prw file |
| `class` | TLPP class | .tlpp file |
| `mvc` | MVC structure (MenuDef, ModelDef, ViewDef) | .prw file |
| `rest` | REST API endpoint | .prw or .tlpp file |
| `ponto-entrada` | Entry point | .prw file |
| `webservice` | SOAP Web Service | .prw file |

## Options

| Flag | Description | Default |
|------|------------|---------|
| `--module` | Module prefix (COM, FAT, FIN, etc.) | Ask user |
| `--lang` | Language: advpl or tlpp | advpl for function/mvc/pe, tlpp for class |
| `--output` | Output file path | Auto-generated based on name |

## Process

1. **Parse arguments** - Extract type, name, and flags
2. **Ask missing details** - If name or module not provided, ask the user
3. **Ask business requirements** - What should the code do?
4. **Load skill** - Invoke `advpl-code-generation` skill
5. **Load patterns** - Read appropriate supporting file for the type
6. **Generate code** - Create complete, production-ready code following all conventions
7. **Write file** - Save with correct extension (.prw or .tlpp)
8. **Report** - Show what was created and key decisions

## Examples

```bash
# Create a User Function for billing module
/advpl-specialist:generate function FATA050 --module FAT

# Create a TLPP service class
/advpl-specialist:generate class PedidoService

# Create complete MVC CRUD
/advpl-specialist:generate mvc CadProduto --module EST

# Create a REST API endpoint
/advpl-specialist:generate rest ClienteAPI --lang tlpp

# Create an entry point
/advpl-specialist:generate ponto-entrada MT100LOK

# Create a SOAP Web Service
/advpl-specialist:generate webservice WSPedido
```

## Output

A complete, compilable source file saved to the project directory with:
- Protheus.doc documentation header
- Proper includes/namespace declarations
- Full implementation following conventions
- Error handling
- Area save/restore for DB operations
