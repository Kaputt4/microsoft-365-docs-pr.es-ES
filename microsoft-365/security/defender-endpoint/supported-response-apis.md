---
title: API de respuesta de Microsoft Defender para punto de conexión admitidas
description: Obtenga información sobre las llamadas API Microsoft Defender para punto de conexión específicas relacionadas con la respuesta.
keywords: response apis, graph api, supported apis, actor, alerts, device, user, domain, ip, file
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.custom: api
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 9086bae05ecfcea2bd055de23137fbe147e77be4
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68221420"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a>API de consulta de Microsoft Defender para punto de conexión admitidas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> [!TIP]
> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-supported-response-apis-abovefoldlink)

Obtenga información sobre las llamadas API compatibles relacionadas con la respuesta que puede ejecutar y detalles como los encabezados de solicitud necesarios y la respuesta esperada de las llamadas.

## <a name="in-this-section"></a>En esta sección

<br>

****

|Tema|Descripción|
|---|---|
|Recopilar el paquete de investigación|Ejecute esta API para recopilar un paquete de investigación de un dispositivo.|
|Aislar el dispositivo|Ejecute esta API para aislar un dispositivo de la red.|
|Dispositivo unisolate|Quite un dispositivo del aislamiento.|
|Restringir la ejecución del código|Ejecute esta API para contener un ataque mediante la detención de procesos malintencionados. También puede bloquear un dispositivo e impedir que se ejecuten intentos posteriores de programas potencialmente malintencionados.|
|Anulación de la ejecución del código|Ejecute esto para revertir la restricción de la directiva de aplicaciones después de comprobar que el dispositivo en peligro se ha corregido.|
|Ejecutar examen de antivirus|Inicie de forma remota un examen antivirus para ayudar a identificar y corregir el malware que podría estar presente en un dispositivo en peligro.|
|Detener y poner en cuarentena un archivo|Ejecute esta llamada para detener la ejecución de procesos, poner en cuarentena los archivos y eliminar la persistencia, como las claves del Registro.|
|Solicitar ejemplo|Ejecute esta llamada para solicitar un ejemplo de un archivo desde un dispositivo específico. El archivo se recopilará del dispositivo y se cargará en un almacenamiento seguro.|
|Bloquear archivo|Ejecute esta API para evitar la propagación de un ataque en su organización mediante la prohibición de archivos potencialmente malintencionados o sospechas de malware.|
|Desbloquear archivo|Permitir la ejecución de un archivo en la organización mediante Microsoft Defender Antivirus.|
|Obtención del URI de SAS del paquete|Ejecute esta API para obtener un URI que permita descargar un paquete de investigación.|
|Get MachineAction (objeto)|Ejecute esta API para obtener el objeto MachineAction.|
|Obtención de la colección MachineActions|Ejecute esta opción para obtener la colección MachineAction.|
|Obtención de la colección FileActions|Ejecute esta API para obtener la colección FileActions.|
|Obtención del objeto FileMachineAction|Ejecute esta API para obtener el objeto FileMachineAction.|
|Obtención de la colección FileMachineActions|Ejecute esta API para obtener la colección FileMachineAction.|
|
