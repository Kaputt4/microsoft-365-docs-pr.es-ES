---
title: Desuso de la aplicación visor de cifrado de mensajes
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: La aplicación Cifrado de mensajes de Office 365 Visor de Cifrado de mensajes de Office 365 (OME) se quitó de las tiendas De Android y Apple en 2018.
ms.openlocfilehash: bb96601a8a542d53f6732ab9316051c1a820ba46
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741527"
---
# <a name="deprecating-message-encryption-viewer-app"></a><span data-ttu-id="580ab-103">Desuso de la aplicación visor de cifrado de mensajes</span><span class="sxs-lookup"><span data-stu-id="580ab-103">Deprecating Message Encryption Viewer App</span></span>

<span data-ttu-id="580ab-104">El 15 de agosto de 2018, quitamos la aplicación móvil visor de Cifrado de mensajes de Office 365 (OME) de las tiendas Android y Apple.</span><span class="sxs-lookup"><span data-stu-id="580ab-104">On August 15, 2018, we removed the Office 365 Message Encryption (OME) Viewer mobile app from Android and Apple stores.</span></span> <span data-ttu-id="580ab-105">La Visor de cifrado de mensajes de Office 365 móvil era necesaria para leer mensajes de correo electrónico y datos adjuntos cifrados con la versión anterior de OME en teléfonos Apple y Android.</span><span class="sxs-lookup"><span data-stu-id="580ab-105">The Office 365 Message Encryption Viewer mobile app was required to read email messages and attachments that were encrypted with the previous version of OME on Apple and Android phones.</span></span> <span data-ttu-id="580ab-106">Además de quitar la aplicación Visor de OME, no estamos realizando ningún otro cambio en la versión anterior de OME.</span><span class="sxs-lookup"><span data-stu-id="580ab-106">Apart from removing the OME Viewer app, we are not making any other changes to the previous version of OME.</span></span>
  
## <a name="changes-from-august-2018"></a><span data-ttu-id="580ab-107">Cambios de agosto de 2018</span><span class="sxs-lookup"><span data-stu-id="580ab-107">Changes from August 2018</span></span>

