---
title: Archivos adjuntos seguros
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.localizationpriority: medium
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
ms.openlocfilehash: b65813dedcf421e8335dc2433b5befee69cc60e6
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2021
ms.locfileid: "61300399"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Caja fuerte datos adjuntos de Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Caja fuerte datos adjuntos de [Microsoft Defender](defender-for-office-365.md) para Office 365 proporciona una capa adicional de protección para los datos adjuntos de correo electrónico que ya han sido examinados por la protección antimalware en [Exchange Online Protection (EOP).](anti-malware-protection.md) En concreto, Caja fuerte datos adjuntos usa un entorno virtual para comprobar los datos adjuntos de los mensajes de correo electrónico antes de entregarse a los destinatarios (un proceso conocido como _detonación_).

La protección de datos adjuntos seguros para mensajes de correo electrónico se controla mediante directivas de datos adjuntos seguros. Aunque no hay ninguna directiva predeterminada de  datos adjuntos de Caja fuerte, la directiva de seguridad predefinida de protección integrada proporciona protección de datos adjuntos de Caja fuerte a todos los destinatarios (usuarios que no están definidos en directivas de datos adjuntos de Caja fuerte personalizadas). Para obtener más información, vea [Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md). También puede crear directivas Caja fuerte datos adjuntos que se aplican a usuarios, grupos o dominios específicos. Para obtener instrucciones, vea [Configurar directivas Caja fuerte datos adjuntos en Microsoft Defender para Office 365](set-up-safe-attachments-policies.md).

En la tabla siguiente se describen escenarios para los datos adjuntos de Caja fuerte en organizaciones de Microsoft 365 y Office 365 que incluyen Microsoft Defender para Office 365 (es decir, la falta de licencias nunca es un problema en los ejemplos).

<br>

****

|Escenario|Resultado|
|---|---|
|La organización de Microsoft 365 E5 pat no tiene configuradas Caja fuerte de datos adjuntos.|Pat está protegido por Caja fuerte adjuntos debido a la directiva de seguridad preestablecida de protección integrada que se aplica a todos los destinatarios que no están definidos de otro modo en las directivas Caja fuerte datos adjuntos. |
|La organización de Lee tiene una directiva Caja fuerte datos adjuntos que solo se aplica a los empleados de finanzas. Lee es miembro del departamento de ventas.|Lee y el resto del departamento de ventas están protegidos  por los datos adjuntos de Caja fuerte debido a la directiva de seguridad preestablecida de protección integrada que se aplica a todos los destinatarios que no están definidos de otro modo en las directivas de datos adjuntos Caja fuerte.|
|Ayer, un administrador de la organización de Juan creó una directiva Caja fuerte datos adjuntos que se aplica a todos los empleados. Anteriormente, Juan recibió un mensaje de correo electrónico que incluía datos adjuntos.|Jean está protegido por Caja fuerte datos adjuntos debido a esa directiva Caja fuerte datos adjuntos personalizados. <p> Normalmente, una nueva directiva tarda unos 30 minutos en tener efecto.|
|La organización de Chris tiene directivas de datos adjuntos Caja fuerte para todos los usuarios de la organización. Chris recibe un correo electrónico que tiene datos adjuntos y, a continuación, reenvía el mensaje a destinatarios externos.|Chis está protegido por Caja fuerte datos adjuntos. <p> Si los destinatarios externos de una Microsoft 365, los mensajes reenviados también están protegidos por Caja fuerte datos adjuntos.|
|

