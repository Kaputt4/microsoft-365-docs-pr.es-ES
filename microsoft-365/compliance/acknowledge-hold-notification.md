---
title: Reconocer notificaciones de retención
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
description: ''
ms.openlocfilehash: 1a627a0927d6ffa2244e9f3580867379ff1fbdc5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "37092185"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="ca10f-102">Confirmar una notificación de retención</span><span class="sxs-lookup"><span data-stu-id="ca10f-102">Acknowledge a hold notification</span></span> 
<span data-ttu-id="ca10f-103">Al responder a una solicitud o investigación reguladora, es posible que deba informar a los custodios de su obligación de conservar la información almacenada electrónicamente (ESI), así como cualquier material que pueda ser relevante para un asunto legal activo o inminente.</span><span class="sxs-lookup"><span data-stu-id="ca10f-103">When responding to a regulatory request or investigation, you may be required to  inform custodians of their obligation to preserve electronically stored information (ESI) as well as any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="ca10f-104">Una vez enviado, los equipos jurídicos deben saber que cada custodio ha recibido, leído y comprendido, y ha aceptado cumplir con las instrucciones indicadas.</span><span class="sxs-lookup"><span data-stu-id="ca10f-104">Once sent, legal teams must know that each custodian has received, read, and understood, and agreed to comply with the given instructions.</span></span>

<span data-ttu-id="ca10f-105">Para ayudar a reducir el tiempo, el coste y el esfuerzo de seguir con sus custodios, la exhibición avanzada de documentos electrónicos le permite enviar y realizar un seguimiento de las notificaciones de retención legal a través del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ca10f-105">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow-up on legal hold notifications through email.</span></span> <span data-ttu-id="ca10f-106">Además de los avisos de correo electrónico, cada custodio también tendrá acceso a un portal de cumplimiento individualizado, lo que permitirá que los custodios se mantengan informados de los cambios en el estado de su obligación.</span><span class="sxs-lookup"><span data-stu-id="ca10f-106">In addition to email notices, each custodian will also have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="ca10f-107">Notificaciones por correo electrónico</span><span class="sxs-lookup"><span data-stu-id="ca10f-107">Email notifications</span></span>
<span data-ttu-id="ca10f-108">Una vez que se haya emitido una notificación de retención legal, cada custodio recibirá un correo electrónico único y personalizado que incluirá el aviso de suspensión legal definido y las instrucciones agregadas.</span><span class="sxs-lookup"><span data-stu-id="ca10f-108">Once a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!Tip] 
> <span data-ttu-id="ca10f-109">Consulte Cómo puede usar el [Editor de comunicaciones](using-communications-editor.md) integrado para permitir que los custodios reconozcan su aviso u obtengan acceso a su portal de cumplimiento directamente desde su correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ca10f-109">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="ca10f-110">En función de la configuración de la notificación de suspensión legal, es posible que los custodios reciban los siguientes avisos:</span><span class="sxs-lookup"><span data-stu-id="ca10f-110">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="ca10f-111">**Aviso de emisión** : es el primer aviso que se envía a su custodio.</span><span class="sxs-lookup"><span data-stu-id="ca10f-111">**Issuance notice** - This is the first notice sent to your custodian.</span></span> <span data-ttu-id="ca10f-112">Esto contendrá las instrucciones de emisión y la notificación de suspensión anexada al final del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ca10f-112">This will contain your issuance instructions as well as the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="ca10f-113">Aviso de **recordatorio** : si se habilita, se enviará una notificación de recordatorio a los custodios en función de la frecuencia y el intervalo especificados.</span><span class="sxs-lookup"><span data-stu-id="ca10f-113">**Reminder notice** - If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="ca10f-114">Los avisos seguirán enviándose hasta que el custodio haya reconocido su aviso o hasta que se haya agotado el número de avisos.</span><span class="sxs-lookup"><span data-stu-id="ca10f-114">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="ca10f-115">**Aviso de remisión** : si se habilita, se enviará un aviso de remisión a su custodio y a su jefe una vez que se hayan agotado los avisos de recordatorio.</span><span class="sxs-lookup"><span data-stu-id="ca10f-115">**Escalation notice** - If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="ca10f-116">El sistema enviará automáticamente avisos de reasignación hasta que se hayan completado las escalaciones asignadas o hasta que el custodio confirme la notificación de suspensión.</span><span class="sxs-lookup"><span data-stu-id="ca10f-116">The system will automatically send escalation notices until the alloted escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="ca10f-117">**Notificación de reemisión** : durante el transcurso de una investigación, si se actualiza el contenido del aviso de retención, el aviso actualizado se enviará automáticamente al custodio.</span><span class="sxs-lookup"><span data-stu-id="ca10f-117">**Re-issue notice** - During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="ca10f-118">**Aviso de lanzamiento** : cuando se publica un custodio desde el caso, se le enviará el aviso de publicación.</span><span class="sxs-lookup"><span data-stu-id="ca10f-118">**Release notice** - When a custodian is released from the case, they will be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="ca10f-119">Portal de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="ca10f-119">Compliance Portal</span></span>
<span data-ttu-id="ca10f-120">Además de las notificaciones de correo electrónico, cada custodio también tendrá acceso a un portal de cumplimiento único.</span><span class="sxs-lookup"><span data-stu-id="ca10f-120">In addition to the email notifications, each custodian will also have access to a unique Compliance Portal.</span></span> <span data-ttu-id="ca10f-121">A través del portal, cada custodio podrá ver, acceder y reconocer sus notificaciones de retención activas.</span><span class="sxs-lookup"><span data-stu-id="ca10f-121">Through the portal, each custodian will be able to view, access, and acknowledge their active hold notifications.</span></span>

![Portal de cumplimiento de un custodio](media/CustodianPortal.jpg)
