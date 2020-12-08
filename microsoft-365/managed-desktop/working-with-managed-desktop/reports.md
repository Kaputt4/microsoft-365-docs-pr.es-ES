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
ms.openlocfilehash: bfd8305d23e0e6d761c629ee3048c6204f702d37
ms.sourcegitcommit: 98146c67a1d99db5510fa130340d3b7be8d81b21
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/07/2020
ms.locfileid: "49585333"
---
# <a name="work-with-reports"></a>Trabajar con informes

El escritorio administrado de Microsoft proporciona varios informes y paneles que los administradores de TI de la organización pueden usar para comprender diversos aspectos de la población de dispositivos.Encontrará informes en dos ubicaciones: en [Microsoft Endpoint Manager](https://endpoint.microsoft.com) y en el centro de [Administración de 365 de Microsoft](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop). 

## <a name="reports-in-microsoft-endpoint-manager"></a>Informes en Microsoft Endpoint Manager

La consola de Microsoft Endpoint Manager combina los informes de varios productos en una sola ubicación para ayudarle a supervisar e investigar los problemas con la configuración y los dispositivos de la organización ("inquilino") de Azure AD. Microsoft Managed Desktop tiene una sección bajo **informes** en el menú principal, donde puede encontrar informes específicos de la administración de Microsoft Managed Desktop de los dispositivos que ha registrado.

Además, en varias ubicaciones de Microsoft Endpoint Manager puede filtrar los informes de otros grupos de productos para incluir o excluir específicamente los dispositivos administrados por el escritorio administrado por Microsoft. Estos informes han integrado esta capacidad de filtrado:

- **Todos los dispositivos**
- **Cumplimiento de dispositivos**
- **Dispositivos no compatibles**

> [!NOTE]
> Las funciones de escritorio administradas de Microsoft personalizadas garantizan el acceso solo a los informes de Microsoft Managed Desktop. Para obtener acceso a otras partes del administrador de extremos de Microsoft, como **todos los dispositivos**, vea [control de acceso basado en roles con Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control). 

## <a name="reports-in-microsoft-365-admin-center"></a>Informes en el centro de administración de Microsoft 365

Puede encontrar informes de Microsoft Managed Desktop Insights abriendo el [centro de administración de microsoft 365](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)y, a continuación, navegando a los **informes** y seleccionando **Microsoft Managed Desktop**. También puede seguir el vínculo directo a estos informes desde la ficha **escritorio administrado de Microsoft** en la Página principal de [Microsoft Endpoint Manager](https://endpoint.microsoft.com). 

Estos informes incluyen: 

- [Información de uso](usage-insights.md) : esta vista proporciona métricas de uso para los dispositivos de escritorio administrados por Microsoft.
- [Confiabilidad Insights](reliability-insights.md) : esta vista le proporciona un resumen de estado de los dispositivos administrados.
- Información sobre las [baterías](battery-insights.md) : esta vista muestra información sobre el consumo de energía de las aplicaciones y la duración prevista de la batería para los dispositivos de su entorno.
- [Windows Security Update Insights](security-update-insights.md) : esta vista muestra información sobre el estado de las actualizaciones de seguridad para los dispositivos de escritorio administrados por Microsoft.

 ## <a name="inventory-data"></a>Datos de inventario

Además de los otros informes, puede exportar información sobre los dispositivos administrados por el escritorio administrado por Microsoft. En la vista **dispositivos** del área **dispositivos** de Microsoft Endpoint Manager, use la pestaña **exportar todo** para [descargar un informe de inventario detallado](device-inventory-report.md).