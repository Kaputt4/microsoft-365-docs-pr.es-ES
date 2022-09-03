---
title: Solución de problemas de integración de herramientas SIEM en Microsoft Defender para punto de conexión
description: Solucione los problemas que pueden surgir al usar herramientas SIEM con Microsoft Defender para punto de conexión.
keywords: solución de problemas, siem, secreto de cliente, secreto
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
ms.topic: troubleshooting
ms.subservice: mde
ms.openlocfilehash: 879f6e2f5572e5cbbbe61a542f294d97e6844ab5
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67585430"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a>Solucionar problemas de integración de la herramienta SIEM

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

Es posible que tenga que solucionar problemas al extraer detecciones en las herramientas siem.

En esta página se proporcionan pasos detallados para solucionar problemas que puedan surgir.

## <a name="learn-how-to-get-a-new-client-secret"></a>Obtenga información sobre cómo obtener un nuevo secreto de cliente.

Si el secreto de cliente expira o si ha perdido la copia proporcionada al habilitar la aplicación de herramientas SIEM, tendrá que obtener un nuevo secreto.

1. Inicie sesión en el [portal de administración de Azure](https://portal.azure.com).

2. Seleccione **Azure Active Directory**.

3. Seleccione el inquilino.

4. Haga clic en **Registros de aplicaciones**. A continuación, en la lista de aplicaciones, seleccione la aplicación.

5. Seleccione **Certificados & sección Secretos** , Haga clic en Nuevo secreto de cliente y, a continuación, proporcione una descripción y especifique la duración de validez.

6. Haga clic en **Guardar**. Se muestra el valor de clave.

7. Copie el valor y guárdelo en un lugar seguro.

## <a name="error-when-getting-a-refresh-access-token"></a>Error al obtener un token de acceso de actualización

Si se produce un error al intentar obtener un token de actualización al usar la API de inteligencia sobre amenazas o las herramientas SIEM, deberá agregar la dirección URL de respuesta para la aplicación pertinente en Azure Active Directory.

1. Inicie sesión en el [portal de administración de Azure](https://ms.portal.azure.com).

2. Seleccione **Azure Active Directory**.

3. Seleccione el inquilino.

4. Haga clic en **Registros de aplicaciones**. A continuación, en la lista de aplicaciones, seleccione la aplicación.

5. Agregue la siguiente dirección URL:
   - Para la Unión Europea: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`
   - Para el Reino Unido: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`
   - Para el Estados Unidos: `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback`.

6. Haga clic en **Guardar**.

## <a name="error-while-enabling-the-siem-connector-application"></a>Error al habilitar la aplicación del conector SIEM

Si se produce un error al intentar habilitar la aplicación del conector SIEM, compruebe la configuración del bloqueador emergente del explorador. Podría estar bloqueando la nueva ventana que se abre al habilitar la funcionalidad.

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-troubleshootsiem-belowfoldlink)

## <a name="related-topics"></a>Temas relacionados

- [Detecciones de extracción en las herramientas SIEM](configure-siem.md)

