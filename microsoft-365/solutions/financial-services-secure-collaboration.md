---
title: Consideraciones clave de cumplimiento y seguridad para los mercados de capital y los bancos de Estados Unidos
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: article
ms.collection:
- highpri
- M365-security-compliance
ms.service: o365-solutions
ms.custom: seo-marvel-jun2020
ms.localizationpriority: high
description: Conozca la forma en que las instituciones de servicios financieros pueden mantener el cumplimiento de la seguridad financiera y colaborar de forma eficaz al usar Microsoft 365 y Teams.
f1.keywords: NOCSH
ms.openlocfilehash: d547e6b8c15716eb63baf748572640f844f1b1c5
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67986870"
---
# <a name="key-compliance-and-security-considerations-for-us-banking-and-capital-markets"></a>Consideraciones clave de cumplimiento y seguridad para los mercados de capital y los bancos de Estados Unidos

## <a name="introduction"></a>Introducción

Las instituciones de servicios financieros superan a casi todas las empresas comerciales en su demanda de estrictos controles de seguridad, cumplimiento y gobierno. La protección de los datos, las identidades, los dispositivos y las aplicaciones no solo es crítica para su negocio, sino que está sujeta a las directrices y requisitos de cumplimiento de organismos normativos como la Comisión de Bolsa y Valores de Estados Unidos (SEC), la Autoridad Reguladora de la Industria Financiera (FINRA), el Consejo Federal de Certificación de Instituciones Financieras (FFIEC) y la Comisión de Comercio de Futuros de Mercancías (CFTC). Además, las instituciones financieras están sujetas a leyes como la Dodd-Frank y la Sarbanes-Oxley de 2002.

En el clima actual de creciente vigilancia de seguridad, inquietudes sobre riesgos internos y vulneraciones de datos públicos, los clientes también demandan altos niveles de seguridad de las instituciones financieras para confiarles sus datos personales y activos bancarios.

Históricamente, la necesidad de controles integrales restringió y afectó directamente a las plataformas y los sistemas de TI que las instituciones financieras usan para permitir la colaboración interna y externa. Hoy en día, los empleados de servicios financieros necesitan una plataforma de colaboración moderna que sea fácil de adoptar y usar. Pero los servicios financieros no pueden sacrificar la flexibilidad necesaria para colaborar entre usuarios, equipos y departamentos en favor de controles de cumplimiento y seguridad que aplican directivas para proteger a los usuarios y sistemas de TI frente a amenazas.

En el sector de servicios financieros, se requiere una reflexión cuidadosa para la configuración e implementación de herramientas de colaboración y controles de seguridad, entre los que se incluyen:

- Evaluación de riesgos de escenarios comunes de colaboración en organizaciones y procesos empresariales
- Requisitos de protección de la información y gobierno de datos
- Amenazas internas y de ciberseguridad
- Requisitos de cumplimiento normativo
- Otros riesgos operativos

**Microsoft 365 es un entorno de área de trabajo actual en la nube que puede tratar las dificultades modernas a las que se enfrentan las organizaciones de servicios financieros. Las colaboraciones seguras y flexibles en toda la empresa se combinan con los controles y la exigencia de directivas para adherir a los estrictos entornos de cumplimiento normativo.** En este artículo se describe cómo la plataforma de Microsoft 365 ayuda a los servicios financieros a pasarse a una plataforma de colaboración moderna, al tiempo que protege los datos y sistemas y les permite cumplir con las normativas:

* Permitir la productividad de los empleados y de la organización con Microsoft 365 y Microsoft Teams
* Proteger la colaboración moderna con Microsoft 365 
* Identificar datos confidenciales y evitar la pérdida de datos
* Defender la fortaleza
* Controlar los datos y cumplir con las normativas mediante una administración efectiva de registros
* Establecer zona de protección de datos confidenciales con barreras de información
* Protegerse contra la exfiltración de datos y los riesgos internos

Como partner de Microsoft, Protiviti contribuyó a este artículo y proporcionó comentarios sobre los materiales.

Las siguientes ilustraciones descargables complementan este artículo. El Woodgrove Bank y la empresa Contoso se utilizan para demostrar la forma en que las capacidades descritas en el presente artículo pueden aplicarse para hacer frente a los requisitos reglamentarios comunes de los servicios financieros. Siéntase libre de adaptar estas ilustraciones para su propio uso. 

**Ilustraciones de protección de información y cumplimiento de Microsoft 365**

| Elemento | Description |
|:-----|:-----|
|[![Póster modelo: capacidades de protección y cumplimiento de la información de Microsoft 365.](../media/solutions-architecture-center/m365-compliance-illustrations-thumb.png)](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf) <br/>Inglés: [Descargar como PDF](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf)  \| [Descargar como Visio](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.vsdx) <br/> Japonés: [Descargar como PDF](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.pdf)  \| [Descargar como Visio](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.vsdx)<br/> Actualizado en noviembre de 2020|Incluye: <ul><li>  Microsoft Purview Information Protection y Prevención de pérdida de datos de Microsoft Purview</li><li>Directivas y etiquetas de retención </li><li>Barreras de información</li><li>Cumplimiento de comunicaciones</li><li>Riesgo de Insider</li><li>Ingesta de datos de terceros</li>|


## <a name="empower-organizational-and-employee-productivity-by-using-microsoft-365-and-teams"></a>Permitir la productividad de los empleados y de la organización con Microsoft 365 y Teams

Generalmente, la colaboración requiere distintas formas de comunicación, la capacidad para almacenar y acceder a documentos y datos, y la capacidad de integrar otras aplicaciones según sea necesario. Los empleados en servicios financieros suelen necesitar colaborar y comunicarse con miembros de otros departamentos o equipos, y a veces con entidades externas. Por lo tanto, es poco recomendable usar sistemas que crean silos o hacen que el uso compartido de la información sea complicado o indeseado. En lugar de ello, es preferible usar plataformas y aplicaciones que permiten a los empleados comunicarse, colaborar y compartir la información de forma segura y en concordancia con las directivas empresariales.

Proporcionar a los empleados una moderna plataforma de colaboración basada en la nube, les permite elegir e integrar las herramientas que los hacen más productivos y les permite encontrar formas ágiles de trabajo. El uso de Teams en combinación con los controles de seguridad y las directivas de gobierno de la información que protegen la organización puede ayudar a que el personal se comunique y colabore eficazmente.

Teams proporciona un centro de colaboración para la organización. Permite juntar a los usuarios para que trabajen de forma productiva en iniciativas y proyectos comunes. Teams permite a los miembros del equipo dirigir conversaciones de chat de 1:1 y con varios participantes, colaborar y trabajar en coautoría en documentos, así como almacenar y compartir archivos. Teams también facilita las reuniones en línea mediante voz y vídeo empresariales integrados. Teams también se puede personalizar con las aplicaciones de Microsoft, como Microsoft Planner, Microsoft Dynamics 365, Power Apps, Power BI y las aplicaciones de línea de negocios de terceros. Teams está diseñado para que lo utilicen miembros del equipo interno y usuarios externos autorizados que pueden unirse a canales de equipo, participar en conversaciones de chat, tener acceso a archivos almacenados y usar otras aplicaciones

Cada Microsoft Teams está respaldado por un grupo de Microsoft 365. Ese grupo se considera el servicio de suscripción para numerosos servicios de Office 365, incluido Teams. Los grupos de Microsoft 365 se usan para distinguir de forma segura entre "propietarios" y "miembros" y para controlar el acceso a las distintas funciones dentro de Teams. Cuando se une con controles de gobierno adecuados y revisiones de acceso de administración periódicas, Teams solo permite que los miembros y propietarios utilicen canales y capacidades autorizados.