El análisis de datos adjuntos seguros tiene lugar en la misma región donde residen los datos de Microsoft 365. Para obtener más información acerca de la geografía del centro de datos, [vea ¿Dónde se encuentran los datos?](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> Las siguientes características se encuentran en la configuración global de las directivas Caja fuerte datos adjuntos en el portal Microsoft 365 Defender datos adjuntos. Sin embargo, estas opciones de configuración están habilitadas o deshabilitadas globalmente y no requieren directivas Caja fuerte datos adjuntos:
>
> - [Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md).
> - [Documentos seguros en Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Caja fuerte de directiva de datos adjuntos

En esta sección se describe la configuración de las Caja fuerte de datos adjuntos:

- **Caja fuerte datos adjuntos respuesta de malware desconocido:** esta configuración controla la acción de la detección de malware Caja fuerte datos adjuntos en los mensajes de correo electrónico. Las opciones disponibles se describen en la tabla siguiente:

  <br>

  ****

  |Opción|Efecto|Úselo cuando desee:|
  |---|---|---|
  |**Desactivado**|Los datos adjuntos no se examinan en busca de malware Caja fuerte datos adjuntos. Los mensajes aún se examinan en busca de malware mediante la [protección antimalware en EOP](anti-malware-protection.md).|Desactiva el examen de los destinatarios seleccionados. <p> Evite retrasos innecesarios en el enrutamiento del correo interno. <p> **Esta opción no se recomienda para la mayoría de los usuarios. Solo debe usar esta opción para desactivar el examen de datos adjuntos Caja fuerte de destinatarios que solo reciben mensajes de remitentes de confianza. ZAP no pondrá en cuarentena los mensajes si Caja fuerte datos adjuntos está desactivado y no se recibe una señal de malware. Para obtener más información, consulte [Zero-hour auto purge](zero-hour-auto-purge.md)**|
  |**Supervisar**|Entrega mensajes con datos adjuntos y, a continuación, realiza un seguimiento de lo que sucede con el malware detectado. <p> La entrega de mensajes seguros puede retrasarse debido a Caja fuerte análisis de datos adjuntos.|Vea dónde va el malware detectado en su organización.|
  |**Bloquear**|Impide que se entreguen los mensajes con datos adjuntos de malware detectados. <p> Los mensajes se ponen en cuarentena. De forma predeterminada, solo los administradores (no los usuarios) pueden revisar, liberar o eliminar los mensajes.<sup>\*</sup> <p> Bloquea automáticamente las instancias futuras de los mensajes y datos adjuntos. <p> La entrega de mensajes seguros puede retrasarse debido a Caja fuerte análisis de datos adjuntos.|Protege su organización de ataques repetidos con los mismos datos adjuntos de malware. <p> Este es el valor predeterminado y el valor recomendado en Directivas de seguridad [preestablecidas](preset-security-policies.md)estándar y estricta.|
  |**Replace**|Quita los datos adjuntos de malware detectados. <p> Notifica a los destinatarios que se han quitado los datos adjuntos. <p>  Los mensajes que contienen datos adjuntos malintencionados se ponen en cuarentena. De forma predeterminada, solo los administradores (no los usuarios) pueden revisar, liberar o eliminar los mensajes.<sup>\*</sup> <p> La entrega de mensajes seguros puede retrasarse debido a Caja fuerte análisis de datos adjuntos.|Aumentar la visibilidad de los destinatarios que se quitaron los datos adjuntos debido al malware detectado.|
  |**Entrega dinámica**|Entrega mensajes inmediatamente, pero reemplaza los datos adjuntos por marcadores de posición hasta Caja fuerte se completa el examen de datos adjuntos. <p> Los mensajes que contienen datos adjuntos malintencionados se ponen en cuarentena. De forma predeterminada, solo los administradores (no los usuarios) pueden revisar, liberar o eliminar los mensajes.<sup>\*</sup> <p> Para obtener más información, vea la sección [Entrega dinámica en Caja fuerte de datos adjuntos](#dynamic-delivery-in-safe-attachments-policies) más adelante en este artículo.|Evite retrasos en los mensajes mientras protege a los destinatarios de archivos malintencionados.|
  |

  <sup>\*</sup>Los administradores pueden  crear y asignar directivas de cuarentena en Caja fuerte directivas de datos adjuntos que definen lo que los usuarios pueden hacer a los mensajes en cuarentena. Para más información, consulte [Políticas de cuarentena](quarantine-policies.md).

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

Si se encuentra que un dato adjunto es malintencionado, el mensaje se pone en cuarentena.

La mayoría de los archivos PDF Office documentos pueden obtener una vista previa en modo seguro mientras Caja fuerte análisis de datos adjuntos está en curso. Si un archivo adjunto no es compatible con el previewer de entrega dinámica, los destinatarios verán un marcador de posición para los datos adjuntos hasta que se complete Caja fuerte análisis de datos adjuntos.

Si usas un dispositivo móvil y los ARCHIVOS PDF no se están representando en el previewer de entrega dinámica en el dispositivo móvil, intenta abrir el mensaje en Outlook en la Web (anteriormente conocido como Outlook Web App) con el explorador móvil.

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
