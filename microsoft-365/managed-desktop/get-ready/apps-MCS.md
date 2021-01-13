---
title: Trabajar con los servicios de consultoría de Microsoft
description: preparación y pasos a seguir para trabajar con MCS para empaquetar las aplicaciones
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación, aplicaciones, MCS, empaquetado
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f8c4e427c536577ea2fc768d4930b9d4db6ac697
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841428"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="8ef6b-104">Trabajar con los servicios de consultoría de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ef6b-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="8ef6b-105">Puede interactuar con los Servicios de consultoría de Microsoft (MCS) para empaquetar las aplicaciones para su uso con escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8ef6b-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="8ef6b-106">Para obtener información exacta, trabaje con el representante de su cuenta para ponerse en contacto con MCS y el ámbito de su proyecto de empaquetado de aplicaciones específico.</span><span class="sxs-lookup"><span data-stu-id="8ef6b-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="8ef6b-107">Roles y responsabilidades</span><span class="sxs-lookup"><span data-stu-id="8ef6b-107">Roles and responsibilities</span></span>

<span data-ttu-id="8ef6b-108">Para trabajar con el empaquetado de aplicaciones de MCS, **debes proporcionar estos elementos:**</span><span class="sxs-lookup"><span data-stu-id="8ef6b-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="8ef6b-109">Los archivos del instalador de origen (por ejemplo, setup.exe o .msi).</span><span class="sxs-lookup"><span data-stu-id="8ef6b-109">The source installer files (for example, setup.exe or .msi).</span></span>
- <span data-ttu-id="8ef6b-110">Las instrucciones de instalación, especificando detalles sobre el aspecto de la instalación final.</span><span class="sxs-lookup"><span data-stu-id="8ef6b-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="8ef6b-111">Por ejemplo, ¿debería haber un acceso directo de escritorio a la aplicación?</span><span class="sxs-lookup"><span data-stu-id="8ef6b-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="8ef6b-112">¿Cuál debe ser la visibilidad de la aplicación?</span><span class="sxs-lookup"><span data-stu-id="8ef6b-112">What should the app's visibility be?</span></span> <span data-ttu-id="8ef6b-113">¿La aplicación debe conectarse a un servidor y, si es así, cuál?</span><span class="sxs-lookup"><span data-stu-id="8ef6b-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="8ef6b-114">Para obtener más información, consulte la [plantilla de solicitud de empaquetado de aplicaciones.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)</span><span class="sxs-lookup"><span data-stu-id="8ef6b-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="8ef6b-115">Debes realizar tus propias pruebas de aceptación para comprobar que la aplicación funciona según lo necesites en tu entorno.</span><span class="sxs-lookup"><span data-stu-id="8ef6b-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="8ef6b-116">**MCS se ocupará de estas acciones:**</span><span class="sxs-lookup"><span data-stu-id="8ef6b-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="8ef6b-117">Comprobar si la aplicación está prohibida o restringida en el entorno de Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8ef6b-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="8ef6b-118">Pruebas de instalación, inicio y desinstalación de la aplicación para garantizar la compatibilidad con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="8ef6b-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="8ef6b-119">Si MCS detecta un problema de compatibilidad, pasará la aplicación al programa [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) para su corrección.</span><span class="sxs-lookup"><span data-stu-id="8ef6b-119">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="8ef6b-120">Empaquetar la aplicación en la especificación y, a continuación, probar la implementación de la aplicación mediante Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="8ef6b-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="8ef6b-121">Programación de entrega de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="8ef6b-121">App delivery schedule</span></span>

<span data-ttu-id="8ef6b-122">Inicie el proceso de empaquetado cargando la información de la aplicación en el portal de Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8ef6b-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="8ef6b-123">El equipo de empaquetado revisa los nuevos envíos cada jueves.</span><span class="sxs-lookup"><span data-stu-id="8ef6b-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="8ef6b-124">Después de revisar y empaquetar, las aplicaciones empaquetadas se entregan el siguiente viernes.</span><span class="sxs-lookup"><span data-stu-id="8ef6b-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="8ef6b-125">Se pueden empaquetar hasta cinco aplicaciones por semana para que se inicien, pero el servicio se puede escalar para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="8ef6b-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![calendario que muestra la entrada de la aplicación un jueves (el día 21 en este ejemplo), validación multimedia al día siguiente, empaquetado el lunes siguiente (día 25) y entrega de la aplicación el viernes siguiente (el día 29)](../../media/MCS-cal.png)

<span data-ttu-id="8ef6b-127">Se te notificará una vez que se haya entregado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8ef6b-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="8ef6b-128">En ese momento, tiene 21 días para realizar pruebas de aceptación y aprobar el trabajo en el portal de Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8ef6b-128">At that point, you have 21 days to perform acceptance testing and approve the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="8ef6b-129">Si detecta algún problema con la aplicación durante las pruebas de aceptación, rechace la aplicación en el portal de Escritorio administrado de Microsoft y se le conectará por correo electrónico con un empaquetador de MCS para comprender y resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="8ef6b-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="8ef6b-130">Entorno y cuentas de prueba</span><span class="sxs-lookup"><span data-stu-id="8ef6b-130">Testing accounts and environment</span></span>

<span data-ttu-id="8ef6b-131">Para que el equipo de empaquetado complete la migración a Microsoft Intune, le recomendamos que proporcione ciertos permisos:</span><span class="sxs-lookup"><span data-stu-id="8ef6b-131">For the packaging team to complete the migration to Microsoft Intune, we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="8ef6b-132">Acceso a las funcionalidades de implementación de aplicaciones de Microsoft Intune para que el empaquetador agregue y asigne la aplicación</span><span class="sxs-lookup"><span data-stu-id="8ef6b-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="8ef6b-133">Grupos de prueba, cuentas de usuario y licencias para que los empaquetadores puedan probar las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="8ef6b-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="8ef6b-134">MCS usará esos permisos para realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="8ef6b-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="8ef6b-135">Asegurarse de que la aplicación funciona en una máquina virtual configurada para escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ef6b-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="8ef6b-136">Cargar la aplicación en Microsoft Intune para su implementación a los usuarios</span><span class="sxs-lookup"><span data-stu-id="8ef6b-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="8ef6b-137">Sin estos permisos, es posible que MCS avance, pero no podrán cargar las aplicaciones en su entorno.</span><span class="sxs-lookup"><span data-stu-id="8ef6b-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>


