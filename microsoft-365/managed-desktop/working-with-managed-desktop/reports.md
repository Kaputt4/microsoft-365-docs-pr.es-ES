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
ms.openlocfilehash: b37ce09a0781aa83970502224ddbb3658ed07d69
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771890"
---
# <a name="work-with-reports"></a>Trabajar con informes

Escritorio administrado de Microsoft proporciona varios informes y paneles que los administradores de TI de su organización pueden usar para comprender diversos aspectos de la población de dispositivos. 

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

## <a name="endpoint-analytics"></a>Análisis de puntos de conexión
Escritorio administrado de Microsoft está integrado con endpoint [analytics.](/mem/analytics/overview) Estos informes le proporcionan información para medir cómo funciona su organización y la calidad de la experiencia que se ofrece a los usuarios. El análisis de extremos se encuentra en **el menú** Informes [de Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Para pivotar una puntuación para incluir solo los dispositivos  administrados por Escritorio administrado de Microsoft ir a cualquier informe, seleccione la lista desplegable Filtro y, a continuación, **seleccione Escritorio administrado de Microsoft dispositivos**.

Si endpoint analytics no se configuró automáticamente para su organización de Azure AD ("inquilino") durante la inscripción, puede hacerlo usted mismo. Para obtener más información, vea [Onboard in the Endpoint analytics portal](/mem/analytics/enroll-intune#bkmk_onboard). Puedes inscribir todos los dispositivos o, si quieres incluir solo  dispositivos Escritorio administrado de Microsoft, selecciona los grupos de dispositivos de lugar de trabajo modernos para Test, First, Fast y Broad. Estos informes pueden requerir permisos diferentes. Para obtener más información, vea [Permissions](/mem/analytics/overview#permissions) to ensure you have roles appropriately assigned.

> [!NOTE]
> Para respetar mejor la privacidad del usuario, debe haber más de 10 dispositivos Escritorio administrado de Microsoft inscritos en endpoint analytics para usar este filtro.

 ## <a name="inventory-data"></a>Datos de inventario

Además de los demás informes, puedes exportar información sobre los dispositivos administrados por Escritorio administrado de Microsoft. En la **vista Dispositivos** del área **Dispositivos** de Microsoft Endpoint Manager, use la pestaña Exportar **todo** para descargar un informe de [inventario detallado.](device-inventory-report.md)
