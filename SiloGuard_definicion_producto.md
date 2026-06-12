# SiloGuard — Definición de Producto
> Documento de referencia pre-diseño · Basado en MVP + sesión de refinamiento

---

## Decisiones de base

| Parámetro | Decisión |
|---|---|
| Roles de usuario | Solo productor |
| Acción de aireación | Recomendación manual (sin control IoT remoto) |
| Cantidad de silos | Variable — se soportan todos los casos |
| Pasaporte de Calidad | Mapeado pero no prioritario en MVP |
| Sin conexión | Muestra último dato conocido + aviso de estado offline |
| Niveles de alerta | Crítica / Advertencia |
| Autenticación | Email + contraseña · Google login · Apple login |
| Tutorial onboarding | Obligatorio (no se puede saltear) |
| Plataforma | iOS + Android |

---

## Funcionalidades

### Autenticación y sesión
- Login con email/contraseña, Google y Apple
- Registro de cuenta con datos del productor y su establecimiento
- Verificación de email post-registro
- Recuperación de contraseña por email
- Cierre de sesión desde perfil

### Onboarding
- Solicitud de permisos de notificaciones push (pantalla dedicada)
- Vinculación de lanza IoT por escaneo QR + configuración WiFi + asignación de nombre al silo
- Tutorial walkthrough obligatorio (3–4 pasos) en el primer ingreso, explicando las secciones principales

### Monitoreo de silos
- Dashboard multi-silo: lista de todos los silos del establecimiento con estado resumido (verde / amarillo / rojo)
- Score general del silo (1–100) calculado por IA en base a los tres sensores
- Lectura en tiempo real de CO₂, temperatura y humedad por silo
- Historial gráfico (líneas) de las últimas 48–72 hs, con selector de variable (CO₂ / temp / humedad)
- Estado offline: banner visible con fecha/hora del último dato conocido cuando no hay conexión

### Sistema de alertas
- Notificación push inmediata al detectar anomalía, diferenciada visualmente por nivel (Crítica / Advertencia)
- Deep link desde la notificación directo a la pantalla de detalle de esa alerta
- Descripción de la alerta en lenguaje simple: qué está pasando, qué zona del silo está afectada, horas estimadas antes de pérdida irreversible
- Acción recomendada contextual (encender aireación / realizar inspección presencial / contactar técnico)
- Confirmación de resolución: el productor registra que actuó y puede agregar una nota opcional
- Lista de alertas filtrable: Todas / Críticas / Advertencias / Resueltas
- Historial de alertas de la temporada con estado de resolución

### Gestión de silos
- Agregar nuevo silo desde el dashboard (vincula una nueva lanza)
- Editar nombre de un silo existente
- Eliminar silo con confirmación

### Configuración
- Configuración de umbrales personalizados por silo (límites de CO₂, temperatura y humedad)
- Silencio de notificaciones nocturnas (rango horario configurable)
- Perfil del usuario: nombre, datos del establecimiento, email

### Pasaporte de Calidad *(futuro — mapeado)*
- Lista de lotes de la temporada con estado y días monitoreados
- Detalle del lote: score histórico, gráfico de evolución, código QR verificable para compartir con bancos o compradores

---

## Pantallas — 23 en total

### Bloque 1 — Autenticación (6 pantallas)

| # | Nombre | Descripción |
|---|---|---|
| 1 | **Splash Screen** | Pantalla inicial con logo y animación de carga mientras se inicializa la app. |
| 2 | **Welcome** | Pantalla de bienvenida con la propuesta de valor de SiloGuard (1–2 slides o pantalla estática) y los CTAs: "Iniciar sesión" / "Registrarme". |
| 3 | **Login** | Formulario de email + contraseña. Opciones de ingreso con Google y Apple. Link a "Olvidé mi contraseña". |
| 4 | **Registro** | Formulario de creación de cuenta: nombre, establecimiento, email, contraseña. |
| 5 | **Verificación de email** | Pantalla de espera post-registro indicando que se envió un email de verificación. Botón para reenviar. |
| 6 | **Recuperar contraseña** | Ingreso del email registrado para recibir el link de reset. Confirmación de envío. |

