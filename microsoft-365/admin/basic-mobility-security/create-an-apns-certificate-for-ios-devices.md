---
title: Crear certificados de APN para dispositivos iOS
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Administrar dispositivos iOS en Movilidad y seguridad básicas.
ms.openlocfilehash: 84f3589593ef26325397f5b6e90d5b21662d2352
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228248"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="c5b32-103">Crear certificados de APN para dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="c5b32-103">Create an APNs certificate for iOS devices</span></span>

<span data-ttu-id="c5b32-104">Para administrar dispositivos iOS, como iPads y iPhones, en Movilidad y seguridad básicas, crea un certificado APNs.</span><span class="sxs-lookup"><span data-stu-id="c5b32-104">To manage iOS devices such as iPads and iPhones in Basic Mobility and Security, create an APNs certificate.</span></span>

1. <span data-ttu-id="c5b32-105">Inicie sesión en Microsoft 365 con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="c5b32-105">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="c5b32-106">En el explorador, escriba  <https://protection.office.com/> .</span><span class="sxs-lookup"><span data-stu-id="c5b32-106">In your browser, type <https://protection.office.com/>.</span></span>

3. <span data-ttu-id="c5b32-107">Seleccione  **Prevención de pérdida de** datos Administración   >  **de** dispositivos y elija Certificado **apns para dispositivos iOS.**</span><span class="sxs-lookup"><span data-stu-id="c5b32-107">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>

4. <span data-ttu-id="c5b32-108">En la página Certificado de notificación de inserción Configuración Apple, elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c5b32-108">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>

5. <span data-ttu-id="c5b32-109">Seleccione Descargar el archivo CSR y guarde la solicitud de firma de certificado en algún lugar del equipo que recuerde.</span><span class="sxs-lookup"><span data-stu-id="c5b32-109">Select Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="c5b32-110">Seleccione  **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c5b32-110">Select  **Next**.</span></span>

6. <span data-ttu-id="c5b32-111">En la página Crear un certificado de APNs:</span><span class="sxs-lookup"><span data-stu-id="c5b32-111">On the Create an APNs certificate page:</span></span>

    1. <span data-ttu-id="c5b32-112">Selecciona Apple APNS Portal para abrir el Portal de certificados de inserción de Apple.</span><span class="sxs-lookup"><span data-stu-id="c5b32-112">Select  Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>

    2. <span data-ttu-id="c5b32-113">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="c5b32-113">Sign in with an Apple ID.</span></span>

       > [!IMPORTANT]
       > <span data-ttu-id="c5b32-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="c5b32-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    3. <span data-ttu-id="c5b32-116">Seleccione  **Crear un certificado** y acepte los   Términos de uso.</span><span class="sxs-lookup"><span data-stu-id="c5b32-116">Select  **Create a Certificate**  and accept the Terms of Use.</span></span>

    4. <span data-ttu-id="c5b32-117">Vaya a la solicitud de firma de certificado que descargó en el equipo desde Microsoft 365 y seleccione **Upload**.</span><span class="sxs-lookup"><span data-stu-id="c5b32-117">Browse to the certificate signing request you downloaded to your computer from Microsoft 365, and select **Upload**.</span></span>

       <span data-ttu-id="c5b32-118">Descargue el certificado apns creado por el Portal de certificados de inserción de Apple en el equipo.</span><span class="sxs-lookup"><span data-stu-id="c5b32-118">Download the APNs certificate created by the Apple Push Certificate Portal to your computer.</span></span>

       > [!TIP]
       > <span data-ttu-id="c5b32-119">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="c5b32-119">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="c5b32-120">Vuelva a Microsoft 365 y seleccione  Siguiente para llegar a la Upload de certificado   de  **APNS.**  </span><span class="sxs-lookup"><span data-stu-id="c5b32-120">Go back to Microsoft 365, and select **Next**  to get to the  **Upload APNS certificate** page.</span></span>

8. <span data-ttu-id="c5b32-121"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="c5b32-121">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>

9. <span data-ttu-id="c5b32-122">Seleccione  **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="c5b32-122">Select  **Finish**.</span></span>

<span data-ttu-id="c5b32-123">Para completar la configuración, vuelva al Centro de seguridad y & cumplimiento > **directivas de** seguridad   >  **Administración de**   >  **dispositivos Administrar la configuración.**</span><span class="sxs-lookup"><span data-stu-id="c5b32-123">To complete setup, go back to the Security & Compliance Center > **Security policies** > **Device management** > **Manage settings**.</span></span>
