---
title: Tomar medidas sobre los resultados de la consulta de búsqueda avanzada en Microsoft 365 Defender
description: Abordar rápidamente las amenazas y los recursos afectados en los resultados de la consulta de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, tomar medidas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b7fbe659902bf89023e994f4e1304f25f3934db8
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65097619"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Realizar acciones en los resultados de consultas de búsqueda avanzadas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Puede contener rápidamente amenazas o abordar los recursos en peligro que encuentre en la [búsqueda avanzada](advanced-hunting-overview.md) mediante opciones de acción eficaces y completas. Con estas opciones, puede:

- Realizar varias acciones en los dispositivos
- Archivos de cuarentena

## <a name="required-permissions"></a>Permisos necesarios
Para realizar acciones en los dispositivos mediante la búsqueda avanzada, necesita un rol en Microsoft Defender para punto de conexión con [permisos para enviar acciones de corrección en los dispositivos](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options). Si no puede realizar ninguna acción, póngase en contacto con un administrador global para obtener el permiso siguiente:

*Acciones de corrección activas > Amenaza y administración de vulnerabilidades: control de corrección*

Para tomar medidas en los correos electrónicos a través de la búsqueda avanzada, necesita un rol en Microsoft Defender para Office 365 para [buscar y purgar correos electrónicos](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).

## <a name="take-various-actions-on-devices"></a>Realizar varias acciones en los dispositivos
Puede realizar las siguientes acciones en los dispositivos identificados por la columna en los `DeviceId` resultados de la consulta:

- Aislar los dispositivos afectados para contener una infección o evitar que los ataques se muevan lateralmente
- Recopilación del paquete de investigación para obtener más información forense
- Ejecución de un examen antivirus para buscar y quitar amenazas mediante las últimas actualizaciones de inteligencia de seguridad
- Iniciar una investigación automatizada para comprobar y corregir amenazas en el dispositivo y posiblemente en otros dispositivos afectados
- Restringir la ejecución de aplicaciones solo a archivos ejecutables firmados por Microsoft, lo que impide la actividad de amenazas posterior a través de malware u otros ejecutables que no son de confianza

Para obtener más información sobre cómo se realizan estas acciones de respuesta a través de Microsoft Defender para punto de conexión, [lea sobre las acciones de respuesta en los dispositivos](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).
   
### <a name="quarantine-files"></a>Archivos de cuarentena
Puede implementar la acción de *cuarentena* en los archivos para que se pongan en cuarentena automáticamente cuando se encuentren. Al seleccionar esta acción, puede elegir entre las columnas siguientes para identificar qué archivos de los resultados de la consulta se ponen en cuarentena:

- `SHA1`: en las tablas de búsqueda más avanzadas, esta columna hace referencia al SHA-1 del archivo que se vio afectado por la acción registrada. Por ejemplo, si se copió un archivo, este archivo afectado sería el archivo copiado.
- `InitiatingProcessSHA1`: en las tablas de búsqueda más avanzadas, esta columna hace referencia al archivo responsable de iniciar la acción registrada. Por ejemplo, si se inicia un proceso secundario, este archivo de iniciador formaría parte del proceso primario. 
- `SHA256`: esta columna es el equivalente SHA-256 del archivo identificado por la `SHA1` columna.
- `InitiatingProcessSHA256`: esta columna es el equivalente SHA-256 del archivo identificado por la `InitiatingProcessSHA1` columna.

Para obtener más información sobre cómo se realizan las acciones de cuarentena y cómo se pueden restaurar los archivos, [lea sobre las acciones de respuesta en los archivos](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).

>[!NOTE]
>Para buscar archivos y ponerlos en cuarentena, los resultados de la consulta también deben incluir `DeviceId` valores como identificadores de dispositivo.  

Para realizar cualquiera de las acciones descritas, seleccione uno o varios registros en los resultados de la consulta y, a continuación, seleccione **Realizar acciones**. Un asistente le guiará a través del proceso de selección y envío de las acciones preferidas.

:::image type="content" source="../../media/take-action-multiple.png" alt-text="La opción Realizar acciones en el portal de Microsoft 365 Defender" lightbox="../../media/take-action-multiple.png":::


## <a name="take-various-actions-on-emails"></a>Realizar varias acciones en los correos electrónicos
Además de los pasos de corrección centrados en el dispositivo, también puede realizar algunas acciones en los correos electrónicos de los resultados de la consulta. Seleccione los registros en los que desea realizar una acción, seleccione **Realizar acciones** y, a continuación, en **Elegir acciones**, seleccione la opción que elija de las siguientes opciones:
- `Move to mailbox folder` : seleccione esta opción para mover los mensajes de correo electrónico a la carpeta Elementos no deseados, Bandeja de entrada o Elementos eliminados.

   :::image type="content" source="../../media/advanced-hunting-take-actions-email.png" alt-text="La opción Realizar acciones en el portal de Microsoft 365 Defender" lightbox="../../media/advanced-hunting-take-actions-email.png":::

- `Delete email` : seleccione esta opción para mover mensajes de correo electrónico a la carpeta Elementos eliminados (**eliminación temporal**) o eliminarlos permanentemente (**eliminación rígida**)

   :::image type="content" source="../../media/advanced-hunting-take-actions-email-del.png" alt-text="La opción Realizar acciones en el portal de Microsoft 365 Defender" lightbox="../../media/advanced-hunting-take-actions-email-del.png":::

También puede proporcionar un nombre de corrección y una breve descripción de la acción realizada para realizar un seguimiento sencillo en el historial del centro de acciones. También puede usar el identificador de aprobación para filtrar estas acciones en el centro de acciones. Este identificador se proporciona al final del asistente:

:::image type="content" source="../../media/choose-email-actions-entities.png" alt-text="Asistente para realizar acciones que muestra acciones de selección para entidades" lightbox="../../media/choose-email-actions-entities.png":::

Estas acciones de correo electrónico también se aplican a [las detecciones personalizadas](custom-detections-overview.md) .


## <a name="review-actions-taken"></a>Revisar las acciones realizadas
Cada acción se registra individualmente en el [centro de acción](m365d-action-center.md) en **Centro** >  de **acciónHistoria** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)). Vaya al centro de acciones para comprobar el estado de cada acción.
 
>[!NOTE]
>Es posible que algunas tablas de este artículo no estén disponibles en Microsoft Defender para punto de conexión. [Active Microsoft 365 Defender](m365d-enable.md) para buscar amenazas mediante más orígenes de datos. Para mover los flujos de trabajo de búsqueda avanzados de Microsoft Defender para punto de conexión a Microsoft 365 Defender, siga los pasos descritos en [Migración de consultas de búsqueda avanzadas desde Microsoft Defender para punto de conexión](advanced-hunting-migrate-from-mde.md) .

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Información general del centro de acciones](m365d-action-center.md)
