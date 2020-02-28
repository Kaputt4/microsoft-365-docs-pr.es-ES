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
ms.openlocfilehash: 4d445d4c917a46b12592308f599570725ace8e9d
ms.sourcegitcommit: 6c7f6ef98c321c80a9254c10bbbb917895b5c156
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "42322569"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="211bd-104">¿Qué viene con la puntuación segura de Microsoft?</span><span class="sxs-lookup"><span data-stu-id="211bd-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="211bd-105">Para hacer que la puntuación segura de Microsoft sea un mejor representante de su postura de seguridad y mejorar el uso, estamos realizando algunos cambios en un futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="211bd-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="211bd-106">Se cambiará la puntuación y la puntuación máxima posible.</span><span class="sxs-lookup"><span data-stu-id="211bd-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="211bd-107">Sin embargo, esto no implica un cambio en su postura de seguridad.</span><span class="sxs-lookup"><span data-stu-id="211bd-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="211bd-108">Para obtener más información sobre los cambios recientes, vea [what's New in Secure score de Microsoft](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="211bd-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="march-2nd-2020"></a><span data-ttu-id="211bd-109">2 de marzo 2020</span><span class="sxs-lookup"><span data-stu-id="211bd-109">March 2nd 2020</span></span>

### <a name="removing-improvement-actions-from-intune"></a><span data-ttu-id="211bd-110">Eliminación de acciones de mejora de Intune</span><span class="sxs-lookup"><span data-stu-id="211bd-110">Removing improvement actions from Intune</span></span>

<span data-ttu-id="211bd-111">Después de una evaluación de las acciones de mejora de la puntuación segura de Microsoft que se han proporcionado desde Intune, se decidió que no proporcionan una representación útil de la postura de seguridad de los dispositivos en las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="211bd-111">After an evaluation of the Microsoft Secure Score improvement actions supplied from Intune, it was decided that they do not provide a useful representation of the security posture of devices in organizations.</span></span> <span data-ttu-id="211bd-112">En lugar de centrarse en las directivas, estamos trabajando para incluir controles de seguridad que evalúen directamente el estado de configuración de los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="211bd-112">Instead of focusing on policies, we are working to bring in security controls that directly assess the configuration state of the devices.</span></span>

<span data-ttu-id="211bd-113">Se quitarán las siguientes acciones para la mejora de Intune:</span><span class="sxs-lookup"><span data-stu-id="211bd-113">The following Intune improvement actions will be removed:</span></span>

- <span data-ttu-id="211bd-114">Habilitar la administración de dispositivos móviles de Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="211bd-114">Enable Microsoft Intune Mobile Device Management</span></span>
- <span data-ttu-id="211bd-115">Crear una directiva de cumplimiento de Microsoft Intune para Android</span><span class="sxs-lookup"><span data-stu-id="211bd-115">Create a Microsoft Intune Compliance Policy for Android</span></span>
- <span data-ttu-id="211bd-116">Crear una directiva de cumplimiento de Microsoft Intune para Android para trabajar</span><span class="sxs-lookup"><span data-stu-id="211bd-116">Create a Microsoft Intune Compliance Policy for Android for Work</span></span>
- <span data-ttu-id="211bd-117">Crear una directiva de protección de aplicaciones de Microsoft Intune para Android</span><span class="sxs-lookup"><span data-stu-id="211bd-117">Create a Microsoft Intune App Protection Policy for Android</span></span>
- <span data-ttu-id="211bd-118">Crear una directiva de protección de aplicaciones de Microsoft Intune para iOS</span><span class="sxs-lookup"><span data-stu-id="211bd-118">Create a Microsoft Intune App Protection Policy for iOS</span></span>
- <span data-ttu-id="211bd-119">Marcar dispositivos sin directiva de cumplimiento de Microsoft Intune asignada como no compatible</span><span class="sxs-lookup"><span data-stu-id="211bd-119">Mark devices with no Microsoft Intune Compliance Policy assigned as not compliant</span></span>
- <span data-ttu-id="211bd-120">Crear una directiva de cumplimiento de Microsoft Intune para iOS</span><span class="sxs-lookup"><span data-stu-id="211bd-120">Create a Microsoft Intune Compliance Policy for iOS</span></span>
- <span data-ttu-id="211bd-121">Crear una directiva de cumplimiento de Microsoft Intune para macOS</span><span class="sxs-lookup"><span data-stu-id="211bd-121">Create a Microsoft Intune Compliance Policy for macOS</span></span>
- <span data-ttu-id="211bd-122">Crear una directiva de cumplimiento de Microsoft Intune para Windows</span><span class="sxs-lookup"><span data-stu-id="211bd-122">Create a Microsoft Intune Compliance Policy for Windows</span></span>
- <span data-ttu-id="211bd-123">Crear un perfil de configuración de Microsoft Intune para Android</span><span class="sxs-lookup"><span data-stu-id="211bd-123">Create a Microsoft Intune Configuration Profile for Android</span></span>
- <span data-ttu-id="211bd-124">Crear un perfil de configuración de Microsoft Intune para Android para trabajar</span><span class="sxs-lookup"><span data-stu-id="211bd-124">Create a Microsoft Intune Configuration Profile for Android for Work</span></span>
- <span data-ttu-id="211bd-125">Crear un perfil de configuración de Microsoft Intune para macOS</span><span class="sxs-lookup"><span data-stu-id="211bd-125">Create a Microsoft Intune Configuration Profile for macOS</span></span>
- <span data-ttu-id="211bd-126">Crear un perfil de configuración de Microsoft Intune para iOS</span><span class="sxs-lookup"><span data-stu-id="211bd-126">Create a Microsoft Intune Configuration Profile for iOS</span></span>
- <span data-ttu-id="211bd-127">Crear un perfil de configuración de Microsoft Intune para Windows</span><span class="sxs-lookup"><span data-stu-id="211bd-127">Create a Microsoft Intune Configuration Profile for Windows</span></span>
- <span data-ttu-id="211bd-128">Habilitar la detección de jailbreak mejorada en Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="211bd-128">Enable enhanced jailbreak detection in Microsoft Intune</span></span>
- <span data-ttu-id="211bd-129">Requerir que todos los dispositivos sean revisados, tengan antivirus y firewalls habilitados</span><span class="sxs-lookup"><span data-stu-id="211bd-129">Require all devices to be patched, have anti-virus, and firewalls enabled</span></span>
- <span data-ttu-id="211bd-130">Habilitar la integración de ATP de Windows Defender en Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="211bd-130">Enable Windows Defender ATP integration into Microsoft Intune</span></span>
- <span data-ttu-id="211bd-131">Crear una directiva de Windows Information Protection para Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="211bd-131">Create a Microsoft Intune Windows Information Protection Policy</span></span>
- <span data-ttu-id="211bd-132">Requerir que todos los dispositivos tengan configuraciones de seguridad avanzada</span><span class="sxs-lookup"><span data-stu-id="211bd-132">Require all devices to have advanced security configurations</span></span>
- <span data-ttu-id="211bd-133">Revisar semanalmente el informe de dispositivos bloqueados</span><span class="sxs-lookup"><span data-stu-id="211bd-133">Review blocked devices report weekly</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a><span data-ttu-id="211bd-134">Eliminación de acciones de mejora que no cumplen las expectativas para una medida fiable</span><span class="sxs-lookup"><span data-stu-id="211bd-134">Removing improvement actions that don't meet expectations for reliable measurement</span></span> 

<span data-ttu-id="211bd-135">Para asegurarse de que la puntuación segura de Microsoft es significativa y que cada acción de mejora es medible y confiable, se quitan las siguientes acciones de mejora.</span><span class="sxs-lookup"><span data-stu-id="211bd-135">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="211bd-136">Activar la grabación de datos de auditoría</span><span class="sxs-lookup"><span data-stu-id="211bd-136">Turn on audit data recording</span></span>
- <span data-ttu-id="211bd-137">Descubra aplicaciones de TI de instantáneas arriesgadas y no compatibles</span><span class="sxs-lookup"><span data-stu-id="211bd-137">Discover risky and non-compliant shadow IT applications</span></span>
- <span data-ttu-id="211bd-138">Revisión de permisos & bloquear aplicaciones de OAuth arriesgadas conectadas a su entorno</span><span class="sxs-lookup"><span data-stu-id="211bd-138">Review permissions & block risky OAuth applications connected to your environment</span></span>
- <span data-ttu-id="211bd-139">Configurar el control de versiones en las bibliotecas de documentos de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="211bd-139">Set up versioning on SharePoint online document libraries</span></span>

### <a name="mfa-improvement-action-updates"></a><span data-ttu-id="211bd-140">Actualizaciones de acciones de mejora de MFA</span><span class="sxs-lookup"><span data-stu-id="211bd-140">MFA improvement action updates</span></span>

<span data-ttu-id="211bd-141">Para reflejar la necesidad de las empresas de garantizar la máxima seguridad al aplicar las directivas que funcionan con su negocio, la calificación segura de Microsoft es quitar tres acciones de mejora centradas alrededor de la autenticación multifactor y agregando dos.</span><span class="sxs-lookup"><span data-stu-id="211bd-141">To reflect the need for businesses to ensure the upmost security while applying policies that work with their business, Microsoft Secure Score is removing three improvement actions centered around multi-factor authentication, and adding two.</span></span>

<span data-ttu-id="211bd-142">Los tres que se quitarán:</span><span class="sxs-lookup"><span data-stu-id="211bd-142">The three that will be removed:</span></span>

- <span data-ttu-id="211bd-143">Registrar todos los usuarios para la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="211bd-143">Register all users for multi-factor authentication</span></span>
- <span data-ttu-id="211bd-144">Requerir MFA para todos los usuarios</span><span class="sxs-lookup"><span data-stu-id="211bd-144">Require MFA for all users</span></span>
- <span data-ttu-id="211bd-145">Requerir MFA para los roles privilegiados de Azure AD</span><span class="sxs-lookup"><span data-stu-id="211bd-145">Require MFA for Azure AD privileged roles</span></span>

<span data-ttu-id="211bd-146">Nuevas acciones de mejora agregadas:</span><span class="sxs-lookup"><span data-stu-id="211bd-146">New improvement actions added:</span></span>

- <span data-ttu-id="211bd-147">Asegurarse de que todos los usuarios puedan completar la autenticación multifactor para el acceso seguro</span><span class="sxs-lookup"><span data-stu-id="211bd-147">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="211bd-148">Requerir MFA para roles administrativos</span><span class="sxs-lookup"><span data-stu-id="211bd-148">Require MFA for administrative roles</span></span>

 <span data-ttu-id="211bd-149">Estas nuevas acciones de mejora requerirán el registro de los usuarios o administradores para la autenticación multifactor (MFA) en el directorio y el establecimiento del conjunto adecuado de directivas que se adapten a las necesidades de la organización.</span><span class="sxs-lookup"><span data-stu-id="211bd-149">These new improvement actions will require registering your users or admins for multi-factor authentication (MFA) across your directory and establishing the right set of policies that fit your organizational needs.</span></span> <span data-ttu-id="211bd-150">El objetivo principal es tener flexibilidad a la vez que se asegura de que todos los usuarios y administradores puedan autenticarse con varios factores o solicitudes de verificación de identidad basadas en riesgos.</span><span class="sxs-lookup"><span data-stu-id="211bd-150">The main goal is have flexibility while ensuring all your users and admins can authenticate with multiple factors or risk-based identity verification prompts.</span></span> <span data-ttu-id="211bd-151">Esto puede tener la forma de tener varias directivas que apliquen decisiones en el ámbito o establecer los valores predeterminados de seguridad (desde el 16 de marzo) que permitan a Microsoft decidir cuándo debe desafiar a los usuarios para MFA.</span><span class="sxs-lookup"><span data-stu-id="211bd-151">That can take the form of having multiple policies that apply scoped decisions, or setting security defaults (coming March 16th) that let Microsoft decide when to challenge users for MFA.</span></span>

### <a name="removing-review-improvement-actions"></a><span data-ttu-id="211bd-152">Eliminación de acciones de mejora de "revisión"</span><span class="sxs-lookup"><span data-stu-id="211bd-152">Removing “review” improvement actions</span></span>

<span data-ttu-id="211bd-153">Uno de los principios de la puntuación segura es que la puntuación debe estar estandarizada y ser fácil de relacionar con.</span><span class="sxs-lookup"><span data-stu-id="211bd-153">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="211bd-154">Las acciones de mejora que no se pueden medir o realizar acciones han causado confusión.</span><span class="sxs-lookup"><span data-stu-id="211bd-154">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="211bd-155">Una calificación segura de Microsoft solo tiene sentido cuando cada recomendación puede tener un efecto claro en la puntuación.</span><span class="sxs-lookup"><span data-stu-id="211bd-155">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="211bd-156">Revisión las acciones de mejora no se miden en el mismo estándar que otras acciones de mejora.</span><span class="sxs-lookup"><span data-stu-id="211bd-156">Review improvement actions are not measured to the same standard as other improvement actions.</span></span>  

<span data-ttu-id="211bd-157">Por estos motivos, todas las acciones de mejora que requerían una cadencia de revisión se eliminarán temporalmente.</span><span class="sxs-lookup"><span data-stu-id="211bd-157">For these reasons, all improvement actions that required a review cadence will be temporarily removed.</span></span> <span data-ttu-id="211bd-158">No es necesario realizar ninguna acción en su parte.</span><span class="sxs-lookup"><span data-stu-id="211bd-158">No action is needed on your part.</span></span>

## <a name="march-16th-2020"></a><span data-ttu-id="211bd-159">16 de marzo de 2020</span><span class="sxs-lookup"><span data-stu-id="211bd-159">March 16th 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="211bd-160">Eliminación de acciones de mejora que no cumplen con las expectativas para una medición fiable o que no proporcionan una representación útil de la postura de seguridad</span><span class="sxs-lookup"><span data-stu-id="211bd-160">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="211bd-161">Para asegurarse de que la puntuación segura de Microsoft es significativa y que cada acción de mejora es medible y confiable, se quitan las siguientes acciones de mejora.</span><span class="sxs-lookup"><span data-stu-id="211bd-161">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="211bd-162">Almacenar documentos de usuario en OneDrive para la empresa</span><span class="sxs-lookup"><span data-stu-id="211bd-162">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="211bd-163">Configurar las directivas de datos adjuntos seguros de Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="211bd-163">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="211bd-164">Configurar vínculos seguros de Office 365 para comprobar direcciones URL</span><span class="sxs-lookup"><span data-stu-id="211bd-164">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="211bd-165">No permitir la delegación de buzones</span><span class="sxs-lookup"><span data-stu-id="211bd-165">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="211bd-166">Permitir vínculos de uso compartido de invitados anónimos para sitios y documentos</span><span class="sxs-lookup"><span data-stu-id="211bd-166">Allow anonymous guest sharing links for sites and docs</span></span>
- <span data-ttu-id="211bd-167">Activar la consola de Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="211bd-167">Turn on Cloud App Security Console</span></span>

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="211bd-168">Compatibilidad con los valores predeterminados de seguridad para acciones de mejora de Azure AD</span><span class="sxs-lookup"><span data-stu-id="211bd-168">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="211bd-169">La calificación segura de Microsoft actualizará las acciones de mejora para admitir los [valores predeterminados de seguridad en Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), que facilitan la protección de la organización con opciones de seguridad preconfiguradas para ataques comunes.</span><span class="sxs-lookup"><span data-stu-id="211bd-169">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="211bd-170">Afectará a las siguientes acciones de mejora:</span><span class="sxs-lookup"><span data-stu-id="211bd-170">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="211bd-171">Asegurarse de que todos los usuarios puedan completar la autenticación multifactor para el acceso seguro</span><span class="sxs-lookup"><span data-stu-id="211bd-171">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="211bd-172">Requerir MFA para roles administrativos</span><span class="sxs-lookup"><span data-stu-id="211bd-172">Require MFA for administrative roles</span></span>
- <span data-ttu-id="211bd-173">Habilitar la Directiva para bloquear la autenticación heredada</span><span class="sxs-lookup"><span data-stu-id="211bd-173">Enable policy to block legacy authentication</span></span>
