# SiloGuard MVP

**SiloGuard** es una aplicación móvil de monitoreo inteligente diseñada para productores agropecuarios. Su funcionamiento se apoya en una lanza con sensores integrados que se clava directamente sobre el silo o silobolsa, midiendo en tiempo real los parámetros que determinan la salud del grano: temperatura, humedad y niveles de CO₂. Esos datos se transmiten de forma continua a través de WiFi hacia la aplicación, donde una inteligencia artificial los analiza para detectar condiciones anómalas como fermentación, calentamiento o inicio de pudrición.

Cuando alguno de esos indicadores supera los límites aceptables, SiloGuard genera automáticamente una alerta en el celular del productor, con al menos 48 horas de anticipación antes de que el deterioro del grano se vuelva irreversible. Esto elimina la necesidad de abrir el silo o depender de inspecciones presenciales que suelen llegar demasiado tarde.

Además de recibir alertas, el productor puede tomar acciones correctivas directamente desde la aplicación, permitiendo intervenir a tiempo y evitar pérdidas significativas en la cosecha almacenada.

**Funcionalidades incluidas:**

|  | Funcionalidad | Justificación |
| ----- | ----- | ----- |
| 1 | **Pantalla principal — Estado del Silo:** Pantalla de home de la app mobile que muestra el score general del silo (1–100), los valores actuales de CO₂, temperatura y humedad, y un indicador visual de estado (verde / amarillo / rojo). El productor ve de un vistazo si su grano está bien o en riesgo.  | Es la pantalla que el productor abre todos los días. Construye el hábito de consulta y genera confianza progresiva en el sistema antes de que llegue la primera alerta real.  |
| 2 | **Pantalla de Alerta — Detalle y Acción Recomendada:** Cuando la IA detecta un patrón de fermentación, el productor recibe una notificación push. Al tocarla, accede a una pantalla con una descripción en lenguaje simple de qué está pasando, qué zona del silo está en riesgo, cuántas horas estimadas quedan antes de pérdida irreversible y una acción concreta recomendada   | Es el núcleo de la hipótesis. Si el productor no entiende la alerta o no sabe qué hacer con ella, no actúa.  |
| 3 | **Pantalla de Historial — Evolución de Sensores:** Gráfico de línea que muestra la evolución de CO₂, temperatura y humedad durante las últimas 48–72 horas. El productor puede ver si los valores están subiendo, estables o bajando después de haber tomado una acción.  | Si el productor encendió la aireación, necesita ver que los valores mejoran para confirmar que su acción funcionó. Sin esta pantalla, actúa a ciegas y no desarrolla confianza en el sistema. |

**Otras Funcionalidades :**

* **Pantalla de Onboarding y vinculación del dispositivo:** flujo de registro del productor y configuración de la lanza IoT desde la app (escaneo QR, conexión WiFi, nombre del silo).   
* **Pantalla de gestión multi-silo:** vista con listado de todos los silos del establecimiento, cada uno con su estado resumido, para productores con más de un punto de almacenamiento.   
* **Pantalla de configuración de alertas:** permite al productor personalizar los umbrales que disparan una alerta (por ejemplo, subir el límite de CO₂ o silenciar notificaciones nocturnas).   
* **Pantalla de Pasaporte de Calidad:** vista del certificado digital del lote con score histórico, días monitoreados y código QR verificable para compartir con bancos o compradores.   
* **Pantalla de historial de alertas de la temporada:** listado cronológico de todas las alertas recibidas durante la campaña, con estado de resolución y grano estimado salvado en cada episodio.   
* **Resumen semanal automático por notificación push:** notificación programada cada lunes con un resumen del estado del silo durante la semana anterior (promedio de valores, tendencia, grano en buen estado).   
* **Pantalla de pronóstico integrado:** vista que combina los datos del silo con el pronóstico meteorológico de los próximos 3 días para anticipar si las condiciones externas van a aumentar el riesgo interno.   
* **Contacto directo con técnico desde la app:** botón o chat dentro de la pantalla de alerta que conecta al productor con un agrónomo o técnico de SiloGuard en tiempo real.

### **Listado de 20 funcionalidades de SiloGuard**

1. **Splash screen** — pantalla inicial con logo mientras carga la app  
2. **Login** — ingreso con email/usuario y contraseña  
3. **Registro** — creación de cuenta del productor (datos del establecimiento)  
4. **Onboarding / vinculación de lanza IoT** — escaneo QR \+ conexión WiFi \+ nombre del silo  
5. **Dashboard / Estado de los silos** — vista resumen con todos los silos del establecimiento  
6. **Detalle del Silo** — score (1-100), valores actuales de CO₂, temperatura y humedad  
7. **Historial de sensores** — gráfico de evolución de las últimas 48-72 hs por variable  
8. **Notificación push de alerta** — aviso inmediato al celular cuando se detecta anomalía  
9. **Lista de Alertas** — listado filtrable por estado (todas / críticas / resueltas)  
10. **Detalle de Alerta** — descripción en lenguaje simple \+ zona afectada \+ tiempo estimado antes de pérdida irreversible  
11. **Acción recomendada** — CTA concreto dentro de la alerta (encender aireación / llamar técnico / inspección)  
12. **Marcar alerta como resuelta** — registrar que el productor actuó  
13. **Configuración de umbrales de alerta** — personalizar límites de CO₂, temperatura, humedad  
14. **Pasaporte de Calidad del lote** — certificado digital con score histórico y código QR verificable  
15. **Lista de Lotes** — vista de todos los lotes almacenados de la temporada  
16. **Resumen semanal automático** — notificación push de los lunes con el estado de la semana anterior  
17. **Pronóstico meteorológico integrado** — clima de los próximos 3 días cruzado con el riesgo interno del silo  
18. **Contacto directo con técnico/agrónomo** — chat o llamada desde la app  
19. **Mi Perfil \+ Configuración** — datos del usuario, establecimiento, preferencias de notificación y cierre de sesión






