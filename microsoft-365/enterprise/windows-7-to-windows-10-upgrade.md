---
title: Guía de actualización de Windows 7 a Windows 10
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 06/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Actualización de Windows 7 a Windows 10
ms.openlocfilehash: aaa1ce39e63aebeb3c2ab6678b3c1ade6791ab22
ms.sourcegitcommit: 7e806db3d44ec223754efe1e9613b2c7117c4788
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2019
ms.locfileid: "34821044"
---
# <a name="windows-7-to-windows-10-manual-upgrade-step-by-step-guide"></a><span data-ttu-id="d768c-103">Guía paso a paso de actualización manual de Windows 7 a Windows 10</span><span class="sxs-lookup"><span data-stu-id="d768c-103">Windows 7 to Windows 10 manual upgrade step-by-step guide</span></span>

<span data-ttu-id="d768c-104">Este artículo describe el proceso para actualizar de forma manual un equipo con Windows 7 Enterprise a Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d768c-104">This article describes the process to manually upgrade a Windows 7 Enterprise PC to Windows 10 Enterprise.</span></span> <span data-ttu-id="d768c-105">Para otras ediciones de Windows 7, como Home y Professional, el proceso es muy similar, pero también tiene la opción de actualizar directamente con la herramienta de creación de medios.</span><span class="sxs-lookup"><span data-stu-id="d768c-105">For other Windows 7 editions, such as Home and Professional, the process is very similar, but you also have the option to upgrade directly using the media creation tool.</span></span> <span data-ttu-id="d768c-106">Las actualizaciones de cualquier edición de Windows 7 a Windows 10 necesitarán una clave de producto válida y solo se podrán actualizar al mismo tipo de edición o a una edición superior de Windows. A modo de ejemplo, Windows 7 Professional se puede actualizar a Windows 10 Pro, pero no se puede actualizar a Windows 10 Home.</span><span class="sxs-lookup"><span data-stu-id="d768c-106">Upgrades for any edition of Windows 7 to Windows 10 will require a valid product key and matching or higher edition of Windows, for example Windows 7 Professional can upgrade to Windows 10 Pro, but cannot be upgraded to Windows 10 Home.</span></span> <span data-ttu-id="d768c-107">Windows 7 Ultimate se tendrá que actualizar a Windows 10 Pro.</span><span class="sxs-lookup"><span data-stu-id="d768c-107">Windows 7 Ultimate will need to be upgraded to Windows 10 Pro.</span></span>

## <a name="windows-10-upgrades-using-the-media-creation-tool-or-iso-files"></a><span data-ttu-id="d768c-108">Actualizaciones de Windows 10 con la herramienta de creación multimedia o con archivos ISO</span><span class="sxs-lookup"><span data-stu-id="d768c-108">Windows 10 upgrades using the media creation tool or ISO files</span></span>

