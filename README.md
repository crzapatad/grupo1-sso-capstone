# Sistema de Gestión de riesgos en faenas

**Descripción del proyecto**

El proyecto consiste en la creación de un sistema  integral para la gestión de riesgos faenas. Para contextualizar, existen muchos entornos de trabajo en que los trabajadores están expuestos a riesgos que puedan dañar su integridad, generalmente riesgos físicos. Pueden ser varios escenarios, como inundaciones, cortes de luz, incendios, derrame de químicos, incluso asaltos. Para poder registrar estos incidentes, lo que hace el trabajador que trabaja en esos entornos es registrar los hechos a mano. Es decir, los reportes que ellos elaboran lo realizan a papel, ya sea en blanco o con un formato de reporte otorgado por la empresa. Una vez hecho el reporte, el trabajador debe enviarlo a su correspondiente supervisor (presencialmente) para que éste pueda analizar el caso y resolverlo. 



**¿Cuál es el problema con esto?**

Que todo este proceso consume tiempo, requiere logística y que la trazabilidad no es del todo seguro. Asimismo, el proceso descrito depende de objetos fisicos como los registros en papel, y no hay una base de datos que albergue dichos registros, y a la vez, consultar, actualizar, seleccionar o eliminar. Al haber dependencia de objetos físicos, ello requiere salvaguardarlos de una forma más engorrosa, y al acumularse con el tiempo, resulta más dificil consultar en un futuro un determinado reporte.

**Solución propuesta**

La solución propuesta consiste en digitalizar los procesos que hemos señalado anteriormente. Para ello, queremos elaborar una plataforma tecnológica que permita una comunicación más eficaz y rápida entre los actores señalados que son el trabajador y el supervisor. La plataforma está compuesta por una aplicacion movil (utilizada por los trabajadores) y una aplicacion web (utilizada por los supervisores), cada una diseñada con sus respectivas interfaces. Para permitir una comunicación entre estas aplicaciones, usaremos una arquitectura de microservicio (API). 
Las funcionalidades de estas interfaces las señalaremos a continuacion para cada aplicación:

1) App móvil: la app movil permitirá al trabajador registrar evidencias. Podrá subir tanto imagenes como texto (ya que usaremos una base de datos no estructurada como firebase). Asimismo, el trabajador podrá iniciar sesión, determinar el nivel de gravedad de un incidente antes de enviar la evidencia, podrá hacer seguimiento de su situación en tiempo real (si está pendiente, o finalizado, cuyo estado dependerá del supervisor).
  
2) App Web: la app web permitirá al supervisor visualizar un dashboard de los reportes que ha recibido a lo largo del tiempo. En dicho dashboard puede ver un mapa de calor en el que cada área coloreada representa un incidente reportado y enviado por parte de un trabajador. También podrá actualizar el estado de un reporte, siendo notificada al trabajador instantaneamente. El supervisor también puede registrarse e iniciar sesión en la app web.

Asimismo, disponemos de un wireframe para ambas aplicaciones, siguiendo el diseño visual propuesto por Alloxentric.


**Beneficios de implementar un sistema digitalizado de gestión de riesgos en faenas**

1) permite a la empresa ahorrar gastos al reducir el tiempo en este proceso. 
2) permite una comunicación más eficaz y rápida entre los actores señalados que son el trabajador y el supervisor. 


## ¿Cuáles son las características principales de este proyecto? 

Para solucionar los problemas señalados inicialmente, el proyecto requiere tener listo estas  características principales que son las siguientes:

- **Reporte de Peligros de Seguridad**: Los trabajadores pueden reportar actos inseguros y condiciones inseguras mediante fotografías, ubicación geográfica y descripciones detalladas.

- **Seguimiento de Estado en Tiempo Real**: Permite monitorear el estado de un reporte durante todo su ciclo de vida (enviado → en revisión → acción asignada → cerrado).

- **Monitoreo de cumplimiento de plazos**: Indicadores visuales que muestran si los reportes están dentro del plazo, en riesgo de incumplimiento o vencidos.

- **Estadísticas Personales de Seguridad**: Permite visualizar tasas de efectividad, rachas de participación y métricas relacionadas con el reporte de Incidentes y Actos Peligrosos (IAP).

- **Notificaciones**: Los usuarios reciben alertas en tiempo real sobre cambios en el estado de sus reportes y avisos de seguridad específicos de su área de trabajo.

- **Soporte Offline**: Los reportes se almacenan localmente cuando no hay conexión a Internet y se sincronizan automáticamente una vez que se restablece la conectividad.

### Funcionalidades Adicionales

