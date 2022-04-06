---
title: Solucionar problemas en Microsoft Defender para endpoint en Android
description: Solucionar problemas de Microsoft Defender para Endpoint en Android
keywords: microsoft, defender, Microsoft Defender para Endpoint, mde, android, cloud, conectividad, comunicación
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 574e02c837ce1f2e3639ed562ed52bacc0e67629
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64472229"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a>Solución de problemas en Microsoft Defender para punto de conexión en Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Al incorporar un dispositivo, es posible que veas problemas de inicio de sesión después de instalar la aplicación.

Durante la incorporación, es posible que encuentres problemas de inicio de sesión después de instalar la aplicación en el dispositivo.

En este artículo se proporcionan soluciones para ayudar a solucionar los problemas de inicio de sesión.

## <a name="sign-in-failed---unexpected-error"></a>Error de inicio de sesión: error inesperado

**Error de inicio de sesión:** *error inesperado, inténtelo más tarde*

:::image type="content" source="images/f9c3bad127d636c1f150d79814f35d4c.png" alt-text="Error de inicio de sesión Error inesperado en la página de inicio de sesión del portal de Microsoft Defender 365." lightbox="images/f9c3bad127d636c1f150d79814f35d4c.png":::

**Mensaje:**

Error inesperado, inténtelo más tarde

**Causa:**

Tienes instalada una versión anterior de la aplicación "Microsoft Authenticator" en el dispositivo.

**Solución:**

Instala la versión más reciente [y Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator) de Google Play Store e inténtelo de nuevo.

## <a name="sign-in-failed---invalid-license"></a>Error al iniciar sesión: licencia no válida

**Error al iniciar sesión: licencia** *no válida, póngase en contacto con el administrador*

:::image type="content" source="images/920e433f440fa1d3d298e6a2a43d4811.png" alt-text="Los detalles de contacto de la directiva en la página de inicio de sesión del portal de Microsoft Defender 365" lightbox="images/920e433f440fa1d3d298e6a2a43d4811.png":::

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

:::image type="content" source="images/0c04975c74746a5cdb085e1d9386e713.png" alt-text="Un mensaje de notificación no seguro para el sitio" lightbox="images/0c04975c74746a5cdb085e1d9386e713.png":::

**Causa:**

Los dispositivos Xiaomi incluyen un nuevo modelo de permisos. Esto impide que Defender para Endpoint para Android muestre ventanas emergentes mientras se ejecuta en segundo plano.

Permiso de dispositivos Xiaomi: "Mostrar ventanas emergentes mientras se ejecuta en segundo plano".

:::image type="content" source="images/6e48e7b29daf50afddcc6c8c7d59fd64.png" alt-text="Panel de configuración emergente en el portal de Microsoft Defender 365" lightbox="images/6e48e7b29daf50afddcc6c8c7d59fd64.png":::

**Solución:**

Habilite el permiso necesario en dispositivos Xiaomi.

- Mostrar ventanas emergentes mientras se ejecuta en segundo plano.

## <a name="unable-to-allow-permission-for-permanent-protection-during-onboarding-on-some-oem-devices"></a>No se puede permitir el permiso para la "protección permanente" durante la incorporación en algunos dispositivos OEM

**Se aplica a:** Solo dispositivos OEM específicos.

- **Xiaomi con Android 11**

Defender App pide permiso de optimización de batería/protección permanente en dispositivos como parte de la incorporación de aplicaciones  y al seleccionar Permitir se devuelve un error que no se pudo establecer el permiso. Solo afecta al último permiso denominado "Protección permanente". 

**Causa:**

Xiaomi cambió los permisos de optimización de batería en Android 11. Defender for Endpoint no puede configurar esta configuración para omitir las optimizaciones de batería.

**Solución:**

Estamos trabajando con OEM para encontrar una solución que habilite este permiso desde la pantalla de incorporación de aplicaciones. Actualizaremos la documentación cuando se resuelva.
Los usuarios pueden seguir estos pasos para habilitar los mismos permisos desde la configuración del dispositivo: 

1. Ve a **Configuración** en el dispositivo.

2. Busque y seleccione **Optimización de batería**.

   :::image type="content" source="images/search-battery-optimisation.png" alt-text="La página en la que puedes buscar y seleccionar Optimización de batería" lightbox="images/search-battery-optimisation.png":::

3. En **Acceso especial a la aplicación**, selecciona **Optimización de batería**.

   :::image type="content" source="images/special-app-access.png" alt-text="Panel de acceso a aplicaciones especiales desde el que puedes seleccionar Optimización de batería" lightbox="images/special-app-access.png":::

4. Cambia el desplegable para mostrar **Todas las aplicaciones**.

   :::image type="content" source="images/show-all-apps-2.png" alt-text="La lista desplegable desde la que puedes cambiar el valor a Todas las aplicaciones en el panel Optimización de batería" lightbox="images/show-all-apps-2.png":::

   :::image type="content" source="images/show-all-apps-1.png" alt-text="La lista desplegable que muestra la opción Todas las aplicaciones en el panel Optimización de batería" lightbox="images/show-all-apps-1.png":::

5. Busque "Microsoft Defender para endpoint" y seleccione **No optimizar**.

   :::image type="content" source="images/select-dont-optimise.png" alt-text="La página que habilita la ubicación de la opción Microsoft Defender para endpoint y la selección de No optimizar" lightbox="images/select-dont-optimise.png":::

Vuelva a la pantalla de incorporación de Microsoft Defender para puntos de conexión, seleccione **Permitir** y se le redirigirá a la pantalla del panel.

## <a name="send-in-app-feedback"></a>Enviar comentarios desde la aplicación

Si un usuario se enfrenta a un problema que aún no se ha tratado en las secciones anteriores o no puede resolver con los pasos enumerados, el usuario  puede proporcionar comentarios desde la aplicación junto con los datos **de diagnóstico**. A continuación, nuestro equipo puede investigar los registros para proporcionar la solución adecuada. Los usuarios pueden seguir estos pasos para hacer lo mismo:

1.  Abre la **aplicación MDE** en el dispositivo y haz clic en el icono **de perfil** en la esquina superior izquierda.

    :::image type="content" source="images/select-profile-icon-1.jpg" alt-text="El icono de perfil en el portal de Microsoft Defender para endpoint" lightbox="images/select-profile-icon-1.jpg":::

2.  Seleccione "Ayuda & comentarios".

    :::image type="content" source="images/selecthelpandfeedback2.png" alt-text="La opción ayuda & comentarios que se pueden seleccionar en el portal de Microsoft Defender para endpoints" lightbox="images/selecthelpandfeedback2.png":::

3.  Seleccione "Enviar comentarios a Microsoft".

    :::image type="content" alt-text="Seleccionar enviar comentarios a Microsoft" source="images/send-feedback-to-microsoft-3.jpg":::

4.  Elija entre las opciones dadas. Para informar de un problema, seleccione "Quiero informar de un problema".

    :::image type="content" source="images/report-issue-4.jpg" alt-text="La opción Quiero informar de un problema" lightbox="images/report-issue-4.jpg":::

5.  Proporcione detalles del problema al que se enfrenta y compruebe "Enviar datos de diagnóstico". Se recomienda comprobar "Incluir la dirección de correo electrónico" para que el equipo pueda contactar con usted con una solución o un seguimiento.

    :::image type="content" source="images/finalsubmit5.png" alt-text="Panel en el que puede agregar detalles y adjuntar datos de diagnóstico" lightbox="images/finalsubmit5.png":::

6.  Haga clic en "Enviar" para enviar correctamente los comentarios.
