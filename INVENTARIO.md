# Inventario de Mejoras Claude Code — Anti-Gravity Ecosystem

> Fecha: 2026-02-22
> Propietario: Charly
> Objetivo: Registro completo de todo lo instalado, configurado y planificado para Claude Code

---

## 1. Skills Instaladas

### 1.1 Skills en `~/.claude/skills/` (Claude Code nativo)

Estas skills se activan **automáticamente** cuando Claude detecta el contexto adecuado.

| Skill | Descripción | Estado |
|-------|-------------|--------|
| `agent-teams` | Guía completa de Agent Teams: creación, roles, prompts, costes, pitfalls. SKILL.md + 4 archivos de referencia. | Activo |
| `blast-protocol` | Protocolo B.L.A.S.T. (Blueprint, Link, Architect, Stylize, Trigger) + template de sub-agentes paralelos. | Activo |

### 1.2 Skills en `~/.agent/skills/` (Antigravity/agente)

| Skill | Tipo | Descripción |
|-------|------|-------------|
| `superpowers-brainstorming` | Superpowers | Sesiones de brainstorming estructuradas |
| `superpowers-executing-plans` | Superpowers | Ejecución de planes paso a paso |
| `superpowers-finishing-branch` | Superpowers | Cerrar una rama de desarrollo limpiamente |
| `superpowers-git-worktrees` | Superpowers | Uso de git worktrees para trabajo aislado |
| `superpowers-parallel-agents` | Superpowers | Despachar sub-agentes en paralelo |
| `superpowers-receiving-review` | Superpowers | Recibir y aplicar code reviews |
| `superpowers-requesting-review` | Superpowers | Solicitar code reviews estructuradas |
| `superpowers-subagent-dev` | Superpowers | Desarrollo dirigido por sub-agentes |
| `superpowers-systematic-debugging` | Superpowers | Debugging metódico paso a paso |
| `superpowers-tdd` | Superpowers | Test-Driven Development |
| `superpowers-using-superpowers` | Superpowers | Meta-skill: cómo usar el framework |
| `superpowers-verification` | Superpowers | Verificación antes de completar tareas |
| `superpowers-writing-plans` | Superpowers | Escribir planes de implementación |
| `superpowers-writing-skills` | Superpowers | Crear nuevas skills |
| `claude-code-agent-teams` | Custom | Versión compacta de Agent Teams |
| `claude-code-docs` | Custom | Índice de documentación oficial (57 páginas) |
| `antigravity-skill-creator` | Original | Crear skills para Antigravity |
| `brainstorming` | Original | Sesiones de ideas |
| `brand-identity` | Original | Identidad de marca + recursos (design-tokens, tech-stack, voice-tone) |
| `error-handling-patterns` | Original | Patrones de manejo de errores (Python, TS, universal) |
| `maya-openclaw` | Original | Gestión de Maya en OpenClaw |
| `openclaw-reference` | Original | Referencia de OpenClaw |
| `orchestrator` | Original | Skill de orquestador Anti-Gravity |
| `reverse-engineering-videos` | Original | Ingeniería inversa de vídeos + templates Remotion |
| `writing-plans` | Original | Escritura de planes |
| `claude-upgrades-maintainer` | Original | Mantenimiento automático del repo claude-upgrades + sync GitHub |

**Total: 26 skills en ~/.agent/ + 2 skills en ~/.claude/**

---

## 2. Plugins

| Ubicación | Contenido |
|-----------|-----------|
| `~/.claude/plugins/marketplaces/claude-plugins-official/` | Marketplace oficial de plugins Claude Code |

---

## 3. Plan de Arquitectura del Ecosistema

| Archivo | Descripción |
|---------|-------------|
| `~/.claude/plans/wondrous-percolating-curry.md` | Plan completo de rediseño (28KB) |

**Contenido del plan:**
- 4 agentes activos: Anti-Gravity, Maya, Matrix, GravityClaw
- 2 agentes futuros: RaspyClaw, MacLaw
- 7 fases de implementación
- 3 capas de memoria: SQLite (local) + Supabase (compartida) + Pinecone (semántica)
- NotebookLM como motor de aprendizaje activo
- Matrix como co-orquestador (no subordinado a Maya)

---

## 4. Configuración del Ecosistema

| Componente | Ubicación | Estado |
|------------|-----------|--------|
| Claude Code settings | `~/.claude/settings.json` | Activo |
| Claude Code local settings | `~/.claude/settings.local.json` | Activo |
| ORQUESTADOR.md | `~/maya/ORQUESTADOR.md` | Activo |
| Maya (OpenClaw VPS) | `46.202.171.91` | Activo |
| GravityClaw (Railway) | `~/antigravityclaw/` | Activo |
| Memoria persistente Anti-Gravity | `~/.claude/projects/-Users-charly-maya/memory/MEMORY.md` | Activo |

---

## 5. Recursos y Enlaces de Referencia

| Recurso | URL | Uso |
|---------|-----|-----|
| Superpowers framework | https://github.com/obra/superpowers | Skills de desarrollo (14 instaladas) |
| Claude Code docs index | https://code.claude.com/docs/llms.txt | 57 páginas de documentación oficial |
| Claude Code setup | https://code.claude.com/docs/en/setup | Guía de instalación |
| Agent Teams docs | https://code.claude.com/docs/en/agent-teams.md | Documentación oficial Agent Teams |
| Agent Teams (Notion) | https://notion.so/Claude-Agent-Teams-303e8d6bd13780a9be44e0e73a9fc138 | Guía completa (requiere auth Notion) |
| Awesome Claude Skills | https://github.com/travisvn/awesome-claude-skills | Repositorio comunitario de skills |

---

## 6. Pendiente de Integrar

| Elemento | Estado | Notas |
|----------|--------|-------|
| B.L.A.S.T. en plan de arquitectura | Pendiente | Integrar como metodología estándar de nuevos proyectos |
| Supabase shared brain | Pendiente | Fase 1 del plan de arquitectura |
| Reestructuración de carpetas | Pendiente | Fase 2 del plan de arquitectura |

---

## Historial de Cambios

| Fecha | Cambio |
|-------|--------|
| 2026-02-22 | Instalación de 14 skills Superpowers |
| 2026-02-22 | Creación de skill Agent Teams (2 versiones) |
| 2026-02-22 | Creación de skill Claude Code Docs |
| 2026-02-22 | Creación de skill B.L.A.S.T. Protocol |
| 2026-02-22 | Plan de arquitectura del ecosistema completado |
| 2026-02-22 | Creación de este inventario |
| 2026-02-22 | Skill `claude-upgrades-maintainer` + workflow `/sync-upgrades` creados |
| 2026-02-22 | Repo subido a GitHub: `Charly103/claude-upgrades` |
| 2026-02-22 | Repo clonado en VPS de Maya + skill `claude-upgrades.md` desplegada |
