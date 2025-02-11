---
title: Solución de problemas de incorporación y mensajes de error
description: Solución de problemas de incorporación y mensaje de error al completar la instalación de Microsoft Defender para punto de conexión.
keywords: solución de problemas, solución de problemas, Azure Active Directory, incorporación, mensaje de error, mensajes de error, Microsoft Defender para punto de conexión
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
- m365-security
- tier3
ms.topic: troubleshooting
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 83dfcb73e9d73df22348e490fbd232bb7d0d4e63
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68231734"
---
# <a name="troubleshoot-subscription-and-portal-access-issues"></a>Solucionar problemas de acceso a la suscripción y al portal

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-troublshootonboarding-abovefoldlink)

En esta página se proporcionan pasos detallados para solucionar problemas que pueden producirse al configurar el servicio de Microsoft Defender para punto de conexión.

Si recibe un mensaje de error, Microsoft 365 Defender proporcionará una explicación detallada sobre cuál es el problema y se proporcionarán vínculos pertinentes.

## <a name="no-subscriptions-found"></a>No se encontró ninguna suscripción

Si al acceder a Microsoft 365 Defender recibe un mensaje **No se encontró ninguna suscripción**, significa que Azure Active Directory (Azure AD) que se usa para iniciar sesión en el usuario en el portal, no tiene una licencia de Microsoft Defender para punto de conexión.

Posibles motivos:

- Las licencias de Windows E5 y Office E5 son licencias separadas.
- La licencia se compró pero no se aprovisionó en esta instancia de Azure AD.
  - Podría tratarse de un problema de aprovisionamiento de licencias.
  - Podría ser que aprovisionara involuntariamente la licencia en un Microsoft Azure AD diferente al que se usa para la autenticación en el servicio.

En ambos casos, debe ponerse en contacto con el soporte técnico de Microsoft en [Soporte técnico general Microsoft Defender para punto de conexión](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) o Soporte técnico por [volumen](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx).

:::image type="content" source="images/atp-no-subscriptions-found.png" alt-text="Página Sin suscripciones encontradas" lightbox="images/atp-no-subscriptions-found.png":::

## <a name="your-subscription-has-expired"></a>La suscripción ha expirado

Si al acceder a Microsoft 365 Defender obtiene un mensaje **Su suscripción ha expirado**, la suscripción de servicio en línea ha expirado. Microsoft Defender para punto de conexión suscripción, al igual que cualquier otra suscripción de servicio en línea, tiene una fecha de expiración.

Puede optar por renovar o ampliar la licencia en cualquier momento. Al acceder al portal después de la fecha de expiración, se mostrará un mensaje **De su suscripción expirada** con una opción para descargar el paquete de retirada del dispositivo, si decide no renovar la licencia.

> [!NOTE]
> Por motivos de seguridad, el paquete usado para dispositivos Offboard expirará 30 días después de la fecha en que se descargó. Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo. Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

:::image type="content" source="images/atp-subscription-expired.png" alt-text="Mensaje de notificación de la suscripción expirada" lightbox="images/atp-subscription-expired.png":::

## <a name="you-are-not-authorized-to-access-the-portal"></a>No tiene autorización para acceder al portal.

Si recibe un no **está autorizado para acceder al portal**, tenga en cuenta que Microsoft Defender para punto de conexión es un producto de supervisión de seguridad, investigación de incidentes y respuesta y, como tal, el acceso a él está restringido y controlado por el usuario.
Para obtener más información, consulte [**Asignación de acceso de usuario al portal**](/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection).

:::image type="content" source="images/atp-not-authorized-to-access-portal.png" alt-text="Mensaje de notificación de acceso no permitido" lightbox="images/atp-not-authorized-to-access-portal.png":::

## <a name="data-currently-isnt-available-on-some-sections-of-the-portal"></a>Actualmente, los datos no están disponibles en algunas secciones del portal

Si el panel del portal y otras secciones muestran un mensaje de error como "Los datos no están disponibles actualmente":

:::image type="content" source="images/atp-data-not-available.png" alt-text="Mensaje de notificación de no disponibilidad de datos" lightbox="images/atp-data-not-available.png":::

Tendrá que permitir los `security.windows.com` subdominios y todos los subdominios en él en el explorador web. Por ejemplo, `*.security.windows.com`.

## <a name="portal-communication-issues"></a>Problemas de comunicación del portal

Si tiene problemas con el acceso al portal, la falta de datos o el acceso restringido a partes del portal, tendrá que comprobar que las siguientes direcciones URL están permitidas y abiertas para la comunicación.

- `*.blob.core.windows.net`
- `crl.microsoft.com`
- `https://*.microsoftonline-p.com`
- `https://*.security.microsoft.com`
- `https://automatediracs-eus-prd.security.microsoft.com`
- `https://login.microsoftonline.com`
- `https://login.windows.net`
- `https://onboardingpackagescusprd.blob.core.windows.net`
- `https://secure.aadcdn.microsoftonline-p.com`
- `https://security.microsoft.com`
- `https://static2.sharepointonline.com`
