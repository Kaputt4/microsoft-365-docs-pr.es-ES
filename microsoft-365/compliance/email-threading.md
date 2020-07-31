---
title: 'Subprocesamiento de correo electrónico: investigaciones de datos'
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
description: Al administrar una investigación de datos, el subprocesamiento de correo electrónico analiza una conversación de correo electrónico y separa cada mensaje en categorías diferentes.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 66238d87bd314f2b29e77886f33cb53f9a879aff
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527668"
---
# <a name="email-threading"></a><span data-ttu-id="b0410-103">Subprocesos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="b0410-103">Email threading</span></span>

<span data-ttu-id="b0410-104">Considere una conversación de correo electrónico que ha estado ocurriendo durante un rato.</span><span class="sxs-lookup"><span data-stu-id="b0410-104">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="b0410-105">En la mayoría de los casos, el último correo electrónico del hilo incluirá el contenido de todos los mensajes de correo electrónico anteriores; la revisión del último correo electrónico proporcionará un contexto completo de la conversación que se produjo en el hilo.</span><span class="sxs-lookup"><span data-stu-id="b0410-105">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="b0410-106">El encadenamiento de correo electrónico identifica dichos mensajes para que los revisores puedan revisar una fracción de los documentos recopilados sin perder ningún contexto.</span><span class="sxs-lookup"><span data-stu-id="b0410-106">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="b0410-107">¿Qué hace la función de subprocesos de correo electrónico?</span><span class="sxs-lookup"><span data-stu-id="b0410-107">What does email threading do?</span></span>

<span data-ttu-id="b0410-108">La creación de subprocesos de correo electrónico analiza cada correo electrónico y lo desconstruye en mensajes individuales; cada correo electrónico es una cadena de mensajes individuales.</span><span class="sxs-lookup"><span data-stu-id="b0410-108">Email threading parses each email and deconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="b0410-109">A continuación, analiza todos los correos electrónicos en el conjunto de trabajo para determinar si un correo electrónico tiene contenido único o si la cadena está contenida por completo en un correo electrónico diferente.</span><span class="sxs-lookup"><span data-stu-id="b0410-109">Then, it analyzes all emails in the working set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="b0410-110">En los mensajes de correo electrónico finales se dividen en cuatro categorías:</span><span class="sxs-lookup"><span data-stu-id="b0410-110">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="b0410-111">**Ambos inclusive**: el último mensaje del correo electrónico tiene contenido único y el correo electrónico tiene todos los datos adjuntos que se incluyeron en otros mensajes de correo electrónico cuyo contenido está incluido por completo en este correo.</span><span class="sxs-lookup"><span data-stu-id="b0410-111">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>


- <span data-ttu-id="b0410-112">**Menos inclusivo**: el último mensaje del correo electrónico tiene contenido único, pero el correo electrónico no contiene algunos de los datos adjuntos que se incluyeron en otros mensajes de correo electrónico cuyo contenido está contenido por completo en este correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b0410-112">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="b0410-113">**Copia inclusiva**: copia exacta de un correo electrónico menos inclusivo inclusive</span><span class="sxs-lookup"><span data-stu-id="b0410-113">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="b0410-114">**Ninguno**: el contenido de este correo electrónico está contenido por completo en al menos un mensaje de correo electrónico que está marcado como incluido/incluido en el signo menos.</span><span class="sxs-lookup"><span data-stu-id="b0410-114">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="b0410-115">¿En qué se diferencia de las conversaciones en Outlook?</span><span class="sxs-lookup"><span data-stu-id="b0410-115">How is it different from conversations in Outlook?</span></span>
<span data-ttu-id="b0410-116">De un solo vistazo, esto suena de forma similar a las agrupaciones de conversaciones en Outlook.</span><span class="sxs-lookup"><span data-stu-id="b0410-116">At a glance, this sounds similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="b0410-117">Sin embargo, hay algunas distinciones importantes.</span><span class="sxs-lookup"><span data-stu-id="b0410-117">However, there are some important distinctions.</span></span> <span data-ttu-id="b0410-118">Considere una conversación de correo electrónico que se ha bifurcado en dos conversaciones; por ejemplo, alguien respondió a un correo electrónico que no es el más reciente en la conversación, por lo que los dos últimos correos electrónicos de la conversación tienen contenido único.</span><span class="sxs-lookup"><span data-stu-id="b0410-118">Consider an email conversation that got forked into two conversations; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="b0410-119">Outlook seguiría agrupando los correos electrónicos en una sola conversación; leer solo el último correo electrónico significa que falta el contexto del segundo al último correo electrónico, que también incluye contenido único.</span><span class="sxs-lookup"><span data-stu-id="b0410-119">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="b0410-120">Como la subprocesamiento de correo electrónico analiza cada correo electrónico en componentes individuales y los compara, el subprocesamiento de correo electrónico marcaría los dos últimos correos electrónicos como incluidos, lo que garantiza que no perderá ningún contexto mientras haya leído todos los correos electrónicos marcados como incluidos.</span><span class="sxs-lookup"><span data-stu-id="b0410-120">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusive, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>
