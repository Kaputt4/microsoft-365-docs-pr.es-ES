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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre la característica Datos adjuntos seguros en Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e85695a6d0fba221f3c614ec33b3552d37153e2
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175852"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Datos adjuntos seguros en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Datos adjuntos seguros en Microsoft Defender para [Office 365](office-365-atp.md) proporciona una capa adicional de protección para los datos adjuntos de correo electrónico que ya han sido analizados por la protección antimalware en [Exchange Online Protection (EOP).](anti-malware-protection.md) En concreto, Datos adjuntos seguros usa un entorno virtual para comprobar los datos adjuntos de los mensajes de correo electrónico antes de entregarse a los destinatarios (un proceso conocido como _detonación)._

La protección de datos adjuntos seguros para los mensajes de correo electrónico se controla mediante directivas de datos adjuntos seguros. No hay ninguna directiva de datos adjuntos seguros predeterminada, por lo que para obtener la protección de datos adjuntos seguros, debe crear una o más directivas de datos **adjuntos seguros.** Para obtener instrucciones, [vea Configurar directivas de datos adjuntos seguros en Defender para Office 365.](set-up-atp-safe-attachments-policies.md)

En la siguiente tabla se describen escenarios para datos adjuntos seguros en organizaciones de Microsoft 365 y Office 365 que incluyen Microsoft Defender para Office 365 (es decir, la falta de licencias nunca es un problema en los ejemplos).

****

|Escenario|Resultado|
|---|---|
|La organización de Microsoft 365 E5 de Pat no tiene configuradas directivas de datos adjuntos seguros.|Pat no está protegido por datos adjuntos seguros. <p> Un administrador debe crear al menos una directiva de datos adjuntos seguros para que la protección de datos adjuntos seguros esté activa. Además, las condiciones de la directiva deben incluir Pat si Pat se va a proteger con datos adjuntos seguros.|
|La organización de Lee tiene una directiva de datos adjuntos seguros que solo se aplica a los empleados de finanzas. Lee es miembro del departamento de ventas.|Lee no está protegido por datos adjuntos seguros. <p> Los empleados de finanzas están protegidos por datos adjuntos seguros, pero los empleados de ventas (y otros empleados) no lo están.|
|Ayer, un administrador de la organización de Juan creó una directiva de datos adjuntos seguros que se aplica a todos los empleados. Hoy mismo, Juan recibió un mensaje de correo electrónico que incluía datos adjuntos.|Juan está protegido por datos adjuntos seguros. <p> Normalmente, una nueva directiva tarda unos 30 minutos en tener efecto.|
|La organización de Chris tiene directivas de datos adjuntos seguros de larga duración para todos los usuarios de la organización. Chris recibe un correo electrónico que tiene datos adjuntos y, a continuación, reenvía el mensaje a destinatarios externos.|Chis está protegido por datos adjuntos seguros. <p> Si los destinatarios externos también tienen directivas de datos adjuntos seguros en su organización, los mensajes reenviados están sujetos a dichas directivas.|
|

