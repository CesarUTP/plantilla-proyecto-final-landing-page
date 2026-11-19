# Guía paso a paso del Proyecto Final

Esta guía sigue el procedimiento del enunciado, parte por parte, con el número de cada tarea (T1.1 a T6.4). En cada una verás **qué se entrega** y **cómo hacerlo**.

- **No necesitas ser experto.** Cada parte tiene **videos de YouTube de apoyo** en [RECURSOS_DE_APOYO.md](RECURSOS_DE_APOYO.md), y puedes pedirle ayuda a una **inteligencia artificial** para entender comandos, errores y código. **El uso de la IA está permitido para acelerar el trabajo y para aprender; siempre se nombra dónde se usó** (en el pull request, en el README y en el informe).
- El informe en Word (Parte 6) tiene su propia guía: [GUIA_DEL_INFORME.md](GUIA_DEL_INFORME.md).
- Los nombres de los botones de GitHub aparecen en inglés, como los muestra la página.
- Donde dice `USUARIO` se escribe el usuario de GitHub, y donde dice `REPO`, el nombre del repositorio del grupo.
- **Nunca** se escribe una contraseña en un archivo del repositorio.

## Plan de días sugerido

El trabajo no puede hacerse en un solo día: los commits de cada integrante deben aparecer en **al menos 3 días distintos**.

| Momento | Qué hacer |
|---|---|
| Primeros días | Partes 1, 2 y 3 (equipo, repositorio y planificación). |
| Días intermedios | Parte 4 (construir la página con ramas y pull requests). Empezar al menos 10 días antes de la entrega. |
| Últimos días | Parte 5 (publicar, completar el README y verificar) y Parte 6 (informe en Word). Ir tomando las capturas del informe mientras se avanza. |

---

## Parte 1. Equipo, roles y acuerdos

**Videos de apoyo:** Git y GitHub desde cero (sección 1 de [RECURSOS_DE_APOYO.md](RECURSOS_DE_APOYO.md)).

### T1.1. Registrar a cada integrante
**Se entrega:** la tabla del equipo (nombre y usuario de GitHub).

1. Cada integrante crea su cuenta gratuita en [github.com](https://github.com) si todavía no tiene una. Cada quien usa **su propia cuenta**; no se comparte ninguna.
2. Recomendado: en GitHub, ir a **Settings, Emails** y activar **Keep my email addresses private** para no mostrar el correo personal.
3. Anotar los nombres y usuarios; se escribirán en el README (T2.4).

### T1.2. Asignar los roles
**Se entrega:** una tabla con el rol, la persona y de dos a tres responsabilidades.

Los cuatro roles son: **coordinador del repositorio** (administra colaboradores, revisa y fusiona), **contenido y textos**, **diseño visual** y **funcionalidad (código)**. Todos los roles incluyen aportes propios a la página, no solo gestión. La tabla va en el README, sección *Responsabilidades por rol*.

### T1.3. Redactar el acuerdo de equipo
**Se entrega:** el acuerdo, de máximo una página, en el README, sección *Acuerdo de equipo*.

Responder las cinco normas: cómo se nombran las ramas, cómo se escriben los mensajes de commit, quién revisa cada pull request, cada cuánto se revisan los issues y qué se hace ante un conflicto de fusión o si alguien no responde.

---

## Parte 2. Creación y configuración del repositorio

**Videos de apoyo:** secciones 1 y 2 de [RECURSOS_DE_APOYO.md](RECURSOS_DE_APOYO.md) (Git y GitHub desde cero; colaboradores y pull requests).

### T2.1. Crear el repositorio (lo hace el coordinador)
**Se entrega:** el repositorio creado, **público**, con README, licencia y `.gitignore`.

1. Abrir la plantilla y pulsar el botón verde **Use this template**, opción **Create a new repository**.
2. En **Owner** dejar la cuenta del coordinador. En **Repository name** escribir un nombre que incluya el tema y el número del grupo, por ejemplo `landing-tema-grupo3` (ejemplo ilustrativo).
3. Marcar **Public**. Debe ser público porque GitHub Pages gratuito lo exige.
4. No marcar **Include all branches**. Pulsar **Create repository**.

La plantilla ya trae el README, la licencia y el `.gitignore`, así que esta tarea queda cubierta.

### T2.2. Invitar a los colaboradores (lo hace el coordinador)
**Se entrega:** la lista de colaboradores con los cuatro integrantes.

1. En el repositorio: **Settings, Collaborators, Add people**.
2. Buscar a cada integrante por su usuario y pulsar **Add**.
3. Cada invitado abre el correo o la notificación de GitHub y **acepta la invitación**.
4. Verificar en **Settings, Collaborators** que los tres aparecen como colaboradores.

### T2.3. Proteger la rama main (lo hace el coordinador)
**Se entrega:** la regla de protección activa.

1. **Settings, Branches, Add branch protection rule** (en algunas cuentas aparece como **Settings, Rules, Rulesets**).
2. En **Branch name pattern** escribir `main`.
3. Marcar **Require a pull request before merging** y **Require approvals** con el valor **1**.
4. Marcar **Do not allow bypassing the above settings**, para que el coordinador también siga la regla.
5. Pulsar **Create**.

Recomendado: en **Settings, General, Pull Requests**, dejar activo solo **Allow merge commits** y desactivar *Allow squash merging* y *Allow rebase merging*. Así cada commit de cada integrante queda visible en el historial de `main`.

### T2.4. Primer commit de cada integrante (lo hacen los cuatro)
**Se entrega:** cuatro pull requests fusionados, uno por integrante.

**a) Instalar y configurar Git.** Instalar Git desde [git-scm.com](https://git-scm.com). Después, en una terminal, escribir con los datos de **tu** cuenta:

```bash
git config --global user.name "Nombre Apellido"
git config --global user.email "ID+USUARIO@users.noreply.github.com"
```

El correo debe ser el de tu cuenta de GitHub. Si activaste el correo privado, usa el que aparece en **Settings, Emails** con el formato `ID+USUARIO@users.noreply.github.com`. Si el correo no coincide, tus commits **no aparecerán a tu nombre** en el repositorio.

**b) Clonar el repositorio.**

