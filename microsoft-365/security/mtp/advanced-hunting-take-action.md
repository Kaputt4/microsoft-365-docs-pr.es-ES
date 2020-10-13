---
title: Realizar acciones en los resultados de la consulta de búsqueda avanzada en protección contra amenazas de Microsoft
description: Solucionar rápidamente las amenazas y los activos afectados en los resultados de la consulta de búsqueda avanzada
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, emprender acciones
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 7250feffa69cc1a6cc37908a599dff0fab6c5e6c
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429664"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Realizar acciones en los resultados de la consulta de búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Protección contra amenazas de Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Puede contener amenazas o dirigir a los activos en peligro que encuentra en la [búsqueda avanzada](advanced-hunting-overview.md) con opciones de acción potentes y completas. Con estas opciones, puede:

- Realizar diversas acciones en los dispositivos
- Archivos en cuarentena

## <a name="required-permissions"></a>Permisos necesarios
Para poder emprender acciones a través de la búsqueda avanzada, necesita un rol en Microsoft defender ATP con [permisos para enviar acciones de corrección en los dispositivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options). Si no puede emprender ninguna acción, póngase en contacto con un administrador global para obtener el siguiente permiso:

*Acciones de corrección activas > administración de amenazas y vulnerabilidades-control de correcciones*

## <a name="take-various-actions-on-devices"></a>Realizar diversas acciones en los dispositivos
Puede realizar las siguientes acciones en los dispositivos identificados por la `DeviceId` columna de los resultados de la consulta:

- Aislar los dispositivos afectados para que contengan una infección o impedir que los ataques se muevan con posterioridad
- Recopilar el paquete de investigación para obtener más información forense
- Ejecutar un análisis antivirus para buscar y eliminar amenazas con las últimas actualizaciones de inteligencia sobre seguridad
- Iniciar una investigación automatizada para comprobar y corregir las amenazas en el dispositivo y posiblemente en otros dispositivos afectados
- Restringir la ejecución de la aplicación solo a archivos ejecutables firmados por Microsoft, evitando actividades posteriores de amenazas a través de malware u otros ejecutables que no son de confianza

Para obtener más información sobre cómo estas acciones de respuesta se realizan a través de ATP de Microsoft defender, [Lea acerca de las acciones de respuesta en los dispositivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).
   
## <a name="quarantine-files"></a>Archivos en cuarentena
Puede implementar la acción de *cuarentena* en los archivos para que se pongan en cuarentena automáticamente cuando se detecten. Al seleccionar esta acción, puede elegir entre las siguientes columnas para identificar los archivos de los resultados de la consulta que se pondrán en cuarentena:

- `SHA1` (En la mayoría de las tablas de búsqueda avanzadas), es el SHA-1 del archivo que se ha visto afectado por la acción grabada. Por ejemplo, si se ha copiado un archivo, sería el archivo copiado.
- `InitiatingProcessSHA1` (En la mayoría de las tablas de la caza avanzadas), es el archivo responsable de iniciar la acción grabada. Por ejemplo, si se inició un proceso secundario, sería el proceso principal. 
- `SHA256` : Es el equivalente de SHA-256 del archivo identificado por la `SHA1` columna.
- `InitiatingProcessSHA256` : Es el equivalente de SHA-256 del archivo identificado por la `InitiatingProcessSHA1` columna.

Para obtener más información sobre cómo se llevan a cabo las acciones de cuarentena y cómo se pueden restaurar los archivos, [vea acciones de respuesta en los archivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).

>[!NOTE]
>Para buscar archivos y ponerlos en cuarentena, los resultados de la consulta también deben incluir `DeviceId` valores como identificadores de dispositivo.  

## <a name="take-action"></a>Emprender acciones
Para realizar cualquiera de las acciones descritas, seleccione uno o más registros en los resultados de la consulta y, a continuación, seleccione **emprender acciones**. Un asistente le guiará por el proceso de selección y envío de las acciones preferidas.

![Imagen del registro seleccionado con panel para inspeccionar el registro](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>Revisión de las acciones realizadas
Cada acción se registra individualmente en el [centro de actividades](mtp-action-center.md) , en historial del **centro de actividades**  >  **History** ([Security.Microsoft.com/Action-Center/History](https://security.microsoft.com/action-center/history)). Vaya al centro de actividades para comprobar el estado de cada acción.
 
## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Información general del centro de actividades](mtp-action-center.md)
