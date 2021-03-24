---
title: Solucionar problemas de incorporación y mensajes de error
description: Solucionar problemas de incorporación y mensaje de error al completar la configuración de Microsoft Defender para endpoint.
keywords: solución de problemas, solución de problemas, Azure Active Directory, incorporación, mensaje de error, mensajes de error, Microsoft Defender para punto de conexión
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
ms.openlocfilehash: 63981d985140858cbbda54a10dc94b30f28131e5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072891"
---
# <a name="troubleshoot-subscription-and-portal-access-issues"></a><span data-ttu-id="c236c-104">Solucionar problemas de acceso a portales y suscripciones</span><span class="sxs-lookup"><span data-stu-id="c236c-104">Troubleshoot subscription and portal access issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c236c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c236c-105">**Applies to:**</span></span>
- [<span data-ttu-id="c236c-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c236c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="c236c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c236c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="c236c-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="c236c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c236c-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="c236c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troublshootonboarding-abovefoldlink)

<span data-ttu-id="c236c-110">En esta página se proporcionan pasos detallados para solucionar problemas que pueden producirse al configurar el servicio de Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="c236c-110">This page provides detailed steps to troubleshoot issues that might occur when setting up your Microsoft Defender for Endpoint service.</span></span>

<span data-ttu-id="c236c-111">Si recibe un mensaje de error, el Centro de seguridad de Microsoft Defender proporcionará una explicación detallada sobre el problema y se proporcionarán vínculos relevantes.</span><span class="sxs-lookup"><span data-stu-id="c236c-111">If you receive an error message, Microsoft Defender Security Center will provide a detailed explanation on what the issue is and relevant links will be supplied.</span></span>

## <a name="no-subscriptions-found"></a><span data-ttu-id="c236c-112">No se encontraron suscripciones</span><span class="sxs-lookup"><span data-stu-id="c236c-112">No subscriptions found</span></span>

<span data-ttu-id="c236c-113">Si al acceder al Centro de seguridad de Microsoft Defender recibe un mensaje No se encontró ninguna suscripción, significa que Azure Active Directory (Azure AD) usado para iniciar sesión en el usuario en el portal, **no** tiene una licencia de Microsoft Defender para endpoints.</span><span class="sxs-lookup"><span data-stu-id="c236c-113">If while accessing Microsoft Defender Security Center you get a **No subscriptions found** message, it means the Azure Active Directory (Azure AD) used to log in the user to the portal, does not have a Microsoft Defender for Endpoint license.</span></span>

<span data-ttu-id="c236c-114">Posibles razones:</span><span class="sxs-lookup"><span data-stu-id="c236c-114">Potential reasons:</span></span>
- <span data-ttu-id="c236c-115">Las licencias de Windows E5 y Office E5 son licencias separadas.</span><span class="sxs-lookup"><span data-stu-id="c236c-115">The Windows E5 and Office E5 licenses are separate licenses.</span></span>
- <span data-ttu-id="c236c-116">La licencia se compró pero no se aprovisionó en esta instancia de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c236c-116">The license was purchased but not provisioned to this Azure AD instance.</span></span>
    - <span data-ttu-id="c236c-117">Podría ser un problema de aprovisionamiento de licencias.</span><span class="sxs-lookup"><span data-stu-id="c236c-117">It could be a license provisioning issue.</span></span>
    - <span data-ttu-id="c236c-118">Podría ser que aprovisionó accidentalmente la licencia a un Microsoft Azure AD diferente al que se usa para la autenticación en el servicio.</span><span class="sxs-lookup"><span data-stu-id="c236c-118">It could be you inadvertently provisioned the license to a different Microsoft Azure AD than the one used for authentication into the service.</span></span>

<span data-ttu-id="c236c-119">En ambos casos, debes ponerse en contacto con el soporte técnico de Microsoft en [General Microsoft Defender para](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) soporte técnico de endpoints o compatibilidad con licencias por [volumen.](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx)</span><span class="sxs-lookup"><span data-stu-id="c236c-119">For both cases, you should contact Microsoft support at [General Microsoft Defender for Endpoint Support](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) or [Volume license support](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx).</span></span>

![Imagen de no se encontró ninguna suscripción](images/atp-no-subscriptions-found.png)

## <a name="your-subscription-has-expired"></a><span data-ttu-id="c236c-121">Su suscripción ha expirado</span><span class="sxs-lookup"><span data-stu-id="c236c-121">Your subscription has expired</span></span>

<span data-ttu-id="c236c-122">Si al acceder al Centro de seguridad de Microsoft Defender recibe un mensaje Su **suscripción** ha expirado, la suscripción al servicio en línea ha expirado.</span><span class="sxs-lookup"><span data-stu-id="c236c-122">If while accessing Microsoft Defender Security Center you get a **Your subscription has expired** message, your online service subscription has expired.</span></span> <span data-ttu-id="c236c-123">La suscripción de Microsoft Defender para endpoint, como cualquier otra suscripción de servicio en línea, tiene una fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="c236c-123">Microsoft Defender for Endpoint subscription, like any other online service subscription, has an expiration date.</span></span> 

<span data-ttu-id="c236c-124">Puede elegir renovar o ampliar la licencia en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="c236c-124">You can choose to renew or extend the license at any point in time.</span></span> <span data-ttu-id="c236c-125">Al acceder al portal después  de la fecha de expiración, se mostrará una opción para descargar el paquete de descarga del dispositivo después de la fecha de expiración, en caso de que decidas no renovar la licencia.</span><span class="sxs-lookup"><span data-stu-id="c236c-125">When accessing the portal after the expiration date a **Your subscription has expired** message will be presented with an option to download the device offboarding package, should you choose to not renew the license.</span></span>

> [!NOTE]
> <span data-ttu-id="c236c-126">Por motivos de seguridad, el paquete usado para dispositivos offboard expirará 30 días después de la fecha en que se descargó.</span><span class="sxs-lookup"><span data-stu-id="c236c-126">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="c236c-127">Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c236c-127">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="c236c-128">Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="c236c-128">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

![Imagen de la suscripción expirada](images/atp-subscription-expired.png)

## <a name="you-are-not-authorized-to-access-the-portal"></a><span data-ttu-id="c236c-130">No está autorizado a acceder al portal</span><span class="sxs-lookup"><span data-stu-id="c236c-130">You are not authorized to access the portal</span></span>

<span data-ttu-id="c236c-131">Si recibe un You **are not authorized to access the portal**, tenga en cuenta que Microsoft Defender for Endpoint es un producto de supervisión de seguridad, investigación de incidentes y respuesta y, como tal, el acceso a él está restringido y controlado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="c236c-131">If you receive a **You are not authorized to access the portal**, be aware that Microsoft Defender for Endpoint is a security monitoring, incident investigation and response product, and as such, access to it is restricted and controlled by the user.</span></span>
<span data-ttu-id="c236c-132">Para obtener más información, vea [**Asignar acceso de usuario al portal**](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="c236c-132">For more information, see, [**Assign user access to the portal**](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection).</span></span>

![Imagen de portal de acceso no autorizado](images/atp-not-authorized-to-access-portal.png)

## <a name="data-currently-isnt-available-on-some-sections-of-the-portal"></a><span data-ttu-id="c236c-134">Actualmente, los datos no están disponibles en algunas secciones del portal</span><span class="sxs-lookup"><span data-stu-id="c236c-134">Data currently isn't available on some sections of the portal</span></span>
<span data-ttu-id="c236c-135">Si el panel del portal y otras secciones muestran un mensaje de error como "Los datos actualmente no están disponibles":</span><span class="sxs-lookup"><span data-stu-id="c236c-135">If the portal dashboard and other sections show an error message such as "Data currently isn't available":</span></span>

![La imagen de los datos actualmente no está disponible](images/atp-data-not-available.png)

<span data-ttu-id="c236c-137">Tendrás que permitir los `securitycenter.windows.com` subdominios y todos los subdominios que hay en él.</span><span class="sxs-lookup"><span data-stu-id="c236c-137">You'll need to allow the `securitycenter.windows.com` and all subdomains under it.</span></span> <span data-ttu-id="c236c-138">Por ejemplo, `*.securitycenter.windows.com`.</span><span class="sxs-lookup"><span data-stu-id="c236c-138">For example, `*.securitycenter.windows.com`.</span></span>


## <a name="portal-communication-issues"></a><span data-ttu-id="c236c-139">Problemas de comunicación del portal</span><span class="sxs-lookup"><span data-stu-id="c236c-139">Portal communication issues</span></span>
<span data-ttu-id="c236c-140">Si tiene problemas con el acceso al portal, la falta de datos o el acceso restringido a partes del portal, deberá comprobar que las siguientes direcciones URL están permitidas y abiertas para la comunicación.</span><span class="sxs-lookup"><span data-stu-id="c236c-140">If you encounter issues with accessing the portal, missing data, or restricted access to portions of the portal, you'll need to verify that the following URLs are allowed and open for communication.</span></span>

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