<span data-ttu-id="d768c-109">Puede actualizar a Windows 10 directamente con la [herramienta de creación multimedia](https://www.microsoft.com/en-us/software-download/windows10ISO) o utilizarla para descargar Windows 10 como archivo ISO.</span><span class="sxs-lookup"><span data-stu-id="d768c-109">You can upgrade to Windows 10 directly using the [media creation tool](https://www.microsoft.com/en-us/software-download/windows10ISO) or use the it to download Windows 10 as an ISO file.</span></span> <span data-ttu-id="d768c-110">Tendrá que saber si su sistema operativo es 32 o 64 bits, el idioma predeterminado de su sistema y la edición de Windows 7 (por ejemplo, Home, Professional o Enterprise).</span><span class="sxs-lookup"><span data-stu-id="d768c-110">You’ll need to note whether your current system is 32 or 64-bit, your system’s default language and edition of Windows 7 (e.g. Home, Professional, or Enterprise).</span></span> <span data-ttu-id="d768c-111">En Windows 7, esta información se encuentra en Panel de control \> Sistema y seguridad \> Sistema.</span><span class="sxs-lookup"><span data-stu-id="d768c-111">In Windows 7, this information is located in the Control Panel \> System and Security \> System.</span></span> <span data-ttu-id="d768c-112">La herramienta de creación multimedia no es compatible con Windows 10 Enterprise para actualizaciones, creación de discos de instalación o descarga archivos ISO.</span><span class="sxs-lookup"><span data-stu-id="d768c-112">The media creation tool does not support Windows 10 Enterprise for upgrades, creating installation media or downloading ISO files.</span></span> <span data-ttu-id="d768c-113">Si actualiza desde Windows 7 Enterprise, necesitará Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d768c-113">Windows 10 Enterprise is required if you are upgrading from Windows 7 Enterprise.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-1.png)

> <span data-ttu-id="d768c-114">Opciones de la herramienta de creación multimedia de Windows 10</span><span class="sxs-lookup"><span data-stu-id="d768c-114">Windows 10 media creation tool options</span></span>

<span data-ttu-id="d768c-115">Al actualizar de Windows 7 Enterprise a Windows 10 Enterprise, debe descargar el archivo ISO correspondiente a su idioma y arquitectura (32 bits o 64 bits) desde el Centro de servicios de licencias por volumen](https://www.microsoft.com/licensing/servicecenter/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="d768c-115">When upgrading from Windows 7 Enterprise to Windows 10 Enterprise, you’ll need to download the ISO file for your language and architecture (32-bit or 64-bit) from the [Volume Licensing Service Center](https://www.microsoft.com/licensing/servicecenter/default.aspx).</span></span>

<span data-ttu-id="d768c-116">Si tiene previsto realizar la actualización con un archivo ISO, tendrá que extraer los archivos del ISO en el sistema de archivos local o en una unidad extraíble, o simplemente grabar el archivo ISO en un DVD.</span><span class="sxs-lookup"><span data-stu-id="d768c-116">If you plan to perform the upgrade using an ISO file, you will need to extract the files within the ISO to either your local file system, to a removable drive, or you can burn the ISO file to a DVD.</span></span> <span data-ttu-id="d768c-117">Los archivos de instalación pueden extraerse en la propia ISO con un equipo con Windows 8 o posterior y guardar estos archivos en una memoria USB extraíble o usar una aplicación como [7zip](https://www.7-zip.org/) para extraer el contenido del archivo ISO en una carpeta de la unidad local en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="d768c-117">You can extract the installation files within the ISO using a Windows 8 or newer PC and save these files to removable USB storage or use an application such as [7zip](https://www.7-zip.org/) to extract the contents of your ISO file to a folder on your local drive within Windows 7.</span></span>

<span data-ttu-id="d768c-118">Una vez que tenga disponibles los medios de instalación en Windows 7, puede iniciar la actualización ejecutando setup.exe como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="d768c-118">Once you have the install media available in Windows 7, you can initiate the upgrade by running setup.exe as shown below.</span></span>

<span data-ttu-id="d768c-119">**Sugerencia importante: para una actualización local en la que quiera migrar sus aplicaciones y datos a Windows 10, tendrá que iniciar el proceso desde una sesión de Windows 7 en ejecución. Arrancar la instalación desde un DVD o memoria USB no le ofrece la opción de mantener sus aplicaciones y archivos, sino que realiza una instalación limpia de Windows 10.**</span><span class="sxs-lookup"><span data-stu-id="d768c-119">**Important tip: For an in-place upgrade where applications and your data are migrated to Window 10, you’ll need to initiate the process from within a running Windows 7 session. Booting to install media from a DVD or USB drive will not give you the option to keep your apps and files, instead it will perform a clean install of Windows 10.**</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-2.png)

> <span data-ttu-id="d768c-120">Archivos extraídos de una ISO de Windows 10 Enterprise 32</span><span class="sxs-lookup"><span data-stu-id="d768c-120">Extracted files from a Windows 10 Enterprise 32-bit ISO</span></span>

<span data-ttu-id="d768c-121">Durante la configuración de Windows 10, se le guiará por el proceso de instalación. La primera pantalla ofrece la opción de descargar actualizaciones, controladores y características opcionales.</span><span class="sxs-lookup"><span data-stu-id="d768c-121">Within Windows 10 Setup, you will be guided through the installation process and the first screen provides an option to download updates, drivers and optional features.</span></span> <span data-ttu-id="d768c-122">Le recomendamos hacerlo para garantizar el éxito de la actualización.</span><span class="sxs-lookup"><span data-stu-id="d768c-122">This is recommended to help ensure success with the upgrade</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-3.png)

> <span data-ttu-id="d768c-123">Pantalla inicial de instalación de Windows 10</span><span class="sxs-lookup"><span data-stu-id="d768c-123">Initial Windows 10 Setup screen</span></span>

