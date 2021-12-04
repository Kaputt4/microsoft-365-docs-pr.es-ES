---
title: Aplicaciones conectadas en Microsoft Defender para endpoint
ms.reviewer: ''
description: Vea las aplicaciones asociadas conectadas que usan el protocolo estándar OAuth 2.0 para autenticar y proporcionar tokens para su uso con Microsoft Defender para las API de punto de conexión.
keywords: partners, aplicaciones, terceros, conexiones, sentinelone, lookout, bitdefender, corrata, morphisec, paloalto, ziften, better mobile
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4dd630dd2b35c2fedc0340cd873ff065b2685b41
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2021
ms.locfileid: "61300651"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a>Aplicaciones conectadas en Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Las aplicaciones conectadas se integran con la plataforma Defender for Endpoint mediante API.

Las aplicaciones usan el protocolo estándar OAuth 2.0 para autenticar y proporcionar tokens para su uso con Microsoft Defender para las API de extremo. Además, las Azure Active Directory (Azure AD) permiten a los administradores de inquilinos establecer un control explícito sobre las API a las que se puede tener acceso mediante la aplicación correspondiente.

Deberá seguir estos pasos [para](/microsoft-365/security/defender-endpoint/apis-intro) usar las API con la aplicación conectada.

En el menú de navegación izquierdo, seleccione **Partners & API** (en **Endpoints**) > **Aplicaciones conectadas**.

## <a name="view-connected-application-details"></a>Ver detalles de la aplicación conectada

La página Aplicaciones conectadas proporciona información sobre las Azure AD conectadas a Microsoft Defender para Endpoint en su organización. Puede revisar el uso de las aplicaciones conectadas: última vista, número de solicitudes en las últimas 24 horas y tendencias de solicitudes en los últimos 30 días.

![Imagen de aplicaciones conectadas.](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a>Editar, volver a configurar o eliminar una aplicación conectada

El **vínculo Abrir configuración de** la aplicación abre la página Azure AD administración de aplicaciones correspondiente en Azure Portal. Desde Azure Portal, puede administrar permisos, reconfigurar o eliminar las aplicaciones conectadas.
