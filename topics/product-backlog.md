# Product Backlog

## Índice

- [Software Engineering 10th Edition - Ian Sommerville](#software-engineering-10th-edition---ian-sommerville)
  - [User Stories: Scenarios y Acceptance Criteria](#user-stories-scenarios-y-acceptance-criteria-p-119)
- [User Stories Applied for Agile Development - Mike Cohn](#user-stories-applied-for-agile-development---mike-cohn)
  - [Elicitación de requisitos como un proceso continuo](#elicitación-de-requisitos-como-un-proceso-continuo-p-43-44)
  - [Slicing para user stories](#slicing-para-user-stories-p-76)
  - [Las user stories son cerradas](#las-user-stories-son-cerradas-p-77)
  - [Las user stories no especifican la solución](#las-user-stories-no-especifican-la-solución-p-79)
  - [Las user stories tienen un único usuario](#las-user-stories-tienen-un-único-usuario-p-81)
  - [¿Por qué usar user stories?](#por-que-usar-user-stories-p-145)
  - [Errores frecuentes](#errores-frecuentes-p-157)
- [Applying BDD acceptance criteria in user stories - Thoughtworks](#applying-bdd-acceptance-criteria-in-user-stories---thoughtworks)
  - [Cómo usar Given](#cómo-usar-given)
  - [Cómo usar When](#cómo-usar-when)

---

## Software Engineering 10th Edition - Ian Sommerville

### User Stories: Scenarios y Acceptance Criteria (p. 119)

Los criterios de aceptación deben incluir:

- Condiciones iniciales (inputs o precondiciones) para iniciar el escenario.
- Flujo normal o ideal (happy path).
- Manejo de errores (unhappy paths).
- Estado final del sistema al concluir.

## User Stories Applied for Agile Development - Mike Cohn

### Elicitación de requisitos como un proceso continuo (p. 43-44)

La elicitación de requisitos es un proceso dinámico, similar a pescar en un río:

- Los requisitos emergen, cambian o desaparecen constantemente.
- Es crucial usar herramientas adecuadas al contexto y necesidades del proyecto.

### Slicing para user stories (p. 76)

Divide las épicas en historias pequeñas que entreguen **valor funcional completo al usuario**. Las historias deben incluir tanto aspectos de frontend como backend.

La división técnica se puede realizar mediante los Task de ingeniería en que se descompone la historia.

### Las user stories son cerradas (p. 77)

Ejemplo incorrecto:

    "Como reclutador, quiero gestionar ofertas para tener control general."

Ejemplos correctos:

    "Como reclutador, quiero revisar currículums para identificar candidatos potenciales."

    "Como reclutador, quiero cambiar la fecha de expiración de una oferta para mantenerla visible."

### Las user stories no especifican la solución (p. 79)

Ejemplo incorrecto:

    "Como usuario, quiero un botón rojo para acceder a mi perfil."

Ejemplo correcto:

    "Como usuario, quiero acceder fácilmente a mi perfil para gestionar mi información."

### Las user stories tienen un único usuario (p. 81)

Historias claras y enfocadas en un único rol de usuario son más fáciles de entender.

Ejemplos de user stories que no siguen esta recomendación:

    "Como vendedor o comprador, quiero ver la lista de productos para comprar productos o saber lo que he puesto a la venta."

    "Como vendedor o comprador, quiero iniciar sesión en mi cuenta para usar la aplicación con mis datos personales."

Ejemplos de dichas user stories, pero siguiendo esta recomendación:

    "Como comprador, quiero ver los distintos productos disponibles para saber lo que puedo comprar."

    "Como vendedor, quiero ver mi lista de productos publicados para saber lo que he puesto a la venta."

Existen casos donde escribir dos veces una misma historia resulta redundante, pues el valor obtenido por distintos roles de usuario por una funcionalidad concreta es el mismo o es muy parecido. En dicho caso, es recomendable elevar las historias a nivel de ***usuario*** genérico.

    "Como usuario, quiero iniciar sesión en mi cuenta para usar la aplicación con mis datos personales.

### Por que usar user stories (p. 145)

- Promueven la comunicación verbal con el cliente.
- Son comprensibles para todos.
- Fomentan la creatividad técnica del equipo.

### Errores frecuentes (p. 157)

El primero de ellos es crear **historias demasiado pequeñas:**. Ejemplo:

    "Como usuario, quiero guardar mi dibujo en .png para tener mi dibujo formato en alta calidad."
    "Como usuario, quiero guardar mi dibujo en .webp para tener mi dibujo en un formato eficiente para la web."

El segundo error, es escribir **historias demasiado largas:**. Ejemplo:

    "Como desarrollador, quiero crear una plataforma de administración de contenidos donde los usuarios puedan subir, editar y eliminar artículos de manera dinámica y eficiente, para que puedan gestionar sus publicaciones de manera eficiente."

En este caso, la historia no solo es larga sino que también es grande: abarca muchas cosas y su redacción se prolonga demasiado.

## Applying BDD acceptance criteria in user stories - Thoughtworks

### Cómo usar Given

- Solo menciona las precondiciones relevantes.
- Agrupa precondiciones similares para evitar redundancia.

Ejemplos que aplica estas recomendaciones:

    Dado que el usuario se encuentra en la página de "Detalles de vuelo"
    Y el usuario omitió la opción de escoger asiento
    Cuando el usuario confirma su selección de detalles de vuelo
    Entonces se muestra un mensaje “El asiento será elegido al azar. ¿Continuar?”.

    Dado que se visualiza el formulario de login
    Y el usuario ingresa las siguientes credenciales válidas:
      - correo
      - contraseña
    Cuando el usuario envía el formulario
    Entonces el sistema muestra el mensaje "Bienvenido"
    Y carga la página principal

### Cómo usar When

- Usa un solo verbo que represente la acción principal.
- Enfócate en el propósito de la acción, no en la interfaz.

Por comparación:

     Incorrecto:
         Cuando el usuario hace click en el botón enviar
         
     Correcto:
         Cuando el usuario envía el formulario

---

Enlace al artículo: [Applying BDD acceptance criteria in user stories](https://www.thoughtworks.com/insights/blog/applying-bdd-acceptance-criteria-user-stories)
