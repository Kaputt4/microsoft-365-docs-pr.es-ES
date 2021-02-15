---
title: Revisar las amenazas detectadas y actuar al respecto
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Aprende a revisar y administrar las amenazas detectadas por el Antivirus de Microsoft Defender en tus dispositivos Windows 10.
ms.openlocfilehash: 41465cb81850415a7b490b6af7f0ec66c724ca68
ms.sourcegitcommit: 490a65d32b6d656c661c36a2cc8dda03bf6cba77
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588522"
---
# <a name="review-detected-threats-and-take-action"></a>Revisar las amenazas detectadas y actuar al respecto

Tan pronto como se detecta un archivo o software malintencionado, Antivirus de Microsoft Defender lo bloquea y evita que se ejecute. Y con la protección de entrega en la nube activada, las amenazas detectadas recientemente se agregan al motor antivirus y antimalware para que los demás dispositivos y usuarios también estén protegidos.

Antivirus de Microsoft Defender detecta y protege contra los siguientes tipos de amenazas:

- Virus, malware y amenazas basadas en web en dispositivos
- Intentos de suplantación de identidad
- Intentos de robo de datos

Como profesional o administrador de TI, puede ver información sobre las detecciones de amenazas en todos los dispositivos [Windows 10](/mem/intune/enrollment/device-enrollment) inscritos en Intune en el Centro de administración de Microsoft 365. Verá información de resumen, como:

- Cuántos dispositivos necesitan protección antivirus
- Cuántos dispositivos no cumplen las directivas de seguridad
- Cuántas amenazas están activas, mitigadas o resueltas actualmente

Tienes varias opciones para ver información específica sobre dispositivos y detecciones de amenazas:

- La **página Dispositivos activos** en el Centro de administración de Microsoft <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">365.</a> Consulta [Administrar detecciones de amenazas en la página Dispositivos activos](#manage-threat-detections-on-the-active-devices-page) en este artículo.
- La **página Amenazas activas** en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365.</a> Consulta [Administrar detecciones de amenazas en la página Amenazas activas](#manage-threat-detections-on-the-active-threats-page) de este artículo.
- La **página Antivirus** en Microsoft Endpoint <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">Manager.</a> Consulta [Administrar detecciones de amenazas en Microsoft Endpoint Manager](#manage-threat-detections-in-microsoft-endpoint-manager) en este artículo.

Para obtener más información, vea [Amenazas detectadas por el Antivirus de Microsoft Defender.](threats-detected-defender-av.md)

## <a name="manage-threat-detections-on-the-active-devices-page"></a>Administrar detecciones de amenazas en la **página Dispositivos activos**

El siguiente procedimiento se aplica a los clientes que tienen Microsoft 365 Empresa Premium.

1. Vaya al Centro de administración de Microsoft 365 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e inicie sesión.

2. En la página de navegación, seleccione  >  **Dispositivos activos.** Verás una lista de dispositivos activos y detalles, como el estado de protección, el estado de protección antivirus (AV) y el número de amenazas activas detectadas.

3. Selecciona un dispositivo para ver más detalles sobre ese dispositivo y las acciones disponibles. Se abre un control desplegable con recomendaciones y acciones disponibles, como directiva de **actualización,** **antivirus** de actualización, **Ejecutar** examen rápido, Ejecutar **examen completo** y mucho más.

## <a name="manage-threat-detections-on-the-active-threats-page"></a>Administrar detecciones de amenazas en la **página Amenazas activas**

El siguiente procedimiento se aplica a los clientes que tienen Microsoft 365 Empresa Premium. [Los dispositivos con Windows 10 deben estar protegidos](/microsoft-365/business/secure-win-10-pcs) [e inscritos en Intune.](/mem/intune/enrollment/windows-enrollment-methods)

> [!NOTE]
> La **tarjeta antivirus de Microsoft Defender** y la página de amenazas activas se están implantando en fases, por lo que es posible que no tenga acceso inmediato a ellas. 

1. Vaya al Centro de administración de Microsoft 365 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e inicie sesión.

2. En la tarjeta **del Antivirus de Microsoft Defender,** seleccione Ver amenazas **activas.** (Como alternativa, en el panel de navegación, seleccione **Estado**  >  **Amenazas & antivirus).)**

3. En la **página Amenazas activas,** selecciona una amenaza detectada para obtener más información sobre ella. Se abre un menú desplegable con detalles sobre esa amenaza, incluidos los dispositivos afectados.

4. En el menú desplegable, selecciona un dispositivo para ver las acciones disponibles, como la directiva de **actualización,** **actualizar antivirus,** **ejecutar un examen rápido** y mucho más.

## <a name="actions-you-can-take"></a>Acciones que puede realizar

Cuando veas detalles sobre amenazas o dispositivos específicos, verás recomendaciones y una o más acciones que puedes realizar. En la tabla siguiente se describen las acciones que puede ver.<br><br>

