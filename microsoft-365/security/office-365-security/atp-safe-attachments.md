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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre la característica datos adjuntos seguros de Microsoft defender para Office 365.
ms.openlocfilehash: d758db46f53be46d8213794f90bf8c462f9135e8
ms.sourcegitcommit: 9546708a5506fdbadbfe2500cbf1bd1aeaec6fcb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49020956"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Datos adjuntos seguros de Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Datos adjuntos seguros en [Microsoft defender para Office 365](office-365-atp.md) proporciona una capa adicional de protección para los datos adjuntos de correo electrónico que ya han sido examinados por [protección antimalware en Exchange Online Protection (EOP)](anti-malware-protection.md). En concreto, los datos adjuntos seguros usan un entorno virtual para comprobar los datos adjuntos en los mensajes de correo electrónico antes de que se entreguen a los destinatarios (un proceso conocido como _detonación_ ).

Las directivas de datos adjuntos seguros controlan la protección de los datos adjuntos seguros de los mensajes de correo. No hay una directiva de datos adjuntos seguros predeterminada, **por lo que para obtener la protección de datos adjuntos seguros, debe crear una o más directivas de datos adjuntos seguros**. Para obtener instrucciones, consulte [configurar directivas de datos adjuntos seguros en defender para Office 365](set-up-atp-safe-attachments-policies.md).

En la tabla siguiente se describen escenarios para los datos adjuntos seguros de las organizaciones de Microsoft 365 y Office 365 que incluyen Microsoft defender para Office 365 (es decir, la falta de licencias nunca es un problema en los ejemplos).

****

|Escenario|Resultado|
|---|---|
|La organización Microsoft 365 E5 de Pat no tiene directivas de datos adjuntos seguros configuradas.|Pat no está protegido por datos adjuntos seguros. <p> Un administrador debe crear al menos una directiva de datos adjuntos seguros para que la protección de datos adjuntos seguros esté activa. Además, las condiciones de la Directiva deben incluir a Pat si Pat debe estar protegida por datos adjuntos seguros.|
|La organización de Lee tiene una directiva de datos adjuntos seguros que solo se aplica a los empleados de finanzas. Lee es un miembro del Departamento de ventas.|Lee no está protegido con datos adjuntos seguros. <p> Los empleados de finanzas están protegidos por datos adjuntos seguros, pero los empleados de ventas (y otros empleados) no lo están.|
|Ayer, un administrador de la organización de Jean creó una directiva de datos adjuntos seguros que se aplica a todos los empleados. Anteriormente, Jean recibió un mensaje de correo electrónico que incluía datos adjuntos.|Jean está protegido por datos adjuntos seguros. <p> Normalmente, tardará unos 30 minutos en aplicarse una nueva Directiva.|
|La organización de Carlos tiene directivas de datos adjuntos seguros de larga duración para todos los usuarios de la organización. Chris recibe un correo electrónico con datos adjuntos y, a continuación, reenvía el mensaje a los destinatarios externos.|Chis está protegido por datos adjuntos seguros. <p> Si los destinatarios externos también tienen directivas de datos adjuntos seguros en su organización, los mensajes reenviados estarán sujetos a esas directivas.|
|

