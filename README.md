# Less

**Less** es un prototipo de asistente personal minimalista para iPhone pensado para reducir la cantidad de decisiones, organización y mantenimiento que una persona tiene que hacer.

La idea central es simple:

> **Vos hablás. Less organiza.**

En lugar de obligarte a decidir si algo es una tarea, evento, hábito, nota o recordatorio, Less intenta interpretarlo y mostrarlo en el lugar correcto.

---

## Estado actual

**Versión:** V14  
**Plataforma actual:** Web App / GitHub Pages, optimizada para iPhone  
**Persistencia:** `localStorage` del navegador  
**Modo visual:** Dark Mode  
**IA real:** todavía no conectada; `Decímelo` utiliza interpretación local de prototipo.

Esta versión es deliberadamente un prototipo de UX. La prioridad actual es descubrir **cómo debería sentirse Less** antes de convertirlo en una aplicación iOS nativa.

---

# 1. Concepto

Less no pretende ser otro Notion, otro gestor de tareas o un calendario más.

El objetivo es reducir:

- decisiones
- formularios
- clasificación manual
- navegación
- información innecesaria
- mantenimiento de listas

La pantalla principal debería responder rápidamente:

> **¿Qué necesito saber o hacer ahora?**

Y dejar el resto disponible solamente cuando el usuario lo necesite.

---

# 2. Estructura actual

La pantalla principal está organizada en contenedores visuales independientes.

## 🌱 Para Ser

Representa una intención personal para el día.

El usuario puede personalizar:

- emoticón
- nombre de la sección
- título
- descripción

Ejemplo:

**🌱 Para Ser**

> Ser paciente antes de responder.

> Una sola intención para hoy.

---

## ✝️ Para Recordar

Representa una idea, pensamiento, versículo o recordatorio que el usuario quiere tener presente.

También es completamente personalizable:

- emoticón
- nombre de la sección
- título
- descripción

Ejemplo:

**✝️ Para Recordar**

> Todo lo que hagan, háganlo de corazón.

> Colosenses 3:23

La intención es que estas dos primeras secciones sean configurables por el usuario y puedan evolucionar más adelante hacia contenido automático.

---

# 3. 📅 Agenda

Agenda es el centro de información temporal de Less.

Tiene dos tabs:

### Hoy

Muestra solamente lo relevante para el día actual.

La filosofía es:

> **Si no necesito saberlo hoy, no me lo muestres hoy.**

Esto evita que la pantalla principal se convierta en una lista interminable.

### Semana

Permite consultar los próximos días.

Los días aparecen con el nombre comenzando en mayúscula:

- Lunes
- Martes
- Miércoles
- Jueves
- Viernes
- Sábado
- Domingo

El cambio entre Hoy y Semana ocurre dentro del mismo contenedor mediante tabs.

---

# 4. Decímelo

Esta es una de las partes centrales de Less.

En lugar de completar formularios, el usuario escribe o habla naturalmente.

Ejemplo:

> El jueves cuando salga del trabajo tengo que comprar pañales y café porque el viernes vienen mis suegros.

Less intenta interpretar:

**Tarea**

Comprar pañales y café

**Cuándo**
Jueves

**Momento**
Al salir del trabajo

**Contexto**
Porque vienen los suegros el viernes

Otros ejemplos:

> Quiero volver a leer antes de dormir.

→ **Hábito**

> El sábado tenemos un cumpleaños.

→ **Evento**

> Quiero acordarme de disfrutar más el tiempo con las chicas.

→ **Memoria / intención**

La meta final es que el usuario no tenga que pensar:

> "¿Esto lo guardo como tarea, evento, nota o hábito?"

Less debería decidirlo.

---

# 5. Interpretación actual

La versión V14 todavía utiliza reglas locales para interpretar el texto.

Esto significa que reconoce ciertos patrones y palabras.

**No es todavía IA real.**

Esto es intencional: primero estamos validando la experiencia y el modelo mental de la aplicación.

