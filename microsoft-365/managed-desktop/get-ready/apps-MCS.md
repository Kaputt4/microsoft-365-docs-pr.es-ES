---
title: Trabajar con los servicios de consultoría de Microsoft
description: preparación y pasos a seguir para trabajar con MCS para empaquetar las aplicaciones
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentation, apps, MCS, Packaging
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 39a5102d045d9ed79b631a3b477bd1c72dea76de
ms.sourcegitcommit: 498340389e1c34f49f0b2da382c23c8d5334ae47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2019
ms.locfileid: "34918741"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="79220-104">Trabajar con los servicios de consultoría de Microsoft</span><span class="sxs-lookup"><span data-stu-id="79220-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="79220-105">Puede participar con los servicios de consultoría de Microsoft (MCS) para empaquetar las aplicaciones para usarlas con el escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="79220-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="79220-106">Para obtener detalles exactos, trabaje con su representante de cuenta para ponerse en contacto con MCS y alcance su proyecto de empaquetado de aplicaciones específico.</span><span class="sxs-lookup"><span data-stu-id="79220-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="79220-107">Roles y responsabilidades</span><span class="sxs-lookup"><span data-stu-id="79220-107">Roles and responsibilities</span></span>

<span data-ttu-id="79220-108">Para trabajar con el empaquetado de la aplicación de MCS, **debe proporcionar estos elementos**:</span><span class="sxs-lookup"><span data-stu-id="79220-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="79220-109">Los archivos del instalador de origen (por ejemplo, setup. exe o. msi).</span><span class="sxs-lookup"><span data-stu-id="79220-109">The source installer files (e.g., setup.exe or .msi).</span></span>
- <span data-ttu-id="79220-110">Las instrucciones de instalación, que especifican los detalles sobre el aspecto de la instalación final.</span><span class="sxs-lookup"><span data-stu-id="79220-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="79220-111">Por ejemplo, ¿debería haber un acceso directo de escritorio a la aplicación?</span><span class="sxs-lookup"><span data-stu-id="79220-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="79220-112">¿Qué debería tener la visibilidad de la aplicación?</span><span class="sxs-lookup"><span data-stu-id="79220-112">What should the app's visibility be?</span></span> <span data-ttu-id="79220-113">¿La aplicación debe conectarse a un servidor y, si es así, ¿cuál?</span><span class="sxs-lookup"><span data-stu-id="79220-113">Should the app connect to a server and if so, which one?</span></span> <!--For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx). -->
- <span data-ttu-id="79220-114">Debe realizar sus propias pruebas de aceptación para comprobar que la aplicación funciona según la necesite en su entorno.</span><span class="sxs-lookup"><span data-stu-id="79220-114">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="79220-115">**MCS se ocupará de estas acciones:**</span><span class="sxs-lookup"><span data-stu-id="79220-115">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="79220-116">Comprobar si la aplicación está prohibida o restringida en el entorno de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="79220-116">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="79220-117">Probar la instalación, iniciar y desinstalar la aplicación para garantizar la compatibilidad con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="79220-117">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="79220-118">Si MCS detecta un problema de compatibilidad, entregará la aplicación al programa de aseguramiento de la [aplicación de escritorio](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) para la corrección.</span><span class="sxs-lookup"><span data-stu-id="79220-118">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="79220-119">Empaquete la aplicación en la especificación y, a continuación, pruebe la implementación de aplicaciones con Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="79220-119">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="79220-120">Programación de entrega de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="79220-120">App delivery schedule</span></span>

<span data-ttu-id="79220-121">Inicie el proceso de empaquetado cargando la información de la aplicación en el portal de escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="79220-121">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="79220-122">El equipo de empaquetado revisa los nuevos envíos cada jueves.</span><span class="sxs-lookup"><span data-stu-id="79220-122">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="79220-123">Después de la revisión y el empaquetado, las aplicaciones empaquetadas se entregan el viernes siguiente.</span><span class="sxs-lookup"><span data-stu-id="79220-123">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="79220-124">Se pueden empaquetar hasta cinco aplicaciones por semana para comenzar, pero el servicio se puede escalar para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="79220-124">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![calendario que muestra la revisión de la aplicación, el empaquetado y las fechas de entrega](images/MCS-cal.png)

<span data-ttu-id="79220-126">Recibirá una notificación una vez que se haya entregado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="79220-126">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="79220-127">En ese momento, dispone de 21 días para realizar las pruebas de aceptación y cerrar la sesión en el trabajo en el portal de escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="79220-127">At that point, you have 21 days to perform acceptance testing and sign off on the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="79220-128">Si detecta algún problema con la aplicación durante las pruebas de aceptación, rechace la aplicación en el portal de escritorio administrado de Microsoft y se conectará a través del correo electrónico con un empaquetador de MCS para comprender y resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="79220-128">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="79220-129">Pruebas de entorno y cuentas</span><span class="sxs-lookup"><span data-stu-id="79220-129">Testing accounts and environment</span></span>

<span data-ttu-id="79220-130">Para que el equipo de empaquetado complete la migración a Microsoft Intune, le recomendamos que proporcione determinados permisos:</span><span class="sxs-lookup"><span data-stu-id="79220-130">For the packaging team to complete the migration to Microsoft Intune we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="79220-131">Acceso a las funcionalidades de implementación de aplicaciones de Microsoft Intune para que el empaquetador agregue y asigne la aplicación</span><span class="sxs-lookup"><span data-stu-id="79220-131">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="79220-132">Grupos de prueba, cuentas de usuario y licencias de los paquetes para poder probar las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="79220-132">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="79220-133">MCS usará esos permisos para realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="79220-133">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="79220-134">Asegurarse de que la aplicación funciona en una máquina virtual configurada para el escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="79220-134">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="79220-135">Carga de la aplicación en Microsoft Intune para su implementación a los usuarios</span><span class="sxs-lookup"><span data-stu-id="79220-135">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="79220-136">Sin estos permisos, es posible que MCS se mueva hacia delante, pero no podrá cargar las aplicaciones en su entorno.</span><span class="sxs-lookup"><span data-stu-id="79220-136">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>