<span data-ttu-id="d768c-124">Cuando se hayan aplicado las actualizaciones, el programa de instalación de Windows 10 pasará a la siguiente fase, la selección de imagen.</span><span class="sxs-lookup"><span data-stu-id="d768c-124">Once updates have been applied, Windows 10 Setup will move to the next phase, Select Image.</span></span> <span data-ttu-id="d768c-125">Aquí, tendrá que seleccionar su edición de Windows.</span><span class="sxs-lookup"><span data-stu-id="d768c-125">Here, you will need to select your edition of Windows.</span></span> <span data-ttu-id="d768c-126">En este caso, dado que el PC tiene Windows 7 Enterprise instalado, seleccionaría Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d768c-126">In this case, since the PC has Windows 7 Enterprise installed, you would select Windows 10 Enterprise.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-4.png)

> <span data-ttu-id="d768c-127">Pantalla de selección de imagen de Windows 10 Enterprise de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="d768c-127">Windows 10 Enterprise 32-bit image selection screen</span></span>

<span data-ttu-id="d768c-128">En la siguiente pantalla de la configuración de Windows 10, se le mostrarán los términos de licencia y avisos aplicables.</span><span class="sxs-lookup"><span data-stu-id="d768c-128">In the next screen in Windows 10 Setup, you’re presented with applicable notices and license terms.</span></span> <span data-ttu-id="d768c-129">Cuando termine de leer y haya comprendido los avisos y los términos, haga clic en "Aceptar" para continuar o en "Rechazar" para cancelar.</span><span class="sxs-lookup"><span data-stu-id="d768c-129">Once you have read and understand the notices and terms, click “Accept” to continue or “Decline” to cancel.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-5.png)

<span data-ttu-id="d768c-130">*Avisos aplicables y términos de licencia de Windows 10*</span><span class="sxs-lookup"><span data-stu-id="d768c-130">*Windows 10 Applicable notices and license terms*</span></span>

<span data-ttu-id="d768c-131">Ahora, el programa de instalación de Windows 10 buscará actualizaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="d768c-131">Now Windows 10 Setup will look for additional updates.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-6.png)

<span data-ttu-id="d768c-132">*El programa de instalación está obteniendo actualizaciones de Windows 10*</span><span class="sxs-lookup"><span data-stu-id="d768c-132">*Windows 10 Setup getting updates*</span></span>

<span data-ttu-id="d768c-133">Cuando termine, el programa de instalación de Windows 10 estará listo para su instalación. De forma predeterminada, se configurará para instalar Windows 10 y conservar los archivos y las aplicaciones personales de la edición anterior de Windows.</span><span class="sxs-lookup"><span data-stu-id="d768c-133">Once complete, Windows 10 Setup is ready to install and by default is configured to install Windows 10 and keep your personal files and apps installed.</span></span> <span data-ttu-id="d768c-134">Esta opción es la recomendada.</span><span class="sxs-lookup"><span data-stu-id="d768c-134">This is the recommended option.</span></span> <span data-ttu-id="d768c-135">Al hacer clic en «Cambiar los elementos que se van a conservar», encontrará opciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="d768c-135">By clicking, “Change what to keep,” you’ll find additional options.</span></span> <span data-ttu-id="d768c-136">En caso contrario, haga clic en «Instalar».</span><span class="sxs-lookup"><span data-stu-id="d768c-136">Otherwise, click “Install.”</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-7.png)

<span data-ttu-id="d768c-137">*Opción predeterminada de actualización de la configuración de Windows 10*</span><span class="sxs-lookup"><span data-stu-id="d768c-137">*Windows 10 Setup upgrade option default*</span></span>

<span data-ttu-id="d768c-138">Si selecciona "Cambiar los elementos que se van a conservar", se le mostrarán estas opciones:</span><span class="sxs-lookup"><span data-stu-id="d768c-138">If you select “Change what to keep”, you’ll be presented with these options:</span></span>

