---
title: Cómo implementar Defender para endpoint en Linux con Chef
description: Obtenga información sobre cómo implementar Defender for Endpoint en Linux con Chef
keywords: microsoft, defender, atp, linux, exámenes, antivirus, microsoft defender para el punto de conexión (linux)
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 362222e4737b1a8dd6b8a0a284bf3bfb1903c288
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861455"
---
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a><span data-ttu-id="5fa9b-104">Implementar Defender para endpoint en Linux con Chef</span><span class="sxs-lookup"><span data-stu-id="5fa9b-104">Deploy Defender for Endpoint on Linux with Chef</span></span>

<span data-ttu-id="5fa9b-105">Antes de empezar:</span><span class="sxs-lookup"><span data-stu-id="5fa9b-105">Before you begin:</span></span>

- <span data-ttu-id="5fa9b-106">Instale descomprimir si aún no está instalado.</span><span class="sxs-lookup"><span data-stu-id="5fa9b-106">Install unzip if it’s not already installed.</span></span> <span data-ttu-id="5fa9b-107">Los componentes de Chef ya están instalados y existe un repositorio de Chef (chef generar repositorio ) para almacenar el libro de recetas que se usará para implementar en Defender for Endpoint en servidores Linux administrados por <reponame> Chef.</span><span class="sxs-lookup"><span data-stu-id="5fa9b-107">The Chef components are already installed and a Chef repository exists (chef generate repo <reponame>) to store the cookbook that will be used to deploy to Defender for Endpoint on Chef managed Linux servers.</span></span>

<span data-ttu-id="5fa9b-108">Puede crear un nuevo libro de recetas en el repositorio existente ejecutando el siguiente comando desde dentro de la carpeta de libros de recetas que se encuentra en el repositorio de chef:</span><span class="sxs-lookup"><span data-stu-id="5fa9b-108">You can create a new cookbook in your existing repository by running the following command from inside the cookbooks folder that is in your chef repository:</span></span></br>
`chef generate cookbook mdatp`

<span data-ttu-id="5fa9b-109">Este comando creará una nueva estructura de carpetas para el nuevo libro de recetas denominado mdatp.</span><span class="sxs-lookup"><span data-stu-id="5fa9b-109">This command will create a new folder structure for the new cookbook called mdatp.</span></span>  <span data-ttu-id="5fa9b-110">También puede usar un libro de recetas existente si ya tiene uno que desea usar para agregar la implementación de MDE.</span><span class="sxs-lookup"><span data-stu-id="5fa9b-110">You can also use an existing cookbook if you already have one you’d like to use to add the MDE deployment into.</span></span>
<span data-ttu-id="5fa9b-111">Después de crear el libro de recetas, cree una carpeta de archivos dentro de la carpeta del libro de recetas que acaba de crear:</span><span class="sxs-lookup"><span data-stu-id="5fa9b-111">After the cookbook is created, create a files folder inside the cookbook folder that just got created:</span></span>

`mkdir mdatp/files`

<span data-ttu-id="5fa9b-112">Transfiera el archivo zip de incorporación de Linux Server que se puede descargar desde el portal del Centro de seguridad de Microsoft Defender a esta nueva carpeta de archivos.</span><span class="sxs-lookup"><span data-stu-id="5fa9b-112">Transfer the Linux Server Onboarding zip file that can be downloaded from the Microsoft Defender Security Center portal to this new files folder.</span></span>

