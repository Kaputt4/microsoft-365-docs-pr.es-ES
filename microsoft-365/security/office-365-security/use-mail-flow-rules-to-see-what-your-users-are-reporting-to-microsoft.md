---
title: Usar reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
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
description: Los administradores pueden aprender a usar reglas de flujo de correo (también conocidas como reglas de transporte) para recibir copias de mensajes que los usuarios notifican a Microsoft.
ms.openlocfilehash: faafd8fb750259c192807349b63eee14279179de
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208578"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="4aa9c-103">Usar reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft</span><span class="sxs-lookup"><span data-stu-id="4aa9c-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="4aa9c-104">En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, hay varias formas de informar a los usuarios de los mensajes a Microsoft para su análisis, como se describe en [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="4aa9c-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="4aa9c-105">Puede crear una regla de flujo de correo (también denominada regla de transporte) que busque mensajes que los usuarios notifican a Microsoft y puede configurar destinatarios de CCO para recibir copias de estos mensajes notificados.</span><span class="sxs-lookup"><span data-stu-id="4aa9c-105">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="4aa9c-106">Puede crear la regla de flujo de correo en el centro de administración de Exchange (EAC) y PowerShell (Exchange Online PowerShell para Microsoft 365 organizaciones con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones de correo de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="4aa9c-106">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4aa9c-107">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="4aa9c-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4aa9c-108">Debe tener asignados permisos en Exchange online o EOP para poder realizar estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="4aa9c-108">You need to be assigned permissions in Exchange Online or EOP before you can do these procedures.</span></span> <span data-ttu-id="4aa9c-109">En concreto, debe tener asignado el rol **reglas de transporte** , que se asigna a las **funciones administración**de la organización, **Administración del cumplimiento**y administración de **registros** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4aa9c-109">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="4aa9c-110">Para obtener más información, consulte[Administrar grupos de roles en Exchange en línea](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="4aa9c-110">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="4aa9c-111">Para abrir el EAC, vea [centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) o [en el centro de administración de Exchange en EOP independiente](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="4aa9c-111">To open the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) or [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="4aa9c-112">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="4aa9c-112">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="4aa9c-113">Para conectarse a Exchange Online Protection PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="4aa9c-113">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="4aa9c-114">Para obtener más información acerca de las reglas de flujo de correo en Exchange Online y EOP independiente, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="4aa9c-114">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="4aa9c-115">Reglas de flujo de correo (reglas de transporte) en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4aa9c-115">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="4aa9c-116">Excepciones (predicados) y condiciones de reglas de flujo de correo en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4aa9c-116">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="4aa9c-117">Acciones de las reglas de flujo de correo en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4aa9c-117">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="4aa9c-118">Usar el EAC para crear una regla de flujo de correo para recibir copias de mensajes notificados</span><span class="sxs-lookup"><span data-stu-id="4aa9c-118">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="4aa9c-119">En el EAC, vaya a **Flujo de correo** \> **Reglas**.</span><span class="sxs-lookup"><span data-stu-id="4aa9c-119">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="4aa9c-120">Haga clic en **Agregar** ![ icono Agregar ](../../media/ITPro-EAC-AddIcon.png) y, a continuación, seleccione **crear una nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="4aa9c-120">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="4aa9c-121">En la ventana **Nueva regla** que se abre, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="4aa9c-121">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="4aa9c-122">**Name**: escriba un nombre único y descriptivo para la regla.</span><span class="sxs-lookup"><span data-stu-id="4aa9c-122">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="4aa9c-123">Por ejemplo, los mensajes CCO que se notifican a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4aa9c-123">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="4aa9c-124">Haga clic en **Más opciones**.</span><span class="sxs-lookup"><span data-stu-id="4aa9c-124">Click **More Options**.</span></span>

   - <span data-ttu-id="4aa9c-125">**Aplicar esta regla si**: seleccione **la dirección del destinatario** \> **incluye cualquiera de estas palabras**: en el cuadro de diálogo **especificar palabras o frases** que aparece, escriba uno de los siguientes valores, haga clic en **Agregar** ![ icono Agregar ](../../media/ITPro-EAC-AddIcon.png) y repita el procedimiento hasta que haya introducido todos los valores.</span><span class="sxs-lookup"><span data-stu-id="4aa9c-125">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="4aa9c-126">Para editar una entrada, selecciónela y haga clic en **Editar** ![ icono de edición ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="4aa9c-126">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="4aa9c-127">Para quitar una entrada, selecciónela y haga clic en **quitar** ![ icono quitar ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="4aa9c-127">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="4aa9c-128">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4aa9c-128">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="4aa9c-129">**Haga lo siguiente**: seleccione **agregar destinatarios** \> **en el cuadro CCO**.</span><span class="sxs-lookup"><span data-stu-id="4aa9c-129">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="4aa9c-130">En el cuadro de diálogo que aparece, busque y seleccione los destinatarios que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="4aa9c-130">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="4aa9c-131">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4aa9c-131">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="4aa9c-132">Puede realizar selecciones adicionales para auditar la regla, probarla, activar la regla durante un período de tiempo específico y otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="4aa9c-132">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="4aa9c-133">Se recomienda probar la regla antes de aplicarla.</span><span class="sxs-lookup"><span data-stu-id="4aa9c-133">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="4aa9c-134">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4aa9c-134">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="4aa9c-135">Usar PowerShell para crear una regla de flujo de correo para recibir copias de mensajes notificados</span><span class="sxs-lookup"><span data-stu-id="4aa9c-135">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="4aa9c-136">En este ejemplo se crea una nueva regla de flujo de correo denominada BCC mensajes enviados a Microsoft que busca mensajes de correo electrónico que se notifican a Microsoft mediante los métodos descritos en este tema y agrega los usuarios laura@contoso.com y julia@contoso.com como destinatarios CCO.</span><span class="sxs-lookup"><span data-stu-id="4aa9c-136">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this topic, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="4aa9c-137">Para obtener información detallada acerca de la sintaxis y los parámetros, vea [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="4aa9c-137">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="4aa9c-138">¿Cómo saber si el proceso se completó correctamente?</span><span class="sxs-lookup"><span data-stu-id="4aa9c-138">How do you know this worked?</span></span>

<span data-ttu-id="4aa9c-139">Para comprobar que ha configurado una regla de flujo de correo para recibir copias de mensajes enviados, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4aa9c-139">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="4aa9c-140">En el EAC, vaya a reglas de **flujo de correo** \> **Rules** \> Seleccione la regla \> haga clic en **Editar** ![ icono ](../../media/ITPro-EAC-EditIcon.png) de edición y Compruebe la configuración.</span><span class="sxs-lookup"><span data-stu-id="4aa9c-140">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="4aa9c-141">En PowerShell, ejecute el siguiente comando para comprobar la configuración:</span><span class="sxs-lookup"><span data-stu-id="4aa9c-141">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="4aa9c-142">Envíe mensajes de prueba a una de las direcciones de correo electrónico de informes y compruebe los resultados.</span><span class="sxs-lookup"><span data-stu-id="4aa9c-142">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
