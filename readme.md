# Hallazgos de SonarQube

**INFORME INTEGRAL — Código Fuente A**

**Reporte de incidencias sin omisiones**

**Proyecto analizado:** `ISY1102-Prueba`
**Fuente:** `SonarQube_CodigoFuenteA.json`

Todas las incidencias se reproducen en el mismo orden del arreglo `issues`. Los nombres de campo y los valores originales se conservan en las fichas detalladas.

## 1. Panorama general

La siguiente distribución y el índice de incidencias son ayudas de lectura adicionales; no sustituyen los registros completos.

- **Incidencias (total):** 25
- **Tipos distintos:** 3
- **Severidades distintas:** 3

| Tipo | BLOCKER | MAJOR | MINOR |
| --- | ---: | ---: | ---: |
| `VULNERABILITY` | 1 | 2 | 3 |
| `BUG` | 0 | 10 | 0 |
| `CODE_SMELL` | 0 | 0 | 9 |
| **TOTAL** | 1 | 12 | 12 |

### Metadatos principales del JSON

| Campo | Valor |
| --- | --- |
| `proyecto` | ``"ISY1102-Prueba"`` |
| `total` | ``25`` |

### Convención de lectura

Los valores están representados en notación JSON (por ejemplo, cadenas entre comillas, valores booleanos `true`/`false` y arreglos `[]`). Los campos anidados se identifican por su estructura original, como `textRange.startLine`; el arreglo `impacts` se reproduce completo. Los campos vacíos y las incidencias repetidas se mantienen expresamente.

## 2. Índice de incidencias

Cada número enlaza con la ficha del hallazgo respectivo. Se mantiene el orden del archivo original.

