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
ms.openlocfilehash: efb75f26d66258880c9defa94869f27e18685052
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372008"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="c52cb-104">¿Qué viene con la puntuación segura de Microsoft?</span><span class="sxs-lookup"><span data-stu-id="c52cb-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="c52cb-105">Para hacer que la puntuación segura de Microsoft sea un mejor representante de su postura de seguridad y mejorar el uso, estamos realizando algunos cambios en un futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="c52cb-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="c52cb-106">Se cambiará la puntuación y la puntuación máxima posible.</span><span class="sxs-lookup"><span data-stu-id="c52cb-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="c52cb-107">Sin embargo, esto no implica un cambio en su postura de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c52cb-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="c52cb-108">Para obtener más información sobre los cambios recientes, vea [what's New in Secure score de Microsoft](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="c52cb-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="march-16th-2020"></a><span data-ttu-id="c52cb-109">16 de marzo de 2020</span><span class="sxs-lookup"><span data-stu-id="c52cb-109">March 16th 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="c52cb-110">Eliminación de acciones de mejora que no cumplen con las expectativas para una medición fiable o que no proporcionan una representación útil de la postura de seguridad</span><span class="sxs-lookup"><span data-stu-id="c52cb-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="c52cb-111">Para asegurarse de que la puntuación segura de Microsoft es significativa y que cada acción de mejora es medible y confiable, se quitan las siguientes acciones de mejora.</span><span class="sxs-lookup"><span data-stu-id="c52cb-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="c52cb-112">Almacenar documentos de usuario en OneDrive para la empresa</span><span class="sxs-lookup"><span data-stu-id="c52cb-112">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="c52cb-113">Configurar las directivas de datos adjuntos seguros de Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="c52cb-113">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="c52cb-114">Configurar vínculos seguros de Office 365 para comprobar direcciones URL</span><span class="sxs-lookup"><span data-stu-id="c52cb-114">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="c52cb-115">No permitir la delegación de buzones</span><span class="sxs-lookup"><span data-stu-id="c52cb-115">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="c52cb-116">Permitir vínculos de uso compartido de invitados anónimos para sitios y documentos</span><span class="sxs-lookup"><span data-stu-id="c52cb-116">Allow anonymous guest sharing links for sites and docs</span></span>
- <span data-ttu-id="c52cb-117">Activar la consola de Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c52cb-117">Turn on Cloud App Security Console</span></span>
- <span data-ttu-id="c52cb-118">Configurar el tiempo de expiración de los vínculos de uso compartido externo</span><span class="sxs-lookup"><span data-stu-id="c52cb-118">Configure expiration time for external sharing links</span></span>

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="c52cb-119">Compatibilidad con los valores predeterminados de seguridad para acciones de mejora de Azure AD</span><span class="sxs-lookup"><span data-stu-id="c52cb-119">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="c52cb-120">La calificación segura de Microsoft actualizará las acciones de mejora para admitir los [valores predeterminados de seguridad en Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), que facilitan la protección de la organización con opciones de seguridad preconfiguradas para ataques comunes.</span><span class="sxs-lookup"><span data-stu-id="c52cb-120">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="c52cb-121">Afectará a las siguientes acciones de mejora:</span><span class="sxs-lookup"><span data-stu-id="c52cb-121">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="c52cb-122">Asegurarse de que todos los usuarios puedan completar la autenticación multifactor para el acceso seguro</span><span class="sxs-lookup"><span data-stu-id="c52cb-122">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="c52cb-123">Requerir MFA para roles administrativos</span><span class="sxs-lookup"><span data-stu-id="c52cb-123">Require MFA for administrative roles</span></span>
- <span data-ttu-id="c52cb-124">Habilitar la Directiva para bloquear la autenticación heredada</span><span class="sxs-lookup"><span data-stu-id="c52cb-124">Enable policy to block legacy authentication</span></span>