Un escenario habitual en el que Teams es un beneficio para los servicios financieros es al ejecutar proyectos o programas internos. Por ejemplo, en el caso de las instituciones financieras, como los bancos, las empresas de administración de la riqueza, las entidades de crédito y los proveedores de seguros, deben contar con programas de prevención de blanqueo de dinero y otros programas de cumplimiento. Es posible que un equipo multifuncional de TI, líneas de negocios, como las ventas minoristas y la administración de la riqueza, y una unidad de delitos financieros deban compartir datos entre sí y comunicarse por el programa o investigaciones específicas. Tradicionalmente, estos programas usan unidades de red compartidas, pero este método puede presentar numerosos desafíos, entre los que se incluyen:

* Solo una persona puede editar un documento a la vez.
* La administración de la seguridad lleva mucho tiempo, ya que al agregar o quitar usuarios se suele involucrar a TI.
* Los datos permanecen en unidades de red compartidas durante más tiempo de lo necesario.

Teams puede ofrecer un espacio de colaboración para almacenar de forma segura datos confidenciales de los clientes y tener conversaciones entre miembros del equipo donde se puedan discutir temas confidenciales. Varios miembros del equipo pueden editar o colaborar en un único documento al mismo tiempo. El propietario o coordinador del programa puede configurarse como el propietario del equipo y, después, puede agregar y quitar miembros según sea necesario.

Otro escenario común es usar Teams como "sala de datos virtual" para colaborar de forma segura, como al almacenar y administrar documentos. Los miembros del equipo y los sindicatos en la banca de inversiones, la administración de activos o las empresas de capitales privadas pueden colaborar de forma segura en un negocio o una inversión. Los equipos multifuncionales suelen participar en la planeación y finalización de estos acuerdos, y la capacidad de compartir datos y entablar conversaciones de forma segura es una exigencia principal. Compartir de forma segura documentos relacionados con inversores externos también es un requisito clave. Teams proporciona una ubicación segura y totalmente auditable desde la que se pueden almacenar, proteger y compartir datos de la inversión de forma centralizada.

![Un grupo de trabajadores de oficina en una reunión comentan imágenes de una pantalla grande.](../media/m365cO19-ent-dell-latitude13-5951.jpg)
 
### <a name="teams-improve-collaboration-and-reduce-compliance-risk"></a>Teams: mejorar la colaboración y reducir el riesgo de cumplimiento

Microsoft 365 proporciona otras funciones de directiva comunes para Teams mediante el uso de grupos de Microsoft 365 como servicio de suscripción subyacente. Estas directivas pueden ayudar a mejorar la colaboración y satisfacer las necesidades de cumplimiento normativo.

**Las directivas de nomenclatura de grupo de Microsoft 365** ayudan a asegurarse de que los grupos de Microsoft 365 y, por tanto, los equipos, se denominen de acuerdo a la directiva empresarial. Los nombres pueden ser problemáticos si no son adecuados. Por ejemplo, es posible que los empleados no sepan con qué equipos trabajar o compartir información si los nombres no se aplicaron correctamente. Las directivas de nomenclatura de grupos (incluida la compatibilidad con directivas basadas en prefijos y sufijos o las palabras bloqueadas personalizadas) pueden exigir una "higiene" adecuada y evitar el uso de palabras específicas, como palabras reservadas o terminología inapropiada.
  
**Microsoft 365 group expiration policies** help ensure that Microsoft 365 groups and therefore teams, aren't retained for longer periods of time than the organization wants or needs. This capability helps prevent two key information-management issues:

* Proliferación de equipos que no son necesarios ni se usan.
* La retención excesiva de datos que ya no necesita o usa la organización (excepto en casos de conservación o preservación legal).

Administrators can specify an expiration period for Microsoft 365 groups, such as 90, 180, or 365 days. If a service that's backed by a Microsoft 365 group is inactive for the expiration period, group owners are notified. If no action is taken, the Microsoft 365 group and all its related services, including Teams, is deleted.
  
La retención excesiva de los datos que se almacenan en Teams y otros servicios basados en grupos puede suponer riesgos para las organizaciones de servicios financieros. Las directivas de expiración del grupo de Microsoft 365 son una forma recomendada para ayudar a evitar la retención de datos que ya no son necesarios. Combinado con las etiquetas y directivas de retención integradas, Microsoft 365 le ayuda a garantizar que las organizaciones solo retienen los datos necesarios para cumplir con las obligaciones de las directivas corporativas y el cumplimiento normativo.

#### <a name="teams-integrate-custom-requirements-with-ease"></a>Teams: integrar requisitos personalizados con facilidad

Teams permite la creación de equipos sin intervención del administrador de forma predeterminada. Sin embargo, muchas organizaciones reguladas quieren controlar y entender qué canales de colaboración están usando actualmente sus empleados, qué canales pueden contener datos confidenciales y los propietarios de los canales de la organización. Para facilitar estos controles de gobierno, Microsoft 365 permite a la organización deshabilitar la creación de equipos sin intervención del administrador. Al usar herramientas de automatización del proceso empresarial, como Microsoft Power apps y Power Automate, las organizaciones pueden crear e implementar formularios y procesos de aprobación sencillos para que los empleados soliciten la creación de un nuevo equipo. Cuando se aprueba, el equipo se puede aprovisionar automáticamente y se envía un vínculo al solicitante. De esta manera, las organizaciones pueden diseñar e integrar sus requisitos personalizados y controles de cumplimiento en el proceso de creación de equipos.
 
### <a name="acceptable-digital-communication-channels"></a>Canales de comunicación digital aceptables

