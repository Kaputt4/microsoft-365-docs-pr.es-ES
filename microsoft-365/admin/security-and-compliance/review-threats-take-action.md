---
title: Revisar las amenazas detectadas y actuar al respecto
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Obtén información sobre cómo revisar y administrar las amenazas detectadas por Antivirus de Microsoft Defender en tus Windows 10 dispositivos.
ms.openlocfilehash: c836554445f56a9a915885d55a4490c6bb5bd1a9
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "64633224"
---
# <a name="review-detected-threats-and-take-action"></a>Revisar las amenazas detectadas y actuar al respecto

Tan pronto como se detecte un archivo o software malintencionado, Antivirus de Microsoft Defender lo bloquea y evita que se ejecute. Y con la protección entregada en la nube activada, las amenazas detectadas recientemente se agregan al motor antivirus y antimalware para que los demás dispositivos y usuarios también estén protegidos.

Antivirus de Microsoft Defender detecta y protege contra los siguientes tipos de amenazas:

- Virus, malware y amenazas basadas en web en dispositivos
- Intentos de suplantación de identidad
- Intentos de robo de datos

Como profesional o administrador de TI, puede ver información sobre las detecciones de [](/mem/intune/enrollment/device-enrollment) amenazas en Windows 10 dispositivos inscritos en Intune en el Centro de administración de Microsoft 365. Verá información de resumen, como:

- Cuántos dispositivos necesitan protección antivirus
- Cuántos dispositivos no cumplen las directivas de seguridad
- Cuántas amenazas están activas, mitigadas o resueltas actualmente

Tienes varias opciones para ver información específica sobre dispositivos y detecciones de amenazas:

