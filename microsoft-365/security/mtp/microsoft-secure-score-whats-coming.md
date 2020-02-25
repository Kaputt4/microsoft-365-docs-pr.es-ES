---
title: ¿Qué viene con la puntuación segura de Microsoft?
description: Describe la puntuación segura de Microsoft en el centro de seguridad 365 de Microsoft, cómo se calculan los detalles y qué administradores de seguridad pueden esperar.
keywords: seguridad, malware, Microsoft 365, M365, calificación segura, centro de seguridad, acciones de mejora
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 55c7cb34c5484eaf8f6693be0ce439e33a82550f
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266990"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="a2576-104">¿Qué viene con la puntuación segura de Microsoft?</span><span class="sxs-lookup"><span data-stu-id="a2576-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="a2576-105">Para hacer que la puntuación segura de Microsoft sea un mejor representante de su postura de seguridad y mejorar el uso, estamos realizando algunos cambios en un futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="a2576-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="a2576-106">Se cambiará la puntuación y la puntuación máxima posible.</span><span class="sxs-lookup"><span data-stu-id="a2576-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="a2576-107">Sin embargo, esto no implica un cambio en su postura de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a2576-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="a2576-108">Para obtener más información sobre los cambios recientes, vea [what's New in Secure score de Microsoft](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="a2576-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="march-2nd-2020"></a><span data-ttu-id="a2576-109">2 de marzo 2020</span><span class="sxs-lookup"><span data-stu-id="a2576-109">March 2nd 2020</span></span>

### <a name="removing-improvement-actions-from-intune"></a><span data-ttu-id="a2576-110">Eliminación de acciones de mejora de Intune</span><span class="sxs-lookup"><span data-stu-id="a2576-110">Removing improvement actions from Intune</span></span>

<span data-ttu-id="a2576-111">Después de una evaluación de las acciones de mejora de la puntuación segura de Microsoft que se han proporcionado desde Intune, se decidió que no proporcionan una representación útil de la postura de seguridad de los dispositivos en las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="a2576-111">After an evaluation of the Microsoft Secure Score improvement actions supplied from Intune, it was decided that they do not provide a useful representation of the security posture of devices in organizations.</span></span> <span data-ttu-id="a2576-112">En lugar de centrarse en las directivas, estamos trabajando para incluir controles de seguridad que evalúen directamente el estado de configuración de los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a2576-112">Instead of focusing on policies, we are working to bring in security controls that directly assess the configuration state of the devices.</span></span>

<span data-ttu-id="a2576-113">Se quitarán las siguientes acciones para la mejora de Intune:</span><span class="sxs-lookup"><span data-stu-id="a2576-113">The following Intune improvement actions will be removed:</span></span>

- <span data-ttu-id="a2576-114">Habilitar la administración de dispositivos móviles de Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a2576-114">Enable Microsoft Intune Mobile Device Management</span></span>
- <span data-ttu-id="a2576-115">Crear una directiva de cumplimiento de Microsoft Intune para Android</span><span class="sxs-lookup"><span data-stu-id="a2576-115">Create a Microsoft Intune Compliance Policy for Android</span></span>
- <span data-ttu-id="a2576-116">Crear una directiva de cumplimiento de Microsoft Intune para Android para trabajar</span><span class="sxs-lookup"><span data-stu-id="a2576-116">Create a Microsoft Intune Compliance Policy for Android for Work</span></span>
- <span data-ttu-id="a2576-117">Crear una directiva de protección de aplicaciones de Microsoft Intune para Android</span><span class="sxs-lookup"><span data-stu-id="a2576-117">Create a Microsoft Intune App Protection Policy for Android</span></span>
- <span data-ttu-id="a2576-118">Crear una directiva de protección de aplicaciones de Microsoft Intune para iOS</span><span class="sxs-lookup"><span data-stu-id="a2576-118">Create a Microsoft Intune App Protection Policy for iOS</span></span>
- <span data-ttu-id="a2576-119">Marcar dispositivos sin directiva de cumplimiento de Microsoft Intune asignada como no compatible</span><span class="sxs-lookup"><span data-stu-id="a2576-119">Mark devices with no Microsoft Intune Compliance Policy assigned as not compliant</span></span>
- <span data-ttu-id="a2576-120">Crear una directiva de cumplimiento de Microsoft Intune para iOS</span><span class="sxs-lookup"><span data-stu-id="a2576-120">Create a Microsoft Intune Compliance Policy for iOS</span></span>
- <span data-ttu-id="a2576-121">Crear una directiva de cumplimiento de Microsoft Intune para macOS</span><span class="sxs-lookup"><span data-stu-id="a2576-121">Create a Microsoft Intune Compliance Policy for macOS</span></span>
- <span data-ttu-id="a2576-122">Crear una directiva de cumplimiento de Microsoft Intune para Windows</span><span class="sxs-lookup"><span data-stu-id="a2576-122">Create a Microsoft Intune Compliance Policy for Windows</span></span>
- <span data-ttu-id="a2576-123">Crear un perfil de configuración de Microsoft Intune para Android</span><span class="sxs-lookup"><span data-stu-id="a2576-123">Create a Microsoft Intune Configuration Profile for Android</span></span>
- <span data-ttu-id="a2576-124">Crear un perfil de configuración de Microsoft Intune para Android para trabajar</span><span class="sxs-lookup"><span data-stu-id="a2576-124">Create a Microsoft Intune Configuration Profile for Android for Work</span></span>
- <span data-ttu-id="a2576-125">Crear un perfil de configuración de Microsoft Intune para macOS</span><span class="sxs-lookup"><span data-stu-id="a2576-125">Create a Microsoft Intune Configuration Profile for macOS</span></span>
- <span data-ttu-id="a2576-126">Crear un perfil de configuración de Microsoft Intune para iOS</span><span class="sxs-lookup"><span data-stu-id="a2576-126">Create a Microsoft Intune Configuration Profile for iOS</span></span>
- <span data-ttu-id="a2576-127">Crear un perfil de configuración de Microsoft Intune para Windows</span><span class="sxs-lookup"><span data-stu-id="a2576-127">Create a Microsoft Intune Configuration Profile for Windows</span></span>
- <span data-ttu-id="a2576-128">Habilitar la detección de jailbreak mejorada en Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a2576-128">Enable enhanced jailbreak detection in Microsoft Intune</span></span>
- <span data-ttu-id="a2576-129">Requerir que todos los dispositivos sean revisados, tengan antivirus y firewalls habilitados</span><span class="sxs-lookup"><span data-stu-id="a2576-129">Require all devices to be patched, have anti-virus, and firewalls enabled</span></span>
- <span data-ttu-id="a2576-130">Habilitar la integración de ATP de Windows Defender en Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a2576-130">Enable Windows Defender ATP integration into Microsoft Intune</span></span>
- <span data-ttu-id="a2576-131">Crear una directiva de Windows Information Protection para Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a2576-131">Create a Microsoft Intune Windows Information Protection Policy</span></span>
- <span data-ttu-id="a2576-132">Requerir que todos los dispositivos tengan configuraciones de seguridad avanzada</span><span class="sxs-lookup"><span data-stu-id="a2576-132">Require all devices to have advanced security configurations</span></span>
- <span data-ttu-id="a2576-133">Revisar semanalmente el informe de dispositivos bloqueados</span><span class="sxs-lookup"><span data-stu-id="a2576-133">Review blocked devices report weekly</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a><span data-ttu-id="a2576-134">Eliminación de acciones de mejora que no cumplen las expectativas para una medida fiable</span><span class="sxs-lookup"><span data-stu-id="a2576-134">Removing improvement actions that don't meet expectations for reliable measurement</span></span>

<span data-ttu-id="a2576-135">Para asegurarse de que la puntuación segura de Microsoft es significativa y que cada acción de mejora es medible y confiable, se quitan las siguientes acciones de mejora.</span><span class="sxs-lookup"><span data-stu-id="a2576-135">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="a2576-136">Activar la grabación de datos de auditoría</span><span class="sxs-lookup"><span data-stu-id="a2576-136">Turn on audit data recording</span></span>
- <span data-ttu-id="a2576-137">Descubra aplicaciones de TI de instantáneas arriesgadas y no compatibles</span><span class="sxs-lookup"><span data-stu-id="a2576-137">Discover risky and non-compliant shadow IT applications</span></span>
- <span data-ttu-id="a2576-138">Revisión de permisos & bloquear aplicaciones de OAuth arriesgadas conectadas a su entorno</span><span class="sxs-lookup"><span data-stu-id="a2576-138">Review permissions & block risky OAuth applications connected to your environment</span></span>
- <span data-ttu-id="a2576-139">Configurar el control de versiones en las bibliotecas de documentos de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a2576-139">Set up versioning on SharePoint online document libraries</span></span>

### <a name="mfa-improvement-action-updates"></a><span data-ttu-id="a2576-140">Actualizaciones de acciones de mejora de MFA</span><span class="sxs-lookup"><span data-stu-id="a2576-140">MFA improvement action updates</span></span>

<span data-ttu-id="a2576-141">Para reflejar la necesidad de las empresas de garantizar la máxima seguridad al aplicar las directivas que funcionan con su negocio, la calificación segura de Microsoft es quitar tres acciones de mejora centradas alrededor de la autenticación multifactor y agregando dos.</span><span class="sxs-lookup"><span data-stu-id="a2576-141">To reflect the need for businesses to ensure the upmost security while applying policies that work with their business, Microsoft Secure Score is removing three improvement actions centered around multi-factor authentication, and adding two.</span></span>

<span data-ttu-id="a2576-142">Los tres que se quitarán:</span><span class="sxs-lookup"><span data-stu-id="a2576-142">The three that will be removed:</span></span>

- <span data-ttu-id="a2576-143">Registrar todos los usuarios para la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="a2576-143">Register all users for multi-factor authentication</span></span>
- <span data-ttu-id="a2576-144">Requerir MFA para todos los usuarios</span><span class="sxs-lookup"><span data-stu-id="a2576-144">Require MFA for all users</span></span>
- <span data-ttu-id="a2576-145">Requerir MFA para los roles privilegiados de Azure AD</span><span class="sxs-lookup"><span data-stu-id="a2576-145">Require MFA for Azure AD privileged roles</span></span>

<span data-ttu-id="a2576-146">Nuevas acciones de mejora agregadas:</span><span class="sxs-lookup"><span data-stu-id="a2576-146">New improvement actions added:</span></span>

- <span data-ttu-id="a2576-147">Asegurarse de que todos los usuarios puedan completar la autenticación multifactor para el acceso seguro</span><span class="sxs-lookup"><span data-stu-id="a2576-147">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="a2576-148">Requerir MFA para roles administrativos</span><span class="sxs-lookup"><span data-stu-id="a2576-148">Require MFA for administrative roles</span></span>

 <span data-ttu-id="a2576-149">Estas nuevas acciones de mejora requerirán el registro de los usuarios o administradores para la autenticación multifactor (MFA) en el directorio y el establecimiento del conjunto adecuado de directivas que se adapten a las necesidades de la organización.</span><span class="sxs-lookup"><span data-stu-id="a2576-149">These new improvement actions will require registering your users or admins for multi-factor authentication (MFA) across your directory and establishing the right set of policies that fit your organizational needs.</span></span> <span data-ttu-id="a2576-150">El objetivo principal es tener flexibilidad a la vez que se asegura de que todos los usuarios y administradores puedan autenticarse con varios factores o solicitudes de verificación de identidad basadas en riesgos.</span><span class="sxs-lookup"><span data-stu-id="a2576-150">The main goal is have flexibility while ensuring all your users and admins can authenticate with multiple factors or risk-based identity verification prompts.</span></span> <span data-ttu-id="a2576-151">Esto puede tener la forma de tener varias directivas que apliquen decisiones en el ámbito o establecer los valores predeterminados de seguridad (desde el 16 de marzo) que permitan a Microsoft decidir cuándo debe desafiar a los usuarios para MFA.</span><span class="sxs-lookup"><span data-stu-id="a2576-151">That can take the form of having multiple policies that apply scoped decisions, or setting security defaults (coming March 16th) that let Microsoft decide when to challenge users for MFA.</span></span>

### <a name="removing-review-improvement-actions"></a><span data-ttu-id="a2576-152">Eliminación de acciones de mejora de "revisión"</span><span class="sxs-lookup"><span data-stu-id="a2576-152">Removing “review” improvement actions</span></span>

<span data-ttu-id="a2576-153">Uno de los principios de la puntuación segura es que la puntuación debe estar estandarizada y ser fácil de relacionar con.</span><span class="sxs-lookup"><span data-stu-id="a2576-153">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="a2576-154">Las acciones de mejora que no se pueden medir o realizar acciones han causado confusión.</span><span class="sxs-lookup"><span data-stu-id="a2576-154">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="a2576-155">Una calificación segura de Microsoft solo tiene sentido cuando cada recomendación puede tener un efecto claro en la puntuación.</span><span class="sxs-lookup"><span data-stu-id="a2576-155">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="a2576-156">Revisión las acciones de mejora no se miden en el mismo estándar que otras acciones de mejora.</span><span class="sxs-lookup"><span data-stu-id="a2576-156">Review improvement actions are not measured to the same standard as other improvement actions.</span></span>  

<span data-ttu-id="a2576-157">Por estos motivos, todas las acciones de mejora que requerían una cadencia de revisión se eliminarán temporalmente.</span><span class="sxs-lookup"><span data-stu-id="a2576-157">For these reasons, all improvement actions that required a review cadence will be temporarily removed.</span></span> <span data-ttu-id="a2576-158">No es necesario realizar ninguna acción en su parte.</span><span class="sxs-lookup"><span data-stu-id="a2576-158">No action is needed on your part.</span></span>

## <a name="march-16th-2020"></a><span data-ttu-id="a2576-159">16 de marzo de 2020</span><span class="sxs-lookup"><span data-stu-id="a2576-159">March 16th 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a><span data-ttu-id="a2576-160">Eliminación de acciones de mejora que no cumplen las expectativas para una medida fiable</span><span class="sxs-lookup"><span data-stu-id="a2576-160">Removing improvement actions that don't meet expectations for reliable measurement</span></span>

<span data-ttu-id="a2576-161">Para asegurarse de que la puntuación segura de Microsoft es significativa y que cada acción de mejora es medible y confiable, se quitan las siguientes acciones de mejora.</span><span class="sxs-lookup"><span data-stu-id="a2576-161">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="a2576-162">Almacenar documentos de usuario en OneDrive para la empresa</span><span class="sxs-lookup"><span data-stu-id="a2576-162">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="a2576-163">Configurar las directivas de datos adjuntos seguros de Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="a2576-163">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="a2576-164">Configurar vínculos seguros de Office 365 para comprobar direcciones URL</span><span class="sxs-lookup"><span data-stu-id="a2576-164">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="a2576-165">No permitir la delegación de buzones</span><span class="sxs-lookup"><span data-stu-id="a2576-165">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="a2576-166">Permitir vínculos de uso compartido de invitados anónimos para sitios y documentos</span><span class="sxs-lookup"><span data-stu-id="a2576-166">Allow anonymous guest sharing links for sites and docs</span></span>

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="a2576-167">Compatibilidad con los valores predeterminados de seguridad para acciones de mejora de Azure AD</span><span class="sxs-lookup"><span data-stu-id="a2576-167">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="a2576-168">La calificación segura de Microsoft actualizará las acciones de mejora para admitir los [valores predeterminados de seguridad en Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), que facilitan la protección de la organización con opciones de seguridad preconfiguradas para ataques comunes.</span><span class="sxs-lookup"><span data-stu-id="a2576-168">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="a2576-169">Afectará a las siguientes acciones de mejora:</span><span class="sxs-lookup"><span data-stu-id="a2576-169">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="a2576-170">Asegurarse de que todos los usuarios puedan completar la autenticación multifactor para el acceso seguro</span><span class="sxs-lookup"><span data-stu-id="a2576-170">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="a2576-171">Requerir MFA para roles administrativos</span><span class="sxs-lookup"><span data-stu-id="a2576-171">Require MFA for administrative roles</span></span>
- <span data-ttu-id="a2576-172">Habilitar la Directiva para bloquear la autenticación heredada</span><span class="sxs-lookup"><span data-stu-id="a2576-172">Enable policy to block legacy authentication</span></span>
