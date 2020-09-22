---
title: Controlar falsos positivos o falsos negativos en AIR en la protección contra amenazas de Microsoft
description: ¿Perdió o se detectó un error por aire en la protección contra amenazas de Microsoft? Obtenga información sobre cómo enviar falsos positivos o falsos negativos a Microsoft para su análisis.
keywords: automatizado, investigación, alerta, desencadenador, acción, corrección, falso positivo, falso negativo
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: 84d2a71f715c31560f6376464bf9da25cc8d58b1
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198636"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Controlar falsos positivos/negativos en capacidades automatizadas de investigación y respuesta

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Protección contra amenazas de Microsoft

¿Las [capacidades automatizadas de investigación y respuesta](mtp-autoir.md) en Microsoft Threat Protection no se han detectado o no detectan nada correctamente? Hay pasos que puede llevar a cabo para solucionarlo. Puede:

- [Informar de un falso positivo/negativo a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);

- [Ajustar las alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (si es necesario); y 

- [Deshacer las acciones de corrección que se tomaron en los dispositivos](#undo-a-remediation-action-that-was-taken-on-a-device). 

Use este artículo como guía. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Informar de un falso positivo/negativo a Microsoft para su análisis

|El elemento perdió o no se detectó correctamente |Servicio  |Qué hacer  |
|---------|---------|---------|
|-Mensaje de correo electrónico <br/>-Datos adjuntos de correo electrónico <br/>-URL en un mensaje de correo electrónico<br/>-URL en un archivo de Office      |[Protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[Enviar un correo no deseado, phish, direcciones URL y archivos sospechosos a Microsoft para su análisis](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|Archivo o aplicación en un dispositivo    |[Protección contra amenazas avanzada de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection)         |[Enviar un archivo a Microsoft para el análisis de malware](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Ajustar una alerta para evitar que se repitan falsos positivos

|Escenario |Servicio |Qué hacer |
|--------|--------|--------|
|-El uso legítimo desencadena una alerta <br/>-Una alerta no es precisa    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> o <br/>[Detección de amenazas avanzadas de Azure](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Administrar alertas en Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|Un archivo, una dirección IP, una dirección URL o un dominio se trata como malware en un dispositivo, aunque sea seguro|[Protección contra amenazas avanzada de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) |[Crear un indicador personalizado con una acción "permitir"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Deshacer una acción de corrección que se ha realizado en un dispositivo

Si se realizó una acción de corrección en un dispositivo (como un dispositivo de Windows 10) y el elemento realmente no es una amenaza, el equipo de operaciones de seguridad puede deshacer la acción de corrección en el [centro de actividades](mtp-action-center.md).

> [!IMPORTANT]
> Asegúrese de que tiene los [permisos necesarios](mtp-action-center.md#required-permissions-for-action-center-tasks) antes de intentar realizar la siguiente tarea.

1. Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión. 

2. En el panel de navegación, elija **Centro de actividades**. 

3. En la ficha **historial** , seleccione la acción que desea deshacer. Se abrirá un control flotante.<br/>
    > [!TIP]
    > Use filtros para restringir la lista de resultados. 

4. En el control flotante del elemento seleccionado, seleccione **abrir página de investigación**.

5. En la vista detalles de la investigación, seleccione la ficha **acciones** .

6. Seleccione un elemento que tenga el estado **completado**y busque un vínculo, como **aprobado**, en la columna **decisiones** . Se abrirá un control flotante con más detalles sobre la acción.

7. Para deshacer la acción, seleccione **eliminar corrección**.

## <a name="see-also"></a>Vea también

- [Ver los detalles y los resultados de una investigación automatizada](mtp-autoir-results.md)
- [Búsqueda proactiva de amenazas con la búsqueda avanzada en la Protección contra amenazas de Microsoft](advanced-hunting-overview.md)
