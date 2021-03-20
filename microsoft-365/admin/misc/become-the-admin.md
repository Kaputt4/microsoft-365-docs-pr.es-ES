---
title: Realizar una toma de administración interna
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Obtenga información sobre cómo comprobar la propiedad del dominio y el correo electrónico para asumir un inquilino no administrado en Microsoft 365
ms.openlocfilehash: 72278fd0e373848a79f9823e186b19bc1cb47770
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914851"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="16790-103">Realizar una toma de administración interna</span><span class="sxs-lookup"><span data-stu-id="16790-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="16790-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="16790-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="16790-105">Si es un administrador y desea asumir un inquilino no administrado creado por un registro de usuario de autoservicio, puede hacerlo con una toma de posesión de un administrador interno.</span><span class="sxs-lookup"><span data-stu-id="16790-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="16790-106">Un registro de autoservicio para cualquier servicio en la nube que use Azure AD agregará al usuario a un directorio de Azure AD no administrado o "de sombra" y creará un inquilino no administrado.</span><span class="sxs-lookup"><span data-stu-id="16790-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="16790-107">Un inquilino no administrado es un directorio sin un administrador global.</span><span class="sxs-lookup"><span data-stu-id="16790-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="16790-108">Para determinar si un inquilino está administrado o no administrado, consulte [Determining Tenant Type](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span><span class="sxs-lookup"><span data-stu-id="16790-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="16790-109">Paso 1: Comprobar la dirección de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="16790-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="16790-110">Si el autoservicio está habilitado en el inquilino, los usuarios pueden suscribirse a servicios gratuitos, como Power BI, por su cuenta.</span><span class="sxs-lookup"><span data-stu-id="16790-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="16790-111">Estos pasos suponen que una suscripción de usuario de autoservicio ha creado el inquilino no administrado que desea asumir como administrador. En el primer paso se crea un contexto de usuario en el inquilino no administrado, con Power BI para ilustrar la ruta de acceso de adquisición de administrador.</span><span class="sxs-lookup"><span data-stu-id="16790-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="16790-112">Para registrarse en Power BI, vaya al sitio de [Power BI](https://powerbi.com) y seleccione **Iniciar** prueba gratuita de inicio gratuito (en Cuadro Compartir con Power  >   BI Pro).</span><span class="sxs-lookup"><span data-stu-id="16790-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="16790-113">Registrarse con una cuenta de usuario que use el nombre de dominio de su organización (como `powerbiadmin@contoso.com` ).</span><span class="sxs-lookup"><span data-stu-id="16790-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="16790-114">Si tu cuenta ya está en uso, inicia sesión con la contraseña actual.</span><span class="sxs-lookup"><span data-stu-id="16790-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="16790-115">Compruebe el código de verificación **del** correo electrónico y escriba el código para validar la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="16790-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="16790-116">Paso 2: Crear una nueva cuenta</span><span class="sxs-lookup"><span data-stu-id="16790-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="16790-117">Cuando escriba el código de verificación, se le mostrará a una página donde puede crear una nueva cuenta.</span><span class="sxs-lookup"><span data-stu-id="16790-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="16790-118">Rellene los campos de nombre de usuario y contraseña con la cuenta que desea usar y, a continuación, **seleccione Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="16790-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="16790-119">Paso 3: Comprobar la propiedad del dominio y convertirse en administrador</span><span class="sxs-lookup"><span data-stu-id="16790-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="16790-120">Se **abrirá el Asistente para** convertirse en administrador.</span><span class="sxs-lookup"><span data-stu-id="16790-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="16790-121">Si el asistente no se inicia, busque el icono **Administrador** y selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="16790-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="16790-122">Seleccione **Sí, quiero ser el administrador**.</span><span class="sxs-lookup"><span data-stu-id="16790-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="16790-123">Compruebe que es el propietario del dominio que desea asumir agregando un registro TXT al registrador de dominios.</span><span class="sxs-lookup"><span data-stu-id="16790-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="16790-124">El asistente le proporcionará el registro TXT que desea agregar, así como un vínculo al sitio web del registrador y un vínculo a instrucciones paso a paso.</span><span class="sxs-lookup"><span data-stu-id="16790-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="16790-125">Una vez que haya agregado el registro TXT al sitio de registrador, vuelva al asistente y seleccione **Correcto,** he agregado el registro .</span><span class="sxs-lookup"><span data-stu-id="16790-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="16790-126">La toma del espacio empresarial de instantáneas no afectará a ninguna información o servicios existentes.</span><span class="sxs-lookup"><span data-stu-id="16790-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="16790-127">Sin embargo, si algún usuario del dominio se ha registrado en los servicios que requieren una licencia, se le pedirá que compre licencias para ellos como parte de la toma del rol de administrador.</span><span class="sxs-lookup"><span data-stu-id="16790-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="16790-128">Puede comprar o quitar licencias una vez finalizado el proceso de configuración de administración.</span><span class="sxs-lookup"><span data-stu-id="16790-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="16790-129">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="16790-129">Related articles</span></span>

<span data-ttu-id="16790-130">YouTube: 3 pasos para realizar una toma de administración de [TI para Power BI y Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span><span class="sxs-lookup"><span data-stu-id="16790-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span></span>

[<span data-ttu-id="16790-131">Toma de posesión de administradores en Azure AD</span><span class="sxs-lookup"><span data-stu-id="16790-131">Admin takeover in Azure AD</span></span>](/azure/active-directory/users-groups-roles/domains-admin-takeover)

[<span data-ttu-id="16790-132">Uso del registro de autoservicio en su organización</span><span class="sxs-lookup"><span data-stu-id="16790-132">Using self-service sign up in your organization</span></span>](self-service-sign-up.md)
  
[<span data-ttu-id="16790-133">Descripción del rol de administrador de servicio de Power BI</span><span class="sxs-lookup"><span data-stu-id="16790-133">Understanding the Power BI service administrator role</span></span>](/power-bi/service-admin-role)