<span data-ttu-id="5fa9b-113">En la estación de trabajo de Chef, vaya a la carpeta mdatp/recipes.</span><span class="sxs-lookup"><span data-stu-id="5fa9b-113">On the Chef Workstation, navigate to the mdatp/recipes folder.</span></span> <span data-ttu-id="5fa9b-114">Esta carpeta se crea cuando se generó el libro de recetas.</span><span class="sxs-lookup"><span data-stu-id="5fa9b-114">This folder is created when the cookbook was generated.</span></span> <span data-ttu-id="5fa9b-115">Use el editor de texto preferido (como vi o nano) para agregar las siguientes instrucciones al final del archivo default.rb:</span><span class="sxs-lookup"><span data-stu-id="5fa9b-115">Use your preferred text editor (like vi or nano) to add the following instructions to the end of the default.rb file:</span></span>
-   <span data-ttu-id="5fa9b-116">include_recipe '::onboard_mdatp'</span><span class="sxs-lookup"><span data-stu-id="5fa9b-116">include_recipe '::onboard_mdatp'</span></span>
- <span data-ttu-id="5fa9b-117">include_recipe '::install_mdatp'</span><span class="sxs-lookup"><span data-stu-id="5fa9b-117">include_recipe '::install_mdatp'</span></span>

<span data-ttu-id="5fa9b-118">A continuación, guarde y cierre el archivo default.rb.</span><span class="sxs-lookup"><span data-stu-id="5fa9b-118">Then save and close the default.rb file.</span></span>
<span data-ttu-id="5fa9b-119">A continuación, cree un nuevo archivo de receta denominado install_mdatp.rb en la carpeta recipes y agregue este texto al archivo:</span><span class="sxs-lookup"><span data-stu-id="5fa9b-119">Next create a new recipe file named install_mdatp.rb in the recipes folder and add this text to the file:</span></span>

```powershell

#Add Microsoft Defender   
Repo  
case node['platform_family']
when 'debian'
 apt_repository 'MDAPRepo' do
   arch               'amd64'
   cache_rebuild      true
   cookbook           false
   deb_src            false
   key                'BC528686B50D79E339D3721CEB3E94ADBE1229CF'
   keyserver          "keyserver.ubuntu.com"
   distribution       'focal'
   repo_name          'microsoft-prod'
   components         ['main']
   trusted            true
   uri                "https://packages.microsoft.com/ubuntu/20.04/prod"
 end
 apt_package "mdatp"
when 'rhel'
 yum_repository 'microsoft-prod' do
   baseurl            "https://packages.microsoft.com/rhel/7/prod/"
   description        "Microsoft Defender for Endpoint"
   enabled            true
   gpgcheck           true
   gpgkey             "https://packages.microsoft.com/keys/microsoft.asc"
 end
 if node['platform_version'] <= 8 then
    yum_package "mdatp"
 else
    dnf_package "mdatp"
 end
end
```

<span data-ttu-id="5fa9b-120">Deberá modificar el número de versión, la distribución y el nombre del repositorio para que coincida con la versión en la que está implementando y el canal que desea implementar.</span><span class="sxs-lookup"><span data-stu-id="5fa9b-120">You’ll need to modify the version number, distribution, and repo name to match the version you’re deploying to and the channel you’d like to deploy.</span></span>
<span data-ttu-id="5fa9b-121">A continuación, debe crear un onboard_mdatp.rb en la carpeta mdatp/recipies.</span><span class="sxs-lookup"><span data-stu-id="5fa9b-121">Next you should create an onboard_mdatp.rb file in the mdatp/recipies folder.</span></span>  <span data-ttu-id="5fa9b-122">Agregue el texto siguiente a ese archivo:</span><span class="sxs-lookup"><span data-stu-id="5fa9b-122">Add the following text to that file:</span></span>

```powershell

#Create MDATP Directory
mdatp = "/etc/opt/microsoft/mdatp"
zip_path = "/path/to/chef-repo/cookbooks/mdatp/files/WindowsDefenderATPOnboardingPackage.zip"

directory "#{mdatp}" do
  owner 'root'
  group 'root'
  mode 0755
  recursive true
end

#Extract WindowsDefenderATPOnbaordingPackage.zip into /etc/opt/microsoft/mdatp

bash 'Extract Onbaording Json MDATP' do
  code <<-EOS
  unzip #{zip_path} -d #{mdatp}
  EOS
  not_if { ::File.exist?('/etc/opt/microsoft/mdatp/mdatp_onboard.json') }
end
```