El análisis de datos adjuntos seguros tiene lugar en la misma región en la que residen los datos de Microsoft 365. Para obtener más información acerca de la geografía del centro de datos, consulte [¿dónde están los datos ubicados?](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> Las siguientes características se encuentran en la configuración global de las directivas de datos adjuntos seguros del centro de seguridad & cumplimiento, pero estas opciones están habilitadas o deshabilitadas globalmente, y no requieren directivas de datos adjuntos seguros:
>
> - [ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md).
>
> - [Documentos seguros en Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Configuración de la Directiva de datos adjuntos seguros

En esta sección se describe la configuración en directivas de datos adjuntos seguros:

- **Datos adjuntos seguros respuesta de malware desconocida** : esta opción controla la acción para el análisis de malware de datos adjuntos seguros en mensajes de correo electrónico. En la tabla siguiente se describen las opciones disponibles:

  ****

  |Opción|Efecto|Se usa cuando se desea:|
  |---|---|---|
  |**Desactivar**|Datos adjuntos seguros no se examinan los datos adjuntos de malware. La [protección antimalware en EOP](anti-malware-protection.md)sigue examinando los mensajes en busca de malware.|Desactivar el análisis para los destinatarios seleccionados. <p> Evitar retrasos innecesarios en el correo interno de enrutamiento. <p> **Esta opción no se recomienda para la mayoría de los usuarios. Solo debe usar esta opción para desactivar el examen de datos adjuntos seguros para los destinatarios que solo reciben mensajes de remitentes de confianza.**|
  |**Monitor**|Entrega los mensajes con datos adjuntos y, a continuación, realiza un seguimiento de lo que ocurre con malware detectado. <p> La entrega de mensajes seguros puede retrasarse debido al análisis de datos adjuntos seguros.|Vea dónde se detecta el malware detectado en su organización.|
  |**Bloquear**|Impide la entrega de mensajes con datos adjuntos de malware detectados. <p> Los mensajes se [ponen en cuarentena](manage-quarantined-messages-and-files.md) donde solo los administradores (no usuarios finales) pueden revisar, liberar o eliminar los mensajes. <p> Bloquea automáticamente las instancias futuras de los mensajes y datos adjuntos. <p> La entrega de mensajes seguros puede retrasarse debido al análisis de datos adjuntos seguros.|Protege a su organización de ataques repetidos con los mismos datos adjuntos de malware. <p> Este es el valor predeterminado y el valor recomendado en las directivas de seguridad estándar y estrictas [preestablecidas](preset-security-policies.md).|
  |**Replace**|Quita los datos adjuntos de malware detectados. <p> Notifica a los destinatarios que se han quitado los datos adjuntos. <p>  Los mensajes se [ponen en cuarentena](manage-quarantined-messages-and-files.md) donde solo los administradores (no usuarios finales) pueden revisar, liberar o eliminar los mensajes. <p> La entrega de mensajes seguros puede retrasarse debido al análisis de datos adjuntos seguros.|Eleva la visibilidad a los destinatarios de que se quitaron los datos adjuntos debido al malware detectado.|
  |**Entrega dinámica**|Entrega los mensajes inmediatamente, pero reemplaza los datos adjuntos con marcadores de posición hasta que se complete el análisis de datos adjuntos seguros. <p> Para obtener más información, consulte la sección [directivas de entrega dinámica en datos adjuntos seguros](#dynamic-delivery-in-safe-attachments-policies) , más adelante en este tema.|Evitar retrasos en los mensajes al proteger a los destinatarios de archivos malintencionados <br/> <br/> Permitir a los destinatarios obtener una vista previa de los datos adjuntos en modo seguro mientras se lleva a cabo el análisis|
  |

- **Redirigir datos adjuntos en detección: habilitar redirección** y **enviar los datos adjuntos a la siguiente dirección de correo electrónico** : para las acciones **bloquear** , **supervisar** o **reemplazar** , envíe mensajes que contengan datos adjuntos de malware a la dirección de correo electrónico interna o externa especificada para el análisis y la investigación.

  La recomendación para la configuración de directivas estándar y estricta es habilitar la redirección. Para obtener más información, consulte [configuración de datos adjuntos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).

- **Aplicar la selección anterior si el análisis de malware para archivos adjuntos se agota el tiempo de espera o error** : la acción especificada por la **respuesta de malware de datos adjuntos seguros** no se realiza en los mensajes, incluso cuando no se completa el análisis de datos adjuntos seguros. Seleccione siempre esta opción si selecciona **Habilitar redirección**. De lo contrario, los mensajes podrían perderse.

- **Filtros de destinatarios** : debe especificar las condiciones y excepciones de destinatarios que determinan a quién se aplica la Directiva. Puede usar estas propiedades para las condiciones y excepciones:

  - **El destinatario es**
  - **El dominio del destinatario es**
  - **El destinatario es un miembro de**

  Solo se puede usar una condición o excepción una vez, pero la condición o excepción puede contener varios valores. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_ ). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_ ).

- **Prioridad** : Si crea varias directivas, puede especificar el orden en que se aplican. Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

  Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Directivas de entrega dinámica en datos adjuntos seguros

> [!NOTE]
> La entrega dinámica solo funciona para buzones de Exchange Online.

La acción de entrega dinámica en las directivas de datos adjuntos seguros pretende eliminar los retrasos de entrega de correo electrónico que puedan estar causados por el análisis de datos adjuntos seguros. El cuerpo del mensaje de correo electrónico se entrega al destinatario con un marcador de posición para cada uno de los datos adjuntos. El marcador de posición permanece hasta que los datos adjuntos se encuentran seguros y los datos adjuntos se pueden abrir o descargar.

Si se detecta que los datos adjuntos son malintencionados, el mensaje se pone en cuarentena. Solo los administradores (no los usuarios finales) pueden revisar, liberar o eliminar mensajes que se pusieron en cuarentena mediante el análisis de datos adjuntos seguros. Para obtener más información, consulte [Manage Quarantined messages and files as a admin](manage-quarantined-messages-and-files.md).

La mayoría de los PDF y los documentos de Office se pueden mostrar como una vista previa en modo seguro mientras está en curso el análisis de datos adjuntos seguros. Si los datos adjuntos no son compatibles con el previsualizador de entrega dinámico, los destinatarios verán un marcador de posición para los datos adjuntos hasta que se complete el análisis de datos adjuntos seguros.

Si está usando un dispositivo móvil y los PDF no se representan en el previsualizador de entrega dinámico en el dispositivo móvil, intente abrir el mensaje en Outlook en la web (anteriormente conocido como Outlook Web App) mediante el explorador móvil.

Estas son algunas consideraciones para los mensajes reenviados y la entrega dinámica:

- Si el destinatario reenviado está protegido por una directiva de datos adjuntos seguros que usa la opción de entrega dinámica, el destinatario verá el marcador de posición, con la capacidad de obtener una vista previa de los archivos compatibles.

- Si el destinatario reenviado no está protegido por una directiva de datos adjuntos seguros, el mensaje y los datos adjuntos se entregarán sin los marcadores de posición de datos adjuntos o los datos adjuntos de datos adjuntos seguros.

Hay escenarios donde la entrega dinámica no puede reemplazar los datos adjuntos en los mensajes. Entre estos escenarios se incluyen lo siguientes:

- Mensajes en carpetas públicas.

- Mensajes que se redirigen hacia fuera y después al buzón de un usuario mediante reglas personalizadas.

- Mensajes que se mueven (de forma automática o manual) fuera de los buzones de la nube a otras ubicaciones, incluidas las carpetas de archivo.

- Mensajes eliminados.

- La carpeta de búsqueda del buzón de correo del usuario se encuentra en estado de error.

- Organizaciones de Exchange online donde exclaimer está habilitado. Para solucionarlo, vea [KB4014438](https://support.microsoft.com/help/4014438).

- [S/MIME)](s-mime-for-message-signing-and-encryption.md) mensajes cifrados.

- Ha configurado la acción de entrega dinámica en una directiva de datos adjuntos seguros, pero el destinatario no admite la entrega dinámica (por ejemplo, el destinatario es un buzón de correo en una organización de Exchange local). Sin embargo, los [vínculos seguros de Microsoft defender para Office 365](set-up-atp-safe-links-policies.md) pueden analizar datos adjuntos de archivos de Office que contienen direcciones URL (dependiendo de cómo esté configurada la [configuración global de los vínculos seguros](configure-global-settings-for-safe-links.md) ).

## <a name="submitting-files-for-malware-analysis"></a>Enviar archivos para el análisis de malware

- Si recibe un archivo que quiere enviar a Microsoft para su análisis, vea [Enviar malware y no malware a Microsoft para su análisis](submitting-malware-and-non-malware-to-microsoft-for-analysis.md).

- Si recibe un mensaje de correo electrónico (con o sin datos adjuntos) que desea enviar a Microsoft para su análisis, vea [Informe de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).
