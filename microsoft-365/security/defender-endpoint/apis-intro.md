---
title: Acceder a las API de Microsoft Defender para punto de conexión
ms.reviewer: ''
description: Descubra cómo puede usar las API para automatizar flujos de trabajo e innovar en función de las capacidades de Microsoft Defender para endpoints
keywords: apis, api, wdatp, api abierta, microsoft defender para la api de punto de conexión, microsoft defender ATP, api pública, apis admitidas, alertas, dispositivo, usuario, dominio, ip, archivo, caza avanzada, consulta
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

> ¿Desea experimentar Microsoft Defender para Endpoint? [Regístrese para una prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



Defender for Endpoint expone gran parte de sus datos y acciones a través de un conjunto de API programáticas. Esas API le permitirán automatizar flujos de trabajo e innovar en función de las capacidades de Defender for Endpoint. El acceso a la API requiere autenticación OAuth2.0. Para obtener más información, consulte [Código de autorización de OAuth 2.0 Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Vea este vídeo para obtener una visión general rápida de las API de Defender for Endpoint. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

En general, deberá seguir los siguientes pasos para usar las API:
- Crear una [aplicación AAD](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)
- Obtenga un token de acceso con esta aplicación
- Use el token para obtener acceso a Defender para endpoint API


Puede acceder a Defender para endpoint API con **contexto de aplicación** o contexto de **usuario**.

- **Contexto de aplicación: (recomendado)** <br>
    Utilizado por aplicaciones que se ejecutan sin un usuario que ha iniciado sesión presente. por ejemplo, aplicaciones que se ejecutan como servicios en segundo plano o demonios.

    Pasos que deben tomarse para tener acceso a defender para la API de punto de conexión con el contexto de la aplicación:

  1. Cree una aplicación web AAD.
  2. Asigne el permiso deseado a la aplicación, por ejemplo, "Leer alertas", "Aislar máquinas". 
  3. Cree una clave para esta aplicación.
  4. Obtenga token con la aplicación con su clave.
  5. Use el token para tener acceso a la API de Microsoft Defender para Endpoint

     Para obtener más información, consulte [Obtener acceso con el contexto de la aplicación.](exposed-apis-create-app-webapp.md)


- **Contexto del usuario:** <br>
    Se utiliza para realizar acciones en la API en nombre de un usuario.

    Pasos a seguir para acceder a defender para endpoint API con contexto de aplicación:

  1. Cree AAD Native-Application.
  2. Asigne el permiso deseado a la aplicación, por ejemplo, "Leer alertas", 'Aislar máquinas', etc. 
  3. Obtenga token con la aplicación con credenciales de usuario.
  4. Use el token para tener acceso a la API de Microsoft Defender para Endpoint

     Para obtener más información, consulte [Obtener acceso con el contexto del usuario.](exposed-apis-create-app-nativeapp.md)


## <a name="related-topics"></a>Temas relacionados
- [Microsoft Defender para las API de endpoints](exposed-apis-list.md)
- [Acceda a Microsoft Defender para endpoint con contexto de aplicación](exposed-apis-create-app-webapp.md)
- [Acceda a Microsoft Defender para endpoint con contexto de usuario](exposed-apis-create-app-nativeapp.md)
