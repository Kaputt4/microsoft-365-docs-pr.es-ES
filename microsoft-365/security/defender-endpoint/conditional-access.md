---
title: Habilitar el acceso condicional para proteger mejor a los usuarios, dispositivos y datos
description: Habilite el acceso condicional para evitar que las aplicaciones se ejecuten si un dispositivo se considera en riesgo y se determina que una aplicación no es compatible.
keywords: acceso condicional, bloquear aplicaciones, nivel de seguridad, intune,
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 21d17ee789a4757df10e99514f23cfc26b186405
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166202"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a><span data-ttu-id="d4bf3-104">Habilitar el acceso condicional para proteger mejor a los usuarios, dispositivos y datos</span><span class="sxs-lookup"><span data-stu-id="d4bf3-104">Enable Conditional Access to better protect users, devices, and data</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d4bf3-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d4bf3-105">**Applies to:**</span></span>
- [<span data-ttu-id="d4bf3-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d4bf3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d4bf3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d4bf3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="d4bf3-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d4bf3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d4bf3-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

<span data-ttu-id="d4bf3-110">El acceso condicional es una funcionalidad que te ayuda a proteger mejor la información de los usuarios y de la empresa al asegurarte de que solo los dispositivos seguros tienen acceso a las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-110">Conditional Access is a capability that helps you better protect your users and enterprise information by making sure that only secure devices have access to applications.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4byD1]

<span data-ttu-id="d4bf3-111">Con el acceso condicional, puedes controlar el acceso a la información empresarial en función del nivel de riesgo de un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-111">With Conditional Access, you can control access to enterprise information based on the risk level of a device.</span></span> <span data-ttu-id="d4bf3-112">Esto ayuda a mantener los usuarios de confianza en dispositivos de confianza con aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-112">This helps keep trusted users on trusted devices using trusted applications.</span></span>

<span data-ttu-id="d4bf3-113">Puedes definir las condiciones de seguridad en las que los dispositivos y las aplicaciones pueden ejecutarse y acceder a la información desde la red aplicando directivas para impedir que las aplicaciones se ejecuten hasta que un dispositivo vuelva a un estado compatible.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-113">You can define security conditions under which devices and applications can run and access information from your network by enforcing policies to stop applications from running until a device returns to a compliant state.</span></span> 

<span data-ttu-id="d4bf3-114">La implementación del acceso condicional en Defender para endpoint se basa en las directivas de cumplimiento de dispositivos de Microsoft Intune (Intune) y las directivas de acceso condicional de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="d4bf3-114">The implementation of Conditional Access in Defender for Endpoint is based on Microsoft Intune (Intune) device compliance policies and Azure Active Directory (Azure AD) conditional access policies.</span></span> 

<span data-ttu-id="d4bf3-115">La directiva de cumplimiento se usa con acceso condicional para permitir que solo los dispositivos que cumplan una o más reglas de directiva de cumplimiento de dispositivos puedan acceder a las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-115">The compliance policy is used with Conditional Access to allow only devices that fulfill one or more device compliance policy rules to access applications.</span></span> 

## <a name="understand-the-conditional-access-flow"></a><span data-ttu-id="d4bf3-116">Comprender el flujo de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="d4bf3-116">Understand the Conditional Access flow</span></span>
<span data-ttu-id="d4bf3-117">El acceso condicional se pone en marcha para que, cuando se ve una amenaza en un dispositivo, se bloquee el acceso al contenido confidencial hasta que se corrija la amenaza.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-117">Conditional Access is put in place so that when a threat is seen on a device, access to sensitive content is blocked until the threat is remediated.</span></span> 

<span data-ttu-id="d4bf3-118">El flujo comienza con dispositivos que se ven con un riesgo bajo, medio o alto.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-118">The flow begins with devices being seen to have a low, medium, or high risk.</span></span> <span data-ttu-id="d4bf3-119">A continuación, estas determinaciones de riesgos se envían a Intune.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-119">These risk determinations are then sent to Intune.</span></span> 

<span data-ttu-id="d4bf3-120">Según cómo configure las directivas en Intune, se puede configurar el acceso condicional para que, cuando se cumplen determinadas condiciones, se aplique la directiva.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-120">Depending on how you configure policies in Intune, Conditional Access can be set up so that when certain conditions are met, the policy is applied.</span></span>

<span data-ttu-id="d4bf3-121">Por ejemplo, puede configurar Intune para aplicar el acceso condicional a dispositivos con un alto riesgo.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-121">For example, you can configure Intune to apply Conditional Access on devices that have a high risk.</span></span>

<span data-ttu-id="d4bf3-122">En Intune, se usa una directiva de cumplimiento de dispositivos junto con el acceso condicional de Azure AD para bloquear el acceso a las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-122">In Intune, a device compliance policy is used in conjunction with Azure AD Conditional Access to block access to applications.</span></span> <span data-ttu-id="d4bf3-123">En paralelo, se inicia un proceso automatizado de investigación y corrección.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-123">In parallel, an automated investigation and remediation process is launched.</span></span>

 <span data-ttu-id="d4bf3-124">Un usuario todavía puede usar el dispositivo mientras se lleva a cabo la investigación automatizada y la corrección, pero el acceso a los datos de la empresa se bloquea hasta que la amenaza se corrija por completo.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-124">A user can still use the device while the automated investigation and remediation is taking place, but access to enterprise data is blocked until the threat is fully remediated.</span></span> 

<span data-ttu-id="d4bf3-125">Para resolver el riesgo encontrado en un dispositivo, tendrás que devolver el dispositivo a un estado compatible.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-125">To resolve the risk found on a device, you'll need to return the device to a compliant state.</span></span> <span data-ttu-id="d4bf3-126">Un dispositivo vuelve a un estado de cumplimiento cuando no se ve ningún riesgo en él.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-126">A device returns to a compliant state when there is no risk seen on it.</span></span> 

<span data-ttu-id="d4bf3-127">Hay tres formas de abordar un riesgo:</span><span class="sxs-lookup"><span data-stu-id="d4bf3-127">There are three ways to address a risk:</span></span>
1. <span data-ttu-id="d4bf3-128">Use la corrección manual o automatizada.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-128">Use Manual or automated remediation.</span></span>
2. <span data-ttu-id="d4bf3-129">Resolver alertas activas en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-129">Resolve active alerts on the device.</span></span> <span data-ttu-id="d4bf3-130">Esto eliminará el riesgo del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-130">This will remove the risk from the device.</span></span>
3. <span data-ttu-id="d4bf3-131">Puedes quitar el dispositivo de las directivas activas y, por lo tanto, el acceso condicional no se aplicará en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-131">You can remove the device from the active policies and consequently, Conditional Access will not be applied on the device.</span></span> 

<span data-ttu-id="d4bf3-132">La corrección manual requiere que un administrador de secops investigue una alerta y solucione el riesgo que se ve en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-132">Manual remediation requires a secops admin to investigate an alert and address the risk seen on the device.</span></span> <span data-ttu-id="d4bf3-133">La corrección automatizada se configura a través de las opciones de configuración proporcionadas en la siguiente sección, [Configurar el acceso condicional](configure-conditional-access.md).</span><span class="sxs-lookup"><span data-stu-id="d4bf3-133">The automated remediation is configured through configuration settings provided in the following section, [Configure Conditional Access](configure-conditional-access.md).</span></span>

<span data-ttu-id="d4bf3-134">Cuando se quita el riesgo a través de la corrección manual o automatizada, el dispositivo vuelve a un estado compatible y se concede acceso a las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-134">When the risk is removed either through manual or automated remediation, the device returns to a compliant state and access to applications is granted.</span></span>

<span data-ttu-id="d4bf3-135">La siguiente secuencia de eventos de ejemplo explica el acceso condicional en acción:</span><span class="sxs-lookup"><span data-stu-id="d4bf3-135">The following example sequence of events explains Conditional Access in action:</span></span>

1. <span data-ttu-id="d4bf3-136">Un usuario abre un archivo malintencionado y Defender para endpoint marca el dispositivo como de alto riesgo.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-136">A user opens a malicious file and Defender for Endpoint flags the device as high risk.</span></span>
2. <span data-ttu-id="d4bf3-137">La evaluación de alto riesgo se pasa a Intune.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-137">The high risk assessment is passed along to Intune.</span></span> <span data-ttu-id="d4bf3-138">En paralelo, se inicia una investigación automatizada para corregir la amenaza identificada.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-138">In parallel, an automated investigation is initiated to remediate the identified threat.</span></span> <span data-ttu-id="d4bf3-139">También se puede realizar una corrección manual para corregir la amenaza identificada.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-139">A manual remediation can also be done to remediate the identified threat.</span></span>
3. <span data-ttu-id="d4bf3-140">Según la directiva creada en Intune, el dispositivo se marca como no compatible.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-140">Based on the policy created in Intune, the device is marked as not compliant.</span></span> <span data-ttu-id="d4bf3-141">A continuación, la directiva de acceso condicional de Intune comunica la evaluación a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-141">The assessment is then communicated to Azure AD by the Intune Conditional Access policy.</span></span> <span data-ttu-id="d4bf3-142">En Azure AD, la directiva correspondiente se aplica para bloquear el acceso a las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-142">In Azure AD, the corresponding policy is applied to block access to applications.</span></span>
4. <span data-ttu-id="d4bf3-143">La investigación y corrección manual o automatizada se completa y se elimina la amenaza.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-143">The manual or automated investigation and remediation is completed and the threat is removed.</span></span> <span data-ttu-id="d4bf3-144">Defender for Endpoint ve que no hay ningún riesgo en el dispositivo e Intune evalúa que el dispositivo está en un estado de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-144">Defender for Endpoint sees that there is no risk on the device and Intune assesses the device to be in a compliant state.</span></span> <span data-ttu-id="d4bf3-145">Azure AD aplica la directiva que permite el acceso a las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-145">Azure AD applies the policy which allows access to applications.</span></span>
5. <span data-ttu-id="d4bf3-146">Los usuarios ahora pueden acceder a las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d4bf3-146">Users can now access applications.</span></span>

 
## <a name="related-topic"></a><span data-ttu-id="d4bf3-147">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="d4bf3-147">Related topic</span></span>
- [<span data-ttu-id="d4bf3-148">Configurar el acceso condicional en Microsoft Defender para el extremo</span><span class="sxs-lookup"><span data-stu-id="d4bf3-148">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>](configure-conditional-access.md)
