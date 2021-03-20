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
ms.openlocfilehash: 04b0c7905c83be2afa46abcfb2d4bb5cd9735e06
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909231"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="5a728-104">Trabajar con los servicios de consultoría de Microsoft</span><span class="sxs-lookup"><span data-stu-id="5a728-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="5a728-105">Puedes interactuar con Microsoft Consulting Services (MCS) para empaquetar tus aplicaciones para usarlas con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="5a728-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="5a728-106">Para obtener detalles exactos, trabaje con el representante de la cuenta para ponerse en contacto con MCS y ámbito de su proyecto de empaquetado de aplicaciones específico.</span><span class="sxs-lookup"><span data-stu-id="5a728-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="5a728-107">Roles y responsabilidades</span><span class="sxs-lookup"><span data-stu-id="5a728-107">Roles and responsibilities</span></span>

<span data-ttu-id="5a728-108">Para trabajar con el empaquetado de la aplicación MCS, **debes proporcionar estos elementos:**</span><span class="sxs-lookup"><span data-stu-id="5a728-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="5a728-109">Los archivos del instalador de origen (por ejemplo, setup.exe o .msi).</span><span class="sxs-lookup"><span data-stu-id="5a728-109">The source installer files (for example, setup.exe or .msi).</span></span>
- <span data-ttu-id="5a728-110">Las instrucciones de instalación, especificando detalles sobre cómo debe ser la instalación final.</span><span class="sxs-lookup"><span data-stu-id="5a728-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="5a728-111">Por ejemplo, ¿debería haber un acceso directo de escritorio a la aplicación?</span><span class="sxs-lookup"><span data-stu-id="5a728-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="5a728-112">¿Cuál debe ser la visibilidad de la aplicación?</span><span class="sxs-lookup"><span data-stu-id="5a728-112">What should the app's visibility be?</span></span> <span data-ttu-id="5a728-113">¿La aplicación debe conectarse a un servidor y, si es así, cuál?</span><span class="sxs-lookup"><span data-stu-id="5a728-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="5a728-114">Para obtener más información, vea la [plantilla de solicitud de empaquetado de aplicaciones](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span><span class="sxs-lookup"><span data-stu-id="5a728-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="5a728-115">Debes realizar tus propias pruebas de aceptación para comprobar que la aplicación funciona según lo necesites en tu entorno.</span><span class="sxs-lookup"><span data-stu-id="5a728-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="5a728-116">**MCS se ocupará de estas acciones:**</span><span class="sxs-lookup"><span data-stu-id="5a728-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="5a728-117">Comprobar si la aplicación está prohibida o restringida en el entorno de Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5a728-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="5a728-118">Pruebas de instalación, inicio y desinstalación de la aplicación para garantizar la compatibilidad con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="5a728-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="5a728-119">Si MCS detecta un problema de compatibilidad, la entregarán al programa [Desktop App Assure](/fasttrack/win-10-desktop-app-assure) para su corrección.</span><span class="sxs-lookup"><span data-stu-id="5a728-119">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="5a728-120">Empaquetar la aplicación en la especificación y, a continuación, probar la implementación de aplicaciones mediante Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="5a728-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="5a728-121">Programación de entrega de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="5a728-121">App delivery schedule</span></span>

<span data-ttu-id="5a728-122">Inicie el proceso de empaquetado cargando la información de la aplicación en el portal de Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5a728-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="5a728-123">El equipo de empaquetado revisa los nuevos envíos cada jueves.</span><span class="sxs-lookup"><span data-stu-id="5a728-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="5a728-124">Después de revisar y empaquetar, las aplicaciones empaquetadas se entregan el viernes siguiente.</span><span class="sxs-lookup"><span data-stu-id="5a728-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="5a728-125">Se pueden empaquetar hasta cinco aplicaciones por semana para iniciarse, pero el servicio puede escalar para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="5a728-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![calendario que muestra la entrada de aplicaciones en un jueves (el día 21 en este ejemplo), validación de medios al día siguiente, empaquetado el lunes siguiente (día 25) y entrega de aplicaciones el viernes siguiente (el día 29)](../../media/MCS-cal.png)

<span data-ttu-id="5a728-127">Se te notificará una vez que se haya entregado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5a728-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="5a728-128">En ese momento, tiene 21 días para realizar pruebas de aceptación y aprobar el trabajo en el portal de Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5a728-128">At that point, you have 21 days to perform acceptance testing and approve the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="5a728-129">Si descubre algún problema con la aplicación durante las pruebas de aceptación, rechace la aplicación en el portal de Escritorio administrado de Microsoft y se conectará por correo electrónico con un empaquetador de MCS para comprender y resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="5a728-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="5a728-130">Probar cuentas y entorno</span><span class="sxs-lookup"><span data-stu-id="5a728-130">Testing accounts and environment</span></span>

<span data-ttu-id="5a728-131">Para que el equipo de empaquetado complete la migración a Microsoft Intune, se recomienda proporcionar ciertos permisos:</span><span class="sxs-lookup"><span data-stu-id="5a728-131">For the packaging team to complete the migration to Microsoft Intune, we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="5a728-132">Acceso a las funcionalidades de implementación de aplicaciones de Microsoft Intune para que el empaquetador agregue y asigne la aplicación</span><span class="sxs-lookup"><span data-stu-id="5a728-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="5a728-133">Grupos de prueba, cuentas de usuario y licencias para que los empaquetadores puedan probar las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="5a728-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="5a728-134">MCS usará esos permisos para realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="5a728-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="5a728-135">Asegurarse de que la aplicación funciona en una máquina virtual configurada para Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="5a728-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="5a728-136">Cargar la aplicación en Microsoft Intune para su implementación a los usuarios</span><span class="sxs-lookup"><span data-stu-id="5a728-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="5a728-137">Sin estos permisos, es posible que MCS avance, pero no podrán cargar las aplicaciones en el entorno.</span><span class="sxs-lookup"><span data-stu-id="5a728-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>