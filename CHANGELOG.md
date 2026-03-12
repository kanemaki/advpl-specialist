# Changelog

All notable changes to this project will be documented in this file.
Todas as mudancas notaveis deste projeto serao documentadas neste arquivo.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.3] - 2026-03-11

### Added / Adicionado
- New `/review` command for code quality analysis (best practices, performance, security, modernization)
- Novo comando `/review` para analise de qualidade de codigo (boas praticas, performance, seguranca, modernizacao)
- New `/test` command for ProBat unit test generation (TLPP only)
- Novo comando `/test` para geracao de testes unitarios ProBat (apenas TLPP)
- New `/process` command for ERP business process consultation
- Novo comando `/process` para consulta de processos de negocio ERP
- New `code-reviewer` agent for ADVPL/TLPP code analysis with 21 review rules
- Novo agent `code-reviewer` para analise de codigo ADVPL/TLPP com 21 regras de revisao
- New `process-consultant` agent for ERP business processes
- Novo agent `process-consultant` para processos de negocio ERP
- New `advpl-code-review` skill with 4 rule categories (BP, PERF, SEC, MOD)
- Nova skill `advpl-code-review` com 4 categorias de regras (BP, PERF, SEC, MOD)
- New `probat-testing` skill with ProBat API reference and unit test patterns (TDN-validated)
- Nova skill `probat-testing` com referencia ProBat API e padroes de testes unitarios (validado no TDN)
- New `protheus-business` skill with 8 ERP module references (COM, EST, FAT, FIN, CTB, FIS, PCP, MNT)
- Nova skill `protheus-business` com referencia de 8 modulos ERP (COM, EST, FAT, FIN, CTB, FIS, PCP, MNT)
- 4 new code generation patterns: TReport, FWFormBrowse, Jobs/Scheduler, Workflow/BPM
- 4 novos padroes de geracao de codigo: TReport, FWFormBrowse, Jobs/Scheduler, Workflow/BPM
- 16 new TDN-validated native functions (TReport, FWFormBrowse, Jobs, Email classes)
- 16 novas funcoes nativas validadas no TDN (TReport, FWFormBrowse, Jobs, classes de Email)
- 93 MV_* parameters validated across 8 modules via TDN and Terminal de Informacao
- 93 parametros MV_* validados em 8 modulos via TDN e Terminal de Informacao
- ProBat annotations validated via official TOTVS tlpp-probat-samples repository
- Anotacoes ProBat validadas via repositorio oficial TOTVS tlpp-probat-samples

### Fixed / Corrigido
- Removed 90+ fabricated MV_* parameters from business module skills
- Removidos 90+ parametros MV_* fabricados das skills de modulos de negocio
- Fixed incorrect parameter names (MV_ESTNEGA→MV_ESTNEG, MV_SPESSION→MV_USASPED, etc.)
- Corrigidos nomes de parametros incorretos (MV_ESTNEGA→MV_ESTNEG, MV_SPESSION→MV_USASPED, etc.)
- Removed fabricated SC2 table fields (C2_TESSION/C2_TESSION2) from PCP skill
- Removidos campos fabricados da tabela SC2 (C2_TESSION/C2_TESSION2) da skill PCP

## [1.0.2] - 2026-03-09

### Added / Adicionado
- Playwright MCP fallback for all web documentation access (agents: docs-reference, debugger, code-generator; skill: protheus-reference)
- Fallback via Playwright MCP para todo acesso web a documentacao (agents: docs-reference, debugger, code-generator; skill: protheus-reference)
- When WebSearch or WebFetch fails, agents now fall back to Playwright browser tools (browser_navigate, browser_snapshot, browser_take_screenshot)
- Quando WebSearch ou WebFetch falham, os agents agora utilizam as ferramentas Playwright como fallback (browser_navigate, browser_snapshot, browser_take_screenshot)
- Hybrid approach: tries text snapshot first, falls back to screenshot for complex visual content
- Abordagem hibrida: tenta snapshot de texto primeiro, usa screenshot para conteudo visual complexo
- Playwright MCP installation recommendation in session-start hook
- Recomendacao de instalacao do Playwright MCP no hook session-start

## [1.0.1] - 2026-03-05

