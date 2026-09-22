# Less — V19 Contact List

## Qué agrega esta versión

V19 mantiene la base de **Less V18 — Section Labels** y agrega una nueva sección personalizable para contactos.

### 📞 PARA CONTACTAR

- Nueva sección en forma de contenedor, siguiendo el mismo lenguaje visual de **Para Ser** y **Para Recordar**.
- Permite guardar una lista de personas.
- Cada persona tiene:
  - **Nombre**
  - **Motivo** por el que hay que contactarla
- Se pueden agregar varias personas.
- Cada contacto puede eliminarse individualmente.
- La lista se guarda localmente en el navegador mediante `localStorage`.
- El nombre de la sección y el emoticón también son editables.

## Persistencia

Los contactos se guardan junto con el estado de Less en `localStorage`, por lo que permanecen al cerrar y volver a abrir la aplicación en el mismo navegador/dispositivo.

## Diseño

Se conserva el sistema visual de V18:

- modo dark
- contenedores redondeados
- tipografía consistente
- etiquetas superiores en MAYÚSCULAS
- mismo tratamiento visual para las etiquetas de sección
- Agenda continúa usando el componente visual unificado de V18

## Archivo principal

- `index.html`

## Versión

**Less V19 — Contact List**
