---
title: Trabajar con informes
description: Los distintos informes disponibles en Escritorio administrado de Microsoft
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 28035a9f0a669c1daa7526d0b1fefac52a77c81a
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52729973"
---
# <a name="work-with-reports"></a>Trabajar con informes

Escritorio administrado de Microsoft proporciona varios informes y paneles que los administradores de TI de su organización pueden usar para comprender diversos aspectos de la población de dispositivos.Encontrará informes en dos ubicaciones: en [Microsoft Endpoint Manager](https://endpoint.microsoft.com) y en el [Centro Microsoft 365 administración](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop). 

## <a name="reports-in-microsoft-endpoint-manager"></a>Informes en Microsoft Endpoint Manager

La consola Microsoft Endpoint Manager reúne informes de varios productos en una única ubicación para ayudarle a supervisar e investigar problemas con la configuración y los dispositivos de la organización de Azure AD ("inquilino"). El escritorio administrado de Microsoft tiene una sección en **Informes** en el menú principal donde puede encontrar informes específicos de Escritorio administrado de Microsoft administración de los dispositivos que ha registrado.

Estos informes incluyen:
- **Dispositivos administrados**  >  **Actualizaciones de características:** esta vista muestra el estado general de las actualizaciones de características en Escritorio administrado de Microsoft dispositivos.
- **Dispositivos administrados**  >  **Office actualizaciones:** esta vista muestra el estado general de las Office actualizaciones en los Escritorio administrado de Microsoft dispositivos.

Además, en varias ubicaciones de Microsoft Endpoint Manager puede filtrar informes de otros grupos de productos para incluir o excluir específicamente los dispositivos administrados por Escritorio administrado de Microsoft. Estos informes han integrado esta funcionalidad de filtrado:

- [Todos los dispositivos](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Cumplimiento de dispositivos](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Dispositivos no compatibles](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Los Escritorio administrado de Microsoft personalizados garantizan el acceso solo a los Escritorio administrado de Microsoft informes. Para obtener acceso a otras partes de Microsoft Endpoint Manager, como **Todos** los dispositivos, vea Control de acceso basado en roles [con Microsoft Intune](/mem/intune/fundamentals/role-based-access-control). 


 ## <a name="inventory-data"></a>Datos de inventario

Además de los demás informes, puedes exportar información sobre los dispositivos administrados por Escritorio administrado de Microsoft. En la **vista Dispositivos** del área **Dispositivos** de Microsoft Endpoint Manager, use la pestaña Exportar **todo** para descargar un informe de [inventario detallado.](device-inventory-report.md)