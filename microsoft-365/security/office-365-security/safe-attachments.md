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
description: Los administradores pueden obtener información sobre la característica datos adjuntos de Caja fuerte en Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9d069d92eb012211af8dd4e12109ebcae7eb221e
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "65128726"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>datos adjuntos de Caja fuerte en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Caja fuerte Datos adjuntos en [Microsoft Defender para Office 365](defender-for-office-365.md) proporciona una capa adicional de protección para los datos adjuntos de correo electrónico que ya han sido examinados por [la protección antimalware en Exchange Online Protection (EOP).](anti-malware-protection.md) En concreto, Caja fuerte Attachments usa un entorno virtual para comprobar los datos adjuntos en los mensajes de correo electrónico antes de que se entreguen a los destinatarios (un proceso conocido como _detonación_).

La protección de datos adjuntos seguros para mensajes de correo electrónico se controla mediante directivas de datos adjuntos seguros. Aunque no hay ninguna directiva de datos adjuntos de Caja fuerte predeterminada, la directiva de seguridad preestablecida **de protección integrada** proporciona Caja fuerte protección de datos adjuntos a todos los destinatarios (usuarios que no están definidos en directivas personalizadas de datos adjuntos de Caja fuerte). Para obtener más información, vea [Directivas de seguridad preestablecidas en EOP y Microsoft Defender para Office 365](preset-security-policies.md). También puede crear directivas de datos adjuntos Caja fuerte que se apliquen a usuarios, grupos o dominios específicos. Para obtener instrucciones, consulte [Configuración de directivas de datos adjuntos de Caja fuerte en Microsoft Defender para Office 365](set-up-safe-attachments-policies.md).

En la tabla siguiente se describen los escenarios de Caja fuerte Datos adjuntos en Microsoft 365 y Office 365 organizaciones que incluyen Microsoft Defender para Office 365 (es decir, la falta de licencias nunca es un problema en los ejemplos).

|Escenario|Resultado|
|---|---|
|La organización Microsoft 365 E5 de Pat no tiene configuradas directivas de datos adjuntos de Caja fuerte.|Pat está protegido por Caja fuerte Datos adjuntos debido a la directiva de seguridad preestablecida **de protección integrada** que se aplica a todos los destinatarios que no están definidos de otro modo en las directivas de datos adjuntos de Caja fuerte.|
|La organización de Lee tiene una directiva de datos adjuntos de Caja fuerte que solo se aplica a los empleados financieros. Lee es miembro del departamento de ventas.|Lee y el resto del departamento de ventas están protegidos por Caja fuerte Attachments debido a la directiva de seguridad preestablecida **de protección integrada** que se aplica a todos los destinatarios que no están definidos de otro modo en Caja fuerte directivas de datos adjuntos.|
|Ayer, un administrador de la organización de Jean creó una directiva de datos adjuntos de Caja fuerte que se aplica a todos los empleados. A primera hora de hoy, Jean recibió un mensaje de correo electrónico que incluía un archivo adjunto.|Jean está protegido por Caja fuerte Datos adjuntos debido a esa directiva de datos adjuntos Caja fuerte personalizados. <br/><br/> Normalmente, una nueva directiva tarda unos 30 minutos en surtir efecto.|
|La organización de Chris tiene directivas de datos adjuntos de Caja fuerte de larga duración para todos los usuarios de la organización. Chris recibe un correo electrónico que tiene datos adjuntos y, a continuación, reenvía el mensaje a destinatarios externos.|Chis está protegido por datos adjuntos de Caja fuerte. <br/><br/> Si los destinatarios externos de una organización Microsoft 365, los mensajes reenviados también están protegidos por Caja fuerte Datos adjuntos.|

