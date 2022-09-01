---
title: Administración del acceso a Microsoft Whiteboard para entornos de GCC High
ms.author: v-jdeweese
author: johnddeweese
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: Obtenga información sobre cómo habilitar, deshabilitar y administrar datos de Pizarra.
ms.openlocfilehash: 7034aba1ea94bcc87a21f8378595ce984a74769f
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67496733"
---
# <a name="manage-access-to-microsoft-whiteboard-for-gcc-high-environments"></a>Administración del acceso a Microsoft Whiteboard para entornos de GCC High

>[!NOTE]
> Esta guía se aplica a los entornos altos de la nube de la comunidad del gobierno de EE. UU. (GCC).

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

- Mostrar u ocultar pizarra para usuarios específicos en reuniones mediante una directiva de reunión de Teams. Seguirá siendo visible a través de la web, los clientes nativos y la aplicación de pestaña Teams.

- Requerir directivas de acceso condicional para acceder a Whiteboard mediante el Centro de administración de Azure Active Directory.

>[!NOTE]
> La pizarra en OneDrive para la Empresa no aparece en el Centro de administración de Microsoft 365. La directiva de reunión de Teams solo oculta los puntos de entrada de pizarra, no impide que los usuarios usen Pizarra. Las directivas de acceso condicional impiden el acceso a Whiteboard, pero no oculta los puntos de entrada.

## <a name="enable-or-disable-whiteboard"></a>Habilitación o deshabilitación de Whiteboard

Para habilitar o deshabilitar Whiteboard para el inquilino, siga estos pasos: 

1. Use el [módulo de PowerShell de SharePoint Online](/microsoft-365/enterprise/manage-sharepoint-online-with-microsoft-365-powershell) para habilitar o deshabilitar todas las experiencias fluidas en el inquilino de Microsoft 365.

2. Conéctese a [PowerShell de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

3. Habilite Fluid con el siguiente <code>Set-SPOTenant</code> cmdlet:

   <pre><code class="lang-powershell">Set-SPOTenant -IsWBFluidEnabled $true</code></pre>

El cambio debe tardar aproximadamente 60 minutos en aplicarse en todo el inquilino. Si no ve esta opción, deberá actualizar el módulo.

>[!NOTE]
> De forma predeterminada, whiteboard está habilitado. Si se ha deshabilitado en las aplicaciones empresariales de Azure Active Directory, whiteboard en OneDrive para la Empresa no funcionará.

## <a name="show-or-hide-whiteboard"></a>Mostrar u ocultar pizarra

Para mostrar u ocultar pizarra en reuniones, consulte Configuración de [directivas de reunión](/microsoftteams/meeting-policies-content-sharing).

## <a name="see-also"></a>Vea también

[Administración de datos para Pizarra: GCC High](manage-data-gcc-high.md)

[Administración del uso compartido para Pizarra: GCC High](manage-sharing-gcc-high.md)

[Administración de clientes para Whiteboard: GCC High](manage-clients-gcc-high.md)




