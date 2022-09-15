---
title: Acceso al portal de clientes Microsoft 365 Defender MSSP
description: Acceso al portal de clientes Microsoft 365 Defender MSSP
keywords: proveedor de servicios de seguridad administrados, mssp, configure, integration
ms.service: microsoft-365-security
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
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: e9ce4b06816e6b7e90b7878803fb985ef16e984a
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67698681"
---
# <a name="access-the-microsoft-365-defender-mssp-customer-portal"></a>Acceso al portal de clientes Microsoft 365 Defender MSSP

**Se aplica a:**
- [plan 1 de Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [plan 2 de Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)

> [!NOTE]
> Este conjunto de pasos se dirige al MSSP.

De forma predeterminada, los clientes de MSSP acceden a su inquilino de Microsoft 365 Defender a través de la siguiente dirección URL: `https://security.microsoft.com/`.

Sin embargo, los MSSP tendrán que usar una dirección URL específica del inquilino en el siguiente formato:  `https://security.microsoft.com?tid=customer_tenant_id` para acceder al portal del cliente de MSSP.

En general, los MSSP deberán agregarse a cada azure AD del cliente de MSSP que pretenden administrar.

Siga estos pasos para obtener el identificador de inquilino del cliente de MSSP y, a continuación, use el identificador para acceder a la dirección URL específica del inquilino:

1. Como MSSP, inicie sesión en Azure AD con sus credenciales.

2. Cambie el directorio al inquilino del cliente de MSSP.

3. Seleccione **Azure Active Directory > Propiedades**. Encontrará el identificador de inquilino en el campo Id. de directorio.

4. Acceda al portal del cliente de MSSP reemplazando el `customer_tenant_id` valor en la siguiente dirección URL: `https://security.microsoft.com/?tid=customer_tenant_id`.

## <a name="related-topics"></a>Temas relacionados

- [Conceder acceso a MSSP al portal](grant-mssp-access.md)
- [Configurar notificaciones de alerta](configure-mssp-notifications.md)
- [Capturar alertas del espacio empresarial del cliente](fetch-alerts-mssp.md)