El próximo salto importante será reemplazar esta interpretación por un sistema de IA real mediante un backend seguro.

### Importante

No se debe colocar una API key de un proveedor de IA directamente dentro de `index.html`.

La futura arquitectura debería ser:

```text
iPhone
   ↓
Less
   ↓
Backend seguro
   ↓
Modelo de IA
   ↓
Respuesta estructurada
   ↓
Less
```

---

# 6. Tipos de información

Less actualmente contempla cuatro grandes tipos:

| Tipo | Propósito |
|---|---|
| Tarea | Algo concreto que hay que hacer |
| Evento | Algo que ocurre en una fecha/momento |
| Hábito | Algo que queremos incorporar |
| Memoria | Algo que queremos conservar o recordar |

La clasificación debe ser invisible o casi invisible para el usuario.

El usuario simplemente habla.

---

# 7. Calendario

Less incorpora una acción de calendario para elementos que tienen una fecha.

La intención es poder pasar información de Less al calendario del iPhone sin tener que volver a escribirla.

El modelo conceptual separa:

### Cuándo ocurre

Ejemplo:

> Jueves después del trabajo.

de:

### Cuándo quiero que Less me avise

Ejemplo:

> Miércoles 09:00.

Esto es importante porque **la fecha de la tarea y la fecha del recordatorio no necesariamente son iguales**.

---

# 8. Avisarme

La interfaz de aviso utiliza selección de:

- fecha
- hora

en lugar de pedir al usuario que escriba manualmente una fecha.

La experiencia buscada es:

**🔔 Avisarme**

→ elegir fecha  
→ elegir hora  
→ guardar

Sin formularios innecesarios.

La notificación real del sistema iOS todavía es parte del roadmap.

---

# 9. Principios de UX

Estos principios deberían mantenerse durante todo el desarrollo.

## 1. Menos decisiones

No preguntarle al usuario algo que Less puede decidir.

## 2. Mostrar solamente lo necesario

La información futura no debe ocupar espacio en Hoy.

## 3. Entrada natural

El usuario debería poder escribir como habla.

## 4. No convertir todo en tareas

Una intención personal, reflexión o contexto no necesariamente es una tarea.

## 5. Contexto bajo demanda

El contexto debe estar disponible cuando sea útil, pero no llenar la pantalla.

## 6. Una interfaz tranquila

Less no debería sentirse como un dashboard lleno de widgets.

---

# 10. Diseño visual

La interfaz actual utiliza:

- Dark Mode
- tarjetas redondeadas
- jerarquía tipográfica simple
- espacios generosos
- pocos elementos visuales
- emojis únicamente cuando ayudan a identificar una sección

Se está evitando especialmente:

- emojis repetidos
- títulos demasiado grandes
- demasiados niveles de información
- botones innecesarios
- explicaciones permanentes

---

# 11. Persistencia

Actualmente los datos se guardan mediante:

```text
localStorage
```

Esto permite que el prototipo mantenga información después de recargar la página en el mismo navegador.

Todavía no existe:

- cuenta de usuario
- sincronización entre dispositivos
- base de datos
- iCloud
- backend

Esto será necesario para una versión real de producción.

---

# 12. Cómo actualizar la versión de GitHub Pages

Actualmente Less se está probando mediante GitHub Pages.

Para actualizar:

1. Descargar el ZIP de la versión.
2. Extraerlo.
3. Entrar al repositorio de Less.
4. Reemplazar `index.html`.
5. Hacer **Commit changes**.
6. Esperar unos segundos.
7. Recargar Less en Safari.

Actualmente el archivo principal de la aplicación es:

```text
index.html
```

---

# 13. Historial de versiones

## V01 — MVP inicial

Primer concepto de Less.

Incluyó:

- pantalla principal
- tareas
- intención del día
- primeras secciones personales
- primer concepto de "Decímelo"

---

## V02 — Decímelo

Primer intento de interpretar lenguaje natural.

Se introdujo la idea de:

- acción
- fecha
- contexto

---

## V03 — Interpretación mejorada

