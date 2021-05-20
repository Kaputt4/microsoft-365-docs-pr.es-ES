---
title: Acceder a las API de Microsoft Defender para punto de conexión
ms.reviewer: ''
description: Obtenga información sobre cómo usar las API para automatizar flujos de trabajo e innovar en función de las capacidades de Microsoft Defender para puntos de conexión
keywords: apis, api, wdatp, open api, microsoft defender para la api de punto de conexión, atp de microsoft defender, api pública, api admitida, alertas, dispositivo, usuario, dominio, ip, archivo, búsqueda avanzada, consulta
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: a91a401d5d57c7757bc043178c95dc42e7733b41
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571834"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>Acceder a las API de Microsoft Defender para punto de conexión 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


**Se aplica a:** 
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



Defender for Endpoint expone gran parte de sus datos y acciones a través de un conjunto de API programáticas. Estas API le permitirán automatizar flujos de trabajo e innovar en función de las capacidades de Defender para endpoints. El acceso a la API requiere autenticación de OAuth2.0. Para obtener más información, vea Código de autorización [de OAuth 2.0 Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Vea este vídeo para obtener una introducción rápida a las API de Defender para Endpoint. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

En general, deberá seguir los pasos siguientes para usar las API:
- Crear una [aplicación de AAD](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)
- Obtener un token de acceso con esta aplicación
- Usar el token para obtener acceso a la API de Defender for Endpoint


Puede obtener acceso a defender para la API de extremo con **contexto de aplicación o** contexto de **usuario.**

- **Contexto de aplicación: (recomendado)** <br>
    Se usa en aplicaciones que se ejecutan sin que haya un usuario que haya iniciado sesión. por ejemplo, aplicaciones que se ejecutan como servicios en segundo plano o demonios.

    Pasos que deben seguirse para obtener acceso a la API de Defender para Endpoint con el contexto de la aplicación:

  1. Crear una aplicación web de AAD.
  2. Asigne el permiso deseado a la aplicación, por ejemplo, "Leer alertas", "Aislar máquinas". 
  3. Cree una clave para esta aplicación.
  4. Obtener token con la aplicación con su clave.
  5. Usar el token para obtener acceso a la API de Microsoft Defender para endpoint

     Para obtener más información, vea [Obtener acceso con contexto de aplicación](exposed-apis-create-app-webapp.md).


- **Contexto de usuario:** <br>
    Se usa para realizar acciones en la API en nombre de un usuario.

    Pasos a seguir para obtener acceso a la API de Defender for Endpoint con el contexto de la aplicación:

  1. Crear una aplicación nativa de AAD.
  2. Asigne el permiso deseado a la aplicación, por ejemplo, "Leer alertas", "Aislar máquinas", etc. 
  3. Obtener token con la aplicación con credenciales de usuario.
  4. Usar el token para obtener acceso a la API de Microsoft Defender para endpoint

     Para obtener más información, vea [Obtener acceso con contexto de usuario](exposed-apis-create-app-nativeapp.md).


## <a name="related-topics"></a>Temas relacionados
- [Microsoft Defender para api de punto de conexión](exposed-apis-list.md)
- [Access Microsoft Defender for Endpoint with application context](exposed-apis-create-app-webapp.md)
- [Access Microsoft Defender for Endpoint with user context](exposed-apis-create-app-nativeapp.md)
