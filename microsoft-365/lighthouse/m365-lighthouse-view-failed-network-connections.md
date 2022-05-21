---
title: Visualización de una conexión de red con errores en un equipo en la nube empresarial en Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolib
- M365-Lighthouse
search.appverid: MET150
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo ver una conexión de red con errores en un equipo en la nube empresarial.
ms.openlocfilehash: 68cae662da8af7ee536a3e0e304c2d46b4f52835
ms.sourcegitcommit: 349f0f54b0397cdd7d8fbb9ef07f1b6654a32d6e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2022
ms.locfileid: "65623739"
---
# <a name="view-an-enterprise-cloud-pc-failed-network-connection-in-microsoft-365-lighthouse"></a>Visualización de una conexión de red con errores en un equipo en la nube empresarial en Microsoft 365 Lighthouse

Microsoft 365 Lighthouse proporciona el estado de conexión entre los inquilinos y Azure Active Directory. Cuando un equipo en la nube tiene una conexión de red errónea, puede ver información detallada en Microsoft Endpoint Manager centro de administración.

## <a name="before-you-begin"></a>Antes de empezar

- Debe ser administrador global en el inquilino del asociado.
- Debe tener acceso de administrador de PC en la nube o lector de PC en la nube para ver los problemas de conexión.

## <a name="view-a-failed-network-connection"></a>Visualización de una conexión de red con errores

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Windows 365**.

2. Seleccione la pestaña **Conexiones de red de Azure** .

3. En el área de resumen de la conexión, seleccione **Conexiones con errores**.

4. En la lista filtrada, seleccione **Ver detalles de conexión en Microsoft Endpoint Manager** junto a la conexión que desea investigar.

5. En Microsoft Endpoint Manager centro de administración, seleccione **Ver detalles** para obtener más información sobre el error.

## <a name="next-steps"></a>Siguientes pasos

Para solucionar problemas de conexión, consulte [el artículo Solución de problemas de conexión de red local](/windows-365/enterprise/troubleshoot-on-premises-network-connection) .

## <a name="related-content"></a>Contenido relacionado

[Control de acceso basado en rol de PC en la nube ](/windows-365/enterprise/role-based-access)(artículo)\
[Unión a dominio de Active Directory](/windows-365/enterprise/troubleshoot-on-premises-network-connection#active-directory-domain-join) (artículo)\
[Azure Active Directory device Sync](/windows-365/enterprise/troubleshoot-on-premises-network-connection#azure-active-directory-device-sync) (artículo)