<span data-ttu-id="d768c-139">«Conservar solo los archivos personales» no migrará las aplicaciones instaladas ni las configuraciones de Windows 7 a Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d768c-139">“Keep personal files only” will not move your installed apps or settings from Windows 7 to Windows 10.</span></span> <span data-ttu-id="d768c-140">Simplemente migrará los archivos y las cuentas de usuario a Windows.</span><span class="sxs-lookup"><span data-stu-id="d768c-140">Instead it will only move your files and user accounts to Windows.</span></span> <span data-ttu-id="d768c-141">Si elige esta opción, tendrá que reinstalar las aplicaciones más adelante.</span><span class="sxs-lookup"><span data-stu-id="d768c-141">Apps will need to be reinstalled later with this option.</span></span> <span data-ttu-id="d768c-142">Use esta opción solo si está seguro de poder volver a instalar y configurar las aplicaciones que necesite después de instalar Windows. De lo contrario, deje la opción predeterminada: «Conserva los archivos personales y las aplicaciones».</span><span class="sxs-lookup"><span data-stu-id="d768c-142">Only use this option if you are confident you can reinstall and configure the apps you will need after Windows is installed, otherwise stick with the default “Keep personal files and apps” option.</span></span>

<span data-ttu-id="d768c-143">Si selecciona «Nada», se eliminarán sus archivos, aplicaciones y configuraciones, y realizará una instalación limpia de Windows.</span><span class="sxs-lookup"><span data-stu-id="d768c-143">“Nothing” will delete your files, apps and settings and perform a clean install of Windows.</span></span> <span data-ttu-id="d768c-144">Use solo esta opción si ha hecho una copia de seguridad de los datos que desea mantener y puede volver a instalar las aplicaciones que necesite.</span><span class="sxs-lookup"><span data-stu-id="d768c-144">Use this option only if you have previously backed up the data you want to keep and you are able to reinstall your apps.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-8.png)

<span data-ttu-id="d768c-145">*Opciones de instalación de Windows 10*</span><span class="sxs-lookup"><span data-stu-id="d768c-145">*Windows 10 Setup installation options*</span></span>

<span data-ttu-id="d768c-146">Ahora, el programa de instalación de Windows 10 obtendrá las actualizaciones en función de lo que haya seleccionado en la pantalla anterior.</span><span class="sxs-lookup"><span data-stu-id="d768c-146">Now Windows 10 Setup will get updates again based on what you selected in the previous screen.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-9.png)

<span data-ttu-id="d768c-147">*El programa de instalación está obteniendo actualizaciones de Windows 10*</span><span class="sxs-lookup"><span data-stu-id="d768c-147">*Windows 10 Setup getting updates*</span></span>

<span data-ttu-id="d768c-148">Ahora, se procederá a instalar Windows 10 durante varios minutos y, si eligió conservar sus archivos personales y aplicaciones, tendrá sus archivos y aplicaciones en las mismas ubicaciones que antes.</span><span class="sxs-lookup"><span data-stu-id="d768c-148">Now Windows 10 will install for several minutes and if you chose to keep your personal files and apps, everything will be in the same file locations and your apps will now be available in Windows 10.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-10.png)

<span data-ttu-id="d768c-149">*Progreso de la instalación de Windows 10*</span><span class="sxs-lookup"><span data-stu-id="d768c-149">*Windows 10 installation progress*</span></span>

## 

## <a name="recovery-in-windows-10"></a><span data-ttu-id="d768c-150">Recuperación de Windows 10</span><span class="sxs-lookup"><span data-stu-id="d768c-150">Recovery in Windows 10</span></span>

<span data-ttu-id="d768c-151">Después de instalar Windows 10, la opción de Recuperación en Windows 10 le ofrece hasta 10 días para volver a Windows 7.</span><span class="sxs-lookup"><span data-stu-id="d768c-151">After Windows 10 is installed, the Recovery option in Windows 10 gives you up to 10 days to go back to Windows 7.</span></span> <span data-ttu-id="d768c-152">Esto es útil si un dispositivo o una aplicación en el sistema no funciona correctamente y necesita volver a la instalación anterior de Windows 7.</span><span class="sxs-lookup"><span data-stu-id="d768c-152">This is useful if a device or app on your system does not function properly and you need to go back to your previous Windows 7 installation.</span></span> <span data-ttu-id="d768c-153">Después de 10 días, Windows 10 eliminará del disco duro los archivos de recuperación de Windows 7 y los archivos de la instalación anterior.</span><span class="sxs-lookup"><span data-stu-id="d768c-153">After 10 days, by default Windows 10 will free up the space consumed by your Windows 7 recovery files on your hard drive and delete files from the previous installation.</span></span> <span data-ttu-id="d768c-154">Aunque Windows 7 se eliminará en este momento y ya no podrá volver a la instalación anterior de Windows 7, las aplicaciones y los archivos personales permanecerán en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d768c-154">Although Windows 7 after this time is deleted and you won’t be able to revert Windows 7, your apps and personal files will remain in Windows 10.</span></span>

