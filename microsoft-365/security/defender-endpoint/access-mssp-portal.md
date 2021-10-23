---
title: Obtener acceso Microsoft 365 Defender portal de clientes de MSSP
description: Obtener acceso Microsoft 365 Defender portal de clientes de MSSP
keywords: proveedor de servicios de seguridad administrados, mssp, configuración, integración
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 23d8c03070ec0a89e86adf8afcdafb78dbb844a7
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2021
ms.locfileid: "60556381"
---
# <a name="access-the-microsoft-365-defender-mssp-customer-portal"></a>Obtener acceso Microsoft 365 Defender portal de clientes de MSSP

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)

> [!NOTE]
> Este conjunto de pasos se dirige al MSSP.

De forma predeterminada, los clientes MSSP tienen acceso Microsoft 365 Defender inquilino mediante la siguiente dirección URL: `https://securitycenter.windows.com/` .

Sin embargo, los MSSP tendrán que usar una dirección URL específica del inquilino en el siguiente formato: para obtener acceso al portal de  `https://securitycenter.windows.com?tid=customer_tenant_id` clientes de MSSP.

En general, los MSSP tendrán que agregarse a cada una de las Azure AD cliente de MSSP que tienen la intención de administrar.

Siga estos pasos para obtener el identificador de inquilino del cliente MSSP y, a continuación, use el identificador para obtener acceso a la dirección URL específica del inquilino:

1. Como MSSP, inicie sesión en Azure AD con sus credenciales.

2. Cambie el directorio al inquilino del cliente de MSSP.

3. Seleccione **Azure Active Directory > propiedades**. Encontrará el identificador de inquilino en el campo Id. de directorio.

4. Para obtener acceso al portal de clientes de MSSP, reemplace el `customer_tenant_id` valor en la siguiente dirección URL: `https://securitycenter.windows.com/?tid=customer_tenant_id` .

## <a name="related-topics"></a>Temas relacionados

- [Conceder acceso a MSSP al portal](grant-mssp-access.md)
- [Configurar notificaciones de alerta](configure-mssp-notifications.md)
- [Capturar alertas del espacio empresarial del cliente](fetch-alerts-mssp.md)