- **Medidas de mitigación**: Permite asignar, monitorear y dar seguimiento a acciones correctivas, incluyendo fechas límite y estado de cumplimiento.
- **Comentar y Discutir**: Facilita la colaboración entre los miembros del equipo mediante comentarios asociados a cada reporte.
- **Clasificar los reportes**: Los reportes pueden clasificarse como actos inseguros o condiciones inseguras para mejorar su análisis y tratamiento.
- **Soporte para Múltiples Turnos**: Permite registrar incidentes y observaciones correspondientes a turnos de mañana, tarde o noche.
- **Modo oscuro**: Interfaz diseñada específicamente con una temática oscura y acentos en color naranja de seguridad, optimizando la visibilidad y la experiencia de uso en entornos industriales.


## Stack Tecnológico para el proyecto

El stack tecnológico consiste en 5 puntos principales:

-**Backend**

-**Frontend (página web)**

-**Frontend (app móvil)**

-**Base de datos**

-**Modelo de datos**


### 1) Backend

El backend del Sistema Integral de Gestión de Riesgos (SSO) constituye el núcleo operativo de la plataforma, siendo responsable de procesar la información proveniente de las aplicaciones web y móviles, ejecutar la lógica de negocio, gestionar la seguridad del sistema y coordinar el almacenamiento de datos y archivos. La arquitectura implementada se basa en un modelo de microservicios desplegados sobre infraestructura cloud, lo que permite alcanzar altos niveles de escalabilidad, disponibilidad y mantenibilidad.

![Pantalla de Login](images/stack2.png)


### 2) Frontend (Página web)

El frontend constituye la capa de interacción entre los usuarios y la plataforma, proporcionando interfaces especializadas para distintos perfiles operativos y administrativos. La arquitectura frontend fue diseñada bajo un enfoque multiplataforma, compuesto por una aplicación web orientada a la gestión y supervisión, y una aplicación móvil destinada al personal operativo en terreno. Ambas aplicaciones comparten principios de diseño, contratos de API y mecanismos de autenticación, permitiendo mantener coherencia funcional y facilitar la evolución del sistema.
![Pantalla de Login](images/stack3.png)

### 3) Frontend (App móvil)

El frontend de la aplicación móvil está desarrollada con React Native y TypeScript. Su función es proporcionar una interfaz intuitiva para que trabajadores y supervisores puedan registrar, consultar y dar seguimiento a reportes de riesgos. Además, integra funcionalidades como autenticación, captura de evidencias fotográficas, geolocalización, notificaciones y funcionamiento offline, comunicándose de forma segura con el backend mediante servicios web.
![Pantalla de Login](images/stack4.png) 


### 4) Base de Datos
- Para este proyecto usamos Cloud Firestore como sistema de gestión de bases de datos. Firestore es una base de datos NoSQL, encargada de almacenar datos no estructurados (como contenido multimedia, imágenes) que forma parte del ecosistema de Google Cloud Platform (GCP). Hemos escogido Firestore debido a su escalabilidad y su capacidad de almacenamiento para los reportes, además de que nuestro proyecto es un SaaS (software como un servicio).

Una de las principales ventajas de Firestore es su capacidad de escalamiento horizontal automático. El escalamiento horizontal automático de Firestore significa que, si la aplicación crece y comienzan a utilizarla muchas más empresas y usuarios, Google aumenta la capacidad necesaria detrás de escena sin que nosotros tengamos que preocuparnos por administrar servidores adicionales.

Adicionalmente, Firestore ofrece integración nativa con servicios de Google Cloud, simplificando los mecanismos de autenticación y autorización mediante cuentas de servicio utilizadas por los microservicios desplegados en Cloud Run. Asimismo, dispone de soporte para operaciones asíncronas a través del SDK oficial de Python, facilitando su integración con servicios desarrollados en FastAPI y ejecutados mediante Uvicorn.

La plataforma también incorpora capacidades de sincronización en tiempo real mediante listeners, permitiendo que los cambios en los reportes, alertas o acciones correctivas se reflejen instantáneamente en las interfaces de usuario sin necesidad de consultas periódicas al servidor.


## 5) Modelos de Datos

La estructura de Firestore se organiza utilizando un esquema jerárquico basado en colecciones y subcolecciones. En el nivel superior se encuentra la colección clients, donde cada documento representa una organización cliente del sistema. Este enfoque permite implementar un modelo multi-tenant, asegurando la separación lógica de los datos entre distintas empresas.

Dentro de cada cliente se almacenan diversas subcolecciones que representan las entidades funcionales del sistema:

