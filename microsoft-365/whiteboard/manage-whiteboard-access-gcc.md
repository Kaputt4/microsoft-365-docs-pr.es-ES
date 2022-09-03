---
title: Administración del acceso a Microsoft Whiteboard para entornos GCC
ms.author: v-jdeweese
author: johnddeweese
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.service: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: Obtenga información sobre cómo habilitar, deshabilitar y administrar datos de Pizarra.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 46a4c6db8755f7ee2928828453518acdb2a2eb36
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67597613"
---
# <a name="manage-access-to-microsoft-whiteboard-for-gcc-environments"></a>Administración del acceso a Microsoft Whiteboard para entornos GCC

>[!NOTE]
> Esta guía se aplica a los entornos de la nube comunitaria (GCC) de la administración pública de EE. UU.

Microsoft Whiteboard en OneDrive para la Empresa está habilitado de forma predeterminada para los inquilinos de Microsoft 365 aplicables. Se puede habilitar o deshabilitar en un nivel de todo el inquilino. También debe asegurarse de que **Microsoft Whiteboard Services** está habilitado en las **aplicaciones enterprise** del Centro  >  de **administración de Azure Active Directory**.

Se requieren las siguientes direcciones URL:

- 'https://*.office365.us/'
- 'https://login.microsoftonline.us/'
- 'https://graph.microsoft.us/'
- 'https://graph.microsoftazure.us/'
- 'https://admin.onedrive.us'
- 'https://shell.cdn.office.net/'
- 'https://config.ecs.gov.teams.microsoft.us'
- 'https://tb.events.data.microsoft.com/'

Puede controlar el acceso a Whiteboard de las siguientes maneras:

- Habilite o deshabilite Whiteboard para todo el inquilino mediante el [módulo de PowerShell de SharePoint Online](/microsoft-365/enterprise/manage-sharepoint-online-with-microsoft-365-powershell).

- Mostrar u ocultar pizarra para usuarios específicos en reuniones mediante una directiva de reunión de Microsoft Teams. Seguirá siendo visible a través de la web, los clientes nativos y la aplicación de pestaña Teams.

- Requerir directivas de acceso condicional para acceder a Whiteboard mediante el Centro de administración de Azure Active Directory.

>[!NOTE]
> La directiva de reunión de Teams solo oculta los puntos de entrada de pizarra. No impide que los usuarios usen Whiteboard. Las directivas de acceso condicional impiden el acceso a Whiteboard, pero no oculta los puntos de entrada.

## <a name="enable-or-disable-whiteboard"></a>Habilitación o deshabilitación de Whiteboard

Para habilitar o deshabilitar Whiteboard para el inquilino, siga estos pasos: 

1. Use el [módulo de PowerShell de SharePoint Online](/microsoft-365/enterprise/manage-sharepoint-online-with-microsoft-365-powershell) para habilitar o deshabilitar todas las experiencias fluidas en el inquilino de Microsoft 365.

2. Conéctese a [PowerShell de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

3. Habilite Fluid con el siguiente <code>Set-SPOTenant</code> cmdlet:

   <pre><code class="lang-powershell">Set-SPOTenant -IsWBFluidEnabled $true</code></pre>

El cambio debe tardar aproximadamente 60 minutos en aplicarse en todo el inquilino. Si no ve esta opción, deberá actualizar el módulo.

## <a name="show-or-hide-whiteboard"></a>Mostrar u ocultar pizarra

Para mostrar u ocultar pizarra en reuniones, consulte Configuración de [directivas de reunión](/microsoftteams/meeting-policies-content-sharing).

## <a name="see-also"></a>Vea también

[Administración de datos para Whiteboard: GCC](manage-data-gcc.md)

[Administración del uso compartido para Pizarra: GCC](manage-sharing-gcc.md)

[Administración de clientes para Whiteboard: GCC](manage-clients-gcc.md)