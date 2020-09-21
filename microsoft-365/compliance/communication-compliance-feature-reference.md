---
title: Referencia de la característica de cumplimiento de comunicación
description: Referencia de características para el cumplimiento de la comunicación en Microsoft 365. Obtenga información detallada y especificaciones para cada uno de los componentes de la característica.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 757b1fcdae69e98ec45bb29e669ceda8f8cb8f98
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "48131640"
---
# <a name="communication-compliance-feature-reference"></a>Referencia de la característica de cumplimiento de comunicación

## <a name="policies"></a>Directivas

>[!Important]
>No se admite el uso de PowerShell para crear y administrar directivas de cumplimiento de comunicaciones. Para crear y administrar estas directivas, debe usar los controles de administración de directivas de la [solución Microsoft 365 Communication Compliance](https://compliance.microsoft.com/supervisoryreview).

Puede crear directivas de cumplimiento de comunicaciones para organizaciones de Microsoft 365 en el centro de cumplimiento de Microsoft 365. Las directivas de cumplimiento de comunicaciones definen qué comunicaciones y usuarios están sujetos a revisión en la organización, definen las condiciones personalizadas que deben cumplir las comunicaciones y especifican quién debe realizar revisiones. Los usuarios que tengan asignado el rol de *Administrador de cumplimiento de comunicaciones* pueden configurar directivas y cualquier persona que tenga este rol asignado puede tener acceso a la página cumplimiento de **comunicaciones** y a la configuración global del centro de cumplimiento de Microsoft 365. Si es necesario, puede exportar el historial de modificaciones de una directiva a un archivo. csv que también incluye el estado de las alertas revisión pendiente, elementos escalados y elementos resueltos. No se puede cambiar el nombre de las directivas y eliminarse cuando ya no se necesiten.

>[!NOTE]
>Las directivas de supervisión creadas en el centro de seguridad & cumplimiento para las suscripciones de Office 365 no se pueden migrar a Microsoft 365. Si va a migrar desde una suscripción de Office 365 a una suscripción de Microsoft 365, tendrá que crear nuevas directivas de cumplimiento de comunicaciones para reemplazar las directivas de supervisión existentes.

## <a name="policy-templates"></a>Plantillas de directiva

Las plantillas de Directiva son opciones de directiva predefinidas que puede usar para crear rápidamente directivas para cumplir escenarios de cumplimiento comunes. Cada una de estas plantillas tiene diferencias en las condiciones y el ámbito, y todas las plantillas usan los mismos tipos de señales de detección. Puede elegir entre las siguientes plantillas de directiva:

|**Área**|**Plantilla de Directiva**|**Detalles**|
|:-----|:-----|:-----|
| **Idioma ofensivo y Antiacoso** | Supervisar las comunicaciones para un lenguaje ofensivo | -Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype empresarial <br> -Direction: entrante, saliente, interno <br> -Porcentaje de revisión: 100% <br> -Condiciones: clasificador de idioma ofensivo |
| **Información confidencial** | Supervisión de las comunicaciones para información confidencial | -Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype empresarial <br> -Direction: entrante, saliente, interno <br> -Porcentaje de revisión: 10% <br> -Condiciones: información confidencial, patrones de contenido prejuntos y tipos, opción de diccionario personalizado, datos adjuntos mayores de 1 MB |
| **Cumplimiento normativo** | Supervisión de las comunicaciones para obtener información relacionada con el cumplimiento de normativas financieras | -Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype empresarial <br> -Direction: entrante, saliente <br> -Porcentaje de revisión: 10% <br> -Condiciones: opción de diccionario personalizado, datos adjuntos mayores de 1 MB |

## <a name="permissions-preview"></a>Permisos (versión preliminar)

>[!Important]
>De forma predeterminada, los administradores globales no tienen acceso a las características de cumplimiento de comunicaciones. Los roles asignados en este paso son necesarios antes de que se pueda tener acceso a las características de cumplimiento de la comunicación.

Hay cinco grupos de roles usados para configurar los permisos para administrar las características de cumplimiento de comunicaciones. Para que el cumplimiento de la **comunicación** esté disponible como una opción de menú en el centro de cumplimiento de Microsoft 365 y para continuar con estos pasos de configuración, debe estar asignado a los grupos de roles de *cumplimiento normativo de comunicaciones* o *Administración cumplimiento de comunicaciones* . Para obtener acceso y administrar las características de cumplimiento de comunicaciones tras la configuración inicial, los usuarios deben pertenecer al menos a un grupo de roles de cumplimiento de la comunicación.

En función de cómo desee administrar las directivas y alertas de comunicación, deberá asignar usuarios a grupos de roles específicos. Tiene la opción de asignar usuarios con responsabilidades de cumplimiento diferentes a grupos de roles específicos para administrar diferentes áreas de características de cumplimiento de comunicaciones. O bien, puede decidir asignar todas las cuentas de usuario para administradores, analistas, investigadores y visores designados al grupo de funciones de *cumplimiento de comunicaciones* . Use un grupo de roles único o varios grupos de roles para ajustarse mejor a los requisitos de administración de cumplimiento.

Elija entre estas opciones de grupo de roles al configurar el cumplimiento de la comunicación:

|**Rol**|**Permisos de funciones**|
|:-----|:-----|
| **Cumplimiento de la comunicación** | Use este grupo de roles para administrar el cumplimiento de la comunicación de su organización en un único grupo. Al agregar todas las cuentas de usuario para administradores, analistas, investigadores y visores designados, puede configurar los permisos de cumplimiento de comunicaciones en un único grupo. Este grupo de roles contiene todos los roles de permisos de cumplimiento de comunicaciones. Esta configuración es la forma más sencilla de empezar rápidamente con el cumplimiento de la comunicación y es una buena opción para las organizaciones que no necesitan permisos separados definidos para grupos de usuarios independientes. |
| **Administrador de cumplimiento de comunicaciones** | Use este grupo de roles para configurar inicialmente el cumplimiento de comunicaciones y posteriormente para separar los administradores de cumplimiento de comunicaciones en un grupo definido. Los usuarios asignados a este grupo de roles pueden crear, leer, actualizar y eliminar las directivas de cumplimiento de la comunicación, la configuración global y las asignaciones de grupos de roles. Los usuarios asignados a este grupo de roles no pueden ver los mensajes de alerta. |
| **Analista de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que van a actuar como analistas de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver las directivas en las que se asignan como revisores, ver los metadatos de los mensajes (no el contenido del mensaje), remitir a otros revisores o enviar notificaciones a los usuarios. Los analistas no pueden resolver alertas pendientes. |
| **Investigador de cumplimiento de la comunicación** | Use este grupo para asignar permisos a los usuarios que actuarán como investigadores de cumplimiento de la comunicación. Los usuarios asignados a este grupo de roles pueden ver el contenido y los metadatos de los mensajes, escalar a revisores adicionales, escalar a un caso de eDiscovery avanzado, enviar notificaciones a los usuarios y resolver la alerta. |
| **Visor de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que van a administrar los informes de comunicación. Los usuarios asignados a este grupo de roles pueden tener acceso a todos los widgets de informes en la página de inicio de cumplimiento de comunicaciones y pueden ver todos los informes de cumplimiento de comunicaciones. |

### <a name="for-organizations-using-the-original-permissions-and-role-groups"></a>Para organizaciones que usan los grupos de roles y permisos originales

La nueva estructura de grupo de roles reemplaza la estructura de grupo de roles inicial para el cumplimiento de la comunicación. Para las organizaciones que ya usan el cumplimiento de las comunicaciones, debe tener asignado el rol de administrador de revisión de supervisión para empezar con el cumplimiento de la comunicación en el centro de cumplimiento de Microsoft 365. Además, tenía que crear un nuevo grupo de roles para revisores con el administrador de revisión de supervisión, la administración de casos, el administrador de cumplimiento y la revisión de roles para investigar y corregir mensajes con coincidencias de directivas. Básicamente, todos los administradores y revisores estaban en un solo grupo de roles y todos tenían los mismos permisos de acceso y administración. Con las últimas actualizaciones del cumplimiento de comunicaciones, debe planear la migración de la estructura de grupo de roles anterior a la nueva estructura de grupos de roles. Se eliminará la compatibilidad con la estructura de grupo de roles anterior.

Para ayudarle en la planeación de la migración, tenga en cuenta el siguiente ejemplo. Actualmente tiene tres tipos de usuarios en la organización, administradores de ti, clasificaciones y revisores. Estos tres tipos de usuarios se encuentran en la estructura de grupo de roles anterior y son todos los miembros de un único grupo de roles que tienen asignadas las siguientes funciones:

- Administrador de revisión de supervisión
- Administración de casos
- Administrador de cumplimiento
- Revisar

Para actualizar los roles de estos usuarios para la nueva estructura de grupo de roles y separar los permisos de acceso y de administración de los usuarios, puede considerar tres grupos nuevos y las nuevas asignaciones de grupos de roles asociadas:

- **Administradores de ti**: asignados al nuevo grupo de roles de *Administración de cumplimiento de comunicaciones* .
- **Clasificación**: asignada al grupo de funciones *Analista de cumplimiento de comunicaciones* .
- **Revisores**: asignados al nuevo grupo de roles de *investigador de cumplimiento de comunicaciones* .

## <a name="supervised-users"></a>Usuarios supervisados

Antes de empezar a usar el cumplimiento de la comunicación, debe determinar quién necesita que se revisen sus comunicaciones. En la Directiva, las direcciones de correo electrónico de usuario identifican a los individuos o grupos de personas que deben supervisarse. Algunos ejemplos de estos grupos son los grupos de Microsoft 365, las listas de distribución basadas en Exchange, las comunidades de Yammer y los canales de Microsoft Teams. También puede excluir usuarios o grupos específicos del análisis con un grupo de exclusión específico o con una lista de grupos.

>[!IMPORTANT]
>Los usuarios a los que se aplican las directivas de cumplimiento de comunicaciones deben tener una licencia de cumplimiento de Microsoft 365 E5, una licencia de Office 365 Enterprise E3 con el complemento de cumplimiento avanzado o incluirse en una suscripción a Office 365 Enterprise E5. Si no tiene un plan existente de Enterprise E5 y desea probar el cumplimiento de la comunicación, puede [registrarse para obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).

## <a name="reviewers"></a>Reviewers

Al crear una directiva de cumplimiento de la comunicación, debe determinar quién revisa los mensajes de los usuarios supervisados. En la Directiva, las direcciones de correo electrónico de usuario identifican personas o grupos de personas para revisar las comunicaciones supervisadas. Todos los revisores deben tener buzones de correo hospedados en Exchange Online y deben asignarse a los roles *análisis de cumplimiento de comunicaciones* o de investigación de cumplimiento en la *comunicación* . Los revisores (analistas o investigadores) también deben tener asignado el rol de *Administración de casos de cumplimiento* de la comunicación. Cuando se agregan revisores a una directiva, reciben automáticamente un mensaje de correo electrónico que les notifica la asignación a la Directiva y proporciona vínculos a la información sobre el proceso de revisión.

## <a name="groups-for-supervised-users-and-reviewers"></a>Grupos de usuarios supervisados y revisores

Para simplificar la configuración, cree grupos para los usuarios que necesitan sus comunicaciones revisadas y grupos para los usuarios que revisen dichas comunicaciones. Si está usando grupos, es posible que necesite varios. Por ejemplo, si desea examinar las comunicaciones entre dos grupos de personas distintos, o si desea especificar un grupo que no está supervisado.

Cuando se asigna un grupo de distribución en la Directiva, la Directiva supervisa todos los mensajes de correo de cada usuario en el grupo de distribución. Cuando asigna un grupo de Microsoft 365 en la Directiva, la Directiva supervisa todos los mensajes de correo electrónico enviados a ese grupo, no los mensajes de correo electrónico individuales recibidos por cada miembro del grupo.

La adición de grupos y listas de distribución a las directivas de cumplimiento de comunicaciones forma parte del conjunto de reglas y condiciones generales, por lo que el número máximo de grupos y listas de distribución que admite una directiva varía en función del número de condiciones que se agreguen también a la Directiva. Cada Directiva debe admitir aproximadamente 20 grupos o listas de distribución, según el número de condiciones adicionales presentes en la Directiva.

## <a name="supported-communication-types"></a>Tipos de comunicación admitidos

Con las directivas de cumplimiento de la comunicación, puede elegir analizar los mensajes en una o varias de las plataformas de comunicación siguientes como un grupo o como orígenes independientes. Las comunicaciones capturadas en estas plataformas se conservan durante siete años para cada directiva de forma predeterminada, incluso si los usuarios dejan la organización y sus buzones de correo se eliminan.

- **Microsoft Teams**: se pueden analizar las comunicaciones de chat en los canales públicos y privados de Microsoft Teams y en los chats individuales. Cuando se asignan usuarios a una directiva de cumplimiento de la comunicación con la cobertura de Microsoft Teams seleccionada, las comunicaciones de chat para los usuarios se supervisan automáticamente en todos los equipos de Microsoft en los que los usuarios son miembros. La cobertura de Microsoft Teams se incluye automáticamente para las plantillas de directiva predefinidas y está seleccionada de forma predeterminada en la plantilla de directiva personalizada. Equipos chats la coincidencia de las condiciones de la Directiva de cumplimiento de comunicaciones puede tardar hasta 24 horas en procesarse. Use las siguientes configuraciones de administración de grupos para supervisar los chats de usuarios individuales y las comunicaciones de canal en Microsoft Teams:

    - **Para las comunicaciones de chat de Microsoft Teams:** Asigne usuarios individuales o asigne un [grupo de distribución](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) a la Directiva de cumplimiento de la comunicación. Esta configuración es para relaciones de usuario y chat uno a uno o uno a varios.
    - **Para las comunicaciones de canal de Teams:** Asigne cada canal de Microsoft Teams o grupo de Microsoft 365 que desee analizar que contenga un usuario específico a la Directiva de cumplimiento de la comunicación. Si agrega el mismo usuario a otros canales de Microsoft Teams o a grupos de Microsoft 365, asegúrese de agregar estos nuevos canales y grupos a la Directiva de cumplimiento de la comunicación.
    - **Para las comunicaciones de chat de Microsoft Teams con entornos de correo electrónico híbridos**: el cumplimiento de la comunicación puede supervisar los mensajes de chat para los usuarios de organizaciones con una implementación local de Exchange o un proveedor de correo electrónico externo que haya habilitado Microsoft Teams. Debe crear un grupo de distribución para los usuarios con buzones locales o externos para supervisar. Al crear una directiva de cumplimiento de comunicaciones, asignará este grupo de distribución como la selección de **usuarios y grupos supervisados** en el Asistente para directivas.

    >[!IMPORTANT]
    >Debe archivar una solicitud con soporte técnico de Microsoft para permitir que su organización use la interfaz gráfica de usuario del centro de seguridad & cumplimiento para buscar los datos de chat de Microsoft Teams para los usuarios locales. Para obtener más información, vea [Buscar buzones de correo basados en la nube para usuarios locales](search-cloud-based-mailboxes-for-on-premises-users.md).

Debe presentar una solicitud al Soporte técnico de Microsoft para que su organización pueda utilizar la interfaz gráfica de usuario en el Centro de seguridad y cumplimiento para buscar datos de chat de Teams en los buzones de correo basados en la nube para los usuarios locales.

- **Correo electrónico de Exchange**: los buzones hospedados en Exchange online como parte de su suscripción a Microsoft 365 u Office 365 son aptos para el análisis de mensajes. Los mensajes de correo electrónico de Exchange y los datos adjuntos que cumplen las condiciones de la Directiva de cumplimiento de comunicaciones pueden tardar hasta 24 horas en procesarse. Los tipos de datos adjuntos admitidos para el cumplimiento de la comunicación son los mismos que los [tipos de archivo compatibles con las visitas de contenido de reglas de flujo de correo de Exchange](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).

- **Yammer**: se pueden examinar mensajes privados y conversaciones públicas y datos adjuntos asociados en comunidades de Yammer. Cuando se agrega un usuario a una directiva de cumplimiento de la comunicación que incluye Yammer como un canal definido, las comunicaciones de todas las comunidades de Yammer a las que pertenece el usuario se incluyen en el proceso de detección. Chats y datos adjuntos de Yammer que cumplen las condiciones de la Directiva de cumplimiento de comunicaciones pueden tardar hasta 24 horas en procesarse. Yammer debe estar en [modo nativo](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) para las directivas de cumplimiento de comunicaciones para supervisar las comunicaciones y los datos adjuntos de Yammer. En el modo nativo, todos los usuarios de Yammer están en Azure Active Directory (AAD), todos los grupos son Grupos de Office 365 y todos los archivos se almacenan en SharePoint Online.

- **Skype empresarial online**: las comunicaciones de chat y los datos adjuntos asociados en Skype empresarial online pueden supervisarse. Chats de Skype empresarial online la coincidencia de las condiciones de la Directiva de cumplimiento de comunicaciones puede tardar hasta 24 horas en procesarse. Las conversaciones de chat supervisadas se han originado a partir de [conversaciones anteriores guardadas en Skype empresarial online](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2).  Use la siguiente configuración de administración de grupos para supervisar las comunicaciones de chat de los usuarios en Skype empresarial online:

    - **Para las comunicaciones de chat de Skype empresarial online**: asigne usuarios individuales o asigne un [grupo de distribución](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) a la Directiva de cumplimiento de la comunicación. Esta configuración es para relaciones de usuario y chat uno a uno o uno a varios.

- **Orígenes de terceros**: puede examinar las comunicaciones de orígenes de terceros para los datos importados en buzones de la organización de Microsoft 365. Los conectores admiten los siguientes recursos de terceros:

    - [Instant Bloomberg](archive-instant-bloomberg-data.md)
    - [Mensaje de Bloomberg](archive-bloomberg-message-data.md)
    - [Chat ICE](archive-icechat-data.md)

Debe configurar un conector de terceros para la organización de Microsoft 365 antes de poder asignar el conector a una directiva de cumplimiento de la comunicación. La sección **orígenes de terceros** del Asistente para la Directiva de cumplimiento de comunicaciones solo muestra los conectores de terceros configurados actualmente.

## <a name="transitioning-from-supervision-in-office-365"></a>Transición desde la supervisión en Office 365

Las organizaciones que usan directivas de supervisión en Office 365 y la planeación de la transición a directivas de cumplimiento de comunicaciones en Microsoft 365 necesitan comprender estos puntos importantes:

- Ambas soluciones pueden usarse en paralelo en la organización, pero las directivas que se usan en cada solución deben tener nombres de directiva únicos. Los grupos y los diccionarios de palabras clave personalizados se pueden compartir entre las soluciones durante un período de transición.
- Los mensajes guardados en la supervisión de las coincidencias de directivas de Office 365 no se pueden mover ni compartir con el cumplimiento de la comunicación en Microsoft 365.
- La solución de supervisión de Office 365 se reemplazará completamente por la solución de cumplimiento de comunicaciones en Microsoft 365. Se recomienda crear nuevas directivas en el cumplimiento de la comunicación que tengan la misma configuración que las directivas de supervisión existentes para usar las nuevas mejoras de investigación y corrección. Al realizar la transición al cumplimiento de la comunicación en Microsoft 365, debe planear la exportación de los datos de informes desde la supervisión en Office 365 si tiene requisitos internos de la Directiva de retención de cumplimiento.

Para obtener información de jubilación para la supervisión en Office 365, consulte el [mapa de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para obtener más información.

## <a name="policy-settings"></a>Configuración de directivas

### <a name="users"></a>Usuarios

Tiene la opción de seleccionar **todos los usuarios** o de definir usuarios específicos en una directiva de cumplimiento de la comunicación. La selección de **todos los usuarios** aplica la Directiva a todos los usuarios y a todos los grupos en los que cualquier usuario se incluye como miembro. La definición de usuarios específicos aplica la Directiva a los usuarios definidos y a todos los grupos de los que los usuarios definidos se incluyen como miembros.

### <a name="direction"></a>Dirección

De forma predeterminada, la condición **es la dirección** se muestra y no se puede quitar. La configuración de la dirección de la comunicación en una directiva se eligen de forma individual o conjunta:

- **Entrante**: puede elegir **entrante** para revisar las comunicaciones enviadas **a** las personas que haya elegido supervisar.
- **Saliente**: puede elegir **saliente** si desea revisar las comunicaciones enviadas **por** las personas que ha elegido supervisar.
- **Interno**: puede elegir **interna** para revisar las comunicaciones enviadas **entre** las personas que identificó en la Directiva.

### <a name="sensitive-information-types"></a>Tipos de información confidencial

Tiene la opción de incluir tipos de información confidencial como parte de la Directiva de cumplimiento en la comunicación. Los tipos de información confidencial son tipos de datos predefinidos o personalizados que pueden ayudar a identificar y proteger números de tarjetas de crédito, números de cuentas bancarias, números de pasaporte, etc. Como parte de la [prevención de pérdida de datos (DLP)](data-loss-prevention-policies.md), la configuración de información confidencial puede usar patrones, proximidad de caracteres, niveles de confianza e incluso tipos de datos personalizados para ayudar a identificar y marcar contenido que pueda ser confidencial. Los tipos de información confidencial predeterminados son:

- Financiera
- Médico y salud
- Privacidad
- Tipo de información personalizada

Para obtener más información acerca de los detalles de información confidencial y los patrones incluidos en los tipos predeterminados, vea tipos de [información confidencial definiciones de entidad](sensitive-information-type-entity-definitions.md).

### <a name="custom-keyword-dictionaries"></a>Diccionarios de palabras clave personalizados

Configure diccionarios de palabras clave personalizados (o léxicos) para proporcionar una administración sencilla de palabras clave específicas de la organización o del sector. Los diccionarios de palabras clave admiten hasta 100 KB de términos (posteriores a la compresión) en el Diccionario y admiten cualquier idioma. El límite del espacio empresarial es también de 100 KB tras la compresión. Si es necesario, puede aplicar varios diccionarios de palabras clave personalizados a una sola directiva o tener un diccionario de palabras clave único por directiva. Estos diccionarios se asignan en una directiva de cumplimiento de la comunicación y pueden originarse a partir de un archivo (como una lista. csv o. txt) o de una lista que se puede [importar en el centro de cumplimiento](create-a-keyword-dictionary.md). Use diccionarios personalizados cuando necesite admitir términos o idiomas específicos de la organización y las directivas.

### <a name="classifiers"></a>Clasificadores

Los clasificadores globales y con formación integradas integrados examinan los mensajes enviados o recibidos en todos los canales de comunicación de la organización para diferentes tipos de problemas de cumplimiento. Los clasificadores usan una combinación de inteligencia artificial y palabras clave para identificar el idioma de los mensajes que puedan infringir las directivas Antiacoso. Actualmente, los clasificadores integrados solo admiten palabras clave en inglés en los mensajes.

Cumplimiento en la comunicación los clasificadores globales y que se integran en el ámbito de la comunicación examinan las comunicaciones de términos, imágenes y sentimientos para los siguientes tipos de idiomas y contenido:

- **Amenaza**: busca amenazas para confirmar violencia o daño físico a una persona o propiedad.
- **Acoso dirigido**: explora los objetivos ofensivos de las personas relacionadas con la raza, el color, la religión y el origen nacional.
- **Blasfemias**: explora las expresiones irreverentes que avergonzan a la mayoría de las personas.
- **Imágenes de adultos**: explora imágenes que tienen una naturaleza sexualmente explícita.
- **Imágenes de racy**: explora imágenes que son de naturaleza sexual, pero contienen contenido menos explícito que las imágenes que se consideran adultas.
- **Imágenes de Gory**: explora imágenes que describen violencia y Gore.

Los clasificadores de imágenes de *adultos*, *racy*y *Gory* digitalizan archivos en. JPEG,. PNG,. GIF y. Formatos BMP. El tamaño de los archivos de imagen debe ser inferior a 4 megabytes (MB) y las dimensiones de las imágenes deben ser superiores a 50x50 píxeles y superiores a 50 kilobytes (KB) para que la imagen pueda calificarse para la evaluación. La identificación de imagen es compatible con los mensajes de correo electrónico de Exchange Online y los canales y chats de Microsoft Teams.

Los clasificadores globales y capacitados integrados no proporcionan una lista exhaustiva de términos o imágenes en estas áreas. Además, los estándares de idioma y culturales cambian continuamente y, teniendo en cuenta estas realidades, Microsoft se reserva el derecho de actualizar los clasificadores según su criterio. Aunque los clasificadores pueden ayudar a su organización a supervisar estas áreas, los clasificadores no están destinados a proporcionar a los únicos medios de la organización la supervisión o el direccionamiento de dicho idioma o imagen. La organización, no Microsoft, sigue siendo responsable de todas las decisiones relacionadas con el idioma y las imágenes de análisis y bloqueo en estas áreas.

Para obtener información acerca de los clasificadores que se capacitan en Microsoft 365, consulte [Getting Started with Trainer Classifiers](classifier-get-started-with.md).

### <a name="conditional-settings"></a>Configuración condicional
<a name="ConditionalSettings"> </a>

Las condiciones que elija para la Directiva se aplican a las comunicaciones de los orígenes de correo electrónico y de terceros de la organización (por ejemplo, Bloomberg o DropBox instantánea).

La siguiente tabla explica más sobre cada condición.
  
|**Condición**|**Cómo usar esta condición**|
|:-----|:-----|
| **El contenido coincide con cualquiera de estos clasificadores** | Se aplican a la Directiva cuando se incluyen o excluyen clasificadores en un mensaje. Algunos clasificadores están predefinidos en su espacio empresarial y los clasificadores personalizados deben configurarse por separado antes de que estén disponibles para esta condición. Solo se puede definir un clasificador como condición en una directiva. Para obtener más información acerca de la configuración de clasificadores, vea información sobre los clasificadores que se van a [capacitar (versión preliminar)](classifier-learn-about.md). |
| **El contenido contiene cualquiera de estos tipos de información confidencial** | Se aplican a la Directiva cuando se incluyen o excluyen tipos de información confidencial en un mensaje. Algunos clasificadores están predefinidos en su espacio empresarial y los clasificadores personalizados se pueden configurar por separado o como parte del proceso de asignación de condición. Cada tipo de información confidencial que elija se aplica por separado y solo uno de estos tipos de información confidencial se debe aplicar para que la Directiva se aplique al mensaje. Para obtener más información acerca de los tipos personalizados de información confidencial, vea [tipos personalizados de información confidencial](custom-sensitive-info-types.md). |
| **Se recibe el mensaje desde cualquiera de estos dominios**  <br><br> **No se recibe el mensaje desde ninguno de estos dominios** | Aplicar la Directiva para incluir o excluir dominios o direcciones de correo electrónico específicos en los mensajes recibidos. Escriba cada dominio o dirección de correo electrónico y separe los distintos dominios o direcciones de correo electrónico con una coma. Cada dominio o dirección de correo electrónico que se escriba se aplica por separado, solo se debe solicitar un dominio o una dirección de correo electrónico para que la Directiva se aplique al mensaje. <br><br> Si desea analizar todo el correo electrónico de un dominio específico, pero desea excluir los mensajes que no necesitan revisión (boletines, anuncios, etc.), debe configurar un mensaje que **no se reciba de ninguna de estas** condiciones de dominio que excluya la dirección de correo electrónico (por ejemplo, "Newsletter@contoso.com"). |
| **El mensaje se envía a cualquiera de estos dominios**  <br><br> **El mensaje no se envía a ninguno de estos dominios** | Aplicar la Directiva para incluir o excluir dominios o direcciones de correo electrónico específicos en los mensajes enviados. Escriba cada dominio o dirección de correo electrónico y separe los distintos dominios o direcciones de correo electrónico con una coma. Cada dirección de correo electrónico o dominio se aplica por separado, solo se debe solicitar un dominio o una dirección de correo electrónico para que la Directiva se aplique al mensaje. <br><br> Si desea analizar todo el correo electrónico enviado a un dominio específico, pero quiere excluir los mensajes enviados que no necesitan revisión, debe configurar dos condiciones: <br> - **Se envía un mensaje a cualquiera de estas condiciones de los dominios** que define el dominio ("contoso.com") y <br> -Un **mensaje no se envía a ninguna condición de dominio** que excluya la dirección de correo electrónico ("subscriptions@contoso.com"). |
| **El mensaje se clasifica con cualquiera de estas etiquetas**  <br><br> **El mensaje no está clasificado con ninguna de estas etiquetas** | Para aplicar la Directiva cuando se incluyen o excluyen determinadas etiquetas de retención en un mensaje. Las etiquetas de retención se deben configurar por separado y las etiquetas configuradas se eligen como parte de esta condición. Cada etiqueta que elija se aplica por separado (solo una de estas etiquetas se debe aplicar para que la Directiva se aplique al mensaje). Para obtener más información acerca de las etiquetas de retención, consulte [información sobre las directivas de retención y las etiquetas de retención](retention.md).|
| **El mensaje contiene alguna de estas palabras**  <br><br> **El mensaje no contiene ninguna de estas palabras** | Para aplicar la Directiva cuando se incluyan o excluyan ciertas palabras o frases en un mensaje, escriba cada palabra separada por una coma. Para las frases de dos palabras o más, use comillas alrededor de la frase. Cada palabra o frase que escriba se aplica por separado (solo se debe aplicar una palabra para que la Directiva se aplique al mensaje). Para obtener más información sobre cómo escribir palabras o frases, consulte la sección siguiente [Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords).|
| **Los datos adjuntos contienen alguna de estas palabras**  <br><br> **Los datos adjuntos no contienen ninguna de estas palabras** | Para aplicar la Directiva cuando se incluyan o excluyan ciertas palabras o frases en un adjunto de mensaje (por ejemplo, un documento de Word), escriba cada palabra separada por una coma. Para las frases de dos palabras o más, use comillas alrededor de la frase. Cada palabra o frase que escriba se aplica por separado (solo se debe aplicar una palabra para que la Directiva se aplique a los datos adjuntos). Para obtener más información sobre cómo escribir palabras o frases, consulte la sección siguiente [Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords).|
| **Los datos adjuntos son cualquiera de estos tipos de archivo**  <br><br> **Datos adjuntos no es ninguno de estos tipos de archivo** | Para supervisar las comunicaciones que incluyan o excluyan tipos de datos adjuntos específicos, escriba las extensiones de archivo (por ejemplo,. exe o. pdf). Si desea incluir o excluir varias extensiones de archivo, indíquela en líneas separadas. Para que se aplique la Directiva, solo debe coincidir una extensión de datos adjuntos.|
| **El tamaño del mensaje es mayor que**  <br><br> **El tamaño del mensaje no es mayor que** | Para revisar los mensajes según un tamaño determinado, use estas condiciones para especificar el tamaño máximo o mínimo que puede tener un mensaje antes de que se someta a revisión. Por ejemplo, si especifica que **el tamaño del mensaje es superior a** \> **1,0 MB**, todos los mensajes que tengan 1,01 MB o más, estarán sujetos a revisión. Puede elegir bytes, kilobytes, megabytes o gigabytes para esta condición.|
| **El dato adjunto es mayor que**  <br><br> **Los datos adjuntos no tienen un tamaño superior a** | Para revisar los mensajes en función del tamaño de los datos adjuntos, especifique el tamaño máximo o mínimo que pueden tener los datos adjuntos antes de que el mensaje y sus datos adjuntos estén sujetos a revisión. Por ejemplo, si especifica que el **dato adjunto es superior** a \> **2,0 MB**, todos los mensajes con datos adjuntos 2,01 MB y sobre estarán sujetos a revisión. Puede elegir bytes, kilobytes, megabytes o gigabytes para esta condición.|
   
#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Coincidencia de palabras y frases para mensajes de correo electrónico o datos adjuntos
<a name="Matchwords"> </a>

Cada palabra que escriba y separe con una coma se aplica por separado (solo se debe aplicar una palabra para que la condición de la Directiva se aplique al correo electrónico o los datos adjuntos). Por ejemplo, vamos a usar la condición, el **mensaje contiene cualquiera de estas palabras**, con las palabras clave "Banker", "Confidential" y "Insider comercia" separadas por una coma (Banker, Confidential, "transacciones de Insiders"). La Directiva se aplica a todos los mensajes que incluyan la palabra "Banker", "Confidential" o la frase "comercio Insider". Solo una de estas palabras o frases debe aparecer para que esta condición de directiva se aplique. Las palabras del mensaje o del archivo adjunto deben coincidir exactamente con lo que se especifique.

>[!IMPORTANT]
>Al importar un archivo de diccionario personalizado, cada palabra o frase debe separarse con un retorno de carro y en una línea independiente. <br> Por ejemplo: <br><br>
>*Banco* <br>
>*confidencial* <br>
>*Comercio de Insiders*

Para analizar los mensajes de correo electrónico y los datos adjuntos de las mismas palabras clave, cree una [Directiva de prevención de pérdida de datos](create-test-tune-dlp-policy.md) con un diccionario de [palabras clave personalizado](create-a-keyword-dictionary.md) para los términos que desee analizar en los mensajes. Esta configuración de directiva identifica las palabras clave definidas que aparecen en el mensaje de correo electrónico **o** en los datos adjuntos del correo electrónico. El uso de la configuración de directivas condicionales estándar (el*mensaje contiene alguna de estas palabras* y *datos adjuntos contiene alguna de estas palabras*) para **identificar los términos** de los mensajes y en los datos adjuntos requiere que los términos estén presentes en el mensaje y los datos adjuntos.
  
#### <a name="enter-multiple-conditions"></a>Escribir varias condiciones

Si escribe varias condiciones, Microsoft 365 usa todas las condiciones de forma conjunta para determinar cuándo debe aplicarse la Directiva de cumplimiento de comunicaciones a los elementos de comunicación. Al configurar varias condiciones, se deben cumplir todas las condiciones para que se aplique la Directiva, a menos que se especifique una excepción. Por ejemplo, necesita una directiva que se aplique si un mensaje contiene la palabra "Trade" y su tamaño es superior a 2 MB. Sin embargo, si el mensaje también contiene las palabras "aprobado por contoso Financial", la Directiva no debe aplicarse. En este ejemplo, las tres condiciones se definirían de la siguiente manera:
  
- El **mensaje contiene cualquiera de estas palabras**, con la palabra clave "Trade"
- El **tamaño del mensaje es mayor que**, con el valor de 2 MB
- El **mensaje no contiene ninguna de estas palabras**, con las palabras clave "aprobado por el equipo financiero de Contoso"

### <a name="review-percentage"></a>Porcentaje de revisión

Si desea reducir la cantidad de contenido que se va a revisar, puede especificar un porcentaje de todas las comunicaciones regidas por una directiva de cumplimiento de la comunicación. Se selecciona un ejemplo aleatorio en tiempo real del contenido del porcentaje total de contenido que coincide con las condiciones de la directiva elegida. Si desea que los revisores revisen todos los elementos, puede configurar **100%** en una directiva de cumplimiento de la comunicación.

## <a name="privacy-preview"></a>Privacidad (versión preliminar)

La protección de la privacidad de los usuarios que tienen coincidencias de directivas es importante y puede ayudar a promover la objetividad en las revisiones de análisis y investigación de datos para las alertas de cumplimiento de comunicaciones. Esta configuración solo se aplica a los nombres de usuario que muestran la solución de cumplimiento de comunicación. No afecta al modo en que se muestran los nombres en otras soluciones de cumplimiento o en el centro de administración.

Para los usuarios con una coincidencia de cumplimiento de la comunicación, puede elegir una de las siguientes opciones en **configuración de cumplimiento**de la comunicación:

- **Mostrar anonimizan versiones de**los nombres de usuario: los nombres de usuario son anonimizan para evitar que los administradores, analistas, investigadores de datos y revisores vean a quién está asociado con las alertas de directiva. Por ejemplo, un usuario de "el período de gracia de Taylor" aparecería con un Pseudonym aleatorio como "AnonIS8-988" en todas las áreas de la experiencia de cumplimiento de comunicación. La elección de esta opción anonymizes todos los usuarios con coincidencias de directivas actuales y pasadas y se aplica a todas las directivas. La información de Perfil de usuario en los detalles de alerta de cumplimiento de comunicaciones no estará disponible cuando se seleccione esta opción. Sin embargo, los nombres de usuario se muestran cuando se agregan nuevos usuarios a directivas existentes o cuando se asignan usuarios a nuevas directivas. Si elige desactivar esta opción, se mostrarán los nombres de usuario para todos los usuarios que tengan coincidencias de directivas actuales o pasadas.
- **No mostrar anonimizan versiones de nombres de**usuario: los nombres de usuario se muestran en todas las coincidencias de directivas actuales y pasadas para las alertas de cumplimiento de comunicaciones. La información del perfil de usuario (el nombre, el cargo, el alias y la organización o departamento) se muestra al usuario para todas las alertas de cumplimiento de comunicación.

## <a name="notice-templates"></a>Plantillas de aviso

Puede crear plantillas de notificación si desea enviar a los usuarios una notificación de recordatorio de correo electrónico para las coincidencias de directivas como parte del proceso de resolución de problemas. Los avisos solo pueden enviarse a la dirección de correo electrónico del usuario asociada con la Directiva que generó la alerta específica para la corrección. Al seleccionar una plantilla de notificación para aplicar a una infracción de directiva como parte del flujo de trabajo de corrección, puede optar por aceptar los valores de campo definidos en la plantilla o sobrescribir los campos según sea necesario.

Las plantillas de notificaciones son plantillas de correo electrónico personalizadas donde puede definir los siguientes campos de mensaje en el área de **configuración de cumplimiento de comunicaciones** :

|**Field**|**Required**| **Detalles** |
|:-----|:-----|:-----|
|**Nombre de la plantilla** | Sí | Nombre descriptivo de la plantilla de aviso que seleccionará en el flujo de trabajo Notify durante la corrección, admite caracteres de texto. |
| **Dirección del remitente** | Sí | La dirección de uno o más usuarios o grupos que envían el mensaje al usuario con una coincidencia de Directiva, seleccionada en Active Directory de la suscripción. |
| **Direcciones CC y CCO** | No | Que los usuarios o grupos opcionales reciban una notificación de la coincidencia de la Directiva, seleccionada en Active Directory de la suscripción. |
| **Asunto** | Sí | La información que aparece en la línea de asunto del mensaje admite caracteres de texto. |
| **Cuerpo del mensaje** | Sí | La información que aparece en el cuerpo del mensaje admite texto o valores HTML. |

### <a name="html-for-notices"></a>HTML para avisos

Si desea crear más de un mensaje de correo electrónico basado en texto sencillo para las notificaciones, puede crear un mensaje más detallado usando HTML en el campo cuerpo del mensaje de una plantilla de notificación. El siguiente ejemplo proporciona el formato del cuerpo del mensaje para una plantilla básica de notificación de correo electrónico basada en HTML:

```HTML
<!DOCTYPE html>
<html>
    <body>
        <h2>Action Required: Contoso Employee Code of Conduct Policy Training</h2>
        <p>A recent message you've sent has generated a policy alert for the Contoso Employee <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
        <p>You are required to attend the Contoso Employee Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
        <p>Thank you,</p>
        <p><em>Human Resources</em></p>
    </body>
</html>
```

>[!NOTE]
>La implementación de atributos de href HTML en las plantillas de notificación de cumplimiento de la comunicación solo admiten comillas simples, en lugar de comillas dobles para las referencias a direcciones URL.

## <a name="filters"></a>Filtros

Los filtros de cumplimiento de comunicaciones le permiten filtrar y ordenar los mensajes de alerta para obtener una investigación más rápida y acciones de corrección. El filtrado está disponible en las pestañas **pendientes** y **resueltas** para cada Directiva. Para guardar un filtro o un conjunto de filtros como una consulta de filtro guardada, se deben configurar uno o más valores como selecciones de filtro. En la tabla siguiente se describen los detalles del filtro:

|**Filtro**|**Detalles**|
|:-----|:-----|
| **Date** | La fecha en la que un usuario de la organización envió o recibió el mensaje. |
| **Clase File** | La clase del mensaje en función del tipo de mensaje, ya sea *mensaje* o *datos adjuntos*. |
| **Tiene datos adjuntos** | La presencia de datos adjuntos en el mensaje. |
| **Clase Item** | El origen del mensaje en función del tipo de mensaje, el correo electrónico, Microsoft Team chat, Bloomberg, etc. Para obtener más información acerca de los tipos de elementos y las clases de mensajes comunes, vea [tipos de elementos y clases de mensajes](https://docs.microsoft.com/office/vba/outlook/concepts/forms/item-types-and-message-classes). |
| **Dominios de destinatarios** | El dominio al que se envió el mensaje. Este dominio suele ser su dominio de suscripción de Microsoft 365 de forma predeterminada. |
| **Recipient** | El usuario al que se envió el mensaje. |
| **Sender** | La persona que envió el mensaje. |
| **Dominio del remitente** | El dominio que envió el mensaje. |
| **Tamaño** | El tamaño del mensaje en KB. |
| **Asunto/título** | El asunto del mensaje o el título del chat. |
| **Tags** | Las etiquetas asignadas a un mensaje, ya sea *dudosa*, *compatible*o *no compatible*. |
| **Remitir a** | El nombre de usuario de la persona incluida como parte de una acción de elevación de mensajes. |
| **Clasificadores** | El nombre de los clasificadores integrados y personalizados que se aplican al mensaje. Algunos ejemplos son el *lenguaje ofensivo*, el *acoso dirigido*, la *blasfemia*, la *amenaza*y mucho más.

## <a name="alert-policies"></a>Directivas de alerta

Después de configurar una directiva, se crea automáticamente una directiva de alerta correspondiente y se generan alertas para los mensajes que coinciden con las condiciones definidas en la Directiva. De forma predeterminada, todas las directivas coinciden con los activadores de alertas a los que se asigna un nivel de gravedad medio en la Directiva de alerta asociada. Las alertas se generan para una directiva de cumplimiento de la comunicación una vez que se cumple el nivel umbral del desencadenador de agregación en la Directiva de alerta asociada.

Para las directivas de cumplimiento de la comunicación, los siguientes valores de la Directiva de alerta están configurados de forma predeterminada:

|**Desencadenador de la Directiva de alerta**|**Valor predeterminado**|
|:-----|:-----|
| Cronológica | Agregación sencilla |
| Umbral | 4 actividades |
| Window | 60 minutos |

>[!Note]
>La configuración de desencadenadores de umbral de la Directiva de alerta para actividades admite un valor mínimo de 3 o superior para las directivas de cumplimiento de la comunicación.

Puede cambiar la configuración predeterminada de los desencadenadores en el número de actividades, el período de las actividades y los usuarios específicos de las directivas de alertas en la página **directivas de alertas** del centro de seguridad & cumplimiento.

### <a name="change-the-severity-level-for-an-alert-policy"></a>Cambiar el nivel de gravedad de una directiva de alerta

Si desea cambiar el nivel de gravedad asignado en una directiva de alertas para una directiva de cumplimiento de comunicaciones específica, siga estos pasos:

1. Inicie sesión [https://compliance.microsoft.com](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador en la organización de Microsoft 365.

2. En el centro de cumplimiento de Microsoft 365, vaya a **directivas**.

3. Seleccione **office 365 Alert** en la página **directivas** para abrir la página **directivas de alertas** en el centro de **seguridad & cumplimiento de Office 365**.

4. Marque la casilla de verificación de la Directiva de cumplimiento de comunicaciones que quiera actualizar y, después, seleccione **Editar Directiva**.

5. En la ficha **Descripción** , seleccione la lista desplegable **gravedad** para configurar el nivel de alerta de la Directiva.

6. Seleccione **Guardar** para aplicar el nuevo nivel de gravedad a la Directiva.

7. Seleccione **cerrar** para salir de la página Detalles de la Directiva de alerta.

## <a name="power-automate-flows-preview"></a>Flujos de automatización de la potencia (versión preliminar)

[Microsoft Power Automate](https://docs.microsoft.com/power-automate/getting-started) es un servicio de flujo de trabajo que automatiza acciones en aplicaciones y servicios. Mediante el uso de flujos de plantillas o creados manualmente, puede automatizar tareas comunes asociadas con estas aplicaciones y servicios. Al habilitar flujos de alimentación automatizada para el cumplimiento de la comunicación, puede automatizar las tareas importantes para las alertas y los usuarios. Puede configurar los flujos de alimentación automatizada para notificar a los administradores cuando los usuarios tienen alertas de cumplimiento de comunicaciones y otras aplicaciones.

Los clientes con suscripciones de Microsoft 365 que incluyen el cumplimiento de la comunicación no necesitan una automatización adicional para usar la plantilla de automatización de cumplimiento de comunicaciones predeterminada recomendada. La plantilla predeterminada se puede personalizar para apoyar a su organización y cubrir los principales escenarios de cumplimiento de comunicaciones. Si decide usar las características de automatizar la alimentación avanzada en estas plantillas, cree una plantilla personalizada con el conector de cumplimiento de Microsoft 365 o use las plantillas de Power automatizada para otras áreas de cumplimiento en Microsoft 365, es posible que necesite otras licencias de Power automatizada.

![Automatización de la energía de cumplimiento de comunicaciones](../media/communication-compliance-power-automate.png)

La siguiente plantilla de autoautomatización se proporciona a los clientes para que admitan la automatización de procesos para las alertas de cumplimiento de comunicaciones:

- **Notificar al administrador cuando un usuario tiene una alerta de cumplimiento de comunicaciones**: es posible que algunas organizaciones necesiten una notificación de administración inmediata cuando un usuario tiene una alerta de cumplimiento de la comunicación. Cuando se configura y se selecciona este flujo, se envía un mensaje de correo electrónico al administrador del caso al usuario con la siguiente información sobre todas las alertas:
    - Directiva aplicable para la alerta
    - Fecha y hora de la alerta
    - Nivel de gravedad de la alerta

### <a name="create-a-power-automate-flow"></a>Crear un flujo de automatización de potencia

Para crear un flujo de automatización de la potencia desde una plantilla predeterminada recomendada, use la opción **administrar flujos de automatización** **del control** automatizado cuando trabaje directamente en una alerta. Para crear un flujo de automatización automatizada con **administrar flujos de alimentación automatizada**, debe ser miembro de, al menos, un grupo de funciones de cumplimiento de la comunicación.

Complete los pasos siguientes para crear un flujo de automatización de eficacia desde una plantilla predeterminada:

1. En el centro de cumplimiento de Microsoft 365, vaya a directivas de **cumplimiento de comunicaciones**  >  **Policies** y seleccione la Directiva con la alerta que desea revisar.
2. En la Directiva, seleccione la pestaña **pendiente** y seleccione una alerta pendiente.
3. Seleccione **energía automatizada** en el menú Acción de alerta.
4. En la página **automatizar la automatización** , seleccione una plantilla predeterminada en la sección **plantillas de cumplimiento de comunicaciones que** puede desear que se refieren a la página.
5. El flujo mostrará una lista de las conexiones incrustadas necesarias para el flujo y se mostrará si los Estados de conexión están disponibles. Si es necesario, actualice las conexiones que no se muestren como disponibles. Seleccione **continuar**.
6. De forma predeterminada, los flujos recomendados están preconfigurados con los campos de datos de servicio de Microsoft 365 y cumplimiento de comunicaciones recomendados para completar la tarea asignada al flujo. Si es necesario, Personalice los componentes de flujo mediante el control **Mostrar opciones avanzadas** y configurando las propiedades disponibles para el componente de flujo.
7. Si es necesario, agregue pasos adicionales al flujo seleccionando el botón **nuevo paso** . En la mayoría de los casos, este cambio no debería ser necesario para las plantillas predeterminadas recomendadas.
8. Seleccione **Guardar borrador** para guardar el flujo para una configuración más reciente o seleccione **Guardar** para completar la configuración del flujo.
9. Seleccione **cerrar** para volver a la página flujo de energía automatizada. La nueva plantilla aparecerá como un flujo en la ficha **Mis flujos** y estará disponible automáticamente desde el control Power Automate para el usuario que creó el flujo al trabajar con las alertas de cumplimiento de comunicaciones.

### <a name="share-a-power-automate-flow"></a>Compartir un flujo de automatización de la alimentación

De forma predeterminada, los flujos de automatización creados por un usuario solo están disponibles para ese usuario. Para que otros usuarios de cumplimiento de comunicaciones tengan acceso y usen un flujo, el flujo debe compartirse con el creador del flujo. Para compartir un flujo, deberá usar el control **exponencial automatizada** cuando trabaje directamente en una alerta.

Para compartir un flujo de automatización, debe ser miembro de, al menos, un grupo de funciones de cumplimiento de la comunicación.
Complete los pasos siguientes para compartir un flujo de automatización de la alimentación:

1. En el centro de cumplimiento de Microsoft 365, vaya a directivas de **cumplimiento de comunicaciones**  >  **Policies** y seleccione la Directiva con la alerta que desea revisar.
2. En la Directiva, seleccione la pestaña **pendiente** y seleccione una alerta pendiente.
3. Seleccione **energía automatizada** en el menú Acción de alerta.
4. En la página **flujos de automatización eléctrica** , seleccione la pestaña **Mis flujos** o **flujos de equipo** .
5. Seleccione el flujo que desea compartir y, a continuación, seleccione **compartir** en el menú opciones de flujo.
6. En la página uso compartido de flujo, escriba el nombre del usuario o grupo que desea agregar como propietario del flujo.
7. En el cuadro de diálogo **conexión utilizada** , seleccione **Aceptar** para confirmar que el flujo de usuario o grupo agregado tendrá acceso total al flujo.

### <a name="edit-a-power-automate-flow"></a>Edición de un flujo de automatización de la alimentación

Si tiene que editar un flujo, usará el control **exponencial automatizando** el control cuando trabaje directamente en una alerta. Para editar un flujo de automatización, debe ser miembro de, al menos, un grupo de funciones de cumplimiento de la comunicación.

Complete los pasos siguientes para editar un flujo de automatización de consumo:

1. En el centro de cumplimiento de Microsoft 365, vaya a directivas de **cumplimiento de comunicaciones**  >  **Policies** y seleccione la Directiva con la alerta que desea revisar.
2. En la Directiva, seleccione la pestaña **pendiente** y seleccione una alerta pendiente.
3. Seleccione **energía automatizada** en el menú Acción de alerta.
4. En la página **flujos de automatización eléctrica** , seleccione flujo para editar. Seleccione **Editar** en el menú de control de flujo.
5. Seleccione la configuración de **puntos suspensivos**  >  **Settings** para cambiar una configuración del componente de flujo o **puntos suspensivos**  >  **Delete** para eliminar un componente de flujo.
6. Seleccione **Guardar** y, a continuación, **cerrar** para completar la edición del flujo.

### <a name="delete-a-power-automate-flow"></a>Eliminar un flujo de automatización de alimentación

Si necesita eliminar un flujo, deberá usar el control **Automate exponencial** cuando trabaje directamente en una alerta. Para eliminar un flujo de automatización de la alimentación, debe ser miembro de al menos un grupo de roles de cumplimiento de la comunicación.

Complete los pasos siguientes para eliminar un flujo de automatización de la alimentación:

1. En el centro de cumplimiento de Microsoft 365, vaya a directivas de **cumplimiento de comunicaciones**  >  **Policies** y seleccione la Directiva con la alerta que desea revisar.
2. En la Directiva, seleccione la pestaña **pendiente** y seleccione una alerta pendiente.
3. Seleccione **energía automatizada** en el menú Acción de alerta.
4. En la página **flujos de automatización eléctrica** , seleccione flujo para eliminar. Seleccione **eliminar** en el menú de control de flujo.
5. En el cuadro de diálogo de confirmación de eliminación, seleccione **eliminar** para quitar el flujo o seleccione **Cancelar** para salir de la acción de eliminación.

## <a name="reports-preview"></a>Informes (versión preliminar)

El nuevo panel **informes** es la ubicación central para ver todos los informes de cumplimiento de la comunicación. Los widgets de informe proporcionan una vista rápida de la información más necesaria para una evaluación general del estado de las actividades de cumplimiento de la comunicación. La información contenida en los widgets del informe no es exportable. Los informes detallados proporcionan información detallada relacionada con las áreas de cumplimiento de comunicaciones específicas y ofrecen la posibilidad de filtrar, agrupar, ordenar y exportar información durante la revisión.

El **Panel informes** contiene los siguientes widgets de informe e informes detallados:

- Widget de **coincidencias de directivas recientes** : muestra el número de coincidencias por Directiva activa a lo largo del tiempo.
- Widget **elementos resueltos por directiva** : muestra el número de alertas de coincidencia de directivas que la Directiva resuelve a lo largo del tiempo.
- **Usuarios con la mayoría** de los widgets de coincidencia de directivas: muestra los usuarios (o los nombres de usuario de anonimizan) y el número de coincidencias de directivas para un período determinado.
- **Directiva con el widget de más coincidencias** : muestra las directivas y el número de coincidencias de un período determinado, clasificados de mayor a menor para las coincidencias.
- **Extensiones por** widget de directiva: muestra el número de escalas por directiva a lo largo de un tiempo determinado.
- **Configuración de la Directiva e** informe detallado del estado: proporciona una visión detallada de la configuración y las opciones de la Directiva, así como el estado general de cada una de las directivas (coincidencias y acciones) en los mensajes. Use la opción *exportar* para crear un. Archivo CSV que contiene los detalles del informe.
- Informe detallado de **elementos y acciones por directiva** : Revise y exporte los elementos coincidentes y las acciones de corrección por directiva. Use la opción *exportar* para crear un. Archivo CSV que contiene los detalles del informe.
- Informe detallado de elementos **y acciones por ubicación** : Revise y exporte los elementos coincidentes y las acciones de corrección por ubicación de Microsoft 365. Use la opción *exportar* para crear un. Archivo CSV que contiene los detalles del informe.

## <a name="audit"></a>Auditoría

En algunos casos, debe proporcionar información a los auditores reglamentarios o de cumplimiento para demostrar la supervisión de las actividades y comunicaciones de los usuarios. Esta información puede ser un resumen de todas las actividades asociadas con una directiva de organización definida o cada vez que cambia una directiva de cumplimiento de la comunicación. Las directivas de cumplimiento de comunicaciones tienen pistas de auditoría integradas para una preparación completa de las auditorías internas o externas. Los historiales de auditoría detallados de cada acción de creación, edición y eliminación son capturados por las directivas de comunicación para proporcionar una prueba de los procedimientos de supervisión.

>[!Important]
>La auditoría debe estar habilitada para su organización antes de que se registren los eventos de cumplimiento de comunicaciones. Para habilitar la auditoría, consulte [Habilitar el registro de auditoría](communication-compliance-configure.md#step-2-required-enable-the-audit-log).

Para ver las actividades de actualización de la Directiva de cumplimiento de comunicaciones, seleccione el control **exportar actualizaciones de directivas** en la Página principal de cualquier directiva. Debe tener asignado el *administrador global* o los roles de *Administrador de cumplimiento* en la comunicación para exportar actividades de actualización. Esta acción genera un archivo de auditoría en el formato. csv que contiene la siguiente información:

|**Field**|**Detalles**|
|:-----|:-----|
| **CreationDate** | Fecha en que se realizó la actividad de actualización en una directiva. |
| **UserIds** | El usuario que realizó la actividad de actualización en una directiva. |
| **Operations** | Las operaciones de actualización realizadas en la Directiva. |
| **AuditData** | Este campo es el origen de datos principal para todas las actividades de actualización de directiva. Todas las actividades de actualización se registran y se separan mediante delimitadores de coma. |

Para ver las actividades de revisión de cumplimiento de comunicaciones de una directiva, seleccione el control **exportar actividades de revisión** en la página de **información general** de una directiva específica. Debe tener asignado el *administrador global* o los roles de *Administrador de cumplimiento* en las comunicaciones para exportar las actividades de revisión. Esta acción genera un archivo de auditoría en el formato. csv que contiene la siguiente información:

|**Field**|**Detalles**|
|:-----|:-----|
| **CreationDate** | Fecha en que se realizó la actividad de revisión en una directiva. |
| **UserIds** | El usuario que realizó la actividad de revisión en una directiva. |
| **Operations** | Las operaciones de revisión realizadas en la Directiva. |
| **AuditData** | Este campo es el origen de datos principal de todas las actividades de revisión de directivas. Todas las actividades de revisión se registran y se separan mediante delimitadores de coma. |

También puede ver actividades de auditoría en el registro de auditoría unificado o con el cmdlet [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) PowerShell.

Por ejemplo, en el siguiente ejemplo, se devuelven las actividades de todas las actividades de revisión de supervisión (directivas y reglas):

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType AeD -Operations SupervisoryReviewTag
```

En este ejemplo se devuelven las actividades de actualización de las directivas de cumplimiento de comunicaciones:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType Discovery -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeleted
```

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

Para configurar el cumplimiento de comunicaciones para la organización de Microsoft 365, vea [Configure Communication Compliance for your microsoft 365 Organization](communication-compliance-configure.md).
