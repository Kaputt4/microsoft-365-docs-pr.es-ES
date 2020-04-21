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
ms.openlocfilehash: 234ae17ab31d56d1bbd65f1aa8ed29475e9cd155
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583720"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="e7d3e-104">¿Qué viene con la puntuación segura de Microsoft?</span><span class="sxs-lookup"><span data-stu-id="e7d3e-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="e7d3e-105">Para hacer que la [puntuación segura de Microsoft](microsoft-secure-score.md) sea un mejor representante de su postura de seguridad y mejorar el uso, estamos realizando algunos cambios en un futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="e7d3e-105">To make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="e7d3e-106">Se cambiará la puntuación y la puntuación máxima posible.</span><span class="sxs-lookup"><span data-stu-id="e7d3e-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="e7d3e-107">Sin embargo, esto no implica un cambio en su postura de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e7d3e-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="e7d3e-108">Para obtener más información sobre los cambios recientes, vea [what's New in Secure score de Microsoft](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="e7d3e-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="e7d3e-109">21 de abril de 2020</span><span class="sxs-lookup"><span data-stu-id="e7d3e-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="e7d3e-110">Eliminación de acciones de mejora que no cumplen con las expectativas para una medición fiable o que no proporcionan una representación útil de la postura de seguridad</span><span class="sxs-lookup"><span data-stu-id="e7d3e-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="e7d3e-111">Para asegurarse de que la puntuación segura de Microsoft es significativa y que cada acción de mejora es medible y confiable, se quitan las siguientes acciones de mejora.</span><span class="sxs-lookup"><span data-stu-id="e7d3e-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="e7d3e-112">Aplicar protecciones de IRM a los documentos</span><span class="sxs-lookup"><span data-stu-id="e7d3e-112">Apply IRM protections to documents</span></span>
- <span data-ttu-id="e7d3e-113">Aplicar directivas de prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="e7d3e-113">Apply Data Loss Prevention policies</span></span>

### <a name="adding-azure-ad-improvement-action-to-preview"></a><span data-ttu-id="e7d3e-114">Adición de la acción de mejora de Azure AD a la vista previa</span><span class="sxs-lookup"><span data-stu-id="e7d3e-114">Adding Azure AD improvement action to preview</span></span>

<span data-ttu-id="e7d3e-115">Adición de la siguiente acción de mejora de Azure Active Directory a la [versión preliminar de la puntuación segura de Microsoft](microsoft-secure-score-preview.md):</span><span class="sxs-lookup"><span data-stu-id="e7d3e-115">Adding the following Azure Active Directory improvement action to the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md):</span></span>

- <span data-ttu-id="e7d3e-116">No permitir a los usuarios conceder consentimiento a las aplicaciones no administradas (actualmente disponibles en la versión de lanzamiento)</span><span class="sxs-lookup"><span data-stu-id="e7d3e-116">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

### <a name="adding-azure-atp-improvement-actions-to-preview"></a><span data-ttu-id="e7d3e-117">Adición de acciones de mejora de ATP de Azure a vista previa</span><span class="sxs-lookup"><span data-stu-id="e7d3e-117">Adding Azure ATP improvement actions to preview</span></span>

<span data-ttu-id="e7d3e-118">Agregar las siguientes acciones de mejora de la protección contra amenazas avanzada de Azure a la [versión preliminar de la puntuación segura de Microsoft](microsoft-secure-score-preview.md):</span><span class="sxs-lookup"><span data-stu-id="e7d3e-118">Adding the following Azure Advanced Threat Protection improvement actions to the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md):</span></span>

- <span data-ttu-id="e7d3e-119">Deshabilitar el servicio de cola de impresión en controladores de dominio</span><span class="sxs-lookup"><span data-stu-id="e7d3e-119">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="e7d3e-120">Modificar las delegaciones Kerberos no seguras para impedir la suplantación</span><span class="sxs-lookup"><span data-stu-id="e7d3e-120">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="e7d3e-121">Proteger y administrar contraseñas de administración local con los intervalos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="e7d3e-121">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="e7d3e-122">Reducir el riesgo de ruta de movimiento lateral a las entidades confidenciales</span><span class="sxs-lookup"><span data-stu-id="e7d3e-122">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="e7d3e-123">Eliminación de cuentas latentes de grupos confidenciales</span><span class="sxs-lookup"><span data-stu-id="e7d3e-123">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="e7d3e-124">Quitar atributos del historial SID no seguro de entidades</span><span class="sxs-lookup"><span data-stu-id="e7d3e-124">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="e7d3e-125">Resolver atributos de cuenta no segura</span><span class="sxs-lookup"><span data-stu-id="e7d3e-125">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="e7d3e-126">Detener la exposición de credenciales de texto no cifrado</span><span class="sxs-lookup"><span data-stu-id="e7d3e-126">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="e7d3e-127">Detener la comunicación de protocolos heredados</span><span class="sxs-lookup"><span data-stu-id="e7d3e-127">Stop legacy protocols communication</span></span>
- <span data-ttu-id="e7d3e-128">Detener el uso de cifrado débil</span><span class="sxs-lookup"><span data-stu-id="e7d3e-128">Stop weak cipher usage</span></span>

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-preview"></a><span data-ttu-id="e7d3e-129">Compatibilidad con las recomendaciones de seguridad de la amenaza ATP de Microsoft defender & Vulnerability Management (TVM) en versión preliminar</span><span class="sxs-lookup"><span data-stu-id="e7d3e-129">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations in preview</span></span>

<span data-ttu-id="e7d3e-130">Todas las recomendaciones de seguridad publicadas suministradas por TVM ahora también estarán disponibles la [versión preliminar de la puntuación segura de Microsoft](microsoft-secure-score-preview.md).</span><span class="sxs-lookup"><span data-stu-id="e7d3e-130">All released security recommendations supplied by TVM will now also be available the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md).</span></span>
