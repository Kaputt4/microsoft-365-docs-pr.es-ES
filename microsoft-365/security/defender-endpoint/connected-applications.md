---
title: Aplicaciones conectadas en Microsoft Defender para punto de conexión
ms.reviewer: ''
description: Vea las aplicaciones asociadas conectadas que usan el protocolo estándar de OAuth 2.0 para autenticar y proporcionar tokens para su uso con Microsoft Defender para punto de conexión API.
keywords: partners, aplicaciones, terceros, conexiones, sentinelone, lookout, bitdefender, corrata, morphisec, paloalto, ziften, better mobile
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
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 4fadae99a563516869d4652645ff3594b73d2073
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67694951"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a>Aplicaciones conectadas en Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Las aplicaciones conectadas se integran con la plataforma Defender para punto de conexión mediante LAS API.

Las aplicaciones usan el protocolo estándar OAuth 2.0 para autenticar y proporcionar tokens para su uso con las API de Microsoft Defender para punto de conexión. Además, las aplicaciones de Azure Active Directory (Azure AD) permiten a los administradores de inquilinos establecer un control explícito sobre las API a las que se puede acceder mediante la aplicación correspondiente.

Deberá seguir [estos pasos](/microsoft-365/security/defender-endpoint/apis-intro) para usar las API con la aplicación conectada.

En el menú de navegación izquierdo, seleccione **Asociados & API** (en Puntos de **conexión**) > **Aplicaciones conectadas**.

## <a name="view-connected-application-details"></a>Visualización de los detalles de la aplicación conectada

La página Aplicaciones conectadas proporciona información sobre las aplicaciones de Azure AD conectadas a Microsoft Defender para punto de conexión de la organización. Puede revisar el uso de las aplicaciones conectadas: última vista, número de solicitudes en las últimas 24 horas y tendencias de solicitudes en los últimos 30 días.

:::image type="content" source="images/connected-apps.png" alt-text="Las aplicaciones conectadas" lightbox="images/connected-apps.png":::
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a>Edición, reconfiguración o eliminación de una aplicación conectada

El vínculo **Abrir configuración de la aplicación** abre la página de administración de aplicaciones de Azure AD correspondiente en el Azure Portal. Desde el Azure Portal, puede administrar permisos, volver a configurar o eliminar las aplicaciones conectadas.
