---
title: Usar reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Puede crear una regla de flujo de correo de Exchange para evitar que los usuarios envíen mensajes de correo electrónico a Microsoft para su análisis y usarlos en sus propios procesos de seguridad.
ms.openlocfilehash: 530cc12fd83650f319da3f65e961c925a1de7409
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598067"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="0ac8b-103">Usar reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft</span><span class="sxs-lookup"><span data-stu-id="0ac8b-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="0ac8b-104">There are multiple ways you can send false positive and false negative messages to Microsoft for analysis.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-104">There are multiple ways you can send false positive and false negative messages to Microsoft for analysis.</span></span> <span data-ttu-id="0ac8b-105">Como administrador, puede usar reglas de flujo de correo para ver lo que los usuarios notifican a Microsoft como correo no deseado, fraudes de suplantación de identidad (phishing).</span><span class="sxs-lookup"><span data-stu-id="0ac8b-105">As an administrator, you can use mail flow rules to see what your users are reporting to Microsoft as spam, non-spam, and phishing scams.</span></span> <span data-ttu-id="0ac8b-106">Para obtener más información, vea enviar correo electrónico no deseado, mensajes de correo [no deseado y mensajes de estafa de suplantación de identidad a Microsoft para su análisis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="0ac8b-106">For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span> <span data-ttu-id="0ac8b-107">Por el contrario, puede crear una regla de flujo de correo de Exchange (también denominada regla de transporte) para evitar que los usuarios envíen mensajes de correo electrónico a Microsoft para su análisis y usarlos en sus propios procesos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-107">Conversely, you can create an Exchange mail flow rule (also known as a transport rule) to prevent your users from sending email messages to Microsoft for analysis and use them in your own security processes.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0ac8b-108">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="0ac8b-108">What do you need to know before you begin?</span></span>

<span data-ttu-id="0ac8b-109">Tiempo estimado para finalizar: 5 minutos</span><span class="sxs-lookup"><span data-stu-id="0ac8b-109">Estimated time to complete: 5 minutes</span></span>

<span data-ttu-id="0ac8b-110">Deberá tener permisos asignados para poder llevar a cabo estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-110">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="0ac8b-111">Para ver qué permisos necesita, consulte el entrada "flujo de correo" y "directivas de buzón de correo de Outlook en la web" en [permisos de Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions).</span><span class="sxs-lookup"><span data-stu-id="0ac8b-111">To see what permissions you need, see the "Mail flow"  and "Outlook on the web mailbox policies" entries in [Exchange Online permissions](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions).</span></span>

<span data-ttu-id="0ac8b-112">Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="0ac8b-112">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a><span data-ttu-id="0ac8b-113">Usar el EAC para crear una regla de flujo de correo para ver los informes de correo no deseado manuales de los usuarios, suplantación de identidad (phishing) y no</span><span class="sxs-lookup"><span data-stu-id="0ac8b-113">Use the EAC to create a mail flow rule to view users' manual junk, phishing, and not junk reports</span></span>

1. <span data-ttu-id="0ac8b-114">En el EAC, vaya a **Flujo de correo** \> **Reglas**.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-114">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="0ac8b-115">Click ![Agregar icono](../media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-115">Click ![Add Icon](../media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="0ac8b-116">Give the rule a name and then click **More options**.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-116">Give the rule a name and then click **More options**.</span></span>

4. <span data-ttu-id="0ac8b-117">Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-117">Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.</span></span>

5. <span data-ttu-id="0ac8b-118">En el cuadro **especificar palabras o frases** , siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0ac8b-118">In the **specify words or phrases** box, do the following steps:</span></span>

   - <span data-ttu-id="0ac8b-119">Escriba `abuse@messaging.microsoft.com`, haga \*\*\*\* ![clic en agregar](../media/ITPro-EAC-AddIcon.gif)icono de `junk@office365.microsoft.com` agregar, escriba y, a](../media/ITPro-EAC-AddIcon.gif)continuación, haga clic en **Agregar** ![icono Agregar.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-119">Type `abuse@messaging.microsoft.com`, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif), type `junk@office365.microsoft.com` and then click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="0ac8b-120">These email addresses are used to submit false negative messages to Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-120">These email addresses are used to submit false negative messages to Microsoft.</span></span>

   - <span data-ttu-id="0ac8b-121">Escriba `phish@office365.microsoft.com` y, a continuación, haga](../media/ITPro-EAC-AddIcon.gif)clic en **Agregar** ![icono de agregar.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-121">Type `phish@office365.microsoft.com` and then click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="0ac8b-122">Esta dirección de correo electrónico se usa para enviar mensajes de suplantación de identidad perdidos a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-122">This email address is used to submit missed phishing messages to Microsoft.</span></span>

   - <span data-ttu-id="0ac8b-123">Escriba `false_positive@messaging.microsoft.com`, haga \*\*\*\* ![clic en agregar](../media/ITPro-EAC-AddIcon.gif)icono de `not_junk@office365.microsoft.com`agregar, escriba y, a continuación](../media/ITPro-EAC-AddIcon.gif), haga clic en **Agregar** ![icono de agregar.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-123">Type `false_positive@messaging.microsoft.com`, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif), type `not_junk@office365.microsoft.com`, and then click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="0ac8b-124">These email addresses are used to submit false positive messages to Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-124">These email addresses are used to submit false positive messages to Microsoft.</span></span>

   - <span data-ttu-id="0ac8b-125">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-125">Click **OK**.</span></span>

6. <span data-ttu-id="0ac8b-126">En **hacer lo siguiente**, seleccione **CCO el mensaje a...** y, a continuación, seleccione los buzones donde quiera recibir los mensajes.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-126">Under **Do the following**, select **Bcc the message to...** and then and then select the mailboxes where you'd like to receive the messages.</span></span>

7. <span data-ttu-id="0ac8b-127">Si lo desea, puede realizar selecciones para auditar la regla, probarla, activarla durante un período de tiempo específico y otras selecciones.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-127">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="0ac8b-128">Recomendamos probar la regla durante un tiempo antes de aplicarla.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-128">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="0ac8b-129">Consulte [procedimientos para reglas de flujo de correo](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span><span class="sxs-lookup"><span data-stu-id="0ac8b-129">See [Procedures for mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span></span>

8. <span data-ttu-id="0ac8b-130">Haga clic en el botón **Guardar** para guardar la regla.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-130">Click the **save** button to save the rule.</span></span> <span data-ttu-id="0ac8b-131">Aparecerá en la lista de reglas.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-131">It appears in your list of rules.</span></span>

<span data-ttu-id="0ac8b-132">Después de crear y aplicar la regla, todos los mensajes que se envíen desde la organización a las direcciones de correo electrónico especificadas se copiarán en el buzón especificado.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-132">After you create and enforce the rule, any messages that are sent from your organization to specified email addresses will be copied to the specified mailbox.</span></span>
