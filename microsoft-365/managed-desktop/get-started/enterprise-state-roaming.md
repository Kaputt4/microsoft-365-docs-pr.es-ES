---
title: Habilitar Enterprise State Roaming
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 709a231f1c3f401ceeee2b3aaf99ff275f107e30
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409121"
---
# <a name="enable-enterprise-state-roaming"></a><span data-ttu-id="0807b-103">Habilitar Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="0807b-103">Enable Enterprise State Roaming</span></span>

<span data-ttu-id="0807b-104">[Enterprise State Roaming permite](/azure/active-directory/devices/enterprise-state-roaming-overview) a los usuarios sincronizar de forma segura los datos de configuración de usuario y aplicación en la nube.</span><span class="sxs-lookup"><span data-stu-id="0807b-104">[Enterprise State Roaming](/azure/active-directory/devices/enterprise-state-roaming-overview) lets users securely synchronize user and application settings data to the cloud.</span></span> <span data-ttu-id="0807b-105">Esto significa que tendrán la misma experiencia independientemente Windows dispositivo en el que inicien sesión.</span><span class="sxs-lookup"><span data-stu-id="0807b-105">This means they'll have the same experience no matter which Windows device they sign into.</span></span> <span data-ttu-id="0807b-106">Por ejemplo, si reemplaza uno de sus dispositivos Escritorio administrado de Microsoft por uno nuevo, se verá y se comportará exactamente igual que el último.</span><span class="sxs-lookup"><span data-stu-id="0807b-106">For example, if you replace one of their Microsoft Managed Desktop devices with a new one, it will look and behave exactly the same as the last one.</span></span> <span data-ttu-id="0807b-107">Enterprise La itinerancia de estado es una característica opcional para el servicio de Escritorio administrado de Microsoft que puede configurar para los usuarios y que no se incluye ni administra como parte de Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0807b-107">Enterprise State Roaming is an optional feature for the Microsoft Managed Desktop service that you can configure for your users and isn't included or managed as part of Microsoft Managed Desktop.</span></span>

<span data-ttu-id="0807b-108">Para habilitar Enterprise itinerancia de estado, siga los pasos descritos en [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).</span><span class="sxs-lookup"><span data-stu-id="0807b-108">To enable Enterprise State Roaming, follow the steps in [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

>[!NOTE]
><span data-ttu-id="0807b-109">Si habilitas la Enterprise de estado, la lista de idioma preferido sobrescribirá el idioma seleccionado durante la configuración del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0807b-109">If you enable Enterprise State Roaming, your preferred language list will overwrite the language selected during device setup.</span></span> <span data-ttu-id="0807b-110">Aunque los usuarios pueden solucionar esto fácilmente, podría provocar una experiencia de localización incoherente inicialmente.</span><span class="sxs-lookup"><span data-stu-id="0807b-110">Although users can fix this easily, it could cause an inconsistent localization experience initially.</span></span> <span data-ttu-id="0807b-111">Determine si Enterprise itinerancia de estado es adecuada para los usuarios antes de configurar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0807b-111">Determine if Enterprise State Roaming is right for your users before setting up devices.</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="0807b-112">Pasos para empezar con Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="0807b-112">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="0807b-113">Agregar y verificar los contactos de administración en el portal de administración </span><span class="sxs-lookup"><span data-stu-id="0807b-113">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="0807b-114">Ajustar el acceso condicional</span><span class="sxs-lookup"><span data-stu-id="0807b-114">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="0807b-115">Asignar licencias</span><span class="sxs-lookup"><span data-stu-id="0807b-115">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="0807b-116">Desplegar el portal de empresa de Intune</span><span class="sxs-lookup"><span data-stu-id="0807b-116">Deploy Intune Company Portal</span></span>](company-portal.md)
5. <span data-ttu-id="0807b-117">Habilitar Enterprise itinerancia de estado (este tema)</span><span class="sxs-lookup"><span data-stu-id="0807b-117">Enable Enterprise State Roaming (this topic)</span></span>
6. [<span data-ttu-id="0807b-118">Instalar dispositivos</span><span class="sxs-lookup"><span data-stu-id="0807b-118">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="0807b-119">Prepare a los usuarios para que usen los dispositivos</span><span class="sxs-lookup"><span data-stu-id="0807b-119">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="0807b-120">Implementar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="0807b-120">Deploy apps</span></span>](deploy-apps.md)
