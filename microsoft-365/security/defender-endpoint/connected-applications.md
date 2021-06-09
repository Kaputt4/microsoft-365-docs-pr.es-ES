---
title: Aplicaciones conectadas en Microsoft Defender para endpoint
ms.reviewer: ''
description: Vea las aplicaciones asociadas conectadas que usan el protocolo estándar OAuth 2.0 para autenticar y proporcionar tokens para su uso con Microsoft Defender para las API de punto de conexión.
keywords: partners, aplicaciones, terceros, conexiones, sentinelone, lookout, bitdefender, corrata, morphisec, paloalto, ziften, better mobile
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 06ef716e9deee7b20e8615bd22c93130ee18b77f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845587"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a>Aplicaciones conectadas en Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Las aplicaciones conectadas se integran con la plataforma Defender for Endpoint mediante API. 

Las aplicaciones usan el protocolo estándar OAuth 2.0 para autenticar y proporcionar tokens para su uso con Microsoft Defender para las API de extremo.  Además, las Azure Active Directory (Azure AD) permiten a los administradores de inquilinos establecer un control explícito sobre las API a las que se puede tener acceso mediante la aplicación correspondiente.
 
Deberá seguir estos pasos [para](/microsoft-365/security/defender-endpoint/apis-intro) usar las API con la aplicación conectada.
 
## <a name="access-the-connected-application-page"></a>Acceder a la página de la aplicación conectada
En el menú de navegación izquierdo, seleccione **Partners & API**  >  **conectadas aplicaciones de AAD**.

 
## <a name="view-connected-application-details"></a>Ver detalles de la aplicación conectada
La página Aplicaciones conectadas proporciona información sobre las aplicaciones de Azure AD conectadas a Microsoft Defender para endpoint en su organización. Puede revisar el uso de las aplicaciones conectadas: última vista, número de solicitudes en las últimas 24 horas y tendencias de solicitudes en los últimos 30 días.

![Imagen de aplicaciones conectadas](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a>Editar, volver a configurar o eliminar una aplicación conectada
El **vínculo Abrir configuración de la** aplicación abre la página de administración de aplicaciones de Azure AD correspondiente en Azure Portal. Desde Azure Portal, puede administrar permisos, reconfigurar o eliminar las aplicaciones conectadas.
