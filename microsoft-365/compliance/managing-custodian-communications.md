---
title: Trabajar con comunicaciones en Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery facilita la administración del flujo de trabajo de notificación de retención legal en torno a notificar a los custodios en investigaciones legales.
ms.openlocfilehash: 28b719a83cbc1608ad5468e401a8b7946cb8da5f
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551251"
---
# <a name="work-with-communications-in-advanced-ediscovery"></a><span data-ttu-id="72a61-103">Trabajar con comunicaciones en Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="72a61-103">Work with communications in Advanced eDiscovery</span></span>

<span data-ttu-id="72a61-104">Advanced eDiscovery permite a los departamentos legales simplificar sus procesos en torno al seguimiento y distribución de notificaciones de retención legal.</span><span class="sxs-lookup"><span data-stu-id="72a61-104">Advanced eDiscovery allows legal departments to simplify their processes around tracking and distributing legal hold notifications.</span></span> <span data-ttu-id="72a61-105">La herramienta de comunicaciones de custodia permite a los departamentos legales administrar y automatizar todo el proceso de retención legal, desde las notificaciones iniciales, hasta los avisos y las escalaciones, todo en una ubicación.</span><span class="sxs-lookup"><span data-stu-id="72a61-105">The custodian communications tool enables legal departments to manage and automate the entire legal hold process, from initial notifications, to reminders, and to escalations, all in one location.</span></span>

## <a name="what-is-a-legal-hold-notification"></a><span data-ttu-id="72a61-106">¿Qué es una notificación de retención legal?</span><span class="sxs-lookup"><span data-stu-id="72a61-106">What is a legal hold notification?</span></span>

<span data-ttu-id="72a61-107">Un aviso de retención legal (también conocido como retención por *juicio)* es una notificación enviada desde el departamento jurídico de una organización a empleados, personal contingente o custodios de datos que pueden ser relevantes para una investigación legal.</span><span class="sxs-lookup"><span data-stu-id="72a61-107">A legal hold (also known as a *litigation hold*) notice is a notification sent from an organization’s legal department to employees, contingent staff, or custodians of data that may be relevant to a legal investigation.</span></span> <span data-ttu-id="72a61-108">Estas notificaciones instruyen a los custodios a conservar la información almacenada electrónicamente, así como cualquier contenido que pueda ser relevante para un asunto legal activo o inminente.</span><span class="sxs-lookup"><span data-stu-id="72a61-108">These notifications instruct custodians to preserve electronically stored information as well as any content that may be relevant to an active or impending legal matter.</span></span> <span data-ttu-id="72a61-109">Los equipos legales deben saber que cada custodio ha recibido, leído, comprendido y aceptado cumplir con las instrucciones dadas.</span><span class="sxs-lookup"><span data-stu-id="72a61-109">Legal teams must know that each custodian has received, read, understood, and has agreed to comply with the given instructions.</span></span>

## <a name="the-legal-hold-notification-process"></a><span data-ttu-id="72a61-110">El proceso de notificación de retención legal</span><span class="sxs-lookup"><span data-stu-id="72a61-110">The legal hold notification process</span></span>

<span data-ttu-id="72a61-111">Una organización tiene el deber de conservar la información relevante cuando se entera de un litigio inminente o una investigación reglamentaria.</span><span class="sxs-lookup"><span data-stu-id="72a61-111">An organization has a duty to preserve relevant information when it learns about an impending litigation or regulatory investigation.</span></span> <span data-ttu-id="72a61-112">Para cumplir con los requisitos de conservación de una investigación, la organización debe informar inmediatamente a los posibles custodios sobre su deber de conservar información relevante.</span><span class="sxs-lookup"><span data-stu-id="72a61-112">To comply with the preservation requirements of an investigation, the organization should immediately inform potential custodians about their duty to preserve relevant information.</span></span>

<span data-ttu-id="72a61-113">Con Advanced eDiscovery, los equipos legales pueden crear y personalizar su flujo de trabajo de notificación de retención legal.</span><span class="sxs-lookup"><span data-stu-id="72a61-113">With Advanced eDiscovery, legal teams can create and customize their legal hold notification workflow.</span></span> <span data-ttu-id="72a61-114">La herramienta de comunicaciones de custodia permite a los equipos legales configurar los siguientes avisos y flujos de trabajo:</span><span class="sxs-lookup"><span data-stu-id="72a61-114">The custodian communications tool lets legal teams to configure the following notices and workflows:</span></span>