<span data-ttu-id="d768c-155">Para iniciar el proceso vaya a Volver a Windows 7, desplácese hasta Configuración \> Actualización y Seguridad \> Recuperación.</span><span class="sxs-lookup"><span data-stu-id="d768c-155">To start the Go back to Windows 7 process, navigate to Settings \> Update & Security \> Recovery.</span></span> <span data-ttu-id="d768c-156">Bajo Volver a Windows 7, seleccione «Comenzar».</span><span class="sxs-lookup"><span data-stu-id="d768c-156">Under Go back to Windows 7, select “Get started.”</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-11.png)

<span data-ttu-id="d768c-157">*Opciones de Recuperación de Windows 10*</span><span class="sxs-lookup"><span data-stu-id="d768c-157">*Windows 10 Recovery options*</span></span>

<span data-ttu-id="d768c-158">En este momento, Windows 10 le preguntará por qué quiere volver a Windows 7.</span><span class="sxs-lookup"><span data-stu-id="d768c-158">Now, Windows 10 will ask why you are going back.</span></span> <span data-ttu-id="d768c-159">Si es por algún motivo técnico, nos ayudaría que rellene este espacio para que otras personas puedan beneficiarse de su experiencia.</span><span class="sxs-lookup"><span data-stu-id="d768c-159">If there is a technical reason, this is useful to fill out in order to help drive resolution and ensure others can benefit from your experience.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-12.png)

<span data-ttu-id="d768c-160">*Windows 10 le pregunta por qué quiere volver a Windows 7*</span><span class="sxs-lookup"><span data-stu-id="d768c-160">*Windows 10 asking why you are going back to Windows 7*</span></span>

<span data-ttu-id="d768c-161">En muchos casos, su versión de Windows 10 ofrecerá actualizaciones que puedan resolver problemas técnicos.</span><span class="sxs-lookup"><span data-stu-id="d768c-161">In many cases, your version of Windows 10 will have had updates issued, which may resolve technical issues.</span></span> <span data-ttu-id="d768c-162">Se recomienda que compruebe si hay actualizaciones y que, si las hay y se instalan, a continuación compruebe si resuelven los problemas que sufría.</span><span class="sxs-lookup"><span data-stu-id="d768c-162">It is encouraged that you check for updates and if found and installed, then check if that fixes the problems you have experienced.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-13.png)

<span data-ttu-id="d768c-163">*Comprobación de actualizaciones de Recuperación de Windows 10*</span><span class="sxs-lookup"><span data-stu-id="d768c-163">*Windows 10 Recovery check for updates*</span></span>

<span data-ttu-id="d768c-164">Si las actualizaciones no solucionan problemas y necesita revertir a la instalación anterior de Windows 7, puede que algunas aplicaciones deban reinstalarse (como cualquier aplicación que se haya instalado durante el tiempo en que se ejecute Windows 10), y algunas configuraciones pueden perderse.</span><span class="sxs-lookup"><span data-stu-id="d768c-164">If the updates do not resolve issues and you do need to revert to your previous installation of Windows 7, there is a chance that some apps will need to be reinstalled – such as any app that installed during the time you were running Windows 10 – and some settings may be lost.</span></span> <span data-ttu-id="d768c-165">Es importante resaltar que los archivos y los documentos que haya guardado localmente mientras usa Windows 10 se conservarán y estarán disponibles para usted una vez que vuelva a Windows 7.</span><span class="sxs-lookup"><span data-stu-id="d768c-165">Importantly, files and docs you’ve saved locally while using Windows 10 will remain and be available for you once you’re back in Windows 7.</span></span> 

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-14.png)

<span data-ttu-id="d768c-166">*Recuperación de Windows 10: lo que debe conocer*</span><span class="sxs-lookup"><span data-stu-id="d768c-166">*Windows 10 Recovery: What you need to know*</span></span>

