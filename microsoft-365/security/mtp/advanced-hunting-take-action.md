---
title: Tomar medidas sobre los resultados de la consulta de búsqueda avanzada en Microsoft 365 Defender
description: Abordar rápidamente las amenazas y los activos afectados en los resultados de la consulta de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, tomar medidas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 9e8ad544cfe17d0d8e5c895e208b42ec56555565
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932183"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Tomar medidas en los resultados de consulta de búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Puede contener rápidamente amenazas o solucionar activos comprometidos que encuentre en la búsqueda avanzada mediante opciones de acción eficaces y completas. [](advanced-hunting-overview.md) Con estas opciones, puede:

- Realizar diversas acciones en dispositivos
- Cuarentena de archivos

## <a name="required-permissions"></a>Permisos necesarios
Para poder tomar medidas a través de la búsqueda avanzada, necesita un rol en Microsoft Defender para Endpoint con permisos para enviar acciones de corrección [en dispositivos.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options) Si no puede tomar medidas, póngase en contacto con un administrador global para obtener el siguiente permiso:

*Acciones de corrección activas > administración de amenazas y vulnerabilidades: control de corrección*

## <a name="take-various-actions-on-devices"></a>Realizar diversas acciones en dispositivos
Puede realizar las siguientes acciones en dispositivos identificados por la `DeviceId` columna en los resultados de la consulta:

- Aislar los dispositivos afectados para contener una infección o evitar que los ataques se muevan lateralmente
- Recopilar el paquete de investigación para obtener más información forense
- Ejecutar un examen antivirus para buscar y quitar amenazas con las últimas actualizaciones de inteligencia de seguridad
- Iniciar una investigación automatizada para comprobar y corregir las amenazas en el dispositivo y, posiblemente, en otros dispositivos afectados
- Restringir la ejecución de la aplicación solo a archivos ejecutables firmados por Microsoft, evitando la actividad de amenaza posterior a través de malware u otros archivos ejecutables que no son de confianza

Para obtener más información sobre cómo se realizan estas acciones de respuesta a través de Microsoft Defender para endpoint, lea sobre las [acciones de respuesta en los dispositivos.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
   
## <a name="quarantine-files"></a>Cuarentena de archivos
Puedes implementar la acción *de cuarentena* en los archivos para que se pongan automáticamente en cuarentena cuando se encuentren. Al seleccionar esta acción, puede elegir entre las siguientes columnas para identificar qué archivos de los resultados de la consulta se ponen en cuarentena:

- `SHA1` — En la mayoría de las tablas de búsqueda avanzadas, este es el SHA-1 del archivo que se ha visto afectado por la acción grabada. Por ejemplo, si se copió un archivo, este sería el archivo copiado.
- `InitiatingProcessSHA1` — En la mayoría de las tablas de búsqueda avanzadas, este es el archivo responsable de iniciar la acción grabada. Por ejemplo, si se inicia un proceso secundario, este sería el proceso primario. 
- `SHA256` Es el equivalente SHA-256 del archivo identificado por la `SHA1` columna.
- `InitiatingProcessSHA256` Es el equivalente SHA-256 del archivo identificado por la `InitiatingProcessSHA1` columna.

Para obtener más información sobre cómo se toman las acciones de cuarentena y cómo se pueden restaurar los archivos, lea acerca de [las acciones de respuesta en los archivos.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)

>[!NOTE]
>Para localizar archivos y ponerlos en cuarentena, los resultados de la consulta también deben incluir `DeviceId` valores como identificadores de dispositivo.  

## <a name="take-action"></a>Tomar medidas
Para realizar cualquiera de las acciones descritas, seleccione uno o más registros en los resultados de la consulta y, a continuación, **seleccione Realizar acciones.** Un asistente le guiará a través del proceso de selección y envío de las acciones preferidas.

![Imagen del registro seleccionado con panel para inspeccionar el registro](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>Revisar las acciones realizadas
Cada acción se registra individualmente en el centro [de acciones en](mtp-action-center.md) Historial **del** centro de acciones  >   ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)). Vaya al centro de acciones para comprobar el estado de cada acción.
 
## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Introducción al centro de actividades](mtp-action-center.md)
