---
title: Trabajar con los servicios de consultoría de Microsoft
description: preparación y pasos a seguir para trabajar con MCS para empaquetar las aplicaciones
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentation, apps, MCS, Packaging
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d2a6c09e1bcb84885e607d133c14e26e08e3c621
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530168"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="ec37d-104">Trabajar con los servicios de consultoría de Microsoft</span><span class="sxs-lookup"><span data-stu-id="ec37d-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="ec37d-105">Puede participar con los servicios de consultoría de Microsoft (MCS) para empaquetar las aplicaciones para usarlas con el escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ec37d-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="ec37d-106">Para obtener detalles exactos, trabaje con su representante de cuenta para ponerse en contacto con MCS y alcance su proyecto de empaquetado de aplicaciones específico.</span><span class="sxs-lookup"><span data-stu-id="ec37d-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="ec37d-107">Roles y responsabilidades</span><span class="sxs-lookup"><span data-stu-id="ec37d-107">Roles and responsibilities</span></span>

<span data-ttu-id="ec37d-108">Para trabajar con el empaquetado de la aplicación de MCS, **debe proporcionar estos elementos**:</span><span class="sxs-lookup"><span data-stu-id="ec37d-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="ec37d-109">Los archivos del instalador de origen (por ejemplo, setup.exe o. msi).</span><span class="sxs-lookup"><span data-stu-id="ec37d-109">The source installer files (e.g., setup.exe or .msi).</span></span>
- <span data-ttu-id="ec37d-110">Las instrucciones de instalación, que especifican los detalles sobre el aspecto de la instalación final.</span><span class="sxs-lookup"><span data-stu-id="ec37d-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="ec37d-111">Por ejemplo, ¿debería haber un acceso directo de escritorio a la aplicación?</span><span class="sxs-lookup"><span data-stu-id="ec37d-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="ec37d-112">¿Qué debería tener la visibilidad de la aplicación?</span><span class="sxs-lookup"><span data-stu-id="ec37d-112">What should the app's visibility be?</span></span> <span data-ttu-id="ec37d-113">¿La aplicación debe conectarse a un servidor y, si es así, ¿cuál?</span><span class="sxs-lookup"><span data-stu-id="ec37d-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="ec37d-114">Para obtener más información, consulte la [plantilla solicitud de empaquetado de aplicaciones](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span><span class="sxs-lookup"><span data-stu-id="ec37d-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="ec37d-115">Debe realizar sus propias pruebas de aceptación para comprobar que la aplicación funciona según la necesite en su entorno.</span><span class="sxs-lookup"><span data-stu-id="ec37d-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="ec37d-116">**MCS se ocupará de estas acciones:**</span><span class="sxs-lookup"><span data-stu-id="ec37d-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="ec37d-117">Comprobar si la aplicación está prohibida o restringida en el entorno de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ec37d-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="ec37d-118">Probar la instalación, iniciar y desinstalar la aplicación para garantizar la compatibilidad con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ec37d-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="ec37d-119">Si MCS detecta un problema de compatibilidad, entregará la aplicación al programa de [aseguramiento](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) de la aplicación de escritorio para la corrección.</span><span class="sxs-lookup"><span data-stu-id="ec37d-119">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="ec37d-120">Empaquete la aplicación en la especificación y, a continuación, pruebe la implementación de aplicaciones con Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="ec37d-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="ec37d-121">Programación de entrega de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ec37d-121">App delivery schedule</span></span>

<span data-ttu-id="ec37d-122">Inicie el proceso de empaquetado cargando la información de la aplicación en el portal de escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ec37d-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="ec37d-123">El equipo de empaquetado revisa los nuevos envíos cada jueves.</span><span class="sxs-lookup"><span data-stu-id="ec37d-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="ec37d-124">Después de la revisión y el empaquetado, las aplicaciones empaquetadas se entregan el viernes siguiente.</span><span class="sxs-lookup"><span data-stu-id="ec37d-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="ec37d-125">Se pueden empaquetar hasta cinco aplicaciones por semana para comenzar, pero el servicio se puede escalar para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="ec37d-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![calendario que muestra la entrada de la aplicación en un jueves (el 21 de este ejemplo), validación de medios al día siguiente, empaquetado el lunes siguiente (el 25) y entrega de la aplicación en el viernes posterior (el 29)](../../media/MCS-cal.png)

<span data-ttu-id="ec37d-127">Recibirá una notificación una vez que se haya entregado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec37d-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="ec37d-128">En ese momento, dispone de 21 días para realizar las pruebas de aceptación y cerrar la sesión en el trabajo en el portal de escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ec37d-128">At that point, you have 21 days to perform acceptance testing and sign off on the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="ec37d-129">Si detecta algún problema con la aplicación durante las pruebas de aceptación, rechace la aplicación en el portal de escritorio administrado de Microsoft y se conectará a través del correo electrónico con un empaquetador de MCS para comprender y resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="ec37d-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="ec37d-130">Pruebas de entorno y cuentas</span><span class="sxs-lookup"><span data-stu-id="ec37d-130">Testing accounts and environment</span></span>

<span data-ttu-id="ec37d-131">Para que el equipo de empaquetado complete la migración a Microsoft Intune, le recomendamos que proporcione determinados permisos:</span><span class="sxs-lookup"><span data-stu-id="ec37d-131">For the packaging team to complete the migration to Microsoft Intune we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="ec37d-132">Acceso a las funcionalidades de implementación de aplicaciones de Microsoft Intune para que el empaquetador agregue y asigne la aplicación</span><span class="sxs-lookup"><span data-stu-id="ec37d-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="ec37d-133">Grupos de prueba, cuentas de usuario y licencias de los paquetes para poder probar las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ec37d-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="ec37d-134">MCS usará esos permisos para realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="ec37d-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="ec37d-135">Asegurarse de que la aplicación funciona en una máquina virtual configurada para el escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="ec37d-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="ec37d-136">Carga de la aplicación en Microsoft Intune para su implementación a los usuarios</span><span class="sxs-lookup"><span data-stu-id="ec37d-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="ec37d-137">Sin estos permisos, es posible que MCS se mueva hacia delante, pero no podrá cargar las aplicaciones en su entorno.</span><span class="sxs-lookup"><span data-stu-id="ec37d-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>


