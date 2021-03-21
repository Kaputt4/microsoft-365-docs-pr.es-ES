---
title: Trabajar con informes
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e509ae63225362613962cd0c366c51239f3d4493
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917687"
---
# <a name="work-with-reports"></a>Trabajar con informes

Microsoft Managed Desktop proporciona varios informes y paneles que los administradores de TI de su organización pueden usar para comprender diversos aspectos de la población de dispositivos.Encontrará informes en dos ubicaciones: en [Microsoft Endpoint Manager](https://endpoint.microsoft.com) y en el Centro de administración de Microsoft [365](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop). 

## <a name="reports-in-microsoft-endpoint-manager"></a>Informes en Microsoft Endpoint Manager

La consola de Microsoft Endpoint Manager reúne informes de varios productos en una única ubicación para ayudarle a supervisar e investigar problemas con la configuración y los dispositivos de la organización de Azure AD ("inquilino"). El escritorio administrado de Microsoft tiene una sección en **Informes** en el menú principal donde puede encontrar informes específicos de la administración de Microsoft Managed Desktop de los dispositivos que ha registrado.

Estos informes incluyen:
- **Dispositivos administrados**  >  **Actualizaciones de características:** esta vista muestra el estado general de las actualizaciones de características en los dispositivos de Escritorio administrado de Microsoft.
- **Dispositivos administrados**  >  **Actualizaciones de Office:** esta vista muestra el estado general de las actualizaciones de Office en los dispositivos de Escritorio administrado de Microsoft.

Además, en varias ubicaciones de Microsoft Endpoint Manager puede filtrar informes de otros grupos de productos para incluir o excluir específicamente los dispositivos administrados por Microsoft Managed Desktop. Estos informes han integrado esta funcionalidad de filtrado:

- [Todos los dispositivos](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Cumplimiento de dispositivos](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Dispositivos no compatibles](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Los roles personalizados de Escritorio administrado de Microsoft garantizan el acceso solo a los informes de Escritorio administrado de Microsoft. Para obtener acceso a otras partes de Microsoft Endpoint Manager, como **Todos** los dispositivos, consulte Control de acceso basado en [roles con Microsoft Intune](/mem/intune/fundamentals/role-based-access-control). 

## <a name="reports-in-microsoft-365-admin-center"></a>Informes en el Centro de administración de Microsoft 365

Para encontrar los informes de información de Escritorio administrado de Microsoft, abra  el Centro de administración de [Microsoft 365](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)y, a continuación, vaya a Informes y seleccione **Escritorio administrado de Microsoft**. También puede seguir el vínculo directo a estos informes desde la pestaña **Escritorio** administrado de Microsoft en la página principal [de Microsoft Endpoint Manager](https://endpoint.microsoft.com). 

Estos informes incluyen: 

- [Información de uso:](usage-insights.md) esta vista proporciona métricas de uso para los dispositivos de Escritorio administrado de Microsoft.
- [Información de confiabilidad:](reliability-insights.md) esta vista le proporciona un resumen de estado de los dispositivos administrados.
- [Información sobre la batería:](battery-insights.md) esta vista muestra información sobre el consumo de energía de las aplicaciones y la duración de la batería proyectada para los dispositivos de su entorno.
- [Información sobre actualizaciones de seguridad de Windows:](security-update-insights.md) esta vista muestra información sobre el estado de las actualizaciones de seguridad de los dispositivos de Escritorio administrado de Microsoft.

 ## <a name="inventory-data"></a>Datos de inventario

Además de los demás informes, puede exportar información sobre los dispositivos administrados por Microsoft Managed Desktop. En la **vista Dispositivos** del área **Dispositivos** de Microsoft Endpoint Manager, use la pestaña Exportar **todo** para descargar un [informe de inventario detallado.](device-inventory-report.md)