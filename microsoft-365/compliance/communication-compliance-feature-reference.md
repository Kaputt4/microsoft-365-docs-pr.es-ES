---
title: Referencia de característica de cumplimiento de comunicaciones
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
ms.openlocfilehash: 87f5e414a13d966ba2fbb30d84d7d4adae7a1d13
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624354"
---
# <a name="communication-compliance-feature-reference"></a>Referencia de característica de cumplimiento de comunicaciones

## <a name="policies"></a>Directivas

>[!Important]
>No se admite el uso de PowerShell para crear y administrar directivas de cumplimiento de comunicaciones. Para crear y administrar estas directivas, debe usar los controles de administración de directivas en la [Microsoft 365 de cumplimiento de comunicaciones](https://compliance.microsoft.com/supervisoryreview).

Puede crear directivas de cumplimiento de comunicaciones para organizaciones de Microsoft 365 en el Centro de cumplimiento de Microsoft 365. Las directivas de cumplimiento de comunicación definen qué comunicaciones y usuarios están sujetos a revisión en su organización, definen las condiciones personalizadas que deben cumplir las comunicaciones y especifican quién debe hacer las revisiones. Los usuarios asignados *al* rol de administrador de cumplimiento de comunicaciones pueden configurar directivas y cualquier persona que tenga asignada esta función puede tener acceso a la página Cumplimiento de comunicaciones y a la configuración global del centro de Microsoft 365 cumplimiento.  Si es necesario, puede exportar el historial de modificaciones de una directiva a un archivo .csv (valores separados por comas) que también incluya el estado de las alertas pendientes de revisión, los elementos escalados y los elementos resueltos. No se puede cambiar el nombre de las directivas y se pueden eliminar cuando ya no sea necesario.

>[!NOTE]
>Las directivas de supervisión creadas en el Centro de seguridad & cumplimiento para Office 365 suscripciones no pueden migrar a Microsoft 365. Si está migrando de una suscripción de Office 365 a una suscripción de Microsoft 365, deberá crear nuevas directivas de cumplimiento de comunicaciones para reemplazar las directivas de supervisión existentes.

## <a name="policy-templates"></a>Plantillas de directiva

Las plantillas de directiva son configuraciones de directiva predefinidas que puede usar para crear rápidamente directivas para abordar escenarios de cumplimiento comunes. Cada una de estas plantillas tiene diferencias en las condiciones y el ámbito, y todas las plantillas usan los mismos tipos de señales de examen. Puede elegir entre las siguientes plantillas de directiva:

|**Área**|**Plantilla de directiva**|**Detalles**|
|:-----|:-----|:-----|
| **Lenguaje ofensivo y contra el acoso** | Supervisar las comunicaciones en busca de lenguaje ofensivo | - Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype Empresarial <br> - Dirección: entrante, saliente, interno <br> - Porcentaje de revisión: 100% <br> - Condiciones: clasificador de idioma ofensivo |
| **Información confidencial** | Supervisar las comunicaciones para obtener información confidencial | - Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype Empresarial <br> - Dirección: entrante, saliente, interno <br> - Porcentaje de revisión: 10% <br> - Condiciones: información confidencial, patrones de contenido y tipos integrados, opción de diccionario personalizado, datos adjuntos de más de 1 MB |
| **Cumplimiento normativo** | Supervisar las comunicaciones para obtener información relacionada con el cumplimiento normativo financiero | - Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype Empresarial <br> - Dirección: entrante, saliente <br> - Porcentaje de revisión: 10% <br> - Condiciones: opción de diccionario personalizado, datos adjuntos de más de 1 MB |
| **Conflicto de intereses** | Supervisar las comunicaciones entre dos grupos o dos usuarios para ayudar a evitar conflictos de interés | - Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype Empresarial <br> - Dirección: interna <br> - Porcentaje de revisión: 100% <br> - Condiciones: Ninguna |

Las comunicaciones se examinan cada 24 horas a partir del momento en que se crean las directivas. Por ejemplo, si crea una directiva de idioma ofensivo a las 11:00 a.m., la directiva recopilará señales de cumplimiento de comunicaciones cada 24 horas a las 11:00 a.m. todos los días. La edición de una directiva no cambia esta vez. Para ver la última fecha y hora de examen de una directiva, vaya a la columna Último *examen de* directivas de la **página** Directiva. Después de crear una nueva directiva, puede tardar hasta 24 horas en ver la primera fecha y hora del examen de directivas. La fecha y hora del último examen se convertirán en la zona horaria del sistema local.

## <a name="permissions"></a>Permisos

>[!Important]
>De forma predeterminada, los administradores globales no tienen acceso a las características de cumplimiento de la comunicación. Los roles asignados en este paso son necesarios antes de que se pueda acceder a las características de cumplimiento de comunicaciones.

Hay cinco grupos de roles que se usan para configurar permisos para administrar las características de cumplimiento de comunicaciones. Para que **el** cumplimiento de la comunicación esté disponible como una opción de menú en  el Centro de cumplimiento de Microsoft 365 y para continuar con estos pasos de configuración, debe asignarse a los grupos de roles Cumplimiento de comunicaciones o Administración de cumplimiento *de* comunicaciones. Para obtener acceso y administrar las características de cumplimiento de comunicaciones después de la configuración inicial, los usuarios deben ser miembros de al menos un grupo de roles de cumplimiento de comunicaciones.

Dependiendo de cómo desee administrar las directivas de comunicación y las alertas, deberá asignar usuarios a grupos de roles específicos. Puede elegir asignar usuarios con diferentes responsabilidades de cumplimiento a grupos de roles específicos para administrar diferentes áreas de características de cumplimiento de comunicación. O puede decidir asignar todas las cuentas de usuario para administradores, analistas, investigadores y visores designados al grupo de roles *Cumplimiento* de comunicaciones. Use un único grupo de roles o varios grupos de roles para ajustarse mejor a sus requisitos de administración de cumplimiento.

Elija entre estas opciones de grupo de roles al configurar el cumplimiento de la comunicación:

|**Grupo de funciones**|**Permisos de grupo de roles**|
|:-----|:-----|
| **Cumplimiento de comunicaciones** | Use este grupo de roles para administrar el cumplimiento de comunicaciones de su organización en un solo grupo. Al agregar todas las cuentas de usuario para administradores designados, analistas, investigadores y visores, puede configurar los permisos de cumplimiento de comunicaciones en un solo grupo. Este grupo de funciones contiene todos los roles de permisos de cumplimiento de comunicación. Esta configuración es la forma más sencilla de empezar rápidamente con el cumplimiento de las comunicaciones y es una buena opción para las organizaciones que no necesitan permisos independientes definidos para grupos independientes de usuarios. |
| **Administrador de cumplimiento de comunicaciones** | Use este grupo de roles para configurar inicialmente el cumplimiento de las comunicaciones y posteriormente para segregar a los administradores de cumplimiento de comunicaciones en un grupo definido. Los usuarios asignados a este grupo de roles pueden crear, leer, actualizar y eliminar directivas de cumplimiento de comunicación, configuración global y asignaciones de grupos de roles. Los usuarios asignados a este grupo de roles no pueden ver alertas de mensajes. |
| **Analista de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que actuarán como analistas de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver directivas en las que se les asigna como revisores, ver metadatos de mensajes (no contenido del mensaje), escalar a otros revisores o enviar notificaciones a los usuarios. Los analistas no pueden resolver alertas pendientes. |
| **Investigador de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que actuarán como investigadores de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver los metadatos y el contenido de los mensajes, escalar a otros revisores, escalar a un caso Advanced eDiscovery, enviar notificaciones a los usuarios y resolver la alerta. |
| **Visor de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que administrarán informes de comunicación. Los usuarios asignados a este grupo de roles pueden tener acceso a todos los widgets de informes de la página principal de cumplimiento de comunicaciones y pueden ver todos los informes de cumplimiento de comunicaciones. |

### <a name="for-organizations-using-the-original-permissions-and-role-groups"></a>Para organizaciones que usan los permisos y grupos de roles originales

La nueva estructura del grupo de roles reemplaza la estructura inicial del grupo de roles para el cumplimiento de las comunicaciones. Para las organizaciones que ya usan el cumplimiento de comunicaciones, es necesario que se le asigne el rol Administrador de revisión de supervisión para empezar con el cumplimiento de comunicaciones en el centro de Microsoft 365 cumplimiento. Además, tenía que crear un nuevo grupo de roles para revisores con los roles Administrador de revisión de supervisión, Administración de casos, Administrador de cumplimiento y Revisión para investigar y corregir mensajes con coincidencias de directiva. Básicamente, todos los administradores y revisores estaban en un solo grupo de roles y todos tenían los mismos permisos de acceso y administración. Con las actualizaciones más recientes sobre el cumplimiento de la comunicación, debe planear la migración de la estructura del grupo de roles anterior a la nueva estructura del grupo de roles. La compatibilidad con la estructura del grupo de roles anterior se elimina gradualmente.

Para ayudar a planear la migración, tenga en cuenta el siguiente ejemplo. Actualmente tiene tres tipos de usuarios en su organización, administradores de TI, expertos y revisores. Estos tres tipos de usuarios están en la estructura del grupo de roles anterior y son todos miembros de un único grupo de roles con los siguientes roles asignados:

- Administrador de revisión de supervisión
- Administración de casos
- Administrador de cumplimiento
- Revisar

Para actualizar los roles de estos usuarios para la nueva estructura de grupos de roles y separar los permisos de acceso y administración para los usuarios, puede considerar tres nuevos grupos y las asignaciones de nuevos grupos de roles asociadas:

- **Administradores de TI: asignados** al nuevo grupo de roles *De administrador de cumplimiento* de comunicaciones.
- **Triaje:** asignado al grupo de roles *Analista de cumplimiento de* comunicaciones.
- **Revisores:** asignados al nuevo grupo de roles Del investigador *de cumplimiento de* comunicaciones.

## <a name="supervised-users"></a>Usuarios supervisados

Antes de empezar a usar el cumplimiento de comunicaciones, necesita determinar a quién se debe revisar las comunicaciones. En la directiva, las direcciones de correo electrónico de los usuarios identifican a las personas o grupos de personas que se van a supervisar. Algunos ejemplos de estos grupos son Microsoft 365, listas de distribución basadas Exchange, Yammer comunidades y Microsoft Teams canales. Asimismo, puede excluir usuarios o grupos específicos de la revisión con un grupo de exclusión específico o una lista de grupos. Para obtener más información acerca de los tipos de grupos admitidos en las directivas de cumplimiento de comunicaciones, vea [Introducción al cumplimiento de comunicaciones.](communication-compliance-configure.md#step-3-optional-set-up-groups-for-communication-compliance)

>[!IMPORTANT]
>Los usuarios cubiertos por directivas de cumplimiento de comunicaciones deben tener una licencia de Cumplimiento de Microsoft 365 E5, una licencia de E3 de Office 365 Enterprise con el complemento de cumplimiento avanzado o estar incluidos en una suscripción Office 365 Enterprise E5. Si no tiene un plan Enterprise E5 y desea probar el cumplimiento de las comunicaciones, puede registrarse para una prueba de [Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).

## <a name="reviewers"></a>Reviewers

Al crear una directiva de cumplimiento de comunicaciones, debe determinar quién revisa los mensajes de los usuarios supervisados. En la directiva, las direcciones de correo electrónico de los usuarios identifican a individuos o grupos de personas que revisarán las comunicaciones supervisadas. Todos los revisores deben tener buzones hospedados en Exchange Online  y deben estar asignados a los roles análisis de cumplimiento de comunicación o investigación de cumplimiento *de* comunicación. Los revisores (analistas o investigadores) también deben tener asignado el rol *de administración* de casos de cumplimiento de comunicación. Cuando se agregan revisores a una directiva, reciben automáticamente un mensaje de correo electrónico que les notifica la asignación a la directiva y proporciona vínculos a información sobre el proceso de revisión.

## <a name="groups-for-supervised-users-and-reviewers"></a>Grupos para usuarios y revisores supervisados

Para simplificar la configuración, cree grupos para las personas que necesitan revisar sus comunicaciones y grupos para las personas que revisan dichas comunicaciones. Si usa grupos, es posible que necesite varios. Por ejemplo, si quiere examinar las comunicaciones entre dos grupos distintos de personas, o si desea especificar un grupo que no esté supervisado.

Al asignar un grupo de distribución en la directiva, la directiva supervisa todos los correos electrónicos de cada usuario en el grupo de distribución. Al asignar un grupo Microsoft 365 en la directiva, la directiva supervisa todos los correos electrónicos enviados a ese grupo, no los correos electrónicos individuales recibidos por cada miembro del grupo.

La adición de grupos y listas de distribución a las directivas de cumplimiento de comunicaciones forma parte de las condiciones generales y las reglas establecidas, por lo que el número máximo de grupos y listas de distribución que admite una directiva varía en función del número de condiciones que también se agreguen a la directiva. Cada directiva debe admitir aproximadamente 20 grupos o listas de distribución, según el número de condiciones adicionales presentes en la directiva.

## <a name="supported-communication-types"></a>Tipos de comunicación compatibles

Con las directivas de cumplimiento de comunicaciones, puede elegir examinar mensajes en una o varias de las siguientes plataformas de comunicación como un grupo o como orígenes independientes. Las comunicaciones capturadas en estas plataformas se conservan durante siete años para cada directiva de forma predeterminada, incluso si los usuarios abandonan su organización y sus buzones se eliminan.

- **Microsoft Teams:** se pueden examinar las comunicaciones de chat en canales de Microsoft Teams públicos y privados y chats individuales. Cuando los usuarios se asignan a una directiva de cumplimiento de comunicaciones con una cobertura Microsoft Teams seleccionada, las comunicaciones de chat para los usuarios se supervisan automáticamente en todos los Microsoft Teams donde los usuarios son miembros. Microsoft Teams cobertura se incluye automáticamente para las plantillas de directiva predefinidas y se selecciona de forma predeterminada en la plantilla de directiva personalizada. Teams chats que coincidan con las condiciones de la directiva de cumplimiento de comunicaciones pueden tardar hasta 48 horas en procesarse. Use las siguientes configuraciones de administración de grupos para supervisar los chats de usuarios individuales y las comunicaciones de canal en Teams:

    - **Para Teams de chat:** Asignar usuarios individuales o asignar un [grupo de distribución](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) a la directiva de cumplimiento de comunicaciones. Esta configuración es para relaciones de usuario/chat de uno a uno o de uno a varios.
    - **Para Teams de canal:** Asigne cada Microsoft Teams canal o Microsoft 365 grupo que desee examinar que contenga un usuario específico a la directiva de cumplimiento de comunicaciones. Si agrega el mismo usuario a otros canales de Microsoft Teams o grupos de Microsoft 365, asegúrese de agregar estos nuevos canales y grupos a la directiva de cumplimiento de comunicaciones. Si algún miembro del canal es un usuario  supervisado dentro de una directiva y la dirección de entrada está configurada en una directiva, todos los mensajes enviados dentro del canal están sujetos a revisión y posibles coincidencias de directiva (incluso para los usuarios del canal que no están supervisados explícitamente). Por ejemplo, el usuario A es el propietario o miembro de un canal. El usuario B y el usuario C son miembros del mismo canal y usan un idioma que coincide con la directiva de idioma ofensivo que supervisa solo al usuario A. El usuario B y el usuario C crean coincidencias de directiva para las conversaciones dentro del canal aunque no estén supervisadas directamente en la directiva de idioma ofensivo. Teams conversaciones entre el usuario B y el usuario C que están fuera del canal que incluye el usuario A no estarían sujetas a la directiva de idioma ofensivo que incluye el usuario A. Para excluir a los miembros del canal de la supervisión cuando  otros miembros del canal se supervisan explícitamente, desactive la configuración Dirección de comunicación entrante en la directiva de cumplimiento de comunicaciones aplicable.
    - Para Teams de chat con entornos de correo electrónico **híbridos:** el cumplimiento de las comunicaciones puede supervisar los mensajes de chat de los usuarios de organizaciones con una implementación local de Exchange o un proveedor de correo electrónico externo que haya Microsoft Teams. Debe crear un grupo de distribución para que los usuarios con buzones locales o externos supervisen. Al crear una directiva de cumplimiento de comunicaciones, asignará este grupo de distribución como la selección de usuarios y grupos supervisados en el asistente para directivas. 

- **Exchange** correo electrónico: los buzones hospedados en Exchange Online como parte de la suscripción Microsoft 365 o Office 365 son aptos para el examen de mensajes. Exchange mensajes de correo electrónico y datos adjuntos que coincidan con las condiciones de la directiva de cumplimiento de comunicaciones pueden tardar hasta 24 horas en procesarse. Los tipos de datos adjuntos admitidos para el cumplimiento de comunicaciones son los mismos que los [tipos de archivo admitidos en las inspecciones de contenido de reglas de flujo de correo de Exchange](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).

- **Yammer:** los mensajes privados y las conversaciones públicas y los datos adjuntos asociados en Yammer comunidades pueden examinarse. Cuando se agrega un usuario a la directiva de cumplimiento de comunicaciones que incluye Yammer como un canal definido, las comunicaciones en todas las comunidades de Yammer de las que el usuario es miembro se incluyen en el proceso de examen. Yammer chats y datos adjuntos que coincidan con las condiciones de la directiva de cumplimiento de comunicaciones pueden tardar hasta 24 horas en procesarse. Yammer estar en modo nativo para [que](/yammer/configure-your-yammer-network/overview-native-mode) las directivas de cumplimiento de comunicaciones supervisen Yammer comunicaciones y datos adjuntos. En el modo nativo, todos los usuarios de Yammer están en Azure Active Directory (AAD), todos los grupos son Grupos de Office 365 y todos los archivos se almacenan en SharePoint Online.

- **Skype Empresarial Online**: se pueden supervisar las comunicaciones de chat y los datos adjuntos asociados en Skype Empresarial Online. Los chats de Skype Empresarial Online que coincidan con las condiciones de directiva de cumplimiento de comunicaciones pueden tardar hasta 24 horas en procesarse. Las conversaciones de chat supervisadas se orígenes de [conversaciones anteriores guardadas en Skype Empresarial Online](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2).  Use la siguiente configuración de administración de grupos para supervisar las comunicaciones de chat de usuario en Skype Empresarial Online:

    - **Para Skype Empresarial de chat** en línea: asigne usuarios individuales o asigne [un](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) grupo de distribución a la directiva de cumplimiento de comunicaciones. Esta configuración es para relaciones de usuario/chat de uno a uno o de uno a varios.

- **Orígenes** de terceros: puede examinar las comunicaciones en busca de datos importados en buzones de correo de su organización de Microsoft 365 desde orígenes de terceros como [Instant Bloomberg](archive-instant-bloomberg-data.md), [Slack,](archive-slack-data.md) [Zoom](archive-zoommeetings-data.md), SMS y muchos otros. Para obtener una lista completa de conectores compatibles con el cumplimiento de comunicaciones, vea [Archivar datos de terceros](archiving-third-party-data.md).

    Debe configurar un conector de terceros para su Microsoft 365 para poder asignar el conector a una directiva de cumplimiento de comunicaciones. La **sección Orígenes de terceros** del Asistente para directivas de cumplimiento de comunicaciones solo muestra los conectores de terceros configurados actualmente.

## <a name="policy-settings"></a>Configuración de la directiva

### <a name="users"></a>Usuarios

Puede elegir seleccionar Todos los usuarios **o** definir usuarios específicos en una directiva de cumplimiento de comunicaciones. Al seleccionar **Todos los usuarios**, se aplica la directiva a todos los usuarios y a todos los grupos en los que se incluya cualquier usuario como miembro. Al definir usuarios específicos, la directiva se aplica a los usuarios definidos y a todos los grupos en los que los usuarios definidos se incluyan como miembro.

### <a name="direction"></a>Dirección

De forma predeterminada, **se muestra** la condición Dirección es y no se puede quitar. La configuración de dirección de comunicación en una directiva se elige individual o conjuntamente:

- **Entrante:** detecta las  comunicaciones enviadas a usuarios supervisados de remitentes externos e internos, incluidos otros usuarios supervisados en la directiva.
- **Saliente:** detecta las comunicaciones enviadas desde usuarios **supervisados** a destinatarios externos e internos, incluidos otros usuarios supervisados en la directiva.
- **Interno:** detecta las **comunicaciones entre** los usuarios o grupos supervisados en la directiva.

### <a name="sensitive-information-types"></a>Tipos de información confidencial

Tiene la opción de incluir tipos de información confidencial como parte de la directiva de cumplimiento de comunicaciones. Los tipos de información confidencial son tipos de datos predefinidos o personalizados que pueden ayudar a identificar y proteger números de tarjetas de crédito, números de cuenta bancaria, números de pasaporte y mucho más. Como parte de Información sobre la prevención de pérdida de [datos,](dlp-learn-about-dlp.md)la configuración de información confidencial puede usar patrones, proximidad de caracteres, niveles de confianza e incluso tipos de datos personalizados para ayudar a identificar y marcar el contenido que puede ser confidencial. Los tipos de información confidencial predeterminados son:

- Financiera
- Medicina y salud
- Privacidad
- Tipo de información personalizada

Para obtener más información acerca de los detalles de información confidencial y los patrones incluidos en los tipos predeterminados, vea [Definiciones](sensitive-information-type-entity-definitions.md)de entidad de tipo de información confidencial .

### <a name="custom-keyword-dictionaries"></a>Diccionarios de palabras clave personalizadas

Configure diccionarios de palabras clave personalizadas (o léxicos) para proporcionar una administración sencilla de palabras clave específicas de su organización o sector. Los diccionarios de palabras clave admiten hasta 100 KB de términos (después de la compresión) en el diccionario y admiten cualquier idioma. El límite del espacio empresarial también es de 100 KB después de la compresión. Si es necesario, puede aplicar varios diccionarios de palabras clave personalizadas a una sola directiva o tener un único diccionario de palabras clave por directiva. Estos diccionarios se asignan en una directiva de cumplimiento de comunicaciones y se pueden obtener desde un archivo (como una lista .csv o .txt) o desde una lista que puede importar en el Centro de cumplimiento [.](create-a-keyword-dictionary.md) Use diccionarios personalizados cuando necesite admitir términos o idiomas específicos de su organización y directivas.

### <a name="classifiers"></a>Clasificadores

Los clasificadores globales y capacitados integrados analizan los mensajes enviados o recibidos en todos los canales de comunicación de la organización en busca de diferentes tipos de problemas de cumplimiento. Los clasificadores usan una combinación de inteligencia artificial y de palabras clave para identificar lenguaje en los mensajes que es probable que infrinja las directivas contra el acoso. Actualmente, los clasificadores integrados admiten la identificación de palabras clave de mensaje en varios idiomas:

- Chino (simplificado)
- Inglés
- Francés
- Alemán
- Italiano
- Japonés
- Portugués
- Español

Los clasificadores globales y capacitados para el cumplimiento de la comunicación analizan las comunicaciones en busca de términos, imágenes y sentimientos para los siguientes tipos de idioma y contenido:

- **Amenaza:** busca amenazas para cometer violencia o daño físico a una persona o propiedad.
- **Hostigamiento dirigido:** busca conductas ofensivas dirigidas a personas relacionadas con la raza, el color, la religión, el origen nacional.
- **Profanidad:** busca expresiones profanas que ensoñen a la mayoría de las personas.
- **Imágenes para adultos:** busca imágenes sexualmente explícitas en la naturaleza.
- **Imágenes** rácidas: busca imágenes sexualmente sugerentes en la naturaleza, pero que contienen contenido menos explícito que las imágenes que se consideran adultos.
- **Imágenes de gory:** busca imágenes que represente violencia y sangre.

Los *clasificadores* de imágenes Adult, *Racy* y *Gory* analizan archivos en formatos .jpeg, .png, .gif y .bmp. El tamaño de los archivos de imagen debe ser inferior a 4 megabytes (MB) y las dimensiones de las imágenes deben ser mayores de 50 x 50 píxeles y superiores a 50 kilobytes (KB) para que la imagen pueda ser valorada. La identificación de imágenes es compatible Exchange Online mensajes de correo electrónico y Microsoft Teams canales y chats.

Los clasificadores globales y los clasificadores integrados no proporcionan una lista exhaustiva de términos o imágenes en estas áreas. Además, los estándares lingüísticos y culturales cambian continuamente y, a la luz de estas realidades, Microsoft se reserva el derecho de actualizar clasificadores a su discreción. Aunque los clasificadores pueden ayudar a su organización a supervisar estas áreas, los clasificadores no están diseñados para proporcionar el único medio de supervisión o dirección de su organización. Su organización, no Microsoft, sigue siendo responsable de todas las decisiones relacionadas con la supervisión, el examen y el bloqueo del idioma y las imágenes en estas áreas, incluido el cumplimiento de la privacidad local y otras leyes aplicables. Microsoft anima a consultar con abogados antes de la implementación y el uso.

>[!NOTE]
>Las directivas que usan clasificadores inspeccionarán y evaluarán los mensajes con un recuento de palabras de seis o más. Los mensajes que contienen menos de seis palabras no se evalúan en las directivas mediante clasificadores. Para identificar y tomar medidas en mensajes más cortos que contengan contenido inadecuado, se recomienda incluir un diccionario de palabras clave personalizado para supervisar las directivas de cumplimiento de comunicación para este tipo de contenido.

Para obtener información acerca de los clasificadores que se pueden entrenar en Microsoft 365, vea [Getting started with trainable classifiers](classifier-get-started-with.md).

### <a name="optical-character-recognition-ocr"></a>Reconocimiento óptico de caracteres (OCR)

Configure directivas de cumplimiento de comunicación integradas o personalizadas para examinar e identificar texto impreso o escrito a mano de imágenes que puedan ser inapropiadas en su organización. La compatibilidad integrada de [Azure Cognitive Services](/azure/cognitive-services/computer-vision/overview-ocr) y el examen óptico para identificar texto en imágenes ayudan a los analistas e investigadores a detectar y actuar en casos en los que se puede perder una conducta inapropiada en comunicaciones que no son principalmente textuales.

Puede habilitar el reconocimiento óptico de caracteres (OCR) en nuevas directivas de plantillas, directivas personalizadas o actualizar directivas existentes para ampliar la compatibilidad con el procesamiento de imágenes incrustadas y datos adjuntos. Cuando se habilita en una directiva creada a partir de una plantilla de directiva, se admite el examen automático para imágenes incrustadas o adjuntas en el correo electrónico Microsoft Teams mensajes de chat. Para las directivas personalizadas, una o más configuraciones condicionales asociadas con palabras clave, clasificadores integrados o tipos de información confidencial deben configurarse en la directiva para habilitar la selección del examen OCR.

Las imágenes de 50 KB a 4 MB en los siguientes formatos de imagen se examinan y procesan:

- .jpg/.jpeg (grupo de expertos fotográficos conjuntos)
- .png (gráficos de red portátiles)
- .bmp (mapa de bits)
- .tiff (formato de archivo de imagen de etiqueta)
- .pdf (formato de documento portátil)

>[!NOTE]
>Actualmente, el examen y la extracción de imágenes .pdf incrustadas y adjuntas solo se admiten para los mensajes de correo electrónico.

Al revisar alertas pendientes para directivas con OCR habilitado, las imágenes identificadas y coincidentes con las condiciones de directiva se muestran como elementos secundarios para las alertas asociadas. Puede ver la imagen original para evaluar el texto identificado en contexto con el mensaje original. Las imágenes detectadas pueden tardar hasta 48 horas en estar disponibles con alertas.

### <a name="conditional-settings"></a>Configuración condicional
<a name="ConditionalSettings"> </a>

Las condiciones que elija para la directiva se aplican a las comunicaciones tanto de correo electrónico como de orígenes de terceros de su organización (como de Instant Bloomberg).

En la tabla siguiente se explica más sobre cada condición.
  
|**Condition**|**Cómo usar esta condición**|
|:-----|:-----|
| **El contenido coincide con cualquiera de estos clasificadores** | Aplicar a la directiva cuando se incluyan o excluyan los clasificadores en un mensaje. Algunos clasificadores están predefinidos en el espacio empresarial y los clasificadores personalizados deben configurarse por separado antes de que estén disponibles para esta condición. Solo se puede definir un clasificador como una condición en una directiva. Para obtener más información acerca de la configuración de clasificadores, vea [Learn about trainable classifiers (preview).](classifier-learn-about.md) |
| **El contenido contiene cualquiera de estos tipos de información confidencial** | Se aplica a la directiva cuando se incluya o excluya cualquier tipo de información confidencial en un mensaje. Algunos clasificadores están predefinidos en el espacio empresarial y los clasificadores personalizados se pueden configurar por separado o como parte del proceso de asignación de condiciones. Cada tipo de información confidencial que elija se aplica por separado y solo uno de estos tipos de información confidencial debe aplicar para que la directiva se aplique al mensaje. Para obtener más información acerca de los tipos de información confidencial personalizados, vea [Learn about sensitive information types](sensitive-information-type-learn-about.md). |
| **El mensaje se recibe desde cualquiera de estos dominios**  <br><br> **El mensaje no se recibe de ninguno de estos dominios** | Aplique la directiva para incluir o excluir dominios o direcciones de correo electrónico específicos en los mensajes recibidos. Escriba cada dominio o dirección de correo electrónico y separe varios dominios o direcciones de correo electrónico con una coma. Cada dominio o dirección de correo electrónico especificado se aplica por separado, solo debe aplicarse un dominio o dirección de correo electrónico para que la directiva se aplique al mensaje. <br><br> Si desea examinar todo el correo electrónico de un dominio específico, pero desea excluir los mensajes que no necesitan  revisión (boletines, anuncios, entre otros), debe configurar que un mensaje no se reciba desde ninguna condición de estos dominios que excluya la dirección de correo electrónico (ejemplo "newsletter@contoso.com"). |
| **El mensaje se envía a cualquiera de estos dominios**  <br><br> **El mensaje no se envía a ninguno de estos dominios** | Aplique la directiva para incluir o excluir dominios o direcciones de correo electrónico específicos en los mensajes enviados. Escriba cada dominio o dirección de correo electrónico y separe varios dominios o direcciones de correo electrónico con una coma. Cada dominio o dirección de correo electrónico se aplica por separado, solo debe aplicarse un dominio o dirección de correo electrónico para que la directiva se aplique al mensaje. <br><br> Si desea examinar todo el correo electrónico enviado a un dominio específico, pero desea excluir los mensajes enviados que no necesitan revisión, debe configurar dos condiciones: <br> - Se **envía un mensaje a cualquiera de estos dominios** condición que define el dominio ("contoso.com"), AND <br> - Un **mensaje no se envía a ninguna condición de estos** dominios que excluya la dirección de correo electrónico ("subscriptions@contoso.com"). |
| **El mensaje se clasifica con cualquiera de estas etiquetas**  <br><br> **El mensaje no se clasifica con ninguna de estas etiquetas** | Para aplicar la directiva cuando se incluyen o excluyen determinadas etiquetas de retención en un mensaje. Las etiquetas de retención deben configurarse por separado y las etiquetas configuradas se eligen como parte de esta condición. Cada etiqueta que elija se aplica por separado (solo una de estas etiquetas debe aplicar para que la directiva se aplique al mensaje). Para obtener más información acerca de las etiquetas de retención, vea [Learn about retention policies and retention labels](retention.md).|
| **El mensaje contiene cualquiera de estas palabras**  <br><br> **El mensaje no contiene ninguna de estas palabras** | Para aplicar la directiva cuando se incluyan o excluyan determinadas palabras o frases en un mensaje, escriba cada palabra separada con una coma. Para frases de dos o más palabras, use comillas alrededor de la frase. Cada palabra o frase que escriba se aplica por separado (solo debe aplicarse una palabra para que la directiva se aplique al mensaje). Para obtener más información sobre cómo escribir palabras o frases, consulte la sección siguiente [Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords).|
| **Los datos adjuntos contienen cualquiera de estas palabras**  <br><br> **Los datos adjuntos no contienen ninguna de estas palabras** | Para aplicar la directiva cuando se incluyan o excluyan determinadas palabras o frases en los datos adjuntos de un mensaje (como un documento de Word), escriba cada palabra separada con una coma. Para frases de dos o más palabras, use comillas alrededor de la frase. Cada palabra o frase que escriba se aplica por separado (solo debe aplicarse una palabra para que la directiva se aplique a los datos adjuntos). Para obtener más información sobre cómo escribir palabras o frases, consulte la sección siguiente [Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords).|
| **Los datos adjuntos son cualquiera de estos tipos de archivo**  <br><br> **Los datos adjuntos no son ninguno de estos tipos de archivo** | Para supervisar las comunicaciones que incluyen o excluyen tipos específicos de datos adjuntos, escriba las extensiones de archivo (como .exe o .pdf). Si desea incluir o excluir varias extensiones de archivo, escriba estas en líneas independientes. Solo debe coincidir una extensión de datos adjuntos para que se aplique la directiva.|
| **El tamaño del mensaje es mayor que**  <br><br> **El tamaño del mensaje no es mayor que** | Para revisar los mensajes en función de un tamaño determinado, use estas condiciones para especificar el tamaño máximo o mínimo que puede tener un mensaje antes de que esté sujeto a revisión. Por ejemplo, si especifica que **el** tamaño del mensaje es mayor que \> **1,0 MB,** todos los mensajes de 1,01 MB o más están sujetos a revisión. Puede elegir bytes, kilobytes, megabytes o gigabytes para esta condición.|
| **Los datos adjuntos son mayores que**  <br><br> **Los datos adjuntos no son mayores que** | Para revisar los mensajes en función del tamaño de sus datos adjuntos, especifique el tamaño máximo o mínimo que puede tener un archivo adjunto antes de que el mensaje y sus datos adjuntos estén sujetos a revisión. Por ejemplo, si  especifica Que datos adjuntos supere \> **los 2,0 MB,** todos los mensajes con datos adjuntos de 2,01 MB o más estarán sujetos a revisión. Puede elegir bytes, kilobytes, megabytes o gigabytes para esta condición.|
   
#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Coincidencia de palabras y frases para mensajes de correo electrónico o datos adjuntos
<a name="Matchwords"> </a>

Cada palabra que escriba y separe con una coma se aplica por separado (solo debe aplicarse una palabra para que la condición de directiva se aplique al correo electrónico o los datos adjuntos). Por ejemplo, vamos a usar la condición, **Message** contiene cualquiera de estas palabras , con las palabras clave "banker", "confidential" y "insider trading" separadas por una coma (banker, confidential,"insider trading"). La directiva se aplica a cualquier mensaje que incluya la palabra "banker", "confidential" o la frase "insider trading". Solo una de estas palabras o frases debe aparecer para que esta condición de directiva se aplique. Las palabras del mensaje o los datos adjuntos deben coincidir exactamente con lo que escriba.

>[!IMPORTANT]
>Al importar un archivo de diccionario personalizado, cada palabra o frase debe separarse con un retorno de carro y en una línea independiente. <br> Por ejemplo: <br><br>
>*banker* <br>
>*confidencial* <br>
>*insider trading*

Para examinar los mensajes de correo electrónico y los datos adjuntos [](create-a-keyword-dictionary.md) de las mismas palabras clave, cree una directiva de prevención de pérdida de datos con un diccionario de palabras clave personalizado para los [términos](create-test-tune-dlp-policy.md) que desea examinar en los mensajes. Esta configuración de directiva identifica palabras clave definidas que aparecen en el mensaje de correo **electrónico O en** los datos adjuntos del correo electrónico. El uso de la configuración de directiva condicional estándar (*Message* contiene cualquiera de estas palabras y Attachment  *contiene* cualquiera de estas palabras ) para identificar los términos de los mensajes y los datos adjuntos requiere que los términos se presenten tanto en el mensaje como en los datos adjuntos.
  
#### <a name="enter-multiple-conditions"></a>Especificar varias condiciones

Si especifica varias condiciones, Microsoft 365 todas las condiciones juntas para determinar cuándo aplicar la directiva de cumplimiento de comunicación a los elementos de comunicación. Al configurar varias condiciones, se deben cumplir todas las condiciones para que se aplique la directiva, a menos que especifique una excepción. Por ejemplo, necesita una directiva que se aplique si un mensaje contiene la palabra "trade" y es mayor que 2 MB. Sin embargo, si el mensaje también contiene las palabras "Aprobado por Contoso financial", la directiva no debe aplicarse. En este ejemplo, las tres condiciones se definirían de la siguiente manera:
  
- **El mensaje contiene cualquiera de estas palabras**, con la palabra clave "trade"
- **El tamaño del mensaje es mayor que**, con el valor 2 MB
- **El mensaje no contiene ninguna de estas palabras**, con las palabras clave "Aprobado por el equipo financiero de Contoso"

### <a name="review-percentage"></a>Porcentaje de revisión

Si desea reducir la cantidad de contenido que se va a revisar, puede especificar un porcentaje de todas las comunicaciones regida por una directiva de cumplimiento de comunicaciones. Se selecciona una muestra de contenido aleatoria en tiempo real del porcentaje total de contenido que coincida con las condiciones de directiva elegidas. Si quiere que los revisores revisen todos los elementos, puede configurar el **100 %** en una directiva de cumplimiento de comunicaciones.

## <a name="privacy"></a>Privacidad

Proteger la privacidad de los usuarios que tienen coincidencias de directiva es importante y puede ayudar a promover la objetividad en las revisiones de investigación y análisis de datos para alertas de cumplimiento de comunicaciones. Esta configuración solo se aplica a los nombres de usuario que muestran la solución de cumplimiento de comunicaciones. No afecta a cómo se muestran los nombres en otras soluciones de cumplimiento o en el Centro de administración.

Para los usuarios con una coincidencia de cumplimiento de comunicación, puede elegir una de las siguientes opciones en **Configuración de cumplimiento de comunicaciones:**

- **Mostrar versiones anonimizadas** de nombres de usuario:  los nombres de usuario se anonimizan para impedir que los usuarios del grupo de roles de analista de cumplimiento de comunicaciones vean quién está asociado con las alertas de directiva. Los usuarios del grupo *de roles Investigador de cumplimiento* de comunicaciones siempre verán nombres de usuario, no las versiones anonimizadas. Por ejemplo, un usuario "Grace Taylor" aparecería con un seudónimo aleatorio como "AnonIS8-988" en todas las áreas de la experiencia de cumplimiento de comunicación. Al elegir esta configuración, se anonimizan todos los usuarios con coincidencias de directivas actuales y pasadas, y se aplica a todas las directivas. La información del perfil de usuario en los detalles de la alerta de cumplimiento de comunicaciones no estará disponible cuando se elija esta opción. Sin embargo, los nombres de usuario se muestran al agregar nuevos usuarios a directivas existentes o al asignar usuarios a nuevas directivas. Si decide desactivar esta configuración, se mostrarán los nombres de usuario para todos los usuarios que tengan coincidencias de directiva actuales o pasadas.
- **No mostrar versiones anónimas de** nombres de usuario: los nombres de usuario se muestran para todas las coincidencias de directiva actuales y pasadas para las alertas de cumplimiento de comunicaciones. La información de perfil de usuario (nombre, título, alias y organización o departamento) se muestra para el usuario para todas las alertas de cumplimiento de comunicaciones.

## <a name="notice-templates"></a>Plantillas de aviso

Puede crear plantillas de aviso si desea enviar a los usuarios un aviso de aviso por correo electrónico para las coincidencias de directivas como parte del proceso de resolución de problemas. Los avisos solo se pueden enviar a la dirección de correo electrónico del usuario asociada con la coincidencia de directiva que generó la alerta específica para la corrección. Al seleccionar una plantilla de aviso para aplicar a una infracción de directiva como parte del flujo de trabajo de corrección, puede elegir aceptar los valores de campo definidos en la plantilla o sobrescribir los campos según sea necesario.

Las plantillas de avisos son plantillas de correo electrónico personalizadas donde puede definir los siguientes campos de mensaje en el área **Configuración de cumplimiento de** comunicación:

|**Field**|**Required**| **Detalles** |
|:-----|:-----|:-----|
|**Nombre de la plantilla** | Sí | Nombre descriptivo de la plantilla de aviso que seleccionará en el flujo de trabajo de notificación durante la corrección, admite caracteres de texto. |
| **Dirección del remitente** | Sí | La dirección de uno o varios usuarios o grupos que envían el mensaje al usuario con una coincidencia de directiva, seleccionada en Active Directory para la suscripción. |
| **Direcciones CC y CCO** | No | Usuarios o grupos opcionales que se notificarán de la coincidencia de directiva, seleccionados desde Active Directory para su suscripción. |
| **Asunto** | Sí | La información que aparece en la línea de asunto del mensaje admite caracteres de texto. |
| **Cuerpo del mensaje** | Sí | La información que aparece en el cuerpo del mensaje admite valores de texto o HTML. |

### <a name="html-for-notices"></a>HTML para avisos

Si desea crear más que un mensaje de correo electrónico simple basado en texto para notificaciones, puede crear un mensaje más detallado mediante HTML en el campo cuerpo del mensaje de una plantilla de aviso. En el siguiente ejemplo se proporciona el formato del cuerpo del mensaje para una plantilla básica de notificación de correo electrónico basada en HTML:

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
>La implementación del atributo href HTML en las plantillas de notificación de cumplimiento de comunicaciones actualmente solo admite comillas simples en lugar de comillas dobles para las referencias url.

## <a name="filters"></a>Filtros

Los filtros de cumplimiento de comunicaciones permiten filtrar y ordenar mensajes de alerta para acciones de investigación y corrección más rápidas. El filtrado está disponible  en **las pestañas Pendiente** y Resuelto para cada directiva. Para guardar un filtro o un conjunto de filtros como una consulta de filtro guardada, uno o varios valores deben configurarse como selecciones de filtro. En la tabla siguiente se describen los detalles del filtro:

|**Filter**|**Detalles**|
|:-----|:-----|
| **Fecha** | La fecha en que un usuario de la organización envió o recibió el mensaje. Para filtrar por un solo día, seleccione un intervalo de fechas que comience con el día para el que desea obtener los resultados y termine con el día siguiente. Por ejemplo, si desea filtrar los resultados del 20/9/2020, elegiría un intervalo de fechas de filtro del 20/09/2020-9/21/2020.|
| **Clase File** | Clase del mensaje basada en el tipo de mensaje, ya sea *mensaje o* *datos adjuntos.* |
| **Tiene datos adjuntos** | La presencia de datos adjuntos en el mensaje. |
| **Clase Item** | El origen del mensaje según el tipo de mensaje, el correo electrónico, el chat de Microsoft Team, Bloomberg, etc. Para obtener más información sobre tipos de elementos y clases de mensaje comunes, vea [Tipos de elementos y clases de mensaje](/office/vba/outlook/concepts/forms/item-types-and-message-classes). |
| **Dominios de destinatarios** | Dominio al que se envió el mensaje. Normalmente, este dominio es su Microsoft 365 de suscripción de forma predeterminada. |
| **Destinatario** | El usuario al que se envió el mensaje. |
| **Sender** | La persona que envió el mensaje. |
| **Dominio del remitente** | Dominio que envió el mensaje. |
| **Tamaño** | Tamaño del mensaje en KB. |
| **Asunto/Título** | Asunto del mensaje o título del chat. |
| **Tags** | Las etiquetas asignadas a un mensaje, *ya sea Questionable*, *Compliant* o *Non-compliant*. |
| **Language** | El idioma de texto detectado en el mensaje. El mensaje se clasifica según el idioma de la mayoría del texto del mensaje. Por ejemplo, para un mensaje que contiene texto alemán e italiano, pero la mayoría de texto es alemán, el mensaje se clasifica como alemán (DE). Se admiten los siguientes idiomas: chino (simplificado - ZH), inglés (EN), francés (FR), alemán (DE), italiano (IT), japonés (JP), portugués (PT) y español (ES). Por ejemplo, para filtrar mensajes clasificados como alemán e italiano, escriba "DE,IT" (los códigos de idioma de 2 dígitos) en el cuadro de búsqueda Filtro de idioma. Para ver la clasificación de idioma detectado para un mensaje, seleccione un mensaje, seleccione Ver detalles del mensaje y desplácese al campo EmailDetectedLanguage. |
| **Escalado a** | Nombre de usuario de la persona incluida como parte de una acción de escalamiento de mensajes. |
| **Clasificadores** | Nombre de clasificadores integrados y personalizados que se aplican al mensaje. Algunos ejemplos son *Offensive Language*, *Targeted Harassment*, *Profanity*, *Threat* y mucho más.

## <a name="alert-policies"></a>Directivas de alerta

Después de configurar una directiva, se crea automáticamente una directiva de alerta correspondiente y se generan alertas para los mensajes que coinciden con las condiciones definidas en la directiva. De forma predeterminada, todos los desencadenadores de alerta de coincidencias de directiva tienen asignado un nivel de gravedad de medio en la directiva de alerta asociada. Las alertas se generan para una directiva de cumplimiento de comunicaciones una vez que se cumple el nivel de umbral de desencadenador de agregación en la directiva de alerta asociada.

Para las directivas de cumplimiento de comunicaciones, los siguientes valores de directiva de alerta están configurados de forma predeterminada:

|**Desencadenador de directiva de alerta**|**Valor predeterminado**|
|:-----|:-----|
| Agregación | Agregación sencilla |
| Umbral | 4 actividades |
| Window | 60 minutos |

>[!Note]
>La configuración del desencadenador de umbral de directiva de alerta para actividades admite un valor mínimo de 3 o superior para las directivas de cumplimiento de comunicaciones.

Puede cambiar la configuración predeterminada para desencadenadores en número de actividades, período para  las actividades y para usuarios específicos en directivas de alerta en la página Directivas de alerta del Centro de seguridad & cumplimiento.

### <a name="change-the-severity-level-for-an-alert-policy"></a>Cambiar el nivel de gravedad de una directiva de alerta

Si desea cambiar el nivel de gravedad asignado en una directiva de alerta para una directiva de cumplimiento de comunicación específica, siga estos pasos:

1. Inicie sesión [https://compliance.microsoft.com](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador en su Microsoft 365 organización.

2. En el centro Microsoft 365 cumplimiento, vaya a **Directivas**.

3. Seleccione **Office 365 alerta en** la **página** Directivas para abrir la página Directivas **de** alertas en el Centro de Office 365 seguridad **& cumplimiento**.

4. Active la casilla de verificación de la directiva de cumplimiento de comunicaciones que desea actualizar y, a continuación, **seleccione Editar directiva**.

5. En la **pestaña Descripción,** seleccione el desplegable **Gravedad** para configurar el nivel de alerta de directiva.

6. Seleccione **Guardar** para aplicar el nuevo nivel de gravedad a la directiva.

7. Seleccione **Cerrar para** salir de la página de detalles de la directiva de alertas.

## <a name="power-automate-flows"></a>Power Automate flujos

[Microsoft Power Automate](/power-automate/getting-started) es un servicio de flujo de trabajo que automatiza las acciones entre aplicaciones y servicios. Mediante el uso de flujos de plantillas o creados manualmente, puede automatizar tareas comunes asociadas con estas aplicaciones y servicios. Al habilitar los flujos Power Automate para el cumplimiento de las comunicaciones, puede automatizar tareas importantes para alertas y usuarios. Puede configurar los flujos Power Automate para notificar a los administradores cuando los usuarios tienen alertas de cumplimiento de comunicaciones y otras aplicaciones.

Los clientes con Microsoft 365 que incluyen el cumplimiento de la comunicación no necesitan licencias Power Automate para usar la plantilla de cumplimiento de comunicaciones Power Automate recomendada. La plantilla predeterminada se puede personalizar para admitir la organización y cubrir los escenarios principales de cumplimiento de comunicaciones. Si elige usar características de Power Automate premium en estas plantillas, cree una plantilla personalizada con el conector de cumplimiento de Microsoft 365 o use plantillas Power Automate para otras áreas de cumplimiento en Microsoft 365, puede que necesite licencias Power Automate adicionales.

>[!IMPORTANT]
>¿Recibe avisos para la validación de licencias adicionales al probar Power Automate flujos? Es posible que su organización aún no haya recibido actualizaciones de servicio para esta característica de vista previa. Las actualizaciones se implementan y todas las organizaciones con suscripciones Microsoft 365 que incluyan el cumplimiento de comunicaciones deben tener compatibilidad con licencias para los flujos creados a partir de las plantillas Power Automate recomendadas antes del 30 de octubre de 2020.

![Cumplimiento de Power Automate](../media/communication-compliance-power-automate.png)

La siguiente Power Automate se proporciona a los clientes para admitir la automatización de procesos para alertas de cumplimiento de comunicaciones:

- **Notificar al administrador cuando un usuario tiene una alerta** de cumplimiento de comunicación: es posible que algunas organizaciones necesiten recibir una notificación de administración inmediata cuando un usuario tiene una alerta de cumplimiento de comunicación. Cuando se configura y selecciona este flujo, se envía un mensaje de correo electrónico al administrador del usuario del caso con la siguiente información sobre todas las alertas:
    - Directiva aplicable para la alerta
    - Fecha y hora de la alerta
    - Nivel de gravedad de la alerta

### <a name="create-a-power-automate-flow"></a>Crear un flujo Power Automate de datos

Para crear un flujo Power Automate de una plantilla predeterminada recomendada, usará la opción Administrar flujos **de Power Automate** desde el control **Automatizar** al trabajar directamente en una alerta. Para crear un flujo de Power Automate con **Administrar Power Automate,** debe ser miembro de al menos un grupo de roles de cumplimiento de comunicaciones.

Siga estos pasos para crear un flujo Power Automate de una plantilla predeterminada:

1. En el centro Microsoft 365 cumplimiento, vaya a Directivas de **cumplimiento** de comunicación y seleccione la directiva con la alerta que  >   desea revisar.
2. En la directiva, seleccione la **pestaña** Pendiente y seleccione una alerta pendiente.
3. Seleccione **Power Automate** en el menú de acción de alerta.
4. En la **Power Automate,** seleccione una plantilla predeterminada de la sección Plantillas de cumplimiento de comunicación que le pueden **gustar** en la página.
5. El flujo enumerará las conexiones incrustadas necesarias para el flujo y se mostrará si los estados de conexión están disponibles. Si es necesario, actualice las conexiones que no se muestran como disponibles. Seleccione **Continuar**.
6. De forma predeterminada, los flujos recomendados están preconfigurados con el cumplimiento de comunicaciones recomendado y los campos de datos de servicio Microsoft 365 necesarios para completar la tarea asignada para el flujo. Si es necesario, personalice los componentes de flujo mediante el control **Mostrar** opciones avanzadas y configurando las propiedades disponibles para el componente de flujo.
7. Si es necesario, agregue cualquier paso adicional al flujo seleccionando el **botón Nuevo** paso. En la mayoría de los casos, este cambio no debe ser necesario para las plantillas predeterminadas recomendadas.
8. Seleccione **Guardar borrador** para guardar el flujo para una configuración posterior o seleccione **Guardar** para completar la configuración del flujo.
9. Seleccione **Cerrar** para volver a la página Power Automate flujo. La nueva plantilla aparecerá como un  flujo en la pestaña Mis flujos y estará disponible automáticamente desde el control Power Automate para el usuario que creó el flujo al trabajar con alertas de cumplimiento de comunicaciones.

### <a name="share-a-power-automate-flow"></a>Compartir un flujo Power Automate de datos

De forma predeterminada, Power Automate flujos creados por un usuario solo están disponibles para ese usuario. Para que otros usuarios de cumplimiento de comunicaciones tengan acceso y usen un flujo, el creador del flujo debe compartir el flujo. Para compartir un flujo, usará el control Power Automate **cuando** trabaje directamente en una alerta.

Para compartir un flujo Power Automate, debe ser miembro de al menos un grupo de roles de cumplimiento de comunicaciones.
Siga estos pasos para compartir un flujo Power Automate datos:

1. En el centro Microsoft 365 cumplimiento, vaya a Directivas de **cumplimiento** de comunicación y seleccione la directiva con la alerta que  >   desea revisar.
2. En la directiva, seleccione la **pestaña** Pendiente y seleccione una alerta pendiente.
3. Seleccione **Power Automate** en el menú de acción de alerta.
4. En la **página Power Automate flujos,** seleccione la **pestaña Mis flujos** o Flujos **de** equipo.
5. Seleccione el flujo que desea compartir y, a continuación, **seleccione Compartir** en el menú opciones de flujo.
6. En la página de uso compartido de flujo, escriba el nombre del usuario o grupo que desea agregar como propietario del flujo.
7. En el cuadro de diálogo Conexión **usada,** seleccione **Aceptar** para confirmar que el usuario o grupo agregado tendrá acceso total al flujo.

### <a name="edit-a-power-automate-flow"></a>Editar un flujo Power Automate datos

Si necesita editar un flujo, usará el **control** Power Automate cuando trabaje directamente en una alerta. Para editar un flujo Power Automate, debe ser miembro de al menos un grupo de roles de cumplimiento de comunicaciones.

Siga estos pasos para editar un flujo Power Automate datos:

1. En el centro Microsoft 365 cumplimiento, vaya a Directivas de **cumplimiento** de comunicación y seleccione la directiva con la alerta que  >   desea revisar.
2. En la directiva, seleccione la **pestaña** Pendiente y seleccione una alerta pendiente.
3. Seleccione **Power Automate** en el menú de acción de alerta.
4. En la **página Power Automate flujos,** seleccione flujo para editar. Seleccione **Editar** en el menú control de flujo.
5. Seleccione los **puntos suspensivos** Configuración cambiar una configuración de componente de flujo o puntos suspensivos  >     >  **Eliminar** para eliminar un componente de flujo.
6. Seleccione **Guardar** y, a continuación, **Cerrar** para completar la edición del flujo.

### <a name="delete-a-power-automate-flow"></a>Eliminar un flujo Power Automate datos

Si necesita eliminar un flujo, usará el **control** Power Automate cuando trabaje directamente en una alerta. Para eliminar un flujo Power Automate, debe ser miembro de al menos un grupo de roles de cumplimiento de comunicaciones.

Siga estos pasos para eliminar un flujo Power Automate datos:

1. En el centro Microsoft 365 cumplimiento, vaya a Directivas de **cumplimiento** de comunicación y seleccione la directiva con la alerta que  >   desea revisar.
2. En la directiva, seleccione la **pestaña** Pendiente y seleccione una alerta pendiente.
3. Seleccione **Power Automate** en el menú de acción de alerta.
4. En la **página Power Automate flujos,** seleccione flujo que desea eliminar. Seleccione **Eliminar** en el menú control de flujo.
5. En el cuadro de diálogo de confirmación de eliminación, seleccione **Eliminar** para quitar el flujo o **seleccione Cancelar** para salir de la acción de eliminación.

## <a name="reports"></a>Informes

El nuevo **panel de** informes es la ubicación central para ver todos los informes de cumplimiento de comunicaciones. Los widgets de informe proporcionan una vista rápida de los conocimientos más necesarios para una evaluación general del estado de las actividades de cumplimiento de comunicaciones. La información contenida en los widgets del informe no es exportable. Los informes detallados proporcionan información detallada relacionada con áreas específicas de cumplimiento de comunicaciones y ofrecen la capacidad de filtrar, agrupar, ordenar y exportar información durante la revisión.

![Panel de informes de cumplimiento de comunicaciones](../media/communication-compliance-reports-dashboard.png)

El **panel informes contiene** los siguientes widgets de informe y vínculos de informes detallados:

- **Widget Coincidencias de directivas** recientes: muestra el número de coincidencias por directiva activa con el tiempo.
- **Elementos resueltos por** widget de directiva: muestra el número de alertas de coincidencia de directivas resueltas por directiva con el tiempo.
- **Usuarios con la mayoría del** widget de coincidencia de directiva: muestra los usuarios (o nombres de usuario anonimizados) y el número de coincidencias de directiva durante un período determinado.
- **Directiva con la mayoría de los** widgets de coincidencias: muestra las directivas y el número de coincidencias de un período determinado, clasificados de mayor a menor para las coincidencias.
- **Escalaciones por widget de** directiva: muestra el número de escalaciones por directiva durante un tiempo determinado.
- **Informe** detallado sobre la configuración de la directiva y el estado: proporciona una vista detallada de la configuración y la configuración de la directiva, así como el estado general de cada directiva (coincidencias y acciones) de los mensajes. Incluye información de directiva y cómo se asocian las directivas con usuarios y grupos, ubicaciones, porcentajes de revisión, revisores, estado y cuándo se modificó por última vez la directiva. Use la *opción* Exportar para crear un archivo .csv que contenga los detalles del informe.
- **Elementos y acciones por informe detallado** de directiva: Revisar y exportar elementos y acciones de corrección correspondientes por directiva. Incluye información de directivas y cómo se asocian las directivas con:

    - Elementos coincidentes
    - Elementos escalados
    - Elementos resueltos
    - Etiquetado como compatible
    - Etiquetado como no compatible
    - Etiquetado como cuestionable
    - Revisión pendiente de elementos
    - Notificación de usuario
    - Case created
    
    Use la *opción* Exportar para crear un archivo .csv que contenga los detalles del informe.
- **Informe detallado de elementos** y acciones por ubicación: revisar y exportar elementos y acciones de corrección correspondientes por Microsoft 365 ubicación. Incluye información sobre cómo están asociadas las plataformas de carga de trabajo:

    - Elementos coincidentes
    - Elementos escalados
    - Elementos resueltos
    - Etiquetado como compatible
    - Etiquetado como no compatible
    - Etiquetado como cuestionable
    - Revisión pendiente de elementos
    - Notificación de usuario
    - Case created

    Use la *opción* Exportar para crear un archivo .csv que contenga los detalles del informe.
- **Actividad por informe detallado** del usuario: Revisar y exportar elementos y acciones de corrección correspondientes por usuario. Incluye información sobre cómo se asocian los usuarios a:

    - Elementos coincidentes
    - Elementos escalados
    - Elementos resueltos
    - Etiquetado como compatible
    - Etiquetado como no compatible
    - Etiquetado como cuestionable
    - Revisión pendiente de elementos
    - Notificación de usuario
    - Case created

    Use la *opción* Exportar para crear un archivo .csv que contenga los detalles del informe.

- **Informe detallado de tipo** de información confidencial por ubicación (versión preliminar): revise y exporte información sobre la detección de tipos de información confidencial y los orígenes asociados en las directivas de cumplimiento de comunicaciones. Incluye el total general y el desglose específico de las instancias de tipo de información confidencial en los orígenes configurados en la organización. Algunos ejemplos son:

    - **Correo** electrónico: tipos de información confidencial detectados en Exchange de correo electrónico.
    - **Teams:** tipos de información confidencial detectados en Microsoft Teams canales y mensajes de chat.
    - **Skype Empresarial:** tipos de información confidencial detectados en Skype para comunicaciones empresariales.
    - **Yammer:** tipos de información confidencial detectados en Yammer bandejas de entrada, publicaciones, chats y respuestas.
    - **Orígenes de terceros:** tipos de información confidencial detectados para actividades asociadas con conectores de terceros configurados en la organización. Para ver el desglose de orígenes de terceros para un tipo de información confidencial específico en el informe, mantenga el mouse sobre el valor del tipo de información confidencial en la columna Origen de terceros.
    - **Otros:** tipos de información confidencial usados para el procesamiento interno del sistema. Seleccionar o anular la selección de este origen para el informe no afectará a ningún valor.

    Use la *opción* Exportar para crear un archivo .csv que contenga los detalles del informe. Los valores de cada origen de terceros se muestran en columnas independientes en el .csv archivo.

## <a name="audit"></a>Auditoría

En algunos casos, debe proporcionar información a auditores normativos o de cumplimiento para demostrar la supervisión de las actividades y comunicaciones de los usuarios. Esta información puede ser un resumen de todas las actividades asociadas con una directiva organizativa definida o en cualquier momento en que cambie una directiva de cumplimiento de comunicación. Las directivas de cumplimiento de comunicaciones tienen seguimientos de auditoría integrados para una preparación completa para auditorías internas o externas. Las directivas de comunicación capturan historiales de auditoría detallados de cada acción de creación, edición y eliminación para proporcionar una prueba de los procedimientos de supervisión.

>[!Important]
>La auditoría debe estar habilitada para su organización antes de que se grabe el cumplimiento de la comunicación. Para habilitar la auditoría, vea [Habilitar el registro de auditoría](communication-compliance-configure.md#step-2-required-enable-the-audit-log). Cuando las actividades desencadenan eventos que se capturan en el registro de auditoría de Microsoft 365, pueden tardar hasta 48 horas antes de que estos eventos se puedan ver en las directivas de cumplimiento de comunicaciones.

Para ver las actividades de actualización de directivas de cumplimiento de comunicaciones, seleccione el control Exportar actualizaciones **de directivas** en la página principal de cualquier directiva. Debe tener asignados los roles *Administrador global* o Administrador de cumplimiento *de* comunicaciones para exportar actividades de actualización. Esta acción genera un archivo de auditoría en el .csv que contiene la siguiente información:

|**Field**|**Detalles**|
|:-----|:-----|
| **CreationDate** | La fecha en que se realizó la actividad de actualización en una directiva. |
| **UserIds** | El usuario que realizó la actividad de actualización en una directiva. |
| **Operaciones** | Las operaciones de actualización realizadas en la directiva. |
| **AuditData** | Este campo es el origen de datos principal de todas las actividades de actualización de directivas. Todas las actividades de actualización se registran y se separan por delimitadores por comas. |

Para ver las actividades de revisión de cumplimiento de comunicación de una directiva, seleccione el control **Exportar** actividades de revisión en **la** página Información general de una directiva específica. Debe tener asignados los roles Administrador *global* o Administrador de cumplimiento *de* comunicaciones para exportar actividades de revisión. Esta acción genera un archivo de auditoría en el .csv que contiene la siguiente información:

|**Field**|**Detalles**|
|:-----|:-----|
| **CreationDate** | La fecha en que se realizó la actividad de revisión en una directiva. |
| **UserIds** | El usuario que realizó la actividad de revisión en una directiva. |
| **Operaciones** | Las operaciones de revisión realizadas en la directiva. |
| **AuditData** | Este campo es el origen de datos principal de todas las actividades de revisión de directivas. Todas las actividades de revisión se registran y se separan por delimitadores por comas. |

También puede ver las actividades de auditoría en el registro de auditoría unificado o con el cmdlet [de PowerShell Search-UnifiedAuditLog.](/powershell/module/exchange/search-unifiedauditlog) Para obtener más información sobre las directivas de retención de registros de auditoría, vea [Manage audit log retention policies](audit-log-retention-policies.md).

Por ejemplo, el siguiente ejemplo devuelve las actividades de todas las actividades de revisión de supervisión (directivas y reglas):

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType AeD -Operations SupervisoryReviewTag
```

En este ejemplo se devuelven las actividades de actualización de las directivas de cumplimiento de comunicación:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType Discovery -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeleted
```

En este ejemplo se devuelven actividades que coinciden con las directivas de cumplimiento de comunicaciones actuales:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -Operations SupervisionRuleMatch 
```

Las coincidencias de directivas de cumplimiento de comunicaciones se almacenan en un buzón de supervisión para cada directiva. En algunos casos, es posible que deba comprobar el tamaño del buzón de supervisión de una directiva para asegurarse de que no se acerca al límite actual de 50 GB. Si se alcanza el límite de buzones de correo, las coincidencias de directiva no se capturan y tendrás que crear una nueva directiva (con la misma configuración) para seguir capturando coincidencias para las mismas actividades.

Para comprobar el tamaño de un buzón de supervisión para una directiva, siga estos pasos:

1. Use el cmdlet [Conectar-ExchangeOnline](/powershell/module/exchange/connect-exchangeonline) en el módulo Exchange Online PowerShell V2 para conectarse a Exchange Online PowerShell mediante la autenticación moderna.
2. Ejecute el siguiente comando en PowerShell:

    ```PowerShell
    ForEach ($p in Get-SupervisoryReviewPolicyV2 | Sort-Object Name) 
    {
       "<Name of your communication compliance policy>: " + $p.Name
       Get-MailboxStatistics $p.ReviewMailbox | ft ItemCount,TotalItemSize
    }
    ```

## <a name="transitioning-from-supervision-in-office-365"></a>Transición desde supervisión en Office 365

Las organizaciones que usan directivas de supervisión en Office 365 deben planear inmediatamente la transición a las directivas de cumplimiento de comunicaciones en Microsoft 365 y deben comprender estos puntos importantes:

- La solución de supervisión en Office 365 se ha reemplazado completamente por la solución de cumplimiento de comunicaciones en Microsoft 365. Se recomienda crear nuevas directivas en el cumplimiento de comunicaciones que tengan la misma configuración que las directivas de supervisión existentes para usar las nuevas mejoras de investigación y corrección.
- Los mensajes guardados en supervisión en Office 365 coincidencias de directiva no se pueden mover ni compartir en el cumplimiento de la comunicación en Microsoft 365.
- Para las organizaciones con ambas soluciones usadas en paralelo durante el proceso de transición, las directivas usadas en cada solución deben tener nombres de directiva únicos. Los grupos y los diccionarios de palabras clave personalizados se pueden compartir entre soluciones durante un período de transición.

Para obtener información sobre la retirada para la supervisión en Office 365, consulte [Microsoft 365 Roadmap para](https://www.microsoft.com/microsoft-365/roadmap) obtener más información.

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

Para configurar el cumplimiento de comunicaciones para su Microsoft 365, vea [Configure communication compliance for your Microsoft 365 organization](communication-compliance-configure.md).
