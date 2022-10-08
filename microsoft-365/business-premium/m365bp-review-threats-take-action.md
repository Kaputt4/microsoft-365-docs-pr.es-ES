---
title: Revisar las amenazas detectadas en los dispositivos y tomar medidas
f1.keywords: NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-security
ms.subservice: other
ms.date: 09/15/2022
ms.localizationpriority: medium
ms.collection:
- m365-security
- tier1
search.appverid: MET150
description: Obtenga información sobre cómo revisar y administrar las amenazas detectadas por Microsoft Defender Antivirus en los dispositivos Windows.
ms.openlocfilehash: c9dab2a71d7ce8ce352ae1315be9ff0453215108
ms.sourcegitcommit: 0283c436f3ba61a708b52b57a1955f5ea74376a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2022
ms.locfileid: "68097673"
---
# <a name="review-detected-threats"></a>Revisión de las amenazas detectadas

En cuanto se detecta un archivo o software malintencionado, Microsoft Defender lo bloquea e impide que se ejecute. Y con la protección entregada en la nube activada, las amenazas recién detectadas se agregan al motor antivirus y antimalware para que los demás dispositivos y usuarios también estén protegidos.

Microsoft Defender Antivirus detecta y protege contra los siguientes tipos de amenazas:

- Virus, malware y amenazas basadas en web en dispositivos
- Intentos de suplantación de identidad
- Intentos de robo de datos

Como profesional o administrador de TI, puede ver información sobre las detecciones de amenazas [en todos los dispositivos Windows inscritos en Intune](/mem/intune/enrollment/device-enrollment) en el Centro de administración de Microsoft 365. Verá información de resumen, como:

- Cuántos dispositivos necesitan protección antivirus
- Cuántos dispositivos no cumplen las directivas de seguridad
- Cuántas amenazas están activas, mitigadas o resueltas

## <a name="actions-you-can-take"></a>Acciones que puede realizar

Cuando vea detalles sobre amenazas o dispositivos específicos, verá recomendaciones y una o varias acciones que puede realizar. En la tabla siguiente se describen las acciones que puede ver.<br><br>

| Acción | Descripción |
|--|--|
| Configuración de la protección | Es necesario configurar las directivas de protección contra amenazas. Seleccione el vínculo para ir a la página de configuración de la directiva.<br><br>¿Necesita ayuda? Consulte [Administración de la seguridad de dispositivos con directivas de seguridad de punto de conexión en Microsoft Intune](/mem/intune/protect/endpoint-security-policy). |
| Actualizar directiva | Los antivirus y las directivas de protección en tiempo real deben actualizarse o configurarse. Seleccione el vínculo para ir a la página de configuración de directivas.<br><br>¿Necesita ayuda? Consulte [Administración de la seguridad de dispositivos con directivas de seguridad de punto de conexión en Microsoft Intune](/mem/intune/protect/endpoint-security-policy). |
| Ejecución del examen rápido | Inicia un examen rápido del antivirus en el dispositivo, centrándose en ubicaciones comunes donde se puede registrar malware, como claves del Registro y carpetas de inicio conocidas de Windows. |
| Ejecución del examen completo | Inicia un examen antivirus completo en el dispositivo, centrándose en ubicaciones comunes donde se podría registrar malware e incluyendo todos los archivos y carpetas del dispositivo. Los resultados se envían a [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Actualización del antivirus | Requiere que el dispositivo obtenga [actualizaciones de inteligencia de seguridad](https://go.microsoft.com/fwlink/?linkid=2149926) para la protección antivirus y antimalware. |
| Reiniciar el dispositivo | Obliga a un dispositivo Windows a reiniciarse en cinco minutos.<br><br>**IMPORTANTE:** El propietario o usuario del dispositivo no recibe una notificación automática del reinicio y podría perder el trabajo no guardado. |

## <a name="view-and-manage-threat-detections-in-the-microsoft-365-defender-portal"></a>Visualización y administración de detecciones de amenazas en el portal de Microsoft 365 Defender

1. Vaya al portal ([Microsoft 365 Defender](https://security.microsoft.com)) e inicie sesión.

1. En el panel de navegación, elija **Análisis de amenazas** para ver todas las amenazas actuales. Se clasifican por gravedad y tipo de amenaza.

1. Haga clic en una amenaza para ver más detalles sobre la amenaza.

1. En la tabla, puede filtrar las alertas según una serie de criterios.

## <a name="manage-threat-detections-in-microsoft-intune"></a>Administración de detecciones de amenazas en Microsoft InTune

También puede usar Microsoft Endpoint Manager para administrar las detecciones de amenazas. En primer lugar, todos los dispositivos, ya sean Windows, iOS o Android, deben [inscribirse en Intune](/mem/intune/enrollment/windows-enrollment-methods) (parte de Microsoft Endpoint Manager).

1. Vaya al Centro de administración de Microsoft Endpoint Manager en <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">https://endpoint.microsoft.com</a> e inicie sesión.

2. En el panel de navegación, seleccione **Seguridad del punto de conexión**.

3. En **Administrar**, seleccione **Antivirus**. Verá pestañas para **Resumen**, **Puntos de conexión incorrectos** y **Malware activo**.

4. Revise la información de las pestañas disponibles y, a continuación, realice las acciones necesarias.

Por ejemplo, supongamos que los dispositivos aparecen en la pestaña **Malware activo** . Al seleccionar un dispositivo, tendrá ciertas acciones disponibles, como **Reiniciar**, **Examen rápido**, **Examen completo**, **Sincronizar** o **Actualizar firmas**. Seleccione una acción para ese dispositivo.

En la tabla siguiente se describen las acciones que puede ver en Microsoft Endpoint Manager.<br><br>

| Acción | Descripción |
|--|--|
| Restart | Obliga a un dispositivo Windows a reiniciarse en cinco minutos.<br><br>**IMPORTANTE:** El propietario o usuario del dispositivo no recibe una notificación automática del reinicio y podría perder el trabajo no guardado. |
| Examen rápido | Inicia un examen rápido del antivirus en el dispositivo, centrándose en ubicaciones comunes donde se puede registrar malware, como claves del Registro y carpetas de inicio conocidas de Windows. Los resultados se envían a [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Examen completo | Inicia un examen antivirus completo en el dispositivo, centrándose en ubicaciones comunes donde se podría registrar malware e incluyendo todos los archivos y carpetas del dispositivo. Los resultados se envían a [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Sincronizar | Requiere que un dispositivo se active con Intune (parte de Microsoft Endpoint Manager). Cuando el dispositivo se registra, el dispositivo recibe las acciones o directivas pendientes asignadas al dispositivo. |
| Actualización de firmas | Requiere que el dispositivo obtenga [actualizaciones de inteligencia de seguridad](https://go.microsoft.com/fwlink/?linkid=2149926) para la protección antivirus y antimalware. |

> [!TIP]
> Para obtener más información, consulte [Acciones remotas para dispositivos](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices).

## <a name="how-to-submit-a-file-for-malware-analysis"></a>Cómo enviar un archivo para el análisis de malware

Si tiene un archivo que cree que se perdió o se clasificó erróneamente como malware, puede enviar ese archivo a Microsoft para su análisis de malware. Los usuarios y los administradores de TI pueden enviar un archivo para su análisis. Visite [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission).

## <a name="see-also"></a>Vea también

[Procedimientos recomendados para proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)

[Introducción a Microsoft Defender para Empresas](../security/defender-business/mdb-overview.md) (Defender para empresas se está implementando para Microsoft 365 Empresa Premium clientes, a partir del 1 de marzo de 2022)
