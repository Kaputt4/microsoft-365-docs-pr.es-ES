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
ms.openlocfilehash: 38f7ff40416835e9908757456520f0a90a745dfd
ms.sourcegitcommit: f358e321f7e81eff425fe0f0db1be0f3348d2585
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2021
ms.locfileid: "58508279"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a>Solución de problemas en Microsoft Defender para punto de conexión en Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

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

- **Xiaomi**

El phishing y las amenazas web nocivas detectadas por Defender para Endpoint para Android no se bloquean en algunos dispositivos Xiaomi. La siguiente funcionalidad no funciona en estos dispositivos.

![Imagen del sitio notificado no seguro](images/0c04975c74746a5cdb085e1d9386e713.png)

**Causa:**

Los dispositivos Xiaomi incluyen un nuevo modelo de permisos. Esto impide que Defender para Endpoint para Android muestre ventanas emergentes mientras se ejecuta en segundo plano.

Permiso de dispositivos Xiaomi: "Mostrar ventanas emergentes mientras se ejecuta en segundo plano".

![Imagen de configuración emergente](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

**Solución:**

Habilite el permiso necesario en dispositivos Xiaomi.

- Mostrar ventanas emergentes mientras se ejecuta en segundo plano.

## <a name="unable-to-allow-permission-for-permanent-protection-during-onboarding-on-some-oem-devices"></a>No se puede permitir el permiso para la "protección permanente" durante la incorporación en algunos dispositivos OEM

**Se aplica a:** Solo dispositivos OEM específicos.

- **Xiaomi con Android 11**

Defender App pide permiso de optimización de batería/protección permanente en  dispositivos como parte de la incorporación de aplicaciones y al seleccionar Permitir se devuelve un error que no se pudo establecer el permiso. Solo afecta al último permiso denominado "Protección permanente". 

**Causa:**

Xiomi cambió los permisos de optimización de batería en Android 11. Defender no puede configurar esta configuración para omitir las optimizaciones de batería.

**Solución:**

Estamos trabajando con OEM para encontrar una solución que habilite este permiso desde la pantalla de incorporación de aplicaciones. Actualizaremos la documentación cuando se resuelva.
Los usuarios pueden seguir estos pasos para habilitar los mismos permisos desde la configuración del dispositivo: 

1. Ve a **Configuración** en el dispositivo.

2. Busque y seleccione **Optimización de batería.**

   ![Busque y seleccione "Optimización de batería".](images/search-battery-optimisation.png)

3. En **Acceso especial a la aplicación,** selecciona **Optimización de batería.**

   ![En Acceso especial a la aplicación, selecciona "Optimización de batería".](images/special-app-access.png)

4. Cambie el menú desplegable para mostrar **Todas las aplicaciones**.

   ![Paso uno para cambiar el desplegable para mostrar "Todas las aplicaciones".](images/show-all-apps-2.png)

   ![Paso dos para cambiar el desplegable para mostrar "Todas las aplicaciones".](images/show-all-apps-1.png)

5. Busque "Punto de conexión de Microsoft Defender" y seleccione **No optimizar**.

   ![Busque "Punto de conexión de Microsoft Defender" y seleccione "No optimizar".](images/select-dont-optimise.png)

Vuelva a la pantalla de incorporación de Puntos de conexión de Microsoft Defender, seleccione **Permitir** y se le redirigirá a la pantalla del panel.
