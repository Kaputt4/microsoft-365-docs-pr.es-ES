---
title: Referencia de características de cumplimiento de comunicaciones
description: Referencia de características para el cumplimiento de comunicaciones en Microsoft 365. Obtenga información sobre los detalles y las especificaciones de cada uno de los componentes de la característica.
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
ms.openlocfilehash: 6260e28f5df8e6be82db90a6a7e3efa64516f4f8
ms.sourcegitcommit: c10eb675da725830e9776d2a0566ba3622eb361c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980093"
---
# <a name="communication-compliance-feature-reference"></a>Referencia de características de cumplimiento de comunicaciones

## <a name="policies"></a>Directivas

>[!Important]
>No se admite el uso de PowerShell para crear y administrar directivas de cumplimiento de comunicaciones. Para crear y administrar estas directivas, debe usar los controles de administración de directivas en la solución de cumplimiento de comunicaciones [de Microsoft 365.](https://compliance.microsoft.com/supervisoryreview)

Puede crear directivas de cumplimiento de comunicaciones para organizaciones de Microsoft 365 en el Centro de cumplimiento de Microsoft 365. Las directivas de cumplimiento de comunicaciones definen qué comunicaciones y usuarios están sujetos a revisión en su organización, definen las condiciones personalizadas que deben cumplir las comunicaciones y especifican quién debe realizar revisiones. Los usuarios asignados *al* rol de administrador de cumplimiento de comunicaciones pueden configurar directivas y cualquier persona que tenga asignado este rol puede acceder a la página de cumplimiento de comunicaciones y a la configuración global en el Centro de cumplimiento de Microsoft 365.  Si es necesario, puedes exportar el historial de modificaciones de una directiva a un archivo .csv que también incluya el estado de las alertas pendientes de revisión, los elementos escalados y los elementos resueltos. No se puede cambiar el nombre de las directivas y se pueden eliminar cuando ya no sea necesario.

>[!NOTE]
>Las directivas de supervisión creadas en el Centro de & cumplimiento para suscripciones de Office 365 no pueden migrar a Microsoft 365. Si va a migrar de una suscripción de Office 365 a una suscripción de Microsoft 365, deberá crear nuevas directivas de cumplimiento de comunicaciones para reemplazar las directivas de supervisión existentes.

## <a name="policy-templates"></a>Plantillas de directiva

Las plantillas de directiva son configuraciones de directiva predefinidas que puede usar para crear rápidamente directivas para abordar escenarios comunes de cumplimiento. Cada una de estas plantillas tiene diferencias en condiciones y ámbito, y todas las plantillas usan los mismos tipos de señales de examen. Puede elegir entre las siguientes plantillas de directiva:

|**Área**|**Plantilla de directiva**|**Detalles**|
|:-----|:-----|:-----|
| **Lenguaje ofensivo y contra el acoso** | Supervisar las comunicaciones para el idioma ofensivo | - Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype Empresarial <br> - Dirección: entrante, saliente, interna <br> - Porcentaje de revisión: 100 % <br> - Condiciones: clasificador de idioma ofensivo |
| **Información confidencial** | Supervisar las comunicaciones para obtener información confidencial | - Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype Empresarial <br> - Dirección: entrante, saliente, interna <br> - Porcentaje de revisión: 10 % <br> - Condiciones: información confidencial, patrones de contenido y tipos integrados, opción de diccionario personalizado, datos adjuntos de más de 1 MB |
| **Cumplimiento normativo** | Supervisar las comunicaciones para obtener información relacionada con el cumplimiento normativo financiero | - Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype Empresarial <br> - Dirección: entrante, saliente <br> - Porcentaje de revisión: 10 % <br> - Condiciones: opción de diccionario personalizado, datos adjuntos de más de 1 MB |
| **Conflicto de interés** | Supervisar las comunicaciones entre dos grupos o dos usuarios para ayudar a evitar conflictos de interés | - Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype Empresarial <br> - Dirección: interna <br> - Porcentaje de revisión: 100 % <br> - Condiciones: ninguna |

Las comunicaciones se examinan cada 24 horas desde el momento en que se crean las directivas. Por ejemplo, si crea una directiva de lenguaje ofensivo a las 11:00 a.m., la directiva recopilará señales de cumplimiento de comunicaciones cada 24 horas a las 11:00 a.m. diariamente. La edición de una directiva no cambia esta vez. Para ver la fecha y hora del último examen de una directiva, vaya a la columna Último examen *de directivas* en la **página** Directiva.

## <a name="permissions"></a>Permisos

>[!Important]
>De forma predeterminada, los administradores globales no tienen acceso a las características de cumplimiento de comunicaciones. Los roles asignados en este paso son necesarios antes de que se pueda acceder a las características de cumplimiento de comunicaciones.

Hay cinco grupos de roles que se usan para configurar permisos para administrar las características de cumplimiento de comunicaciones. Para que el cumplimiento de comunicaciones esté disponible como opción de menú en el Centro  de cumplimiento  de Microsoft 365 y para continuar con estos pasos de configuración, debe estar asignado a los grupos de roles Cumplimiento de comunicaciones o Administrador de cumplimiento de comunicaciones.  Para obtener acceso a las características de cumplimiento de comunicaciones y administrarlas después de la configuración inicial, los usuarios deben ser miembros de al menos un grupo de roles de cumplimiento de comunicaciones.

Dependiendo de cómo quiera administrar las directivas y alertas de comunicación, deberá asignar usuarios a grupos de roles específicos. Tiene la opción de asignar usuarios con diferentes responsabilidades de cumplimiento a grupos de roles específicos para administrar diferentes áreas de características de cumplimiento de comunicaciones. O puede decidir asignar todas las cuentas de usuario para administradores designados, analistas, investigadores y visores al grupo de roles *Cumplimiento* de comunicaciones. Use un único grupo de roles o varios grupos de roles para ajustarse mejor a sus requisitos de administración de cumplimiento.

Elija entre estas opciones de grupo de roles al configurar el cumplimiento de las comunicaciones:

|**Grupo de funciones**|**Permisos de grupo de roles**|
|:-----|:-----|
| **Cumplimiento de comunicaciones** | Use este grupo de roles para administrar el cumplimiento de las comunicaciones de su organización en un solo grupo. Al agregar todas las cuentas de usuario para administradores, analistas, investigadores y visores designados, puede configurar los permisos de cumplimiento de comunicaciones en un solo grupo. Este grupo de roles contiene todas las funciones de permisos de cumplimiento de comunicaciones. Esta configuración es la forma más sencilla de empezar rápidamente con el cumplimiento de las comunicaciones y es una buena opción para las organizaciones que no necesitan permisos independientes definidos para grupos de usuarios independientes. |
| **Administrador de cumplimiento de comunicaciones** | Use este grupo de roles para configurar inicialmente el cumplimiento de las comunicaciones y, posteriormente, separar a los administradores de cumplimiento de comunicaciones en un grupo definido. Los usuarios asignados a este grupo de roles pueden crear, leer, actualizar y eliminar directivas de cumplimiento de comunicaciones, configuraciones globales y asignaciones de grupos de roles. Los usuarios asignados a este grupo de roles no pueden ver alertas de mensajes. |
| **Analista de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que actuarán como analistas de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver directivas donde se asignan como revisores, ver metadatos de mensajes (no contenido del mensaje), escalar a revisores adicionales o enviar notificaciones a los usuarios. Los analistas no pueden resolver alertas pendientes. |
| **Investigador de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que actuarán como investigadores de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver los metadatos y el contenido de los mensajes, escalar a revisores adicionales, escalar a un caso de eDiscovery avanzado, enviar notificaciones a los usuarios y resolver la alerta. |
| **Visor de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que administrarán informes de comunicación. Los usuarios asignados a este grupo de roles pueden acceder a todos los widgets de informes en la página principal de cumplimiento de comunicaciones y ver todos los informes de cumplimiento de comunicaciones. |

### <a name="for-organizations-using-the-original-permissions-and-role-groups"></a>Para organizaciones que usan los permisos y grupos de roles originales

La nueva estructura del grupo de roles reemplaza la estructura inicial del grupo de roles para el cumplimiento de las comunicaciones. Para las organizaciones que ya usan el cumplimiento de comunicaciones, debe tener asignado el rol de administrador de revisión de supervisión para empezar a trabajar con el cumplimiento de comunicaciones en el Centro de cumplimiento de Microsoft 365. Además, tenía que crear un nuevo grupo de roles para los revisores con los roles Administrador de revisión de supervisión, Administración de casos, Administrador de cumplimiento y Revisión para investigar y corregir mensajes con coincidencias de directiva. Básicamente, todos los administradores y revisores estaban en un solo grupo de roles y todos tenían los mismos permisos de acceso y administración. Con las últimas actualizaciones de cumplimiento de comunicaciones, debe planear la migración de la estructura del grupo de roles anterior a la nueva estructura del grupo de roles. Se elimina gradualmente la compatibilidad con la estructura del grupo de roles anterior.

Para ayudar a planear la migración, tenga en cuenta el siguiente ejemplo. Actualmente tiene tres tipos de usuarios en su organización, administradores de TI, expertos y revisores. Estos tres tipos de usuarios se encuentran en la estructura anterior del grupo de roles y son todos miembros de un único grupo de funciones con los siguientes roles asignados:

- Administrador de revisión de supervisión
- Administración de casos
- Administrador de cumplimiento
- Revisar

Para actualizar los roles de estos usuarios para la nueva estructura del grupo de roles y separar los permisos de acceso y administración para los usuarios, puede considerar tres nuevos grupos y las asignaciones de nuevos grupos de roles asociados:

- **Administradores de TI: asignados** al nuevo grupo de roles *de administrador de cumplimiento de* comunicaciones.
- **Triage:** asignado al grupo de *roles de analista de cumplimiento de* comunicaciones.
- **Revisores:** asignado al nuevo grupo de roles *Investigación de cumplimiento de* comunicaciones.

## <a name="supervised-users"></a>Usuarios supervisados

Antes de empezar a usar el cumplimiento de las comunicaciones, debe determinar quién necesita que se revisen sus comunicaciones. En la directiva, las direcciones de correo electrónico de usuario identifican a personas o grupos de personas que se deben supervisar. Algunos ejemplos de estos grupos son Grupos de Microsoft 365, listas de distribución basadas en Exchange, comunidades de Yammer y canales de Microsoft Teams. También puedes excluir usuarios o grupos específicos del análisis con un grupo de exclusión específico o una lista de grupos.

>[!IMPORTANT]
>Los usuarios cubiertos por directivas de cumplimiento de comunicaciones deben tener una licencia de Cumplimiento de Microsoft 365 E5, una licencia de Office 365 Enterprise E3 con el complemento cumplimiento avanzado o estar incluidos en una suscripción de Office 365 Enterprise E5. Si no tiene un plan Enterprise E5 existente y desea probar el cumplimiento de las comunicaciones, puede registrarse para obtener una versión de prueba de [Office 365 Enterprise E5.](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="reviewers"></a>Reviewers

Al crear una directiva de cumplimiento de comunicaciones, debe determinar quién revisa los mensajes de los usuarios supervisados. En la directiva, las direcciones de correo electrónico de los usuarios identifican a personas o grupos de personas para revisar las comunicaciones supervisadas. Todos los revisores deben tener buzones hospedados en Exchange Online y deben estar asignados a los roles Análisis de *cumplimiento* de comunicaciones o Investigación de cumplimiento *de comunicaciones.* Los revisores (analistas o investigadores) también deben tener asignado el rol de administración de casos de cumplimiento *de* comunicaciones. Cuando se agregan revisores a una directiva, reciben automáticamente un mensaje de correo electrónico que les notifica la asignación a la directiva y proporciona vínculos a información sobre el proceso de revisión.

## <a name="groups-for-supervised-users-and-reviewers"></a>Grupos para usuarios y revisores supervisados

Para simplificar la configuración, cree grupos para las personas que necesitan revisar sus comunicaciones y grupos para las personas que revisan dichas comunicaciones. Si usa grupos, es posible que necesite varios. Por ejemplo, si desea examinar las comunicaciones entre dos grupos distintos de personas o si desea especificar un grupo que no esté supervisado.

Cuando asigna un grupo de distribución en la directiva, la directiva supervisa todos los correos electrónicos de cada usuario del grupo de distribución. Cuando asigna un grupo de Microsoft 365 en la directiva, la directiva supervisa todos los correos electrónicos enviados a ese grupo, no los correos electrónicos individuales recibidos por cada miembro del grupo.

La adición de grupos y listas de distribución a las directivas de cumplimiento de comunicaciones forma parte de las condiciones y reglas generales establecidas, por lo que el número máximo de grupos y listas de distribución que admite una directiva varía en función del número de condiciones que también se agreguen a la directiva. Cada directiva debe admitir aproximadamente 20 grupos o listas de distribución, en función del número de condiciones adicionales presentes en la directiva.

## <a name="supported-communication-types"></a>Tipos de comunicación admitidos

Con las directivas de cumplimiento de comunicaciones, puede elegir examinar los mensajes en una o varias de las siguientes plataformas de comunicación como un grupo o como orígenes independientes. Las comunicaciones capturadas en estas plataformas se conservan durante siete años para cada directiva de forma predeterminada, incluso si los usuarios abandonan su organización y sus buzones se eliminan.

- **Microsoft Teams:** se pueden analizar las comunicaciones de chat en canales de Microsoft Teams públicos y privados y chats individuales. Cuando los usuarios se asignan a una directiva de cumplimiento de comunicaciones con la cobertura de Microsoft Teams seleccionada, las comunicaciones de chat de los usuarios se supervisan automáticamente en todos los Microsoft Teams en los que los usuarios son miembros. La cobertura de Microsoft Teams se incluye automáticamente para las plantillas de directiva predefinidas y se selecciona de forma predeterminada en la plantilla de directiva personalizada. Los chats de Teams que coincidan con las condiciones de la directiva de cumplimiento de comunicaciones pueden tardar hasta 48 horas en procesarse. Use las siguientes configuraciones de administración de grupos para supervisar los chats de usuarios individuales y las comunicaciones de canal en Teams:

    - **Para las comunicaciones de chat de Teams:** Asignar usuarios individuales o asignar un [grupo de distribución](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) a la directiva de cumplimiento de comunicaciones. Esta configuración es para las relaciones de usuario/chat uno a uno o uno a varios.
    - **Para las comunicaciones del Canal de Teams:** Asigne todos los canales de Microsoft Teams o grupos de Microsoft 365 que desee examinar que contengan un usuario específico a la directiva de cumplimiento de comunicaciones. Si agrega el mismo usuario a otros canales de Microsoft Teams o grupos de Microsoft 365, asegúrese de agregar estos nuevos canales y grupos a la directiva de cumplimiento de comunicaciones.
    - Para las comunicaciones de chat de Teams con entornos de correo electrónico **híbridos:** el cumplimiento de las comunicaciones puede supervisar los mensajes de chat para los usuarios de organizaciones con una implementación local de Exchange o un proveedor de correo electrónico externo que haya habilitado Microsoft Teams. Debe crear un grupo de distribución para que los usuarios con buzones locales o externos puedan supervisar. Al crear una directiva de cumplimiento de comunicaciones, asignará este grupo de distribución como la selección de usuarios y grupos supervisados en el asistente para directivas. 

    >[!IMPORTANT]
    >Debe presentar una solicitud al Soporte técnico de Microsoft para que su organización pueda utilizar la interfaz gráfica de usuario en el Centro de seguridad y cumplimiento para buscar datos de chat de Teams de usuarios locales. Para obtener más información, consulte Buscar buzones [basados en la nube para usuarios locales.](search-cloud-based-mailboxes-for-on-premises-users.md)

Debe presentar una solicitud al Soporte técnico de Microsoft para que su organización pueda utilizar la interfaz gráfica de usuario en el Centro de seguridad y cumplimiento para buscar datos de chat de Teams en los buzones de correo basados en la nube para los usuarios locales.

- **Correo electrónico de Exchange:** todos los buzones hospedados en Exchange Online como parte de su suscripción a Microsoft 365 u Office 365 son aptos para el análisis de mensajes. Los mensajes de correo electrónico y los datos adjuntos de Exchange que coincidan con las condiciones de la directiva de cumplimiento de comunicaciones pueden tardar hasta 24 horas en procesarse. Los tipos de datos adjuntos admitidos para el cumplimiento de comunicaciones son los mismos que los tipos de archivo admitidos para las inspecciones de contenido de reglas [de flujo de correo de Exchange.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)

- **Yammer:** se pueden examinar los mensajes privados, las conversaciones públicas y los datos adjuntos asociados en las comunidades de Yammer. Cuando se agrega un usuario a la directiva de cumplimiento de comunicaciones que incluye Yammer como canal definido, las comunicaciones entre todas las comunidades de Yammer de las que el usuario es miembro se incluyen en el proceso de análisis. Los chats y datos adjuntos de Yammer que coincidan con las condiciones de la directiva de cumplimiento de comunicaciones pueden tardar hasta 24 horas en procesarse. Yammer debe estar en modo [nativo para que](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) las directivas de cumplimiento de comunicaciones supervisen las comunicaciones y los datos adjuntos de Yammer. En el modo nativo, todos los usuarios de Yammer están en Azure Active Directory (AAD), todos los grupos son Grupos de Office 365 y todos los archivos se almacenan en SharePoint Online.

- **Skype Empresarial Online:** las comunicaciones de chat y los datos adjuntos asociados en Skype Empresarial Online se pueden supervisar. Los chats de Skype Empresarial Online que coincidan con las condiciones de la directiva de cumplimiento de comunicaciones pueden tardar hasta 24 horas en procesarse. Las conversaciones de chat supervisadas se encuentran en conversaciones [anteriores guardadas en Skype Empresarial Online.](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2)  Use la siguiente configuración de administración de grupos para supervisar las comunicaciones de chat de usuario en Skype Empresarial Online:

    - **Para las comunicaciones de chat de Skype Empresarial Online:** asigne usuarios individuales o asigne un grupo de [distribución](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) a la directiva de cumplimiento de comunicaciones. Esta configuración es para relaciones de usuario/chat uno a uno o uno a varios.

- **Orígenes** de terceros: puede examinar las comunicaciones en busca de datos importados en buzones de su organización de Microsoft 365 desde orígenes de terceros como [Instant Bloomberg](archive-instant-bloomberg-data.md), [Slack,](archive-slack-data.md) [Zoom,](archive-zoommeetings-data.md)SMS y muchos otros. Para obtener una lista completa de los conectores compatibles con el cumplimiento de las comunicaciones, vea [Archivar datos de terceros.](archiving-third-party-data.md)

    Debe configurar un conector de terceros para su organización de Microsoft 365 antes de poder asignar el conector a una directiva de cumplimiento de comunicaciones. La **sección Orígenes de terceros** del Asistente para directivas de cumplimiento de comunicaciones solo muestra los conectores de terceros configurados actualmente.

## <a name="transitioning-from-supervision-in-office-365"></a>Transición desde la supervisión en Office 365

Las organizaciones que usan directivas de supervisión en Office 365 y planean la transición a directivas de cumplimiento de comunicaciones en Microsoft 365 necesitan comprender estos puntos importantes:

- Ambas soluciones pueden usarse en paralelo en la organización, pero las directivas usadas en cada solución deben tener nombres de directiva únicos. Los grupos y los diccionarios de palabras clave personalizadas se pueden compartir entre soluciones durante un período de transición.
- Los mensajes guardados en supervisión en las coincidencias de directivas de Office 365 no se pueden mover ni compartir en el cumplimiento de las comunicaciones en Microsoft 365.
- La solución de supervisión de Office 365 se reemplazará completamente por la solución de cumplimiento de comunicaciones de Microsoft 365. Se recomienda crear nuevas directivas en el cumplimiento de las comunicaciones que tengan la misma configuración que las directivas de supervisión existentes para usar las nuevas mejoras de investigación y corrección. Al realizar la transición al cumplimiento de comunicaciones en Microsoft 365, debe planear la exportación de datos de informes desde la supervisión en Office 365 si tiene requisitos de directiva de retención de cumplimiento interno.

Para obtener información sobre la retirada para la supervisión en Office 365, consulte la guía básica de [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para obtener más información.

## <a name="policy-settings"></a>Configuración de directivas

### <a name="users"></a>Usuarios

Tiene la opción de seleccionar Todos **los usuarios o** definir usuarios específicos en una directiva de cumplimiento de comunicaciones. Al seleccionar **Todos los usuarios,** se aplica la directiva a todos los usuarios y a todos los grupos en los que cualquier usuario está incluido como miembro. La definición de usuarios específicos aplica la directiva a los usuarios definidos y a los grupos en los que los usuarios definidos se incluyen como miembros.

### <a name="direction"></a>Dirección

De forma predeterminada, **se muestra la** condición Dirección y no se puede quitar. La configuración de la dirección de comunicación en una directiva se elige de forma individual o conjunta:

- **Entrante:** puede elegir Entrante **para** revisar las comunicaciones **enviadas a** las personas que eligió supervisar.
- **Saliente:** puede elegir **Saliente** si desea  revisar las comunicaciones enviadas desde las personas que eligió supervisar.
- **Interno:** puede elegir **Interno** para revisar las comunicaciones enviadas **entre** las personas que identificó en la directiva.

### <a name="sensitive-information-types"></a>Tipos de información confidencial

Tiene la opción de incluir tipos de información confidencial como parte de la directiva de cumplimiento de comunicaciones. Los tipos de información confidencial son tipos de datos predefinidos o personalizados que pueden ayudar a identificar y proteger números de tarjeta de crédito, números de cuentas bancarias, números de pasaporte y mucho más. Como parte de la prevención de pérdida de datos [(DLP),](data-loss-prevention-policies.md)la configuración de información confidencial puede usar patrones, proximidad de caracteres, niveles de confianza e incluso tipos de datos personalizados para ayudar a identificar y marcar el contenido que puede ser confidencial. Los tipos de información confidencial predeterminados son:

- Financiera
- Salud y salud
- Privacidad
- Tipo de información personalizada

Para obtener más información acerca de los detalles de información confidencial y los patrones incluidos en los tipos predeterminados, vea Definiciones de entidad de tipo [de información confidencial.](sensitive-information-type-entity-definitions.md)

### <a name="custom-keyword-dictionaries"></a>Diccionarios de palabras clave personalizadas

Configure diccionarios de palabras clave personalizados (o léxicos) para proporcionar una administración sencilla de palabras clave específicas de su organización o sector. Los diccionarios de palabras clave admiten hasta 100 KB de términos (posterior a la compresión) en el diccionario y admiten cualquier idioma. El límite del espacio empresarial también es de 100 KB después de la compresión. Si es necesario, puede aplicar varios diccionarios de palabras clave personalizadas a una sola directiva o tener un único diccionario de palabras clave por directiva. Estos diccionarios se asignan en una directiva de cumplimiento de comunicación y pueden obtenerse de un archivo (como una lista .csv o .txt) o de una lista que puede importar en el Centro de [cumplimiento.](create-a-keyword-dictionary.md) Use diccionarios personalizados cuando necesite admitir términos o idiomas específicos de su organización y directivas.

### <a name="classifiers"></a>Clasificadores

Los clasificadores globales y capacitados integrados analizan los mensajes enviados o recibidos en todos los canales de comunicación de la organización en busca de diferentes tipos de problemas de cumplimiento. Los clasificadores usan una combinación de inteligencia artificial y palabras clave para identificar el lenguaje de los mensajes que probablemente infrinjan las directivas contra el acoso. Actualmente, los clasificadores integrados solo admiten palabras clave en inglés en los mensajes.

Los clasificadores globales y capacitados para el cumplimiento de las comunicaciones analizan las comunicaciones en busca de términos, imágenes y opiniones para los siguientes tipos de idioma y contenido:

- **Amenaza:** busca amenazas para cometir violencia o daños físicos a una persona o propiedad.
- **Hostigamiento dirigido: explora** la conducta ofensiva dirigida a personas relacionadas con la carrera, el color, el color, el origen nacional.
- **Blasfez:** busca expresiones profanas que a la mayoría de las personas les da la mente.
- **Imágenes para adultos:** busca imágenes que son sexualmente explícitas por naturaleza.
- **Imágenes rizadas:** busca imágenes que sean sexualmente sugerentes por naturaleza, pero que contengan contenido menos explícito que las imágenes consideradas para adultos.
- **Imágenes gory:** busca imágenes que muestran la violencia y el sangre.

Los *clasificadores* de imágenes Para adultos, *Racy* y *Gory* analizan los archivos en . JPEG, . PNG, . GIF y . Formatos BMP. El tamaño de los archivos de imagen debe ser inferior a 4 megabytes (MB) y las dimensiones de las imágenes deben ser superiores a 50 x 50 píxeles y superiores a 50 kilobytes (KB) para que la imagen pueda ser evaluada. La identificación de imágenes es compatible con los mensajes de correo electrónico de Exchange Online y los canales y chats de Microsoft Teams.

Los clasificadores integrados que se pueden entrenar y los clasificadores globales no proporcionan una lista exhaustiva de términos o imágenes en estas áreas. Además, los estándares culturales y de idioma cambian continuamente y, a la luz de estas realidades, Microsoft se reserva el derecho de actualizar clasificadores a su criterio. Aunque los clasificadores pueden ayudar a su organización a supervisar estas áreas, los clasificadores no están diseñados para proporcionar el único medio de supervisión o direccionamiento de dichas imágenes o idiomas de su organización. Su organización, no Microsoft, sigue siendo responsable de todas las decisiones relacionadas con la supervisión, el examen y el bloqueo de idiomas e imágenes en estas áreas, incluido el cumplimiento de la privacidad local y otras leyes aplicables. Microsoft recomienda consultar a los asesores legales antes de su implementación y uso.

>[!NOTE]
>Las directivas que usan clasificadores inspeccionarán y evaluarán los mensajes con un recuento de palabras de seis o más. Los mensajes que contienen menos de seis palabras no se evalúan en las directivas que usan clasificadores. Para identificar y tomar medidas en mensajes más cortos que contengan contenido inapropiado, se recomienda incluir un diccionario de palabras clave personalizado para la supervisión de directivas de cumplimiento de comunicaciones para este tipo de contenido.

Para obtener información acerca de los clasificadores que se pueden entrenar en Microsoft 365, vea Introducción a los [clasificadores que se](classifier-get-started-with.md)pueden entrenar.

### <a name="conditional-settings"></a>Configuración condicional
<a name="ConditionalSettings"> </a>

Las condiciones que elija para la directiva se aplican a las comunicaciones de correo electrónico y de orígenes de terceros de su organización (como de Instant Bloomberg).

En la tabla siguiente se explica más acerca de cada condición.
  
|**Condition**|**Cómo usar esta condición**|
|:-----|:-----|
| **El contenido coincide con cualquiera de estos clasificadores** | Aplicar a la directiva cuando se incluyan o excluyan clasificadores en un mensaje. Algunos clasificadores están predefinidos en el espacio empresarial y los clasificadores personalizados deben configurarse por separado antes de que estén disponibles para esta condición. Solo se puede definir un clasificador como condición en una directiva. Para obtener más información acerca de la configuración de clasificadores, vea [Learn about trainable classifiers (preview).](classifier-learn-about.md) |
| **El contenido contiene cualquiera de estos tipos de información confidencial** | Aplicar a la directiva cuando se incluyan o excluyan tipos de información confidencial en un mensaje. Algunos clasificadores están predefinidos en el espacio empresarial y los clasificadores personalizados se pueden configurar por separado o como parte del proceso de asignación de condiciones. Cada tipo de información confidencial que elija se aplica por separado y solo uno de estos tipos de información confidencial debe aplicarse para que la directiva se aplique al mensaje. Para obtener más información acerca de los tipos personalizados de información confidencial, vea [Más información sobre los tipos de información confidencial.](sensitive-information-type-learn-about.md) |
| **El mensaje se recibe desde cualquiera de estos dominios**  <br><br> **El mensaje no se recibe de ninguno de estos dominios** | Aplique la directiva para incluir o excluir dominios o direcciones de correo electrónico específicos en los mensajes recibidos. Escriba cada dominio o dirección de correo electrónico y separe varios dominios o direcciones de correo electrónico con una coma. Cada dominio o dirección de correo electrónico especificado se aplica por separado, solo debe aplicarse un dominio o dirección de correo electrónico para que la directiva se aplique al mensaje. <br><br> Si desea examinar todo el correo electrónico de un dominio específico, pero desea excluir los mensajes que no necesitan  revisión (boletines, anuncios, entre otros), debe configurar que no se reciba un mensaje de ninguna condición de estos dominios que excluya la dirección de correo electrónico (por ejemplo, "newsletter@contoso.com"). |
| **El mensaje se envía a cualquiera de estos dominios**  <br><br> **El mensaje no se envía a ninguno de estos dominios** | Aplique la directiva para incluir o excluir dominios o direcciones de correo electrónico específicos en los mensajes enviados. Escriba cada dominio o dirección de correo electrónico y separe varios dominios o direcciones de correo electrónico con una coma. Cada dominio o dirección de correo electrónico se aplica por separado, solo debe aplicarse un dominio o dirección de correo electrónico para que la directiva se aplique al mensaje. <br><br> Si desea examinar todo el correo electrónico enviado a un dominio específico, pero desea excluir los mensajes enviados que no necesitan revisión, debe configurar dos condiciones: <br> - Se **envía un mensaje a cualquiera de estos dominios** condición que define el dominio ("contoso.com"), AND <br> - No **se envía un mensaje a ninguna condición de estos** dominios que excluya la dirección de correo electrónico ("subscriptions@contoso.com"). |
| **El mensaje se clasifica con cualquiera de estas etiquetas**  <br><br> **El mensaje no se clasifica con ninguna de estas etiquetas** | Para aplicar la directiva cuando se incluyen o excluyen determinadas etiquetas de retención en un mensaje. Las etiquetas de retención deben configurarse por separado y las etiquetas configuradas se eligen como parte de esta condición. Cada etiqueta que elija se aplica por separado (solo debe aplicarse una de estas etiquetas para que la directiva se aplique al mensaje). Para obtener más información acerca de las etiquetas de retención, vea [Más información sobre las directivas de retención y las etiquetas de retención.](retention.md)|
| **El mensaje contiene cualquiera de estas palabras**  <br><br> **El mensaje no contiene ninguna de estas palabras** | Para aplicar la directiva cuando determinadas palabras o frases se incluyan o excluyan en un mensaje, escriba cada palabra separada por una coma. Para frases de dos o más palabras, use comillas alrededor de la frase. Cada palabra o frase que escriba se aplica por separado (solo debe aplicarse una palabra para que la directiva se aplique al mensaje). Para obtener más información sobre cómo escribir palabras o frases, consulte la sección siguiente [Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords).|
| **Los datos adjuntos contienen cualquiera de estas palabras**  <br><br> **Los datos adjuntos no contienen ninguna de estas palabras** | Para aplicar la directiva cuando se incluyan o excluyan determinadas palabras o frases en un archivo adjunto de mensaje (como un documento de Word), escriba cada palabra separada por una coma. Para frases de dos o más palabras, use comillas alrededor de la frase. Cada palabra o frase que escriba se aplica por separado (solo debe aplicarse una palabra para que la directiva se aplique a los datos adjuntos). Para obtener más información sobre cómo escribir palabras o frases, consulte la sección siguiente [Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords).|
| **Los datos adjuntos son cualquiera de estos tipos de archivo**  <br><br> **Los datos adjuntos no son ninguno de estos tipos de archivo** | Para supervisar las comunicaciones que incluyen o excluyen tipos específicos de datos adjuntos, escriba las extensiones de archivo (como .exe o .pdf). Si desea incluir o excluir varias extensiones de archivo, escriba estas en líneas independientes. Solo debe coincidir una extensión de datos adjuntos para que se aplique la directiva.|
| **El tamaño del mensaje es mayor que**  <br><br> **El tamaño del mensaje no es mayor que** | Para revisar los mensajes en función de un tamaño determinado, use estas condiciones para especificar el tamaño máximo o mínimo que puede tener un mensaje antes de que esté sujeto a revisión. Por ejemplo, si  especifica que el tamaño del mensaje es superior a \> **1,0 MB,** todos los mensajes de 1,01 MB o más estarán sujetos a revisión. Puede elegir bytes, kilobytes, megabytes o gigabytes para esta condición.|
| **Los datos adjuntos son más grandes que**  <br><br> **Los datos adjuntos no son mayores que** | Para revisar los mensajes en función del tamaño de sus datos adjuntos, especifique el tamaño máximo o mínimo que puede tener un archivo adjunto antes de que el mensaje y sus datos adjuntos estén sujetos a revisión. Por ejemplo, si  especifica datos adjuntos de más de \> **2,0 MB,** todos los mensajes con datos adjuntos de 2,01 MB o más estarán sujetos a revisión. Puede elegir bytes, kilobytes, megabytes o gigabytes para esta condición.|
   
#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Coincidencia de palabras y frases para mensajes de correo electrónico o datos adjuntos
<a name="Matchwords"> </a>

Cada palabra que escriba y separe con una coma se aplica por separado (solo debe aplicarse una palabra para que la condición de directiva se aplique al correo electrónico o los datos adjuntos). Por ejemplo, vamos a usar la condición, **El** mensaje contiene cualquiera de estas palabras, con las palabras clave "banker", "confidential" y "insider trading" separadas por una coma (banker, confidential, "insider trading"). La directiva se aplica a cualquier mensaje que incluya la palabra "banker", "confidential" o la frase "insider trading". Solo una de estas palabras o frases debe aparecer para que esta condición de directiva se aplique. Las palabras del mensaje o los datos adjuntos deben coincidir exactamente con lo que escriba.

>[!IMPORTANT]
>Al importar un archivo de diccionario personalizado, cada palabra o frase debe separarse con un retorno de carro y en una línea independiente. <br> Por ejemplo: <br><br>
>*banker* <br>
>*confidencial* <br>
>*insider trading*

Para examinar los mensajes de correo electrónico y los datos adjuntos [](create-a-keyword-dictionary.md) de las mismas palabras clave, cree una directiva de prevención de pérdida de datos con un diccionario de palabras clave personalizado para los [términos](create-test-tune-dlp-policy.md) que desea analizar en los mensajes. Esta configuración de directiva identifica palabras clave definidas que aparecen en el mensaje de correo **electrónico o** en los datos adjuntos de correo electrónico. El uso de la configuración de directiva condicional estándar *(el* mensaje contiene cualquiera de estas palabras y  *los* datos adjuntos contienen cualquiera de estas palabras) para identificar los términos de los mensajes y los datos adjuntos requiere que los términos se presenten tanto en el mensaje como en los datos adjuntos.
  
#### <a name="enter-multiple-conditions"></a>Especificar varias condiciones

Si especifica varias condiciones, Microsoft 365 usa todas las condiciones juntas para determinar cuándo aplicar la directiva de cumplimiento de comunicaciones a los elementos de comunicación. Al configurar varias condiciones, se deben cumplir todas las condiciones para que se aplique la directiva, a menos que escriba una excepción. Por ejemplo, necesita una directiva que se aplique si un mensaje contiene la palabra "trade" y tiene un tamaño superior a 2 MB. Sin embargo, si el mensaje también contiene las palabras "Aprobado por Contoso financiero", la directiva no debe aplicarse. En este ejemplo, las tres condiciones se definirían de la siguiente manera:
  
- **El mensaje contiene cualquiera de estas palabras,** con la palabra clave "trade"
- **El tamaño del mensaje es mayor que**, con el valor 2 MB
- **El mensaje no contiene ninguna de estas palabras,** con las palabras clave "Aprobado por el equipo financiero de Contoso"

### <a name="review-percentage"></a>Porcentaje de revisión

Si desea reducir la cantidad de contenido que se va a revisar, puede especificar un porcentaje de todas las comunicaciones regida por una directiva de cumplimiento de comunicaciones. Se selecciona una muestra aleatoria en tiempo real del contenido del porcentaje total de contenido que coincide con las condiciones de directiva elegidas. Si desea que los revisores revisen todos los elementos, puede configurar **el 100 %** en una directiva de cumplimiento de comunicaciones.

## <a name="privacy"></a>Privacidad

Proteger la privacidad de los usuarios que tienen coincidencias de directiva es importante y puede ayudar a promover la objectividad en la investigación de datos y las revisiones de análisis para alertas de cumplimiento de comunicaciones. Esta configuración solo se aplica a los nombres de usuario que se muestran en la solución de cumplimiento de comunicaciones. No afecta a cómo se muestran los nombres en otras soluciones de cumplimiento o centro de administración.

Para los usuarios con una coincidencia de cumplimiento de comunicaciones, puede elegir una de las siguientes opciones en la configuración de cumplimiento **de comunicaciones:**

- **Mostrar versiones anónimas** de nombres de usuario: los  nombres de usuario se anonimizan para evitar que los usuarios del grupo de roles de analista de cumplimiento de comunicaciones vean quién está asociado a las alertas de directiva. Los usuarios del grupo *de roles Investigación de* cumplimiento de comunicaciones siempre verán los nombres de usuario, no las versiones anónimas. Por ejemplo, un usuario "Grace Grace" aparecería con un seudónimo aleatorio como "AnonIS8-988" en todas las áreas de la experiencia de cumplimiento de comunicaciones. Al elegir esta opción, se anonimizan todos los usuarios con coincidencias de directiva actuales y pasadas y se aplica a todas las directivas. La información de perfil de usuario en los detalles de alertas de cumplimiento de comunicaciones no estará disponible cuando se seleccione esta opción. Sin embargo, los nombres de usuario se muestran al agregar nuevos usuarios a directivas existentes o al asignar usuarios a nuevas directivas. Si decide desactivar esta configuración, se mostrarán los nombres de usuario de todos los usuarios que tengan coincidencias de directiva actuales o pasadas.
- **No mostrar versiones anónimas** de nombres de usuario: los nombres de usuario se muestran para todas las coincidencias de directiva actuales y pasadas para las alertas de cumplimiento de comunicaciones. La información de perfil de usuario (nombre, título, alias y organización o departamento) se muestra al usuario para todas las alertas de cumplimiento de comunicaciones.

## <a name="notice-templates"></a>Plantillas de aviso

Puede crear plantillas de aviso si desea enviar a los usuarios un aviso de correo electrónico para las coincidencias de directiva como parte del proceso de resolución de problemas. Los avisos solo se pueden enviar a la dirección de correo electrónico del usuario asociada con la coincidencia de directiva que generó la alerta específica de corrección. Al seleccionar una plantilla de aviso para aplicar a una infracción de directiva como parte del flujo de trabajo de corrección, puede elegir aceptar los valores de campo definidos en la plantilla o sobrescribir los campos según sea necesario.

Las plantillas de avisos son plantillas de correo electrónico personalizadas donde puede definir los siguientes campos de mensaje en el área configuración de **cumplimiento de** comunicaciones:

|**Field**|**Required**| **Detalles** |
|:-----|:-----|:-----|
|**Nombre de la plantilla** | Sí | El nombre descriptivo de la plantilla de aviso que seleccionará en el flujo de trabajo de notificación durante la corrección admite caracteres de texto. |
| **Dirección del remitente** | Sí | La dirección de uno o más usuarios o grupos que envían el mensaje al usuario con una coincidencia de directiva, seleccionada en Active Directory para su suscripción. |
| **Direcciones CC y CCO** | No | Usuarios o grupos opcionales a los que se notificará la coincidencia de directiva, seleccionados desde Active Directory para su suscripción. |
| **Asunto** | Sí | La información que aparece en la línea de asunto del mensaje admite caracteres de texto. |
| **Cuerpo del mensaje** | Sí | La información que aparece en el cuerpo del mensaje admite texto o valores HTML. |

### <a name="html-for-notices"></a>HTML para avisos

Si desea crear algo más que un mensaje de correo electrónico simple basado en texto para las notificaciones, puede crear un mensaje más detallado mediante HTML en el campo del cuerpo del mensaje de una plantilla de aviso. En el siguiente ejemplo se proporciona el formato del cuerpo del mensaje para una plantilla básica de notificación de correo electrónico basada en HTML:

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
>Actualmente, la implementación del atributo href HTML en las plantillas de notificación de cumplimiento de comunicaciones solo admite comillas simples en lugar de comillas dobles para las referencias a direcciones URL.

## <a name="filters"></a>Filtros

Los filtros de cumplimiento de comunicaciones permiten filtrar y ordenar los mensajes de alerta para realizar acciones de investigación y corrección más rápidas. El filtrado está disponible en **las pestañas** **Pendiente** y Resuelto para cada directiva. Para guardar un filtro o un conjunto de filtros como una consulta de filtro guardada, uno o más valores deben configurarse como selecciones de filtro. En la tabla siguiente se describen los detalles del filtro:

|**Filtro**|**Detalles**|
|:-----|:-----|
| **Fecha** | La fecha en que un usuario de la organización envió o recibió el mensaje. Para filtrar por un solo día, seleccione un intervalo de fechas que comience por el día para el que desea obtener los resultados y termine con el día siguiente. Por ejemplo, si desea filtrar los resultados del 20/9/2020, elegiría un intervalo de fechas de filtro del 20/9/2020-9/21/2020.|
| **Clase File** | La clase del mensaje en función del tipo de mensaje, ya sea *mensaje o* *datos adjuntos.* |
| **Tiene datos adjuntos** | La presencia de datos adjuntos en el mensaje. |
| **Clase Item** | El origen del mensaje en función del tipo de mensaje, el correo electrónico, el chat de Microsoft Team, Bloomberg, etc. Para obtener más información sobre tipos de elementos y clases de mensajes comunes, vea [Tipos de elementos y clases de mensajes.](https://docs.microsoft.com/office/vba/outlook/concepts/forms/item-types-and-message-classes) |
| **Dominios de destinatario** | Dominio al que se envió el mensaje. Este dominio suele ser su dominio de suscripción de Microsoft 365 de forma predeterminada. |
| **Recipient** | El usuario al que se envió el mensaje. |
| **Sender** | La persona que envió el mensaje. |
| **Dominio del remitente** | Dominio que envió el mensaje. |
| **Tamaño** | El tamaño del mensaje en KB. |
| **Asunto/Título** | Asunto del mensaje o título del chat. |
| **Tags** | Las etiquetas asignadas a un mensaje, ya sea *Questionable*, *Compliant* o *Non-compliant*. |
| **Escalado a** | El nombre de usuario de la persona incluida como parte de una acción de escalamiento de mensajes. |
| **Clasificadores** | El nombre de los clasificadores integrados y personalizados que se aplican al mensaje. Algunos ejemplos incluyen *lenguaje ofensivo,* *acoso* dirigido, blasfismo, *amenaza* y mucho más. 

## <a name="alert-policies"></a>Directivas de alerta

Después de configurar una directiva, se crea automáticamente una directiva de alerta correspondiente y se generan alertas para los mensajes que coinciden con las condiciones definidas en la directiva. De forma predeterminada, a todos los desencadenadores de alerta de coincidencia de directiva se les asigna un nivel de gravedad de medio en la directiva de alerta asociada. Las alertas se generan para una directiva de cumplimiento de comunicaciones una vez que se alcanza el nivel de umbral del desencadenador de agregación en la directiva de alerta asociada.

Para las directivas de cumplimiento de comunicaciones, los siguientes valores de directiva de alerta están configurados de forma predeterminada:

|**Desencadenador de directiva de alerta**|**Valor predeterminado**|
|:-----|:-----|
| Agregación | Agregación simple |
| Umbral | 4 actividades |
| Window | 60 minutos |

>[!Note]
>La configuración del desencadenador de umbral de la directiva de alerta para las actividades admite un valor mínimo de 3 o superior para las directivas de cumplimiento de comunicaciones.

Puede cambiar la configuración predeterminada para desencadenadores en número de actividades, período de  las actividades y para usuarios específicos en directivas de alerta en la página Directivas de alerta en el Centro de seguridad & cumplimiento.

### <a name="change-the-severity-level-for-an-alert-policy"></a>Cambiar el nivel de gravedad de una directiva de alerta

Si desea cambiar el nivel de gravedad asignado en una directiva de alerta para una directiva de cumplimiento de comunicación específica, siga estos pasos:

1. Inicie sesión [https://compliance.microsoft.com](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador de su organización de Microsoft 365.

2. En el Centro de cumplimiento de Microsoft 365, vaya a **Directivas.**

3. Seleccione **alerta de Office 365** en  la página Directivas para abrir la página Directivas de alertas en el Centro de seguridad & cumplimiento de **Office 365.** 

4. Active la casilla de verificación de la directiva de cumplimiento de comunicaciones que desea actualizar y, a continuación, **seleccione Editar directiva.**

5. En la **pestaña Descripción,** selecciona la lista desplegable **Gravedad** para configurar el nivel de alerta de directiva.

6. Seleccione **Guardar** para aplicar el nuevo nivel de gravedad a la directiva.

7. Seleccione **Cerrar para** salir de la página de detalles de la directiva de alertas.

## <a name="power-automate-flows"></a>Flujos de Power Automate

[Microsoft Power Automate es](https://docs.microsoft.com/power-automate/getting-started) un servicio de flujo de trabajo que automatiza las acciones entre aplicaciones y servicios. Mediante el uso de flujos de plantillas o creados manualmente, puede automatizar tareas comunes asociadas a estas aplicaciones y servicios. Al habilitar los flujos de Power Automate para el cumplimiento de las comunicaciones, puede automatizar tareas importantes para alertas y usuarios. Puede configurar los flujos de Power Automate para notificar a los administradores cuando los usuarios tienen alertas de cumplimiento de comunicaciones y otras aplicaciones.

Los clientes con suscripciones de Microsoft 365 que incluyen cumplimiento de comunicaciones no necesitan licencias adicionales de Power Automate para usar la plantilla de Power Automate de cumplimiento de comunicaciones predeterminada recomendada. La plantilla predeterminada se puede personalizar para admitir su organización y cubrir los escenarios principales de cumplimiento de comunicaciones. Si decide usar las características premium de Power Automate en estas plantillas, crear una plantilla personalizada con el conector de cumplimiento de Microsoft 365 o usar plantillas de Power Automate para otras áreas de cumplimiento en Microsoft 365, es posible que necesite licencias adicionales de Power Automate.

>[!IMPORTANT]
>¿Recibe solicitudes de validación de licencia adicional al probar los flujos de Power Automate? Es posible que su organización aún no haya recibido actualizaciones de servicio para esta característica de vista previa. Se están implementando actualizaciones y todas las organizaciones con suscripciones de Microsoft 365 que incluyan cumplimiento de comunicaciones deben tener compatibilidad con licencias para los flujos creados a partir de las plantillas recomendadas de Power Automate antes del 30 de octubre de 2020.

![Cumplimiento de comunicaciones Power Automate](../media/communication-compliance-power-automate.png)

La siguiente plantilla de Power Automate se proporciona a los clientes para admitir la automatización de procesos para las alertas de cumplimiento de comunicaciones:

- **Notificar al administrador cuando un usuario tiene** una alerta de cumplimiento de comunicaciones: es posible que algunas organizaciones necesiten recibir una notificación de administración inmediata cuando un usuario tiene una alerta de cumplimiento de comunicaciones. Cuando se configura y selecciona este flujo, se envía un mensaje de correo electrónico al administrador del usuario del caso con la siguiente información sobre todas las alertas:
    - Directiva aplicable para la alerta
    - Fecha y hora de la alerta
    - Nivel de gravedad de la alerta

### <a name="create-a-power-automate-flow"></a>Crear un flujo de Power Automate

Para crear un flujo de Power Automate a partir de una plantilla predeterminada recomendada, usará la opción Administrar flujos de **Power Automate** desde el control **Automatizar** cuando trabaje directamente en una alerta. Para crear un flujo de Power Automate con Administrar flujos **de Power Automate,** debe ser miembro de al menos un grupo de roles de cumplimiento de comunicaciones.

Siga estos pasos para crear un flujo de Power Automate a partir de una plantilla predeterminada:

1. En el Centro de cumplimiento de Microsoft 365, vaya a Directivas de cumplimiento de comunicaciones y seleccione la directiva con la  >   alerta que desea revisar.
2. En la directiva, seleccione la **pestaña** Pendiente y seleccione una alerta pendiente.
3. Selecciona **Power Automate** en el menú de acción de alerta.
4. En la **página Power Automate,** seleccione una plantilla predeterminada de las plantillas de cumplimiento de comunicación que **le pueden gustar** en la sección de la página.
5. El flujo enumerará las conexiones incrustadas necesarias para el flujo y se mostrará si los estados de conexión están disponibles. Si es necesario, actualice las conexiones que no se muestran como disponibles. Seleccione **Continuar**.
6. De forma predeterminada, los flujos recomendados están preconfigurados con el cumplimiento de las comunicaciones recomendado y los campos de datos de servicio de Microsoft 365 necesarios para completar la tarea asignada para el flujo. Si es necesario, personalice los componentes de flujo mediante el control **Mostrar** opciones avanzadas y configurando las propiedades disponibles para el componente de flujo.
7. Si es necesario, agregue los pasos adicionales al flujo seleccionando el **botón Nuevo** paso. En la mayoría de los casos, este cambio no debe ser necesario para las plantillas predeterminadas recomendadas.
8. Seleccione **Guardar borrador** para guardar el flujo para una configuración posterior más adelante o seleccione Guardar para completar la configuración del flujo. 
9. Seleccione **Cerrar para** volver a la página de flujo de Power Automate. La nueva plantilla aparecerá como un  flujo en la pestaña Mis flujos y estará disponible automáticamente desde el control de Power Automate para el usuario que creó el flujo al trabajar con alertas de cumplimiento de comunicaciones.

### <a name="share-a-power-automate-flow"></a>Compartir un flujo de Power Automate

De forma predeterminada, los flujos de Power Automate creados por un usuario solo están disponibles para ese usuario. Para que otros usuarios de cumplimiento de comunicaciones tengan acceso y usen un flujo, el creador del flujo debe compartir el flujo. Para compartir un flujo, usarás el control **de Power Automate** cuando trabajes directamente en una alerta.

Para compartir un flujo de Power Automate, debe ser miembro de al menos un grupo de roles de cumplimiento de comunicaciones.
Siga estos pasos para compartir un flujo de Power Automate:

1. En el Centro de cumplimiento de Microsoft 365, vaya a Directivas de cumplimiento de comunicaciones y seleccione la directiva con la  >   alerta que desea revisar.
2. En la directiva, seleccione la **pestaña** Pendiente y seleccione una alerta pendiente.
3. Selecciona **Power Automate** en el menú de acción de alerta.
4. En la página **Flujos de Power Automate,** seleccione la **pestaña Mis flujos** o **Flujos de** equipo.
5. Seleccione el flujo que desea compartir y, a continuación, **seleccione Compartir** en el menú de opciones de flujo.
6. En la página de uso compartido de flujo, escriba el nombre del usuario o grupo que desea agregar como propietario del flujo.
7. En el **cuadro de diálogo** Conexión usada, seleccione **Aceptar** para confirmar que el usuario o grupo agregado tendrá acceso completo al flujo.

### <a name="edit-a-power-automate-flow"></a>Editar un flujo de Power Automate

Si necesitas editar un flujo, usarás el control **de Power Automate** cuando trabajes directamente en una alerta. Para editar un flujo de Power Automate, debe ser miembro de al menos un grupo de roles de cumplimiento de comunicaciones.

Siga estos pasos para editar un flujo de Power Automate:

1. En el Centro de cumplimiento de Microsoft 365, vaya a Directivas de cumplimiento de comunicaciones y seleccione la directiva con la  >   alerta que desea revisar.
2. En la directiva, seleccione la **pestaña** Pendiente y seleccione una alerta pendiente.
3. Selecciona **Power Automate** en el menú de acción de alerta.
4. En la **página Flujos de Power Automate,** seleccione flujo para editar. Seleccione **Editar en** el menú de control de flujo.
5. Seleccione la configuración **de puntos suspensivos** para cambiar la configuración de un componente de flujo o la eliminación de puntos suspensivos  >   para eliminar un componente de   >   flujo.
6. Seleccione **Guardar** y, a **continuación,** Cerrar para completar la edición del flujo.

### <a name="delete-a-power-automate-flow"></a>Eliminar un flujo de Power Automate

Si necesita eliminar un flujo, usará el control **de Power Automate** cuando trabaje directamente en una alerta. Para eliminar un flujo de Power Automate, debe ser miembro de al menos un grupo de roles de cumplimiento de comunicaciones.

Siga estos pasos para eliminar un flujo de Power Automate:

1. En el Centro de cumplimiento de Microsoft 365, vaya a Directivas de cumplimiento de comunicaciones y seleccione la directiva con la  >   alerta que desea revisar.
2. En la directiva, seleccione la **pestaña** Pendiente y seleccione una alerta pendiente.
3. Selecciona **Power Automate** en el menú de acción de alerta.
4. En la **página Flujos de Power Automate,** seleccione el flujo que desea eliminar. Seleccione **Eliminar en** el menú de control de flujo.
5. En el cuadro de diálogo de confirmación de eliminación, seleccione **Eliminar** para quitar el flujo o **cancelar** para salir de la acción de eliminación.

## <a name="reports-preview"></a>Informes (versión preliminar)

El nuevo panel **informes** es la ubicación central para ver todos los informes de cumplimiento de comunicaciones. Los widgets de informes proporcionan una vista rápida de las conclusiones más necesarias para una evaluación general del estado de las actividades de cumplimiento de las comunicaciones. La información contenida en los widgets del informe no se puede exportar. Los informes detallados proporcionan información detallada relacionada con áreas específicas de cumplimiento de comunicaciones y ofrecen la capacidad de filtrar, agrupar, ordenar y exportar información mientras se revisa.

El **panel Informes contiene** los siguientes widgets de informes y vínculos de informes detallados:

- **Widget Coincidencias de directivas** recientes: muestra el número de coincidencias por directiva activa a lo largo del tiempo.
- **Elementos resueltos por** widget de directiva: muestra el número de alertas de coincidencia de directiva resueltas por directiva a lo largo del tiempo.
- **Usuarios con la mayoría del** widget de coincidencia de directiva: muestra los usuarios (o nombres de usuario anonimizados) y el número de coincidencias de directiva durante un período determinado.
- **Directiva con el** widget con más coincidencias: muestra las directivas y el número de coincidencias de un período determinado, clasificados de mayor a menor para las coincidencias.
- **Escalaciones por** widget de directiva: muestra el número de escalaciones por directiva en un momento determinado.
- **Informe** detallado de configuración de directiva y estado: proporciona una vista detallada de la configuración y la configuración de la directiva, así como el estado general de cada directiva (coincidencias y acciones) en los mensajes. Use la *opción* Exportar para crear un archivo . Archivo CSV que contiene los detalles del informe.
- **Elementos y acciones por informe detallado** de directiva: revisar y exportar elementos y acciones de corrección correspondientes por directiva. Use la *opción* Exportar para crear un archivo . Archivo CSV que contiene los detalles del informe.
- **Elemento y acciones por informe detallado** de ubicación: revisar y exportar elementos y acciones de corrección correspondientes por ubicación de Microsoft 365. Use la *opción* Exportar para crear un archivo . Archivo CSV que contiene los detalles del informe.

## <a name="audit"></a>Auditoría

En algunos casos, debe proporcionar información a auditores normativos o de cumplimiento para demostrar la supervisión de las actividades y comunicaciones de los usuarios. Esta información puede ser un resumen de todas las actividades asociadas a una directiva organizativa definida o en cualquier momento en que cambie una directiva de cumplimiento de comunicaciones. Las directivas de cumplimiento de comunicaciones tienen pistas de auditoría integradas para una preparación completa para las auditorías internas o externas. Las directivas de comunicación capturan historiales de auditoría detallados de cada acción de creación, edición y eliminación para proporcionar pruebas de procedimientos de supervisión.

>[!Important]
>La auditoría debe estar habilitada para su organización antes de que se grabe el cumplimiento de las comunicaciones. Para habilitar la auditoría, vea [Habilitar el registro de auditoría.](communication-compliance-configure.md#step-2-required-enable-the-audit-log)

Para ver las actividades de actualización de directivas de cumplimiento de comunicaciones, seleccione el control Exportar actualizaciones **de** directivas en la página principal de cualquier directiva. Debe tener asignados los roles Administrador *global* o Administrador *de cumplimiento de comunicaciones* para exportar actividades de actualización. Esta acción genera un archivo de auditoría en el formato .csv que contiene la siguiente información:

|**Field**|**Detalles**|
|:-----|:-----|
| **CreationDate** | La fecha en que se realizó la actividad de actualización en una directiva. |
| **UserIds** | El usuario que realizó la actividad de actualización en una directiva. |
| **Operations** | Las operaciones de actualización realizadas en la directiva. |
| **AuditData** | Este campo es el origen de datos principal para todas las actividades de actualización de directivas. Todas las actividades de actualización se registran y separan mediante delimitadores de coma. |

Para ver las actividades de revisión de cumplimiento de  comunicaciones de una directiva, seleccione el control Exportar **actividades** de revisión en la página Información general de una directiva específica. Debe tener asignados los roles Administrador *global* o Administrador *de cumplimiento de comunicaciones* para exportar las actividades de revisión. Esta acción genera un archivo de auditoría en el formato .csv que contiene la siguiente información:

|**Field**|**Detalles**|
|:-----|:-----|
| **CreationDate** | La fecha en que se realizó la actividad de revisión en una directiva. |
| **UserIds** | El usuario que realizó la actividad de revisión en una directiva. |
| **Operations** | Las operaciones de revisión realizadas en la directiva. |
| **AuditData** | Este campo es el origen de datos principal para todas las actividades de revisión de directivas. Todas las actividades de revisión se registran y separan por delimitadores de coma. |

También puede ver las actividades de auditoría en el registro de auditoría unificado o con el cmdlet [de PowerShell Search-UnifiedAuditLog.](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog)

Por ejemplo, en el siguiente ejemplo se devuelven las actividades de todas las actividades de revisión de supervisión (directivas y reglas):

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType AeD -Operations SupervisoryReviewTag
```

En este ejemplo se devuelven las actividades de actualización de las directivas de cumplimiento de comunicaciones:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType Discovery -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeleted
```

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

Para configurar el cumplimiento de comunicaciones para su organización de Microsoft 365, consulte Configurar el cumplimiento de comunicaciones [para su organización de Microsoft 365.](communication-compliance-configure.md)
