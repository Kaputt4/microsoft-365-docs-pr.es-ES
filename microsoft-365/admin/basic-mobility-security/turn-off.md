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
ms.openlocfilehash: 0786ac8ebd190b9af3211c211cc6db2ea9e0ea48
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876845"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="05207-103">Desactivar la movilidad y la seguridad básicas</span><span class="sxs-lookup"><span data-stu-id="05207-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="05207-104">Para desactivar eficazmente la movilidad y la seguridad básicas, quita los grupos de personas definidos por los grupos de seguridad de las directivas de administración de dispositivos o quita las directivas en sí.</span><span class="sxs-lookup"><span data-stu-id="05207-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="05207-105">Quita grupos de usuarios quitando los grupos de seguridad de usuario de las directivas de dispositivo que hayas creado.</span><span class="sxs-lookup"><span data-stu-id="05207-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>

- <span data-ttu-id="05207-106">Deshabilite la movilidad y la seguridad básicas para todos los usuarios mediante la eliminación de todas las directivas de dispositivos de movilidad y seguridad básicas.</span><span class="sxs-lookup"><span data-stu-id="05207-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>

<span data-ttu-id="05207-107">Estas opciones quitan la aplicación de movilidad y seguridad básica para los dispositivos de la organización.</span><span class="sxs-lookup"><span data-stu-id="05207-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="05207-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span><span class="sxs-lookup"><span data-stu-id="05207-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="05207-109">Ten en cuenta el impacto en los dispositivos de los usuarios al quitar grupos de seguridad de usuarios de las directivas o quitar las propias directivas.</span><span class="sxs-lookup"><span data-stu-id="05207-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="05207-110">Por ejemplo, los perfiles de correo electrónico y los correos electrónicos almacenados en caché pueden quitarse, según el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="05207-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="05207-111">Para obtener más información, consulta  [¿Qué sucede cuando eliminas una directiva o quitas un usuario de la directiva?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span><span class="sxs-lookup"><span data-stu-id="05207-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="05207-112">Quitar grupos de seguridad de usuario de las directivas de dispositivos de movilidad y seguridad básicas</span><span class="sxs-lookup"><span data-stu-id="05207-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="05207-113">En el tipo de explorador:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="05207-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="05207-114">Selecciona una directiva de dispositivo y selecciona **Editar directiva.**</span><span class="sxs-lookup"><span data-stu-id="05207-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="05207-115">En la  **página Implementación,**   seleccione **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="05207-115">On the  **Deployment**  page, select **Remove**.</span></span>

4. <span data-ttu-id="05207-116">En  **Grupos,** seleccione un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="05207-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="05207-117">Seleccione  **Quitar** y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="05207-117">Select  **Remove**, and select **Save**.</span></span>

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="05207-118">Quitar directivas de dispositivos de movilidad y seguridad básicas</span><span class="sxs-lookup"><span data-stu-id="05207-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="05207-119">En el tipo de explorador:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="05207-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="05207-120">Seleccione una directiva de dispositivo y, a  **continuación, seleccione Eliminar directiva.**</span><span class="sxs-lookup"><span data-stu-id="05207-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="05207-121">En el cuadro de diálogo Advertencia, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="05207-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE]
><span data-ttu-id="05207-122">Para obtener más pasos para desbloquear dispositivos si los dispositivos de su organización aún están bloqueados, vea la entrada de blog Quitar el control de acceso de la administración de dispositivos móviles [para Office 365.](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)</span><span class="sxs-lookup"><span data-stu-id="05207-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
