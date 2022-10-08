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
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- m365-security
- m365initiative-defender-office365
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre la característica Datos adjuntos seguros en Microsoft Defender para Office 365.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 3816b047fce131a161a6154a013def9a6c92cd2b
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68054806"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Datos adjuntos seguros en Microsoft Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Datos adjuntos seguros en [Microsoft Defender para Office 365](defender-for-office-365.md) proporciona una capa adicional de protección para los datos adjuntos de correo electrónico que ya han sido examinados por [la protección antimalware en Exchange Online Protection (EOP)](anti-malware-protection.md). En concreto, Los datos adjuntos seguros usan un entorno virtual para comprobar los datos adjuntos en los mensajes de correo electrónico antes de que se entreguen a los destinatarios (un proceso conocido como _detonación_).

La protección de datos adjuntos seguros para mensajes de correo electrónico se controla mediante directivas de datos adjuntos seguros. Aunque no hay ninguna directiva de datos adjuntos seguros predeterminada, la directiva de seguridad preestablecida **de protección integrada** proporciona protección de datos adjuntos seguros a todos los destinatarios (usuarios que no están definidos en las directivas de seguridad preestablecidas estándar o estricta o en directivas de datos adjuntos seguros personalizadas). Para obtener más información, vea [Directivas de seguridad preestablecidas en EOP y Microsoft Defender para Office 365](preset-security-policies.md). También puede crear directivas de datos adjuntos seguros que se apliquen a usuarios, grupos o dominios específicos. Para obtener instrucciones, consulte [Configurar directivas de datos adjuntos seguros en Microsoft Defender para Office 365](set-up-safe-attachments-policies.md).

En la tabla siguiente se describen los escenarios de datos adjuntos seguros en Microsoft 365 y Office 365 organizaciones que incluyen Microsoft Defender para Office 365 (es decir, la falta de licencias nunca es un problema en los ejemplos).

|Escenario|Resultado|
|---|---|
|La organización Microsoft 365 E5 pat no tiene configuradas directivas de datos adjuntos seguros.|Pat está protegido por datos adjuntos seguros debido a la directiva de seguridad preestablecida **de protección integrada** que se aplica a todos los destinatarios que no están definidos de otro modo en las directivas de datos adjuntos seguros.|
|La organización de Lee tiene una directiva de datos adjuntos seguros que solo se aplica a los empleados financieros. Lee es miembro del departamento de ventas.|Lee y el resto del departamento de ventas están protegidos por datos adjuntos seguros debido a la directiva de seguridad preestablecida **de protección integrada** que se aplica a todos los destinatarios que no están definidos de otro modo en las directivas de datos adjuntos seguros.|
|Ayer, un administrador de la organización de Jean creó una directiva de datos adjuntos seguros que se aplica a todos los empleados. A primera hora de hoy, Jean recibió un mensaje de correo electrónico que incluía un archivo adjunto.|Jean está protegido por datos adjuntos seguros debido a esa directiva de datos adjuntos seguros personalizados. <br/><br/> Normalmente, una nueva directiva tarda unos 30 minutos en surtir efecto.|
|La organización de Chris tiene directivas de datos adjuntos seguros de larga duración para todos los usuarios de la organización. Chris recibe un correo electrónico que tiene datos adjuntos y, a continuación, reenvía el mensaje a destinatarios externos.|Chis está protegido por datos adjuntos seguros. <br/><br/> Si los destinatarios externos están en una organización de Microsoft 365, los mensajes reenviados también están protegidos por datos adjuntos seguros.|