| Acción | Descripción |
|--|--|
| Configurar la protección | Las directivas de protección contra amenazas deben configurarse. Seleccione el vínculo para ir a la página de configuración de la directiva.<br><br>¿Necesita ayuda? Consulta [Administrar la seguridad de dispositivos con directivas de seguridad de puntos de conexión en Microsoft Intune.](/mem/intune/protect/endpoint-security-policy) |
| Actualizar directiva | Las directivas de protección antivirus y en tiempo real deben actualizarse o configurarse. Seleccione el vínculo para ir a la página de configuración de directiva.<br><br>¿Necesita ayuda? Consulta [Administrar la seguridad de dispositivos con directivas de seguridad de puntos de conexión en Microsoft Intune.](/mem/intune/protect/endpoint-security-policy) |
| Ejecutar examen rápido | Inicia un examen antivirus rápido en el dispositivo y se centra en las ubicaciones comunes donde se puede registrar malware, como las claves del Registro y las carpetas de inicio de Windows conocidas. |
| Ejecutar examen completo | Inicia un examen antivirus completo en el dispositivo, centrándose en las ubicaciones comunes donde se puede registrar malware e incluyendo todos los archivos y carpetas del dispositivo. Los resultados se envían a [Microsoft Endpoint Manager.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) |
| Actualizar antivirus | Requiere que el dispositivo obtenga actualizaciones [de inteligencia de seguridad](https://go.microsoft.com/fwlink/?linkid=2149926) para la protección antivirus y antimalware. |
| Reiniciar dispositivo | Fuerza el reinicio de un dispositivo Windows 10 en cinco minutos.<br><br>**IMPORTANTE:** El propietario o usuario del dispositivo no se notifica automáticamente del reinicio y podría perder el trabajo no guardado. |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>Administrar detecciones de amenazas en Microsoft Endpoint Manager

Puedes usar Microsoft Endpoint Manager para administrar las detecciones de amenazas. Los dispositivos windows 10 deben [inscribirse en Intune](/mem/intune/enrollment/windows-enrollment-methods) (parte de Microsoft Endpoint Manager).

1. Vaya al Centro de administración de Microsoft Endpoint Manager <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">https://endpoint.microsoft.com</a> e inicie sesión.

2. En el panel de navegación, seleccione **Seguridad de extremo.**

3. En **Administrar,** seleccione **Antivirus.** Verás varias pestañas, como **resumen,** puntos de conexión incorrectos de **Windows 10** y malware detectado en **Windows 10.**

4. Revise la información de las pestañas disponibles y, a continuación, tome las medidas necesarias.

Por ejemplo, supongamos que los dispositivos aparecen en la pestaña de malware detectado de **Windows 10.** Al seleccionar un dispositivo, tendrá determinadas acciones disponibles, como **Reiniciar** **,** Examen **rápido,** Examen **completo,** Sincronizar o **Actualizar firmas.** Selecciona una acción para ese dispositivo.

En la tabla siguiente se describen las acciones que puede ver en Microsoft Endpoint Manager.<br><br>

| Acción | Descripción |
|--|--|
| Restart | Fuerza el reinicio de un dispositivo Windows 10 en cinco minutos.<br><br>**IMPORTANTE:** El propietario o usuario del dispositivo no se notifica automáticamente del reinicio y podría perder el trabajo no guardado. |
| Examen rápido | Inicia un examen antivirus rápido en el dispositivo y se centra en las ubicaciones comunes donde se puede registrar malware, como las claves del Registro y las carpetas de inicio de Windows conocidas. Los resultados se envían a [Microsoft Endpoint Manager.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) |
| Examen completo | Inicia un examen antivirus completo en el dispositivo, centrándose en las ubicaciones comunes donde se puede registrar malware e incluyendo todos los archivos y carpetas del dispositivo. Los resultados se envían a [Microsoft Endpoint Manager.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) |
| Sincronizar | Requiere que un dispositivo se active con Intune (parte de Microsoft Endpoint Manager). Cuando el dispositivo se comprueba, el dispositivo recibe las acciones o directivas pendientes asignadas al dispositivo. |
| Actualizar firmas | Requiere que el dispositivo obtenga actualizaciones [de inteligencia de seguridad](https://go.microsoft.com/fwlink/?linkid=2149926) para la protección antivirus y antimalware. |

> [!TIP]
> Para obtener más información, consulta [Acciones remotas para dispositivos.](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices)

## <a name="how-to-submit-a-file-for-malware-analysis"></a>Cómo enviar un archivo para el análisis de malware

Si tiene un archivo que cree que se ha perdido o clasificado incorrectamente como malware, puede enviar ese archivo a Microsoft para su análisis de malware. Los usuarios y administradores de TI pueden enviar un archivo para su análisis. Visite [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) .
