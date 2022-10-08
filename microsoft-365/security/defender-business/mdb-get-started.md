---
title: Visitar el portal de Microsoft 365 Defender
description: El centro de seguridad de Defender para empresas es el portal de Microsoft 365 Defender. Obtenga información sobre cómo navegar por el portal y ver los pasos siguientes.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.date: 09/15/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-security
- m365-initiative-defender-business
- tier1
ms.custom: intro-get-started
ms.openlocfilehash: 7f23c0aa6ee3db1b549484b69bbc49907d13d4ed
ms.sourcegitcommit: 4dfb5de8c61847b8ddd10410ad20d34860eed8f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2022
ms.locfileid: "68110829"
---
# <a name="visit-the-microsoft-365-defender-portal"></a>Visitar el portal de Microsoft 365 Defender

El portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) es tu tienda integral para usar y administrar Microsoft Defender para Empresas. Incluye llamadas que le ayudarán a empezar, tarjetas que exponen información relevante y una barra de navegación para facilitar el acceso a varias características y funcionalidades.

:::image type="content" source="../../media/defender-business/mdb-portal-home.png" alt-text="Portal de Microsoft 365 Defender":::

## <a name="the-navigation-bar"></a>Barra de navegación

Use la barra de navegación del lado izquierdo de la pantalla para acceder a los incidentes, ver informes y administrar las directivas de seguridad. En la tabla siguiente se describen los elementos que verá en la barra de navegación.