<span data-ttu-id="d768c-167">Antes de empezar, asegúrese de tener listas una cuenta local o de dominio y una contraseña de la instalación anterior de Windows 7.</span><span class="sxs-lookup"><span data-stu-id="d768c-167">Before you get started, make sure you have a local or domain account and password ready from the previous Windows 7 installation.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-15.png)

<span data-ttu-id="d768c-168">*Recuperación de Windows 10 que garantiza que tiene credenciales de inicio de sesión de la instalación anterior*</span><span class="sxs-lookup"><span data-stu-id="d768c-168">*Windows 10 Recovery ensuring you have logon credentials from the previous installation*</span></span>

<span data-ttu-id="d768c-169">Desde aquí puede iniciar el proceso para volver a Windows 7.</span><span class="sxs-lookup"><span data-stu-id="d768c-169">From here you can initiate the process to go back to Windows 7.</span></span> <span data-ttu-id="d768c-170">Tras unos minutos, el equipo se iniciará nuevamente en Windows 7 de la misma manera que antes de actualizar a Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d768c-170">After a few minutes, your PC will boot back into Windows 7 with the same experience prior to upgrading to Windows 10.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-16.png)

<span data-ttu-id="d768c-171">*Pantalla final de Recuperación de Windows 10 antes de volver a Windows 7*</span><span class="sxs-lookup"><span data-stu-id="d768c-171">*Windows 10 Recovery final screen before going back to Windows 7*</span></span>

## <a name="moving-to-windows-10-on-a-new-pc"></a><span data-ttu-id="d768c-172">Pasar a Windows 10 en un equipo nuevo</span><span class="sxs-lookup"><span data-stu-id="d768c-172">Moving to Windows 10 on a new PC</span></span>

<span data-ttu-id="d768c-173">Otra opción recomendada es pasar a Windows 10 en un equipo nuevo.</span><span class="sxs-lookup"><span data-stu-id="d768c-173">Another recommended option is to move to Windows 10 on a new PC.</span></span> <span data-ttu-id="d768c-174">Si esta es su preferencia, puede transferir los archivos de su equipo antiguo con una copia de seguridad de [OneDrive, las Copias de seguridad y restauración integradas en Windows, usando manualmente un [dispositivo de almacenamiento externo](https://support.microsoft.com/es-ES/help/4465814/windows-7-move-files-off-pc-with-an-external-storage-device?ocid=MoveToWindows10) o con herramientas como PCmover Express de LapLink. </span><span class="sxs-lookup"><span data-stu-id="d768c-174">If this is your preference, you can transfer your files from your old computer using [OneDrive](https://support.office.com/article/b5e918be-0fd4-4095-98da-bceed57f8e0c?ocid=MoveToWindows10) backup, [Backup and Restore built into Windows](https://support.microsoft.com/help/4469209?ocid=MoveToWindows10), manually using an [external storage device](https://support.microsoft.com/en-us/help/4465814/windows-7-move-files-off-pc-with-an-external-storage-device?ocid=MoveToWindows10), or tools like [Laplink’s PCmover Express](https://www.microsoft.com/en-us/windows/transfer-your-data).</span></span> <span data-ttu-id="d768c-175">Con cualquiera de estas opciones, tendrá que volver a instalar cualquier aplicación no incluida en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d768c-175">With any of these options, you will still need to re-install any required applications not included with Windows 10.</span></span> <span data-ttu-id="d768c-176">Si desea informarse sobre las opciones para pasar de forma manual desde Windows 7 en un equipo existente a Windows 10 en un equipo nuevo, consulte [Migrar a un PC con Windows 10](https://support.microsoft.com/es-ES/help/4229823?ocid=MoveToWindows10) en el soporte técnico de Windows.</span><span class="sxs-lookup"><span data-stu-id="d768c-176">To learn more about your options for manually moving from an existing PC running Windows 7 to a new PC with Windows 10, see [Moving to a Windows 10 PC](https://support.microsoft.com/en-us/help/4229823?ocid=MoveToWindows10) in Windows Support.</span></span>

## <a name="desktop-deployment-centerhttpsakamshowtoshift"></a>[<span data-ttu-id="d768c-177">Centro de implementación de escritorios</span><span class="sxs-lookup"><span data-stu-id="d768c-177">Desktop Deployment Center</span></span>](https://aka.ms/howtoshift)