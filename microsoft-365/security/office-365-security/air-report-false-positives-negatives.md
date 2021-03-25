---
title: Cómo notificar falsos positivos o falsos negativos después de una investigación automatizada en Microsoft Defender para Office 365
description: ¿Se ha detectado algo perdido o incorrecto por AIR en Microsoft Defender para Office 365? Obtenga información sobre cómo enviar falsos positivos o falsos negativos a Microsoft para su análisis.
keywords: automatizado, investigación, alerta, desencadenador, acción, corrección, falso positivo, falso negativo
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.prod: m365-security
ms.date: 01/29/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 4476578939f2ece90c638c919c7e4d134ea2d9ec
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207502"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Cómo notificar falsos positivos/negativos en capacidades automatizadas de investigación y respuesta

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Si las capacidades de investigación y respuesta [automatizadas (AIR) en Office 365](automated-investigation-response-office.md) no se detectaron correctamente o no detectaron algo, hay pasos que el equipo de operaciones de seguridad puede seguir para solucionarlo. Estas acciones incluyen:

- [Notificar un falso positivo/negativo a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Ajustar alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (si es necesario); y
- [Deshacer acciones de corrección que se han realizado](#undo-a-remediation-action).

Use este artículo como guía.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Notificar un falso positivo/negativo a Microsoft para su análisis

Si AIR en Microsoft Defender para Office 365 perdió un mensaje de correo electrónico, un archivo adjunto de correo electrónico, una dirección URL en un mensaje de correo electrónico o una dirección URL en un archivo de Office, puede enviar correo no deseado sospechoso, phish, direcciones URL y archivos a Microsoft para el examen [de Office 365](admin-submission.md).

También puede enviar [un archivo a Microsoft para el análisis de malware.](https://www.microsoft.com/wdsi/filesubmission)

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Ajustar una alerta para evitar que los falsos positivos se repitan

Si una alerta se desencadena por uso legítimo o la alerta es inexacta, puede administrar [alertas en el portal de Cloud App Security](/cloud-app-security/managing-alerts).

Si su organización usa [Microsoft Defender](/windows/security/threat-protection) para endpoint además de Office 365 y un archivo, dirección IP, dirección URL o dominio se trata como malware en un dispositivo, aunque sea seguro, puede crear un indicador personalizado con una acción ["Permitir"](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)para el dispositivo .

## <a name="undo-a-remediation-action"></a>Deshacer una acción de corrección

En la mayoría de los casos, si se ha realizado una acción de corrección en un mensaje de correo electrónico, datos adjuntos de correo electrónico o una dirección URL, y el elemento en realidad no es una amenaza, el equipo de operaciones de seguridad puede deshacer la acción de corrección y tomar medidas para evitar que el falso positivo se repita. Puede usar el Explorador [de amenazas](#undo-an-action-using-threat-explorer) o la pestaña Acciones para una [investigación para](#undo-an-action-in-the-action-center) deshacer una acción.

> [!IMPORTANT]
> Asegúrese de que tiene los permisos necesarios antes de intentar realizar las siguientes tareas.

### <a name="undo-an-action-using-threat-explorer"></a>Deshacer una acción con el Explorador de amenazas

Con el Explorador de amenazas, el equipo de operaciones de seguridad puede encontrar un correo electrónico afectado por una acción y potencialmente deshacer la acción.

|Escenario|Opciones de deshacer|Más información|
|---|---|---|
|Un mensaje de correo electrónico se enrutó a la carpeta correo no deseado de un usuario|- Mover el mensaje a la carpeta Elementos eliminados del usuario<br/>- Mover el mensaje a la Bandeja de entrada del usuario<br/>- Eliminar el mensaje|[Buscar e investigar correo electrónico malintencionado que se entregó en Office 365](investigate-malicious-email-that-was-delivered.md)|
|Se ha puesto en cuarentena un mensaje de correo electrónico o un archivo|- Liberar el correo electrónico o el archivo<br/>- Eliminar el correo electrónico o el archivo|[Administrar mensajes en cuarentena como administrador](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a>Deshacer una acción en el Centro de acciones

En el Centro de acciones, puede ver las acciones de corrección que se realizaron y potencialmente deshacer la acción.

1. Vaya al Centro de seguridad de Microsoft 365 ( <https://security.microsoft.com> ).
2. En el panel de navegación, seleccione **Centro de acciones**.
3. Seleccione la **pestaña** Historial para ver la lista de acciones completadas.
4. Seleccione un elemento. Se abre el panel desplegable.
5. En el panel desplegable, seleccione **Deshacer**. (Solo las acciones que se pueden deshacer tendrán **un botón Deshacer).**

## <a name="see-also"></a>Vea también

- [Microsoft Defender para Office 365](defender-for-office-365.md)
- [Investigaciones automatizadas en Microsoft Defender para Office 365](office-365-air.md)
