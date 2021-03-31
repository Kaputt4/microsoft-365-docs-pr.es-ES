---
title: Pasos para que los Socios puedan registrar dispositivos
description: Cómo los partners pueden registrar dispositivos para que puedan ser administrados por Microsoft Managed Desktop
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
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
ms.openlocfilehash: baf15ca4b83052af84d2b22b3d2604c6022ac900
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445595"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="1fa4c-104">Pasos para que los Socios puedan registrar dispositivos</span><span class="sxs-lookup"><span data-stu-id="1fa4c-104">Steps for Partners to register devices</span></span>


<span data-ttu-id="1fa4c-105">En este tema se describen los pasos que deben seguir los partners para registrar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1fa4c-105">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="1fa4c-106">El proceso para registrar dispositivos usted mismo se documenta en Registrar dispositivos [en Microsoft Managed Desktop usted mismo.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="1fa4c-106">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="1fa4c-107">Prepararse para el registro</span><span class="sxs-lookup"><span data-stu-id="1fa4c-107">Prepare for registration</span></span> 
<span data-ttu-id="1fa4c-108">Antes de completar el registro de un cliente, primero debe establecer una relación con ellos en el [Centro de partners](https://partner.microsoft.com/dashboard).</span><span class="sxs-lookup"><span data-stu-id="1fa4c-108">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="1fa4c-109">Consulta la [documentación de consentimiento](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) para obtener más información sobre ese proceso.</span><span class="sxs-lookup"><span data-stu-id="1fa4c-109">See the [consent documentation](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) for more details on that process.</span></span> <span data-ttu-id="1fa4c-110">Cualquier partner csp puede agregar dispositivos en nombre de cualquier cliente, siempre que el cliente consiente.</span><span class="sxs-lookup"><span data-stu-id="1fa4c-110">Any CSP partner can add devices on behalf of any customer, as long as the customer consents.</span></span> <span data-ttu-id="1fa4c-111">También puede obtener más información sobre las relaciones de partners y los permisos de Autopilot en la [ayuda del Centro de partners.](/partner-center/customers_revoke_admin_privileges#windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="1fa4c-111">You can also learn more about partner relationships and Autopilot permissions at [Partner Center help](/partner-center/customers_revoke_admin_privileges#windows-autopilot).</span></span>


> [!NOTE]
> <span data-ttu-id="1fa4c-112">Esta documentación es solo para partners y OEM.</span><span class="sxs-lookup"><span data-stu-id="1fa4c-112">This documentation is only for Partners and OEMs.</span></span> <span data-ttu-id="1fa4c-113">El proceso de autoinscripción se documenta en Registrar dispositivos [en Microsoft Managed Desktop usted mismo.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="1fa4c-113">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>


## <a name="register-devices-by-using-partner-center"></a><span data-ttu-id="1fa4c-114">Registrar dispositivos mediante el Centro de partners</span><span class="sxs-lookup"><span data-stu-id="1fa4c-114">Register devices by using Partner Center</span></span>

<span data-ttu-id="1fa4c-115">Una vez establecida la relación con los clientes, puede aprovechar el Centro de partners para agregar dispositivos a Autopilot para cualquiera de los clientes con los que tenga una relación siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="1fa4c-115">Once you have established the relationship with your customers, you can leverage Partner Center to add devices to Autopilot for any of the customers that you have a relationship with by following these steps:</span></span>

1. <span data-ttu-id="1fa4c-116">Vaya al [Centro de partners](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="1fa4c-116">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="1fa4c-117">Selecciona **Clientes** en el menú Centro de partners y, a continuación, selecciona el cliente cuyos dispositivos quieres administrar.</span><span class="sxs-lookup"><span data-stu-id="1fa4c-117">Select **Customers** from the Partner Center menu and then select the customer whose devices you want to manage.</span></span>
3. <span data-ttu-id="1fa4c-118">En la página de detalles del cliente, seleccione **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="1fa4c-118">On the customer's detail page, select **Devices**.</span></span>
4. <span data-ttu-id="1fa4c-119">En Aplicar perfiles a **dispositivos,** seleccione **Agregar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="1fa4c-119">Under **Apply profiles** to devices, select **Add devices**.</span></span>
5. <span data-ttu-id="1fa4c-120">Escriba **Microsoft365Managed_Autopilot** nombre del grupo y,  a continuación, seleccione Examinar para cargar la lista del cliente (en formato de archivo .csv) al Centro de partners.</span><span class="sxs-lookup"><span data-stu-id="1fa4c-120">Enter **Microsoft365Managed_Autopilot** for the Group Name and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="1fa4c-121">El nombre del grupo debe coincidir **Microsoft365Managed_Autopilot** exactamente, incluida la mayúscula y los caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="1fa4c-121">The Group Name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="1fa4c-122">Esto permitirá que los dispositivos recién registrados se asignen con el perfil de Microsoft Managed Desktop Autopilot.</span><span class="sxs-lookup"><span data-stu-id="1fa4c-122">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>

>[!NOTE]
> <span data-ttu-id="1fa4c-123">Deberías haber recibido este archivo .csv con la compra del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1fa4c-123">You should have received this .csv file with your device purchase.</span></span> <span data-ttu-id="1fa4c-124">Si no has recibido un archivo .csv, puedes crear uno tú mismo siguiendo los pasos descritos en Agregar dispositivos a [Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="1fa4c-124">If you didn't receive a .csv file, you can create one yourself by following the steps in [Adding devices to Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell).</span></span> <span data-ttu-id="1fa4c-125">El Windows PowerShell script es diferente del que se usa para el portal de administración de [Escritorio administrado de Microsoft](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash).</span><span class="sxs-lookup"><span data-stu-id="1fa4c-125">The Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash).</span></span> <span data-ttu-id="1fa4c-126">Los partners deben [usar Get-WindowsAutoPilotInfo para](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) registrar dispositivos para dispositivos de Escritorio administrado de Microsoft en el Centro de partners.</span><span class="sxs-lookup"><span data-stu-id="1fa4c-126">Partners should use [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to register devices for Microsoft Managed Desktop devices in Partner Center.</span></span>

<span data-ttu-id="1fa4c-127">Si recibe un mensaje de error al intentar cargar el archivo .csv, compruebe el formato del archivo.</span><span class="sxs-lookup"><span data-stu-id="1fa4c-127">If you get an error message while trying to upload the .csv file, check the format of the file.</span></span> <span data-ttu-id="1fa4c-128">Asegúrate de que el orden de columna coincida con lo que se describe en Usar perfiles de [Windows Autopilot](/partner-center/autopilot#add-devices-to-a-customers-account)en nuevos dispositivos para personalizar la experiencia de un cliente de forma personalizada.</span><span class="sxs-lookup"><span data-stu-id="1fa4c-128">Make sure the column order matches what is described in [Use Windows Autopilot profiles on new devices to customize a customer's out-of-box experience](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span> <span data-ttu-id="1fa4c-129">También puedes usar el archivo .csv de ejemplo proporcionado desde el vínculo junto a **Agregar dispositivos** para crear una lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1fa4c-129">You can also use the sample .csv file provided from the link next to **Add devices** to create a device list.</span></span> 

<span data-ttu-id="1fa4c-130">Para obtener más información acerca de Autopilot en escenarios de partners, vea [Agregar dispositivos a la cuenta de un cliente.](/partner-center/autopilot#add-devices-to-a-customers-account)</span><span class="sxs-lookup"><span data-stu-id="1fa4c-130">For more information about Autopilot in Partner scenarios, see [Add devices to a customer’s account](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span>


## <a name="register-devices-by-using-the-oem-api"></a><span data-ttu-id="1fa4c-131">Registrar dispositivos mediante la API oem</span><span class="sxs-lookup"><span data-stu-id="1fa4c-131">Register devices by using the OEM API</span></span>

<span data-ttu-id="1fa4c-132">Antes de completar el registro de un cliente, primero debe establecer una relación con ellos.</span><span class="sxs-lookup"><span data-stu-id="1fa4c-132">Before completing registration for a customer, you must first establish a relationship with them.</span></span> <span data-ttu-id="1fa4c-133">Debe tener un vínculo único para proporcionar a sus respectivos clientes.</span><span class="sxs-lookup"><span data-stu-id="1fa4c-133">You should have a unique link to provide to your respective customers.</span></span> <span data-ttu-id="1fa4c-134">Consulte [How to establish OEM relationship](/windows/deployment/windows-autopilot/registration-auth#oem-authorization).</span><span class="sxs-lookup"><span data-stu-id="1fa4c-134">See [How to establish OEM relationship](/windows/deployment/windows-autopilot/registration-auth#oem-authorization).</span></span>

<span data-ttu-id="1fa4c-135">Una vez establecida la relación, puede empezar a registrar dispositivos para clientes mediante la etiqueta **de grupo Microsoft365Managed_Autopilot**.</span><span class="sxs-lookup"><span data-stu-id="1fa4c-135">Once you've established the relationship, you can start registering devices for customers using the Group Tag **Microsoft365Managed_Autopilot**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1fa4c-136">El nombre del grupo debe coincidir **Microsoft365Managed_Autopilot** exactamente, incluida la mayúscula y los caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="1fa4c-136">The group name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="1fa4c-137">Esto permitirá que los dispositivos recién registrados se asignen con el perfil de Microsoft Managed Desktop Autopilot.</span><span class="sxs-lookup"><span data-stu-id="1fa4c-137">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>