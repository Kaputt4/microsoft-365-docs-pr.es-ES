---
title: Conectar su dominio a Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Aprenda a verificar su dominio y a crear registros DNS con Microsoft 365.
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: 206b435130e8e77ed1540432e3bbeff7f16463bf
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658220"
---
# <a name="connect-your-domain-to-microsoft-365"></a><span data-ttu-id="2f354-103">Conectar su dominio a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2f354-103">Connect your domain to Microsoft 365</span></span>

> [!NOTE]
> <span data-ttu-id="2f354-104">Si no agrega el dominio, los integrantes de la organización usarán el dominio onmicrosoft.com para las direcciones de correo electrónico hasta que lo agregue.</span><span class="sxs-lookup"><span data-stu-id="2f354-104">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="2f354-105">Es importante que agregue el dominio antes de agregar usuarios, para evitar tener que configurarlo dos veces.</span><span class="sxs-lookup"><span data-stu-id="2f354-105">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="2f354-106">[Consulte las preguntas frecuentes sobre los dominios](../setup/domains-faq.yml) si no encuentra lo que busca debajo.</span><span class="sxs-lookup"><span data-stu-id="2f354-106">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for below.</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="2f354-107">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="2f354-107">Add an MX record so email for your domain will come to Microsoft</span></span>

<span data-ttu-id="2f354-108">Obtendrá la información del registro MX del asistente de configuración del dominio del centro de administración.</span><span class="sxs-lookup"><span data-stu-id="2f354-108">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="2f354-109">En el sitio web del proveedor de host, agregue un nuevo registro MX.</span><span class="sxs-lookup"><span data-stu-id="2f354-109">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="2f354-110">Asegúrese de configurar los campos con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="2f354-110">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="2f354-111">Tipo de registro: `MX`</span><span class="sxs-lookup"><span data-stu-id="2f354-111">Record Type: `MX`</span></span>
- <span data-ttu-id="2f354-112">Prioridad: defina la prioridad con el valor más alto posible, que suele ser `0`.</span><span class="sxs-lookup"><span data-stu-id="2f354-112">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="2f354-113">Nombre de host: `@`</span><span class="sxs-lookup"><span data-stu-id="2f354-113">Host Name: `@`</span></span>
- <span data-ttu-id="2f354-114">Dirección de destino: copie el valor del centro de administración y péguelo aquí.</span><span class="sxs-lookup"><span data-stu-id="2f354-114">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="2f354-115">TTL: `3600‎` (o el proveedor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="2f354-115">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="2f354-116">Guarde el registro y, a continuación, quite cualquier otro registro MX.</span><span class="sxs-lookup"><span data-stu-id="2f354-116">Save the record, and then remove any other MX records.</span></span>

## <a name="add-a-cname-record-to-connect-users-to-their-mailboxes"></a><span data-ttu-id="2f354-117">Agregar un registro CNAME para conectar a los usuarios con sus buzones</span><span class="sxs-lookup"><span data-stu-id="2f354-117">Add a CNAME record to connect users to their mailboxes</span></span>
<span data-ttu-id="2f354-118">Obtendrá la información de los registros CNAME del asistente de configuración del dominio del centro de administración.</span><span class="sxs-lookup"><span data-stu-id="2f354-118">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="2f354-119">En el sitio web de su proveedor de hospedaje, agregue el siguiente registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="2f354-119">On your hosting provider's website, add the following CNAME record.</span></span> <span data-ttu-id="2f354-120">Asegúrese de configurar los campos con los siguientes valores para cada uno:</span><span class="sxs-lookup"><span data-stu-id="2f354-120">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="2f354-121">Tipo de registro: `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="2f354-121">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="2f354-122">Host: pegue aquí los valores que copie del centro de administración.</span><span class="sxs-lookup"><span data-stu-id="2f354-122">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="2f354-123">Dirección de destino: copie el valor del centro de administración y péguelo aquí.</span><span class="sxs-lookup"><span data-stu-id="2f354-123">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="2f354-124">TTL: `3600‎` (o el proveedor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="2f354-124">TTL: `3600‎` (or your provider default)</span></span>

## <a name="add-a-txt-record-to-help-prevent-spam"></a><span data-ttu-id="2f354-125">Agregar un registro TXT para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="2f354-125">Add a TXT record to help prevent spam</span></span>
<span data-ttu-id="2f354-126">**Antes de empezar:** si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2f354-126">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="2f354-127">En vez de eso, agregue los valores necesarios de Microsoft 365 para el registro actual en el sitio web de su proveedor de host, de modo que solo tenga un *único* registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="2f354-127">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="2f354-128">En el sitio web de su proveedor de host, edite el registro SPF existente o cree un nuevo registro SPF.</span><span class="sxs-lookup"><span data-stu-id="2f354-128">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="2f354-129">Asegúrese de configurar los campos con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="2f354-129">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="2f354-130">Tipo de registro: `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="2f354-130">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="2f354-131">Host: `@`</span><span class="sxs-lookup"><span data-stu-id="2f354-131">Host: `@`</span></span>
- <span data-ttu-id="2f354-132">Valor TXT: `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="2f354-132">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="2f354-133">TTL: `3600‎` (o el proveedor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="2f354-133">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="2f354-134">Guarde el registro.</span><span class="sxs-lookup"><span data-stu-id="2f354-134">Save the record.</span></span>

<span data-ttu-id="2f354-135">Para validar el registro de SPF, use una de estas[herramientas de validación de SPF](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain).</span><span class="sxs-lookup"><span data-stu-id="2f354-135">Validate your SPF record by using one of these [SPF validation tools](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="2f354-136">SPF está diseñado para ayudar a evitar la suplantación de identidad, pero hay técnicas de suplantación de identidad contra las que SPF no puede proteger.</span><span class="sxs-lookup"><span data-stu-id="2f354-136">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="2f354-137">Para protegerse de estos, una vez que haya configurado el SPF, también debe configurar DKIM y DMARC para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2f354-137">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span>

<span data-ttu-id="2f354-138">Para comenzar, consulte [Usar DKIM para validar el correo electrónico saliente enviado desde su dominio en Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) y[Usar DMARC para validar el correo electrónico en Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="2f354-138">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) and [Use DMARC to validate email in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="2f354-139">Por último, vuelva al asistente de configuración del dominio del centro de administración para completar la configuración.</span><span class="sxs-lookup"><span data-stu-id="2f354-139">Finally, head back to the admin center domain setup wizard to complete your setup.</span></span>
