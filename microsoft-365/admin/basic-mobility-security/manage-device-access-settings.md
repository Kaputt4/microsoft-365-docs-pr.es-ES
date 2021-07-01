---
title: Administrar la configuración de acceso a dispositivos en Movilidad y seguridad básicas
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
description: La movilidad y la seguridad básicas pueden ayudarle a proteger y administrar dispositivos móviles.
ms.openlocfilehash: 24eeb1dfccef3d30e577b15ecb9d2fda4d902cdc
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228164"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a><span data-ttu-id="4709b-103">Administrar la configuración de acceso a dispositivos en Movilidad y seguridad básicas</span><span class="sxs-lookup"><span data-stu-id="4709b-103">Manage device access settings in Basic Mobility and Security</span></span>

<span data-ttu-id="4709b-104">Si usas Movilidad y seguridad básicas, es posible que haya dispositivos que no puedas administrar con Movilidad y seguridad básicas.</span><span class="sxs-lookup"><span data-stu-id="4709b-104">If you're using Basic Mobility and Security, there might be devices that you can't manage with Basic Mobility and Security.</span></span> <span data-ttu-id="4709b-105">Si es así, debes bloquear Exchange ActiveSync acceso de la aplicación a Microsoft 365 correo electrónico para dispositivos móviles que no son compatibles con La movilidad y la seguridad básicas.</span><span class="sxs-lookup"><span data-stu-id="4709b-105">If so, you should block Exchange ActiveSync app access to Microsoft 365 email for mobile devices that aren't supported by Basic Mobility and Security.</span></span> <span data-ttu-id="4709b-106">Esto ayuda a proteger la información de la organización en más dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4709b-106">This helps secure your organization information across more devices.</span></span>

<span data-ttu-id="4709b-107">Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4709b-107">Use these steps:</span></span>

1. <span data-ttu-id="4709b-108">Inicie sesión en Microsoft 365 con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="4709b-108">Sign in to  Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="4709b-109">En el explorador, escriba:  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="4709b-109">In your browser, type: [https://protection.office.com](https://protection.office.com/).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4709b-110">Si es la primera vez que usas Movilidad y seguridad básicas para Microsoft 365 Empresa Estándar, actíbalo aquí: Activar seguridad [básica y movilidad](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span><span class="sxs-lookup"><span data-stu-id="4709b-110">If this is the first time you're using Basic Mobility and Security for Microsoft 365 Business Standard, activate it here: [Activate Basic Security and Mobility](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="4709b-111">Después de activarlo, administra los dispositivos con Office 365 [seguridad & cumplimiento](https://protection.office.com/).</span><span class="sxs-lookup"><span data-stu-id="4709b-111">After you've activated it, manage your devices with [Office 365 Security & Compliance](https://protection.office.com/).</span></span>

3. <span data-ttu-id="4709b-112">Ve a Prevención de pérdida de datos > **Administración** de dispositivos Directivas de dispositivos y selecciona Administrar la configuración de acceso de dispositivos en toda   >  \*\*\*\* **la organización.**</span><span class="sxs-lookup"><span data-stu-id="4709b-112">Go to Data loss prevention > **Device management** > **Device policies**, and select **Manage organization-wide device access settings**.</span></span>

4. <span data-ttu-id="4709b-113">Seleccione **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="4709b-113">Select **Block**.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Casilla de verificación Acceso bloqueado de movilidad básica y seguridad":::

5. <span data-ttu-id="4709b-115">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4709b-115">Select **Save**.</span></span>

<span data-ttu-id="4709b-116">Para obtener información sobre los dispositivos compatibles con la movilidad básica y la seguridad, consulte [Capabilities of Basic Mobility and Security](capabilities.md).</span><span class="sxs-lookup"><span data-stu-id="4709b-116">To learn what devices Basic Mobility and Security supports, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>
