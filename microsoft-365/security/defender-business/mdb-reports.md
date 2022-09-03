---
title: Informes en Microsoft Defender para Empresas
description: Obtenga información general sobre los informes de seguridad en Defender para empresas. Los informes mostrarán las amenazas detectadas, las alertas, las vulnerabilidades y el estado del dispositivo.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.date: 08/11/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 6e4413eb506a40f39fdd16dabaf839eedf5ac205
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67598052"
---
# <a name="reports-in-microsoft-defender-for-business"></a>Informes en Microsoft Defender para Empresas

Los informes de protección están disponibles en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). En este artículo se describen estos informes, cómo puede usarlos y cómo encontrarlos.

## <a name="reports-in-defender-for-business"></a>Informes en Defender para empresas

|Informe  |Descripción  |
|---------|---------|
| **Informe de seguridad**  | El informe de seguridad proporciona información sobre las identidades, los dispositivos y las aplicaciones de la empresa. Para acceder a este informe, en el panel de navegación, elija Informe de seguridad **general** >  **de informes** > . <br/><br/>Puede ver información similar en la página principal del portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). |
| **Protección contra amenazas**  | El informe de protección contra amenazas proporciona información sobre alertas y tendencias de alertas. Use la columna **Tendencias de alertas** para ver información sobre las alertas que se desencadenaron en los últimos 30 días. Use la columna **Estado de alerta** para ver la información de instantáneas actual sobre alertas, como categorías de alertas sin resolver y su clasificación. Para acceder a este informe, en el panel de navegación, elija **Informes** > **puntos de conexión** > **Protección contra amenazas**. <br/><br/>También puede usar la lista **Incidentes** para ver información sobre las alertas. En el panel de navegación, elija **Incidentes** para ver y administrar los incidentes actuales. Para más información, consulte [Visualización y administración de incidentes en Defender para empresas](mdb-view-manage-incidents.md). |
| **Cumplimiento y mantenimiento del dispositivo** | El informe de estado y cumplimiento del dispositivo proporciona información sobre el estado y las tendencias del dispositivo. Puede usar este informe para determinar si los sensores de Defender para empresas funcionan correctamente en los dispositivos y el estado actual del Antivirus de Microsoft Defender. Para acceder a este informe, en el panel de navegación, elija **Informes** >  de estado **y cumplimiento del dispositivo** de **puntos** >  de conexión. <br/><br/>Puede usar la lista **Inventario de** dispositivos para ver información sobre los dispositivos de su empresa. En el panel de navegación, elija **Inventario de dispositivos**. Para más información, consulte [Administración de dispositivos en Defender para empresas](mdb-manage-devices.md). |
| **Dispositivos vulnerables** | El informe de dispositivos vulnerables proporciona información sobre los dispositivos y las tendencias. Use la columna **Tendencias** para ver información sobre los dispositivos que han tenido alertas en los últimos 30 días. Use la columna **Estado** para ver la información de instantáneas actual sobre los dispositivos que tienen alertas. Para acceder a este informe, en el panel de navegación, elija Dispositivos **vulnerables** de **puntos** >  de conexión de **informes** > .<br/><br/>**SUGERENCIA**: Puede usar la lista **Inventario** de dispositivos para ver información sobre los dispositivos de su empresa. En el panel de navegación, elija **Inventario de dispositivos**. Para más información, consulte [Administración de dispositivos en Defender para empresas](mdb-manage-devices.md). |
| **Protección web** | El informe de protección web muestra los intentos de acceder a sitios de phishing, vectores de malware, sitios de vulnerabilidades de seguridad, sitios que no son de confianza o de baja reputación y sitios que están bloqueados explícitamente. Las categorías de sitios bloqueados incluyen contenido para adultos, sitios de ocio, sitios de responsabilidad legal, etc. Para acceder a este informe, en el panel de navegación, elija Protección **web** de **puntos** >  de conexión **de informes** > .<br/><br/>Si aún no ha configurado la protección web para su empresa, elija el botón **Configuración** en una vista de informe. A continuación, en **Reglas**, elija **Filtrado de contenido web**. Para más información sobre el filtrado de contenido web, consulte [Filtrado de contenido web](../defender-endpoint/web-content-filtering.md). |
| **Firewall** | El informe de firewall muestra las conexiones entrantes, salientes y de aplicación bloqueadas. Este informe también muestra direcciones IP remotas conectadas por varios dispositivos y direcciones IP remotas con la mayoría de los intentos de conexión. <br/><br/>Si aún no ha configurado la protección del firewall, en el panel de navegación, elija Configuración de dispositivos de **administración de** >  **puntos** >  de **conexión**. Para más información, consulte [Firewall en Defender para empresas](mdb-firewall.md). |
| **Control de dispositivos** | El informe de control de dispositivos muestra información sobre el uso de medios, como el uso de dispositivos de almacenamiento extraíbles en su organización. |


## <a name="see-also"></a>Vea también

- [Introducción al uso de Defender para empresas](mdb-get-started.md)
- [Visualización y administración de incidentes en Defender para empresas](mdb-view-manage-incidents.md)
- [Administración de dispositivos en Defender para empresas](mdb-manage-devices.md)
