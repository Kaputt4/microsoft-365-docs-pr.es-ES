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
description: Obtenga información sobre cómo revisar y administrar las amenazas detectadas por Antivirus de Microsoft Defender en los dispositivos Windows 10.
ms.openlocfilehash: 2d75149f8bcb4ea13e1e474acbb1dedfccb4ec50
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2022
ms.locfileid: "65469478"
---
# <a name="review-threats-detected-by-microsoft-defender-antivirus-and-take-action"></a>Revisar las amenazas detectadas por Antivirus de Microsoft Defender y tomar medidas

En cuanto se detecta un archivo o software malintencionado, Antivirus de Microsoft Defender lo bloquea e impide que se ejecute. Y con la protección entregada en la nube activada, las amenazas recién detectadas se agregan al motor antivirus y antimalware para que los demás dispositivos y usuarios también estén protegidos.

Antivirus de Microsoft Defender detecta y protege contra los siguientes tipos de amenazas:

- Virus, malware y amenazas basadas en web en dispositivos
- Intentos de suplantación de identidad
- Intentos de robo de datos

Como profesional o administrador de TI, puede ver información sobre las detecciones de amenazas en [Windows 10 dispositivos inscritos en Intune](/mem/intune/enrollment/device-enrollment) en el Centro de administración de Microsoft 365. Verá información de resumen, como:

- Cuántos dispositivos necesitan protección antivirus
- Cuántos dispositivos no cumplen las directivas de seguridad
- Cuántas amenazas están activas, mitigadas o resueltas

Tiene varias opciones para ver información específica sobre las detecciones de amenazas y los dispositivos:

