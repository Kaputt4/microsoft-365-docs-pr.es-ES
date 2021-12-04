---
title: Explorador de API en Microsoft Defender para endpoint
ms.reviewer: ''
description: Usar el Explorador de API para crear y realizar consultas api, probar y enviar solicitudes para cualquier API disponible
keywords: api, explorer, send, request, get, post,
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
ms.custom: api
ms.openlocfilehash: 6e7d0e5927a85f2f3952221c294fe2387c268546
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2021
ms.locfileid: "61300171"
---
# <a name="api-explorer"></a>Explorador de API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

El Explorador de API de Microsoft Defender para Endpoint es una herramienta que le ayuda a explorar varias API de Defender for Endpoint de forma interactiva.

El Explorador de API facilita la construcción y la realización de consultas api, pruebas y envío de solicitudes para cualquier punto de conexión disponible de Defender para endpoint API. Use el Explorador de API para realizar acciones o buscar datos que aún no estén disponibles a través de la interfaz de usuario.

La herramienta es útil durante el desarrollo de aplicaciones. Le permite realizar consultas api que respetan la configuración de acceso de usuario, lo que reduce la necesidad de generar tokens de acceso.

También puede usar la herramienta para explorar la galería de consultas de ejemplo, copiar ejemplos de código de resultado y generar información de depuración.

Con el Explorador de API, puede:

- Ejecutar solicitudes para cualquier método y ver respuestas en tiempo real
- Examinar rápidamente los ejemplos de API y obtener información sobre los parámetros que admiten
- Realizar llamadas API con facilidad; no es necesario autenticar más allá del inicio de sesión del portal de administración

## <a name="access-api-explorer"></a>Explorador de API de Access

En el menú de navegación izquierdo, seleccione **Partners & API** \> **Explorer**.

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
