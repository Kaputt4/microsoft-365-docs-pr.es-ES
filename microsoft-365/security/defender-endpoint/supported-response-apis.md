---
title: Api de respuesta admitidas de Microsoft Defender para puntos de conexión
description: Obtenga información sobre las llamadas específicas de Microsoft Defender para api de extremo relacionadas con la respuesta.
keywords: apis de respuesta, api de gráfico, api admitidas, actor, alertas, dispositivo, usuario, dominio, ip, archivo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: dc5f55f760f4cb291050962fdb493ddd135c0df0
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2021
ms.locfileid: "53623089"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a>Api de consulta de extremo admitidas de Microsoft Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!TIP]
> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-supported-response-apis-abovefoldlink)

Obtenga información sobre las llamadas API relacionadas con la respuesta admitidas que puede ejecutar y detalles como los encabezados de solicitud necesarios y la respuesta esperada de las llamadas.

## <a name="in-this-section"></a>En esta sección
Tema | Descripción
:---|:---
Recopilar paquete de investigación | Ejecute esta API para recopilar un paquete de investigación desde un dispositivo.
Aislar dispositivo | Ejecute esta API para aislar un dispositivo de la red.
Unisolate device | Quita un dispositivo del aislamiento. 
Restringir la ejecución de código | Ejecute esta API para contener un ataque deteniendo procesos malintencionados. También puedes bloquear un dispositivo e impedir que se ejecuten los intentos posteriores de programas potencialmente malintencionados.
Ejecución de código sin restricto | Ejecute esto para revertir la restricción de la directiva de aplicaciones después de comprobar que el dispositivo en peligro se ha corregido.
Ejecutar examen antivirus | Inicie de forma remota un examen antivirus para ayudar a identificar y corregir malware que podría estar presente en un dispositivo en peligro.
Detener y poner en cuarentena un archivo |  Ejecute esta llamada para detener la ejecución de procesos, poner en cuarentena archivos y eliminar la persistencia, como las claves del Registro.
Ejemplo de solicitud | Ejecute esta llamada para solicitar una muestra de un archivo desde un dispositivo específico. El archivo se recopilará desde el dispositivo y se cargará en un almacenamiento seguro.
Bloquear archivo | Ejecute esta API para evitar la propagación posterior de un ataque en su organización mediante la prohibición de archivos potencialmente malintencionados o malware sospechoso. 
Desbloquear archivo | Permitir que un archivo se ejecute en la organización mediante Antivirus de Microsoft Defender.
Obtener EL URI de SAS del paquete | Ejecute esta API para obtener un URI que permita descargar un paquete de investigación.
Obtener objeto MachineAction | Ejecute esta API para obtener el objeto MachineAction.
Obtener colección MachineActions | Ejecute esto para obtener la colección MachineAction.
Obtener colección FileActions | Ejecute esta API para obtener la colección FileActions.
Obtener objeto FileMachineAction | Ejecute esta API para obtener el objeto FileMachineAction.
Obtener colección FileMachineActions | Ejecute esta API para obtener la colección FileMachineAction.
