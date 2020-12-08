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
description: Obtén información sobre cómo revisar y administrar las amenazas detectadas por el antivirus de Microsoft defender en los dispositivos con Windows 10.
ms.openlocfilehash: 41465cb81850415a7b490b6af7f0ec66c724ca68
ms.sourcegitcommit: 490a65d32b6d656c661c36a2cc8dda03bf6cba77
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588522"
---
# <a name="review-detected-threats-and-take-action"></a>Revisar las amenazas detectadas y actuar al respecto

En cuanto se detecta un archivo malintencionado o software, antivirus de Microsoft defender lo bloquea e impide que se ejecute. Y con la protección entregada en la nube activada, se agregan amenazas recientemente detectadas al motor antivirus y antimalware para que también se protejan los demás dispositivos y usuarios.

Antivirus de Microsoft defender detecta y protege contra los siguientes tipos de amenazas:

- Virus, malware y amenazas basadas en Web en dispositivos
- Intentos de phishing
- Intentos de robo de datos

Como administrador profesional de ti, puede ver información sobre las detecciones de amenazas en los [dispositivos Windows 10 que se inscriben en Intune](/mem/intune/enrollment/device-enrollment) en el centro de administración de Microsoft 365. Verá información de Resumen, como:

- Cuántos dispositivos necesitan protección antivirus
- El número de dispositivos que no cumplen las directivas de seguridad
- El número de amenazas actualmente activas, mitigadas o resueltas

Tiene varias opciones para ver información específica sobre detección de amenazas y dispositivos:

