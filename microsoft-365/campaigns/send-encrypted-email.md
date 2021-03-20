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
ms.openlocfilehash: af34d632ead2ae1e6ed81845c56b95b95af1dc51
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911989"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="5b3fb-103">Cifre o etiquete su correo electrónico confidencial</span><span class="sxs-lookup"><span data-stu-id="5b3fb-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="5b3fb-104">Los datos y la información de la campaña son importantes y, a menudo, confidenciales.</span><span class="sxs-lookup"><span data-stu-id="5b3fb-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="5b3fb-105">Ayude a proteger esta información confidencial mediante el uso de etiquetas de cifrado y confidencialidad para que usted y los destinatarios de correo electrónico traten la información con la confidencialidad que requiere.</span><span class="sxs-lookup"><span data-stu-id="5b3fb-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>

## <a name="best-practices"></a><span data-ttu-id="5b3fb-106">Procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="5b3fb-106">Best practices</span></span>

<span data-ttu-id="5b3fb-107">Antes de enviar correo electrónico con información confidencial o confidencial, considere la posibilidad de activar:</span><span class="sxs-lookup"><span data-stu-id="5b3fb-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="5b3fb-108">**Cifrado:** Puede cifrar el correo electrónico para proteger la privacidad de la información del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5b3fb-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="5b3fb-109">Al cifrar un mensaje de correo electrónico, se convierte de texto sin formato legible en texto de chipher codificado.</span><span class="sxs-lookup"><span data-stu-id="5b3fb-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="5b3fb-110">Solo el destinatario que tiene la clave privada que coincide con la clave pública usada para cifrar el mensaje puede descifrar el mensaje para su lectura.</span><span class="sxs-lookup"><span data-stu-id="5b3fb-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="5b3fb-111">Sin embargo, cualquier destinatario sin la clave privada correspondiente ve texto indescifrable.</span><span class="sxs-lookup"><span data-stu-id="5b3fb-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="5b3fb-112">El administrador puede definir reglas para cifrar automáticamente los mensajes que cumplan determinados criterios.</span><span class="sxs-lookup"><span data-stu-id="5b3fb-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="5b3fb-113">Por ejemplo, el administrador puede crear una regla que cifre todos los mensajes enviados fuera de la organización o todos los mensajes que mencionen palabras o frases específicas.</span><span class="sxs-lookup"><span data-stu-id="5b3fb-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="5b3fb-114">Las reglas de cifrado se aplicarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="5b3fb-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="5b3fb-115">**Etiquetas de confidencialidad:** Tu campaña también puede configurar etiquetas de confidencialidad que puedes aplicar a tus archivos y correo electrónico para que cumplan con las directivas de protección de la información de la campaña.</span><span class="sxs-lookup"><span data-stu-id="5b3fb-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="5b3fb-116">Al establecer una etiqueta, la etiqueta persiste con el correo electrónico, incluso cuando se envía; por ejemplo, aparece como un encabezado en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="5b3fb-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![Diagrama de un correo electrónico con llamadas para etiquetas y cifrado](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a><span data-ttu-id="5b3fb-118">Configúrelo</span><span class="sxs-lookup"><span data-stu-id="5b3fb-118">Set it up</span></span>

<span data-ttu-id="5b3fb-119">Si desea cifrar un mensaje que no cumple con una regla predefinida o el administrador no ha configurado ninguna regla, puede aplicar una variedad de reglas de cifrado diferentes antes de enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="5b3fb-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="5b3fb-120">Para enviar un mensaje cifrado desde Outlook 2013 o 2016, o Outlook 2016 para Mac, seleccione Opciones **> permisos** y, a continuación, seleccione la opción de protección que necesita.</span><span class="sxs-lookup"><span data-stu-id="5b3fb-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="5b3fb-121">También puede enviar un mensaje cifrado seleccionando el botón **Proteger** en Outlook en la web.</span><span class="sxs-lookup"><span data-stu-id="5b3fb-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="5b3fb-122">Para obtener más información, vea [Enviar, ver y responder a](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)mensajes cifrados en Outlook para PC .</span><span class="sxs-lookup"><span data-stu-id="5b3fb-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="5b3fb-123">Configuración de administrador</span><span class="sxs-lookup"><span data-stu-id="5b3fb-123">Admin settings</span></span>

<span data-ttu-id="5b3fb-124">Puede obtener información sobre cómo configurar el cifrado de correo electrónico en [Cifrado de correo electrónico en Microsoft 365](../compliance/email-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="5b3fb-124">You can learn all about setting up email encryption at [Email encryption in Microsoft 365](../compliance/email-encryption.md).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="5b3fb-125">Cifrar automáticamente mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="5b3fb-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="5b3fb-126">Los administradores pueden crear reglas de flujo de correo para proteger automáticamente los mensajes de correo electrónico que se envían y reciben de la campaña.</span><span class="sxs-lookup"><span data-stu-id="5b3fb-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="5b3fb-127">Configure reglas para cifrar los mensajes de correo electrónico salientes y quite el cifrado de los mensajes cifrados procedentes de dentro de la organización o de las respuestas a los mensajes cifrados enviados desde su organización.</span><span class="sxs-lookup"><span data-stu-id="5b3fb-127">Set up rules to encrypt any outgoing email messages, and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span>

<span data-ttu-id="5b3fb-128">Cree reglas de flujo de correo para cifrar los mensajes de correo electrónico con las nuevas funcionalidades de cifrado de mensajes (OME) de Office 365.</span><span class="sxs-lookup"><span data-stu-id="5b3fb-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="5b3fb-129">Definir reglas de flujo de correo para desencadenar el cifrado de mensajes con las nuevas funcionalidades de OME mediante el Centro de administración de Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="5b3fb-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="5b3fb-130">En un explorador web, con una cuenta de trabajo o escuela a la que se han concedido permisos de administrador global, inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="5b3fb-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in.</span></span>
2. <span data-ttu-id="5b3fb-131">Elija el icono Administrador.</span><span class="sxs-lookup"><span data-stu-id="5b3fb-131">Choose the Admin tile.</span></span>
3. <span data-ttu-id="5b3fb-132">En el Centro de administración, elija **Centros de administración > Exchange**.</span><span class="sxs-lookup"><span data-stu-id="5b3fb-132">In the admin center, choose **Admin centers > Exchange**.</span></span>

<span data-ttu-id="5b3fb-133">Para obtener más información, vea [Definir reglas de flujo de correo para cifrar mensajes de correo electrónico.](../compliance/define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="5b3fb-133">For more information, see [Define mail flow rules to encrypt email messages](../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="5b3fb-134">Marca los mensajes de cifrado</span><span class="sxs-lookup"><span data-stu-id="5b3fb-134">Brand your encryption messages</span></span>

<span data-ttu-id="5b3fb-135">También puedes aplicar la personalización de marca de la campaña para personalizar la apariencia y el texto de los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5b3fb-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="5b3fb-136">Para obtener más información, vea [Add your organization's brand to your encrypted messages](../compliance/email-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="5b3fb-136">For more information, see [Add your organization's brand to your encrypted messages](../compliance/email-encryption.md).</span></span>