- La **página Dispositivos activos** de la <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>. Consulta [Administrar detecciones de amenazas en la página Dispositivos activos](#manage-threat-detections-on-the-active-devices-page) en este artículo.
- La **página Amenazas activas** de la <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>. Consulte [Administrar detecciones de amenazas en la página Amenazas activas](#manage-threat-detections-on-the-active-threats-page) de este artículo.
- La **página Antivirus** en <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">Microsoft Endpoint Manager</a>. Consulte [Manage threat detections in Microsoft Endpoint Manager](#manage-threat-detections-in-microsoft-endpoint-manager) en este artículo.

Para obtener más información, consulte [Amenazas detectadas por Antivirus de Microsoft Defender](threats-detected-defender-av.md).

## <a name="manage-threat-detections-on-the-active-devices-page"></a>Administrar detecciones de amenazas en la **página Dispositivos activos**

El siguiente procedimiento se aplica a los clientes que tienen Microsoft 365 Business Premium.

1. Vaya al Centro de administración de Microsoft 365 e <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> inicie sesión.

2. En la página de navegación, seleccione **Dispositivosactivos** > . Verá una lista de dispositivos activos y detalles, como el estado de protección, el estado de protección antivirus (AV) y el número de amenazas activas detectadas.

3. Selecciona un dispositivo para ver más detalles sobre ese dispositivo y las acciones disponibles. Se abre un control desplegable con recomendaciones y acciones disponibles, como la directiva de **actualización,** **actualizar antivirus**, **Ejecutar examen rápido**, **Ejecutar examen completo** y mucho más.

## <a name="manage-threat-detections-on-the-active-threats-page"></a>Administrar detecciones de amenazas en la **página Amenazas activas**

El siguiente procedimiento se aplica a los clientes que tienen Microsoft 365 Business Premium. [Windows 10 dispositivos deben protegerse](../setup/secure-win-10-pcs.md) [e inscribirse en Intune](/mem/intune/enrollment/windows-enrollment-methods).

> [!NOTE]
> La **Antivirus de Microsoft Defender** y la **página Amenazas** activas se están implantando en fases, por lo que es posible que no tenga acceso inmediato a ellas.

1. Vaya al Centro de administración de Microsoft 365 e <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> inicie sesión.

2. En la **Antivirus de Microsoft Defender**, seleccione **Ver amenazas activas**. (Como alternativa, en el panel de navegación, seleccione **Estado** >  **Amenazas & antivirus**).)

3. En la **página Amenazas activas** , seleccione una amenaza detectada para obtener más información sobre ella. Se abre un flyout con detalles sobre esa amenaza, incluidos los dispositivos que se ven afectados.

4. En el menú desplegable, selecciona un dispositivo para ver las acciones disponibles, como La directiva de **actualización,** **Actualizar antivirus**, **Ejecutar examen rápido** y mucho más.

## <a name="actions-you-can-take"></a>Acciones que puede realizar

Cuando veas detalles sobre amenazas o dispositivos específicos, verás recomendaciones y una o más acciones que puedes realizar. En la tabla siguiente se describen las acciones que puede ver.<br><br>

| Acción | Descripción |
|--|--|
| Configurar la protección | Es necesario configurar las directivas de protección contra amenazas. Seleccione el vínculo para ir a la página de configuración de directivas.<br><br>¿Necesita ayuda? Consulta [Administrar la seguridad de dispositivos con directivas de seguridad de puntos de conexión en Microsoft Intune](/mem/intune/protect/endpoint-security-policy). |
| Actualizar directiva | Las directivas de protección en tiempo real y antivirus deben actualizarse o configurarse. Seleccione el vínculo para ir a la página de configuración de directivas.<br><br>¿Necesita ayuda? Consulta [Administrar la seguridad de dispositivos con directivas de seguridad de puntos de conexión en Microsoft Intune](/mem/intune/protect/endpoint-security-policy). |
| Ejecutar examen rápido | Inicia un examen rápido del antivirus en el dispositivo, centrándose en ubicaciones comunes en las que se puede registrar malware, como las claves del Registro y las carpetas de inicio conocidas Windows inicio. |
| Ejecutar examen completo | Inicia un examen antivirus completo en el dispositivo, centrándose en ubicaciones comunes donde se puede registrar malware e incluyendo todos los archivos y carpetas del dispositivo. Los resultados se [envían a Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Actualizar antivirus | Requiere que el dispositivo obtenga actualizaciones [de inteligencia de seguridad](https://go.microsoft.com/fwlink/?linkid=2149926) para la protección antivirus y antimalware. |
| Reiniciar el dispositivo | Fuerza a Windows 10 dispositivo a reiniciarse en cinco minutos.<br><br>**IMPORTANTE:** El propietario o usuario del dispositivo no se notifica automáticamente del reinicio y podría perder el trabajo no guardado. |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>Administrar detecciones de amenazas en Microsoft Endpoint Manager

Puede usar Microsoft Endpoint Manager para administrar las detecciones de amenazas. Windows 10 los dispositivos deben [estar inscritos en Intune](/mem/intune/enrollment/windows-enrollment-methods) (parte de Microsoft Endpoint Manager).

1. Vaya al Centro Microsoft Endpoint Manager administración en e <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">https://endpoint.microsoft.com</a> inicie sesión.

2. En el panel de navegación, seleccione **Seguridad del extremo**.

3. En **Administrar**, seleccione **Antivirus**. Verá varias pestañas, como **Resumen, Windows 10** extremos en mal estado y Windows 10 **malware detectado**.

4. Revise la información de las pestañas disponibles y, a continuación, tome las medidas necesarias.

Por ejemplo, supongamos que los dispositivos aparecen en la **Windows 10 de malware detectado**. Cuando seleccionas un dispositivo, tendrás ciertas acciones disponibles, como **Reiniciar**, **Examinar** **rápidamente, Examinar** **completo, Sincronizar** o **Actualizar firmas**. Selecciona una acción para ese dispositivo.

En la tabla siguiente se describen las acciones que puede ver en Microsoft Endpoint Manager.<br><br>

| Acción | Descripción |
|--|--|
| Restart | Fuerza a Windows 10 dispositivo a reiniciarse en cinco minutos.<br><br>**IMPORTANTE:** El propietario o usuario del dispositivo no se notifica automáticamente del reinicio y podría perder el trabajo no guardado. |
| Examen rápido | Inicia un examen rápido del antivirus en el dispositivo, centrándose en ubicaciones comunes en las que se puede registrar malware, como las claves del Registro y las carpetas de inicio conocidas Windows inicio. Los resultados se [envían a Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Examen completo | Inicia un examen antivirus completo en el dispositivo, centrándose en ubicaciones comunes donde se puede registrar malware e incluyendo todos los archivos y carpetas del dispositivo. Los resultados se [envían a Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Sincronizar | Requiere que un dispositivo se desproteba con Intune (parte de Microsoft Endpoint Manager). Cuando el dispositivo se comprueba, el dispositivo recibe cualquier acción o directivas pendientes asignadas al dispositivo. |
| Actualizar firmas | Requiere que el dispositivo obtenga actualizaciones [de inteligencia de seguridad](https://go.microsoft.com/fwlink/?linkid=2149926) para la protección antivirus y antimalware. |

> [!TIP]
> Para obtener más información, consulta [Acciones remotas para dispositivos](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices).

## <a name="how-to-submit-a-file-for-malware-analysis"></a>Cómo enviar un archivo para el análisis de malware

Si tiene un archivo que cree que se ha perdido o clasificado incorrectamente como malware, puede enviar ese archivo a Microsoft para su análisis de malware. Los usuarios y administradores de TI pueden enviar un archivo para su análisis. Visite [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission).

## <a name="see-also"></a>Vea también

[Principales 10 formas de proteger Microsoft 365 para planes empresariales](../../admin/security-and-compliance/secure-your-business-data.md)

[Información general Microsoft Defender für Unternehmen](../../security/defender-business/mdb-overview.md) (Defender for Business se está implementando para Microsoft 365 Business Premium clientes, a partir del 1 de marzo de 2022)