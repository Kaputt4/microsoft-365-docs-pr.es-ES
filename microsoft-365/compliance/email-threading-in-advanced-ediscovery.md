---
title: Subprocesos de correo electrónico en Advanced eDiscovery
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
description: Al realizar un análisis Advanced eDiscovery, el subproceso de correo electrónico analiza una conversación de correo electrónico y separa cada mensaje en diferentes categorías.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285566"
---
# <a name="email-threading-in-advanced-ediscovery"></a><span data-ttu-id="19000-103">Subprocesos de correo electrónico en Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="19000-103">Email threading in Advanced eDiscovery</span></span>

<span data-ttu-id="19000-104">Considere una conversación de correo electrónico que ha estado sucediendo durante un tiempo.</span><span class="sxs-lookup"><span data-stu-id="19000-104">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="19000-105">En la mayoría de los casos, el último correo electrónico del subproceso incluirá el contenido de todos los correos electrónicos anteriores; revisar el último correo electrónico le dará un contexto completo de la conversación que ocurrió en el subproceso.</span><span class="sxs-lookup"><span data-stu-id="19000-105">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="19000-106">El subproceso de correo electrónico identifica dichos correos electrónicos para que los revisores puedan revisar una fracción de documentos recopilados sin perder ningún contexto.</span><span class="sxs-lookup"><span data-stu-id="19000-106">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="19000-107">¿Qué hace el subproceso de correo electrónico?</span><span class="sxs-lookup"><span data-stu-id="19000-107">What does email threading do?</span></span>

<span data-ttu-id="19000-108">El subproceso de correo electrónico analiza cada correo electrónico y lo deconstruye en mensajes individuales; cada correo electrónico es una cadena de mensajes individuales.</span><span class="sxs-lookup"><span data-stu-id="19000-108">Email threading parses each email and deconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="19000-109">A continuación, analiza todos los correos electrónicos del conjunto de revisión para determinar si un correo electrónico tiene contenido único o si la cadena está totalmente contenida en un correo electrónico diferente.</span><span class="sxs-lookup"><span data-stu-id="19000-109">Then, it analyzes all emails in the review set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="19000-110">Al final, los correos electrónicos se dividen en cuatro categorías:</span><span class="sxs-lookup"><span data-stu-id="19000-110">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="19000-111">**Hilo completo**: el último mensaje del correo electrónico tiene contenido único y, además, el correo electrónico tiene todos los datos adjuntos que se incluyeron en otros correos electrónicos cuyo contenido está contenido en este correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="19000-111">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="19000-112">**Hilo completo sin un adjunto**: el último mensaje del correo electrónico tiene contenido único, pero el correo electrónico no contiene algunos de los datos adjuntos que se incluyeron en otros correos electrónicos cuyo contenido contenga este correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="19000-112">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="19000-113">**Copia de hilo completo**: una copia exacta de un correo electrónico de hilo completo o hilo completo sin un adjunto</span><span class="sxs-lookup"><span data-stu-id="19000-113">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="19000-114">**Ninguno**: el contenido de este correo electrónico está contenido en al menos un correo electrónico que se marca como "menos inclusivo/inclusivo".</span><span class="sxs-lookup"><span data-stu-id="19000-114">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="19000-115">¿En qué se diferencia de las conversaciones de Outlook?</span><span class="sxs-lookup"><span data-stu-id="19000-115">How is it different from conversations in Outlook?</span></span>

<span data-ttu-id="19000-116">De un vistazo, esto suena similar a las agrupaciones de conversaciones en Outlook.</span><span class="sxs-lookup"><span data-stu-id="19000-116">At a glance, this sounds similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="19000-117">Sin embargo, hay algunas distinciones importantes.</span><span class="sxs-lookup"><span data-stu-id="19000-117">However, there are some important distinctions.</span></span> <span data-ttu-id="19000-118">Considere una conversación de correo electrónico que se bifurca en dos conversaciones; por ejemplo, alguien respondió a un correo electrónico que no es el más reciente de la conversación, por lo que los dos últimos correos electrónicos de la conversación tienen contenido único.</span><span class="sxs-lookup"><span data-stu-id="19000-118">Consider an email conversation that got forked into two conversations; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="19000-119">Outlook seguiría agrupando los correos electrónicos en una sola conversación; leer solo el último correo electrónico significaría faltar al contexto del segundo y último correo electrónico, que también contiene contenido único.</span><span class="sxs-lookup"><span data-stu-id="19000-119">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="19000-120">Dado que el subproceso de correo electrónico analiza cada correo electrónico en componentes individuales y los compara, el subproceso de correo electrónico marcaría los dos últimos correos electrónicos como inclusivos, lo que garantiza que no se pierda ningún contexto mientras lea todos los correos electrónicos marcados como inclusivos.</span><span class="sxs-lookup"><span data-stu-id="19000-120">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusive, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>
