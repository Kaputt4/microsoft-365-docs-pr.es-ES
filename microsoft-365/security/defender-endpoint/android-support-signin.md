---
title: Solucionar problemas en Microsoft Defender para endpoint en Android
description: Solucionar problemas de Microsoft Defender para Endpoint en Android
keywords: microsoft, defender, Microsoft Defender para Endpoint, mde, android, cloud, conectividad, comunicación
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 18afd4aa160ec345839d23719d1b3fcce21654ec
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246361"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a>Solución de problemas en Microsoft Defender para Endpoint en Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Al incorporar un dispositivo, es posible que veas problemas de inicio de sesión después de instalar la aplicación.

Durante la incorporación, es posible que encuentres problemas de inicio de sesión después de instalar la aplicación en el dispositivo.

En este artículo se proporcionan soluciones para ayudar a solucionar los problemas de inicio de sesión.  

## <a name="sign-in-failed---unexpected-error"></a>Error de inicio de sesión: error inesperado
**Error de inicio de sesión:** *error inesperado, inténtelo más tarde*

![Imagen del error de inicio de sesión Error inesperado](images/f9c3bad127d636c1f150d79814f35d4c.png)

**Mensaje:**

Error inesperado, inténtelo más tarde

**Causa:**

Tienes instalada una versión anterior de la aplicación "Microsoft Authenticator" en el dispositivo.

**Solución:**

Instalar la versión más reciente [y Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) de Google Play Store e intentarlo de nuevo

## <a name="sign-in-failed---invalid-license"></a>Error al iniciar sesión: licencia no válida

**Error al iniciar sesión: licencia** *no válida, póngase en contacto con el administrador*

![Imagen del error de inicio de sesión póngase en contacto con el administrador](images/920e433f440fa1d3d298e6a2a43d4811.png)

**Mensaje: Licencia** *no válida, póngase en contacto con el administrador*

**Causa:**

No tiene asignada Microsoft 365 licencia o su organización no tiene una licencia para Microsoft 365 Enterprise suscripción.

**Solución:**

Póngase en contacto con el administrador para obtener ayuda.

## <a name="report-unsafe-site"></a>Informe de sitio no seguro

Los sitios web de suplantación de identidad suplantan sitios web de confianza con el fin de obtener su información personal o financiera. Visita la [página Proporcionar comentarios sobre la protección de](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) red si quieres informar de un sitio web que podría ser un sitio de suplantación de identidad.

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a>Las páginas de suplantación de identidad no están bloqueadas en algunos dispositivos OEM

**Se aplica a:** Oem específicos solo

-   **Xiaomi**

El phishing y las amenazas web nocivas detectadas por Defender para Endpoint para Android no se bloquean en algunos dispositivos Xiaomi. La siguiente funcionalidad no funciona en estos dispositivos.

![Imagen del sitio notificado no seguro](images/0c04975c74746a5cdb085e1d9386e713.png)


**Causa:**

Los dispositivos Xiaomi incluyen un nuevo modelo de permisos. Esto impide que Defender para Endpoint para Android muestre ventanas emergentes mientras se ejecuta en segundo plano.

Permiso de dispositivos Xiaomi: "Mostrar ventanas emergentes mientras se ejecuta en segundo plano".

![Imagen de configuración emergente](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

**Solución:**

Habilite el permiso necesario en dispositivos Xiaomi.

- Mostrar ventanas emergentes mientras se ejecuta en segundo plano.
