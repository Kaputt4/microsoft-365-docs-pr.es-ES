---
title: Solucionar problemas de integración de herramientas SIEM en Microsoft Defender para endpoint
description: Solucionar problemas que pueden surgir al usar herramientas SIEM con Microsoft Defender para endpoint.
keywords: troubleshoot, siem, client secret, secret
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 59db066644a549cf52252602f494dd1267e216f9
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61165575"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a>Solucionar problemas de integración de la herramienta SIEM

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Plan 1 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

Es posible que deba solucionar problemas al extraer detecciones en las herramientas SIEM.

En esta página se proporcionan pasos detallados para solucionar problemas que puedan surgir.

## <a name="learn-how-to-get-a-new-client-secret"></a>Obtenga información sobre cómo obtener un nuevo secreto de cliente

Si el secreto de cliente expira o si ha perdido la copia proporcionada al habilitar la aplicación de herramienta SIEM, tendrá que obtener un nuevo secreto.

1. Inicie sesión en [el Portal de administración de Azure](https://portal.azure.com).

2. Seleccione **Azure Active Directory**.

3. Seleccione el espacio empresarial.

4. Haga **clic en Registros de aplicaciones**. A continuación, en la lista aplicaciones, seleccione la aplicación.

5. Seleccione **Certificados & secretos,** Haga clic en Nuevo secreto de cliente y, a continuación, proporcione una descripción y especifique la duración de validez.

6. Haga clic en **Guardar**. Se muestra el valor de la clave.

7. Copie el valor y guárdelo en un lugar seguro.

## <a name="error-when-getting-a-refresh-access-token"></a>Error al obtener un token de acceso de actualización

Si se produce un error al intentar obtener un token de actualización al usar la API de inteligencia de amenazas o las herramientas SIEM, deberá agregar la dirección URL de respuesta para la aplicación relevante en Azure Active Directory.

1. Inicie sesión en [el Portal de administración de Azure](https://ms.portal.azure.com).

2. Seleccione **Azure Active Directory**.

3. Seleccione el espacio empresarial.

4. Haga **clic en Registros de aplicaciones**. A continuación, en la lista aplicaciones, seleccione la aplicación.

5. Agregue la siguiente dirección URL:
   - Para la Unión Europea: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`
   - Para el Reino Unido: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`
   - Para Estados Unidos:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` .

6. Haga clic en **Guardar**.

## <a name="error-while-enabling-the-siem-connector-application"></a>Error al habilitar la aplicación de conector SIEM

Si se produce un error al intentar habilitar la aplicación de conector SIEM, compruebe la configuración del bloqueador de elementos emergentes del explorador. Puede que esté bloqueando la nueva ventana que se abre al habilitar la funcionalidad.

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-troubleshootsiem-belowfoldlink)

## <a name="related-topics"></a>Temas relacionados

- [Habilitar la integración de SIEM en Microsoft Defender para endpoint](enable-siem-integration.md)
- [Configurar ArcSight para extraer Microsoft Defender para detecciones de puntos de conexión](configure-arcsight.md)
- [Extraer detecciones a las herramientas SIEM](configure-siem.md)
- [Campos de Microsoft Defender para detección de puntos de conexión](api-portal-mapping.md)
- [Extraer Microsoft Defender para detecciones de puntos de conexión mediante la API de REST](pull-alerts-using-rest-api.md)
