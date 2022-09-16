---
title: Acceder a las API de Microsoft Defender para punto de conexión
ms.reviewer: ''
description: Obtenga información sobre cómo puede usar las API para automatizar flujos de trabajo e innovar en función de las funcionalidades de Microsoft Defender para punto de conexión
keywords: apis, api, wdatp, open api, microsoft defender for endpoint api, atp de Microsoft Defender, API pública, API admitidas, alertas, dispositivo, usuario, dominio, ip, archivo, búsqueda avanzada, consulta
ms.service: microsoft-365-security
ms.subservice: mde
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
ms.custom: api
search.appverid: met150
ms.openlocfilehash: d4e009f321e5990223f6c8cf49c260ee12908bd3
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "67740717"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>Acceder a las API de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender para Empresas](../defender-business/index.yml)

> [!IMPORTANT]
> Las funcionalidades avanzadas de búsqueda no se incluyen en Defender para empresas. Consulte [Comparar Microsoft Defender para Empresas con los planes 1 y 2 de Microsoft Defender para punto de conexión](../defender-business/compare-mdb-m365-plans.md#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2).

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Defender para punto de conexión expone gran parte de sus datos y acciones a través de un conjunto de API mediante programación. Esas API le permitirán automatizar flujos de trabajo e innovar en función de las funcionalidades de Defender para punto de conexión. El acceso a la API requiere la autenticación de OAuth2.0. Para obtener más información, vea [Flujo de código de autorización de OAuth 2.0](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Vea este vídeo para obtener una introducción rápida a las API de Defender para punto de conexión.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4d73M]

En general, deberá realizar los pasos siguientes para usar las API:

- Creación de una [aplicación de AAD](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)
- Obtención de un token de acceso mediante esta aplicación
- Uso del token para acceder a Defender for Endpoint API

Puede acceder a defender para la API de punto de conexión con **contexto de aplicación** o **contexto de usuario**.

- **Contexto de la aplicación: (recomendado)**

  Lo usan las aplicaciones que se ejecutan sin un usuario que ha iniciado sesión presente. por ejemplo, las aplicaciones que se ejecutan como servicios en segundo plano o demonios.

  Pasos que deben realizarse para acceder a Defender for Endpoint API con el contexto de la aplicación:

  1. Cree una aplicación web de AAD.
  2. Asigne el permiso deseado a la aplicación, por ejemplo, "Leer alertas", "Aislar máquinas".
  3. Cree una clave para esta aplicación.
  4. Obtenga el token mediante la aplicación con su clave.
  5. Uso del token para acceder a la API de Microsoft Defender para punto de conexión

     Para obtener más información, vea [Obtener acceso con el contexto de la aplicación](exposed-apis-create-app-webapp.md).

- **Contexto de usuario:**

  Se usa para realizar acciones en la API en nombre de un usuario.

  Pasos para acceder a Defender for Endpoint API con el contexto de usuario:

  1. Cree una aplicación nativa de AAD.
  2. Asigne el permiso deseado a la aplicación, por ejemplo, "Leer alertas", "Aislar máquinas", etc.
  3. Obtenga el token mediante la aplicación con credenciales de usuario.
  4. Uso del token para acceder a la API de Microsoft Defender para punto de conexión

     Para obtener más información, vea [Obtener acceso con el contexto de usuario](exposed-apis-create-app-nativeapp.md).

## <a name="related-topics"></a>Temas relacionados

- [API de Microsoft Defender para punto de conexión](exposed-apis-list.md)
- [Acceso a Microsoft Defender para punto de conexión con contexto de aplicación](exposed-apis-create-app-webapp.md)
- [Acceso a Microsoft Defender para punto de conexión con el contexto de usuario](exposed-apis-create-app-nativeapp.md)
