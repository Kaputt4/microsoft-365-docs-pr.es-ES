---
title: Respuesta a incidentes de seguridad
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/27/2018
audience: ITPro
ms.topic: overview
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: Esta solución le indica cómo podrían ser los ataques de ciberseguridad más comunes en Microsoft 365 y cómo responder a ellos.
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 65ff75253f45ae2d0f051dafe73c6e665f89827a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073232"
---
# <a name="security-incident-response"></a><span data-ttu-id="9b676-103">Respuesta a incidentes de seguridad</span><span class="sxs-lookup"><span data-stu-id="9b676-103">Security Incident Response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9b676-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="9b676-104">**Applies to**</span></span>
- [<span data-ttu-id="9b676-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9b676-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9b676-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="9b676-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9b676-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b676-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

 <span data-ttu-id="9b676-108">**Resumen:** Esta solución le indica cuáles son los indicadores de los ataques de ciberseguridad más comunes en Office 365, cómo confirmar positivamente cualquier ataque determinado y cómo responder a él.</span><span class="sxs-lookup"><span data-stu-id="9b676-108">**Summary:** This solution tells you what the indicators are for the most common cybersecurity attacks in Office 365, how to positively confirm any given attack, and how to respond to it.</span></span>

## <a name="learn-how-to-respond-to-cyberattacks"></a><span data-ttu-id="9b676-109">Aprenda a responder a los ciberataques</span><span class="sxs-lookup"><span data-stu-id="9b676-109">Learn how to respond to cyberattacks</span></span>

<span data-ttu-id="9b676-110">No todos los ciberataques pueden frustrarse.</span><span class="sxs-lookup"><span data-stu-id="9b676-110">Not all cyberattacks can be thwarted.</span></span> <span data-ttu-id="9b676-111">Los atacantes buscan constantemente nuevas debilidades en la estrategia defensivo o aprovechan las antiguas.</span><span class="sxs-lookup"><span data-stu-id="9b676-111">Attackers are constantly looking for new weaknesses in your defensive strategy or they are exploiting old ones.</span></span> <span data-ttu-id="9b676-112">Saber cómo reconocer un ataque te permite responder a él más rápido, lo que acorta la duración del incidente de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9b676-112">Knowing how to recognize an attack allows you to respond to it faster, which shortens the duration of the security incident.</span></span>

<span data-ttu-id="9b676-113">Esta serie de artículos te ayuda a comprender cómo podría ser un tipo concreto de ataque en Microsoft 365 y te ofrece los pasos que puedes seguir para responder.</span><span class="sxs-lookup"><span data-stu-id="9b676-113">This series of article helps you understand what a particular type of attack might look like in Microsoft 365 and gives you steps you can take to respond.</span></span> <span data-ttu-id="9b676-114">Son puntos de entrada rápidos para comprender:</span><span class="sxs-lookup"><span data-stu-id="9b676-114">They are quick entry points to understanding:</span></span>

- <span data-ttu-id="9b676-115">Cuál es el ataque y cómo funciona.</span><span class="sxs-lookup"><span data-stu-id="9b676-115">What the attack is and how it works.</span></span>

- <span data-ttu-id="9b676-116">Qué signos, denominados indicadores de compromiso (IOC), para buscarlos y cómo buscarlos.</span><span class="sxs-lookup"><span data-stu-id="9b676-116">What signs, called indicators of compromise (IOC), to look for and how to look for them.</span></span>

- <span data-ttu-id="9b676-117">Cómo confirmar positivamente el ataque.</span><span class="sxs-lookup"><span data-stu-id="9b676-117">How to positively confirm the attack.</span></span>

- <span data-ttu-id="9b676-118">Pasos a seguir para cortar el ataque y proteger mejor su organización en el futuro.</span><span class="sxs-lookup"><span data-stu-id="9b676-118">Steps to take to cut off the attack and better protect your organization in the future.</span></span>

- <span data-ttu-id="9b676-119">Vínculos a información detallada sobre cada tipo de ataque.</span><span class="sxs-lookup"><span data-stu-id="9b676-119">Links to in-depth information on each attack type.</span></span>

<span data-ttu-id="9b676-120">Vuelva aquí mensualmente, ya que se agregarán más artículos con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="9b676-120">Check back here monthly as more articles will be added over time.</span></span>

## <a name="detect-and-remediate-articles"></a><span data-ttu-id="9b676-121">Detectar y corregir artículos</span><span class="sxs-lookup"><span data-stu-id="9b676-121">Detect and remediate articles</span></span>

- [<span data-ttu-id="9b676-122">Detectar y solucionar la concesión de consentimiento ilegal en Office 365</span><span class="sxs-lookup"><span data-stu-id="9b676-122">Detect and Remediate Illicit Consent Grants in Office 365</span></span>](detect-and-remediate-illicit-consent-grants.md)

- [<span data-ttu-id="9b676-123">Detectar y corregir las reglas de Outlook y ataques de inserciones de formularios personalizados en Office 365</span><span class="sxs-lookup"><span data-stu-id="9b676-123">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

## <a name="incident-response-articles"></a><span data-ttu-id="9b676-124">Artículos de respuesta a incidentes</span><span class="sxs-lookup"><span data-stu-id="9b676-124">Incident response articles</span></span>

- [<span data-ttu-id="9b676-125">Responder a una cuenta de correo electrónico en peligro en Office 365</span><span class="sxs-lookup"><span data-stu-id="9b676-125">Responding to a Compromised Email Account in Office 365</span></span>](responding-to-a-compromised-email-account.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="9b676-126">Proteger Microsoft 365 como un profesional de la ciberseguridad</span><span class="sxs-lookup"><span data-stu-id="9b676-126">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="9b676-127">Su suscripción a Microsoft 365 incluye un potente conjunto de capacidades de seguridad que puede usar para proteger sus datos y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9b676-127">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="9b676-128">Use el plan de seguridad de Microsoft 365: prioridades principales para los primeros [30 días, 90](security-roadmap.md) días y más para implementar los procedimientos recomendados por Microsoft para proteger su organización de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9b676-128">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 organization.</span></span>

- <span data-ttu-id="9b676-129">Tareas a realizar en los primeros 30 días.</span><span class="sxs-lookup"><span data-stu-id="9b676-129">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="9b676-130">Estas tienen un efecto inmediato y de bajo impacto para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9b676-130">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="9b676-131">Tareas para llevar a cabo en 90 días.</span><span class="sxs-lookup"><span data-stu-id="9b676-131">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="9b676-132">Estos toman un poco más de tiempo para planear e implementar, pero mejoran en gran medida su posición de seguridad</span><span class="sxs-lookup"><span data-stu-id="9b676-132">These take a bit more time to plan and implement but greatly improve your security posture</span></span>

- <span data-ttu-id="9b676-133">Más de 90 días.</span><span class="sxs-lookup"><span data-stu-id="9b676-133">Beyond 90 days.</span></span> <span data-ttu-id="9b676-134">Estas mejoras se crean en el trabajo de los 90 primeros días.</span><span class="sxs-lookup"><span data-stu-id="9b676-134">These enhancements build in your first 90 days work.</span></span>
