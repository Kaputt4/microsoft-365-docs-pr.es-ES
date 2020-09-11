---
title: Desactivar la movilidad y la seguridad básicas
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
description: Quitar grupos o directivas para desactivar la movilidad y la seguridad básicas.
ms.openlocfilehash: 54f78cc30e5259ad5244ce3a8fc6d0f46a395d7c
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430294"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="46ace-103">Desactivar la movilidad y la seguridad básicas</span><span class="sxs-lookup"><span data-stu-id="46ace-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="46ace-104">Para desactivar eficazmente la movilidad y la seguridad básica, se quitan los grupos de personas definidas por grupos de seguridad de las directivas de administración de dispositivos o se quitan las directivas.</span><span class="sxs-lookup"><span data-stu-id="46ace-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="46ace-105">Quite grupos de usuarios quitando grupos de seguridad de usuarios de las directivas de dispositivo que ha creado.</span><span class="sxs-lookup"><span data-stu-id="46ace-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>
    
- <span data-ttu-id="46ace-106">Deshabilite la movilidad y la seguridad básicas para todos al quitar todas las directivas de dispositivos de seguridad y movilidad básicas.</span><span class="sxs-lookup"><span data-stu-id="46ace-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>
    
<span data-ttu-id="46ace-107">Estas opciones eliminan la movilidad básica y el cumplimiento de la seguridad de los dispositivos de la organización.</span><span class="sxs-lookup"><span data-stu-id="46ace-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="46ace-108">Desafortunadamente, no se puede simplemente "desaprovisionar" la movilidad y la seguridad básicas una vez que se ha configurado.</span><span class="sxs-lookup"><span data-stu-id="46ace-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="46ace-109">Tenga en cuenta el impacto en los dispositivos de los usuarios al quitar grupos de seguridad de usuarios de las directivas o quitar las directivas en sí.</span><span class="sxs-lookup"><span data-stu-id="46ace-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="46ace-110">Por ejemplo, los perfiles de correo electrónico y los correos electrónicos en caché se pueden quitar, según el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="46ace-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="46ace-111">Para obtener más información, vea  [¿Qué sucede cuando se elimina una directiva o se quita un usuario de la Directiva?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span><span class="sxs-lookup"><span data-stu-id="46ace-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="46ace-112">Quitar grupos de seguridad de usuarios de las directivas básicas de dispositivos de seguridad y movilidad</span><span class="sxs-lookup"><span data-stu-id="46ace-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="46ace-113">En el explorador, escriba:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="46ace-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="46ace-114">Seleccione una directiva de dispositivo y seleccione **Editar Directiva**.</span><span class="sxs-lookup"><span data-stu-id="46ace-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="46ace-115">En la página  **implementación**   , seleccione **quitar**.</span><span class="sxs-lookup"><span data-stu-id="46ace-115">On the  **Deployment**  page, select **Remove**.</span></span>
    
4. <span data-ttu-id="46ace-116">En  **grupos**, seleccione un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="46ace-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="46ace-117">Seleccione  **quitar**y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="46ace-117">Select  **Remove**, and select **Save**.</span></span>
    

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="46ace-118">Quitar directivas de dispositivos de seguridad y movilidad básicas</span><span class="sxs-lookup"><span data-stu-id="46ace-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="46ace-119">En el explorador, escriba:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="46ace-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="46ace-120">Seleccione una directiva de dispositivo y, a continuación, seleccione  **eliminar Directiva**.</span><span class="sxs-lookup"><span data-stu-id="46ace-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="46ace-121">En el cuadro de diálogo de advertencia, seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="46ace-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE] 
><span data-ttu-id="46ace-122">Para obtener más pasos para desbloquear dispositivos si los dispositivos de la organización siguen estando en estado bloqueados, vea la entrada [de blog quitar el control de acceso de la administración de dispositivos móviles para Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span><span class="sxs-lookup"><span data-stu-id="46ace-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
