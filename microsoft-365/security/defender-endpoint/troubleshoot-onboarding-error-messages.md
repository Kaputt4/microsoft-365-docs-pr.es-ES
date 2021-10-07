---
title: Solucionar problemas de incorporación y mensajes de error
description: Solucionar problemas de incorporación y mensaje de error al completar la configuración de Microsoft Defender para endpoint.
keywords: solución de problemas, solución de problemas, Azure Active Directory, incorporación, mensaje de error, mensajes de error, microsoft defender para el punto de conexión
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
ms.openlocfilehash: 10ec4562063c7352b337cdb6f5d11b76985ae19d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159227"
---
# <a name="troubleshoot-subscription-and-portal-access-issues"></a>Solucionar problemas de acceso a la suscripción y al portal

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-troublshootonboarding-abovefoldlink)

En esta página se proporcionan pasos detallados para solucionar problemas que pueden producirse al configurar el servicio de Microsoft Defender para puntos de conexión.

Si recibe un mensaje de error, Microsoft 365 Defender proporcionará una explicación detallada sobre el problema y se proporcionarán vínculos relevantes.

## <a name="no-subscriptions-found"></a>No se encontraron suscripciones

Si al acceder Microsoft 365 Defender recibe un mensaje **No se** encontró suscripciones, significa que el Azure Active Directory (Azure AD) usado para iniciar sesión en el usuario en el portal, no tiene una licencia de Microsoft Defender para endpoint.

Posibles razones:

- Las licencias de Windows E5 y Office E5 son licencias separadas.
- La licencia se compró pero no se aprovisionó en esta instancia de Azure AD.
  - Podría ser un problema de aprovisionamiento de licencias.
  - Podría ser que aprovisionó la licencia de forma involuntaria a un Microsoft Azure AD diferente al que se usa para la autenticación en el servicio.

En ambos casos, debes ponerse en contacto con el soporte técnico de Microsoft en [General Microsoft Defender para](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) soporte técnico de endpoints o compatibilidad con licencias por [volumen.](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx)

![Imagen de no se encontró ninguna suscripción.](images/atp-no-subscriptions-found.png)

## <a name="your-subscription-has-expired"></a>Su suscripción ha expirado

Si al acceder a Microsoft 365 Defender recibe un mensaje Su suscripción ha **expirado,** la suscripción de servicio en línea ha expirado. La suscripción de Microsoft Defender para endpoint, como cualquier otra suscripción de servicio en línea, tiene una fecha de expiración.

Puede elegir renovar o ampliar la licencia en cualquier momento. Al acceder al portal después  de la fecha de expiración, se mostrará una opción para descargar el paquete de descarga del dispositivo después de la fecha de expiración, en caso de que decidas no renovar la licencia.

> [!NOTE]
> Por motivos de seguridad, el paquete usado para dispositivos offboard expirará 30 días después de la fecha en que se descargó. Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo. Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

![Imagen de la suscripción expirada.](images/atp-subscription-expired.png)

## <a name="you-are-not-authorized-to-access-the-portal"></a>No está autorizado a acceder al portal

Si recibe un You **are not authorized to access the portal**, tenga en cuenta que Microsoft Defender for Endpoint es un producto de supervisión de seguridad, investigación de incidentes y respuesta y, como tal, el acceso a él está restringido y controlado por el usuario.
Para obtener más información, vea [**Asignar acceso de usuario al portal**](/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection).

![Imagen de no autorizado para acceder al portal.](images/atp-not-authorized-to-access-portal.png)

## <a name="data-currently-isnt-available-on-some-sections-of-the-portal"></a>Actualmente, los datos no están disponibles en algunas secciones del portal

Si el panel del portal y otras secciones muestran un mensaje de error como "Los datos actualmente no están disponibles":

![La imagen de los datos actualmente no está disponible.](images/atp-data-not-available.png)

Tendrás que permitir los `security.windows.com` subdominios y todos los subdominios que hay en él. Por ejemplo, `*.security.windows.com`.

## <a name="portal-communication-issues"></a>Problemas de comunicación del portal

Si tiene problemas con el acceso al portal, la falta de datos o el acceso restringido a partes del portal, deberá comprobar que las siguientes direcciones URL están permitidas y abiertas para la comunicación.

- `*.blob.core.windows.net`
- `crl.microsoft.com`
- `https://*.microsoftonline-p.com`
- `https://*.securitycenter.windows.com`
- `https://automatediracs-eus-prd.securitycenter.windows.com`
- `https://login.microsoftonline.com`
- `https://login.windows.net`
- `https://onboardingpackagescusprd.blob.core.windows.net`
- `https://secure.aadcdn.microsoftonline-p.com`
- `https://securitycenter.windows.com`
- `https://static2.sharepointonline.com`