```bash
git clone https://github.com/USUARIO-DEL-COORDINADOR/REPO.git
cd REPO
```

Al subir cambios por primera vez, Git abrirá una ventana del navegador para iniciar sesión en GitHub. GitHub ya no acepta contraseñas en la terminal.

**c) Crear tu rama y agregar tu fila al README.**

```bash
git switch -c feature/USUARIO-equipo
```

Abrir `README.md` con el editor, completar **tu fila** en la tabla *Equipo* (nombre, usuario y rol) y guardar.

```bash
git add README.md
git commit -m "Agregar integrante USUARIO al equipo"
git push -u origin feature/USUARIO-equipo
```

**d) Abrir el pull request.** En GitHub aparece un aviso amarillo con el botón **Compare & pull request**. Pulsarlo, completar la plantilla y pulsar **Create pull request**. Luego, un compañero lo revisa y lo aprueba (ver T4.3).

---

## Parte 3. Planificación de la landing page

**Videos de apoyo:** sección 4 de [RECURSOS_DE_APOYO.md](RECURSOS_DE_APOYO.md) (ver cómo se arma una landing page antes de decidir las secciones).

### T3.1. Elegir el tema
**Se entrega:** la descripción del tema, de tres a cinco líneas, en el README.

Puede ser un producto, servicio, evento o proyecto real o ficticio (por ejemplo, una herramienta colaborativa estudiada en el curso, una jornada académica o un emprendimiento estudiantil). **No uses datos personales reales de terceros.** La descripción dice qué se ofrece, a quién y qué acción se espera del visitante.

### T3.2. Definir las secciones mínimas
**Se entrega:** la lista de secciones.

La página lleva como mínimo:
1. Encabezado con el nombre y un botón de llamado a la acción.
2. Propuesta de valor.
3. Al menos tres características o servicios.
4. Una sección con el equipo.
5. Un pie con datos de contacto ficticios o institucionales.

### T3.3. Crear al menos 8 issues
**Se entrega:** los issues creados, cada uno con título claro y un responsable. Todos los integrantes deben tener issues asignados.

1. En el repositorio: **Issues, New issue**, y elegir la plantilla **Tarea del proyecto**.
2. Completar el título, la descripción y los criterios de aceptación.
3. En el panel derecho, en **Assignees**, elegir al responsable.

Lista sugerida (el grupo puede cambiarla):

| N.º | Issue sugerido | Rol que lo lidera |
|---|---|---|
| 1 | Encabezado con nombre y botón de llamado a la acción | Diseño visual |
| 2 | Sección de propuesta de valor | Contenido y textos |
| 3 | Sección de características o servicios (tres o más) | Contenido y textos |
| 4 | Sección del equipo | Cualquiera |
| 5 | Pie con datos de contacto | Funcionalidad (código) |
| 6 | Estilos generales: colores, tipografía y espaciado | Diseño visual |
| 7 | Adaptación a pantallas de celular | Funcionalidad (código) |
| 8 | Imágenes, texto alternativo y créditos | Diseño visual |
| 9 | Completar README, IA y créditos | Coordinador |
| 10 | Publicar con GitHub Pages | Coordinador |

---

## Parte 4. Construcción colaborativa de la página

**Videos de apoyo:** secciones 2, 3, 4 y 6 de [RECURSOS_DE_APOYO.md](RECURSOS_DE_APOYO.md) (pull requests, conflictos, HTML y CSS, y uso de la IA).