---

### Bloque 2 — Onboarding post-registro (3 pantallas)

| # | Nombre | Descripción |
|---|---|---|
| 7 | **Solicitud de permisos** | Pantalla que explica por qué son necesarias las notificaciones push antes de lanzar el diálogo del sistema operativo. |
| 8 | **Vincular Lanza IoT** | Flujo de vinculación del dispositivo: (1) escaneo del QR de la lanza, (2) conexión WiFi, (3) asignación de nombre al silo. |
| 9 | **Tutorial walkthrough** | Overlay obligatorio de 3–4 pasos que muestra las secciones principales de la app (Dashboard, Alertas, Historial). No se puede cerrar hasta completarlo. |

---

### Bloque 3 — Core: silos y monitoreo (3 pantallas)

| # | Nombre | Descripción |
|---|---|---|
| 10 | **Dashboard / Lista de silos** | Vista principal post-login. Lista de todos los silos del establecimiento, cada uno con nombre, indicador de estado (verde / amarillo / rojo) y valores resumidos. Botón para agregar nuevo silo. |
| 11 | **Detalle del silo** | Score general (1–100), valores actuales de CO₂, temperatura y humedad, indicador visual de estado. Muestra banner de "Sin conexión — último dato: fecha/hora" cuando corresponde. |
| 12 | **Historial de sensores** | Gráfico de líneas de las últimas 48–72 hs. Selector de variable (CO₂ / temperatura / humedad). Permite ver la tendencia después de una acción correctiva. |

---

### Bloque 4 — Alertas (3 pantallas)

| # | Nombre | Descripción |
|---|---|---|
| 13 | **Lista de alertas** | Listado cronológico de alertas de la temporada. Filtros: Todas / Críticas / Advertencias / Resueltas. Cada ítem muestra nivel, silo afectado, fecha y estado. |
| 14 | **Detalle de alerta** | Descripción en lenguaje simple de qué está pasando, qué zona está en riesgo, horas estimadas antes de pérdida irreversible, y la acción recomendada (encender aireación / inspección presencial / llamar técnico). |
| 15 | **Confirmación de resolución** | Pantalla o modal que el productor completa al marcar la alerta como resuelta. Campo opcional para nota de lo que hizo. |

---

### Bloque 5 — Gestión de silos (2 pantallas)

| # | Nombre | Descripción |
|---|---|---|
| 16 | **Agregar silo** | Reutiliza el flujo de la pantalla 8 pero accesible desde el Dashboard. Permite vincular una nueva lanza al establecimiento. |
| 17 | **Editar / Eliminar silo** | Permite renombrar el silo o eliminarlo. Confirmación de eliminación con advertencia de pérdida de historial. |

---

### Bloque 6 — Configuración y perfil (3 pantallas)

| # | Nombre | Descripción |
|---|---|---|
| 18 | **Mi perfil** | Nombre del productor, datos del establecimiento, email vinculado. Botón de cerrar sesión. |
| 19 | **Configuración de umbrales** | Personalización de los límites de alerta por silo: CO₂, temperatura y humedad. Selector del silo al que aplica cada configuración. |
| 20 | **Configuración general** | Preferencias de notificaciones: activar/desactivar tipos de alerta, configurar rango horario de silencio nocturno. |

---

### Bloque 7 — Pasaporte de Calidad *(futuro — mapeado)* (2 pantallas)

| # | Nombre | Descripción |
|---|---|---|
| 21 | **Lista de lotes** | Todos los lotes almacenados de la temporada con nombre, silo, score promedio y días monitoreados. |
| 22 | **Detalle del lote / Pasaporte** | Score histórico del lote, gráfico de evolución de la temporada, días bajo monitoreo continuo y código QR verificable para compartir. |

---

### Bloque 8 — Estado especial (1 pantalla)

| # | Nombre | Descripción |
|---|---|---|
| 23 | **Sin conexión / Error de dispositivo** | Pantalla o estado global que informa que la lanza no responde o que no hay conectividad. Muestra el último dato conocido con su timestamp y sugiere acciones (verificar WiFi del silo, revisar lanza físicamente). |