FINRA [enfatiza que la comunicación digital de las empresas reguladas cumpla con los requisitos de mantenimiento de registros de las Reglas 17a-3 y 17a-4 de la Ley de Intercambio, así como la Serie de reglas 4510 de la FINRA](https://www.finra.org/rules-guidance/key-topics/books-records). FINRA publica un informe anual que contiene conclusiones, observaciones y prácticas útiles clave para ayudar a las organizaciones a mejorar la administración de riesgos y el cumplimiento. En su [Informe sobre la Evaluación de 2019, Hallazgos y Observaciones](https://www.finra.org/rules-guidance/guidance/reports/2019-report-exam-findings-and-observations), FINRA identificó la comunicación digital como área clave en la que las empresas enfrentan dificultades de cumplimiento con los requisitos de supervisión y mantenimiento de registros.

Si una organización permite que sus empleados usen una aplicación específica, como un servicio de mensajería basado en aplicaciones o una plataforma de colaboración, la empresa debe archivar los registros de la empresa y supervisar las actividades y las comunicaciones de los empleados en esa aplicación. Las organizaciones son responsables de la diligencia debida para cumplir con las normas y leyes de títulos y valores de FINRA, y de hacer un seguimiento de las infracciones potenciales de las reglas relacionadas con el uso de estas aplicaciones por parte de los empleados.
  
Entre los procedimientos eficaces recomendados por FINRA se incluyen los siguientes:

* Establecer un programa de gobierno exhaustivo para los canales de comunicación digital. Administrar las decisiones de la organización sobre qué canales de comunicación digital se permiten y definir procesos de cumplimiento para cada canal digital. Supervisar atentamente el cambiante escenario de los canales de comunicación digital y mantener los procesos de cumplimiento actualizados.
* Definir claramente y controlar los canales digitales permitidos. Definir tanto canales digitales aprobados como prohibidos. Bloquear o restringir el uso de canales digitales prohibidos o de características prohibidas en canales digitales, que limiten la capacidad de la organización para cumplir los requisitos de administración y supervisión de registros.
* Proporcionar formación para las comunicaciones digitales. Implementar programas de formación obligatorios antes de que los representantes autorizados puedan acceder a los canales digitales aprobados. La formación permite aclarar las expectativas de la organización en lo que se refiere a las comunicaciones digitales empresariales y personales, así como guiar al personal al usar las características permitidas de cada canal de forma conforme a las normas.

Las conclusiones y observaciones de FINRA para las comunicaciones digitales se relacionan directamente con la capacidad de una organización para cumplir con la [Regla 17a-4 de la SEC](https://www.law.cornell.edu/cfr/text/17/240.17a-4) para conservar todas las comunicaciones relacionadas con la empresa, las Reglas de FINRA [3110](https://www.finra.org/rules-guidance/rulebooks/finra-rules/3110) y [3120](https://www.finra.org/rules-guidance/rulebooks/finra-rules/3120) para la supervisión y la revisión de las comunicaciones, y la Serie de reglas [4510](https://www.finra.org/rules-guidance/rulebooks/finra-rules/4510) para el mantenimiento de registros. La Comisión de Comercio de Futuros de Mercancías (CFTC) promulga requisitos similares bajo la Regla 17 CFR 131. Estas normas se tratan en profundidad más adelante en este artículo.

***Teams, along with the comprehensive suite of Microsoft 365 security and compliance offerings, provides a corporate digital communication channel for financial services institutions to effectively conduct business and comply with regulations.*** The remainder of this article describes how Microsoft 365 built-in capabilities for records management, information protection, information barriers, and supervisory control gives Teams a robust toolset to help meet these regulatory obligations.

## <a name="protect-modern-collaboration-with-microsoft-365"></a>Proteger la colaboración moderna con Microsoft 365

### <a name="secure-user-identities-and-control-access"></a>Identidades de usuario seguras y control de acceso

***La protección del acceso a la información de los clientes, los documentos financieros y las aplicaciones comienza asegurando firmemente las identidades de los usuarios.*** Esto requiere una plataforma segura para que la empresa pueda almacenar y administrar identidades, lo que proporciona un medio de autenticación de confianza y controla dinámicamente el acceso a esas aplicaciones.

A medida que los empleados trabajan, pueden pasar de una aplicación a otra o cambiar entre múltiples ubicaciones y dispositivos. El acceso a los datos debe autenticarse en cada paso durante el proceso. El proceso de autenticación tiene que admitir un protocolo de alto nivel y varios factores de autenticación (como un código de acceso SMS único, una aplicación de autenticación y un certificado) para asegurarse de que las identidades no se han visto comprometidas. Exigir las directivas de acceso basadas en riesgos es fundamental para proteger los datos financieros y las aplicaciones de las amenazas internas, la filtración involuntaria de datos y el robo de datos.

Microsoft 365 proporciona una plataforma de identidades segura en [Azure Active Directory (Azure AD)](/azure/active-directory/), donde las identidades se almacenan de forma centralizada y se administran de forma segura. Azure AD, junto con una variedad de servicios de seguridad de Microsoft 365 relacionados, forma la base para proporcionar a los empleados el acceso que necesitan para trabajar de forma segura, a la vez que protege la organización frente a las amenazas.

[La autenticación multifactor (MFA) de Azure AD](/azure/active-directory/fundamentals/concept-fundamentals-mfa-get-started) está integrada en la plataforma y proporciona una prueba adicional de autenticación que le ayuda a confirmar la identidad del usuario cuando obtenga acceso a aplicaciones y datos financieros confidenciales. Azure MFA necesita al menos dos formas de autenticación, como una contraseña y un dispositivo móvil conocido. Admite varias opciones de autenticación de segundo factor, entre las que se incluyen:

- La aplicación de Microsoft Authenticator
- Un código de acceso de un solo uso entregado a través de SMS
- Un llamado telefónico en el que un usuario tiene que escribir un PIN

Si la contraseña se viese comprometida de alguna forma, un hacker potencial aún necesitaría el teléfono del usuario para obtener acceso a los datos de la organización. Además, Microsoft 365 usa la autenticación moderna como protocolo clave, que ofrece la misma experiencia de autenticación eficaz y enriquecida de los exploradores web a las herramientas de colaboración que usan los empleados en el día a día, como Microsoft Outlook y otras aplicaciones de Microsoft Office.

#### <a name="passwordless"></a>Sin contraseña

Las contraseñas son el eslabón más débil de una cadena de seguridad. Pueden ser un punto único de error si no hay ninguna comprobación adicional. Microsoft admite una amplia variedad de opciones de autenticación para satisfacer las necesidades de las instituciones financieras.

Los métodos *sin contraseña* permiten que la MFA resulte más cómoda para los usuarios. Aunque no todas las MFA carecen de contraseña, las tecnologías sin contraseñas usan la autenticación multifactor. Microsoft, Google y otros líderes del sector han desarrollado estándares para permitir una experiencia de autenticación más sencilla y segura en la web y los dispositivos móviles en un grupo llamado Fast IDentity Online (FIDO). El estándar FIDO2 desarrollado recientemente permite que los usuarios puedan autenticarse de forma fácil y segura sin requerir una contraseña para eliminar la suplantación de identidad.

Los métodos de Microsoft MFA que no tienen contraseñas son:
* [Microsoft Authenticator](/azure/active-directory/user-help/user-help-auth-app-overview): para mayor flexibilidad, comodidad y mejores costos, recomendamos usar la aplicación móvil Microsoft Authenticator. Microsoft Authenticator es compatible con la biometría, las notificaciones de inserción y los códigos de acceso de un solo uso en cualquier aplicación conectada a Azure AD. Está disponible en las tiendas de aplicaciones de Apple y Android.
*  [Windows Hello](/windows/security/identity-protection/hello-for-business/hello-overview): para obtener una experiencia integrada en el equipo PC, recomendamos usar Windows Hello. Usa información biométrica (como una cara o huella digital) para iniciar sesión automáticamente.  
* [Las claves de seguridad de FIDO2](/windows/security/identity-protection/hello-for-business/microsoft-compatible-security-key) ya están disponibles de varios partners de Microsoft: Yubico, Feitian Technologies y HID Global en una llave NFC, USB o clave biométrica.

[El acceso condicional de Azure AD](/azure/active-directory/conditional-access/) ofrece una solución robusta para automatizar las decisiones de control de acceso y exigir las directivas de la organización para proteger los activos de la empresa. Un ejemplo clásico es cuando un programador financiero quiere tener acceso a una aplicación que tiene datos confidenciales de los clientes. Se requieren automáticamente para realizar una autenticación multifactor para tener acceso específico a la aplicación y el acceso debe ser desde un dispositivo administrado por la empresa. El acceso condicional de Azure reúne las señales sobre la solicitud de acceso de un usuario, como las propiedades del usuario, el dispositivo, la ubicación, la red y la aplicación a la que el usuario está intentando acceder. Evalúa dinámicamente los intentos de acceso a la aplicación en directivas configuradas. Si se eleva el riesgo de un usuario o un dispositivo, o no se cumplen otras condiciones, Azure AD puede aplicar automáticamente directivas como requerir MFA, requerir el restablecimiento de una contraseña segura o restringir o bloquear el acceso. Esto permite garantizar que los activos confidenciales de la organización estén protegidos en entornos cambiantes.
 
Azure AD, and the related Microsoft 365 security services, provide the foundation on which a modern cloud collaboration platform can be rolled out to financial institutions so that access to data and applications can be secured, and regulator compliance obligations can be met. These tools provide the following key capabilities:

* Almacenar y administrar identidades de usuario de forma segura y centralizada.
* Usar un protocolo de autenticación eficaz, incluida la autenticación multifactor, para autenticar usuarios en solicitudes de acceso y proporcionar una experiencia de autenticación coherente y robusta en todas las aplicaciones.
* Validar dinámicamente las directivas en todas las solicitudes de acceso, al incorporar múltiples señales en el proceso de toma de decisiones de la directiva, como la identidad, la pertenencia de usuarios y grupos, la aplicación, el dispositivo, la red, la ubicación y la puntuación de riesgo en tiempo real.
* Validar directivas pormenorizadas basadas en el comportamiento de los usuarios y en las propiedades de archivo, y aplicar dinámicamente medidas de seguridad adicionales cuando sea necesario.
* Identificar "shadow IT" en la organización y permitir que los equipos de InfoSec puedan sancionar o bloquear aplicaciones en la nube.
* Supervisar y controlar el acceso a las aplicaciones en la nube de Microsoft o ajenas a Microsoft.
* Proteger de forma proactiva frente a ataques de phishing y ransomware por correo electrónico.

#### <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection

Aunque el acceso condicional protege los recursos de las solicitudes sospechosas, Identity Protection va más allá al ofrecer la detección y corrección continuadas de cuentas de usuarios sospechosos. Identity Protection le mantiene informado en todo momento de comportamientos de inicio de sesión o usuarios sospechosos en su entorno. La respuesta automática impide proactivamente que se abuse de las identidades que hayan sido comprometidas.
 
Identity Protection es una herramienta que permite a las organizaciones llevar a cabo tres tareas clave:

* Automatizar la detección y corrección de riesgos basados en la identidad.
* Investigar riesgos mediante el uso de datos en el portal.
* Exportar datos de detección de riesgos a utilidades de terceros para analizarlos en más profundidad.

Identity Protection usa el conocimiento que Microsoft ha adquirido de su posición en organizaciones con Azure AD, el espacio de consumidores con cuentas de Microsoft y en juegos con Xbox para proteger a los usuarios. Microsoft analiza 65 billones de señales diarias para identificar y proteger a los clientes frente a las amenazas. Las señales generadas por Identity Protection o añadidas a esta pueden incluirse en herramientas como el acceso condicional para tomar decisiones de acceso. También pueden volver a introducirse en una herramienta de administración de eventos e información de seguridad (SIEM) para investigar en mayor detalle en función de las directivas exigidas por la organización.

Identity Protection ayuda a las organizaciones a protegerse de forma automática frente al compromiso de identidades aprovechando la inteligencia en la nube con tecnología de detección avanzada basada en heurística, análisis de comportamiento de usuarios y entidades (UEBA) y aprendizaje automático (ML) en el ecosistema de Microsoft.

![Cinco profesionales de la información ven la presentación de otro.](../media/win17-15021-00-n9.jpg)
 
## <a name="identify-sensitive-data-and-prevent-data-loss"></a>Identificar datos confidenciales y evitar la pérdida de datos

Microsoft 365 permite que todas las organizaciones identifiquen datos confidenciales en la organización a través de una combinación de potentes funciones, entre las que se incluyen:

* **Microsoft Purview Information Protection** para la clasificación basada en el usuario como y para la clasificación automatizada de datos confidenciales.
* **La prevención de pérdida de datos (DLP) de Microsoft Purview** para identificar automáticamente datos confidenciales con tipos de datos confidenciales (es decir, expresiones regulares), así como palabras clave y aplicación de directivas.

**[Microsoft Purview Information Protection](../compliance/information-protection.md)** permite a las organizaciones clasificar documentos y mensajes de correo electrónico de forma inteligente mediante etiquetas de confidencialidad. Los usuarios pueden aplicar manualmente las etiquetas de confidencialidad en documentos en aplicaciones de Microsoft Office y en mensajes de correo electrónico en Outlook. Las etiquetas pueden aplicar automáticamente marcas de documento, protección mediante el cifrado y la exigencia de administración de derechos. Las etiquetas de confidencialidad también se pueden aplicar automáticamente si se configuran directivas que usen palabras clave y tipos de datos confidenciales (como números de tarjeta de crédito, números de seguridad social y números de identidad) para buscar y clasificar automáticamente datos confidenciales.

Además, Microsoft ofrece "clasificadores que se pueden entrenar" que usan modelos de aprendizaje automático para identificar datos confidenciales basándose en el contenido, en lugar de usar solo la coincidencia de patrones o los elementos dentro del contenido. Un clasificador aprende cómo identificar un tipo de contenido al revisar numerosos ejemplos del contenido que se va a clasificar. El entrenamiento de un clasificador comienza por añadir ejemplos de contenido para una categoría determinada. Después de aprender de estos ejemplos, el modelo se prueba añadiendo una mezcla de ejemplos coincidentes y no coincidentes. El clasificador predice si un ejemplo determinado entra o no en la categoría. Después, una persona confirma los resultados, ordenando los positivos, negativos, falsos positivos y falsos negativos para ayudar a aumentar la precisión de las predicciones del clasificador. Cuando se publica el clasificador entrenado, este procesa el contenido de Microsoft SharePoint Online, Exchange Online y OneDrive para la Empresa y clasifica automáticamente el contenido.

La aplicación de etiquetas de confidencialidad a documentos y mensajes de correo electrónico inserta metadatos que identifican la confidencialidad elegida dentro del objeto. La confidencialidad viaja con los datos. Por lo tanto, incluso si un documento con etiqueta se almacena en el escritorio de un usuario o en un sistema local, seguirá estando protegido. Esta funcionalidad permite que otras soluciones de Microsoft 365, como Microsoft Defender for Cloud Apps o dispositivos perimetrales de red, identifiquen datos confidenciales y apliquen automáticamente controles de seguridad. Las etiquetas de confidencialidad tienen la ventaja adicional de informar a los empleados sobre los datos de una organización que se consideran confidenciales y cómo tratar esos datos cuando se reciben.

**[La protección de pérdida de datos (DLP) de Microsoft Purview](../compliance/dlp-learn-about-dlp.md)** identifica automáticamente documentos, correos y conversaciones que contienen datos confidenciales mediante el análisis en busca de datos confidenciales y la aplicación de directivas en esos objetos. Las directivas se aplican a los documentos de SharePoint y OneDrive para la Empresa. También se aplican cuando los usuarios envían correo electrónico y en los chats o conversaciones de canales de Teams. Las directivas pueden configurarse para buscar palabras clave, tipos de datos confidenciales, etiquetas de retención y si los datos se comparten dentro de la organización o externamente. Se proporcionan controles para ayudar a las organizaciones a ajustar las directivas DLP para reducir los falsos positivos. Cuando se encuentra información confidencial, las sugerencias de directiva personalizables se pueden mostrar a los usuarios de las aplicaciones de Microsoft 365 para informarles de que su contenido contiene datos confidenciales y proponer acciones de corrección. Las directivas también pueden impedir que los usuarios accedan a documentos, compartan documentos o envíen mensajes de correo electrónico que contengan determinados tipos de datos confidenciales. Microsoft 365 admite más de 100 tipos de datos confidenciales integrados. Las organizaciones pueden configurar tipos de datos confidenciales personalizados para cumplir con sus directivas.

La implementación de directivas DLP y Microsoft Purview Information Protection para las organizaciones requiere un planeamiento cuidadoso y un programa de aprendizaje para los usuarios, de modo que los empleados comprendan el esquema de clasificación de datos de la organización y los tipos de datos que se consideran confidenciales. Proporcionar a los empleados herramientas y programas educativos que les permitan identificar datos confidenciales y comprender cómo administrarlos los convierte en parte de la solución para reducir los riesgos de seguridad de la información.

Las señales generadas por Identity Protection o añadidas también pueden incluirse en herramientas como el acceso condicional para tomar decisiones de acceso o a una herramienta de administración de eventos e información de seguridad (SIEM) para investigar en función de las directivas exigidas por la organización.

Identity Protection ayuda a las organizaciones a protegerse de forma automática frente al compromiso de identidades aprovechando la inteligencia en la nube con tecnología de detección avanzada basada en heurística, análisis de comportamiento de usuarios y entidades y aprendizaje automático en el ecosistema de Microsoft.

![Se muestra un profesional de la información delante de un gran número de monitores.](../media/clo1718-portrait-006.jpg)

## <a name="defend-the-fortress"></a>Defender la fortaleza

Microsoft ha lanzado recientemente la solución Microsoft 365 Defender de Microsoft, que está diseñada para proteger la organización moderna frente al escenario cambiante de amenazas. Al usar Intelligent Security Graph, la solución de Protección contra amenazas ofrece seguridad completa integrada frente a varios tipos de ataques.

### <a name="the-intelligent-security-graph"></a>[Intelligent Security Graph](https://www.microsoft.com/security/business/intelligence) 
Los servicios de seguridad de Microsoft 365 usan la tecnología de Intelligent Security Graph. Para combatir las amenazas informáticas, Intelligent Security Graph usa análisis avanzados para relacionar las señales de seguridad e inteligencia de amenazas de Microsoft y sus asociados. Microsoft opera servicios globales a gran escala, al obtener billones de señales de seguridad que impulsan capas de protección en la pila. Los modelos de aprendizaje automático evalúan esta inteligencia y la información de las amenazas y señales se comparte entre los productos y servicios. Esto nos permite detectar y responder rápidamente a las amenazas y enviar a los clientes las alertas y la información para corregirlas. Nuestros modelos de aprendizaje automáticos se entrenan y actualizan continuamente con nueva información, ayudando a crear productos más seguros y ofrecer una seguridad más proactiva.

[Microsoft Defender para Office 365](../security/office-365-security/defender-for-office-365.md) ofrece un servicio integrado de Microsoft 365 que protege a las organizaciones frente a vínculos malintencionados y malware ocultos en documentos de Office y correos. Uno de los tipos de ataque más comunes que afecta a los usuarios en estos momentos son los ataques de suplantación de identidad de correo electrónico. Estos ataques pueden dirigirse a usuarios específicos y ser muy convincentes, con alguna solicitud que pida al usuario que haga clic en un vínculo malintencionado o que abra un archivo adjunto que contenga malware. Cuando un equipo está infectado, el atacante puede robar las credenciales del usuario y desplazarse por la organización o robar mensajes de correo electrónico y datos para buscar información confidencial. Microsoft Defender para Office 365 es compatible con datos adjuntos seguros y vínculos seguros mediante la evaluación de documentos y vínculos en el momento de hacer clic para detectar intenciones maliciosas y bloquear el acceso. Los datos adjuntos de correo se abren en un espacio aislado protegido antes de entregarse al buzón de un usuario. También examina vínculos en documentos de Office en busca de URL malintencionadas. Microsoft Defender para Office 365 también protege vínculos y archivos en SharePoint Online, OneDrive para la Empresa y Teams. Si se detecta un archivo malintencionado, Microsoft Defender para Office 365 lo bloquea automáticamente para reducir los posibles daños.

[Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) es una plataforma de seguridad de punto de conexión unificada para la protección preventiva, la detección posterior a la vulneración y la respuesta e investigación automatizadas. Defender para punto de conexión ofrece funciones integradas para detectar y proteger los datos confidenciales en los puntos de conexión de la empresa.

[Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security) permite a las organizaciones aplicar directivas en un nivel granular y detectar anomalías en el comportamiento en función de los perfiles de usuario individuales que se definen automáticamente con el aprendizaje automático. Las directivas de Defender for Cloud Apps se pueden basar en directivas de acceso condicional de Azure para proteger los activos confidenciales de la empresa al evaluar otras señales relacionadas con el comportamiento del usuario y las propiedades de los documentos a los que se accede. Con el tiempo, Defender for Cloud Apps aprende el comportamiento habitual para cada empleado con respecto a los datos a los que acceden y a las aplicaciones que usan. Basándose en patrones de comportamiento aprendidos, las directivas pueden exigir de forma automática controles de seguridad si un empleado actúa fuera de ese perfil de comportamiento. Por ejemplo, si un empleado generalmente accede a una aplicación de contabilidad entre las 9:00 y las 17:00 de lunes a viernes, pero de repente comienza a acceder a esa aplicación un domingo por la tarde, Defender for Cloud Apps puede aplicar dinámicamente directivas para requerir que el usuario vuelva a autenticarse. Esto permite garantizar que las credenciales del usuario no se hayan visto comprometidas. Defender for Cloud Apps también pueden ayudar a identificar "shadow IT" en la organización, lo que permite a los equipos de seguridad de la información asegurarse de que los empleados usan herramientas autorizadas cuando trabajan con datos confidenciales. Por último, Defender for Cloud Apps puede proteger datos confidenciales en cualquier lugar de la nube, incluso fuera de la plataforma de Microsoft 365. Permite a las organizaciones autorizar (o no autorizar) aplicaciones externas específicas en la nube, controlar el acceso y supervisar el uso.
 
[Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp) is a cloud-based security solution that leverages your on-premises Active Directory signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization. AATP enables SecOp analysts and security professionals detect advanced attacks in hybrid environments to:
* Supervisar usuarios, el comportamiento de las entidades y las actividades mediante el análisis basado en aprendizaje.
* Proteger las identidades de usuario y las credenciales almacenadas en Active Directory.
* Identificar e investigar actividades de usuarios sospechosas y ataques avanzados en la cadena de eliminación.
* Proporcionar información clara sobre el incidente en una escala de tiempo simple para una evaluación rápida.

![The office workers meet in a small conference room. One gives a presentation.](../media/clo1717-corporate-office-021.jpg)
 
## <a name="govern-data-and-manage-records"></a>Gobierno de datos y administración de registros

Las instituciones financieras deben conservar sus registros y su información según sus obligaciones normativas, jurídicas y comerciales, como se representa en la programación de retención de su empresa. Por ejemplo, la [SEC exige períodos de retención](https://www.sec.gov/rules/interp/34-47806.htm) de entre tres y seis años, basándose en el tipo de registro, con accesibilidad inmediata para los dos primeros años. Las organizaciones se enfrentan a los riesgos legales y normativos si los datos se retienen menos tiempo (se descartan muy anticipadamente) y ahora también administran las normas que exigen la eliminación cuando ya no se necesita información. Una estrategia de administración de registros eficaz enfatiza un enfoque práctico y coherente para que la información se elimine de forma adecuada al tiempo que se reducen los costes y los riesgos para la organización.
 
In addition, regulatory mandates from the New York State Department of Financial Services require covered entities to maintain policies and procedures for disposal of nonpublic information. 23 NYCRR 500, Section 500.13, Limitations on Data Retention requires that "As part of its cybersecurity program, each Covered Entity shall include policies and procedures for the secure disposal on a periodic basis of any Nonpublic Information identified in section 500.01(g)(2)-(3) of this Part that is no longer necessary for business operations or for other legitimate business purposes of the Covered Entity, except where such information is otherwise required to be retained by law or regulation."
 
Las instituciones financieras administran una gran cantidad de datos. Y algunos períodos de retención se activan por eventos, como un contrato que expira o un empleado que abandona la organización. En esta atmósfera, puede resultar complicado aplicar directivas de retención de registros. Los métodos para asignar períodos de retención de registros de forma exacta en documentos de la organización pueden variar. Algunos aplican directivas de retención más amplias o aprovechan técnicas de clasificación y aprendizaje automáticos. Otros identifican un enfoque que necesita un proceso más pormenorizado que asigna períodos de retención de forma individual en cada documento.

***Microsoft 365 ofrece funciones flexibles para definir las etiquetas de retención y las directivas para implementar de forma inteligente los requisitos de administración de registros.*** Un administrador de registros define una etiqueta de retención que representa un "tipo de registro" en una programación de retención tradicional. La etiqueta de retención contiene la configuración que define estos detalles:

- Cuánto tiempo se retiene un registro
- Qué ocurre cuando expira el período de retención (eliminar el documento, iniciar una revisión de disposición o no realizar ninguna acción)
-  Qué provoca que comience el período de retención (fecha de creación, fecha de la última modificación, fecha de la etiqueta o un evento) y marca el documento o correo electrónico como un registro (lo que significa que no se puede editar ni eliminar).

Las etiquetas de retención se publican en sitios de SharePoint o OneDrive, buzones de Exchange y grupos de Microsoft 365. Los usuarios pueden aplicar manualmente las etiquetas de retención a documentos y mensajes de correo electrónico. Los administradores de registros pueden usar la inteligencia para aplicar las etiquetas automáticamente. Las funciones inteligentes se pueden basar en [más de 90 tipos de información confidencial](../compliance/content-search.md) (como el código ABA, el número de cuenta bancaria estadounidense o el número de la seguridad social de Estados Unidos). También son personalizables en función de palabras clave o datos confidenciales que se encuentran en documentos o mensajes de correo electrónico, como números de tarjeta de crédito u otra información de identificación personal, o en base a los metadatos de SharePoint. Para datos que no son fáciles de identificar mediante la coincidencia manual o automatizada de patrones, se pueden usar clasificadores que se pueden entrenar para clasificar documentos de forma inteligente en base a técnicas de aprendizaje automático.
 
La **Comisión de valores y bolsa (SEC)** requiere que los corredores de bolsa y otras instituciones financieras reguladas conserven todas las comunicaciones relacionadas con la empresa. Estos requisitos se aplican a muchos tipos de comunicación y datos, como correos electrónicos, documentos, mensajes instantáneos, faxes y mucho más. **La norma 17a-4 de la SEC** define los criterios que deben cumplir estas organizaciones para almacenar registros en un sistema de almacenamiento electrónico de datos. En 2003, la SEC emitió un comunicado que clarifica estos requisitos. Incluyó los siguientes criterios:

* Los datos que conserva un sistema de almacenamiento electrónico deben ser no regrabables y no eliminables. Esto es lo que se conoce como un requisito de "escribir una vez, leer muchas veces" (WORM por sus siglas en inglés).
* El sistema de almacenamiento debe poder almacenar datos que superen el período de retención requerido por la norma, en el caso de una citación u otra orden legal.
* Ninguna organización vulneraría la exigencia en el párrafo (f)(2)(ii)(A) de la regla si usa un sistema de almacenamiento electrónico que impide que se sobrescriba, se borre o se altere de algún otro modo el registro durante el período de retención requerido mediante el uso de los códigos integrados de control de hardware y software.
* Los sistemas de almacenamiento electrónico que simplemente "mitigan" el riesgo de que un registro se sobrescriba o se elimine (por ejemplo, al depender del control de acceso), no cumplen con los requisitos de la regla.

To help financial institutions meet the requirements of SEC rule 17a-4, Microsoft 365 provides a combination of capabilities related to how data is retained, policies are configured, and data is stored within the service. These include:

* **Preservación de datos (Norma 17a-4 (a), (b)(4))**: las etiquetas de retención y las directivas son flexibles para satisfacer las necesidades de la organización, y se pueden aplicar de forma automática o manual a diferentes tipos de datos, documentos e información. Se admiten una amplia variedad de tipos de datos y comunicaciones, incluidos los documentos de SharePoint y OneDrive para la Empresa, datos de buzones de Exchange Online y datos en Teams.  
* **Un formato que no se puede volver a escribir y que no se puede eliminar (Regla 17a-4 (f)(2)(ii)(A))**: la capacidad de bloqueo de conservación para las directivas de retención permite a los administradores y administradores de registros configurar las directivas de retención para que sean restrictivas, de modo que ya no se puedan modificar. Esto prohíbe que se pueda quitar, deshabilitar o modificar la directiva de retención de ninguna manera. Esto quiere decir que, una vez que el bloqueo de conservación está habilitado, no se puede deshabilitar y no hay ningún método mediante el que los datos a los que se haya aplicado la directiva de retención se puedan sobrescribir, modificar o eliminar durante el período de retención. Además, el período de retención no se puede acortar. Sin embargo, el período de retención se puede alargar cuando existe un requisito legal para continuar la retención de datos.<br/><br/>Cuando se aplica un bloqueo de conservación a una directiva de retención, se restringen las acciones siguientes:

  - The retention period of the policy can only be increased. It can't be shortened.
  - Se pueden agregar usuarios a la directiva, pero no se podrán quitar los usuarios existentes configurados en la directiva.
   - La directiva de retención no puede ser eliminada por ningún administrador dentro de la organización.
 
  El bloqueo de conservación ayuda a garantizar que ningún usuario, ni siquiera administradores con los niveles más altos de acceso con privilegios, pueda cambiar la configuración, modificar, sobrescribir o eliminar los datos que se han almacenado, trasladando el archivado en Microsoft 365 en línea con las instrucciones proporcionadas en la versión 2003 de SEC.

* **Calidad, precisión y comprobación del almacenamiento, la serialización y la indización de datos (Regla 17a-4(f)(2)(ii)(B) y (C))**: cada carga de trabajo de Office 365 contiene capacidades para comprobar de forma automática la calidad y la precisión del proceso de grabación de datos en medios de almacenamiento. Además, los datos se almacenan con metadatos y marcas de tiempo para asegurar que la indexación sea suficiente para permitir la búsqueda y la recuperación de los datos de forma eficaz.
 
* **Almacenamiento independiente para las copias duplicadas (Regla 17a-4 (f) (3(iii))**: el servicio en la nube de Office 365 almacena copias duplicadas de los datos como un aspecto fundamental de su elevada disponibilidad. Esto se logra mediante la implementación de redundancia en todos los niveles del servicio, incluido el nivel físico en todos los servidores, en el nivel de servidor dentro del centro de datos y en el nivel de servicio para los centros de datos geográficamente dispersos.

* **Datos descargables y accesibles (Regla 17a-4 (f)(2)(ii)(D))**: Office 365 generalmente permite que se busquen datos rotulados para la retención, se puede acceder a ellos y descargarlos en el lugar. Y permite que los datos de los archivos de Exchange Online se puedan buscar mediante el uso de características de eDiscovery integradas. Se pueden descargar datos según sea necesario en formatos estándar, como EDRML y PST.
 
* **Requisitos de auditoría (Regla 17a-4(f)(3)(v))**: Office 365 proporciona un registro de auditoría para cada una de las acciones administrativas y de usuario que modifiquen objetos de datos, configure o modifique las directivas de retención, realice búsquedas eDiscovery o modifique los permisos de acceso. Office 365 mantiene una traza de auditoría integral, que incluye datos de quién realizó una acción, cuándo la realizó, detalles de la acción y los comandos que se realizaron. Luego, el registro de auditoría se puede obtener e incluir como parte de procesos de auditoría formal cuando sea necesario.

Por último, la Regla 17a-4 exige a las organizaciones que conserven los registros de muchos tipos de transacciones para que se pueda acceder a ellas inmediatamente durante dos años. Los registros deben retenerse durante entre tres y seis años más con acceso no inmediato. Los registros duplicados también deben mantenerse durante el mismo periodo en una ubicación fuera del sitio. Las funciones de administración de registros de Microsoft 365 permiten que los registros se retengan de forma que no se puedan modificar ni eliminar, pero que se pueda acceder a ellos fácilmente durante un período de tiempo que controle el administrador de registros. Estos períodos pueden abarcar días, meses o años, en función de las obligaciones de cumplimiento normativo de la organización.
 
Previa solicitud, Microsoft proporcionará una carta de atestación del cumplimiento con la regla 17a-4 de la SEC cuando lo requiera una organización.

In addition, these capabilities also help Microsoft 365 meet storage requirements for [CFTC Rule 1.31(c)-(d)](https://www.cftc.gov/sites/default/files/opa/press99/opa4266-99-attch.htm) from the **U.S. Commodity Futures Trading Commission** and [FINRA Rule Series 4510](https://www.finra.org/rules-guidance/rulebooks/finra-rules/4511) from the **Financial Industry Regulatory Authority.** Collectively, these rules represent the most-prescriptive guidance globally for financial institutions to retain records.

Hay más información sobre cómo Microsoft 365 cumple con la regla SEC 17a-4 y otras normativas disponibles en el documento de descarga [Office 365 - Evaluación de Cohasset - regla SEC 17a-4(f) - Almacenamiento inmutable para SharePoint, OneDrive, Exchange, Teams y Yammer (2022)](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).

## <a name="establish-ethical-walls-with-information-barriers"></a>Establecer zona de protección de datos confidenciales con barreras de información

Las instituciones financieras pueden estar sujetas a normas que impiden que los empleados de determinados roles puedan cambiar la información o colaborar con otros roles. Por ejemplo, FINRA ha publicado las reglas 2241 (b)(2)(G), 2242 (b)(2)(D), (b)(2)(H)(ii) y (b)(2)(H)(iii) que exigen a los miembros:

"(G) establecer barreras de la información u otros tipos de salvaguardia institucionales diseñados para asegurar que los analistas de investigación estén aislados de la revisión, presión o supervisión por parte de personas que participen en actividades de servicios bancarios de inversión u otras personas, incluyendo al personal de ventas y comercio, que podría verse sesgado en su juicio o supervisión"; y "(H) establecer barreras de información u otros tipos de salvaguardia institucional especialmente diseñados para asegurar que los analistas de investigación de deudas estén aislados de la revisión, la presión o la supervisión por parte de personas que participen en: (i) servicios bancarios de inversiones; (ii) transacciones importantes o actividades de ventas y transacciones; y (iii) otras personas cuyo juicio o supervisión podría verse sesgado.

Por último, estas reglas requieren que las organizaciones establezcan directivas e implementen barreras en la información entre las funciones involucradas en servicios bancarios, ventas o transacciones que intercambien la información y las comunicaciones con analistas.

[Las barreras de la información](../compliance/information-barriers.md) ofrecen la capacidad para establecer límites éticos en el entorno de Office 365, lo que permite a los administradores de cumplimiento u otros administradores autorizados definir directivas que permiten o impiden las comunicaciones entre grupos de usuarios en Teams. Las barreras de información realizan comprobaciones en acciones específicas para evitar la comunicación no autorizada. Las barreras de información también pueden restringir la comunicación en escenarios en los que los equipos internos estén trabajando en fusiones o adquisiciones, en transacciones confidenciales o con información interna confidencial que deba tener una restricción severa.

Las barreras de la información son compatibles con conversaciones y archivos en Teams. Pueden impedir los siguientes tipos de acciones relacionadas con las comunicaciones para ayudar a cumplir con las normativas de FINRA:

* Buscar un usuario
* Agregar un miembro a un equipo o seguir participando con otro miembro de un equipo
* Iniciar o continuar una sesión de chat
* Iniciar o continuar un chat grupal
* Invitar a alguien a unirse a una reunión
* Compartir una pantalla
* Realizar una llamada

## <a name="implement-supervisory-control"></a>Implementar control de supervisión

Financial institutions are typically required to establish and maintain a supervisory function within their organizations to monitor the activities of employees and to help it achieve compliance with applicable securities laws. Specifically, FINRA has established these supervision requirements:
 
* [FINRA Rule 3110 (Supervision)](https://www.finra.org/rules-guidance/rulebooks/finra-rules/3110) requires firms to have written supervisory procedures (WSPs) to supervise activities of its employees and the types of businesses in which it engages. In addition to other requirements, procedures must include:

   - Supervisión de personal de supervisión
   - Revisión del banco de inversión, negocios de valores, comunicaciones internas e investigaciones internas de la empresa
   - Revisión de las transacciones para el intercambio de información privilegiada
   - Revisión de quejas y correspondencia

   Los procedimientos deben describir las personas responsables de las revisiones, la actividad de supervisión que realizará cada persona, la frecuencia de revisión y los tipos de documentación o comunicaciones que se revisan.
 
* [La Regla 3120 de FINRA (Sistema de control de supervisión)](https://www.finra.org/rules-guidance/rulebooks/finra-rules/3120) requiere que las empresas tengan un sistema de políticas y procedimientos de control de vigilancia (SCP) que valide sus procedimientos de supervisión escritos, según se define en la Regla 3110. Las empresas no solo deben tener WSP, sino que también directivas que prueben estos procedimientos de anualmente para validar su capacidad para asegurar el cumplimiento de las leyes y normativas de los valores aplicables. Se pueden usar metodologías basadas en riesgo y muestreo para definir el ámbito de las pruebas. Entre otros requisitos, esta regla requiere que las empresas proporcionen un informe anual a la dirección de la empresa que incluya un resumen de los resultados de las pruebas y cualquier excepción importante o procedimientos modificados en respuesta a los resultados de las pruebas.

![Un trabajador de oficina ve un gráfico y tablas en una pantalla mientras otros trabajadores se encuentran en segundo plano.](../media/wco18-desk-work-002.jpg)
 
### <a name="communication-compliance"></a>Cumplimiento de las comunicaciones

[Cumplimiento de comunicaciones de Microsoft Purview](/microsoft-365/compliance/communication-compliance) es una solución de cumplimiento que ayuda a minimizar los riesgos de comunicación, ya que le ayuda a detectar, investigar y actuar sobre mensajes inadecuados en su organización. Las directivas personalizadas y predefinidas le permiten examinar las comunicaciones internas y externas para ver las coincidencias de directivas y que los revisores designados puedan examinarlas. Los revisores pueden investigar los mensajes de correo electrónico analizados, Microsoft Teams, Yammer o las comunicaciones de terceros de su organización y tomar medidas apropiadas para asegurarse de que cumplen con los estándares de mensajería de su organización.
  
El cumplimiento de comunicaciones ofrece informes que permiten auditar actividades de revisión de directivas en función de la directiva y el revisor. Los informes están disponibles para validar que las directivas funcionan tal como se define en las directivas escritas de la organización. También se pueden usar para identificar las comunicaciones que necesitan revisarse y aquellas que no cumplen con las directivas corporativas. Por último, todas las actividades relacionadas con la configuración de directivas y la revisión de las comunicaciones se auditan en el registro de auditoría unificado de Office 365. Como resultado, el cumplimiento de comunicaciones también ayuda a las instituciones financieras a cumplir con la regla 3120 de FINRA.

Además de cumplir con las reglas de FINRA, el cumplimiento de comunicaciones permite a las organizaciones detectar y actuar sobre las comunicaciones que pueden verse afectadas por otros requisitos legales, directivas corporativas y estándares éticos. El cumplimiento de las comunicaciones ofrece clasificadores integrados de amenazas, acoso y blasfemias que ayudan a reducir los falsos positivos al revisar las comunicaciones, lo que permite ahorrar tiempo a los revisores durante el proceso de investigación y corrección. También permite a las organizaciones reducir los riesgos al detectar las comunicaciones cuando se producen cambios confidenciales en la organización, como fusiones y adquisiciones o cambios de liderazgo.

![Un trabajador de la información se centra en una pantalla.](../media/msc16-slalom-004.jpg)
 
## <a name="protect-against-data-exfiltration-and-insider-risk"></a>Protegerse contra la exfiltración de datos y los riesgos internos

Un peligro común para las empresas es la exfiltración de datos o el acto de extraer datos de una organización. Este riesgo puede suponer un problema importante para las instituciones financieras debido al carácter confidencial de la información a la que se puede acceder a diario. Con la creciente cantidad de canales de comunicación disponibles y la proliferación de herramientas para mover los datos, por lo general se requieren funcionalidades avanzadas para mitigar el riesgo de pérdida de datos, infracciones de directivas y riesgos internos.

### <a name="insider-risk-management"></a>Administración de riesgos internos

Permitir que los empleados utilicen herramientas de colaboración en línea a las que se puede tener acceso desde cualquier lugar, supone un riesgo inherente para la organización. Los empleados pueden filtrar datos, de forma involuntaria o malintencionada, a atacantes o competidores.  O bien, pueden exfiltrar datos para uso personal o llevarlos con ellos a un futuro empleador. Estos escenarios presentan serios riesgos para las instituciones de servicios financieros tanto desde el punto de vista de seguridad como del cumplimiento. Identificar estos riesgos cuando se producen y mitigarlos rápidamente requiere herramientas inteligentes para la recopilación de datos y colaboración entre departamentos como los departamentos legal, de seguridad de la información y de Recursos Humanos.

La [Administración de riesgos internos de Microsoft Purview](/microsoft-365/compliance/insider-risk-management) es una solución de cumplimiento que ayuda a minimizar los riesgos internos, ya que le permite detectar, investigar y actuar en actividades malintencionadas e involuntarias en su organización. Las directivas de riesgos internos le permiten definir los tipos de riesgos a identificar y detectar en su organización, incluida la acción sobre casos y la elevación de casos a Microsoft eDiscovery (Premium) si es necesario. Los analistas de riesgo de su organización pueden tomar rápidamente las medidas adecuadas para asegurarse de que los usuarios cumplen los estándares de cumplimiento de su organización.  

Por ejemplo, la administración de riesgos internos puede correlacionar las señales de los dispositivos de un usuario (como la copia de archivos a una unidad USB o el envío de un correo electrónico a una cuenta de correo electrónico personal) con actividades de servicios en línea (como el correo electrónico de Office 365, SharePoint Online, Microsoft Teams o OneDrive para la Empresa) para identificar los patrones de filtración de datos. También puede correlacionar estas actividades con los empleados que abandonan una organización, que es un patrón común de exfiltración de datos. Puede detectar varias actividades y comportamientos potencialmente peligrosos a lo largo del tiempo. Cuando surgen patrones comunes, se pueden generar alertas y ayudar a los investigadores a centrarse en las actividades clave para comprobar la violación de la directiva con un alto grado de confianza. La administración de riesgos internos puede anonimizar los datos de los investigadores para ayudar a cumplir con las normas de privacidad de datos, a la vez que se siguen realizando actividades clave que les ayudan a realizar investigaciones de forma eficaz. Permite que los investigadores empaqueten y envíen con seguridad datos de actividad clave a los departamentos de RR. HH. y jurídicos, siguiendo los flujos de trabajo de escalamiento comunes para establecer casos para acciones correctivas.

La administración de riesgos internos incrementa significativamente las funciones de las organizaciones para detectar e investigar los riesgos internos, a la vez que permite a las organizaciones seguir satisfaciendo las normativas de privacidad de datos y seguir las rutas de escalación establecidas cuando los casos requieren una acción de nivel superior.

![Un trabajador de un centro de llamadas en un cubículo escribe mientras ve una pantalla.](../media/clo17-call-center-006.jpg)

### <a name="tenant-restrictions"></a>Restricciones de espacio empresarial

Las organizaciones que trabajan con datos confidenciales y ponen énfasis estricto en la seguridad suelen querer controlar los recursos en línea a los que pueden acceder los usuarios. Al mismo tiempo, quieren permitir una colaboración segura a través de servicios en línea como Office 365. Como consecuencia, el control de los entornos de Office 365 a los que los usuarios pueden tener acceso se convierte en un reto, ya que los entornos de Office 365 no corporativos se pueden usar para la exfiltración de datos de dispositivos corporativos, ya sea malintencionadamente o por error. Tradicionalmente, las organizaciones restringen los dominios o las direcciones IP a los que los usuarios pueden acceder desde dispositivos corporativos. Pero esto no funciona en un mundo que prioriza la nube, donde los usuarios tienen que tener acceso a los servicios de Office 365 de forma legítima.

Microsoft 365 proporciona a las [restricciones](/azure/active-directory/manage-apps/tenant-restrictions) del espacio empresarial la capacidad de afrontar este desafío. Las restricciones de espacio empresarial pueden configurarse para restringir el acceso a los espacios empresariales externos de Office 365 que usan identidades malintencionadas (identidades que no forman parte de su directorio corporativo). En la actualidad, las restricciones de espacios empresariales se aplican en todo el espacio empresarial, lo que permite el acceso solo a esos espacios empresariales que aparecen en la lista que configure. Microsoft continúa desarrollando esta solución para incrementar la granularidad del control y mejorar las protecciones que proporciona.

![GRÁFICO.](../media/clo1717-corporate-office-001.jpg)

## <a name="conclusion"></a>Conclusión

Microsoft 365 y Teams proporcionan una solución completa e integrada para las empresas de servicios financieros, lo que permite funciones sencillas y eficientes de colaboración y comunicación basadas en la nube en toda la empresa. Mediante el uso de las tecnologías de seguridad y cumplimiento de Microsoft 365, las instituciones pueden operar de forma más segura y compatible con efectivos controles de seguridad para proteger los datos, las identidades, los dispositivos y las aplicaciones frente a diversos riesgos operativos, incluido riesgos ciberseguridad e internos. Microsoft 365 proporciona una plataforma fundamentalmente segura en la que las organizaciones de servicios financieros pueden lograr más a la vez que protege la empresa, los empleados y los clientes.