Se mejoró la presentación de la interpretación.

Comenzó a extraer:

- fecha
- momento
- persona
- lugar
- contexto

---

## V04 — Clasificación

Se introdujeron los cuatro conceptos:

- Tarea
- Evento
- Hábito
- Memoria

También se mejoró la presentación del resultado.

---

## V05 — Persistencia de categorías

Se agregó almacenamiento de:

- tareas
- eventos
- hábitos
- memorias

Las categorías dejaron de ser solamente una interpretación visual.

---

## V06 — Calendario y avisos

Se comenzó a incorporar:

- fechas
- calendario
- avisos
- separación entre información del día y futura

---

## V07 — Selector de fecha/hora

Se reemplazó el ingreso manual de avisos por controles de fecha y hora.

La intención fue acercar la interacción a una experiencia nativa de iPhone.

---

## V08 — Vista semanal

Se mejoró la navegación temporal:

- Hoy
- otros días
- semana

La información futura dejó de mezclarse con la pantalla principal.

---

## V09 — Dark Mode

Se incorporó una interfaz completamente oscura.

---

## V10 — Agenda

Se consolidó la navegación temporal en una única sección de Agenda.

Se buscó evitar mostrar simultáneamente:

- Hoy
- Semana

como bloques independientes.

---

## V11 — Tabs

Se reemplazó el cambio anterior por tabs:

**Hoy | Semana**

La Agenda pasó a funcionar como un único contenedor.

También se redujo la repetición de emojis.

---

## V12 — Personalización

Se agregó personalización de:

- Para Ser
- Para Recordar

Además:

- los títulos se hicieron más compactos
- Decímelo pasó a priorizar el campo de entrada y el botón
- la explicación quedó debajo de la acción principal

---

## V13 — Ajustes visuales

Se refinó:

- tamaño de títulos
- tamaño de descripciones
- tamaño de iconos
- jerarquía tipográfica
- espacio entre elementos

También se cambió el saludo para que funcione durante todo el día.

---

## V15 — Agenda por día

Refinamiento visual:
- Agenda usa exactamente la misma escala de encabezado que las secciones Para Ser / Para Recordar.
- En Semana, cada día se presenta dentro de su propio contenedor.
- Dentro de cada día, **Para Hacer** y **Para Incorporar** quedan agrupados en contenedores internos.

---

## V14 — Dark Clean

Versión actual.

Cambios principales:

- títulos y descripciones superiores más compactos
- Agenda alineada visualmente con las demás secciones
- mayor espacio entre el campo de Decímelo y su botón
- eliminación de la sección final innecesaria
- mantenimiento de Dark Mode
- mantenimiento de tabs Hoy/Semana
- mantenimiento de personalización
- mantenimiento de calendario y avisos

---

# 14. Qué falta

La interfaz ya permite validar bastante bien el concepto, pero todavía faltan piezas importantes antes de considerarla una aplicación real.

### Alta prioridad

- IA real para Decímelo
- notificaciones reales de iOS
- persistencia robusta
- calendario real
- recurrencias
- edición de elementos
- eliminación de elementos
- búsqueda
- sincronización

### Después

- widgets de iOS
- Apple Watch
- Siri
- integración con Reminders
- integración profunda con Calendar
- sugerencias inteligentes
- aprendizaje de preferencias

---

# 15. La visión

Less no debería convertirse en:

> "Otro lugar donde tengo que organizar mi vida."

Debería convertirse en:

> **"El lugar donde le cuento a alguien lo que tengo en la cabeza y esa persona se ocupa de organizarlo."**

La experiencia ideal sería:

**Vos:**

> Mañana después de buscar a las chicas tengo que llamar al seguro porque quiero averiguar cuánto me sale renovar la póliza.

**Less:**

> Entendido.

**Llamar al seguro**

Mañana · Después de buscar a las chicas

🔔 ¿Querés que te avise?

Y listo.

Sin formulario.  
Sin tags.  
Sin carpetas.  
Sin decidir dónde guardarlo.

**Less se ocupa.**