<span data-ttu-id="5fa9b-123">Asegúrese de actualizar el nombre de la ruta de acceso a la ubicación del archivo de incorporación.</span><span class="sxs-lookup"><span data-stu-id="5fa9b-123">Make sure to update the path name to the location of the onboarding file.</span></span>
<span data-ttu-id="5fa9b-124">Para probar la implementación en la estación de trabajo de Chef, simplemente ejecute ``sudo chef-client -z -o mdatp`` .</span><span class="sxs-lookup"><span data-stu-id="5fa9b-124">To test deploy it on the Chef workstation, just run ``sudo chef-client -z -o mdatp``.</span></span>
<span data-ttu-id="5fa9b-125">Después de la implementación, debes considerar la posibilidad de crear e implementar un archivo de configuración en los servidores según establecer preferencias para ATP de Microsoft Defender para Linux: seguridad de  [Windows | Microsoft Docs](/windows/security/threat-protection/microsoft-defender-atp/linux-preferences).</span><span class="sxs-lookup"><span data-stu-id="5fa9b-125">After your deployment you should consider creating and deploying a configuration file to the servers based on  [Set preferences for Microsoft Defender ATP for Linux - Windows security | Microsoft Docs](/windows/security/threat-protection/microsoft-defender-atp/linux-preferences).</span></span>  
<span data-ttu-id="5fa9b-126">Después de crear y probar el archivo de configuración, puede colocarlo en la carpeta cookbook/mdatp/files donde también colocó el paquete de incorporación.</span><span class="sxs-lookup"><span data-stu-id="5fa9b-126">After you've created and tested your configuration file, you can place it into the cookbook/mdatp/files folder where you also placed the onboarding package.</span></span>  <span data-ttu-id="5fa9b-127">A continuación, puede crear un archivo settings_mdatp.rb en la carpeta mdatp/recipies y agregar este texto:</span><span class="sxs-lookup"><span data-stu-id="5fa9b-127">Then you can create a settings_mdatp.rb file in the mdatp/recipies folder and add this text:</span></span>

```powershell
#Copy the configuration file
cookbook_file '/etc/opt/microsoft/mdatp/managed/mdatp_managed.json' do
  source 'mdatp_managed.json'
  owner 'root'
  group 'root'
  mode '0755'
  action :create
end
```

<span data-ttu-id="5fa9b-128">Para incluir este paso como parte de la receta, simplemente agregue include_recipe ":: settings_mdatp" al archivo default.rb dentro de la carpeta de recetas.</span><span class="sxs-lookup"><span data-stu-id="5fa9b-128">To include this step as part of the recipe just add include_recipe ':: settings_mdatp' to your default.rb file within the recipe folder.</span></span>
<span data-ttu-id="5fa9b-129">También puede usar crontab para programar actualizaciones automáticas Programe una actualización [de Microsoft Defender para Endpoint (Linux).](linux-update-MDE-Linux.md)</span><span class="sxs-lookup"><span data-stu-id="5fa9b-129">You can also use crontab to schedule automatic updates [Schedule an update of the Microsoft Defender for Endpoint (Linux)](linux-update-MDE-Linux.md).</span></span>

<span data-ttu-id="5fa9b-130">Desinstalar el libro de recetas MDATP:</span><span class="sxs-lookup"><span data-stu-id="5fa9b-130">Uninstall MDATP cookbook:</span></span>

```powershell
#Uninstall the Defender package
case node['platform_family']
when 'debian'
 apt_package "mdatp" do
   action :remove
 end
when 'rhel'
 if node['platform_version'] <= 8 
then
    yum_package "mdatp" do
      action :remove
    end
 else
    dnf_package "mdatp" do
      action :remove
    end
 end
end
```