- users: contiene la información de los usuarios registrados, incluyendo nombre, correo electrónico, rol, áreas asignadas y estado.
- zones: almacena información de las zonas o áreas de trabajo, incluyendo procesos asociados, colores de visualización y coordenadas utilizadas para representar polígonos en mapas de planta.
- reports: registra los reportes de riesgos, actos inseguros, condiciones inseguras e IAP, junto con información sobre responsables, fotografías, turnos y estado del reporte.
- report_events: mantiene un historial completo de cambios de estado, implementando un enfoque de auditoría basado en eventos.
- actions: almacena las acciones correctivas derivadas de los reportes, incluyendo responsables, fechas de vencimiento y estado de cumplimiento.
- comments: permite registrar conversaciones y comentarios asociados a cada reporte.
- alerts: administra las notificaciones y alertas generadas por el sistema.
- exports: conserva el historial de exportaciones de información y reportes generados por los usuarios.

Este diseño favorece la organización lógica de los datos, reduce la complejidad de las consultas y facilita la escalabilidad de la plataforma.


## Seguridad

La arquitectura propuesta incorpora un conjunto de controles de seguridad diseñados para proteger la confidencialidad, integridad y disponibilidad de la información gestionada por el sistema. Estos controles se aplican tanto a nivel de infraestructura como de aplicación, siguiendo buenas prácticas recomendadas para entornos cloud y arquitecturas basadas en microservicios.

**Seguridad en las Comunicaciones**

Todo el tráfico entre clientes, servicios y componentes de la plataforma se realiza mediante el protocolo HTTPS utilizando TLS 1.3. Esta configuración garantiza que la información transmitida viaje cifrada y protegida frente a interceptaciones o ataques de tipo "man-in-the-middle". Adicionalmente, la infraestructura impide conexiones HTTP en entornos de producción, asegurando que todas las comunicaciones utilicen canales seguros.

**Autenticación entre Servicios**

Los distintos microservicios de la plataforma se autentican mediante Service Accounts administradas por Google Cloud Platform. Para ello se utiliza Workload Identity Federation, mecanismo que permite validar la identidad de los servicios sin necesidad de almacenar credenciales o contraseñas dentro del código fuente. Esta estrategia reduce significativamente la superficie de ataque asociada a la gestión de secretos.

**Principio de Mínimos Privilegios**

Cada componente del sistema dispone únicamente de los permisos estrictamente necesarios para ejecutar sus funciones. Este enfoque limita el impacto potencial de una vulnerabilidad o acceso no autorizado. Por ejemplo, los servicios encargados de generar exportaciones son los únicos que poseen permisos de escritura sobre los repositorios de almacenamiento destinados a reportes y documentos.

**Validación de Entradas**

Toda la información ingresada por los usuarios es validada antes de ser procesada por la lógica de negocio. Para ello se emplean modelos de validación definidos mediante Pydantic, verificando tipos de datos, formatos y restricciones de contenido. Esta medida ayuda a prevenir errores de procesamiento, inconsistencias de datos y diversos tipos de ataques basados en entradas maliciosas.

**Auditoría y Trazabilidad**

El sistema mantiene registros estructurados de las acciones realizadas por los usuarios y servicios. Operaciones como creación, modificación, actualización de estados y asignación de acciones correctivas generan eventos de auditoría que incluyen información como identificador de usuario, organización cliente, fecha, hora, acción ejecutada y resultado obtenido. Estos registros permiten realizar análisis posteriores, investigaciones y procesos de cumplimiento normativo.

**Control de Acceso mediante CORS**

La API implementa políticas CORS (Cross-Origin Resource Sharing) para restringir el acceso únicamente a los dominios autorizados del frontend web y la aplicación móvil. En ambientes de desarrollo se permite el acceso desde localhost para facilitar las pruebas, mientras que en producción se aplican restricciones más estrictas para evitar solicitudes provenientes de orígenes no autorizados.

**Protección contra Abuso y Sobrecarga**

La plataforma incorpora mecanismos de limitación de solicitudes (Rate Limiting) para reducir riesgos asociados a ataques de fuerza bruta, automatización maliciosa y consumo excesivo de recursos. Se establecen límites por dirección IP y se aplican controles más estrictos en operaciones sensibles, como los procesos de autenticación.

**Protección de Datos Sensibles**

Las evidencias fotográficas asociadas a incidentes y reportes se consideran información sensible y no se exponen públicamente. El acceso a estos recursos se realiza mediante URLs firmadas generadas dinámicamente por el backend, con tiempos de expiración limitados. De esta manera se garantiza que únicamente usuarios autorizados puedan visualizar el contenido durante un período controlado.

**Beneficios de la Estrategia de Seguridad**

La combinación de cifrado de comunicaciones, autenticación basada en identidades de servicio, validación de datos, auditoría centralizada y control granular de permisos permite construir una plataforma alineada con las buenas prácticas de seguridad modernas. Esta estrategia contribuye a proteger la información operacional de las organizaciones, asegurar la trazabilidad de las acciones realizadas y reducir los riesgos asociados a accesos no autorizados o manipulaciones de datos.

## Integrantes

**CAPSTONE_001D - Grupo 1**

