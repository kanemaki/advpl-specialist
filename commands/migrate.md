---
description: Migrate ADVPL procedural code to TLPP object-oriented code with classes, namespaces, and modern patterns
allowed-tools: Read, Write, Edit, Glob, Grep, Bash, Agent, Skill, WebSearch, WebFetch
argument-hint: "<file.prw> [--output file.tlpp] [--dry-run]"
---

# /advpl-specialist:migrate

**IMPORTANT:** Always respond in the same language the user is writing in. If the user writes in Portuguese, respond in Portuguese. If in English, respond in English. Adapt all explanations and suggestions to the user's language. Code comments may remain in English or match the user's language.

Convert ADVPL procedural code to TLPP with object-oriented patterns.

## Usage

```bash
/advpl-specialist:migrate <file.prw> [options]
```

## Options

| Flag | Description | Default |
|------|------------|---------|
| `--output` | Output .tlpp file path | Same name with .tlpp extension |
| `--dry-run` | Show migration plan without generating files | false |
| `--keep-original` | Keep the original .prw file | true |
| `--wrapper` | Generate backward compatibility wrapper | true |
| `--namespace` | Override namespace | Auto-detect from module |

## Process

1. **Read source file** - Read the .prw file completely
2. **Analyze structure** - Identify functions, dependencies, shared variables
3. **Search for callers** - Grep codebase for `u_FunctionName` references
4. **Design class structure** - Map functions to classes and methods
5. **Present plan** - Show migration mapping to user for approval
6. **If --dry-run** - Stop here and show the plan
7. **Execute migration** - Generate .tlpp file(s) following `advpl-to-tlpp-migration` skill
8. **Generate wrapper** - Create backward compatibility .prw wrapper if --wrapper
9. **Run checklist** - Validate against migration-checklist.md
10. **Report** - Show summary of changes

## Examples

```bash
# Migrate a file (shows plan first, then generates)
/advpl-specialist:migrate src/FATA001.prw

# Preview migration without generating files
/advpl-specialist:migrate src/FATA001.prw --dry-run

# Specify output path and namespace
/advpl-specialist:migrate src/FATA001.prw --output src/tlpp/PedidoService.tlpp --namespace mycompany.faturamento

# Migrate without backward compatibility wrapper
/advpl-specialist:migrate src/FATA001.prw --wrapper false
```

## Output

- `.tlpp` file with migrated class-based code
- Optional `.prw` wrapper for backward compatibility
- Migration summary with what changed and why
