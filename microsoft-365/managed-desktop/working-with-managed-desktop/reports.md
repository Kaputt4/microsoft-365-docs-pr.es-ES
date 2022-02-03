---
title: Trabajar con informes
description: Los distintos informes disponibles en Microsoft Managed Desktop
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: edf1025008fe13161e32a1a824413fd5eda0f5ff
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2022
ms.locfileid: "62322378"
---
# <a name="work-with-reports"></a>Trabajar con informes

La consola Microsoft Endpoint Manager reúne informes de varios productos en una única ubicación para ayudarle a supervisar e investigar problemas con la configuración y los dispositivos de la organización Azure AD ("inquilino").

Microsoft Managed Desktop tiene una sección **en el menú** Informes donde puede encontrar informes específicos de la administración de Microsoft Managed Desktop de los dispositivos registrados. En varias ubicaciones de Microsoft Endpoint Manager, puede filtrar informes de otros grupos de productos. Puede incluir o excluir dispositivos administrados por Microsoft Managed Desktop.

## <a name="microsoft-managed-desktop-reports"></a>Informes de Escritorio administrado de Microsoft

Microsoft Managed Desktop proporciona varios informes y paneles. Los administradores de TI, en su organización, pueden usar estos informes y paneles para comprender diversos aspectos de la población de dispositivos. En Microsoft Endpoint Manager, vaya a la sección Informes, en Escritorio administrado de Microsoft, seleccione Dispositivos administrados.

En la **pestaña Resumen** , encontrarás métricas rápidas sobre las actualizaciones de dispositivos. Seleccione **Ver detalles de** cualquier métrica para descargar información adicional para el análisis sin conexión, incluido el conjunto de datos subyacente para la métrica.

Al seleccionar la **pestaña Informes** , verá descripciones de los informes detallados disponibles. Estos informes son más completos y admiten la visualización y el filtrado de datos en el portal. También puede exportar los datos subyacentes para el análisis o distribución sin conexión. Los siguientes informes están disponibles hoy:

| Informe | Descripción |
| ------ | ------ |
| [**Informe de estado** del dispositivo](device-status-report.md) (*en versión preliminar*) | Este informe muestra el uso del servicio de Escritorio administrado de Microsoft en función de la actividad y el uso del dispositivo. |
| **Tendencia de estado del dispositivo** (*en versión preliminar*) | Esto supervisa las tendencias del estado del dispositivo en los últimos 60 días para los dispositivos de Escritorio administrado de Microsoft. Las tendencias pueden ayudarte a asociar el estado del dispositivo con otros cambios con el tiempo, por ejemplo, nuevas implementaciones. |
| [**Windows de actualizaciones de seguridad**](security-updates-report.md) (*en versión preliminar*) | Este informe muestra cómo se Windows actualizaciones de seguridad en todos los dispositivos de Escritorio administrado de Microsoft. |
| [**Informe de uso de** aplicaciones](app-usage-report.md) | Este informe proporciona información sobre el uso típico de la aplicación en los dispositivos de Escritorio administrado de Microsoft. Para que los dispositivos proporcionen datos a este informe, deben establecerse en el nivel de datos de diagnóstico opcional. |

## <a name="endpoint-analytics"></a>Análisis de puntos de conexión

Microsoft Managed Desktop ahora está integrado con endpoint [analytics](/mem/analytics/overview). Estos informes le proporcionan información para medir cómo funciona su organización y la calidad de la experiencia que se ofrece a los usuarios. Puede encontrar Análisis de extremos en el **menú Informes** de [Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Para pivotar una puntuación para incluir solo los dispositivos administrados por Microsoft Managed Desktop, vaya a cualquier  informe, seleccione el menú desplegable Filtro y, a continuación, seleccione **Dispositivos de Escritorio administrado de Microsoft**.

Si endpoint analytics no se configuró automáticamente para su Azure AD organización ("inquilino") durante la inscripción, puede hacerlo usted mismo. Para obtener más información, consulte [Incorporación en el portal de análisis de puntos de conexión](/mem/analytics/enroll-intune#bkmk_onboard). Puedes inscribir todos los dispositivos o, si quieres incluir solo dispositivos de Escritorio administrado de Microsoft, selecciona los grupos  de dispositivos modernos del lugar de trabajo para Test, First, Fast y Broad. Estos informes pueden requerir permisos diferentes. Para obtener más información, vea [Permissions](/mem/analytics/overview#permissions) to ensure you have roles appropriately assigned.

> [!NOTE]
> Para respetar mejor la privacidad del usuario, debe haber más de 10 dispositivos de Escritorio administrado de Microsoft inscritos con análisis de puntos de conexión para usar este filtro.

## <a name="intune-reports"></a>Informes de Intune

Microsoft Intune es uno de los servicios que usamos para administrar dispositivos en su nombre. En algunos casos, puede resultar útil usar informes de Intune para supervisar específicamente la administración de los dispositivos de Escritorio administrado de Microsoft. Puedes excluir los dispositivos que administramos del informe que usas para administrar otros dispositivos. Los siguientes informes permiten filtrar la funcionalidad para incluir o excluir dispositivos de Escritorio administrado de Microsoft.

- [Todos los dispositivos](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Cumplimiento de dispositivos](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Dispositivos no conformes](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Los roles personalizados de Escritorio administrado de Microsoft garantizan el acceso solo a los informes de Escritorio administrado de Microsoft. Para obtener acceso a otras partes de Microsoft Endpoint Manager, como **Todos** los dispositivos, consulte Control de acceso basado en roles [con Microsoft Intune](/mem/intune/fundamentals/role-based-access-control).

## <a name="microsoft-managed-desktop-inventory-data"></a>Datos de inventario de Escritorio administrado de Microsoft

Además de los demás informes, puede exportar información sobre los dispositivos administrados por Microsoft Managed Desktop. En Microsoft Endpoint Manager, vaya a la sección Dispositivos, en Escritorio administrado de Microsoft, seleccione  Dispositivos y use  la pestaña Exportar todo para [descargar un informe de inventario detallado](device-inventory-report.md).