| Elemento | Descripción |
|:---|:---|
| **Inicio** | Le lleva a la página principal en el portal de Microsoft 365 Defender. La página principal resalta las amenazas activas que se detectan, junto con recomendaciones para ayudar a proteger los datos y los dispositivos de su empresa. Las recomendaciones se incluyen en Defender for Business para ahorrar tiempo y esfuerzo al equipo de seguridad. Las recomendaciones se basan en los procedimientos recomendados del sector. Para más información, consulte [Recomendaciones de seguridad: Administración de vulnerabilidades de Microsoft Defender](../defender-endpoint/tvm-security-recommendation.md). |
| **Incidentes** | Le lleva a la lista de incidentes recientes. A medida que se desencadenan alertas, se crean incidentes. Un incidente puede incluir varias alertas. Asegúrese de revisar los incidentes con regularidad. Para más información, consulte [Visualización y administración de incidentes en Defender para empresas](mdb-view-manage-incidents.md).|
| **Acciones & envíos** >  **Centro de acciones** | Le lleva a la lista de acciones de respuesta, incluidas las acciones completadas y pendientes.<br/>- Seleccione la pestaña **Pendiente** para ver las acciones que requieren aprobación para continuar.<br/>- Seleccione la pestaña **Historial** para ver las acciones realizadas. Algunas acciones se realizan automáticamente; otros se toman manualmente o se completan después de que se aprueben.<br/><br/>Para obtener más información, consulte [Revisar las acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md). |
| **Acciones & envíos** >  **Presentaciones** | Le lleva al portal de envíos unificados, donde puede enviar archivos a Microsoft para su análisis. Para obtener más información, consulte [Envío de archivos en Microsoft Defender para punto de conexión](../defender-endpoint/admin-submissions-mde.md) (el proceso es similar para Defender para empresas). |
| **Análisis de amenazas** | Le lleva a una vista de las amenazas actuales y proporciona una vista general del panorama de las amenazas. El análisis de amenazas también incluye informes e información de investigadores de seguridad de Microsoft. Para más información, consulte [Seguimiento y respuesta a amenazas emergentes a través del análisis de amenazas](../defender-endpoint/threat-analytics.md). |
| **Puntuación de seguridad** | Proporciona una representación de la posición de seguridad de su empresa y ofrece sugerencias para mejorarla. Para más información, consulte [Puntuación segura de Microsoft para dispositivos](../defender-endpoint/tvm-microsoft-secure-score-devices.md). |
| **Centro de aprendizaje** | Proporciona acceso al entrenamiento de seguridad y a otros recursos a través de rutas de aprendizaje que se incluyen con la suscripción. Puede filtrar por producto, nivel de aptitud, rol y mucho más. El centro de aprendizaje puede ayudar al equipo de seguridad a aumentar las características y funcionalidades de seguridad en Defender para empresas y más ofertas de Microsoft, como [Microsoft Defender para punto de conexión](../defender-endpoint/microsoft-defender-endpoint.md) y [Microsoft Defender para Office 365](../office-365-security/defender-for-office-365.md).  |
| **Ensayos** | Pruebe las funcionalidades de seguridad y cumplimiento adicionales agregando una suscripción de prueba. Si no ve **Pruebas** en la barra de navegación y desea agregar en otra prueba, puede realizar uno de los pasos siguientes: <br/>- Visite la [página Soluciones para pequeñas empresas](https://www.microsoft.com/en-us/store/b/business?icid=CNavBusinessStore) y elija **Preguntas. Hable con un experto** para obtener ayuda para agregar una suscripción de prueba. <br/>- Vaya al [Centro de administración de Microsoft 365](https://admin.microsoft.com/?auth_upn=admin%40M365B614031.onmicrosoft.com&source=applauncher#/catalog) y elija **Servicios** de **compra de facturación** > . Si necesita ayuda, elija **Ayuda & soporte técnico**.    |
| **Activos** >  **Dispositivos** | Permite ver dispositivos, como equipos y dispositivos móviles inscritos en [Microsoft Intune](/mem/intune/fundamentals/what-is-intune). |
| **Extremos** >  **Administración de vulnerabilidades** | Permite acceder a las funcionalidades [de Administración de vulnerabilidades de Microsoft Defender](../defender-vulnerability-management/defender-vulnerability-management.md). Proporciona un panel, recomendaciones, actividades de corrección, un inventario de software y una lista de posibles debilidades dentro de la empresa. |
| **Extremos** >  **Tutoriales** | Proporciona acceso a tutoriales y simulaciones para ayudarle a obtener más información sobre cómo funcionan las características de protección contra amenazas. Seleccione el vínculo **Leer el tutorial** antes de intentar obtener el archivo de simulación para cada tutorial. Algunas simulaciones requieren aplicaciones de Office, como Microsoft Word, para leer el tutorial. |
| **Extremos** >  **Administración de configuración** >  **Configuración del dispositivo** | Enumera las directivas de seguridad por sistema operativo y por tipo. Para obtener más información sobre las directivas de seguridad, consulte [Visualización o edición de directivas en Defender para empresas](mdb-view-edit-policies.md). |
| **Extremos** >  **Administración de configuración** >  **Informes de administración de dispositivos** | Enumera los dispositivos que se incorporan a Defender for Business, junto con su versión del sistema operativo, el estado de mantenimiento del sensor y la última vez que se actualizaron. |
| Email &**reglas de & de directivas de** **colaboración** >  | Si la suscripción incluye Exchange Online Protection o Microsoft Defender para Office 365, en esta sección se administrarán las directivas de seguridad y la configuración de los servicios de correo electrónico y colaboración. [Obtenga más información sobre Office 365 seguridad](/microsoft-365/office-365-security/overview). *La versión independiente de Defender para empresas no incluye directivas de colaboración & correo electrónico, pero Microsoft 365 Empresa Premium incluye Exchange Online Protection y Defender para Office 365 Plan 1*. [Comparar las características de seguridad de los planes de Microsoft 365 para pequeñas y medianas empresas](compare-mdb-m365-plans.md).  |
| **Aplicaciones en la nube** >  **Gobernanza de aplicaciones** | Si la suscripción incluye [Microsoft Defender for Cloud Apps](/defender-cloud-apps/what-is-defender-for-cloud-apps), puede agregar la [gobernanza](/defender-cloud-apps/app-governance-manage-app-governance) de aplicaciones y esta sección es donde verá y accederá a esas funcionalidades. *Defender para empresas y Microsoft 365 Empresa Premium no incluyen Defender for Cloud Apps*. |
| **Informes** | Enumera los informes de seguridad disponibles. Estos informes le permiten ver las tendencias de seguridad, ver detalles sobre las detecciones y alertas de amenazas y obtener más información sobre los dispositivos vulnerables de su empresa. |
| **Estado** | Permite ver el estado de mantenimiento del servicio y planear los próximos cambios. <br/>- Seleccione **Estado del servicio** para ver el estado de mantenimiento de los servicios de Microsoft 365 que se incluyen en la suscripción de su empresa.<br/>- Seleccione **Centro de** mensajes para obtener información sobre los cambios planeados y lo que se espera.  |
| **Permisos** | Permite asignar permisos a las personas de la empresa que administran la seguridad y ver incidentes e informes en el portal de Microsoft 365 Defender. También le permite configurar y administrar grupos de dispositivos para incorporar los dispositivos de su empresa y asignar directivas de protección contra amenazas.  |
| **Configuración** | Permite editar la configuración del portal de Microsoft 365 Defender y Defender para empresas. Por ejemplo, puede incorporar (o offboard) los dispositivos de su empresa (también conocidos como puntos de conexión). También puede definir reglas, como las reglas de supresión de alertas, y configurar indicadores para bloquear o permitir determinados archivos o procesos.  |
| **Más recursos** | Vaya a otros portales, como Azure Active Directory. Pero tenga en cuenta que el portal de Microsoft 365 Defender debe satisfacer sus necesidades sin necesidad de navegar a otros portales. |
| **Personalización del panel de navegación** | Seleccione esta opción para ocultar o mostrar opciones en la barra de navegación. |

## <a name="next-steps"></a>Pasos siguientes

- [Uso del asistente para la instalación en Defender para empresas](mdb-use-wizard.md)
- [Consulte el proceso de configuración y configuración general.](mdb-setup-configuration.md)