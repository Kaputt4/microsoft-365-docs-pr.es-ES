---
title: Administrar la configuración de acceso a dispositivos en la movilidad y la seguridad básicas
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: La movilidad y la seguridad básica pueden ayudarle a proteger y administrar dispositivos móviles.
ms.openlocfilehash: 0d8f4293c45bcc1dc2a71dbc749641cf3791337e
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337077"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a><span data-ttu-id="387f4-103">Administrar la configuración de acceso a dispositivos en la movilidad y la seguridad básicas</span><span class="sxs-lookup"><span data-stu-id="387f4-103">Manage device access settings in Basic Mobility and Security</span></span>

<span data-ttu-id="387f4-104">Si está usando la movilidad y la seguridad básicas, puede haber dispositivos que no puede administrar con la movilidad y la seguridad básicas.</span><span class="sxs-lookup"><span data-stu-id="387f4-104">If you're using Basic Mobility and Security, there might be devices that you can't manage with Basic Mobility and Security.</span></span> <span data-ttu-id="387f4-105">Si es así, debe bloquear el acceso a la aplicación de Exchange ActiveSync al correo electrónico de Microsoft 365 para dispositivos móviles que no son compatibles con la movilidad y la seguridad básicas.</span><span class="sxs-lookup"><span data-stu-id="387f4-105">If so, you should block Exchange ActiveSync app access to Microsoft 365 email for mobile devices that aren't supported by Basic Mobility and Security.</span></span> <span data-ttu-id="387f4-106">Esto ayuda a proteger la información de la organización en más dispositivos.</span><span class="sxs-lookup"><span data-stu-id="387f4-106">This helps secure your organization information across more devices.</span></span>

<span data-ttu-id="387f4-107">Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="387f4-107">Use these steps:</span></span>

1. <span data-ttu-id="387f4-108">Inicie sesión en Microsoft 365 con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="387f4-108">Sign in to  Microsoft 365 with your global admin account.</span></span>
    
2. <span data-ttu-id="387f4-109">En el explorador, escriba:  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="387f4-109">In your browser, type: [https://protection.office.com](https://protection.office.com/).</span></span>    

    >[!IMPORTANT]
    ><span data-ttu-id="387f4-110">Si esta es la primera vez que usa MDM para Microsoft 365 Business Standard, actívelo aquí: activar la [Administración de dispositivos móviles](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span><span class="sxs-lookup"><span data-stu-id="387f4-110">If this is the first time you're using MDM for Microsoft 365 Business Standard, activate it here: [Activate Mobile Device Management](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="387f4-111">Una vez que la haya activado, administre los dispositivos con [Office 365 Security & Compliance](https://protection.office.com/).</span><span class="sxs-lookup"><span data-stu-id="387f4-111">After you've activated it, manage your devices with [Office 365 Security & Compliance](https://protection.office.com/).</span></span>

3. <span data-ttu-id="387f4-112">Vaya a prevención de pérdida de datos >directivas de dispositivo de  **Administración de dispositivos**   >  **Device policies**y seleccione **administrar la configuración de acceso a dispositivos en toda la organización**.</span><span class="sxs-lookup"><span data-stu-id="387f4-112">Go to Data loss prevention > **Device management** > **Device policies**, and select **Manage organization-wide device access settings**.</span></span>
    
4. <span data-ttu-id="387f4-113">Seleccione **bloquear**.</span><span class="sxs-lookup"><span data-stu-id="387f4-113">Select **Block**.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Casilla de verificación de acceso básico a bloque de seguridad y movilidad":::

5. <span data-ttu-id="387f4-115">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="387f4-115">Select **Save**.</span></span> 

<span data-ttu-id="387f4-116">Para obtener información sobre los dispositivos compatibles con la movilidad y la seguridad básica, consulte [capacidades básicas de movilidad y seguridad](capabilities-of-basic-mobility-and-secruity.md).</span><span class="sxs-lookup"><span data-stu-id="387f4-116">To learn what devices Basic Mobility and Security supports, see [Capabilities of Basic Mobility and Security](capabilities-of-basic-mobility-and-secruity.md).</span></span>