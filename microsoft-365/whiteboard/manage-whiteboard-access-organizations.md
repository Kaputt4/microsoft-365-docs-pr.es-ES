---
title: Administración del acceso a La pizarra de Microsoft para su organización
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
description: Obtenga información sobre cómo configurar Microsoft Whiteboard para su organización en el Centro de administración de Microsoft 365.
ms.openlocfilehash: 12c16c428d6cd03459d6de4bb4e372d471b1ba36
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2022
ms.locfileid: "67369847"
---
# <a name="manage-access-to-microsoft-whiteboard-for-your-organization"></a>Administración del acceso a La pizarra de Microsoft para su organización

>[!NOTE]
> Este artículo se aplica a las organizaciones empresariales o educativas que usan Whiteboard. En el caso de los entornos de GCC High del gobierno de EE. UU., consulte [Administración del acceso a Microsoft Whiteboard para entornos de GCC High](manage-whiteboard-access-gcc-high.md).

Microsoft Whiteboard es un lienzo de colaboración visual en el que se reúnen personas, contenido e ideas. Microsoft Whiteboard en OneDrive para la Empresa está habilitado de forma predeterminada para los inquilinos de Microsoft 365 aplicables. Se puede habilitar o deshabilitar en un nivel de todo el inquilino. También debe asegurarse de que **Microsoft Whiteboard Services** está habilitado en las **aplicaciones enterprise** del Centro  >  de **administración de Azure Active Directory**.

La pizarra se ajusta a los estándares globales, incluidas las cláusulas SOC 1, SOC 2, ISO 27001, HIPAA y MODELO de la UE. 

La siguiente configuración de administrador es necesaria para Whiteboard:

- La pizarra se debe habilitar globalmente en el Centro de administración de Microsoft 365.

- El <code>Set-SPOTenant -IsWBFluidEnabled</code> cmdlet debe estar habilitado mediante [PowerShell de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

Puede controlar el acceso a Whiteboard de las siguientes maneras:

- Habilite o deshabilite Whiteboard para todo el inquilino mediante el Centro de administración de Microsoft 365.

- Mostrar u ocultar pizarra para usuarios específicos en reuniones mediante una directiva de reunión de Teams. Seguirá siendo visible a través de la web, los clientes nativos y la aplicación de pestaña Teams.

- Requerir directivas de acceso condicional para acceder a Whiteboard mediante el Centro de administración de Azure Active Directory.

>[!NOTE]
> Las directivas de reunión de Teams solo ocultan los puntos de entrada de pizarra; no impide que los usuarios usen Whiteboard. Las directivas de acceso condicional impiden cualquier acceso a Whiteboard, pero no oculta los puntos de entrada.

## <a name="enable-or-disable-whiteboard"></a>Habilitación o deshabilitación de Whiteboard

Para habilitar o deshabilitar Whiteboard para el inquilino, siga estos pasos:

1. Vaya al Centro de administración de Microsoft 365.

2. En la página principal del centro de administración, en el cuadro Buscar de la parte superior derecha, escriba *Pizarra*.

3. En los resultados de la búsqueda, seleccione **Configuración de pizarra**.

4. En el panel Pizarra, active **o desactive Activar pizarra para toda la organización** en **Activado**.

5. Haga clic en **Guardar**.

6. Conéctese a [PowerShell de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

7. Habilite Fluid con el siguiente <code>Set-SPOTenant</code> cmdlet:

   <pre><code class="lang-powershell">Set-SPOTenant -IsWBFluidEnabled $true</code></pre>
 
## <a name="show-or-hide-whiteboard"></a>Mostrar u ocultar pizarra

Para mostrar u ocultar pizarra en reuniones, consulte Configuración de [directivas de reunión](/microsoftteams/meeting-policies-content-sharing). 

## <a name="prevent-access-to-whiteboard"></a>Impedir el acceso a whiteboard

Para evitar el acceso a Whiteboard para usuarios específicos, consulte [Creación de una directiva de acceso condicional](/azure/active-directory/conditional-access/concept-conditional-access-policies).

## <a name="see-also"></a>Vea también

[Administración de datos para Whiteboard](manage-data-organizations.md)

[Administración del uso compartido para Whiteboard](manage-sharing-organizations.md)

[Implementación de pizarra en Windows](deploy-on-windows-organizations.md)