El examen de datos adjuntos seguros tiene lugar en la misma región donde residen los datos de Microsoft 365. Para obtener más información acerca de la geografía del centro de datos, [consulte ¿Dónde se encuentran los datos?](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> Las siguientes características se encuentran en la configuración global de las directivas de datos adjuntos seguros en el Centro de seguridad y cumplimiento de &, pero estas opciones están habilitadas o deshabilitadas globalmente y no requieren directivas de datos adjuntos seguros:
>
> - [Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams.](atp-for-spo-odb-and-teams.md)
>
> - [Documentos seguros en Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Configuración de directiva de datos adjuntos seguros

En esta sección se describe la configuración de las directivas de datos adjuntos seguros:

- **Respuesta de malware desconocido de** datos adjuntos seguros: esta configuración controla la acción para el análisis de malware de datos adjuntos seguros en los mensajes de correo electrónico. Las opciones disponibles se describen en la tabla siguiente:

  ****

  |Opción|Efecto|Úselo cuando desee:|
  |---|---|---|
  |**Desactivado**|Datos adjuntos seguros no examina los datos adjuntos en busca de malware. Los mensajes aún se examinan en busca de malware [mediante la protección antimalware en EOP.](anti-malware-protection.md)|Desactive el examen de los destinatarios seleccionados. <p> Evite retrasos innecesarios en el enrutamiento del correo interno. <p> **Esta opción no se recomienda para la mayoría de los usuarios. Solo debe usar esta opción para desactivar el examen de datos adjuntos seguros para los destinatarios que solo reciben mensajes de remitentes de confianza.**|
  |**Monitor**|Entrega mensajes con datos adjuntos y, a continuación, realiza un seguimiento de lo que sucede con el malware detectado. <p> Es posible que la entrega de mensajes seguros se retrase debido al examen de datos adjuntos seguros.|Ver dónde va el malware detectado en la organización.|
  |**Bloquear**|Impide que se entreguen los mensajes con datos adjuntos de malware detectados. <p> Los mensajes [se ponen en cuarentena](manage-quarantined-messages-and-files.md) donde solo los administradores (no los usuarios finales) pueden revisar, liberar o eliminar los mensajes. <p> Bloquea automáticamente las instancias futuras de los mensajes y datos adjuntos. <p> Es posible que la entrega de mensajes seguros se retrase debido al examen de datos adjuntos seguros.|Protege su organización de ataques repetidos con los mismos datos adjuntos de malware. <p> Este es el valor predeterminado y el valor recomendado en las directivas de seguridad preestablecidas Estándar y [Estricto.](preset-security-policies.md)|
  |**Replace**|Quita los datos adjuntos de malware detectados. <p> Notifica a los destinatarios que se han quitado los datos adjuntos. <p>  Los mensajes [se ponen en cuarentena](manage-quarantined-messages-and-files.md) donde solo los administradores (no los usuarios finales) pueden revisar, liberar o eliminar los mensajes. <p> Es posible que la entrega de mensajes seguros se retrase debido al examen de datos adjuntos seguros.|Aumentar la visibilidad a los destinatarios de que se quitaron los datos adjuntos debido al malware detectado.|
  |**Entrega dinámica**|Entrega mensajes inmediatamente, pero reemplaza los datos adjuntos por marcadores de posición hasta que se complete el examen de datos adjuntos seguros. <p> Para obtener más información, vea la sección [Entrega dinámica en directivas de datos](#dynamic-delivery-in-safe-attachments-policies) adjuntos seguros más adelante en este artículo.|Evite retrasos en los mensajes mientras protege a los destinatarios de archivos malintencionados. <p> Permitir que los destinatarios obtengan una vista previa de los datos adjuntos en modo seguro mientras se realiza el examen.|
  |

- Redirigir datos adjuntos al **detectarlos:** habilite el redireccionamiento y envíe  los datos adjuntos a la siguiente dirección de correo **electrónico:** para las acciones **Bloquear,** **Supervisar** o Reemplazar, envíe mensajes que contengan datos adjuntos de malware a la dirección de correo electrónico interna o externa especificada para su análisis e investigación.

  La recomendación para la configuración de directivas estándar y estricta es habilitar el redireccionamiento. Para obtener más información, vea [Configuración de datos adjuntos seguros.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)

- Aplique la selección anterior si se ha completado el análisis de malware para datos adjuntos o si se produce un error: la acción especificada por la respuesta de **malware** desconocido de datos adjuntos seguros se toma en los mensajes incluso cuando no se puede completar el examen de datos **adjuntos** seguros. Seleccione siempre esta opción si selecciona **Habilitar** redireccionamiento. De lo contrario, es posible que se pierdan mensajes.

- **Filtros de** destinatarios: debe especificar las condiciones de destinatario y excepciones que determinan a quién se aplica la directiva. Puede usar estas propiedades para condiciones y excepciones:

  - **El destinatario es**
  - **El dominio del destinatario es**
  - **El destinatario es un miembro de**

  Solo puede usar una condición o excepción una vez, pero la condición o excepción puede contener varios valores. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

- **Prioridad:** si crea varias directivas, puede especificar el orden en que se aplican. Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

  Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Entrega dinámica en directivas de datos adjuntos seguros

> [!NOTE]
> La entrega dinámica solo funciona para los buzones de Exchange Online.

La acción de entrega dinámica en las directivas de datos adjuntos seguros busca eliminar los retrasos en la entrega de correo electrónico que puedan deberse al examen de datos adjuntos seguros. El cuerpo del mensaje de correo electrónico se entrega al destinatario con un marcador de posición para cada dato adjunto. El marcador de posición permanece hasta que se encuentra que los datos adjuntos son seguros y, a continuación, los datos adjuntos están disponibles para abrirse o descargarse.

Si se encuentra que un archivo adjunto es malintencionado, el mensaje se pone en cuarentena. Solo los administradores (no los usuarios finales) pueden revisar, liberar o eliminar mensajes que se han puesto en cuarentena mediante el examen de datos adjuntos seguros. Para obtener más información, vea [Administrar mensajes y archivos en cuarentena como administrador.](manage-quarantined-messages-and-files.md)

La mayoría de los archivos PDF y documentos de Office se pueden obtener una vista previa en modo seguro mientras el examen de datos adjuntos seguros está en curso. Si un archivo adjunto no es compatible con la vista previa de entrega dinámica, los destinatarios verán un marcador de posición para los datos adjuntos hasta que se complete el examen de datos adjuntos seguros.

Si usa un dispositivo móvil y los archivos PDF no se están representando en la vista previa de entrega dinámica en su dispositivo móvil, intente abrir el mensaje en Outlook en la Web (anteriormente conocido como Outlook Web App) con el explorador móvil.

Estas son algunas consideraciones para la entrega dinámica y los mensajes reenviados:

- Si el destinatario reenviado está protegido por una directiva de datos adjuntos seguros que usa la opción de entrega dinámica, el destinatario ve el marcador de posición, con la capacidad de obtener una vista previa de los archivos compatibles.

- Si el destinatario reenviado no está protegido por una directiva de datos adjuntos seguros, el mensaje y los datos adjuntos se entregarán sin ningún análisis de datos adjuntos seguros ni marcadores de posición de datos adjuntos.

Hay escenarios en los que la entrega dinámica no puede reemplazar los datos adjuntos de los mensajes. Entre estos escenarios se incluyen lo siguientes:

- Mensajes en carpetas públicas.

- Mensajes que se enruten fuera y, a continuación, de nuevo en el buzón de un usuario mediante reglas personalizadas.

- Mensajes que se mueven (de forma automática o manual) fuera de los buzones de la nube a otras ubicaciones, incluidas las carpetas de archivo.

- Mensajes eliminados.

- La carpeta de búsqueda del buzón del usuario se encuentra en un estado de error.

- Organizaciones de Exchange Online donde Exclaimer está habilitado. Para resolver esto, consulte [KB4014438](https://support.microsoft.com/help/4014438).

- [S/MIME)](s-mime-for-message-signing-and-encryption.md) mensajes cifrados.

- Configuró la acción entrega dinámica en una directiva de datos adjuntos seguros, pero el destinatario no admite la entrega dinámica (por ejemplo, el destinatario es un buzón de una organización de Exchange local). Sin embargo, Vínculos seguros en Microsoft Defender para [Office 365](set-up-atp-safe-links-policies.md) es capaz de examinar los datos adjuntos de archivos de Office que contienen direcciones URL (dependiendo de cómo se configuren las opciones [globales](configure-global-settings-for-safe-links.md) de vínculos seguros).

## <a name="submitting-files-for-malware-analysis"></a>Envío de archivos para análisis de malware

- Si recibe un archivo que desea enviar a Microsoft para su análisis, vea Enviar malware y no malware a [Microsoft para su análisis.](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)

- Si recibe un mensaje de correo electrónico (con o sin datos adjuntos) que desea enviar a Microsoft para su análisis, vea Notificar mensajes y [archivos a Microsoft.](report-junk-email-messages-to-microsoft.md)