### T4.1. Construir la página
**Se entrega:** la página con todas las secciones de T3.2 en la rama `main`.

La plantilla trae `index.html` en la raíz, `css/styles.css` y la carpeta `img/`. Se puede usar HTML y CSS, y JavaScript si el grupo lo desea. **El uso de inteligencia artificial está permitido** para crear la página (código, textos, diseño e imágenes), para acelerar el trabajo y para aprender, por ejemplo pidiéndole que explique el código que genera. **Siempre se nombra dónde se usó** (ver T4.3 y T5.2). Ideas de qué pedirle están en [RECURSOS_DE_APOYO.md](RECURSOS_DE_APOYO.md).

### T4.2. Una rama por tarea, commits pequeños y push
**Se entrega:** las ramas y los commits de cada integrante.

**Mínimo por integrante: 8 commits propios, en al menos 3 días distintos.**

El ciclo de trabajo de cada tarea es siempre el mismo:

```bash
# 1. Actualizar tu copia local de main
git switch main
git pull

# 2. Crear tu rama para la tarea (nombre según el acuerdo de equipo)
git switch -c feature/USUARIO-encabezado

# 3. Trabajar en el editor y revisar qué cambió
git status

# 4. Guardar un cambio pequeño con un mensaje claro
git add index.html css/styles.css
git commit -m "Agregar encabezado con botón de llamado a la acción"

# 5. Repetir los pasos 3 y 4 las veces necesarias, y subir la rama
git push -u origin feature/USUARIO-encabezado
```

Si la rama ya existe en GitHub, los siguientes envíos se hacen solo con `git push`.

Buenas prácticas para los commits:
- **Pequeños:** un cambio con sentido por commit.
- **Mensajes claros:** verbo en infinitivo y qué cambió (por ejemplo, "Corregir el color del botón"). Evitar mensajes como "cambios" o "arreglos".
- **Con tu propia cuenta:** nadie sube el trabajo de otro integrante desde su computador.

### T4.3. Pull requests, revisión y fusión
**Se entrega:** los pull requests con sus revisiones.

**Mínimo por integrante: 2 pull requests propios fusionados (contando el de T2.4), 2 comentarios o revisiones en pull requests de compañeros y 1 issue asignado cerrado.**

**Autor:**
1. Subir la rama con `git push` y pulsar **Compare & pull request**.
2. Verificar que **base** sea `main` y **compare** sea tu rama.
3. Completar la plantilla del pull request. Para cerrar el issue al fusionar, escribir `Closes #N` (con el número del issue). **En la casilla "Uso de inteligencia artificial", marcar si se usó o no y, si se usó, la herramienta y dónde (archivo o sección).**
4. En **Reviewers**, elegir a un compañero **distinto de ti**.

**Revisor:**
1. Abrir el pull request, entrar a **Files changed** y leer los cambios.
2. Pulsar **Review changes**, escribir al menos un comentario y elegir **Comment** o **Approve**.
3. Si pide cambios, el autor los hace en la misma rama, hace `commit` y `git push`; el pull request se actualiza solo.

**Fusión:** con la aprobación, el autor (o el coordinador) pulsa **Merge pull request** y luego **Delete branch**. Después, cada integrante actualiza su copia local con `git switch main` y `git pull`.

### T4.4. Resolver conflictos de fusión
**Se entrega:** el comentario en el pull request que explica cómo se resolvió, si hubo conflictos.

Un conflicto ocurre cuando dos personas cambian las mismas líneas. GitHub lo avisa en el pull request. Para resolverlo:

```bash
# Traer los cambios nuevos de main a tu rama
git switch feature/USUARIO-encabezado
git merge main
```

Git marca el archivo con `<<<<<<<`, `=======` y `>>>>>>>`. Se abre el archivo, se **decide entre las personas involucradas** qué versión queda (o una mezcla), se borran las marcas, y luego:

```bash
git add index.html
git commit -m "Resolver conflicto con main en el encabezado"
git push
```

Dejar un comentario en el pull request que diga qué se decidió y por qué.

### T4.5. Verificar diseño y accesibilidad
**Se entrega:** la página corregida en `main`.

- **Celular y computador:** en el navegador, abrir las herramientas de desarrollo (tecla F12) y activar la vista de dispositivos móviles. La página no debe cortarse ni requerir desplazamiento horizontal.
- **Texto alternativo:** cada `<img>` lleva el atributo `alt` con una descripción breve.
- **Títulos jerárquicos:** un solo `<h1>` y luego `<h2>`, `<h3>` en orden.
- **Enlaces:** hacer clic en cada uno; todos deben funcionar.

### T4.6. Imágenes y recursos con crédito
**Se entrega:** la lista de créditos, en el README.