| N.º | Severidad | Tipo | Regla | Componente / línea |
| ---: | --- | --- | --- | --- |
| [01](#301-hallazgo-01-de-25) | `MINOR` | `VULNERABILITY` | `docker:S6471` | `BACKEND/Dockerfile` · L1 |
| [02](#302-hallazgo-02-de-25) | `MINOR` | `VULNERABILITY` | `javascript:S5689` | `BACKEND/src/app.js` · L20 |
| [03](#303-hallazgo-03-de-25) | `MAJOR` | `VULNERABILITY` | `javascript:S5122` | `BACKEND/src/app.js` · L22 |
| [04](#304-hallazgo-04-de-25) | `BLOCKER` | `VULNERABILITY` | `secrets:S6698` | `BACKEND/src/db.js` · L6 |
| [05](#305-hallazgo-05-de-25) | `MAJOR` | `VULNERABILITY` | `javascript:S5693` | `BACKEND/src/routes/contracts.js` · L15 |
| [06](#306-hallazgo-06-de-25) | `MINOR` | `CODE_SMELL` | `javascript:S7773` | `BACKEND/src/routes/contracts.js` · L213 |
| [07](#307-hallazgo-07-de-25) | `MINOR` | `CODE_SMELL` | `javascript:S7773` | `BACKEND/src/routes/contracts.js` · L220 |
| [08](#308-hallazgo-08-de-25) | `MINOR` | `CODE_SMELL` | `javascript:S7773` | `BACKEND/src/routes/contracts.js` · L232 |
| [09](#309-hallazgo-09-de-25) | `MINOR` | `CODE_SMELL` | `javascript:S7773` | `BACKEND/src/routes/contracts.js` · L244 |
| [10](#310-hallazgo-10-de-25) | `MINOR` | `CODE_SMELL` | `javascript:S7773` | `BACKEND/src/routes/contracts.js` · L256 |
| [11](#311-hallazgo-11-de-25) | `MINOR` | `CODE_SMELL` | `javascript:S7773` | `BACKEND/src/routes/metricas.js` · L130 |
| [12](#312-hallazgo-12-de-25) | `MINOR` | `CODE_SMELL` | `javascript:S7773` | `BACKEND/src/routes/metricas.js` · L137 |
| [13](#313-hallazgo-13-de-25) | `MINOR` | `CODE_SMELL` | `javascript:S7773` | `BACKEND/src/routes/metricas.js` · L149 |
| [14](#314-hallazgo-14-de-25) | `MINOR` | `CODE_SMELL` | `javascript:S7773` | `BACKEND/src/routes/metricas.js` · L161 |
| [15](#315-hallazgo-15-de-25) | `MINOR` | `VULNERABILITY` | `docker:S6471` | `FRONTEND/Dockerfile` · L34 |
| [16](#316-hallazgo-16-de-25) | `MAJOR` | `BUG` | `css:S4649` | `FRONTEND/src/index.css` · L6 |
| [17](#317-hallazgo-17-de-25) | `MAJOR` | `BUG` | `javascript:S9383` | `FRONTEND/src/pages/Home.jsx` · L77 |
| [18](#318-hallazgo-18-de-25) | `MAJOR` | `BUG` | `javascript:S9383` | `FRONTEND/src/pages/clientes/ClienteForm.jsx` · L63 |
| [19](#319-hallazgo-19-de-25) | `MAJOR` | `BUG` | `javascript:S9383` | `FRONTEND/src/pages/contratos/ContratoDetalle.jsx` · L21 |
| [20](#320-hallazgo-20-de-25) | `MAJOR` | `BUG` | `javascript:S9383` | `FRONTEND/src/pages/contratos/ContratoForm.jsx` · L34 |
| [21](#321-hallazgo-21-de-25) | `MAJOR` | `BUG` | `javascript:S9383` | `FRONTEND/src/pages/contratos/ContratoForm.jsx` · L46 |
| [22](#322-hallazgo-22-de-25) | `MAJOR` | `BUG` | `javascript:S9383` | `FRONTEND/src/pages/contratos/ContratosTabCreate.jsx` · L27 |
| [23](#323-hallazgo-23-de-25) | `MAJOR` | `BUG` | `javascript:S9383` | `FRONTEND/src/pages/empresas/EmpresaForm.jsx` · L33 |
| [24](#324-hallazgo-24-de-25) | `MAJOR` | `BUG` | `javascript:S9383` | `FRONTEND/src/pages/empresas/EmpresasList.jsx` · L50 |
| [25](#325-hallazgo-25-de-25) | `MAJOR` | `BUG` | `javascript:S9383` | `FRONTEND/src/pages/usuarios/UsuarioForm.jsx` · L36 |

---

### 3.01 Hallazgo 01 de 25

**Regla:** `docker:S6471` · **Severidad:** `MINOR` · **Tipo:** `VULNERABILITY`

**`message` · Descripción original**

> The "node" image runs with "root" as the default user. Make sure it is safe here.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"d32e65e5-e62c-4ef6-b9cc-ac1a471600ae"`` |
| `rule` | ``"docker:S6471"`` |
| `severity` | ``"MINOR"`` |
| `component` | ``"ISY1102-Prueba:BACKEND/Dockerfile"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``1`` |
| `hash` | ``"216a2f74829b60c1ee0ca07e7200168f"`` |
| `textRange.startLine` | ``1`` |
| `textRange.endLine` | ``1`` |
| `textRange.startOffset` | ``0`` |
| `textRange.endOffset` | ``19`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"15min"`` |
| `debt` | ``"15min"`` |
| `author` | ``""`` |
| `tags` | ``["cwe", "dockerfile", "former-hotspot"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"VULNERABILITY"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``false`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"COMPLETE"`` |
| `cleanCodeAttributeCategory` | ``"INTENTIONAL"`` |
| `impacts` | ``[{"softwareQuality": "SECURITY", "severity": "LOW"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.02 Hallazgo 02 de 25

**Regla:** `javascript:S5689` · **Severidad:** `MINOR` · **Tipo:** `VULNERABILITY`

**`message` · Descripción original**

> This framework implicitly discloses version information by default. Make sure it is safe here.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"886a9c48-b2b6-4ecd-ba7d-2a92292847ed"`` |
| `rule` | ``"javascript:S5689"`` |
| `severity` | ``"MINOR"`` |
| `component` | ``"ISY1102-Prueba:BACKEND/src/app.js"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``20`` |
| `hash` | ``"4af77bcf43147b78489dd9c4043bfe01"`` |
| `textRange.startLine` | ``20`` |
| `textRange.endLine` | ``20`` |
| `textRange.startOffset` | ``6`` |
| `textRange.endOffset` | ``9`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"5min"`` |
| `debt` | ``"5min"`` |
| `author` | ``""`` |
| `tags` | ``["cwe", "express.js", "former-hotspot"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"VULNERABILITY"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``false`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"TRUSTWORTHY"`` |
| `cleanCodeAttributeCategory` | ``"RESPONSIBLE"`` |
| `impacts` | ``[{"softwareQuality": "SECURITY", "severity": "LOW"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.03 Hallazgo 03 de 25

**Regla:** `javascript:S5122` · **Severidad:** `MAJOR` · **Tipo:** `VULNERABILITY`

**`message` · Descripción original**

> Make sure that enabling CORS is safe here.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"7575f040-6795-459e-811f-46c81ae7ab29"`` |
| `rule` | ``"javascript:S5122"`` |
| `severity` | ``"MAJOR"`` |
| `component` | ``"ISY1102-Prueba:BACKEND/src/app.js"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``22`` |
| `hash` | ``"c130ad820d45a83a455ca80ab658384e"`` |
| `textRange.startLine` | ``22`` |
| `textRange.endLine` | ``22`` |
| `textRange.startOffset` | ``0`` |
| `textRange.endOffset` | ``15`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"4h"`` |
| `debt` | ``"4h"`` |
| `author` | ``""`` |
| `tags` | ``["cwe", "express.js", "former-hotspot"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"VULNERABILITY"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``false`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"COMPLETE"`` |
| `cleanCodeAttributeCategory` | ``"INTENTIONAL"`` |
| `impacts` | ``[{"softwareQuality": "SECURITY", "severity": "MEDIUM"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.04 Hallazgo 04 de 25

**Regla:** `secrets:S6698` · **Severidad:** `BLOCKER` · **Tipo:** `VULNERABILITY`

**`message` · Descripción original**

> Make sure this PostgreSQL password gets changed and removed from the code.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"28f00c1d-d4f7-4f9b-8d50-8dd6734dc791"`` |
| `rule` | ``"secrets:S6698"`` |
| `severity` | ``"BLOCKER"`` |
| `component` | ``"ISY1102-Prueba:BACKEND/src/db.js"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``6`` |
| `hash` | ``"9bd480a5cc8cb8951e6bfc4c75b2d1b0"`` |
| `textRange.startLine` | ``6`` |
| `textRange.endLine` | ``6`` |
| `textRange.startOffset` | ``23`` |
| `textRange.endOffset` | ``30`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"30min"`` |
| `debt` | ``"30min"`` |
| `author` | ``""`` |
| `tags` | ``["cwe", "secret"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"VULNERABILITY"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``false`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"TRUSTWORTHY"`` |
| `cleanCodeAttributeCategory` | ``"RESPONSIBLE"`` |
| `impacts` | ``[{"softwareQuality": "SECURITY", "severity": "BLOCKER"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.05 Hallazgo 05 de 25

**Regla:** `javascript:S5693` · **Severidad:** `MAJOR` · **Tipo:** `VULNERABILITY`

**`message` · Descripción original**

> Make sure the content length limit is safe here.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"8cc0a7df-ed52-45eb-94e0-0a8f5a2db6d2"`` |
| `rule` | ``"javascript:S5693"`` |
| `severity` | ``"MAJOR"`` |
| `component` | ``"ISY1102-Prueba:BACKEND/src/routes/contracts.js"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``15`` |
| `hash` | ``"9b926b79547ceaf33a15d55d3b76d035"`` |
| `textRange.startLine` | ``15`` |
| `textRange.endLine` | ``15`` |
| `textRange.startOffset` | ``15`` |
| `textRange.endOffset` | ``21`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"5min"`` |
| `debt` | ``"5min"`` |
| `author` | ``""`` |
| `tags` | ``["cwe", "express.js", "former-hotspot"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"VULNERABILITY"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``false`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"TRUSTWORTHY"`` |
| `cleanCodeAttributeCategory` | ``"RESPONSIBLE"`` |
| `impacts` | ``[{"softwareQuality": "SECURITY", "severity": "MEDIUM"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.06 Hallazgo 06 de 25

**Regla:** `javascript:S7773` · **Severidad:** `MINOR` · **Tipo:** `CODE_SMELL`

**`message` · Descripción original**

> Prefer `Number.parseInt` over `parseInt`.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"35f33271-6ffc-4093-9326-806fd035e5b1"`` |
| `rule` | ``"javascript:S7773"`` |
| `severity` | ``"MINOR"`` |
| `component` | ``"ISY1102-Prueba:BACKEND/src/routes/contracts.js"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``213`` |
| `hash` | ``"d55ab40cf16c0e074be1bcc12fd37172"`` |
| `textRange.startLine` | ``213`` |
| `textRange.endLine` | ``213`` |
| `textRange.startOffset` | ``26`` |
| `textRange.endOffset` | ``34`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"2min"`` |
| `debt` | ``"2min"`` |
| `author` | ``""`` |
| `tags` | ``["convention", "es2015", "editable-source"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"CODE_SMELL"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``true`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"CONVENTIONAL"`` |
| `cleanCodeAttributeCategory` | ``"CONSISTENT"`` |
| `impacts` | ``[{"softwareQuality": "RELIABILITY", "severity": "MEDIUM"}, {"softwareQuality": "MAINTAINABILITY", "severity": "LOW"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.07 Hallazgo 07 de 25

**Regla:** `javascript:S7773` · **Severidad:** `MINOR` · **Tipo:** `CODE_SMELL`

**`message` · Descripción original**

> Prefer `Number.parseInt` over `parseInt`.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"f28770a5-96ee-4667-ad2f-7352290ed27b"`` |
| `rule` | ``"javascript:S7773"`` |
| `severity` | ``"MINOR"`` |
| `component` | ``"ISY1102-Prueba:BACKEND/src/routes/contracts.js"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``220`` |
| `hash` | ``"7485c19d5ce5ceee7c92e86894f6e529"`` |
| `textRange.startLine` | ``220`` |
| `textRange.endLine` | ``220`` |
| `textRange.startOffset` | ``26`` |
| `textRange.endOffset` | ``34`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"2min"`` |
| `debt` | ``"2min"`` |
| `author` | ``""`` |
| `tags` | ``["convention", "es2015", "editable-source"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"CODE_SMELL"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``true`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"CONVENTIONAL"`` |
| `cleanCodeAttributeCategory` | ``"CONSISTENT"`` |
| `impacts` | ``[{"softwareQuality": "RELIABILITY", "severity": "MEDIUM"}, {"softwareQuality": "MAINTAINABILITY", "severity": "LOW"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.08 Hallazgo 08 de 25

**Regla:** `javascript:S7773` · **Severidad:** `MINOR` · **Tipo:** `CODE_SMELL`

**`message` · Descripción original**

> Prefer `Number.parseInt` over `parseInt`.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"f3d165b0-a049-4bde-aa11-530d19a6c6d6"`` |
| `rule` | ``"javascript:S7773"`` |
| `severity` | ``"MINOR"`` |
| `component` | ``"ISY1102-Prueba:BACKEND/src/routes/contracts.js"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``232`` |
| `hash` | ``"2c0d7c66101259f2969d9d3c366690d6"`` |
| `textRange.startLine` | ``232`` |
| `textRange.endLine` | ``232`` |
| `textRange.startOffset` | ``27`` |
| `textRange.endOffset` | ``35`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"2min"`` |
| `debt` | ``"2min"`` |
| `author` | ``""`` |
| `tags` | ``["convention", "es2015", "editable-source"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"CODE_SMELL"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``true`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"CONVENTIONAL"`` |
| `cleanCodeAttributeCategory` | ``"CONSISTENT"`` |
| `impacts` | ``[{"softwareQuality": "RELIABILITY", "severity": "MEDIUM"}, {"softwareQuality": "MAINTAINABILITY", "severity": "LOW"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.09 Hallazgo 09 de 25

**Regla:** `javascript:S7773` · **Severidad:** `MINOR` · **Tipo:** `CODE_SMELL`

**`message` · Descripción original**

> Prefer `Number.parseInt` over `parseInt`.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"0e5af43c-1861-40bd-826d-7e3e5ee7b2cc"`` |
| `rule` | ``"javascript:S7773"`` |
| `severity` | ``"MINOR"`` |
| `component` | ``"ISY1102-Prueba:BACKEND/src/routes/contracts.js"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``244`` |
| `hash` | ``"32f99d69357c4766bf939de5fb9d307b"`` |
| `textRange.startLine` | ``244`` |
| `textRange.endLine` | ``244`` |
| `textRange.startOffset` | ``28`` |
| `textRange.endOffset` | ``36`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"2min"`` |
| `debt` | ``"2min"`` |
| `author` | ``""`` |
| `tags` | ``["convention", "es2015", "editable-source"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"CODE_SMELL"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``true`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"CONVENTIONAL"`` |
| `cleanCodeAttributeCategory` | ``"CONSISTENT"`` |
| `impacts` | ``[{"softwareQuality": "RELIABILITY", "severity": "MEDIUM"}, {"softwareQuality": "MAINTAINABILITY", "severity": "LOW"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.10 Hallazgo 10 de 25

**Regla:** `javascript:S7773` · **Severidad:** `MINOR` · **Tipo:** `CODE_SMELL`

**`message` · Descripción original**

> Prefer `Number.parseInt` over `parseInt`.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"6e2bf94d-51ee-489f-b240-99ef928909fe"`` |
| `rule` | ``"javascript:S7773"`` |
| `severity` | ``"MINOR"`` |
| `component` | ``"ISY1102-Prueba:BACKEND/src/routes/contracts.js"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``256`` |
| `hash` | ``"5029baf5851d739aa796e02f805b4ace"`` |
| `textRange.startLine` | ``256`` |
| `textRange.endLine` | ``256`` |
| `textRange.startOffset` | ``28`` |
| `textRange.endOffset` | ``36`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"2min"`` |
| `debt` | ``"2min"`` |
| `author` | ``""`` |
| `tags` | ``["convention", "es2015", "editable-source"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"CODE_SMELL"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``true`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"CONVENTIONAL"`` |
| `cleanCodeAttributeCategory` | ``"CONSISTENT"`` |
| `impacts` | ``[{"softwareQuality": "RELIABILITY", "severity": "MEDIUM"}, {"softwareQuality": "MAINTAINABILITY", "severity": "LOW"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.11 Hallazgo 11 de 25

**Regla:** `javascript:S7773` · **Severidad:** `MINOR` · **Tipo:** `CODE_SMELL`

**`message` · Descripción original**

> Prefer `Number.parseInt` over `parseInt`.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"4774fa61-d27f-4980-b068-ae53b4a1c86d"`` |
| `rule` | ``"javascript:S7773"`` |
| `severity` | ``"MINOR"`` |
| `component` | ``"ISY1102-Prueba:BACKEND/src/routes/metricas.js"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``130`` |
| `hash` | ``"d55ab40cf16c0e074be1bcc12fd37172"`` |
| `textRange.startLine` | ``130`` |
| `textRange.endLine` | ``130`` |
| `textRange.startOffset` | ``26`` |
| `textRange.endOffset` | ``34`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"2min"`` |
| `debt` | ``"2min"`` |
| `author` | ``""`` |
| `tags` | ``["convention", "es2015", "editable-source"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"CODE_SMELL"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``true`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"CONVENTIONAL"`` |
| `cleanCodeAttributeCategory` | ``"CONSISTENT"`` |
| `impacts` | ``[{"softwareQuality": "RELIABILITY", "severity": "MEDIUM"}, {"softwareQuality": "MAINTAINABILITY", "severity": "LOW"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.12 Hallazgo 12 de 25

**Regla:** `javascript:S7773` · **Severidad:** `MINOR` · **Tipo:** `CODE_SMELL`

**`message` · Descripción original**

> Prefer `Number.parseInt` over `parseInt`.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"099af42c-dc0b-4cbc-bd7d-2e199d261c26"`` |
| `rule` | ``"javascript:S7773"`` |
| `severity` | ``"MINOR"`` |
| `component` | ``"ISY1102-Prueba:BACKEND/src/routes/metricas.js"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``137`` |
| `hash` | ``"7485c19d5ce5ceee7c92e86894f6e529"`` |
| `textRange.startLine` | ``137`` |
| `textRange.endLine` | ``137`` |
| `textRange.startOffset` | ``26`` |
| `textRange.endOffset` | ``34`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"2min"`` |
| `debt` | ``"2min"`` |
| `author` | ``""`` |
| `tags` | ``["convention", "es2015", "editable-source"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"CODE_SMELL"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``true`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"CONVENTIONAL"`` |
| `cleanCodeAttributeCategory` | ``"CONSISTENT"`` |
| `impacts` | ``[{"softwareQuality": "RELIABILITY", "severity": "MEDIUM"}, {"softwareQuality": "MAINTAINABILITY", "severity": "LOW"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.13 Hallazgo 13 de 25

**Regla:** `javascript:S7773` · **Severidad:** `MINOR` · **Tipo:** `CODE_SMELL`

**`message` · Descripción original**

> Prefer `Number.parseInt` over `parseInt`.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"1bf7d93a-5d29-4c4f-9c90-3cdf86f873f8"`` |
| `rule` | ``"javascript:S7773"`` |
| `severity` | ``"MINOR"`` |
| `component` | ``"ISY1102-Prueba:BACKEND/src/routes/metricas.js"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``149`` |
| `hash` | ``"32f99d69357c4766bf939de5fb9d307b"`` |
| `textRange.startLine` | ``149`` |
| `textRange.endLine` | ``149`` |
| `textRange.startOffset` | ``28`` |
| `textRange.endOffset` | ``36`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"2min"`` |
| `debt` | ``"2min"`` |
| `author` | ``""`` |
| `tags` | ``["convention", "es2015", "editable-source"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"CODE_SMELL"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``true`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"CONVENTIONAL"`` |
| `cleanCodeAttributeCategory` | ``"CONSISTENT"`` |
| `impacts` | ``[{"softwareQuality": "RELIABILITY", "severity": "MEDIUM"}, {"softwareQuality": "MAINTAINABILITY", "severity": "LOW"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.14 Hallazgo 14 de 25

**Regla:** `javascript:S7773` · **Severidad:** `MINOR` · **Tipo:** `CODE_SMELL`

**`message` · Descripción original**

> Prefer `Number.parseInt` over `parseInt`.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"cfb1435e-d139-49af-af44-e98d04d7deed"`` |
| `rule` | ``"javascript:S7773"`` |
| `severity` | ``"MINOR"`` |
| `component` | ``"ISY1102-Prueba:BACKEND/src/routes/metricas.js"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``161`` |
| `hash` | ``"5029baf5851d739aa796e02f805b4ace"`` |
| `textRange.startLine` | ``161`` |
| `textRange.endLine` | ``161`` |
| `textRange.startOffset` | ``28`` |
| `textRange.endOffset` | ``36`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"2min"`` |
| `debt` | ``"2min"`` |
| `author` | ``""`` |
| `tags` | ``["convention", "es2015", "editable-source"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"CODE_SMELL"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``true`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"CONVENTIONAL"`` |
| `cleanCodeAttributeCategory` | ``"CONSISTENT"`` |
| `impacts` | ``[{"softwareQuality": "RELIABILITY", "severity": "MEDIUM"}, {"softwareQuality": "MAINTAINABILITY", "severity": "LOW"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.15 Hallazgo 15 de 25

**Regla:** `docker:S6471` · **Severidad:** `MINOR` · **Tipo:** `VULNERABILITY`

**`message` · Descripción original**

> The "nginx" image runs with "root" as the default user. Make sure it is safe here.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"5b7b0b32-87c6-436e-a039-d77ce216e571"`` |
| `rule` | ``"docker:S6471"`` |
| `severity` | ``"MINOR"`` |
| `component` | ``"ISY1102-Prueba:FRONTEND/Dockerfile"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``34`` |
| `hash` | ``"ba1cfc103b0642f37c869e0148f67986"`` |
| `textRange.startLine` | ``34`` |
| `textRange.endLine` | ``34`` |
| `textRange.startOffset` | ``0`` |
| `textRange.endOffset` | ``17`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"15min"`` |
| `debt` | ``"15min"`` |
| `author` | ``""`` |
| `tags` | ``["cwe", "dockerfile", "former-hotspot"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"VULNERABILITY"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``false`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"COMPLETE"`` |
| `cleanCodeAttributeCategory` | ``"INTENTIONAL"`` |
| `impacts` | ``[{"softwareQuality": "SECURITY", "severity": "LOW"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.16 Hallazgo 16 de 25

**Regla:** `css:S4649` · **Severidad:** `MAJOR` · **Tipo:** `BUG`

**`message` · Descripción original**

> Missing generic font family

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"b8ca7a7d-4461-4ff0-a28d-cb4a7879034c"`` |
| `rule` | ``"css:S4649"`` |
| `severity` | ``"MAJOR"`` |
| `component` | ``"ISY1102-Prueba:FRONTEND/src/index.css"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``6`` |
| `hash` | ``"c8cb8ce7edf5c33230ddc4f8800c6688"`` |
| `textRange.startLine` | ``6`` |
| `textRange.endLine` | ``6`` |
| `textRange.startOffset` | ``35`` |
| `textRange.endOffset` | ``47`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"1min"`` |
| `debt` | ``"1min"`` |
| `author` | ``""`` |
| `tags` | ``[]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"BUG"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``false`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"COMPLETE"`` |
| `cleanCodeAttributeCategory` | ``"INTENTIONAL"`` |
| `impacts` | ``[{"softwareQuality": "RELIABILITY", "severity": "MEDIUM"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.17 Hallazgo 17 de 25

**Regla:** `javascript:S9383` · **Severidad:** `MAJOR` · **Tipo:** `BUG`

**`message` · Descripción original**

> Promises must be awaited, end with a call to .catch, end with a call to .then with a rejection handler or be explicitly marked as ignored with the `void` operator.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"42f03762-621a-43f7-9385-e17d45989666"`` |
| `rule` | ``"javascript:S9383"`` |
| `severity` | ``"MAJOR"`` |
| `component` | ``"ISY1102-Prueba:FRONTEND/src/pages/Home.jsx"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``77`` |
| `hash` | ``"4336c02c1f361cd9328fe1d81ffb7e79"`` |
| `textRange.startLine` | ``77`` |
| `textRange.endLine` | ``77`` |
| `textRange.startOffset` | ``4`` |
| `textRange.endOffset` | ``20`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"5min"`` |
| `debt` | ``"5min"`` |
| `author` | ``""`` |
| `tags` | ``["async", "es2017", "type-dependent", "promise"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"BUG"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``true`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"LOGICAL"`` |
| `cleanCodeAttributeCategory` | ``"INTENTIONAL"`` |
| `impacts` | ``[{"softwareQuality": "RELIABILITY", "severity": "MEDIUM"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.18 Hallazgo 18 de 25

**Regla:** `javascript:S9383` · **Severidad:** `MAJOR` · **Tipo:** `BUG`

**`message` · Descripción original**

> Promises must be awaited, end with a call to .catch, end with a call to .then with a rejection handler or be explicitly marked as ignored with the `void` operator.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"9056558a-a9ab-4df0-823b-804150861afe"`` |
| `rule` | ``"javascript:S9383"`` |
| `severity` | ``"MAJOR"`` |
| `component` | ``"ISY1102-Prueba:FRONTEND/src/pages/clientes/ClienteForm.jsx"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``63`` |
| `hash` | ``"6ecb85f8ecd2144fa75249f174f1d4d8"`` |
| `textRange.startLine` | ``63`` |
| `textRange.endLine` | ``100`` |
| `textRange.startOffset` | ``4`` |
| `textRange.endOffset` | ``9`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"5min"`` |
| `debt` | ``"5min"`` |
| `author` | ``""`` |
| `tags` | ``["async", "es2017", "type-dependent", "promise"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"BUG"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``true`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"LOGICAL"`` |
| `cleanCodeAttributeCategory` | ``"INTENTIONAL"`` |
| `impacts` | ``[{"softwareQuality": "RELIABILITY", "severity": "MEDIUM"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.19 Hallazgo 19 de 25

**Regla:** `javascript:S9383` · **Severidad:** `MAJOR` · **Tipo:** `BUG`

**`message` · Descripción original**

> Promises must be awaited, end with a call to .catch, end with a call to .then with a rejection handler or be explicitly marked as ignored with the `void` operator.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"2e5423d2-c0be-4810-8ed3-3128bb1423e2"`` |
| `rule` | ``"javascript:S9383"`` |
| `severity` | ``"MAJOR"`` |
| `component` | ``"ISY1102-Prueba:FRONTEND/src/pages/contratos/ContratoDetalle.jsx"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``21`` |
| `hash` | ``"eae67ff96afcbd0aa8348c6ac1503a8a"`` |
| `textRange.startLine` | ``21`` |
| `textRange.endLine` | ``21`` |
| `textRange.startOffset` | ``4`` |
| `textRange.endOffset` | ``11`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"5min"`` |
| `debt` | ``"5min"`` |
| `author` | ``""`` |
| `tags` | ``["async", "es2017", "type-dependent", "promise"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"BUG"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``true`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"LOGICAL"`` |
| `cleanCodeAttributeCategory` | ``"INTENTIONAL"`` |
| `impacts` | ``[{"softwareQuality": "RELIABILITY", "severity": "MEDIUM"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.20 Hallazgo 20 de 25

**Regla:** `javascript:S9383` · **Severidad:** `MAJOR` · **Tipo:** `BUG`

**`message` · Descripción original**

> Promises must be awaited, end with a call to .catch, end with a call to .then with a rejection handler or be explicitly marked as ignored with the `void` operator.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"ff880bd2-ee1b-4d3d-b404-883d817d283a"`` |
| `rule` | ``"javascript:S9383"`` |
| `severity` | ``"MAJOR"`` |
| `component` | ``"ISY1102-Prueba:FRONTEND/src/pages/contratos/ContratoForm.jsx"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``34`` |
| `hash` | ``"6ecb85f8ecd2144fa75249f174f1d4d8"`` |
| `textRange.startLine` | ``34`` |
| `textRange.endLine` | ``41`` |
| `textRange.startOffset` | ``4`` |
| `textRange.endOffset` | ``9`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"5min"`` |
| `debt` | ``"5min"`` |
| `author` | ``""`` |
| `tags` | ``["async", "es2017", "type-dependent", "promise"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"BUG"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``true`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"LOGICAL"`` |
| `cleanCodeAttributeCategory` | ``"INTENTIONAL"`` |
| `impacts` | ``[{"softwareQuality": "RELIABILITY", "severity": "MEDIUM"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.21 Hallazgo 21 de 25

**Regla:** `javascript:S9383` · **Severidad:** `MAJOR` · **Tipo:** `BUG`

**`message` · Descripción original**

> Promises must be awaited, end with a call to .catch, end with a call to .then with a rejection handler or be explicitly marked as ignored with the `void` operator.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"eff56949-809f-4425-84f9-5e0ab71e9e7e"`` |
| `rule` | ``"javascript:S9383"`` |
| `severity` | ``"MAJOR"`` |
| `component` | ``"ISY1102-Prueba:FRONTEND/src/pages/contratos/ContratoForm.jsx"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``46`` |
| `hash` | ``"6ecb85f8ecd2144fa75249f174f1d4d8"`` |
| `textRange.startLine` | ``46`` |
| `textRange.endLine` | ``59`` |
| `textRange.startOffset` | ``4`` |
| `textRange.endOffset` | ``9`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"5min"`` |
| `debt` | ``"5min"`` |
| `author` | ``""`` |
| `tags` | ``["async", "es2017", "type-dependent", "promise"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"BUG"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``true`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"LOGICAL"`` |
| `cleanCodeAttributeCategory` | ``"INTENTIONAL"`` |
| `impacts` | ``[{"softwareQuality": "RELIABILITY", "severity": "MEDIUM"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.22 Hallazgo 22 de 25

**Regla:** `javascript:S9383` · **Severidad:** `MAJOR` · **Tipo:** `BUG`

**`message` · Descripción original**

> Promises must be awaited, end with a call to .catch, end with a call to .then with a rejection handler or be explicitly marked as ignored with the `void` operator.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"c76489e2-36ef-4d46-a83c-f0be5046d2cc"`` |
| `rule` | ``"javascript:S9383"`` |
| `severity` | ``"MAJOR"`` |
| `component` | ``"ISY1102-Prueba:FRONTEND/src/pages/contratos/ContratosTabCreate.jsx"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``27`` |
| `hash` | ``"6ecb85f8ecd2144fa75249f174f1d4d8"`` |
| `textRange.startLine` | ``27`` |
| `textRange.endLine` | ``34`` |
| `textRange.startOffset` | ``4`` |
| `textRange.endOffset` | ``9`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"5min"`` |
| `debt` | ``"5min"`` |
| `author` | ``""`` |
| `tags` | ``["async", "es2017", "type-dependent", "promise"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"BUG"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``true`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"LOGICAL"`` |
| `cleanCodeAttributeCategory` | ``"INTENTIONAL"`` |
| `impacts` | ``[{"softwareQuality": "RELIABILITY", "severity": "MEDIUM"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.23 Hallazgo 23 de 25

**Regla:** `javascript:S9383` · **Severidad:** `MAJOR` · **Tipo:** `BUG`

**`message` · Descripción original**

> Promises must be awaited, end with a call to .catch, end with a call to .then with a rejection handler or be explicitly marked as ignored with the `void` operator.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"915642e8-d780-4d8c-96b0-8d147f3c1b1c"`` |
| `rule` | ``"javascript:S9383"`` |
| `severity` | ``"MAJOR"`` |
| `component` | ``"ISY1102-Prueba:FRONTEND/src/pages/empresas/EmpresaForm.jsx"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``33`` |
| `hash` | ``"3315912ab84c3b5268cf2c179c45c008"`` |
| `textRange.startLine` | ``33`` |
| `textRange.endLine` | ``45`` |
| `textRange.startOffset` | ``5`` |
| `textRange.endOffset` | ``8`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"5min"`` |
| `debt` | ``"5min"`` |
| `author` | ``""`` |
| `tags` | ``["async", "es2017", "type-dependent", "promise"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"BUG"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``true`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"LOGICAL"`` |
| `cleanCodeAttributeCategory` | ``"INTENTIONAL"`` |
| `impacts` | ``[{"softwareQuality": "RELIABILITY", "severity": "MEDIUM"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.24 Hallazgo 24 de 25

**Regla:** `javascript:S9383` · **Severidad:** `MAJOR` · **Tipo:** `BUG`

**`message` · Descripción original**

> Promises must be awaited, end with a call to .catch, end with a call to .then with a rejection handler or be explicitly marked as ignored with the `void` operator.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"c1a63a77-b868-442c-a637-1ae4346ef69e"`` |
| `rule` | ``"javascript:S9383"`` |
| `severity` | ``"MAJOR"`` |
| `component` | ``"ISY1102-Prueba:FRONTEND/src/pages/empresas/EmpresasList.jsx"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``50`` |
| `hash` | ``"9bb4b71e94b92dd4c8d9123479c28114"`` |
| `textRange.startLine` | ``50`` |
| `textRange.endLine` | ``50`` |
| `textRange.startOffset` | ``4`` |
| `textRange.endOffset` | ``10`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"5min"`` |
| `debt` | ``"5min"`` |
| `author` | ``""`` |
| `tags` | ``["async", "es2017", "type-dependent", "promise"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"BUG"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``true`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"LOGICAL"`` |
| `cleanCodeAttributeCategory` | ``"INTENTIONAL"`` |
| `impacts` | ``[{"softwareQuality": "RELIABILITY", "severity": "MEDIUM"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |

---

### 3.25 Hallazgo 25 de 25

**Regla:** `javascript:S9383` · **Severidad:** `MAJOR` · **Tipo:** `BUG`

**`message` · Descripción original**

> Promises must be awaited, end with a call to .catch, end with a call to .then with a rejection handler or be explicitly marked as ignored with the `void` operator.

**Registro completo · nombres y valores del JSON original**

#### Identificación, archivo y ubicación

| Campo | Valor original |
| --- | --- |
| `key` | ``"5764b985-135f-4698-9b59-61ec606a5c15"`` |
| `rule` | ``"javascript:S9383"`` |
| `severity` | ``"MAJOR"`` |
| `component` | ``"ISY1102-Prueba:FRONTEND/src/pages/usuarios/UsuarioForm.jsx"`` |
| `project` | ``"ISY1102-Prueba"`` |
| `line` | ``36`` |
| `hash` | ``"6ecb85f8ecd2144fa75249f174f1d4d8"`` |
| `textRange.startLine` | ``36`` |
| `textRange.endLine` | ``46`` |
| `textRange.startOffset` | ``4`` |
| `textRange.endOffset` | ``9`` |

#### Estado, esfuerzo y trazabilidad

| Campo | Valor original |
| --- | --- |
| `flows` | ``[]`` |
| `status` | ``"OPEN"`` |
| `effort` | ``"5min"`` |
| `debt` | ``"5min"`` |
| `author` | ``""`` |
| `tags` | ``["async", "es2017", "type-dependent", "promise"]`` |
| `creationDate` | ``"2026-10-13T20:23:06-0300"`` |
| `updateDate` | ``"2026-10-13T20:23:06-0300"`` |
| `type` | ``"BUG"`` |
| `scope` | ``"MAIN"`` |
| `quickFixAvailable` | ``true`` |
| `messageFormattings` | ``[]`` |
| `codeVariants` | ``[]`` |
| `cleanCodeAttribute` | ``"LOGICAL"`` |
| `cleanCodeAttributeCategory` | ``"INTENTIONAL"`` |
| `impacts` | ``[{"softwareQuality": "RELIABILITY", "severity": "MEDIUM"}]`` |
| `issueStatus` | ``"OPEN"`` |
| `prioritizedRule` | ``false`` |
| `fromSonarQubeUpdate` | ``false`` |
| `internalTags` | ``[]`` |
| `linkedTicketStatus` | ``"NOT_LINKED"`` |
