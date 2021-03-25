---
title: Tomar medidas sobre los resultados avanzados de consulta de búsqueda en Microsoft Threat Protection
description: Abordar rápidamente las amenazas y los activos afectados en los resultados avanzados de la consulta de búsqueda
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, atp de microsoft defender, búsqueda de wdatp, consulta, telemetría, detecciones personalizadas, esquema, kusto, evitar el tiempo de espera, líneas de comandos, id. de proceso
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 79d720a8b996f826548b79834e5d5c2048e28c2b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075451"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Realizar acciones en los resultados avanzados de la consulta de búsqueda

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Puede contener rápidamente amenazas o solucionar activos en peligro que encuentre en la búsqueda avanzada [mediante](advanced-hunting-overview.md) opciones de acción eficaces y completas. Con estas opciones, puede:

- Realizar varias acciones en dispositivos
- Archivos en cuarentena

## <a name="required-permissions"></a>Permisos necesarios

Para poder tomar medidas a través de la búsqueda avanzada, necesita un rol en Defender for Endpoint con permisos para enviar acciones de corrección [en dispositivos](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options). Si no puede tomar medidas, póngase en contacto con un administrador global para obtener el siguiente permiso:

*Acciones de corrección activas > administración de amenazas y vulnerabilidades: control de corrección*

## <a name="take-various-actions-on-devices"></a>Realizar varias acciones en dispositivos

Puede realizar las siguientes acciones en dispositivos identificados por la `DeviceId` columna en los resultados de la consulta:

- Aislar dispositivos afectados para contener una infección o evitar que los ataques se muevan lateralmente
- Recopilar paquete de investigación para obtener más información forense
- Ejecutar un examen antivirus para buscar y eliminar amenazas con las últimas actualizaciones de inteligencia de seguridad
- Iniciar una investigación automatizada para comprobar y corregir las amenazas en el dispositivo y posiblemente otros dispositivos afectados
- Restringir la ejecución de aplicaciones solo a archivos ejecutables firmados por Microsoft, lo que impide la actividad de amenaza posterior a través de malware u otros ejecutables que no son de confianza

Para obtener más información sobre cómo se realizan estas acciones de respuesta a través de Defender for Endpoint, lea sobre las [acciones de respuesta en dispositivos](respond-machine-alerts.md).

## <a name="quarantine-files"></a>Archivos en cuarentena

Puede implementar la acción *de cuarentena* en los archivos para que se pongan automáticamente en cuarentena cuando se encuentren. Al seleccionar esta acción, puede elegir entre las siguientes columnas para identificar qué archivos de los resultados de la consulta se ponen en cuarentena:

- `SHA1` — En la mayoría de las tablas de búsqueda avanzadas, este es el SHA-1 del archivo que se vio afectado por la acción grabada. Por ejemplo, si se copia un archivo, este sería el archivo copiado.
- `InitiatingProcessSHA1` — En la mayoría de las tablas de búsqueda avanzadas, este es el archivo responsable de iniciar la acción grabada. Por ejemplo, si se inicia un proceso secundario, este sería el proceso primario. 
- `SHA256` — Este es el equivalente SHA-256 del archivo identificado por la `SHA1` columna.
- `InitiatingProcessSHA256` — Este es el equivalente SHA-256 del archivo identificado por la `InitiatingProcessSHA1` columna.

Para obtener más información sobre cómo se toman las acciones de cuarentena y cómo se pueden restaurar los archivos, lea acerca de las [acciones de respuesta en los archivos](respond-file-alerts.md).

>[!NOTE]
>Para buscar archivos y ponerlos en cuarentena, los resultados de la consulta también deben incluir `DeviceId` valores como identificadores de dispositivo.  

## <a name="take-action"></a>Tomar medidas

Para realizar cualquiera de las acciones descritas, seleccione uno o más registros en los resultados de la consulta y, a continuación, **seleccione Realizar acciones**. Un asistente le guiará a través del proceso de selección y envío de las acciones preferidas.

![Imagen del registro seleccionado con panel para inspeccionar el registro](images/ah-take-actions.png)

## <a name="review-actions-taken"></a>Revisar acciones realizadas

Cada acción se registra individualmente en el centro de acciones, en **Historial del centro** de acciones (  >   [security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)). Vaya al centro de acciones para comprobar el estado de cada acción.
 
## <a name="related-topics"></a>Temas relacionados

- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Entender el esquema](advanced-hunting-schema-reference.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Introducción a las detecciones personalizadas](overview-custom-detections.md)