<span data-ttu-id="580ab-108">Como se anunció en septiembre de 2017, hemos lanzado una nueva versión de [Cifrado de mensajes de Office 365](https://aka.ms/ome2017) para que los usuarios puedan enviar mensajes cifrados y protegidos a cualquier persona dentro o fuera de la organización sin el requisito de la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="580ab-108">As announced September 2017, we have released a new version of [Office 365 Message Encryption](https://aka.ms/ome2017) so that users can send encrypted and protected messages to anyone inside or outside the organization without the requirement of the mobile app.</span></span> <span data-ttu-id="580ab-109">Desde entonces, hemos agregado funcionalidades adicionales:</span><span class="sxs-lookup"><span data-stu-id="580ab-109">Since then, we've added additional capabilities:</span></span>
  
- [<span data-ttu-id="580ab-110">Plantilla de solo cifrado</span><span class="sxs-lookup"><span data-stu-id="580ab-110">Encrypt-only template</span></span>](https://aka.ms/encryptonly)

- [<span data-ttu-id="580ab-111">Control para descifrar datos adjuntos</span><span class="sxs-lookup"><span data-stu-id="580ab-111">Control to decrypt attachments</span></span>](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)

<span data-ttu-id="580ab-112">Con este cambio, los usuarios ya no podrán descargar la aplicación Visor de cifrado de mensajes de Office 365 móvil a partir del 1 de agosto.</span><span class="sxs-lookup"><span data-stu-id="580ab-112">With this change, users will no longer be able to download the Office 365 Message Encryption Viewer mobile app beginning August 1.</span></span> <span data-ttu-id="580ab-113">Como resultado, es posible que los destinatarios de correo no puedan leer mensajes cifrados con la versión anterior de OME en algunos dispositivos móviles Android y Apple.</span><span class="sxs-lookup"><span data-stu-id="580ab-113">As a result, mail recipients may not be able to read messages encrypted with the previous version of OME on some Android and Apple mobile devices.</span></span> <span data-ttu-id="580ab-114">Sin embargo, todavía podrán leer estos mensajes en equipos personales (a través de exploradores de escritorio).</span><span class="sxs-lookup"><span data-stu-id="580ab-114">However, they will still be able to read these messages on personal computers (via desktop browsers).</span></span> <span data-ttu-id="580ab-115">Los usuarios que ya han descargado la aplicación seguirán siendo capaces de usarlo.</span><span class="sxs-lookup"><span data-stu-id="580ab-115">Users who have already downloaded the app will continue to be able to use it.</span></span>
  
## <a name="why-this-change-was-made"></a><span data-ttu-id="580ab-116">Por qué se realizó este cambio</span><span class="sxs-lookup"><span data-stu-id="580ab-116">Why this change was made</span></span>

<span data-ttu-id="580ab-117">La nueva versión de OME ya no requiere que una aplicación móvil lea los mensajes de correo electrónico protegidos y los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="580ab-117">The new version of OME no longer requires a mobile app to read protected email messages and attachments.</span></span> <span data-ttu-id="580ab-118">Los clientes que usan las nuevas funcionalidades de OME pueden ver el mensaje protegido en Outlook móviles y no clientes pueden ver mensajes protegidos en un explorador.</span><span class="sxs-lookup"><span data-stu-id="580ab-118">Customers using the new OME capabilities can view the protected message in Outlook mobile and non-customers can view protected messages in a browser.</span></span>
  
<span data-ttu-id="580ab-119">Requerir que los usuarios descarguen una aplicación móvil es otro obstáculo para que los clientes puedan ver mensajes protegidos.</span><span class="sxs-lookup"><span data-stu-id="580ab-119">Requiring users to download a mobile app is another hurdle for customers to view protected messages.</span></span> <span data-ttu-id="580ab-120">Las nuevas Cifrado de mensajes de Office 365 proporcionan una mejor experiencia móvil.</span><span class="sxs-lookup"><span data-stu-id="580ab-120">The new Office 365 Message Encryption capabilities provide a better mobile experience.</span></span>
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="580ab-121">¿Puedo seguir utilizando la versión anterior de Cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="580ab-121">Can I still use the previous version of Office 365 Message Encryption</span></span>

<span data-ttu-id="580ab-122">Sin embargo, la versión anterior de Cifrado de mensajes de Office 365 no estará en desuso en este momento, pero hemos realizado mejoras significativas en la nueva versión de Cifrado de mensajes de Office 365, que facilitan el cifrado y los derechos protegen los datos confidenciales para cualquier usuario y en cualquier dispositivo, incluida la capacidad de los usuarios de leer mensajes protegidos directamente en Outlook (escritorio, móvil y web).</span><span class="sxs-lookup"><span data-stu-id="580ab-122">The previous version of Office 365 Message Encryption will not be deprecated at this time, however, we have made significant enhancements to the new version of Office 365 Message Encryption, which make it easier to encrypt and rights protect sensitive data to anyone and on any device - including the ability for users to read protected messages directly in Outlook (desktop, mobile, and web).</span></span> 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a><span data-ttu-id="580ab-123">¿Qué debo hacer para prepararme para este cambio?</span><span class="sxs-lookup"><span data-stu-id="580ab-123">What do I need to do to prepare for this change</span></span>

<span data-ttu-id="580ab-124">Si tu organización envía actualmente datos adjuntos cifrados a destinatarios que requieren la aplicación Visor de OME, debes actualizar la documentación y los recursos de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="580ab-124">If your organization currently sends encrypted attachments to recipients that require the OME Viewer app, you should update your documentation and training resources.</span></span>
  
<span data-ttu-id="580ab-125">Se recomienda actualizar las Exchange de flujo de correo existentes para usar la versión actual de OME para que su organización pueda aprovechar las nuevas y mejoradas capacidades.</span><span class="sxs-lookup"><span data-stu-id="580ab-125">We recommend updating existing Exchange mail flow rules to use the current version of OME so that your organization can take advantage of the new and improved capabilities.</span></span> <span data-ttu-id="580ab-126">Una vez configuradas las nuevas funcionalidades de OME, los destinatarios no necesitarán la aplicación Visor de OME para leer mensajes cifrados en dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="580ab-126">Once you have set up the new OME capabilities, recipients won't need the OME Viewer app to read encrypted messages on mobile devices.</span></span>
  
<span data-ttu-id="580ab-127">Microsoft recomienda realizar un plan para pasar a las nuevas funcionalidades de OME tan pronto como sea razonable para su organización.</span><span class="sxs-lookup"><span data-stu-id="580ab-127">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="580ab-128">Para obtener instrucciones, vea [Set up new Cifrado de mensajes de Office 365 capabilities](set-up-new-message-encryption-capabilities.md).</span><span class="sxs-lookup"><span data-stu-id="580ab-128">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="580ab-129">Si desea obtener más información sobre cómo funcionan primero las nuevas funcionalidades, [vea Cifrado de mensajes de Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="580ab-129">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span>
  