- La página **dispositivos activos** del <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración de Microsoft 365</a>. Consulte [administrar detecciones de amenazas en la página dispositivos activos](#manage-threat-detections-on-the-active-devices-page) de este artículo.
- La página **amenazas activas** en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración de Microsoft 365</a>. Consulte [administrar detecciones de amenazas en la página amenazas activas](#manage-threat-detections-on-the-active-threats-page) de este artículo.
- La página **antivirus** en <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">Microsoft Endpoint Manager</a>. Consulte [administrar detecciones de amenazas en Microsoft Endpoint Manager](#manage-threat-detections-in-microsoft-endpoint-manager) en este artículo.

Para obtener más información, consulte [amenazas detectadas por antivirus de Microsoft defender](threats-detected-defender-av.md).

## <a name="manage-threat-detections-on-the-active-devices-page"></a>Administración de detecciones de amenazas en la página **dispositivos activos**

El siguiente procedimiento se aplica a los clientes que tienen Microsoft 365 empresa Premium.

1. Vaya al centro de administración de Microsoft 365 en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e inicie sesión.

2. En la página navegación, seleccione **dispositivos**  >  **activos** de dispositivos. Verá una lista de los dispositivos y detalles activos, como el estado de protección, el estado de protección antivirus (AV) y el número de amenazas activas detectadas.

3. Seleccione un dispositivo para ver más detalles sobre el dispositivo y las acciones disponibles. Se abre un control flotante con las recomendaciones y las acciones disponibles, como la **Directiva de actualización**, **Actualizar antivirus**, **Ejecutar examen rápido**, **Ejecutar examen completo** y más.

## <a name="manage-threat-detections-on-the-active-threats-page"></a>Administración de detecciones de amenazas en la página **amenazas activas**

El siguiente procedimiento se aplica a los clientes que tienen Microsoft 365 empresa Premium. Los [dispositivos Windows 10 deben estar protegidos](/microsoft-365/business/secure-win-10-pcs) e [inscritos en Intune](/mem/intune/enrollment/windows-enrollment-methods).

> [!NOTE]
> La página de la tarjeta **antivirus de Microsoft defender** y las **amenazas activas** se están implementando en fases, por lo que es posible que no tenga acceso inmediato a ellas.

1. Vaya al centro de administración de Microsoft 365 en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e inicie sesión.

2. En la tarjeta **antivirus de Microsoft defender** , seleccione **Ver amenazas activas**. (Como alternativa, en el panel de navegación, seleccione **mantenimiento**  >  **Amenazas & antivirus**.)

3. En la página **amenazas activas** , seleccione una amenaza detectada para obtener más información sobre ella. Se abre un control flotante con detalles sobre la amenaza, incluidos los dispositivos que están afectados.

4. En el control flotante, selecciona un dispositivo para ver las acciones disponibles, como la **Directiva de actualización**, **actualizar el antivirus**, **ejecutar el examen rápido** y mucho más.

## <a name="actions-you-can-take"></a>Acciones que puede realizar

Cuando vea detalles sobre amenazas o dispositivos específicos, verá recomendaciones y una o más acciones que puede realizar. En la tabla siguiente se describen las acciones que puede ver.<br><br>

| Acción | Descripción |
|--|--|
| Configurar la protección | Las directivas de protección contra amenazas deben configurarse. Seleccione el vínculo para ir a la página de configuración de directiva.<br><br>¿Necesita ayuda? Consulte [administrar la seguridad de los dispositivos con directivas de seguridad de extremos en Microsoft Intune](/mem/intune/protect/endpoint-security-policy). |
| Actualizar directiva | Es necesario actualizar o configurar las directivas de protección antivirus y en tiempo real. Seleccione el vínculo para ir a la página Configuración de directiva.<br><br>¿Necesita ayuda? Consulte [administrar la seguridad de los dispositivos con directivas de seguridad de extremos en Microsoft Intune](/mem/intune/protect/endpoint-security-policy). |
| Ejecutar examen rápido | Inicia un examen antivirus rápido en el dispositivo, centrándose en las ubicaciones comunes en las que se puede registrar el malware, como las claves del registro y las carpetas de inicio de Windows conocidas. |
| Ejecutar examen completo | Inicia un examen antivirus completo en el dispositivo, centrándose en las ubicaciones comunes en las que se puede registrar el malware, e incluye todos los archivos y carpetas del dispositivo. Los resultados se envían a [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Actualizar antivirus | Requiere que el dispositivo obtenga [actualizaciones de inteligencia de seguridad](https://go.microsoft.com/fwlink/?linkid=2149926) para la protección antivirus y antimalware. |
| Reiniciar dispositivo | Fuerza el reinicio de un dispositivo con Windows 10 en cinco minutos.<br><br>**Importante:** El usuario o el propietario del dispositivo no recibe una notificación automática del reinicio y podría perder el trabajo que no se ha guardado. |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>Administración de detecciones de amenazas en Microsoft Endpoint Manager

Puede usar Microsoft Endpoint Manager para administrar las detecciones de amenazas. Los dispositivos Windows 10 deben estar [inscritos en Intune](/mem/intune/enrollment/windows-enrollment-methods) (parte de Microsoft Endpoint Manager).

1. Vaya al centro de administración de Microsoft Endpoint Manager en <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">https://endpoint.microsoft.com</a> e inicie sesión.

2. En el panel de navegación, seleccione **seguridad de extremos**.

3. En **administrar**, seleccione **antivirus**. Verá varias pestañas, como **Resumen**, extremos sin **Estado de Windows 10** y el **malware detectado en Windows 10**.

4. Revise la información de las pestañas disponibles y, a continuación, lleve a cabo la acción necesaria.

Por ejemplo, supongamos que los dispositivos aparecen en la ficha **malware detectado de Windows 10** . Al seleccionar un dispositivo, dispondrá de determinadas acciones, como **reiniciar**, **análisis rápido**, **examen completo**, **sincronización** o **Actualizar firmas**. Seleccione una acción para ese dispositivo.

En la tabla siguiente se describen las acciones que puede ver en Microsoft Endpoint Manager.<br><br>

| Acción | Descripción |
|--|--|
| Restart | Fuerza el reinicio de un dispositivo con Windows 10 en cinco minutos.<br><br>**Importante:** El usuario o el propietario del dispositivo no recibe una notificación automática del reinicio y podría perder el trabajo que no se ha guardado. |
| Examen rápido | Inicia un examen antivirus rápido en el dispositivo, centrándose en las ubicaciones comunes en las que se puede registrar el malware, como las claves del registro y las carpetas de inicio de Windows conocidas. Los resultados se envían a [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Examen completo | Inicia un examen antivirus completo en el dispositivo, centrándose en las ubicaciones comunes en las que se puede registrar el malware, e incluye todos los archivos y carpetas del dispositivo. Los resultados se envían a [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Sincronizar | Requiere que un dispositivo se proteja con Intune (parte de Microsoft Endpoint Manager). Cuando el dispositivo se registra, el dispositivo recibe las acciones o directivas pendientes asignadas al dispositivo. |
| Actualizar firmas | Requiere que el dispositivo obtenga [actualizaciones de inteligencia de seguridad](https://go.microsoft.com/fwlink/?linkid=2149926) para la protección antivirus y antimalware. |

> [!TIP]
> Para obtener más información, consulte [acciones remotas para dispositivos](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices).

## <a name="how-to-submit-a-file-for-malware-analysis"></a>Cómo enviar un archivo para el análisis de malware

Si tiene un archivo que piensa que perdió o se clasificó de forma incorrecta como malware, puede enviar ese archivo a Microsoft para el análisis de malware. Los usuarios y los administradores de TI pueden enviar un archivo para su análisis. Visite [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) .
