---
title: Solucionar problemas de integración de herramientas SIEM en Microsoft Defender para endpoint
description: Solucionar problemas que pueden surgir al usar herramientas SIEM con Microsoft Defender para endpoint.
keywords: troubleshoot, siem, client secret, secret
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
ms.openlocfilehash: b6ed0342183734d9b4feb1c20a6c4059b77e64d6
ms.sourcegitcommit: 986ea76ecaceb5fe6b9616e553003e3c5b0df2e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2022
ms.locfileid: "62213996"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a>Solucionar problemas de integración de la herramienta SIEM

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
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

- [Extraer detecciones a las herramientas SIEM](configure-siem.md)

