---
title: Trabajar con informes
description: Los distintos informes disponibles en Escritorio administrado de Microsoft
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1fb29ef7555bb3e7ff2024090b3b7cf953a2de10
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213174"
---
# <a name="work-with-reports"></a>Trabajar con informes

La consola Microsoft Endpoint Manager reúne informes de varios productos en una única ubicación para ayudarle a supervisar e investigar problemas con la configuración y los dispositivos de la organización de Azure AD ("inquilino"). El escritorio administrado de  Microsoft tiene una sección en el menú Informes donde puede encontrar informes específicos de Escritorio administrado de Microsoft administración de los dispositivos que ha registrado. Además, en varias ubicaciones de Microsoft Endpoint Manager puede filtrar informes de otros grupos de productos para incluir o excluir específicamente los dispositivos administrados por Escritorio administrado de Microsoft. 

## <a name="microsoft-managed-desktop-reports"></a>Escritorio administrado de Microsoft informes
Escritorio administrado de Microsoft proporciona varios informes y paneles que los administradores de TI de su organización pueden usar para comprender diversos aspectos de la población de dispositivos.Para encontrar estos informes,  vaya a Dispositivos administrados en la *sección* Escritorio administrado de Microsoft del **menú** Informes de Microsoft Endpoint Manager. 

En la **pestaña Resumen,** encontrarás métricas rápidas sobre las actualizaciones de dispositivos. Si selecciona **Ver detalles de** cualquier métrica, podrá descargar información adicional para el análisis sin conexión, incluido el conjunto de datos subyacente de la métrica.

Al seleccionar la **pestaña Informes,** verá descripciones de los informes detallados disponibles. Estos informes son más completos y admiten la visualización y el filtrado de los datos en el portal, así como la exportación de los datos subyacentes para el análisis o distribución sin conexión. Los siguientes informes están disponibles hoy:
- El [ **informe de estado del** dispositivo](device-status-report.md) (*en* versión preliminar ) muestra el uso del servicio Escritorio administrado de Microsoft basado en la actividad y el uso del dispositivo. 
- Puedes usar la **tendencia de estado** del dispositivo ( en versión preliminar ) para supervisar las tendencias en el estado del dispositivo en los últimos 60 días para los dispositivos Escritorio administrado de Microsoft dispositivos. Las tendencias pueden ayudarte a asociar el estado del dispositivo con otros cambios con el tiempo, por ejemplo, nuevas implementaciones. 
- El [ **Windows actualizaciones de**](security-updates-report.md) seguridad *(* en versión preliminar ) muestra cómo se liberan Windows actualizaciones de seguridad en todos los Escritorio administrado de Microsoft dispositivos.
- El **informe de uso de la** aplicación proporciona información sobre el uso típico de la aplicación en Escritorio administrado de Microsoft dispositivos. Para que los dispositivos proporcionen datos a este informe, deben establecerse en el nivel de datos de diagnóstico opcional.

## <a name="endpoint-analytics"></a>Análisis de puntos de conexión
Escritorio administrado de Microsoft está integrado con endpoint [analytics.](/mem/analytics/overview) Estos informes le proporcionan información para medir cómo funciona su organización y la calidad de la experiencia que se ofrece a los usuarios. El análisis de extremos se encuentra en **el menú** Informes [de Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Para pivotar una puntuación para incluir solo los dispositivos  administrados por Escritorio administrado de Microsoft ir a cualquier informe, seleccione la lista desplegable Filtro y, a continuación, **seleccione Escritorio administrado de Microsoft dispositivos**.

Si endpoint analytics no se configuró automáticamente para su organización de Azure AD ("inquilino") durante la inscripción, puede hacerlo usted mismo. Para obtener más información, vea [Onboard in the Endpoint analytics portal](/mem/analytics/enroll-intune#bkmk_onboard). Puedes inscribir todos los dispositivos o, si quieres incluir solo dispositivos Escritorio administrado de Microsoft, selecciona los grupos de dispositivos de lugar de trabajo modernos para Test, First, Fast y Broad.  Estos informes pueden requerir permisos diferentes. Para obtener más información, vea [Permissions](/mem/analytics/overview#permissions) to ensure you have roles appropriately assigned.

> [!NOTE]
> Para respetar mejor la privacidad del usuario, debe haber más de 10 dispositivos Escritorio administrado de Microsoft inscritos con endpoint analytics para usar este filtro.

## <a name="intune-reports"></a>Informes de Intune
Microsoft Intune es uno de los servicios que usamos para administrar dispositivos en su nombre. En algunos casos, puede resultar útil usar informes de Intune para supervisar específicamente la administración de los Escritorio administrado de Microsoft dispositivos. O quizás quieras excluir los dispositivos que administramos de un informe que usas para administrar otros dispositivos. Los siguientes informes te permiten filtrar la funcionalidad para incluir o excluir Escritorio administrado de Microsoft dispositivos.

- [Todos los dispositivos](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Cumplimiento de dispositivos](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Dispositivos no compatibles](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Los Escritorio administrado de Microsoft personalizados garantizan el acceso solo a los Escritorio administrado de Microsoft informes. Para obtener acceso a otras partes de Microsoft Endpoint Manager, como **Todos** los dispositivos, vea Control de acceso basado en roles [con Microsoft Intune](/mem/intune/fundamentals/role-based-access-control). 

## <a name="microsoft-managed-desktop-inventory-data"></a>Escritorio administrado de Microsoft de inventario

Además de los demás informes, puedes exportar información sobre los dispositivos administrados por Escritorio administrado de Microsoft. En la **vista Dispositivos** del área **Dispositivos** de Microsoft Endpoint Manager, use la pestaña Exportar **todo** para descargar un informe de [inventario detallado.](device-inventory-report.md)
