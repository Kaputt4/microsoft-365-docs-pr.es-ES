---
title: Directiva 2 de servicios de pago y autenticación segura de clientes para clientes comerciales
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jamitche
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
- PPM_jmueller
search.appverid: MET150
description: A partir del 14 de septiembre de 2019, los bancos de los 31 países del Espacio Económico Europeo deben comprobar la identidad de la persona que realiza una compra en línea antes de poder procesar el pago".
keywords: directiva 2 de servicios de pago, autenticación segura de clientes, autenticación multifactor
ms.date: 11/03/2020
ms.openlocfilehash: e687cac5bb1b7f1c88e9166993e29d437134e138
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52280852"
---
# <a name="payment-services-directive-2-and-strong-customer-authentication-for-commercial-customers"></a><span data-ttu-id="b9f5e-104">Directiva 2 de servicios de pago y autenticación segura de clientes para clientes comerciales</span><span class="sxs-lookup"><span data-stu-id="b9f5e-104">Payment Services Directive 2 and Strong Customer Authentication for commercial customers</span></span>

<span data-ttu-id="b9f5e-105">A partir del 14 de septiembre de 2019, los bancos de los 31 países del Espacio Económico Europeo deben comprobar la identidad de la persona que realiza una compra en línea antes de poder procesar el pago.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-105">As of September 14, 2019, banks in the 31 countries of the European Economic Area are required to verify the identity of the person making an online purchase before the payment can be processed.</span></span> <span data-ttu-id="b9f5e-106">Esta comprobación requiere autenticación multifactor para garantizar que sus compras en línea estén seguras y protegidas.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-106">This verification requires multi-factor authentication to help ensure your online purchases are secure and protected.</span></span> <span data-ttu-id="b9f5e-107">La fecha de este requisito de verificación se retrasará para algunos países.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-107">The date for this verification requirement will be delayed for some countries.</span></span>

<span data-ttu-id="b9f5e-108">Para obtener más información, vea Preguntas más frecuentes de [Microsoft sobre la Directiva 2](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication)de servicios de pago y Autenticación segura del cliente .</span><span class="sxs-lookup"><span data-stu-id="b9f5e-108">For more information, see [Microsoft FAQ about Payment Services Directive 2 and Strong Customer Authentication](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span></span>

## <a name="when-is-multi-factor-authentication-required"></a><span data-ttu-id="b9f5e-109">¿Cuándo se requiere la autenticación multifactor?</span><span class="sxs-lookup"><span data-stu-id="b9f5e-109">When is multi-factor authentication required?</span></span>

<span data-ttu-id="b9f5e-110">Actualmente, los requisitos de verificación para esta directiva que usan la autenticación multifactor solo se aplican a los clientes que usan tarjetas de crédito de bancos de los 31 países del Espacio Económico Europeo.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-110">Currently, verification requirements for this directive using multi-factor authentication only apply to customers using credit cards from banks in the 31 countries of the European Economic Area.</span></span> <span data-ttu-id="b9f5e-111">A veces se pedirá a los clientes debido a una acción que realizaron y, a veces, se les pedirá que se den debido a eventos con sus suscripciones o servicios existentes.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-111">Sometimes customers will be prompted because of an action that they took, and sometimes they are prompted because of events with their existing subscriptions or services.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="b9f5e-112">Acciones del cliente</span><span class="sxs-lookup"><span data-stu-id="b9f5e-112">Customer Actions</span></span>

<span data-ttu-id="b9f5e-113">El banco puede requerir la verificación mediante la autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-113">Your bank may require verification through multi-factor authentication.</span></span> <span data-ttu-id="b9f5e-114">Algunos ejemplos son:</span><span class="sxs-lookup"><span data-stu-id="b9f5e-114">Some examples include:</span></span>

- <span data-ttu-id="b9f5e-115">Registrarse para una nueva suscripción</span><span class="sxs-lookup"><span data-stu-id="b9f5e-115">Signing up for a new subscription</span></span>
- <span data-ttu-id="b9f5e-116">Agregar licencias a una suscripción</span><span class="sxs-lookup"><span data-stu-id="b9f5e-116">Adding licenses to a subscription</span></span>
- <span data-ttu-id="b9f5e-117">Agregar o reemplazar la tarjeta de crédito usada para pagar una suscripción o servicio</span><span class="sxs-lookup"><span data-stu-id="b9f5e-117">Adding or replacing the credit card used to pay for a subscription or service</span></span>
- <span data-ttu-id="b9f5e-118">Agregar o reemplazar una tarjeta de crédito en un perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="b9f5e-118">Adding or replacing a credit card on a billing profile</span></span>
- <span data-ttu-id="b9f5e-119">Comprar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="b9f5e-119">Buying apps</span></span>

### <a name="subscription-lifecycle-events"></a><span data-ttu-id="b9f5e-120">Eventos de ciclo de vida de suscripción</span><span class="sxs-lookup"><span data-stu-id="b9f5e-120">Subscription lifecycle events</span></span>

<span data-ttu-id="b9f5e-121">Pueden producirse errores en los cargos por pagos periódicos.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-121">Charges for recurring payments might fail.</span></span> <span data-ttu-id="b9f5e-122">Si lo hacen, recibirás un correo electrónico con las instrucciones que debes seguir.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-122">If they do, you’ll receive an email with instructions to follow.</span></span> <span data-ttu-id="b9f5e-123">Se te pedirá que respondas a la solicitud de verificación y realices el pago actual.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-123">You’ll be prompted to respond to the verification request and make your current payment.</span></span>

## <a name="need-more-help"></a><span data-ttu-id="b9f5e-124">¿Necesita más ayuda?</span><span class="sxs-lookup"><span data-stu-id="b9f5e-124">Need more help?</span></span>

<span data-ttu-id="b9f5e-125">La entidad financiera es el mejor contacto para estos escenarios:</span><span class="sxs-lookup"><span data-stu-id="b9f5e-125">Your financial institution is the best contact for these scenarios:</span></span>

- <span data-ttu-id="b9f5e-126">No recibió un código de verificación.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-126">You didn't receive a verification code.</span></span>  
- <span data-ttu-id="b9f5e-127">El proceso de comprobación no funcionaba después de enviar el código de verificación.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-127">The verification process didn't work after you submitted the verification code.</span></span>
- <span data-ttu-id="b9f5e-128">No estás seguro de si la información de contacto de tu tarjeta de crédito es correcta.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-128">You're not sure if the contact info for your credit card is correct.</span></span>
