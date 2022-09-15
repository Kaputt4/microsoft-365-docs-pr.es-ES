---
title: Explorador de API en Microsoft Defender para punto de conexión
ms.reviewer: ''
description: Use el Explorador de API para construir y realizar consultas de API, probar y enviar solicitudes para cualquier API disponible.
keywords: api, explorer, send, request, get, post,
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
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 7e38ef8f7034ff86220fc9452c5d0ea94443783d
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67699398"
---
# <a name="api-explorer"></a>Explorador de API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

El explorador de API de Microsoft Defender para punto de conexión es una herramienta que le ayuda a explorar varias API de Defender para punto de conexión de forma interactiva.

El Explorador de API facilita la construcción y realización de consultas de API, pruebas y envío de solicitudes para cualquier punto de conexión de API de Defender para punto de conexión disponible. Use el Explorador de API para realizar acciones o buscar datos que aún no estén disponibles a través de la interfaz de usuario.

La herramienta es útil durante el desarrollo de aplicaciones. Permite realizar consultas de API que respetan la configuración de acceso del usuario, lo que reduce la necesidad de generar tokens de acceso.

También puede usar la herramienta para explorar la galería de consultas de ejemplo, copiar ejemplos de código de resultados y generar información de depuración.

Con el Explorador de API, puede hacer lo siguiente:

- Ejecute solicitudes para cualquier método y vea las respuestas en tiempo real.
- Examine rápidamente los ejemplos de API y obtenga información sobre los parámetros que admiten.
- Realice llamadas API con facilidad; no es necesario autenticarse más allá del inicio de sesión del portal de administración.

## <a name="access-api-explorer"></a>Explorador de API de Access

En el menú de navegación izquierdo, seleccione **Partners &** **[API API Explorer (Explorador de API](https://security.microsoft.com/interoperability/api-explorer)**\> de API).

## <a name="supported-apis"></a>API admitidas

El Explorador de API admite todas las API que ofrece Defender para punto de conexión.

La lista de API admitidas está disponible en la [documentación de las API](apis-intro.md).

## <a name="get-started-with-the-api-explorer"></a>Introducción al Explorador de API

1. En el panel izquierdo, hay una lista de solicitudes de ejemplo que puede usar.
2. Siga los vínculos y haga clic en **Ejecutar consulta**.

Algunos de los ejemplos pueden requerir la especificación de un parámetro en la dirección URL, por ejemplo, {machine- ID}.

## <a name="faq"></a>Preguntas más frecuentes

**¿Es necesario tener un token de API para usar el Explorador de API?** <br>
No se necesitan credenciales para acceder a una API. El Explorador de API usa el token del portal de administración de Defender para punto de conexión cada vez que realiza una solicitud.

La credencial de autenticación de usuario que ha iniciado sesión se usa para comprobar que el Explorador de API está autorizado para acceder a los datos en su nombre.

Las solicitudes de API específicas están limitadas en función de los privilegios de RBAC. Por ejemplo, una solicitud a "Indicador de envío" se limita al rol de administrador de seguridad.
