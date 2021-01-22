---
title: Controlar falsos positivos o falsos negativos en AIR en Microsoft 365 Defender
description: ¿Se ha detectado algo perdido o detectado incorrectamente por AIR en Microsoft 365 Defender? Obtenga información sobre cómo enviar falsos positivos o falsos negativos a Microsoft para su análisis.
keywords: automatizado, investigación, alerta, desencadenador, acción, corrección, falso positivo, falso negativo
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/16/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: dbef240e28258d1ac4000c05538d0ce073a9d910
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930359"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Controlar falsos positivos/negativos en las capacidades automatizadas de investigación y respuesta

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

¿Las [capacidades automatizadas de](mtp-autoir.md) investigación y respuesta en Microsoft 365 Defender no detectaron o detectaron algo incorrectamente? Hay pasos que puede seguir para corregirlo. Puede:

- [Notificar un falso positivo/negativo a Microsoft;](#report-a-false-positivenegative-to-microsoft-for-analysis)

- [Ajustar las alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (si es necesario); y 

- [Deshacer acciones de corrección realizadas en dispositivos.](#undo-a-remediation-action-that-was-taken-on-a-device) 

Use este artículo como guía. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Notificar un falso positivo/negativo a Microsoft para su análisis

|Elemento perdido o detectado incorrectamente |Servicio  |Qué hacer  |
|---------|---------|---------|
|- Mensaje de correo electrónico <br/>- Datos adjuntos de correo electrónico <br/>- Dirección URL en un mensaje de correo electrónico<br/>- Dirección URL en un archivo de Office      |[Microsoft Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[Enviar correos sospechosos de correo no deseado, phishing, direcciones URL y archivos a Microsoft para su análisis](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|Archivo o aplicación en un dispositivo    |[Microsoft Defender para punto de conexión](https://docs.microsoft.com/windows/security/threat-protection)         |[Enviar un archivo a Microsoft para el análisis de malware](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Ajustar una alerta para evitar que los falsos positivos se repitan

|Escenario |Servicio |Qué hacer |
|--------|--------|--------|
|- Una alerta se desencadena por uso legítimo <br/>- Una alerta no es precisa    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> Otra posibilidad: <br/>[Detección avanzada de amenazas de Azure](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Administrar alertas en el portal de Cloud App Security](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|Un archivo, dirección IP, dirección URL o dominio se trata como malware en un dispositivo, aunque sea seguro|[Microsoft Defender para punto de conexión](https://docs.microsoft.com/windows/security/threat-protection) |[Crear un indicador personalizado con una acción "Permitir"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Deshacer una acción de corrección que se ha realizado en un dispositivo

Si se ha realizado una acción de corrección en un dispositivo (como un dispositivo windows 10) y el elemento no es realmente una amenaza, el equipo de operaciones de seguridad puede deshacer la acción de corrección en el Centro de [actividades.](mtp-action-center.md)

> [!IMPORTANT]
> Asegúrese de que tiene los [permisos necesarios antes](mtp-action-center.md#required-permissions-for-action-center-tasks) de intentar realizar la siguiente tarea.

1. Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión. 

2. En el panel de navegación, elija **Centro de actividades**. 

3. En la **pestaña** Historial, seleccione una acción que desee deshacer. Se abrirá un menú desplegable.<br/>
    > [!TIP]
    > Use filtros para restringir la lista de resultados. 

4. En el menú desplegable del elemento seleccionado, seleccione **Abrir página de investigación.**

5. En la vista de detalles de la investigación, seleccione la **pestaña** Acciones.

6. Seleccione un elemento que tenga el estado **Completado** y busque un vínculo, como **Aprobado,** en la **columna Decisiones.** Se abrirá un menú desplegable con más detalles sobre la acción.

7. Para deshacer la acción, seleccione **Eliminar corrección.**

## <a name="see-also"></a>Consulte también

- [Ver los detalles y los resultados de una investigación automatizada](mtp-autoir-results.md)
- [Búsqueda proactiva de amenazas con búsqueda avanzada en Microsoft 365 Defender](advanced-hunting-overview.md)
