---
title: Solución de problemas en Microsoft Defender para punto de conexión en Android
description: Solución de problemas de Microsoft Defender para punto de conexión en Android
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mde, android, cloud, connectivity, communication
ms.service: microsoft-365-security
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
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 73e87075f17413e361f380d7556dc3988ac4a7f7
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67693331"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a>Solución de problemas en Microsoft Defender para punto de conexión en Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Al incorporar un dispositivo, es posible que vea problemas de inicio de sesión después de instalar la aplicación.

Durante la incorporación, es posible que se produzcan problemas de inicio de sesión después de instalar la aplicación en el dispositivo.

En este artículo se proporcionan soluciones para ayudar a solucionar los problemas de inicio de sesión.

## <a name="sign-in-failed---unexpected-error"></a>Error de inicio de sesión: error inesperado

**Error de inicio de sesión:** *error inesperado, inténtelo más tarde*

:::image type="content" source="images/f9c3bad127d636c1f150d79814f35d4c.png" alt-text="Error de inicio de sesión Error inesperado en la página de inicio de sesión del portal de Microsoft Defender 365." lightbox="images/f9c3bad127d636c1f150d79814f35d4c.png":::

**Mensaje:**

Error inesperado, inténtelo más tarde

**Causa:**

Tiene una versión anterior de la aplicación "Microsoft Authenticator" instalada en el dispositivo.

**Solución:**

Instale la versión más reciente y de [Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator) desde Google Play Store e inténtelo de nuevo.

## <a name="sign-in-failed---invalid-license"></a>Error de inicio de sesión: licencia no válida

**Error de inicio de sesión:** *licencia no válida, póngase en contacto con el administrador*

:::image type="content" source="images/920e433f440fa1d3d298e6a2a43d4811.png" alt-text="Los detalles de contacto de la directiva en la página de inicio de sesión del portal de Microsoft Defender 365" lightbox="images/920e433f440fa1d3d298e6a2a43d4811.png":::

**Mensaje:** *Licencia no válida, póngase en contacto con el administrador*

**Causa:**

No tiene asignada la licencia de Microsoft 365 o su organización no tiene una licencia para Microsoft 365 Enterprise suscripción.

**Solución:**

Póngase en contacto con el administrador para obtener ayuda.

## <a name="report-unsafe-site"></a>Informe de un sitio no seguro

Los sitios web de suplantación de identidad suplantan sitios web de confianza con el fin de obtener su información personal o financiera. Visite la página [Proporcionar comentarios sobre la protección de red](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) si desea informar de un sitio web que podría ser un sitio de suplantación de identidad (phishing).

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a>Las páginas de phishing no están bloqueadas en algunos dispositivos OEM

**Se aplica a:** Solo oem específicos

- **Xiaomi**

La suplantación de identidad (phishing) y las amenazas web dañinas detectadas por Defender para punto de conexión para Android no se bloquean en algunos dispositivos Xiaomi. La siguiente funcionalidad no funciona en estos dispositivos.

:::image type="content" source="images/0c04975c74746a5cdb085e1d9386e713.png" alt-text="Un mensaje de notificación no seguro para el sitio" lightbox="images/0c04975c74746a5cdb085e1d9386e713.png":::

**Causa:**

Los dispositivos Xiaomi incluyen un nuevo modelo de permisos. Esto impide que Defender para punto de conexión para Android muestre ventanas emergentes mientras se ejecuta en segundo plano.

Permiso de dispositivos Xiaomi: "Mostrar ventanas emergentes mientras se ejecuta en segundo plano".

:::image type="content" source="images/6e48e7b29daf50afddcc6c8c7d59fd64.png" alt-text="Panel de configuración emergente en el portal de Microsoft Defender 365" lightbox="images/6e48e7b29daf50afddcc6c8c7d59fd64.png":::

**Solución:**

Habilite el permiso necesario en dispositivos Xiaomi.

- Mostrar ventanas emergentes mientras se ejecuta en segundo plano.

## <a name="unable-to-allow-permission-for-permanent-protection-during-onboarding-on-some-oem-devices"></a>No se puede permitir el permiso para la "protección permanente" durante la incorporación en algunos dispositivos OEM


**Se aplica a:** Solo dispositivos OEM específicos.

- **Xiaomi**

La aplicación Defender solicita el permiso Optimización de batería/Protección permanente en los dispositivos como parte de la incorporación de aplicaciones y al seleccionar **Permitir** se devuelve un error que indica que no se pudo establecer el permiso. Solo afecta al último permiso denominado "Protección permanente". 

**Causa:**

Xiaomi cambió los permisos de optimización de batería en Android 11. Defender para punto de conexión no puede configurar esta configuración para omitir las optimizaciones de batería.

**Solución:**

>[!IMPORTANT]
>Este problema se ha resuelto. Actualice a la versión más reciente de la aplicación para completar el proceso de incorporación. Si el problema persiste, envíe un **[comentario desde la aplicación](/microsoft-365/security/defender-endpoint/android-support-signin#send-in-app-feedback)**.


## <a name="send-in-app-feedback"></a>Enviar comentarios desde la aplicación

Si un usuario se enfrenta a un problema que aún no se ha solucionado en las secciones anteriores o no puede resolverse mediante los pasos enumerados, el usuario puede proporcionar **comentarios desde la aplicación** junto con **datos de diagnóstico**. A continuación, nuestro equipo puede investigar los registros para proporcionar la solución adecuada. Los usuarios pueden seguir estos pasos para hacer lo mismo:

1. Abra la **aplicación MDE** en el dispositivo y haga clic en el **icono de perfil** de la esquina superior izquierda.

    :::image type="content" source="images/select-profile-icon-1.jpg" alt-text="Icono de perfil en el portal de Microsoft Defender para punto de conexión" lightbox="images/select-profile-icon-1.jpg":::

2. Seleccione "Ayuda & comentarios".

    :::image type="content" source="images/selecthelpandfeedback2.png" alt-text="La opción Ayuda & comentarios que se puede seleccionar en el portal de Microsoft Defender para punto de conexión" lightbox="images/selecthelpandfeedback2.png":::

3. Seleccione "Enviar comentarios a Microsoft".

    :::image type="content" alt-text="Seleccionar enviar comentarios a Microsoft" source="images/send-feedback-to-microsoft-3.jpg":::

4. Elija entre las opciones especificadas. Para informar de un problema, seleccione "Quiero informar de un problema".

    :::image type="content" source="images/report-issue-4.jpg" alt-text="La opción Quiero informar de un problema" lightbox="images/report-issue-4.jpg":::

5. Proporcione los detalles del problema al que se enfrenta y compruebe "Enviar datos de diagnóstico". Se recomienda comprobar "Incluir su dirección de correo electrónico" para que el equipo pueda ponerse en contacto con usted con una solución o un seguimiento.

    :::image type="content" source="images/finalsubmit5.png" alt-text="Panel en el que puede agregar detalles y adjuntar datos de diagnóstico" lightbox="images/finalsubmit5.png":::

6. Haga clic en "Enviar" para enviar correctamente los comentarios.

