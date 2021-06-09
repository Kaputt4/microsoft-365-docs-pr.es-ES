---
title: Quitar dispositivos
description: Quitar dispositivos de Escritorio administrado de Microsoft administración
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: fa1cb7307fddd815a2a9249c5a98739d21bd2418
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893931"
---
# <a name="remove-devices"></a><span data-ttu-id="ac33b-103">Quitar dispositivos</span><span class="sxs-lookup"><span data-stu-id="ac33b-103">Remove devices</span></span>

<span data-ttu-id="ac33b-104">Puedes quitar dispositivos de Escritorio administrado de Microsoft administración mediante el portal de administración.</span><span class="sxs-lookup"><span data-stu-id="ac33b-104">You can remove devices from Microsoft Managed Desktop management by using the Admin portal.</span></span> <span data-ttu-id="ac33b-105">Esta acción es permanente, pero puede volver a registrarlas con Escritorio administrado de Microsoft siguiendo los pasos [de registro](../get-started/register-devices-self.md).</span><span class="sxs-lookup"><span data-stu-id="ac33b-105">This action is permanent, but you can register them with Microsoft Managed Desktop again by following the [registration steps](../get-started/register-devices-self.md).</span></span>

<span data-ttu-id="ac33b-106">Al quitar un dispositivo, se produce lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ac33b-106">When you remove a device, all of the following occur:</span></span>

- <span data-ttu-id="ac33b-107">Quitamos el dispositivo de Autopilot.</span><span class="sxs-lookup"><span data-stu-id="ac33b-107">We remove the device from Autopilot.</span></span>
- <span data-ttu-id="ac33b-108">Quitamos el dispositivo de todos los grupos de dispositivos "Modern Workplace".</span><span class="sxs-lookup"><span data-stu-id="ac33b-108">We remove the device from  all "Modern Workplace" device groups.</span></span>
- <span data-ttu-id="ac33b-109">Quitamos el dispositivo de la hoja **Dispositivos** en el portal de administración.</span><span class="sxs-lookup"><span data-stu-id="ac33b-109">We remove the device from the **Devices** blade in the Admin portal.</span></span>

<span data-ttu-id="ac33b-110">Cuando quitas un dispositivo, también tienes la opción de quitarlo de Azure Active Directory (Azure AD) y Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="ac33b-110">When you remove a device, you have the option to also remove it from Azure Active Directory (Azure AD) and Microsoft Intune.</span></span>
 
> [!CAUTION]
> <span data-ttu-id="ac33b-111">Quitar los objetos relacionados con un dispositivo de Azure AD y Microsoft Intune es permanente.</span><span class="sxs-lookup"><span data-stu-id="ac33b-111">Removing the objects related to a device from Azure AD and Microsoft Intune is permanent.</span></span> <span data-ttu-id="ac33b-112">Si quita los objetos, no podrá ver ni administrar los dispositivos desde Intune y Azure Portals.</span><span class="sxs-lookup"><span data-stu-id="ac33b-112">If you remove the objects, you won't be able to view or manage the devices from the Intune and Azure portals.</span></span> <span data-ttu-id="ac33b-113">Los dispositivos no podrán acceder a los recursos corporativos de su empresa.</span><span class="sxs-lookup"><span data-stu-id="ac33b-113">The devices won't be able to access their company's corporate resources.</span></span> <span data-ttu-id="ac33b-114">Es posible que los datos de la empresa se eliminen de ellos si los dispositivos intentan iniciar sesión después de eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="ac33b-114">Company data might be deleted from them if the devices try to sign in after they're deleted.</span></span>

1. <span data-ttu-id="ac33b-115">En [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), seleccione **Dispositivos** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="ac33b-115">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span>
2. <span data-ttu-id="ac33b-116">Busque la sección **Escritorio administrado de Microsoft** del menú y seleccione **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="ac33b-116">Look for the **Microsoft Managed Desktop** section of the menu and select **Devices**.</span></span>
3. <span data-ttu-id="ac33b-117">En el área Escritorio administrado de Microsoft de trabajo Dispositivos, seleccione los dispositivos que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="ac33b-117">In the Microsoft Managed Desktop Devices workspace, select the devices you want to delete.</span></span>
4. <span data-ttu-id="ac33b-118">Selecciona **Acciones de dispositivo** y, a continuación, selecciona Eliminar **dispositivo** que abre un fly-in para quitar los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ac33b-118">Select **Device actions**, and then select **Delete Device** which opens a fly-in to remove the devices.</span></span>
5. <span data-ttu-id="ac33b-119">En el menú desplegable, revise los dispositivos seleccionados y, a continuación, seleccione **Quitar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="ac33b-119">In the fly-in, review the selected devices and then select **Remove devices**.</span></span> <span data-ttu-id="ac33b-120">Si también desea quitar los objetos de Azure AD e Intune al mismo tiempo, active la casilla.</span><span class="sxs-lookup"><span data-stu-id="ac33b-120">If you want to also remove the Azure AD and Intune objects at the same time, select the check box.</span></span> <span data-ttu-id="ac33b-121">La eliminación del dispositivo puede tardar unos minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="ac33b-121">Device removal can take a few minutes to complete.</span></span>

> [!NOTE]
> <span data-ttu-id="ac33b-122">No puedes quitar dispositivos que estén en un **estado de registro** pendiente.</span><span class="sxs-lookup"><span data-stu-id="ac33b-122">You can't remove devices that are in a **pending** registration state.</span></span>