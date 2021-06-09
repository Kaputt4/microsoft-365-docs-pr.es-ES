---
title: Datos adjuntos seguros
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre la característica Caja fuerte datos adjuntos en Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cc5fabf7b0bb4a649aeb7c4e09155037fc09e9f9
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625010"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Caja fuerte Datos adjuntos de Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Caja fuerte Los datos adjuntos de [Microsoft Defender](defender-for-office-365.md) para Office 365 proporcionan una capa adicional de protección para los datos adjuntos de correo electrónico que ya han sido examinados por la protección antimalware en [Exchange Online Protection (EOP).](anti-malware-protection.md) En concreto, Caja fuerte datos adjuntos usa un entorno virtual para comprobar los datos adjuntos de los mensajes de correo electrónico antes de entregarse a los destinatarios (un proceso conocido como _detonación_).

Caja fuerte La protección de datos adjuntos para los mensajes de correo electrónico se controla Caja fuerte de datos adjuntos. No hay ninguna directiva Caja fuerte de datos adjuntos predeterminada, por lo que para obtener la protección de los datos adjuntos de Caja fuerte, debe crear una o más directivas Caja fuerte **datos adjuntos**. Para obtener instrucciones, vea [Configurar Caja fuerte de datos adjuntos en Defender para Office 365](set-up-safe-attachments-policies.md).

En la tabla siguiente se describen escenarios para los datos adjuntos de Caja fuerte en organizaciones de Microsoft 365 y Office 365 que incluyen Microsoft Defender para Office 365 (es decir, la falta de licencias nunca es un problema en los ejemplos).

<br>

****

|Escenario|Resultado|
|---|---|
|La organización de Microsoft 365 E5 pat no tiene configuradas Caja fuerte de datos adjuntos.|Pat no está protegido por Caja fuerte datos adjuntos. <p> Un administrador debe crear al menos una directiva de Caja fuerte datos adjuntos para que Caja fuerte protección de datos adjuntos esté activa. Además, las condiciones de la directiva deben incluir Pat si Pat va a estar protegido por Caja fuerte datos adjuntos.|
|La organización de Lee tiene una directiva Caja fuerte datos adjuntos que solo se aplica a los empleados de finanzas. Lee es miembro del departamento de ventas.|Lee no está protegido por Caja fuerte datos adjuntos. <p> Los empleados de finanzas están protegidos Caja fuerte datos adjuntos, pero los empleados de ventas (y otros empleados) no lo están.|
|Ayer, un administrador de la organización de Juan creó una directiva Caja fuerte datos adjuntos que se aplica a todos los empleados. Anteriormente, Juan recibió un mensaje de correo electrónico que incluía datos adjuntos.|Jean está protegido por Caja fuerte datos adjuntos. <p> Normalmente, una nueva directiva tarda unos 30 minutos en tener efecto.|
|La organización de Chris tiene directivas de datos adjuntos Caja fuerte para todos los usuarios de la organización. Chris recibe un correo electrónico que tiene datos adjuntos y, a continuación, reenvía el mensaje a destinatarios externos.|Chis está protegido por Caja fuerte datos adjuntos. <p> Si los destinatarios externos también tienen Caja fuerte de datos adjuntos en su organización, los mensajes reenviados están sujetos a dichas directivas.|
|

