# Product Backlog

## Índice

 - [Sofware Enginnering 10th Edition - Ian Sommerville](#1)
   - [User Stories: Scenarios y Acceptance Criteria](#1.1)
 - [User Stories Applied for Agile Development - Mike Cohn](#2)
   - [Elicitación de requisitos](#2.1)
   - [Elicitación de requisitos como un proceso contínuo](#2.2)
   - [Slicing para user stories](#2.3)
   - [Las user stories son cerradas](#2.4)
   - [Las user stories no especifican la solución](#2.5)
   - [Las user stories tienen un único usuario](#2.6)
   - [¿Por qué usar user stories?](#2.7)
   - [Errores frecuentes](#2.8)

## Notas

<h3 id="1">Sofware Enginnering 10th Edition - Ian Sommerville</h3>

<h4 id="1.1">User Stories: Scenarios y Acceptance Criteria (p. 119)</h4>

Las historias deben incluir en sus criterios de aceptación:
 - Lo que el usuario y el sistema esperan (como input o precondición) al empezar el escenario
 - El flujo normal o ideal (happy path)
 - Las cosas que pueden fallar y como se maneja el error (unhappy paths)
 - El estado de finalización del sistema al concluir

 <h3 id="2">User Stories Applied for Agile Development - Mike Cohn</h3>

 <h4 id="2.1">Elicitación de requisitos (p. 43)</h4>

 La elicitación de requisitos es como pescar con red. Los requisitos se encuentran allí afuera esperando a ser capturados. Depende de nosotros escoger la red adecuada (instrumentos o métodos de elicitación) para poder capturarlos.

 <h4 id="2.2">Elicitación de requisitos como un proceso contínuo (p. 44)</h4>

 Los equipos ágiles entienden que es imposible capturar todos los requisitos "en una sola pesca".

<h4 id="2.3">Slicing para user stories (p.76)</h4>

Cuando dividimos una épica en historias de usuario, debemos pensar en el tamaño y alcance de cada historia como el de una tajada de torta. No se cortan solo por capas (por ejemplo, backend o frontend), sino desde el exterior hasta el centro. Cada historia de usuario debe ser una pieza que incluya un poco de cada parte necesaria para **entregar valor funcional completo al usuario final**.

Por tanto, una historia de usuario bien definida en definitiva podría incluir cambios tanto en el front-end como en el back-end.

<h4 id="2.4">Las user stories son cerradas (p. 77)</h4>

Esta idea se comprende mejor con un ejemplo. En lugar de escribir historias de usuario demasiado amplias, como:

> "Como reclutador, quiero gestionar las ofertas de trabajo que he creado para tener un control general de las oportunidades laborales publicadas."

Es preferible dividirlas en historias más específicas y accionables, como:

- "Como reclutador, quiero revisar currículums de los aplicantes al trabajo para identificar rápidamente candidatos potenciales."
- "Como reclutador, quiero cambiar la fecha de expiración de una oferta de trabajo existente para asegurar que las posiciones permanezcan visibles mientras estén abiertas y evitar confusión en los candidatos."
- "Como reclutador, quiero eliminar una oferta de trabajo para mantener actualizadas las oportunidades laborales disponibles, evitando postulaciones innecesarias."

De esta manera, cada historia es más concreta, enfocada y fácil de implementar, además de ser más valiosa (por que el valor que percibe el usuario es más concreto). También asegura que las historias de usuarios sean más pequeñas.

<h4 id="2.5">Las user stories no especifican la solución (p. 79)</h4>

Uno de los mayores problemas al especificar requisitos es terminar detallando una solución en lugar de expresar una necesidad o funcionalidad. 

Una user story no debería incluir detalles técnicos o elementos específicos de la interfaz, ya que esto cambia el enfoque de describir una funcionalidad hacia proponer o imponer una implementación. Esto limita la creatividad del equipo para encontrar la mejor solución técnica.

Un ejemplo de una user story que no sigue esta recomendación: 

> "Como usuario, quiero un botón rojo en la página principal para acceder a mi perfil."

Un ejemplo de una user story que sí sigue esta recomendación: 

> "Como usuario, quiero acceder fácilmente a mi perfil desde la página principal para gestionar mi información personal."

<h4 id="2.6">Las user stories tienen un único usuario (p. 81)</h4>

Las historias son más fáciles de entender si:
 - Se escriben en voz activa (sujeto agente).
 - Se escriben para un único rol de usuario (revisar needfinding para más detalles).

Unos ejemplos de user stories que no siguen esta recomendación:

> "Como vendedor o comprador, quiero ver la lista de productos para comprar productos o saber lo que he puesto a la venta."

> "Como vendedor o comprador, quiero iniciar sesión en mi cuenta para usar la aplicación con mis datos personales."

Unos ejemplos de user stories que sí siguen esta recomendación:

> "Como comprador, quiero ver los distintos productos disponibles para saber lo que puedo comprar."

> "Como vendedor, quiero ver mi lista de productos publicados para saber lo que he puesto a la venta."

> "Como usuario, quiero iniciar sesión en mi cuenta para usar la aplicación con mis datos personales.

Existen casos donde escribir dos veces una misma historia resulta redundante, pues el valor obtenido por distintos roles de usuario por una funcionalidad concreta es el mismo o es muy parecido. En dicho caso, es recomendable elevar las historias a nivel de ***usuario*** genérico.

<h4 id="2.7">¿Por qué usar user stories? (p. 145)</h4>

El uso de las user stories para modelar los requisitos de software se ha popularizado debido a que usarlas trae consigo una serie de beneficios:
 - Promueven la conversación verbal con el cliente.
 - Pueden ser entendidas por todos, sin importar el conocimiento técnico.
 - Permite a los desarrolladores familiarizarse con el lenguaje y reglas de negocio.
 - Son ideales para la planificación y desarrollo iterativo.
 - Ofrecen un margen de libertad creativa a los desarrolladores.

<h4 id="2.8">Errores frecuentes (p. 157)</h4>

Hay una serie de errores que pueden identificarse a través de síntomas.
1. Historias ***demasiado*** pequeñas:
 - Síntoma: Estimar el peso de las historias en distinto orden cambia los story points asignados.
 - Ejemplo:

    "Como artista, quiero guardar mi dibujo en .png para mostrar mi trabajo a otros en alta calidad."

    "Como artista, quiero guardar mi dibujo en .webp para contar con una versión altamtente comprimida de este."

2. Historias demasiado largas:
 - Síntoma: No es posible escribir la historia en una tarjeta (referencia física).
 - Ejemplo: 

    Como desarrollador, quiero crear una plataforma de administración de contenidos donde los usuarios puedan subir, editar y eliminar artículos, para que puedan gestionar sus publicaciones de manera eficiente.

