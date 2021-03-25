---
title: Solucionar problemas de integración de herramientas SIEM en ATP de Microsoft Defender
description: Solucionar problemas que pueden surgir al usar herramientas SIEM con ATP de Microsoft Defender.
keywords: troubleshoot, siem, client secret, secret
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: c1c8fdb0b6e84d4265defb95d91b59a584b7f4c2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185784"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a>Solucionar problemas de integración de herramientas SIEM

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

Es posible que deba solucionar problemas al extraer detecciones en las herramientas SIEM.

En esta página se proporcionan pasos detallados para solucionar problemas que puedan surgir.


## <a name="learn-how-to-get-a-new-client-secret"></a>Obtenga información sobre cómo obtener un nuevo secreto de cliente
Si el secreto de cliente expira o si ha perdido la copia proporcionada al habilitar la aplicación de herramienta SIEM, tendrá que obtener un nuevo secreto.

1. Inicie sesión en [el Portal de administración de Azure](https://portal.azure.com).

2. Seleccione **Azure Active Directory**.

3. Seleccione el espacio empresarial.

4. Haga **clic en Registros de aplicaciones**. A continuación, en la lista aplicaciones, seleccione la aplicación.

5. Seleccione **la sección** Claves, proporcione una descripción de clave y especifique la duración de validez de la clave.

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




>¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshootsiem-belowfoldlink) 

## <a name="related-topics"></a>Temas relacionados
- [Habilitar la integración de SIEM en Microsoft Defender para endpoint](enable-siem-integration.md)
- [Configurar ArcSight para extraer Microsoft Defender para detecciones de puntos de conexión](configure-arcsight.md)
- [Extraer detecciones a las herramientas SIEM](configure-siem.md)
- [Campos de Microsoft Defender para detección de puntos de conexión](api-portal-mapping.md)
- [Extraer Microsoft Defender para detecciones de puntos de conexión mediante la API de REST](pull-alerts-using-rest-api.md)
