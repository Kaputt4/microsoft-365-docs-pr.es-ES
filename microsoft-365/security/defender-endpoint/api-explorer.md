---
title: Explorador de API en Microsoft Defender para endpoint
ms.reviewer: ''
description: Usar el Explorador de API para crear y realizar consultas api, probar y enviar solicitudes para cualquier API disponible
keywords: api, explorer, send, request, get, post,
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
ms.openlocfilehash: b8d0d991e46464bae3b4d21d6218b9b3b2d2b4cb
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51930118"
---
# <a name="api-explorer"></a>Explorador de API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)


El Explorador de API de Microsoft Defender para Endpoint es una herramienta que le ayuda a explorar varias API de Defender for Endpoint de forma interactiva. 

El Explorador de API facilita la construcción y la realización de consultas api, pruebas y envío de solicitudes para cualquier punto de conexión disponible de Defender para endpoint API. Use el Explorador de API para realizar acciones o buscar datos que aún no estén disponibles a través de la interfaz de usuario.

La herramienta es útil durante el desarrollo de aplicaciones. Le permite realizar consultas api que respetan la configuración de acceso de usuario, lo que reduce la necesidad de generar tokens de acceso.

También puede usar la herramienta para explorar la galería de consultas de ejemplo, copiar ejemplos de código de resultado y generar información de depuración.

Con el Explorador de API, puede:

- Ejecutar solicitudes para cualquier método y ver respuestas en tiempo real
- Examinar rápidamente los ejemplos de API y obtener información sobre los parámetros que admiten
- Realizar llamadas API con facilidad; no es necesario autenticar más allá del inicio de sesión del portal de administración

## <a name="access-api-explorer"></a>Explorador de API de Access

En el menú de navegación izquierdo, seleccione **Partners & API**  >  **Explorer**.

## <a name="supported-apis"></a>API compatibles

El Explorador de API admite todas las API que ofrece Defender para Endpoint.
  
La lista de API admitidas está disponible en la [documentación de las API.](apis-intro.md) 

## <a name="get-started-with-the-api-explorer"></a>Introducción al Explorador de API

1. En el panel izquierdo, hay una lista de solicitudes de ejemplo que puede usar. 
2. Siga los vínculos y haga clic **en Ejecutar consulta**. 

Algunos de los ejemplos pueden requerir la especificación de un parámetro en la dirección URL, por ejemplo, {machine- ID}.

## <a name="faq"></a>Preguntas más frecuentes

**¿Necesito tener un token de API para usar el Explorador de API?** <br>
Las credenciales para obtener acceso a una API no son necesarias. El Explorador de API usa el token del portal de administración de Defender para puntos de conexión siempre que realiza una solicitud.

La credencial de autenticación de usuario iniciada se usa para comprobar que el Explorador de API está autorizado para tener acceso a los datos en su nombre.

Las solicitudes de API específicas son limitadas en función de los privilegios rbac. Por ejemplo, una solicitud a "Enviar indicador" está limitada al rol de administrador de seguridad. 
