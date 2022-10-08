---
title: Cómo notificar falsos positivos o falsos negativos después de una investigación automatizada en Microsoft Defender para Office 365
description: ¿Se ha detectado algo extraño o erróneamente por AIR en Microsoft Defender para Office 365? Obtenga información sobre cómo enviar falsos positivos o falsos negativos a Microsoft para su análisis.
keywords: automated, investigation, alert, trigger, action, remediation, false positive, false negative
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
ms.service: microsoft-365-security
ms.date: 01/29/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.subservice: mdo
ms.openlocfilehash: 6a7779ced613f5e6c175c2cd6a7181c2c4a00fa0
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68082887"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Cómo notificar falsos positivos o negativos en funcionalidades automatizadas de investigación y respuesta

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Si [las funcionalidades de investigación y respuesta automatizadas (AIR) en Office 365](automated-investigation-response-office.md) han perdido o detectado algo erróneamente, hay pasos que el equipo de operaciones de seguridad puede realizar para corregirlo. Estas acciones incluyen:

- [Notificar un falso positivo/negativo a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Ajustar alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (si es necesario); Y
- [Deshacer las acciones de corrección que se han realizado](#undo-a-remediation-action).

Use este artículo como guía.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Notificar un falso positivo/negativo a Microsoft para su análisis

Si AIR en Microsoft Defender para Office 365 ha perdido un mensaje de correo electrónico, un archivo adjunto de correo electrónico, una dirección URL en un mensaje de correo electrónico o una dirección URL en un archivo de Office, puede [enviar sospechas de correo no deseado, direcciones URL, direcciones URL y archivos a Microsoft para Office 365 examen](admin-submission.md).

También puede [enviar un archivo a Microsoft para el análisis de malware](https://www.microsoft.com/wdsi/filesubmission).

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Ajuste de una alerta para evitar que los falsos positivos se repitan

Si una alerta se desencadena mediante un uso legítimo o la alerta es inexacta, puede [administrar alertas en el portal de Defender for Cloud Apps](/cloud-app-security/managing-alerts).

Si su organización usa [Microsoft Defender para punto de conexión](/windows/security/threat-protection) además de Office 365 y un archivo, dirección IP, dirección URL o dominio se trata como malware en un dispositivo, aunque sea seguro, puede [crear un indicador personalizado con una acción "Permitir" para el dispositivo](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).

## <a name="undo-a-remediation-action"></a>Deshacer una acción de corrección

En la mayoría de los casos, si se ha realizado una acción de corrección en un mensaje de correo electrónico, datos adjuntos de correo electrónico o dirección URL, y el elemento no es realmente una amenaza, el equipo de operaciones de seguridad puede deshacer la acción de corrección y tomar medidas para evitar que el falso positivo se repita. Puede usar [el Explorador de amenazas](#undo-an-action-using-threat-explorer) o la [pestaña Acciones de una investigación para](#undo-an-action-in-the-action-center) deshacer una acción.

> [!IMPORTANT]
> Asegúrese de que tiene los permisos necesarios antes de intentar realizar las siguientes tareas.

### <a name="undo-an-action-using-threat-explorer"></a>Deshacer una acción mediante el Explorador de amenazas

Con el Explorador de amenazas, el equipo de operaciones de seguridad puede encontrar un correo electrónico afectado por una acción y, potencialmente, deshacer la acción.

|Escenario|Deshacer opciones|Más información|
|---|---|---|
|Se enrutó un mensaje de correo electrónico a la carpeta de Email no deseado de un usuario.|<ul><li>Mover el mensaje a la carpeta Elementos eliminados del usuario</li><li>Mover el mensaje a la bandeja de entrada del usuario</li><li>Eliminar el mensaje.</li></ul>|[Busque e investigue el correo electrónico malintencionado que se entregó en Office 365](investigate-malicious-email-that-was-delivered.md)|
|Un mensaje de correo electrónico o un archivo se puso en cuarentena|<ul><li>Liberar el correo electrónico o el archivo</li><li> Eliminar el correo electrónico o el archivo</li></ul>|[Administración de mensajes en cuarentena como administrador](manage-quarantined-messages-and-files.md)|

### <a name="undo-an-action-in-the-action-center"></a>Deshacer una acción en el Centro de acciones

En el Centro de acciones, puede ver las acciones de corrección que se realizaron y, potencialmente, deshacer la acción.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya al Centro de acciones; para ello, seleccione **Centro de acciones**. Para ir directamente al Centro de acciones, use <https://security.microsoft.com/action-center/>.
2. En el Centro de acciones, seleccione la pestaña **Historial** para ver la lista de acciones completadas.
3. Seleccione un elemento. Se abre el panel flotante.
4. En el panel flotante, seleccione **Deshacer**. (Solo las acciones que se pueden deshacer tendrán un botón **Deshacer** ).

## <a name="see-also"></a>Vea también

- [Microsoft Defender para Office 365](defender-for-office-365.md)
- [Investigaciones automatizadas en Microsoft Defender para Office 365](office-365-air.md)
