---
title: Obtener acceso Microsoft 365 Defender portal de clientes de MSSP
description: Obtener acceso Microsoft 365 Defender portal de clientes de MSSP
keywords: proveedor de servicios de seguridad administrados, mssp, configuración, integración
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8583b28adecd892ec6875faa934fd7ab08e5db11
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339591"
---
# <a name="access-the-microsoft-365-defender-mssp-customer-portal"></a>Obtener acceso Microsoft 365 Defender portal de clientes de MSSP

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)

>¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
>Este conjunto de pasos se dirige al MSSP. 

De forma predeterminada, los clientes MSSP tienen acceso Centro de seguridad de Microsoft Defender inquilino a través de la siguiente dirección URL: `https://securitycenter.windows.com` .
 

Sin embargo, los MSSP tendrán que usar una dirección URL específica del inquilino en el siguiente formato: para obtener acceso al portal de  `https://securitycenter.windows.com?tid=customer_tenant_id` clientes de MSSP. 

En general, los MSSP tendrán que agregarse a cada uno de los Azure AD del cliente de MSSP que pretenden administrar.


Siga estos pasos para obtener el identificador de inquilino del cliente MSSP y, a continuación, use el identificador para obtener acceso a la dirección URL específica del inquilino:

1. Como MSSP, inicie sesión en Azure AD con sus credenciales. 

2. Cambie el directorio al inquilino del cliente de MSSP.

3.  Seleccione **Azure Active Directory > propiedades**. Encontrará el identificador de inquilino en el campo Id. de directorio. 

4. Para obtener acceso al portal de clientes de MSSP, reemplace el `customer_tenant_id` valor en la siguiente dirección URL: `https://securitycenter.windows.com?tid=customer_tenant_id` .


## <a name="related-topics"></a>Temas relacionados
- [Conceder acceso a MSSP al portal](grant-mssp-access.md)
- [Configurar notificaciones de alerta](configure-mssp-notifications.md)
- [Capturar alertas del espacio empresarial del cliente](fetch-alerts-mssp.md)
