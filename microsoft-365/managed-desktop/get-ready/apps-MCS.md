---
title: Trabajar con los servicios de consultoría de Microsoft
description: preparación y pasos a seguir para trabajar con MCS para empaquetar las aplicaciones
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentation, apps, MCS, Packaging
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 3687966fd49db3fd58c4ecbb3917e45ec6dfa3c3
ms.sourcegitcommit: b9663acecf0bfdca2486818ec7e08a6f882d0dc9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "35425743"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="dd0ee-104">Trabajar con los servicios de consultoría de Microsoft</span><span class="sxs-lookup"><span data-stu-id="dd0ee-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="dd0ee-105">Puede participar con los servicios de consultoría de Microsoft (MCS) para empaquetar las aplicaciones para usarlas con el escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dd0ee-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="dd0ee-106">Para obtener detalles exactos, trabaje con su representante de cuenta para ponerse en contacto con MCS y alcance su proyecto de empaquetado de aplicaciones específico.</span><span class="sxs-lookup"><span data-stu-id="dd0ee-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="dd0ee-107">Roles y responsabilidades</span><span class="sxs-lookup"><span data-stu-id="dd0ee-107">Roles and responsibilities</span></span>

<span data-ttu-id="dd0ee-108">Para trabajar con el empaquetado de la aplicación de MCS, **debe proporcionar estos elementos**:</span><span class="sxs-lookup"><span data-stu-id="dd0ee-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="dd0ee-109">Los archivos del instalador de origen (por ejemplo, setup. exe o. msi).</span><span class="sxs-lookup"><span data-stu-id="dd0ee-109">The source installer files (e.g., setup.exe or .msi).</span></span>
- <span data-ttu-id="dd0ee-110">Las instrucciones de instalación, que especifican los detalles sobre el aspecto de la instalación final.</span><span class="sxs-lookup"><span data-stu-id="dd0ee-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="dd0ee-111">Por ejemplo, ¿debería haber un acceso directo de escritorio a la aplicación?</span><span class="sxs-lookup"><span data-stu-id="dd0ee-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="dd0ee-112">¿Qué debería tener la visibilidad de la aplicación?</span><span class="sxs-lookup"><span data-stu-id="dd0ee-112">What should the app's visibility be?</span></span> <span data-ttu-id="dd0ee-113">¿La aplicación debe conectarse a un servidor y, si es así, ¿cuál?</span><span class="sxs-lookup"><span data-stu-id="dd0ee-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="dd0ee-114">Para obtener más información, consulte la [plantilla solicitud de empaquetado de aplicaciones](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span><span class="sxs-lookup"><span data-stu-id="dd0ee-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="dd0ee-115">Debe realizar sus propias pruebas de aceptación para comprobar que la aplicación funciona según la necesite en su entorno.</span><span class="sxs-lookup"><span data-stu-id="dd0ee-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="dd0ee-116">**MCS se ocupará de estas acciones:**</span><span class="sxs-lookup"><span data-stu-id="dd0ee-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="dd0ee-117">Comprobar si la aplicación está prohibida o restringida en el entorno de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dd0ee-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="dd0ee-118">Probar la instalación, iniciar y desinstalar la aplicación para garantizar la compatibilidad con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="dd0ee-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="dd0ee-119">Si MCS detecta un problema de compatibilidad, entregará la aplicación al programa de aseguramiento de la [aplicación de escritorio](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) para la corrección.</span><span class="sxs-lookup"><span data-stu-id="dd0ee-119">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="dd0ee-120">Empaquete la aplicación en la especificación y, a continuación, pruebe la implementación de aplicaciones con Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="dd0ee-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="dd0ee-121">Programación de entrega de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="dd0ee-121">App delivery schedule</span></span>

<span data-ttu-id="dd0ee-122">Inicie el proceso de empaquetado cargando la información de la aplicación en el portal de escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dd0ee-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="dd0ee-123">El equipo de empaquetado revisa los nuevos envíos cada jueves.</span><span class="sxs-lookup"><span data-stu-id="dd0ee-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="dd0ee-124">Después de la revisión y el empaquetado, las aplicaciones empaquetadas se entregan el viernes siguiente.</span><span class="sxs-lookup"><span data-stu-id="dd0ee-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="dd0ee-125">Se pueden empaquetar hasta cinco aplicaciones por semana para comenzar, pero el servicio se puede escalar para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="dd0ee-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![calendario que muestra la revisión de la aplicación, el empaquetado y las fechas de entrega](images/MCS-cal.png)

<span data-ttu-id="dd0ee-127">Recibirá una notificación una vez que se haya entregado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dd0ee-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="dd0ee-128">En ese momento, dispone de 21 días para realizar las pruebas de aceptación y cerrar la sesión en el trabajo en el portal de escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dd0ee-128">At that point, you have 21 days to perform acceptance testing and sign off on the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="dd0ee-129">Si detecta algún problema con la aplicación durante las pruebas de aceptación, rechace la aplicación en el portal de escritorio administrado de Microsoft y se conectará a través del correo electrónico con un empaquetador de MCS para comprender y resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="dd0ee-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="dd0ee-130">Pruebas de entorno y cuentas</span><span class="sxs-lookup"><span data-stu-id="dd0ee-130">Testing accounts and environment</span></span>

<span data-ttu-id="dd0ee-131">Para que el equipo de empaquetado complete la migración a Microsoft Intune, le recomendamos que proporcione determinados permisos:</span><span class="sxs-lookup"><span data-stu-id="dd0ee-131">For the packaging team to complete the migration to Microsoft Intune we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="dd0ee-132">Acceso a las funcionalidades de implementación de aplicaciones de Microsoft Intune para que el empaquetador agregue y asigne la aplicación</span><span class="sxs-lookup"><span data-stu-id="dd0ee-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="dd0ee-133">Grupos de prueba, cuentas de usuario y licencias de los paquetes para poder probar las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="dd0ee-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="dd0ee-134">MCS usará esos permisos para realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="dd0ee-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="dd0ee-135">Asegurarse de que la aplicación funciona en una máquina virtual configurada para el escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="dd0ee-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="dd0ee-136">Carga de la aplicación en Microsoft Intune para su implementación a los usuarios</span><span class="sxs-lookup"><span data-stu-id="dd0ee-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="dd0ee-137">Sin estos permisos, es posible que MCS se mueva hacia delante, pero no podrá cargar las aplicaciones en su entorno.</span><span class="sxs-lookup"><span data-stu-id="dd0ee-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>