El análisis de datos adjuntos seguros tiene lugar en la misma región donde residen los datos de Microsoft 365. Para obtener más información sobre la geografía del centro de datos, consulte [¿Dónde se encuentran los datos?](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> Las siguientes características se encuentran en la configuración global de las directivas de datos adjuntos seguros en el portal de Microsoft 365 Defender. Sin embargo, esta configuración está habilitada o deshabilitada globalmente y no requiere directivas de datos adjuntos seguros:
>
> - [Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md).
> - [Documentos seguros en Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Configuración de directiva de datos adjuntos seguros

En esta sección se describe la configuración de directivas de datos adjuntos seguros:

- **Filtros de destinatario**: debe especificar las condiciones y excepciones del destinatario que determinan a quién se aplica la directiva. Puede usar estas propiedades para condiciones y excepciones:
  - **Usuarios**
  - **Grupos**
  - **Dominios**

  Solo puede usar una condición o excepción una vez, pero la condición o excepción puede contener varios valores. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

  > [!IMPORTANT]
  > Los diferentes tipos de condiciones o excepciones no son aditivos; son inclusivos. La directiva se aplica _solo_ a los destinatarios que coinciden con _todos_ los filtros de destinatarios especificados. Por ejemplo, se configura una condición de filtro de destinatario en la directiva con los siguientes valores:
  >
  > - Usuarios: romain@contoso.com
  > - Grupos: Ejecutivos
  >
  > La directiva se aplica a romain@contoso.com _solo_ si también es miembro del grupo de Ejecutivos. Si no es miembro del grupo, la directiva no se le aplica.
  >
  > Asimismo, si utiliza el mismo filtro de destinatarios como excepción a la directiva, esta no se aplica a romain@contoso.com _solo_ si también es miembro del grupo de Ejecutivos. Si no es miembro del grupo, la directiva se le sigue aplicando.

- **Respuesta de malware desconocida de Datos adjuntos seguros**: esta configuración controla la acción para el análisis de malware de datos adjuntos seguros en los mensajes de correo electrónico. Las opciones disponibles se describen en la tabla siguiente:

  |Opción|Efecto|Úselo cuando desee:|
  |---|---|---|
  |**Desactivado**|Los datos adjuntos seguros no examinan los datos adjuntos en busca de malware. Los mensajes todavía se examinan para buscar malware mediante [la protección contra malware en EOP](anti-malware-protection.md).|Desactive el examen de los destinatarios seleccionados. <br/><br/> Evite retrasos innecesarios en el enrutamiento del correo interno. <br/><br/> **Esta opción no se recomienda para la mayoría de los usuarios. Solo debe usar esta opción para desactivar el examen de datos adjuntos seguros para los destinatarios que solo reciben mensajes de remitentes de confianza. ZAP no pondrá en cuarentena los mensajes si se desactivan los datos adjuntos seguros y no se recibe una señal de malware. Para obtener más información, consulte [Purga automática de hora cero](zero-hour-auto-purge.md).**|
  |**Supervisar**|Entrega mensajes con datos adjuntos y, a continuación, realiza un seguimiento de lo que sucede con el malware detectado. <br/><br/> La entrega de mensajes seguros podría retrasarse debido al examen de datos adjuntos seguros.|Vea dónde va el malware detectado en su organización.|
  |**Bloquear**|Impide que se entreguen los mensajes con datos adjuntos de malware detectados. <br/><br/> Los mensajes se ponen en cuarentena. De forma predeterminada, solo los administradores (no los usuarios) pueden revisar, liberar o eliminar los mensajes.<sup>\*</sup> <br/><br/> Bloquea automáticamente las instancias futuras de los mensajes y datos adjuntos. <br/><br/> La entrega de mensajes seguros podría retrasarse debido al examen de datos adjuntos seguros.|Protege su organización frente a ataques repetidos con los mismos datos adjuntos de malware. <br/><br/> Este es el valor predeterminado y el valor recomendado en Directivas de [seguridad preestablecidas](preset-security-policies.md) estándar y estricta.|
  |**Replace**|**Nota**: Esta acción quedará en desuso. Para obtener más información, vea [MC424901](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC424901). <br/><br/> Quita los datos adjuntos de malware detectados. <br/><br/> Notifica a los destinatarios que se han quitado los datos adjuntos. <br/><br/>  Los mensajes que contienen datos adjuntos malintencionados se ponen en cuarentena. De forma predeterminada, solo los administradores (no los usuarios) pueden revisar, liberar o eliminar los mensajes.<sup>\*</sup> <br/><br/> La entrega de mensajes seguros podría retrasarse debido al examen de datos adjuntos seguros.|Aumente la visibilidad para los destinatarios de que los datos adjuntos se quitaron debido al malware detectado.|
  |**Entrega dinámica**|Entrega mensajes inmediatamente, pero reemplaza los datos adjuntos por marcadores de posición hasta que se complete el examen de datos adjuntos seguros. <br/><br/> Los mensajes que contienen datos adjuntos malintencionados se ponen en cuarentena. De forma predeterminada, solo los administradores (no los usuarios) pueden revisar, liberar o eliminar los mensajes.<sup>\*</sup> <br/><br/> Para obtener más información, consulte la sección [Entrega dinámica en directivas de datos adjuntos seguros](#dynamic-delivery-in-safe-attachments-policies) más adelante en este artículo.|Evite retrasos en los mensajes al proteger a los destinatarios de archivos malintencionados.|

  <sup>\*</sup>**Directiva de cuarentena**: los administradores pueden crear y asignar _directivas de cuarentena en directivas_ de datos adjuntos seguros que definen lo que los usuarios pueden hacer con los mensajes en cuarentena. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).

- **Redirigir mensajes con datos adjuntos detectados**: **habilite la redirección** y **enviar mensajes que contengan datos adjuntos bloqueados, supervisados o reemplazados a la dirección de correo electrónico especificada**: para las acciones **Bloquear**, **Supervisar** o **Reemplazar** , envíe mensajes que contengan datos adjuntos de malware a la dirección de correo electrónico interna o externa especificada para su análisis e investigación.

  La recomendación para la configuración de directivas estándar y estricta es habilitar el redireccionamiento. Para obtener más información, consulte [Configuración de datos adjuntos seguros](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

  > [!NOTE]
  > El redireccionamiento estará pronto disponible solo para la acción **Supervisión** . Para obtener más información, consulte [MC424899](https://admin.microsoft.com/AdminPortal/Home?#/MessageCenter/:/messages/MC424899).

- **Aplique la respuesta de detección de datos adjuntos seguros si el examen no puede completarse (tiempo de espera o errores):** la acción especificada por la **respuesta de malware desconocido de Datos adjuntos seguros** se realiza en los mensajes incluso cuando el análisis de datos adjuntos seguros no se puede completar. Seleccione siempre esta opción si selecciona **Habilitar redirección**. De lo contrario, es posible que se pierdan los mensajes.

- **Prioridad**: si crea varias directivas, puede especificar el orden en que se aplican. Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

  Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Entrega dinámica en directivas de datos adjuntos seguros

> [!NOTE]
> La entrega dinámica solo funciona para los buzones de Exchange Online.

La acción Entrega dinámica en las directivas de datos adjuntos seguros busca eliminar los retrasos en la entrega de correo electrónico que puedan deberse al examen de datos adjuntos seguros. El cuerpo del mensaje de correo electrónico se entrega al destinatario con un marcador de posición para cada dato adjunto. El marcador de posición permanece hasta que se detecta que los datos adjuntos son seguros y, a continuación, los datos adjuntos están disponibles para abrirse o descargarse.

Si se detecta que los datos adjuntos son malintencionados, el mensaje se pone en cuarentena.

Se puede obtener una vista previa de la mayoría de los archivos PDF y documentos de Office en modo seguro mientras se está realizando el análisis de datos adjuntos seguros. Si un archivo adjunto no es compatible con el previewer de entrega dinámica, los destinatarios verán un marcador de posición para los datos adjuntos hasta que se complete el examen de datos adjuntos seguros.

Si usa un dispositivo móvil y los archivos PDF no se representan en el previewer de entrega dinámica en el dispositivo móvil, intente abrir el mensaje en Outlook en la Web (anteriormente conocido como Outlook Web App) mediante el explorador móvil.

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
- Exchange Online organizaciones donde Exclaimer está habilitado. Para resolver este problema, consulte [KB4014438](https://support.microsoft.com/help/4014438).
- [S/MIME)](/exchange/security-and-compliance/smime-exo/smime-exo) mensajes cifrados.
- Ha configurado la acción Entrega dinámica en una directiva de datos adjuntos seguros, pero el destinatario no admite la entrega dinámica (por ejemplo, el destinatario es un buzón de una organización local de Exchange). Sin embargo, [vínculos seguros en Microsoft Defender para Office 365](set-up-safe-links-policies.md) es capaz de examinar los datos adjuntos de archivos de Office que contienen direcciones URL (si el examen de vínculos seguros de aplicaciones de Office de soporte técnico está activado en la directiva de vínculos seguros aplicable).

## <a name="submitting-files-for-malware-analysis"></a>Envío de archivos para el análisis de malware

- Si recibe un archivo que desea enviar a Microsoft para su análisis, consulte [Envío de malware y no malware a Microsoft para su análisis](submitting-malware-and-non-malware-to-microsoft-for-analysis.md).
- Si recibe un mensaje de correo electrónico (con o sin datos adjuntos) que desea enviar a Microsoft para su análisis, consulte [Informe de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).