- Sean Parker
- Tomás Figueroa
- Cristóbal Zapata

## Documentación Adicional

- [Carta Gantt](https://docs.google.com/spreadsheets/d/1WdQG8cgWP_Q8y35ntlekh_Nq8pTK4AdS/edit?gid=1137986524#gid=1137986524)

## Arquitectura

La solución propuesta corresponde a una arquitectura distribuida de múltiples capas orientada a servicios, diseñada para soportar la gestión de riesgos e incidentes de Seguridad y Salud Ocupacional (SSO). La arquitectura se basa en una separación clara entre la capa de presentación, la capa de servicios de negocio y la capa de datos, permitiendo escalabilidad, mantenibilidad y facilidad de integración con futuros sistemas.

![Capas arquitectura](images/CapasArquitectura.png)

La capa de presentación está compuesta por aplicaciones cliente web y móvil, desarrolladas para permitir el acceso al sistema desde distintos dispositivos. Estas aplicaciones consumen funcionalidades a través de APIs expuestas por los servicios backend.

La capa de servicios implementa una arquitectura de microservicios, donde cada servicio posee responsabilidades específicas y se comunica mediante interfaces REST. Este enfoque favorece el desacoplamiento funcional, la independencia de despliegue y la escalabilidad de cada componente.

Finalmente, la capa de datos utiliza una base de datos NoSQL basada en Cloud Firestore para el almacenamiento de información operacional y Cloud Storage para la gestión de archivos binarios, tales como fotografías, planos y documentos adjuntos.

La autenticación y autorización son delegadas a un proveedor de identidad externo mediante Keycloak, permitiendo una administración centralizada de usuarios, roles y permisos.



**Beneficios de la Arquitectura Propuesta**
La arquitectura planteada proporciona múltiples beneficios para la organización:
- Escalabilidad horizontal de los servicios.
- Alta disponibilidad de la plataforma.
- Facilidad de mantenimiento y evolución.
- Despliegue independiente de componentes.
- Mayor seguridad mediante autenticación centralizada.
- Trazabilidad completa de eventos e incidentes.
- Integración sencilla con sistemas externos.
- Soporte para crecimiento futuro del número de usuarios y organizaciones.

En conjunto, esta arquitectura permite construir una plataforma robusta, moderna y preparada para soportar las necesidades operacionales de gestión de riesgos e incidentes en entornos industriales y corporativos.
## **Diseño del sistema**

**Diagrama UML**
![DiagramaUML](images/SSO.png)

**Diagrama de clase**
![Diagramaclase](images/clase.png)

## Metodología ágil basada en Scrum

El proyecto fue desarrollado siguiendo una metodología ágil basada en Scrum, permitiendo la construcción incremental de la solución y la incorporación continua de mejoras a medida que se obtenía retroalimentación sobre el funcionamiento del sistema. Esta metodología favoreció la flexibilidad, la adaptación a cambios en los requerimientos y la validación progresiva de las funcionalidades implementadas.





## Sprint 1: Fundación Arquitectónica e Infraestructura Base

Información General

- Sprint: Sprint 1
- Duración: 3 semanas
- Objetivo del Sprint: Implementar la infraestructura inicial del sistema SSO, configurar la arquitectura de microservicios, establecer los mecanismos de autenticación y desarrollar los componentes fundamentales del frontend y backend.

--



## Sprint 2: Implementación de Funcionalidades Operacionales

Información General

- Sprint: Sprint 2
- Duración: 3 semanas
- Objetivo del Sprint: Implementar el flujo principal de reportes, la gestión inicial de incidentes, el módulo de zonas y el sistema básico de alertas.




## Sprint 3: Analítica, Visualización y Generación de Reportes

Información General

- Sprint: Sprint 3
- Duración: 3 semanas
- Objetivo del Sprint: Implementar los módulos de visualización analítica, dashboards ejecutivos, mapas de calor, métricas de riesgo y generación de reportes exportables.


 


## Sprint 4: Optimización, Seguridad y Despliegue Productivo

Información General

- Sprint: Sprint 4
- Duración: 3 semanas
- Objetivo del Sprint: Realizar la validación integral del sistema, optimizar el rendimiento, fortalecer la seguridad, completar la documentación y preparar el despliegue productivo de la plataforma SSO.



Cierre
En la semana 14 se dedica exclusivamente a:
Integración final del sistema.
Pruebas funcionales.
Corrección de incidencias detectadas.
Validación del cumplimiento de requisitos.
Elaboración y revisión de la documentación técnica.
Preparación de la presentación y defensa del Capstone.
Entrega final del proyecto.


## Licencia

Este proyecto fue desarrollado como parte del proyecto APT (Aplicación de Proyecto Tecnológico) para Alloxentric.

**Versión**: 1.0
**Última actualización**: 01-07-2026
