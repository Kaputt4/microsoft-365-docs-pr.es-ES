---
title: Directiva 2 de servicios de pago y alta autenticación de clientes para clientes comerciales
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: A partir del 14 de septiembre de 2019, los bancos de los 31 países del espacio económico europeo están obligados a verificar la identidad de la persona que realiza una compra en línea antes de que se pueda procesar el pago.
keywords: Directiva 2 de servicios de pago, autenticación de varios factores en el cliente segura
ms.openlocfilehash: fc8784949cdacea10957660c99795b4ade0f9f7a
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638428"
---
# <a name="payment-services-directive-2-and-strong-customer-authentication-for-commercial-customers"></a><span data-ttu-id="695d4-104">Directiva 2 de servicios de pago y alta autenticación de clientes para clientes comerciales</span><span class="sxs-lookup"><span data-stu-id="695d4-104">Payment Services Directive 2 and Strong Customer Authentication for commercial customers</span></span>

<span data-ttu-id="695d4-105">A partir del 14 de septiembre de 2019, los bancos de los 31 países del espacio económico europeo están obligados a verificar la identidad de la persona que realiza una compra en línea antes de que se pueda procesar el pago.</span><span class="sxs-lookup"><span data-stu-id="695d4-105">Starting on September 14, 2019, banks in the 31 countries of the European Economic Area are required to verify the identity of the person making an online purchase before the payment can be processed.</span></span> <span data-ttu-id="695d4-106">Esta comprobación requiere la autenticación multifactor para ayudar a garantizar que las compras en línea estén seguras y protegidas.</span><span class="sxs-lookup"><span data-stu-id="695d4-106">This verification requires multi-factor authentication to help ensure your online purchases are secure and protected.</span></span> <span data-ttu-id="695d4-107">La fecha de este requisito de comprobación se retrasará para algunos países.</span><span class="sxs-lookup"><span data-stu-id="695d4-107">The date for this verification requirement will be delayed for some countries.</span></span> 

<span data-ttu-id="695d4-108">Para obtener más información, vea [preguntas más frecuentes de Microsoft sobre la Directiva 2 de servicios de pago y la autenticación segura de clientes](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span><span class="sxs-lookup"><span data-stu-id="695d4-108">For more information, see [Microsoft FAQ about Payment Services Directive 2 and Strong Customer Authentication](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span></span>

## <a name="when-is-multi-factor-authentication-required"></a><span data-ttu-id="695d4-109">¿Cuándo se requiere multi-factor Authentication?</span><span class="sxs-lookup"><span data-stu-id="695d4-109">When is multi-factor authentication required?</span></span>

<span data-ttu-id="695d4-110">Actualmente, los requisitos de verificación para esta Directiva mediante la autenticación multifactor solo se aplican a los clientes mediante tarjetas de crédito de bancos de los 31 países del espacio económico europeo.</span><span class="sxs-lookup"><span data-stu-id="695d4-110">Currently, verification requirements for this directive using multi-factor authentication only apply to customers using credit cards from banks in the 31 countries of the European Economic Area.</span></span> <span data-ttu-id="695d4-111">A veces, se les pedirá a los clientes por una acción que hayan realizado y, en ocasiones, se les pedirá que realicen los eventos con sus suscripciones o servicios existentes.</span><span class="sxs-lookup"><span data-stu-id="695d4-111">Sometimes customers will be prompted because of an action that they took, and sometimes they are prompted because of events with their existing subscriptions or services.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="695d4-112">Acciones del cliente</span><span class="sxs-lookup"><span data-stu-id="695d4-112">Customer Actions</span></span>

<span data-ttu-id="695d4-113">Es posible que el Banco necesite la comprobación mediante la autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="695d4-113">Your bank may require verification through multi-factor authentication.</span></span> <span data-ttu-id="695d4-114">Algunos ejemplos son:</span><span class="sxs-lookup"><span data-stu-id="695d4-114">Some examples include:</span></span>
- <span data-ttu-id="695d4-115">Registrarse para obtener una suscripción nueva</span><span class="sxs-lookup"><span data-stu-id="695d4-115">Signing up for a new subscription</span></span>
- <span data-ttu-id="695d4-116">Agregar licencias a una suscripción</span><span class="sxs-lookup"><span data-stu-id="695d4-116">Adding licenses to a subscription</span></span>
- <span data-ttu-id="695d4-117">Adición o sustitución de la tarjeta de crédito que se usa para pagar por una suscripción o un servicio</span><span class="sxs-lookup"><span data-stu-id="695d4-117">Adding or replacing the credit card used to pay for a subscription or service</span></span>
- <span data-ttu-id="695d4-118">Adición o reemplazo de una tarjeta de crédito en un perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="695d4-118">Adding or replacing a credit card on a billing profile</span></span>
- <span data-ttu-id="695d4-119">Comprar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="695d4-119">Buying apps</span></span>

### <a name="subscription-lifecycle-events"></a><span data-ttu-id="695d4-120">Eventos de ciclo de vida de suscripción</span><span class="sxs-lookup"><span data-stu-id="695d4-120">Subscription lifecycle events</span></span>

<span data-ttu-id="695d4-121">Los cargos por pagos recurrentes podrían producir un error.</span><span class="sxs-lookup"><span data-stu-id="695d4-121">Charges for recurring payments might fail.</span></span> <span data-ttu-id="695d4-122">Si es así, recibirá un correo electrónico con instrucciones para seguir.</span><span class="sxs-lookup"><span data-stu-id="695d4-122">If they do, you’ll receive an email with instructions to follow.</span></span> <span data-ttu-id="695d4-123">Se le pedirá que responda a la solicitud de verificación y que realice el pago actual.</span><span class="sxs-lookup"><span data-stu-id="695d4-123">You’ll be prompted to respond to the verification request and make your current payment.</span></span>

## <a name="need-more-help"></a><span data-ttu-id="695d4-124">¿Necesita más ayuda?</span><span class="sxs-lookup"><span data-stu-id="695d4-124">Need more help?</span></span>

<span data-ttu-id="695d4-125">La entidad financiera es el mejor contacto para estos escenarios:</span><span class="sxs-lookup"><span data-stu-id="695d4-125">Your financial institution is the best contact for these scenarios:</span></span>
- <span data-ttu-id="695d4-126">No ha recibido un código de verificación.</span><span class="sxs-lookup"><span data-stu-id="695d4-126">You didn't receive a verification code.</span></span>  
- <span data-ttu-id="695d4-127">El proceso de comprobación no funcionaba después de enviar el código de comprobación.</span><span class="sxs-lookup"><span data-stu-id="695d4-127">The verification process didn't work after you submitted the verification code.</span></span>
- <span data-ttu-id="695d4-128">No estás seguro si la información de contacto de tu tarjeta de crédito es correcta.</span><span class="sxs-lookup"><span data-stu-id="695d4-128">You're not sure if the contact info for your credit card is correct.</span></span>
