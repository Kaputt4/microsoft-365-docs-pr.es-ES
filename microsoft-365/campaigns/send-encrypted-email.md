---
title: Enviar correo electrónico cifrado
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Obtenga información sobre cómo enviar correo electrónico cifrado con Outlook.
ms.openlocfilehash: d17abccd645b4dfdf933906dc90175be51f95c9a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044221"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="2f256-103">Cifre o etiquete su correo electrónico confidencial</span><span class="sxs-lookup"><span data-stu-id="2f256-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="2f256-104">Los datos y la información de la campaña son importantes y suelen ser confidenciales.</span><span class="sxs-lookup"><span data-stu-id="2f256-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="2f256-105">Ayude a proteger esta información confidencial mediante el cifrado y las etiquetas de confidencialidad para que usted y los destinatarios de correo electrónico traten la información con la confidencialidad que requiere.</span><span class="sxs-lookup"><span data-stu-id="2f256-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>

## <a name="best-practices"></a><span data-ttu-id="2f256-106">Procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="2f256-106">Best practices</span></span>

<span data-ttu-id="2f256-107">Antes de enviar correo electrónico con información confidencial, considere la posibilidad de activar:</span><span class="sxs-lookup"><span data-stu-id="2f256-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="2f256-108">**Cifrado:** Puede cifrar el correo electrónico para proteger la privacidad de la información del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2f256-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="2f256-109">Cuando se cifra un mensaje de correo electrónico, se convierte de texto sin formato legible en texto desenlazado.</span><span class="sxs-lookup"><span data-stu-id="2f256-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="2f256-110">Solo el destinatario que tiene la clave privada que coincide con la clave pública usada para cifrar el mensaje puede descifrarlo para leerlo.</span><span class="sxs-lookup"><span data-stu-id="2f256-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="2f256-111">Sin embargo, cualquier destinatario sin la clave privada correspondiente ve texto indescifrable.</span><span class="sxs-lookup"><span data-stu-id="2f256-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="2f256-112">El administrador puede definir reglas para cifrar automáticamente los mensajes que cumplen ciertos criterios.</span><span class="sxs-lookup"><span data-stu-id="2f256-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="2f256-113">Por ejemplo, el administrador puede crear una regla que cifre todos los mensajes enviados fuera de su organización o todos los mensajes que mencionen palabras o frases específicas.</span><span class="sxs-lookup"><span data-stu-id="2f256-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="2f256-114">Las reglas de cifrado se aplicarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2f256-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="2f256-115">**Etiquetas de confidencialidad:** Tu campaña también puede configurar etiquetas de confidencialidad que puedes aplicar a tus archivos y correo electrónico para que cumplan con las directivas de protección de la información de tu campaña.</span><span class="sxs-lookup"><span data-stu-id="2f256-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="2f256-116">Cuando se establece una etiqueta, la etiqueta persiste con el correo electrónico, incluso cuando se envía, por ejemplo, al aparecer como un encabezado en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="2f256-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![Diagrama de un correo electrónico con llamadas para etiquetas y cifrado](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a><span data-ttu-id="2f256-118">Configúrelo</span><span class="sxs-lookup"><span data-stu-id="2f256-118">Set it up</span></span>

<span data-ttu-id="2f256-119">Si desea cifrar un mensaje que no cumple una regla predefinida o su administrador no ha configurado ninguna regla, puede aplicar una variedad de reglas de cifrado diferentes antes de enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="2f256-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="2f256-120">Para enviar un mensaje cifrado desde Outlook 2013 o 2016, o Outlook 2016 para Mac, seleccione Opciones **> Permisos** y, a continuación, seleccione la opción de protección que necesita.</span><span class="sxs-lookup"><span data-stu-id="2f256-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="2f256-121">También puede enviar un mensaje cifrado seleccionando el botón **Proteger** en Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="2f256-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="2f256-122">Para obtener más información, vea Enviar, ver y responder a mensajes [cifrados en Outlook para PC.](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)</span><span class="sxs-lookup"><span data-stu-id="2f256-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="2f256-123">Configuración de administrador</span><span class="sxs-lookup"><span data-stu-id="2f256-123">Admin settings</span></span>

<span data-ttu-id="2f256-124">Puede obtener información sobre cómo configurar el cifrado de correo electrónico en el cifrado [de correo electrónico en Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)</span><span class="sxs-lookup"><span data-stu-id="2f256-124">You can learn all about setting up email encryption at [Email encryption in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="2f256-125">Cifrar automáticamente los mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="2f256-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="2f256-126">Los administradores pueden crear reglas de flujo de correo para proteger automáticamente los mensajes de correo electrónico que se envían y reciben de la campaña.</span><span class="sxs-lookup"><span data-stu-id="2f256-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="2f256-127">Configure reglas para cifrar los mensajes de correo electrónico saliente y quitar el cifrado de los mensajes cifrados procedentes de su organización o de las respuestas a los mensajes cifrados enviados desde su organización.</span><span class="sxs-lookup"><span data-stu-id="2f256-127">Set up rules to encrypt any outgoing email messages, and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span>

<span data-ttu-id="2f256-128">Cree reglas de flujo de correo para cifrar mensajes de correo electrónico con las nuevas capacidades de Cifrado de mensajes de Office 365 (OME).</span><span class="sxs-lookup"><span data-stu-id="2f256-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="2f256-129">Definir reglas de flujo de correo para desencadenar el cifrado de mensajes con las nuevas funcionalidades de OME mediante el Centro de administración de Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="2f256-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="2f256-130">En un explorador web, con una cuenta de trabajo o escuela a la que se hayan concedido permisos de administrador global, inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="2f256-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in.</span></span>
2. <span data-ttu-id="2f256-131">Elija el icono Administrador.</span><span class="sxs-lookup"><span data-stu-id="2f256-131">Choose the Admin tile.</span></span>
3. <span data-ttu-id="2f256-132">En el centro de administración, elija **Centros de administración > Exchange**.</span><span class="sxs-lookup"><span data-stu-id="2f256-132">In the admin center, choose **Admin centers > Exchange**.</span></span>

<span data-ttu-id="2f256-133">Para obtener más información, vea [Definir reglas de flujo de correo para cifrar mensajes de correo electrónico.](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)</span><span class="sxs-lookup"><span data-stu-id="2f256-133">For more information, see [Define mail flow rules to encrypt email messages](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="2f256-134">Personal de marca de los mensajes de cifrado</span><span class="sxs-lookup"><span data-stu-id="2f256-134">Brand your encryption messages</span></span>

<span data-ttu-id="2f256-135">También puede aplicar la personalización de marca de la campaña para personalizar la apariencia y el texto de los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2f256-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="2f256-136">Para obtener más información, [vea Agregar la marca de su organización a los mensajes cifrados.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)</span><span class="sxs-lookup"><span data-stu-id="2f256-136">For more information, see [Add your organization's brand to your encrypted messages](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>