- Página **Dispositivos activos** de la <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>. Consulte [Administración de detecciones de amenazas en la página Dispositivos activos](#manage-threat-detections-on-the-active-devices-page) de este artículo.
- Página **Amenazas activas** en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>. Consulte [Administración de detecciones de amenazas en la página Amenazas activas](#manage-threat-detections-on-the-active-threats-page) de este artículo.
- La página **Antivirus** de <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">Microsoft Endpoint Manager</a>. Consulte [Administración de detecciones de amenazas en Microsoft Endpoint Manager](#manage-threat-detections-in-microsoft-endpoint-manager) en este artículo.

Para más información, consulte [Amenazas detectadas por Antivirus de Microsoft Defender](threats-detected-defender-av.md).

## <a name="manage-threat-detections-on-the-active-devices-page"></a>Administración de detecciones de amenazas en la página **Dispositivos activos**

El siguiente procedimiento se aplica a los clientes que tienen Microsoft 365 Empresa Premium.

1. Vaya al Centro de administración de Microsoft 365 en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e inicie sesión.

2. En la página de navegación, seleccione **DispositivosDispositivos** >  activos. Verá una lista de dispositivos activos y detalles, como el estado de protección, el estado de protección antivirus (AV) y el número de amenazas activas detectadas.

3. Seleccione un dispositivo para ver más detalles sobre ese dispositivo y las acciones disponibles. Se abre un control flotante con recomendaciones y acciones disponibles, como **Actualizar directiva**, **Actualizar antivirus**, **Ejecutar examen rápido**, **Ejecutar examen completo**, etc.

## <a name="manage-threat-detections-on-the-active-threats-page"></a>Administración de detecciones de amenazas en la página **Amenazas activas**

El siguiente procedimiento se aplica a los clientes que tienen Microsoft 365 Empresa Premium. [Windows 10 dispositivos deben estar protegidos](../setup/secure-win-10-pcs.md) e [inscritos en Intune](/mem/intune/enrollment/windows-enrollment-methods).

> [!NOTE]
> La tarjeta **de Antivirus de Microsoft Defender** y la página **Amenazas activas** se están implementando en fases, por lo que es posible que no tenga acceso inmediato a ellas.

1. Vaya al Centro de administración de Microsoft 365 en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e inicie sesión.

2. En la tarjeta **Antivirus de Microsoft Defender**, seleccione **Ver amenazas activas**. (Como alternativa, en el panel de navegación, seleccione **Estado** > . **Amenazas & antivirus**).

3. En la página **Amenazas activas** , seleccione una amenaza detectada para obtener más información al respecto. Se abre un control flotante con detalles sobre esa amenaza, incluidos los dispositivos afectados.

4. En el control flotante, seleccione un dispositivo para ver las acciones disponibles, como **Actualizar directiva**, **Actualizar antivirus**, **Ejecutar examen rápido**, etc.

## <a name="actions-you-can-take"></a>Acciones que puede realizar

Cuando vea detalles sobre amenazas o dispositivos específicos, verá recomendaciones y una o varias acciones que puede realizar. En la tabla siguiente se describen las acciones que puede ver.<br><br>

| Acción | Descripción |
|--|--|
| Configuración de la protección | Es necesario configurar las directivas de protección contra amenazas. Seleccione el vínculo para ir a la página de configuración de la directiva.<br><br>¿Necesita ayuda? Consulte [Administración de la seguridad de dispositivos con directivas de seguridad de punto de conexión en Microsoft Intune](/mem/intune/protect/endpoint-security-policy). |
| Actualizar directiva | Los antivirus y las directivas de protección en tiempo real deben actualizarse o configurarse. Seleccione el vínculo para ir a la página de configuración de directivas.<br><br>¿Necesita ayuda? Consulte [Administración de la seguridad de dispositivos con directivas de seguridad de punto de conexión en Microsoft Intune](/mem/intune/protect/endpoint-security-policy). |
| Ejecución del examen rápido | Inicia un examen rápido del antivirus en el dispositivo, centrándose en ubicaciones comunes donde se puede registrar malware, como claves del Registro y carpetas de inicio conocidas Windows. |
| Ejecución del examen completo | Inicia un examen antivirus completo en el dispositivo, centrándose en ubicaciones comunes donde se podría registrar malware e incluyendo todos los archivos y carpetas del dispositivo. Los resultados se envían a [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Actualización del antivirus | Requiere que el dispositivo obtenga [actualizaciones de inteligencia de seguridad](https://go.microsoft.com/fwlink/?linkid=2149926) para la protección antivirus y antimalware. |
| Reiniciar el dispositivo | Obliga a un dispositivo Windows 10 a reiniciarse en cinco minutos.<br><br>**IMPORTANTE:** El propietario o usuario del dispositivo no recibe una notificación automática del reinicio y podría perder el trabajo no guardado. |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>Administración de detecciones de amenazas en Microsoft Endpoint Manager

Puede usar Microsoft Endpoint Manager para administrar las detecciones de amenazas. Windows 10 dispositivos deben [inscribirse en Intune](/mem/intune/enrollment/windows-enrollment-methods) (parte de Microsoft Endpoint Manager).

1. Vaya al centro de administración de Microsoft Endpoint Manager en <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">https://endpoint.microsoft.com</a> e inicie sesión.

2. En el panel de navegación, seleccione **Seguridad del punto de conexión**.

3. En **Administrar**, seleccione **Antivirus**. Verá varias pestañas, como **Resumen**, **Windows 10 puntos de conexión incorrectos** y **Windows 10 malware detectado**.

4. Revise la información de las pestañas disponibles y, a continuación, realice las acciones necesarias.

Por ejemplo, supongamos que los dispositivos aparecen en la **pestaña Windows 10 malware detectado**. Al seleccionar un dispositivo, tendrá ciertas acciones disponibles, como **Reiniciar**, **Examen rápido**, **Examen completo**, **Sincronizar** o **Actualizar firmas**. Seleccione una acción para ese dispositivo.

En la tabla siguiente se describen las acciones que puede ver en Microsoft Endpoint Manager.<br><br>

| Acción | Descripción |
|--|--|
| Restart | Obliga a un dispositivo Windows 10 a reiniciarse en cinco minutos.<br><br>**IMPORTANTE:** El propietario o usuario del dispositivo no recibe una notificación automática del reinicio y podría perder el trabajo no guardado. |
| Examen rápido | Inicia un examen rápido del antivirus en el dispositivo, centrándose en ubicaciones comunes donde se puede registrar malware, como claves del Registro y carpetas de inicio conocidas Windows. Los resultados se envían a [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Examen completo | Inicia un examen antivirus completo en el dispositivo, centrándose en ubicaciones comunes donde se podría registrar malware e incluyendo todos los archivos y carpetas del dispositivo. Los resultados se envían a [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Sincronizar | Requiere que un dispositivo se active con Intune (parte de Microsoft Endpoint Manager). Cuando el dispositivo se registra, el dispositivo recibe las acciones o directivas pendientes asignadas al dispositivo. |
| Actualización de firmas | Requiere que el dispositivo obtenga [actualizaciones de inteligencia de seguridad](https://go.microsoft.com/fwlink/?linkid=2149926) para la protección antivirus y antimalware. |

> [!TIP]
> Para obtener más información, consulte [Acciones remotas para dispositivos](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices).

## <a name="how-to-submit-a-file-for-malware-analysis"></a>Cómo enviar un archivo para el análisis de malware

Si tiene un archivo que cree que se perdió o se clasificó erróneamente como malware, puede enviar ese archivo a Microsoft para su análisis de malware. Los usuarios y los administradores de TI pueden enviar un archivo para su análisis. Visite [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission).

## <a name="see-also"></a>Vea también

[Procedimientos recomendados para proteger Microsoft 365 para planes empresariales](../../admin/security-and-compliance/secure-your-business-data.md)

[Introducción a Microsoft Defender para Empresas](../../security/defender-business/mdb-overview.md) (Defender para empresas se está implementando para Microsoft 365 Empresa Premium clientes, a partir del 1 de marzo de 2022)