### Added / Adicionado
- SOAP Web Service patterns (`patterns-soap.md`) with WsService and TWsdlManager
- Padroes de Web Service SOAP (`patterns-soap.md`) com WsService e TWsdlManager
- Superpowers plugin recommendation in session-start hook and README
- Recomendacao do plugin superpowers no hook session-start e README
- Planning mode enforcement for `generate` and `migrate` commands
- Modo planejamento obrigatorio para os comandos `generate` e `migrate`
- 50+ indicator in session-start hook when file count reaches limit
- Indicador 50+ no hook session-start quando a contagem de arquivos atinge o limite
- Official TOTVS TLPP naming conventions from TDN
- Convencoes oficiais de nomenclatura TLPP da TOTVS do TDN
- Language detection in all commands (responds in user's language)
- Deteccao de idioma em todos os comandos (responde no idioma do usuario)
- Embedded SQL skill with BeginSQL/EndSQL patterns and macros
- Skill de Embedded SQL com padroes BeginSQL/EndSQL e macros

### Fixed / Corrigido
- Replaced all obsolete `#Include "Protheus.ch"` with `#Include "TOTVS.CH"` across 10 files
- Substituido o obsoleto `#Include "Protheus.ch"` por `#Include "TOTVS.CH"` em 10 arquivos
- Corrected TLPP includes to use `.th` files (`tlpp-core.th`, `tlpp-rest.th`) instead of `TOTVS.CH`
- Corrigido includes TLPP para usar arquivos `.th` (`tlpp-core.th`, `tlpp-rest.th`) em vez de `TOTVS.CH`
- Removed incorrect `using namespace tlpp.*` (`tlpp.core`, `tlpp.rest`, `tlpp.log`, `tlpp.data`) from all examples
- Removido `using namespace tlpp.*` incorreto (`tlpp.core`, `tlpp.rest`, `tlpp.log`, `tlpp.data`) de todos os exemplos
- Fixed migration target to use `.th` includes instead of `TOTVS.CH`
- Corrigido alvo de migracao para usar includes `.th` em vez de `TOTVS.CH`
- Resolved ambiguous text across repository
- Resolvido texto ambiguo em todo o repositorio
- Added missing `Skill` and `Bash` to allowed-tools in all commands
- Adicionado `Skill` e `Bash` faltantes em allowed-tools de todos os comandos
- Fixed Local variable declarations placement in native-functions examples
- Corrigido posicionamento de declaracoes de variaveis Local nos exemplos de native-functions

## [1.0.0] - 2026-03-04

### Added / Adicionado
- Initial release
- Lancamento inicial
- 4 commands: `generate`, `migrate`, `diagnose`, `docs`
- 4 comandos: `generate`, `migrate`, `diagnose`, `docs`
- 4 agents: `code-generator`, `migrator`, `debugger`, `docs-reference`
- 4 agents: `code-generator`, `migrator`, `debugger`, `docs-reference`
- 5 skills: `advpl-code-generation`, `advpl-to-tlpp-migration`, `advpl-debugging`, `embedded-sql`, `protheus-reference`
- 5 skills: `advpl-code-generation`, `advpl-to-tlpp-migration`, `advpl-debugging`, `embedded-sql`, `protheus-reference`
- SessionStart hook with automatic ADVPL/TLPP project detection
- Hook SessionStart com deteccao automatica de projeto ADVPL/TLPP
- 165+ native functions documented
- 165+ funcoes nativas documentadas
- 9 SX tables reference
- Referencia de 9 tabelas SX
- REST API patterns (FWRest and WsRestFul)
- Padroes de REST API (FWRest e WsRestFul)
- 50 common errors with cause and solution
- 50 erros comuns com causa e solucao
- 10 performance optimization categories
- 10 categorias de otimizacao de performance
- 16 most-used entry points by module
- 16 pontos de entrada mais usados por modulo
- TLPP class templates (Service, Repository, DTO)
- Templates de classes TLPP (Service, Repository, DTO)
- Complete MVC patterns (MenuDef, ModelDef, ViewDef, FWMVCRotAuto)
- Padroes MVC completos (MenuDef, ModelDef, ViewDef, FWMVCRotAuto)
- Marketplace support via `marketplace.json`
- Suporte ao Marketplace via `marketplace.json`
