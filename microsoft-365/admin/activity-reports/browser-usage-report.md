---
title: Centro de administración de Microsoft 365 informes de uso del explorador
ms.author: waxiaoyu
author: sarahwxy
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: Obtenga información sobre cómo obtener un informe de uso del explorador microsoft mediante el panel Informes de Microsoft 365 en el Centro de administración de Microsoft 365.
ms.openlocfilehash: 2444a93a1a68cd994da19325a8a00af868b6ba16
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2022
ms.locfileid: "67386525"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-browser-usage"></a>Informes de Microsoft 365 en el Centro de administración: uso del explorador microsoft

El panel Informes de Microsoft 365 muestra información general sobre la actividad en los productos de su organización. Le permite profundizar en informes individuales de nivel de producto para proporcionarle información más detallada sobre las actividades dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md). 

El **informe uso de Microsoft Browser** en el Centro de Administración de Microsoft 365 le permite ver si los usuarios acceden a Microsoft 365 servicios en línea a través de Microsoft Edge. Esta información del informe puede ayudarle a migrar su organización a Microsoft Edge. Los informes de uso se basan en un recuento agregado de usuarios de su organización que inician sesión en su cuenta de Microsoft 365 y usan el explorador Microsoft Edge para acceder a los servicios de Microsoft 365.

## <a name="how-to-get-to-the-microsoft-browser-usage-report"></a>Cómo acceder al informe de uso del explorador Microsoft

1. En el centro de administración, vaya a la página <b><a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso de</a></b> **informes**\>.

2. En la página principal del panel, haga clic en el botón **Ver más** de la tarjeta de uso del explorador Microsoft.


## <a name="interpret-the-microsoft-browser-usage-report"></a>Interpretación del informe de uso del explorador Microsoft

:::image type="content" alt-text="Informe de uso del explorador Microsoft." source="../../media/95557c88-24ee-417d-a828-96ba00b17aaf.png" lightbox="../../media/95557c88-24ee-417d-a828-96ba00b17aaf.png":::

El informe **de uso del explorador Microsoft** se puede ver para ver las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. 

El gráfico **Usuarios activos diarios** muestra el recuento diario de usuarios de Microsoft Edge cuando se usa para acceder a los servicios de Microsoft 365.

El gráfico **Usuarios activos** muestra el número total de usuarios que acceden a los servicios de Microsoft 365 mientras usan Microsoft Edge durante el período de tiempo seleccionado.

El informe es interno de la organización con permisos limitados a los administradores de TI con acceso existente a los informes de actividad en el panel de uso del Centro de Administración de Microsoft 365.

> [!NOTE]
> El uso agregado del explorador microsoft y los informes de nivel de usuario están disponibles. La identificación de nivel de usuario se puede [quitar según las directivas de la organización](activity-reports.md#show-user-details-in-the-reports) y se pueden usar [controles de acceso basados en roles](../../admin/add-users/assign-admin-roles.md) para ajustar el acceso al informe.


|Elemento|Descripción|
|:-----|:-----|
|**Username** | Dirección de correo electrónico del usuario que se conectó a los servicios de Microsoft 365 mediante Microsoft Edge.|
| **Microsoft Edge usado**| Muestra una marca de graduación si el usuario de servicios de Microsoft 365 conectado con Microsoft Edge.|

Seleccione el icono **Elegir columnas** para agregar o quitar columnas del informe.

También puede exportar los datos del informe a un archivo de excel .csv seleccionando el vínculo **Exportar** . Esto exporta datos para todos los usuarios y le permite realizar agregaciones, ordenaciones y filtrados sencillos para un análisis posterior. 
