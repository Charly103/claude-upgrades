# Guía de Uso — Claude Code Upgrades

> Para: Charly (Anti-Gravity)
> Fecha: 2026-02-22

---

## Qué Tienes y Cómo Usarlo

### Tu setup tiene 3 capas de potencia:

```
Capa 1: Skills automáticas (~/.claude/skills/)
  → Se activan SOLAS cuando Claude detecta el contexto
  → No tienes que hacer nada, solo hablar

Capa 2: Skills de Antigravity (~/.agent/skills/)
  → Disponibles en sesiones de Antigravity
  → Se activan por contexto o invocación

Capa 3: Documentación y planes (~/claude-upgrades/, ~/.claude/plans/)
  → Referencia manual — tú decides cuándo consultar
```

---

## Cuándo se Activa Cada Skill (Automáticamente)

### B.L.A.S.T. Protocol
**Se activa cuando dices:**
- "Empieza un nuevo proyecto"
- "Set up a project"
- "Inicializa esto"
- "Planifica la build"

**Qué hace:** Te guía por las 5 fases (Blueprint → Link → Architect → Stylize → Trigger). Te obliga a responder 5 preguntas de descubrimiento ANTES de escribir código.

**Ejemplo de uso:**
```
Tú: "Quiero crear un bot de Telegram que resuma noticias de YouTube"
Claude: [Activa B.L.A.S.T.] → Te hace las 5 preguntas → Crea gemini.md → Planifica → Ejecuta
```

### Agent Teams
**Se activa cuando dices:**
- "Crea un equipo de agentes"
- "Usa agentes en paralelo"
- "Multi-agent"
- "Spawn agents"

**Qué hace:** Te guía para crear equipos de agentes coordinados. Incluye prompts listos, guía de costes y pitfalls.

**Ejemplo de uso:**
```
Tú: "Crea un equipo de 3 agentes para analizar mi codebase"
Claude: [Activa Agent Teams] → Sugiere roles → Configura → Ejecuta en paralelo
```

### Superpowers (14 skills)
**Se activan por contexto.** Las más importantes:

| Situación | Skill que se activa |
|-----------|-------------------|
| Empiezas a planificar | superpowers-writing-plans |
| Ejecutas un plan | superpowers-executing-plans |
| Necesitas debugging | superpowers-systematic-debugging |
| Quieres TDD | superpowers-tdd |
| Lanzas sub-agentes | superpowers-parallel-agents |
| Pides code review | superpowers-requesting-review |
| Terminas una rama | superpowers-finishing-branch |

---

## Buenas Prácticas

### 1. Para Nuevos Proyectos

**SIEMPRE usa B.L.A.S.T.** Dile a Claude:
```
"Vamos a montar [descripción]. Usa el protocolo B.L.A.S.T."
```
Esto te ahorra horas de retrabajo porque te obliga a definir qué quieres ANTES de codear.

### 2. Para Tareas Complejas

**Usa Agent Teams cuando:**
- El trabajo se puede paralelizar (ej: analizar 5 módulos a la vez)
- Necesitas perspectivas múltiples (ej: debug desde frontend + backend + DB)
- Quieres builder + validator (uno codea, otro revisa)

**NO uses Agent Teams cuando:**
- Es un cambio en 1-2 archivos
- Es una pregunta simple
- Tienes presupuesto limitado de tokens

### 3. Para Debugging

Dile a Claude:
```
"Debuggea esto de forma sistemática"
```
Se activará `superpowers-systematic-debugging` que sigue un proceso metódico en vez de probar cosas al azar.

### 4. Para Code Reviews

```
"Revisa mi código antes de mergear"
```
Se activa `superpowers-requesting-review` con checklist completo.

### 5. Para Desarrollar Skills Nuevas

```
"Quiero crear una skill nueva para [X]"
```
Se activa `superpowers-writing-skills` que te guía en la estructura correcta.

---

## Estructura de Carpetas — Dónde Está Todo

```
~/claude-upgrades/              ← ESTÁS AQUÍ — carpeta de trabajo y registro
├── INVENTARIO.md               ← Lista completa de todo lo instalado
├── GUIA-USO.md                 ← Esta guía
└── (futuras mejoras aquí)

~/.claude/                      ← Config de Claude Code
├── skills/
│   ├── agent-teams/            ← Skill Agent Teams + 4 referencias
│   └── blast-protocol/         ← Skill B.L.A.S.T. + template sub-agentes
├── plans/
│   └── wondrous-percolating-curry.md  ← Plan arquitectura ecosistema
├── plugins/                    ← Marketplace oficial
├── settings.json               ← Settings globales
└── settings.local.json         ← Settings locales

~/.agent/skills/                ← 25 skills (14 Superpowers + 11 custom)

~/maya/                         ← Proyecto Maya (ORQUESTADOR.md, etc.)
~/antigravityclaw/              ← Proyecto GravityClaw
```

---

## Cómo se Mantiene Actualizado (Automático)

Antigravity tiene una skill `claude-upgrades-maintainer` que se encarga automáticamente:

1. **Se activa sola** cuando se instalan/eliminan skills, plugins, o se cambian configs
2. **Audita** los 3 directorios de skills y compara con el inventario
3. **Actualiza** `INVENTARIO.md` y `GUIA-USO.md` si hay diferencias
4. **Push a GitHub** automáticamente tras cada cambio

### Sincronización Manual

Si quieres forzar una sincronización, usa el workflow:
```
/sync-upgrades
```

### Mantenimiento manual (si no estás en Antigravity)

1. **Cuando instales algo nuevo** → Añádelo al INVENTARIO.md
2. **Cuando crees una skill nueva** → Ponla en `~/.claude/skills/` (para Claude Code) o `~/.agent/skills/` (para Antigravity)
3. **Cuando cambies el plan de arquitectura** → Actualiza el plan en `~/.claude/plans/`
4. **Esta carpeta (`~/claude-upgrades/`)** es tu punto de entrada — ábrela en Antigravity cuando quieras ver el estado de todo

---

## Próximos Pasos Recomendados

1. ~~**Subir esto a GitHub**~~ ✅ Repo: `Charly103/claude-upgrades`
2. ~~**Mantenimiento automatizado**~~ ✅ Skill `claude-upgrades-maintainer` + workflow `/sync-upgrades`
3. **Integrar B.L.A.S.T. en el plan de arquitectura** — Que sea el estándar para nuevos proyectos del ecosistema
4. **Empezar Fase 1 del plan** — Supabase shared brain
5. **Probar Agent Teams** en un proyecto real pequeño antes de usarlo en producción
