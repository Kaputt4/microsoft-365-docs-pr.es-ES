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
ms.openlocfilehash: 1a5c5ae702f16bbf47be83837cf244cdd64278cd
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "43541112"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="42e29-104">¿Qué viene con la puntuación segura de Microsoft?</span><span class="sxs-lookup"><span data-stu-id="42e29-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="42e29-105">Para hacer que la puntuación segura de Microsoft sea un mejor representante de su postura de seguridad y mejorar el uso, estamos realizando algunos cambios en un futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="42e29-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="42e29-106">Se cambiará la puntuación y la puntuación máxima posible.</span><span class="sxs-lookup"><span data-stu-id="42e29-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="42e29-107">Sin embargo, esto no implica un cambio en su postura de seguridad.</span><span class="sxs-lookup"><span data-stu-id="42e29-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="42e29-108">Para obtener más información sobre los cambios recientes, vea [what's New in Secure score de Microsoft](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="42e29-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="42e29-109">21 de abril de 2020</span><span class="sxs-lookup"><span data-stu-id="42e29-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="42e29-110">Eliminación de acciones de mejora que no cumplen con las expectativas para una medición fiable o que no proporcionan una representación útil de la postura de seguridad</span><span class="sxs-lookup"><span data-stu-id="42e29-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="42e29-111">Para asegurarse de que la puntuación segura de Microsoft es significativa y que cada acción de mejora es medible y confiable, se quitan las siguientes acciones de mejora.</span><span class="sxs-lookup"><span data-stu-id="42e29-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="42e29-112">Aplicar protecciones de IRM a los documentos</span><span class="sxs-lookup"><span data-stu-id="42e29-112">Apply IRM protections to documents</span></span>
- <span data-ttu-id="42e29-113">Aplicar directivas de prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="42e29-113">Apply Data Loss Prevention policies</span></span>

### <a name="adding-azure-ad-improvement-action-in-the-preview-version"></a><span data-ttu-id="42e29-114">Adición de la acción de mejora de Azure AD en la versión preliminar</span><span class="sxs-lookup"><span data-stu-id="42e29-114">Adding Azure AD improvement action in the preview version</span></span>

- <span data-ttu-id="42e29-115">No permitir a los usuarios conceder consentimiento a las aplicaciones no administradas (actualmente disponibles en la versión de lanzamiento)</span><span class="sxs-lookup"><span data-stu-id="42e29-115">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

### <a name="adding-azure-atp-improvement-actions-in-the-preview-version"></a><span data-ttu-id="42e29-116">Adición de acciones de mejora de ATP de Azure en la versión preliminar</span><span class="sxs-lookup"><span data-stu-id="42e29-116">Adding Azure ATP improvement actions in the preview version</span></span>

- <span data-ttu-id="42e29-117">Deshabilitar el servicio de cola de impresión en controladores de dominio</span><span class="sxs-lookup"><span data-stu-id="42e29-117">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="42e29-118">Modificar las delegaciones Kerberos no seguras para impedir la suplantación</span><span class="sxs-lookup"><span data-stu-id="42e29-118">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="42e29-119">Proteger y administrar contraseñas de administración local con los intervalos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="42e29-119">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="42e29-120">Reducir el riesgo de ruta de movimiento lateral a las entidades confidenciales</span><span class="sxs-lookup"><span data-stu-id="42e29-120">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="42e29-121">Eliminación de cuentas latentes de grupos confidenciales</span><span class="sxs-lookup"><span data-stu-id="42e29-121">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="42e29-122">Quitar atributos del historial SID no seguro de entidades</span><span class="sxs-lookup"><span data-stu-id="42e29-122">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="42e29-123">Resolver atributos de cuenta no segura</span><span class="sxs-lookup"><span data-stu-id="42e29-123">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="42e29-124">Detener la exposición de credenciales de texto no cifrado</span><span class="sxs-lookup"><span data-stu-id="42e29-124">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="42e29-125">Detener la comunicación de protocolos heredados</span><span class="sxs-lookup"><span data-stu-id="42e29-125">Stop legacy protocols communication</span></span>
- <span data-ttu-id="42e29-126">Detener el uso de cifrado débil</span><span class="sxs-lookup"><span data-stu-id="42e29-126">Stop weak cipher usage</span></span>

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-the-preview-version"></a><span data-ttu-id="42e29-127">Compatibilidad con las recomendaciones de seguridad de la amenaza ATP de Microsoft defender & Vulnerability Management (TVM) en la versión preliminar</span><span class="sxs-lookup"><span data-stu-id="42e29-127">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations in the preview version</span></span>

- <span data-ttu-id="42e29-128">Todas las recomendaciones de seguridad emitidas suministradas por TVM ahora también estarán disponibles en la calificación segura de Microsoft</span><span class="sxs-lookup"><span data-stu-id="42e29-128">All released security recommendations supplied by TVM will now also be available in Microsoft Secure Score</span></span>