---

## Flows

---

### Flow 1 — Usuario nuevo: primer uso completo

```
Descarga la app
    → Splash Screen [1]
    → Welcome [2]
    → Registro [4]
    → Verificación de email [5]
    → Solicitud de permisos push [7]
    → Vincular Lanza IoT [8]
    → Tutorial walkthrough (obligatorio) [9]
    → Dashboard / Lista de silos [10]   ← primera acción: revisa el estado del silo
```

---

### Flow 2 — Usuario recurrente: ingreso diario

```
Abre la app
    → Splash Screen [1]
    → Login [3]  (email / Google / Apple)
    → Dashboard / Lista de silos [10]
        → Detalle del silo [11]         ← todo OK: cierra la app
        → Historial de sensores [12]    ← si quiere ver la tendencia
```

---

### Flow 3 — Recuperar contraseña

```
Login [3]
    → "Olvidé mi contraseña"
    → Recuperar contraseña [6]
    → (Email enviado al usuario)
    → El usuario sigue el link externo → setea nueva contraseña
    → Login [3]
    → Dashboard [10]
```

---

### Flow 4 — Task flow crítico: responder una alerta

```
Recibe notificación push (Crítica o Advertencia)
    → Toca la notificación
    → Detalle de alerta [14]  (deep link directo)
        → Lee: causa · zona · horas estimadas · acción recomendada

        ¿Necesita verificar los valores antes de actuar?
        ├── Sí → Detalle del silo [11] → Historial de sensores [12]
        │         └── Vuelve a Detalle de alerta [14]
        └── No → continúa

    → Ejecuta la acción en el campo (manualmente)
    → Confirmación de resolución [15]  (marca como resuelta + nota opcional)
    → Historial de sensores [12]  ← verifica que los valores bajan
    → Alerta resuelta ✓
```

---

### Flow 5 — Task flow diario: revisión rápida del estado

```
Abre la app
    → Dashboard / Lista de silos [10]
        → Ve el indicador de color de cada silo (verde / amarillo / rojo)

        ¿Algún silo en amarillo o rojo?
        ├── No → cierra la app ✓
        └── Sí → Detalle del silo [11]
                    → Historial de sensores [12]
                    → Si hay alerta activa → Lista de alertas [13] → Detalle [14]
```

---

### Flow 6 — Agregar un nuevo silo

```
Dashboard [10]
    → Botón "+" / Agregar silo
    → Agregar silo [16]  (flujo de 3 pasos)
        → Paso 1: Escanear QR de la nueva lanza
        → Paso 2: Conectar la lanza a la red WiFi
        → Paso 3: Asignar nombre al silo
    → Dashboard [10]  ← silo nuevo aparece en la lista
```

---

### Flow 7 — Configurar umbrales de alerta

```
Dashboard [10]
    → Menú / Perfil
    → Configuración de umbrales [19]
    → Selecciona silo
    → Ajusta límites de CO₂, temperatura y humedad
    → Guarda cambios
    → Vuelve al Dashboard [10]
```

---

### Flow 8 — Pasaporte de Calidad *(futuro)*

```
Dashboard [10]
    → Sección "Calidad"
    → Lista de lotes [21]
    → Detalle del lote [22]
    → Comparte QR verificable con banco o comprador
```

---

## Resumen de pantallas

| Bloque | Pantallas | Cantidad |
|---|---|---|
| Autenticación | 1 · 2 · 3 · 4 · 5 · 6 | 6 |
| Onboarding | 7 · 8 · 9 | 3 |
| Silos y monitoreo | 10 · 11 · 12 | 3 |
| Alertas | 13 · 14 · 15 | 3 |
| Gestión de silos | 16 · 17 | 2 |
| Configuración y perfil | 18 · 19 · 20 | 3 |
| Pasaporte de Calidad (futuro) | 21 · 22 | 2 |
| Estado especial | 23 | 1 |
| **Total** | | **23** |