El análisis de datos adjuntos seguros tiene lugar en la misma región donde residen los datos de Microsoft 365. Para obtener más información sobre la geografía del centro de datos, consulte [¿Dónde se encuentran los datos?](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> Las siguientes características se encuentran en la configuración global de las directivas de datos adjuntos de Caja fuerte en el portal de Microsoft 365 Defender. Sin embargo, esta configuración está habilitada o deshabilitada globalmente y no requieren directivas de datos adjuntos de Caja fuerte:
>
> - [Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md).
> - [Documentos seguros en Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>configuración de la directiva de datos adjuntos de Caja fuerte

En esta sección se describe la configuración de las directivas de datos adjuntos de Caja fuerte:

- **Caja fuerte Respuesta de malware desconocida de datos adjuntos**: esta configuración controla la acción para el examen de malware de Caja fuerte Attachments en los mensajes de correo electrónico. Las opciones disponibles se describen en la tabla siguiente:

  |Opción|Efecto|Use cuando desee:|
  |---|---|---|
  |**Desactivado**|Los datos adjuntos no se examinan para buscar malware Caja fuerte Datos adjuntos. Los mensajes todavía se examinan para buscar malware mediante [la protección contra malware en EOP](anti-malware-protection.md).|Desactive el examen para los destinatarios seleccionados. <br/><br/> Evite retrasos innecesarios en el enrutamiento del correo interno. <br/><br/> **Esta opción no se recomienda para la mayoría de los usuarios. Solo debe usar esta opción para desactivar Caja fuerte examen de datos adjuntos para los destinatarios que solo reciben mensajes de remitentes de confianza. ZAP no pondrá en cuarentena los mensajes si Caja fuerte Datos adjuntos está desactivado y no se recibe una señal de malware. Para obtener más información, consulte [Purga automática de hora cero](zero-hour-auto-purge.md).**|
  |**Supervisar**|Entrega mensajes con datos adjuntos y, a continuación, realiza un seguimiento de lo que sucede con el malware detectado. <br/><br/> Es posible que la entrega de mensajes seguros se retrase debido al examen de datos adjuntos Caja fuerte.|Vea dónde va el malware detectado en su organización.|
  |**Bloquear**|Impide que se entreguen mensajes con datos adjuntos de malware detectados. <br/><br/> Los mensajes están en cuarentena. De forma predeterminada, solo los administradores (no los usuarios) pueden revisar, liberar o eliminar los mensajes.<sup>\*</sup> <br/><br/> Bloquea automáticamente futuras instancias de los mensajes y los datos adjuntos. <br/><br/> Es posible que la entrega de mensajes seguros se retrase debido al examen de datos adjuntos Caja fuerte.|Protege su organización de ataques repetidos con los mismos datos adjuntos de malware. <br/><br/> Este es el valor predeterminado y el valor recomendado en Directivas de [seguridad preestablecidas](preset-security-policies.md) estándar y estricta.|
  |**Replace**|Quita los datos adjuntos de malware detectados. <br/><br/> Notifica a los destinatarios que se han quitado los datos adjuntos. <br/><br/>  Los mensajes que contienen datos adjuntos malintencionados se ponen en cuarentena. De forma predeterminada, solo los administradores (no los usuarios) pueden revisar, liberar o eliminar los mensajes.<sup>\*</sup> <br/><br/> Es posible que la entrega de mensajes seguros se retrase debido al examen de datos adjuntos Caja fuerte.|Aumentar la visibilidad para los destinatarios de que los datos adjuntos se quitaron debido a malware detectado.|
  |**Entrega dinámica**|Entrega mensajes inmediatamente, pero reemplaza los datos adjuntos por marcadores de posición hasta que se complete Caja fuerte examen de datos adjuntos. <br/><br/> Los mensajes que contienen datos adjuntos malintencionados se ponen en cuarentena. De forma predeterminada, solo los administradores (no los usuarios) pueden revisar, liberar o eliminar los mensajes.<sup>\*</sup> <br/><br/> Para obtener más información, consulte la sección [Dynamic Delivery in Caja fuerte Attachments policies (Entrega dinámica en Caja fuerte directivas de datos adjuntos](#dynamic-delivery-in-safe-attachments-policies)) más adelante en este artículo.|Evite retrasos en los mensajes al proteger a los destinatarios de archivos malintencionados.|

  <sup>\*</sup>Los administradores pueden crear y asignar _directivas de cuarentena_ en Caja fuerte directivas de datos adjuntos que definen lo que los usuarios pueden hacer en los mensajes en cuarentena. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).

- **Redirigir datos adjuntos en la detección: habilite el redireccionamiento** y **envíe los datos adjuntos a la siguiente dirección de correo electrónico**: para las acciones **Bloquear**, **Supervisar** o **Reemplazar** , envíe mensajes que contengan datos adjuntos de malware a la dirección de correo electrónico interna o externa especificada para su análisis e investigación.

  La recomendación para la configuración de directivas estándar y estricta es habilitar el redireccionamiento. Para obtener más información, consulte [Caja fuerte Configuración de datos adjuntos](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

- **Aplique la selección anterior si se agota el tiempo de espera o se produce un error en el examen de malware de datos adjuntos**: la acción especificada por **Caja fuerte Respuesta de malware desconocida de los datos adjuntos** se realiza en los mensajes incluso cuando no se puede completar el examen de datos adjuntos Caja fuerte. Seleccione siempre esta opción si selecciona **Habilitar redirección**. De lo contrario, es posible que se pierdan los mensajes.

- **Filtros de destinatario**: debe especificar las condiciones y excepciones del destinatario que determinan a quién se aplica la directiva. Puede usar estas propiedades para condiciones y excepciones:
  - **El destinatario es**
  - **El dominio de destinatario es**
  - **El destinatario es un miembro de**

  Solo puede usar una condición o una excepción una vez, pero la condición o la excepción pueden contener varios valores. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

- **Prioridad**: si crea varias directivas, puede especificar el orden en que se aplican. Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

  Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Entrega dinámica en directivas de datos adjuntos de Caja fuerte

> [!NOTE]
> La entrega dinámica solo funciona para los buzones de Exchange Online.

La acción Entrega dinámica en Caja fuerte directivas de datos adjuntos busca eliminar los retrasos en la entrega de correo electrónico que puedan deberse al examen de datos adjuntos de Caja fuerte. El cuerpo del mensaje de correo electrónico se entrega al destinatario con un marcador de posición para cada dato adjunto. El marcador de posición permanece hasta que se detecta que los datos adjuntos son seguros y, a continuación, los datos adjuntos están disponibles para abrirse o descargarse.

Si se detecta que los datos adjuntos son malintencionados, el mensaje se pone en cuarentena.

La mayoría de los archivos PDF y documentos Office se pueden previsualizar en modo seguro mientras Caja fuerte análisis de datos adjuntos está en curso. Si los datos adjuntos no son compatibles con el previewer de entrega dinámica, los destinatarios verán un marcador de posición para los datos adjuntos hasta que se complete Caja fuerte examen de datos adjuntos.

Si usa un dispositivo móvil y los archivos PDF no se representan en el previewer de entrega dinámica en el dispositivo móvil, intente abrir el mensaje en Outlook en la web (anteriormente conocido como Outlook Web App) mediante el explorador móvil.

Estas son algunas consideraciones para la entrega dinámica y los mensajes reenviados:

- Si el destinatario reenviado está protegido por una directiva de datos adjuntos seguros que usa la opción Entrega dinámica, el destinatario verá el marcador de posición, con la capacidad de obtener una vista previa de los archivos compatibles.
- Si el destinatario reenviado no está protegido por una directiva de datos adjuntos seguros, el mensaje y los datos adjuntos se entregarán sin ningún marcador de posición de datos adjuntos o de análisis de datos adjuntos seguros.

Hay escenarios en los que la entrega dinámica no puede reemplazar los datos adjuntos en los mensajes. Entre estos escenarios se incluyen lo siguientes:

- Mensajes en carpetas públicas.
- Mensajes que se enrutan fuera de y, a continuación, de nuevo en el buzón de un usuario mediante reglas personalizadas.
- Mensajes que se mueven (de forma automática o manual) desde buzones de correo en la nube a otras ubicaciones, incluidas las carpetas de archivo.
- Las reglas de bandeja de entrada mueven el mensaje de la Bandeja de entrada a otra carpeta.
- Mensajes eliminados.
- La carpeta de búsqueda del buzón de correo del usuario está en estado de error.
- Organizaciones de Exchange Online donde Exclaimer está habilitado. Para resolver este problema, consulte [KB4014438](https://support.microsoft.com/help/4014438).
- [S/MIME)](/exchange/security-and-compliance/smime-exo/smime-exo) mensajes cifrados.
- Ha configurado la acción Entrega dinámica en una directiva de datos adjuntos seguros, pero el destinatario no admite la entrega dinámica (por ejemplo, el destinatario es un buzón de una organización local de Exchange). Sin embargo, [vínculos seguros en Microsoft Defender para Office 365](set-up-safe-links-policies.md) es capaz de examinar los datos adjuntos de archivos de Office que contienen direcciones URL (dependiendo de cómo se configure la [configuración global para vínculos seguros](configure-global-settings-for-safe-links.md) ).

## <a name="submitting-files-for-malware-analysis"></a>Envío de archivos para el análisis de malware

- Si recibe un archivo que desea enviar a Microsoft para su análisis, consulte [Envío de malware y no malware a Microsoft para su análisis](submitting-malware-and-non-malware-to-microsoft-for-analysis.md).
- Si recibe un mensaje de correo electrónico (con o sin datos adjuntos) que desea enviar a Microsoft para su análisis, consulte [Informe de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).
