---
title: Cómo informar de falsos positivos o falsos negativos en Office 365 de investigación y respuesta automatizada
description: ¿Se perdió alguna pérdida o no se detectó correctamente en la protección contra amenazas avanzada de Office 365? Obtenga información sobre cómo enviar falsos positivos o falsos negativos a Microsoft para su análisis.
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
ms.date: 05/15/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 66b81a474ff81df57c0b2a59672b17061f7235cb
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196088"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Cómo informar de falsos positivos/negativos en capacidades automatizadas de investigación y respuesta

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Se aplica a:**
- Protección contra amenazas avanzada de Office 365

¿Las [capacidades de investigación y respuesta automatizadas (Air) de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) pierden o detectaron algo erróneamente? Hay pasos que puede llevar a cabo para solucionarlo. Puede:
- [Informar de un falso positivo/negativo a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Ajustar las alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (si es necesario); y 
- [Deshacer las acciones de corrección que se tomaron](#undo-a-remediation-action). 

Use este artículo como guía. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Informar de un falso positivo/negativo a Microsoft para su análisis

Si Office 365 AIR perdió un mensaje de correo electrónico, un archivo adjunto de correo electrónico, una dirección URL en un mensaje de correo electrónico o una dirección URL en un archivo de Office, puede [Enviar un correo no deseado, phish, direcciones URL y archivos sospechosos a Microsoft para la detección de office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).

También puede [Enviar un archivo a Microsoft para el análisis de malware](https://www.microsoft.com/wdsi/filesubmission).

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Ajustar una alerta para evitar que se repitan falsos positivos

Si una alerta se activa por uso legítimo, o la alerta no es precisa, puede [administrar las alertas en Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).

Si su organización usa la [protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection) , además de Office 365, y un archivo, la dirección IP, la dirección URL o el dominio se trata como malware en un dispositivo, aunque sea seguro, puede [crear un indicador personalizado con una acción "permitir" para el dispositivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).

## <a name="undo-a-remediation-action"></a>Deshacer una acción de corrección

En la mayoría de los casos, si se realizó una acción de corrección en un mensaje de correo electrónico, un archivo adjunto de correo electrónico o una dirección URL, y el elemento no es realmente una amenaza, el equipo de operaciones de seguridad puede deshacer la acción de corrección y tomar medidas para evitar que el falso positivo se repita. Puede usar el [Explorador de amenazas](#undo-an-action-using-threat-explorer) o la [ficha acciones para realizar una investigación](#undo-an-action-using-the-actions-tab-for-an-investigation) y deshacer una acción. 

> [!IMPORTANT]
> Asegúrese de que tiene los permisos necesarios antes de intentar realizar las siguientes tareas.

### <a name="undo-an-action-using-threat-explorer"></a>Deshacer una acción con el explorador de amenazas

Con el explorador de amenazas, el equipo de operaciones de seguridad puede encontrar un correo electrónico afectado por una acción y, potencialmente, deshacer la acción.

****

|Escenario|Opciones de deshacer|Obtén más información|
|---|---|---|
|Un mensaje de correo electrónico se enrutó a la carpeta de correo electrónico no deseado de un usuario|-Mover el mensaje a la carpeta elementos eliminados del usuario<br/>-Mover el mensaje a la bandeja de entrada del usuario <br/>-Eliminar el mensaje|[Buscar e investigar correo electrónico malintencionado que se entregó en Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered)|
|Un mensaje de correo electrónico o un archivo se ha puesto en cuarentena|-Libere el correo electrónico o el archivo <br/>-Eliminar el correo electrónico o el archivo|[Administrar archivos y mensajes en cuarentena como un administrador en Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files)|
|

### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a>Deshacer una acción con la ficha acciones para una investigación

En el centro de actividades, puede ver las acciones de corrección que se han realizado y, potencialmente, deshacer la acción.

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión. Esto le llevará al centro de seguridad & cumplimiento.

2. Vaya a investigaciones de **Administración de amenazas**  >  **Investigations**.

3. En la lista de investigaciones, seleccione el icono **abrir en ventana nueva** junto al identificador de un elemento.

4. Seleccione la ficha **acciones** .

5. Seleccione un elemento que tenga el estado **completado**y busque un vínculo, como **aprobado**, en la columna **decisión** . Se abrirá un control flotante con más detalles sobre la acción.

6. Para deshacer la acción, seleccione **eliminar corrección**.

## <a name="related-articles"></a>Artículos relacionados

[Protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[Introducción al uso de investigación y respuesta automatizadas (AIR) en Office 365](office-365-air.md)
