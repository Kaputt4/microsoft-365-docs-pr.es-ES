---
title: Visualización de una conexión de red con errores en un equipo en la nube empresarial en Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms.reviewer: katmartin
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolib
- M365-Lighthouse
search.appverid: MET150
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo ver una conexión de red con errores en un equipo en la nube empresarial.
ms.openlocfilehash: 9d4fc475408c1567298e2f91f260ca99157c6e13
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68662541"
---
# <a name="view-an-enterprise-cloud-pc-failed-network-connection-in-microsoft-365-lighthouse"></a>Visualización de una conexión de red con errores en un equipo en la nube empresarial en Microsoft 365 Lighthouse

Microsoft 365 Lighthouse proporciona el estado de conexión entre los inquilinos del cliente y Azure Active Directory (Azure AD). Cuando un equipo en la nube tiene una conexión de red errónea, puede ver información detallada en el Centro de administración de Microsoft Endpoint Manager.

## <a name="before-you-begin"></a>Antes de empezar

- Debe ser administrador global en el inquilino del asociado.
- Debe tener acceso de administrador de PC en la nube o lector de PC en la nube para ver los problemas de conexión.

## <a name="view-a-failed-network-connection"></a>Visualización de una conexión de red con errores

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Dispositivos** >  **Windows 365**.

2. Seleccione la pestaña **Conexiones de red de Azure** .

3. En la barra de anotaciones de recuento de colores, seleccione **Conexiones con errores**.

4. En la lista filtrada, seleccione **Ver detalles de conexión en Microsoft Endpoint Manager** junto a la conexión que desea investigar.

5. En el Centro de administración de Microsoft Endpoint Manager, seleccione **Ver detalles** para obtener más información sobre el error.

## <a name="next-steps"></a>Pasos siguientes

Para solucionar problemas de conexión, consulte [Solución de problemas de conexión de red local](/windows-365/enterprise/troubleshoot-on-premises-network-connection).

## <a name="related-content"></a>Contenido relacionado

[Control de acceso basado en rol de PC en la nube ](/windows-365/enterprise/role-based-access)(artículo)\
[Unión a dominio de Active Directory](/windows-365/enterprise/troubleshoot-on-premises-network-connection#active-directory-domain-join) (artículo)\
[Sincronización de dispositivos de Azure Active Directory](/windows-365/enterprise/troubleshoot-on-premises-network-connection#azure-active-directory-device-sync) (artículo)
