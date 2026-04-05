<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:1E3258,100:137DC5&height=220&section=header&text=Plugin%20QA%20(PQA)&fontSize=50&fontColor=FFD700&fontAlignY=35&desc=Ciclo%20de%20vida%20completo%20para%20plugins%20de%20Claude%20Code&descSize=18&descColor=ffffff&descAlignY=55" alt="Plugin QA Banner" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/versión-2.0.0-137DC5?style=for-the-badge" alt="Versión" />
  <img src="https://img.shields.io/badge/licencia-MIT-122562?style=for-the-badge" alt="Licencia" />
  <img src="https://img.shields.io/badge/agentes-4-FFD700?style=for-the-badge" alt="Agentes" />
  <img src="https://img.shields.io/badge/skills-20-BBA0CC?style=for-the-badge" alt="Skills" />
  <img src="https://img.shields.io/badge/comandos-31-808080?style=for-the-badge" alt="Comandos" />
</p>

---

## Acerca de Plugin QA

**Plugin QA (PQA)** es un framework de calidad para el ciclo de vida completo de plugins de Claude Code. Desde scaffolding hasta validación, con tests automatizados, auditoría de estructura y publicación.

Cada etapa del desarrollo de un plugin queda cubierta: creación de la estructura inicial, validación de convenciones, ejecución de pruebas y preparación para distribución.

---

## Características principales

- **Scaffolding de plugins** — Genera la estructura completa de un plugin en segundos
- **Validación de estructura** — Verifica que el plugin cumple con las convenciones requeridas
- **Tests automatizados** — Suite de pruebas para cada skill y comando del plugin
- **Auditoría de calidad** — Análisis profundo de cobertura, consistencia y documentación
- **Publicación asistida** — Preparación del paquete para distribución
- **Compatible con marketplace** — Validación contra los requisitos del ecosistema

---

## Instalación

Agrega Plugin QA como plugin de Claude Code:

```bash
# Instalar vía CLI
claude plugin:install ./plugins/plugin-qa

# O agregar la ruta del plugin a tu configuración de Claude Code
```

---

## Uso rápido

```
/pqa:create "<idea>"    # Crea un plugin desde cero con ideación guiada
/pqa:lifecycle "<idea>" # Pipeline completo: crear + QA en un solo flujo
/pqa:audit [ruta]       # Auditoría completa de calidad
/pqa:validate           # Validación estructural rápida
/pqa:fix                # Auto-corrección de problemas comunes
/pqa:menu               # Los 31 comandos disponibles
```

---

## Arquitectura

PQA orquesta 4 agentes a través de 9 movimientos:

```
  UPSTREAM (Crear)                     DOWNSTREAM (QA)
  ==================                   ================
  1. IDEATE ----+                      6. VALIDATE
                |  G1                  7. AUDIT
  2. PLAN ------+                      8. REPORT
                |  G2                  9. FIX
  3. DESIGN ----+
                |  G3
  4. SPECIFY ---+
                |  G4
  5. BUILD -----+--> Directorio del Plugin --> VALIDATE -> AUDIT -> REPORT -> (FIX)
```

Las puertas de calidad G1-G4 requieren aprobación del usuario entre movimientos upstream.

---

## Agentes

| Agente | Rol | Movimientos |
|--------|-----|-------------|
| `plugin-architect` | Ideación, planificación de arquitectura, diseño de componentes | IDEATE, PLAN, DESIGN |
| `plugin-spec-writer` | Especificaciones listas para producción y activos MOAT | SPECIFY |
| `plugin-builder-agent` | Generación de código, scaffolding, creación de directorios MOAT | BUILD |
| `plugin-qa-engineer` | Validación, auditoría de seguridad, reportes, auto-corrección | VALIDATE, AUDIT, REPORT, FIX |

---

## Patrón MOAT

MOAT (Methods, Ontology, Assets, Templates) es el patrón de calidad para profundidad de skills:

- `references/` — Archivos de ontología, resúmenes de especificaciones, conocimiento de dominio
- `examples/` — Ejemplos de entrada/salida, casos límite, antes/después
- `prompts/` — Plantillas reutilizables de prompts NL-HP

---

## Parte del Ecosistema MetodologIA / JM Labs

Plugin QA forma parte de un ecosistema más amplio de herramientas:

| Repositorio | Descripción |
|-------------|-------------|
| [mao-discovery-framework](https://github.com/JaviMontano/mao-discovery-framework) | Framework de discovery y análisis organizacional |
| [mao-sdd](https://github.com/JaviMontano/mao-sdd) | Specification-Driven Development para software |
| [mao-sovereign-architect](https://github.com/JaviMontano/mao-sovereign-architect) | Arquitectura de software con agentes autónomos |

---

## Licencia

Este proyecto está licenciado bajo **MIT**. Consulta el archivo [LICENSE](LICENSE) para más detalles.

---

<p align="center">
  Creado por <a href="https://github.com/JaviMontano">Javier Montaño</a> · MetodologIA / JM Labs · MIT
</p>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:1E3258,100:137DC5&height=120&section=footer" alt="Footer" />
</p>
