---
title: Acceso a las API de Microsoft Threat Protection
description: Obtenga información sobre cómo acceder a las API de Microsoft Threat Protection
keywords: acceso, API, contexto de aplicación, contexto de usuario, aplicación AAD, token de acceso
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 653c359c324852719688a374a6e863df0a1909ba
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650554"
---
# <a name="access-the-microsoft-threat-protection-apis"></a>Acceso a las API de Microsoft Threat Protection

**Se aplica a:**
- Protección contra amenazas de Microsoft

>[!IMPORTANT] 
>Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.


 Microsoft Threat Protection expone gran parte de sus datos y acciones a través de un conjunto de API de programación. Estas API le permitirán automatizar flujos de trabajo y innovar en función de las capacidades de Microsoft Threat Protection. El acceso a la API requiere la autenticación OAuth 2.0. Para obtener más información, vea [flujo de código de autorización de OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).


En general, deberá realizar los siguientes pasos para usar las API:
- Crear una aplicación de AAD
- Obtener un token de acceso con esta aplicación
- Usar el token para acceder a la API de protección contra amenazas de Microsoft


Puede tener acceso a la API de Microsoft Threat Protection con **contexto de aplicación** o **contexto de usuario**.

- **Contexto de aplicación: (recomendado)** <br>
    Lo usan las aplicaciones que se ejecutan sin la presencia de un usuario que ha iniciado sesión. por ejemplo, aplicaciones que se ejecutan como daemons o servicios en segundo plano.

    Pasos que se deben seguir para acceder a la API de Microsoft Threat Protection con el contexto de la aplicación:

  1. Cree una aplicación Web de AAD.
  2. Asigne el permiso deseado a applicationFor example, **Incident. Read. All**, **AdvancedHunting. Read. All**. 
  3. Cree una clave para esta aplicación.
  4. Obtiene el token mediante la aplicación con su clave.
  5. Usar el token para acceder a la API de protección contra amenazas de Microsoft

     Para obtener más información, vea [Get Access with Application context](api-create-app-web.md).


- **Contexto de usuario:** <br>
    Se usa para realizar acciones en la API en nombre de un usuario.

    Pasos que se deben realizar para acceder a la API de Microsoft Threat Protection con el contexto de la aplicación:
  1. Cree una aplicación nativa de AAD.
  2. Asigne el permiso deseado a la aplicación. Por ejemplo, **Incident. Read**, **AdvancedHunting. Read**.
  3. Obtiene el token mediante la aplicación con las credenciales de usuario.
  4. Usar el token para acceder a la API de protección contra amenazas de Microsoft

     Para obtener más información, vea [obtener acceso con contexto de usuario](api-create-app-user-context.md).


## <a name="related-topics"></a>Temas relacionados
- [API de Microsoft Threat Protection](api-supported.md)
- [Acceso a Microsoft Threat Protection con contexto de aplicación](api-create-app-web.md)
- [Acceso a Microsoft Threat Protection con contexto de usuario](api-create-app-user-context.md)