Caja fuerte El examen de datos adjuntos se lleva a cabo en la misma región donde reside Microsoft 365 datos. Para obtener más información acerca de la geografía del centro de datos, [vea ¿Dónde se encuentran los datos?](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> Las siguientes características se encuentran en la configuración global de las directivas Caja fuerte datos adjuntos en el Centro de & cumplimiento. Sin embargo, estas opciones de configuración están habilitadas o deshabilitadas globalmente y no requieren directivas Caja fuerte datos adjuntos:
>
> - [Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md).
> - [Documentos seguros en Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Caja fuerte Configuración de directiva de datos adjuntos

En esta sección se describe la configuración de las Caja fuerte de datos adjuntos:

- **Caja fuerte datos adjuntos respuesta de malware desconocido:** esta configuración controla la acción de la detección de malware Caja fuerte datos adjuntos en los mensajes de correo electrónico. Las opciones disponibles se describen en la tabla siguiente:

  <br>

  ****

  |Opción|Efecto|Úselo cuando desee:|
  |---|---|---|
  |**Desactivado**|Los datos adjuntos no se examinan en busca de malware Caja fuerte datos adjuntos. Los mensajes aún se examinan en busca de malware mediante la [protección antimalware en EOP](anti-malware-protection.md).|Desactiva el examen de los destinatarios seleccionados. <p> Evite retrasos innecesarios en el enrutamiento del correo interno. <p> **Esta opción no se recomienda para la mayoría de los usuarios. Solo debe usar esta opción para desactivar el examen de datos adjuntos Caja fuerte de destinatarios que solo reciben mensajes de remitentes de confianza.**|
  |**Supervisar**|Entrega mensajes con datos adjuntos y, a continuación, realiza un seguimiento de lo que sucede con el malware detectado. <p> La entrega de mensajes seguros puede retrasarse debido a Caja fuerte análisis de datos adjuntos.|Vea dónde va el malware detectado en su organización.|
  |**Bloquear**|Impide que se entreguen los mensajes con datos adjuntos de malware detectados. <p> Los mensajes [se ponen en cuarentena](manage-quarantined-messages-and-files.md) donde solo los administradores (no los usuarios finales) pueden revisar, liberar o eliminar los mensajes. <p> Bloquea automáticamente las instancias futuras de los mensajes y datos adjuntos. <p> La entrega de mensajes seguros puede retrasarse debido a Caja fuerte análisis de datos adjuntos.|Protege su organización de ataques repetidos con los mismos datos adjuntos de malware. <p> Este es el valor predeterminado y el valor recomendado en Directivas de seguridad [preestablecidas](preset-security-policies.md)estándar y estricta.|
  |**Replace**|Quita los datos adjuntos de malware detectados. <p> Notifica a los destinatarios que se han quitado los datos adjuntos. <p>  Los mensajes [se ponen en cuarentena](manage-quarantined-messages-and-files.md) donde solo los administradores (no los usuarios finales) pueden revisar, liberar o eliminar los mensajes. <p> La entrega de mensajes seguros puede retrasarse debido a Caja fuerte análisis de datos adjuntos.|Aumentar la visibilidad de los destinatarios que se quitaron los datos adjuntos debido al malware detectado.|
  |**Entrega dinámica**|Entrega mensajes inmediatamente, pero reemplaza los datos adjuntos por marcadores de posición hasta Caja fuerte se completa el examen de datos adjuntos. <p> Para obtener más información, vea la sección [Entrega dinámica en Caja fuerte de datos adjuntos](#dynamic-delivery-in-safe-attachments-policies) más adelante en este artículo.|Evite retrasos en los mensajes mientras protege a los destinatarios de archivos malintencionados. <p> Permitir que los destinatarios obtengan una vista previa de los datos adjuntos en modo seguro mientras se realiza el examen.|
  |

- **Redirigir datos** adjuntos al detectar: habilite redirigir y enviar los datos  adjuntos a la siguiente dirección de correo **electrónico:** para bloquear **,** **supervisar** o reemplazar acciones, envíe mensajes que contengan datos adjuntos de malware a la dirección de correo electrónico interna o externa especificada para análisis e investigación.

  La recomendación para la configuración de directivas estándar y estricta es habilitar la redirección. Para obtener más información, [vea Caja fuerte configuración de datos adjuntos](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

- Aplique la selección anterior si el examen de malware para datos adjuntos se encuentra en tiempo de espera o si se produce un error: la acción especificada por **Caja fuerte Attachments unknown malware response** se toma en los mensajes incluso cuando Caja fuerte el examen de datos **adjuntos** no se puede completar. Seleccione siempre esta opción si selecciona Habilitar **redireccionamiento**. De lo contrario, los mensajes podrían perderse.

- **Filtros de destinatarios:** debe especificar las condiciones de destinatario y las excepciones que determinan a quién se aplica la directiva. Puede usar estas propiedades para condiciones y excepciones:
  - **El destinatario es**
  - **El dominio de destinatario es**
  - **El destinatario es un miembro de**

  Solo puede usar una condición o excepción una vez, pero la condición o excepción puede contener varios valores. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

- **Prioridad:** si crea varias directivas, puede especificar el orden en que se aplican. Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

  Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Entrega dinámica en directivas Caja fuerte datos adjuntos

> [!NOTE]
> La entrega dinámica solo funciona para Exchange Online buzones de correo.

La acción Entrega dinámica en Caja fuerte directivas de datos adjuntos busca eliminar los retrasos en la entrega de correo electrónico que puedan deberse al examen Caja fuerte datos adjuntos. El cuerpo del mensaje de correo electrónico se entrega al destinatario con un marcador de posición para cada dato adjunto. El marcador de posición permanece hasta que se encuentra que los datos adjuntos son seguros y, a continuación, los datos adjuntos están disponibles para abrirse o descargarse.

Si se encuentra que un dato adjunto es malintencionado, el mensaje se pone en cuarentena. Solo los administradores (no los usuarios finales) pueden revisar, liberar o eliminar los mensajes que se han puesto en cuarentena mediante Caja fuerte análisis de datos adjuntos. Para obtener más información, vea [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).

La mayoría de los archivos PDF Office documentos pueden obtener una vista previa en modo seguro mientras Caja fuerte análisis de datos adjuntos está en curso. Si un archivo adjunto no es compatible con el previewer de entrega dinámica, los destinatarios verán un marcador de posición para los datos adjuntos hasta que se complete Caja fuerte análisis de datos adjuntos.

Si usas un dispositivo móvil y los ARCHIVOS PDF no se están representando en el previewer de entrega dinámica en el dispositivo móvil, intenta abrir el mensaje en Outlook en la web (anteriormente conocido como Outlook Web App) con el explorador móvil.

Estas son algunas consideraciones para la entrega dinámica y los mensajes reenviados:

- Si el destinatario reenviado está protegido por una directiva de datos adjuntos de Caja fuerte que usa la opción Entrega dinámica, el destinatario ve el marcador de posición, con la capacidad de obtener una vista previa de los archivos compatibles.
- Si el destinatario reenviado no está protegido por una directiva de datos adjuntos de Caja fuerte, el mensaje y los datos adjuntos se entregarán sin ningún marcador de posición Caja fuerte datos adjuntos o análisis de datos adjuntos.

Hay escenarios en los que la entrega dinámica no puede reemplazar los datos adjuntos de los mensajes. Entre estos escenarios se incluyen lo siguientes:

- Mensajes en carpetas públicas.
- Mensajes que se enruta fuera y, a continuación, de nuevo en el buzón de un usuario mediante reglas personalizadas.
- Mensajes que se mueven (de forma automática o manual) fuera de los buzones de nube a otras ubicaciones, incluidas las carpetas de archivo.
- Las reglas de la Bandeja de entrada mueven el mensaje fuera de la Bandeja de entrada a otra carpeta.
- Mensajes eliminados.
- La carpeta de búsqueda del buzón de correo del usuario está en estado de error.
- Exchange Online donde Exclaimer está habilitado. Para resolver este problema, vea [KB4014438](https://support.microsoft.com/help/4014438).
- [S/MIME)](/exchange/security-and-compliance/smime-exo/smime-exo) mensajes cifrados.
- Configuró la acción Entrega dinámica en una directiva de datos adjuntos de Caja fuerte, pero el destinatario no admite entrega dinámica (por ejemplo, el destinatario es un buzón de correo en una organización Exchange local). Sin embargo, [Caja fuerte links de Microsoft Defender](set-up-safe-links-policies.md) para Office 365 puede examinar datos adjuntos de archivos Office que contienen direcciones URL (en función de cómo se configuren las opciones globales de Caja fuerte [links).](configure-global-settings-for-safe-links.md)

## <a name="submitting-files-for-malware-analysis"></a>Envío de archivos para análisis de malware

- Si recibe un archivo que desea enviar a Microsoft para su análisis, vea Enviar malware y no malware a [Microsoft para su análisis.](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)
- Si recibe un mensaje de correo electrónico (con o sin datos adjuntos) que desea enviar a Microsoft para su análisis, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).
