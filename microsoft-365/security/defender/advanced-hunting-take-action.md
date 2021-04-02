---
title: Realizar acciones en resultados de consulta de búsqueda avanzada en Microsoft 365 Defender
description: Abordar rápidamente las amenazas y los activos afectados en los resultados avanzados de la consulta de búsqueda
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, tomar medidas
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ee35bcc29ef8a283b6b04cb34ab97705d5dd15f4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498224"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Realizar acciones en los resultados avanzados de la consulta de búsqueda

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Puede contener rápidamente amenazas o solucionar activos en peligro que encuentre en la búsqueda avanzada [mediante](advanced-hunting-overview.md) opciones de acción eficaces y completas. Con estas opciones, puede:

- Realizar varias acciones en dispositivos
- Archivos en cuarentena

## <a name="required-permissions"></a>Permisos necesarios
Para poder tomar medidas a través de la búsqueda avanzada, necesita un rol en Microsoft Defender para Endpoint con permisos para enviar acciones de corrección [en dispositivos](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options). Si no puede tomar medidas, póngase en contacto con un administrador global para obtener el siguiente permiso:

*Acciones de corrección activas > administración de amenazas y vulnerabilidades: control de corrección*

## <a name="take-various-actions-on-devices"></a>Realizar varias acciones en dispositivos
Puede realizar las siguientes acciones en dispositivos identificados por la `DeviceId` columna en los resultados de la consulta:

- Aislar dispositivos afectados para contener una infección o evitar que los ataques se muevan lateralmente
- Recopilar paquete de investigación para obtener más información forense
- Ejecutar un examen antivirus para buscar y eliminar amenazas con las últimas actualizaciones de inteligencia de seguridad
- Iniciar una investigación automatizada para comprobar y corregir las amenazas en el dispositivo y posiblemente otros dispositivos afectados
- Restringir la ejecución de aplicaciones solo a archivos ejecutables firmados por Microsoft, lo que impide la actividad de amenaza posterior a través de malware u otros ejecutables que no son de confianza

Para obtener más información sobre cómo se realizan estas acciones de respuesta a través de Microsoft Defender para endpoint, lea acerca de las [acciones de respuesta en dispositivos](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).
   
## <a name="quarantine-files"></a>Archivos en cuarentena
Puede implementar la acción *de cuarentena* en los archivos para que se pongan automáticamente en cuarentena cuando se encuentren. Al seleccionar esta acción, puede elegir entre las siguientes columnas para identificar qué archivos de los resultados de la consulta se ponen en cuarentena:

- `SHA1` — En la mayoría de las tablas de búsqueda avanzadas, este es el SHA-1 del archivo que se vio afectado por la acción grabada. Por ejemplo, si se copia un archivo, este sería el archivo copiado.
- `InitiatingProcessSHA1` — En la mayoría de las tablas de búsqueda avanzadas, este es el archivo responsable de iniciar la acción grabada. Por ejemplo, si se inicia un proceso secundario, este sería el proceso primario. 
- `SHA256` — Este es el equivalente SHA-256 del archivo identificado por la `SHA1` columna.
- `InitiatingProcessSHA256` — Este es el equivalente SHA-256 del archivo identificado por la `InitiatingProcessSHA1` columna.

Para obtener más información sobre cómo se toman las acciones de cuarentena y cómo se pueden restaurar los archivos, lea acerca de las [acciones de respuesta en los archivos](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).

>[!NOTE]
>Para buscar archivos y ponerlos en cuarentena, los resultados de la consulta también deben incluir `DeviceId` valores como identificadores de dispositivo.  

## <a name="take-action"></a>Tomar medidas
Para realizar cualquiera de las acciones descritas, seleccione uno o más registros en los resultados de la consulta y, a continuación, **seleccione Realizar acciones**. Un asistente le guiará a través del proceso de selección y envío de las acciones preferidas.

![Imagen del registro seleccionado con panel para inspeccionar el registro](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>Revisar acciones realizadas
Cada acción se registra individualmente en el centro [de acciones](m365d-action-center.md) en Historial **del centro** de acciones (  >   [security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)). Vaya al centro de acciones para comprobar el estado de cada acción.
 
## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Introducción al Centro de acciones](m365d-action-center.md)
