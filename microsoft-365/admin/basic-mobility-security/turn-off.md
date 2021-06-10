---
title: Desactivar Movilidad y seguridad básicas
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
description: Quite grupos o directivas para desactivar La movilidad y la seguridad básicas.
ms.openlocfilehash: 1d81aed01193fb2ba821ebc055958ac6cd8ac382
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023874"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="f9248-103">Desactivar Movilidad y seguridad básicas</span><span class="sxs-lookup"><span data-stu-id="f9248-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="f9248-104">Para desactivar de forma eficaz la movilidad y la seguridad básicas, quitas grupos de personas definidos por grupos de seguridad de las directivas de administración de dispositivos o quitas las propias directivas.</span><span class="sxs-lookup"><span data-stu-id="f9248-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="f9248-105">Quita grupos de usuarios quitando grupos de seguridad de usuario de las directivas de dispositivo que creaste.</span><span class="sxs-lookup"><span data-stu-id="f9248-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>

- <span data-ttu-id="f9248-106">Deshabilite la movilidad y la seguridad básicas para todos los usuarios quitando todas las directivas de dispositivos de movilidad y seguridad básicas.</span><span class="sxs-lookup"><span data-stu-id="f9248-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>

<span data-ttu-id="f9248-107">Estas opciones quitan el cumplimiento básico de movilidad y seguridad para dispositivos de la organización.</span><span class="sxs-lookup"><span data-stu-id="f9248-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="f9248-108">Desafortunadamente, no puedes simplemente "desaprovisionar" La movilidad y la seguridad básicas después de configurarla.</span><span class="sxs-lookup"><span data-stu-id="f9248-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="f9248-109">Tenga en cuenta el impacto en los dispositivos de los usuarios al quitar grupos de seguridad de usuarios de las directivas o quitar las propias directivas.</span><span class="sxs-lookup"><span data-stu-id="f9248-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="f9248-110">Por ejemplo, los perfiles de correo electrónico y los correos electrónicos almacenados en caché pueden quitarse, según el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f9248-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="f9248-111">Para obtener más información, consulta  [¿Qué sucede cuando eliminas una directiva o quitas a un usuario de la directiva?](../../admin/basic-mobility-security/create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f9248-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](../../admin/basic-mobility-security/create-device-security-policies.md)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="f9248-112">Quitar grupos de seguridad de usuarios de directivas de dispositivos de movilidad básica y seguridad</span><span class="sxs-lookup"><span data-stu-id="f9248-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="f9248-113">En el tipo de explorador:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="f9248-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="f9248-114">Selecciona una directiva de dispositivo y selecciona **Editar directiva**.</span><span class="sxs-lookup"><span data-stu-id="f9248-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="f9248-115">En la  **página Implementación,**   seleccione **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="f9248-115">On the  **Deployment**  page, select **Remove**.</span></span>

4. <span data-ttu-id="f9248-116">En  **Grupos**, seleccione un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f9248-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="f9248-117">Seleccione  **Quitar** y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f9248-117">Select  **Remove**, and select **Save**.</span></span>

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="f9248-118">Quitar directivas básicas de dispositivos de movilidad y seguridad</span><span class="sxs-lookup"><span data-stu-id="f9248-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="f9248-119">En el tipo de explorador:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="f9248-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="f9248-120">Seleccione una directiva de dispositivo y, a continuación,  **seleccione Eliminar directiva**.</span><span class="sxs-lookup"><span data-stu-id="f9248-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="f9248-121">En el cuadro de diálogo Advertencia, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="f9248-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE]
><span data-ttu-id="f9248-122">Para obtener más pasos para desbloquear dispositivos si los dispositivos de la organización siguen en estado [bloqueado,](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)consulta la entrada de blog Quitar control de acceso de Administración de dispositivos móviles para Office 365 .</span><span class="sxs-lookup"><span data-stu-id="f9248-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