Usar solo imágenes, íconos, fuentes y plantillas propios, generados con IA o con una licencia que permita su uso. Anotar en el README, sección *Créditos*, el autor o la herramienta, el enlace y la licencia de cada uno.

---

## Parte 5. Publicación, documentación y verificación

**Videos de apoyo:** sección 5 de [RECURSOS_DE_APOYO.md](RECURSOS_DE_APOYO.md) (publicar con GitHub Pages).

### T5.1. Publicar con GitHub Pages (lo hace el coordinador)
**Se entrega:** el enlace de la página publicada.

1. **Settings, Pages**.
2. En **Build and deployment**, en **Source**, elegir **Deploy from a branch**.
3. En **Branch**, elegir `main` y la carpeta `/ (root)`. Pulsar **Save**.
4. Esperar uno o dos minutos y recargar. Aparece el enlace `https://USUARIO.github.io/REPO/`.
5. Abrirlo y confirmar que se ve la página completa.

### T5.2. Completar el README
**Se entrega:** el README completo.

Debe incluir: nombre y descripción, enlace de la página, tabla de integrantes (usuario, rol y aportes principales), acuerdo de equipo, tecnologías, declaración del uso de IA (herramienta, **archivo o sección donde se usó**, para qué y cómo se revisó) y créditos. **Borrar el bloque "LEER PRIMERO" y todos los textos que dicen COMPLETAR.** Se edita con ramas y pull requests, igual que el resto.

### T5.3. Verificar que se vea el trabajo de todos
**Se entrega:** el repositorio verificado y corregido antes de la fecha de entrega.

1. **Insights, Contributors:** deben aparecer los **cuatro** integrantes. Esta gráfica cuenta los commits que ya están fusionados en `main`, y puede tardar unos minutos en actualizarse.
2. **Code, commits:** el historial muestra los commits de cada uno con su usuario.
3. **Pull requests, Closed:** los pull requests tienen revisiones y comentarios.
4. **Issues, Closed:** los issues están asignados y cerrados.
5. Abrir el repositorio y la página en una **ventana privada** del navegador para confirmar que son públicos.
6. Completar la [lista de verificación](LISTA_DE_VERIFICACION.md).

---

## Parte 6. Informe en Word

Esta parte tiene una guía completa, con la estructura, las tablas y una revisión final: [GUIA_DEL_INFORME.md](GUIA_DEL_INFORME.md).

### T6.1. Redactar el informe
**Se entrega:** el informe en Word, de máximo 8 páginas sin contar la portada, con nueve secciones en este orden: portada, descripción del proyecto, equipo y acuerdo, GitHub como herramienta colaborativa, evidencias, aporte de cada integrante, desafíos y aprendizajes, uso de inteligencia artificial y referencias.

### T6.2. Tomar las cinco capturas de pantalla
**Se entrega:** las capturas dentro del informe, numeradas, con título y fuente: Contributors, historial de commits, un pull request con revisión, la lista de issues y la página publicada. Se pueden ir tomando durante la Parte 4, a medida que el trabajo avanza.

### T6.3. Declarar el uso de la IA en el informe
**Se entrega:** una tabla que diga dónde se usó la IA, la herramienta, qué se le pidió, cómo se revisó y **qué aprendió el grupo**. El uso de la IA para acelerar y aprender está permitido; lo que se exige es nombrar dónde se usó.

### T6.4. Revisar y nombrar el archivo
**Se entrega:** el archivo `.docx` nombrado `Proyecto_Final_Grupo_N`, con máximo 8 páginas sin portada, figuras y tablas numeradas con título y fuente, y referencias en APA 7 (incluidos los videos o tutoriales que se usaron).

---

## Problemas frecuentes

| Problema | Causa probable | Solución |
|---|---|---|
| Mi commit no aparece a mi nombre ni en Contributors | El correo configurado en Git no es el de tu cuenta de GitHub | Revisar `git config user.email` y usar el correo de **Settings, Emails**. Los commits ya hechos no se corrigen solos: los siguientes sí saldrán bien. |
| `git push` dice que el push fue rechazado | Tu rama quedó atrás de la del servidor | Ejecutar `git pull` y volver a hacer `git push`. |
| No puedo subir a `main` | La rama está protegida, como debe ser | Crear una rama y abrir un pull request. |
| No puedo aprobar mi propio pull request | GitHub lo impide a propósito | Pedir la revisión a otro integrante. |
| La página publicada no cambia | GitHub Pages tarda en actualizar | Esperar unos minutos y recargar con Ctrl + F5. |
| Subí por error una clave o un dato personal | GitHub conserva el historial | Avisar al coordinador y al facilitador de inmediato; cambiar la clave y no volver a subirla. |
| No aparezco en Contributors, pero hice commits | Tus pull requests no están fusionados en `main`, o el correo no coincide | Fusionar los pull requests y revisar el correo. |