1. <span data-ttu-id="72a61-115">**Aviso de emisión:** Una notificación del departamento jurídico emite (o inicia) un aviso de retención legal a los custodios que pueden tener información relevante sobre el caso.</span><span class="sxs-lookup"><span data-stu-id="72a61-115">**Issuance notice:** A legal hold notice is issued (or initiated) by a notification from the legal department to custodians who may have relevant information about the case matter.</span></span> <span data-ttu-id="72a61-116">Este aviso indica a los administradores que conserven toda la información que pueda ser necesaria para la detección.</span><span class="sxs-lookup"><span data-stu-id="72a61-116">This notice instructs the custodians to preserve any information that may be needed for discovery.</span></span>

2. <span data-ttu-id="72a61-117">**Aviso de ree emisión:** Durante un caso, es posible que los custodios deban conservar contenido adicional (o menos contenido) del solicitado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="72a61-117">**Re-Issuance notice:** During a case, custodians may be required to preserve additional content (or less content) than was previously requested.</span></span> <span data-ttu-id="72a61-118">Para este escenario, puede actualizar el aviso de retención existente y volver a emitirlo a los custodios.</span><span class="sxs-lookup"><span data-stu-id="72a61-118">For this scenario, you can update the existing hold notice and re-issue it to custodians.</span></span>

3. <span data-ttu-id="72a61-119">**Aviso de lanzamiento:** Una vez resuelto un asunto y el custodio ya no está sujeto a un requisito de conservación, el custodio puede ser liberado del caso.</span><span class="sxs-lookup"><span data-stu-id="72a61-119">**Release notice:** Once a matter is resolved and the custodian is no longer subject to a preservation requirement, the custodian can be released from the case.</span></span> <span data-ttu-id="72a61-120">Además, puede notificar al custodio que ya no es necesario conservar el contenido y proporcionar instrucciones sobre cómo reanudar su actividad laboral normal con respecto a sus datos.</span><span class="sxs-lookup"><span data-stu-id="72a61-120">Additionally, you can notify the custodian that they are no longer required to preserve content, and provide instructions about how to resume their normal work activity with regard to their data.</span></span>

4. <span data-ttu-id="72a61-121">**Avisos y escalaciones:** En algunos casos, solo emitir un aviso no es suficiente para satisfacer los requisitos legales de detección.</span><span class="sxs-lookup"><span data-stu-id="72a61-121">**Reminders and escalations:** In some instances, just issuing a notice isn't enough to satisfy legal discovery requirements.</span></span> <span data-ttu-id="72a61-122">Con cada notificación, los equipos legales pueden programar un conjunto de flujos de trabajo de aviso y escalación para seguir automáticamente el seguimiento con custodios que no responden.</span><span class="sxs-lookup"><span data-stu-id="72a61-122">With each notification, legal teams can schedule a set of reminder and escalation workflows to automatically follow up with unresponsive custodians.</span></span>

   - <span data-ttu-id="72a61-123">**Avisos:** Después de emitir o volver a emitir un aviso de retención legal a un conjunto de custodios, una organización puede configurar avisos para alertar a los custodios no responsables.</span><span class="sxs-lookup"><span data-stu-id="72a61-123">**Reminders:** After a legal hold notice has been issued or re-issued to a set of custodians, an organization can set up reminders to alert unresponsive custodians.</span></span>

   - <span data-ttu-id="72a61-124">**Escalaciones:** En algunos casos, si un custodio sigue sin responder incluso después de un conjunto de avisos durante un período de tiempo, el equipo legal puede configurar un flujo de trabajo de escalamiento para notificar a los custodios no responsables y a su administrador.</span><span class="sxs-lookup"><span data-stu-id="72a61-124">**Escalations:** In some cases, if a custodian remains unresponsive even after a set of reminders over a period of time, the legal team can set up an escalation workflow to notify unresponsive custodians and their manager.</span></span>

<span data-ttu-id="72a61-125">Para obtener más información acerca de cómo administrar el proceso de comunicación de custodia, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="72a61-125">For more information about managing the custodian communication process, see the following:</span></span> 

- [<span data-ttu-id="72a61-126">Crear un aviso de retención legal</span><span class="sxs-lookup"><span data-stu-id="72a61-126">Create a legal hold notice</span></span>](create-hold-notification.md)

- [<span data-ttu-id="72a61-127">Usar el editor de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="72a61-127">Use the communications editor</span></span>](using-communications-editor.md)

- [<span data-ttu-id="72a61-128">Administrar las notificaciones de retención</span><span class="sxs-lookup"><span data-stu-id="72a61-128">Manage hold notifications</span></span>](manage-hold-notification.md)

- [<span data-ttu-id="72a61-129">Confirmar una notificación de retención</span><span class="sxs-lookup"><span data-stu-id="72a61-129">Acknowledge a hold notification</span></span>](acknowledge-hold-notification.md)