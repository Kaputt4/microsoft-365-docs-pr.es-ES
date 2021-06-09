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
ms.openlocfilehash: aa699aae24b1e6383f5a2afbe7fce31e0f53805c
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903933"
---
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a>Implementar Defender para punto de conexión en Linux con Chef

Antes de empezar:

- Instale descomprimir si aún no está instalado. Los componentes de Chef ya están instalados y existe un repositorio de Chef (chef generar repositorio ) para almacenar el libro de recetas que se usará para implementar en Defender for Endpoint en servidores Linux administrados por <reponame> Chef.

Puede crear un nuevo libro de recetas en el repositorio existente ejecutando el siguiente comando desde dentro de la carpeta de libros de recetas que se encuentra en el repositorio de chef:</br>
`chef generate cookbook mdatp`

Este comando creará una nueva estructura de carpetas para el nuevo libro de recetas denominado mdatp.  También puede usar un libro de recetas existente si ya tiene uno que desea usar para agregar la implementación de MDE.
Después de crear el libro de recetas, cree una carpeta de archivos dentro de la carpeta del libro de recetas que acaba de crear:

`mkdir mdatp/files`

Transfiera el archivo zip de incorporación de linux server que se puede descargar desde el portal de Centro de seguridad de Microsoft Defender a esta nueva carpeta de archivos.

En la estación de trabajo de Chef, vaya a la carpeta mdatp/recipes. Esta carpeta se crea cuando se generó el libro de recetas. Use el editor de texto preferido (como vi o nano) para agregar las siguientes instrucciones al final del archivo default.rb:
-   include_recipe '::onboard_mdatp'
- include_recipe '::install_mdatp'

A continuación, guarde y cierre el archivo default.rb.
A continuación, cree un nuevo archivo de receta denominado install_mdatp.rb en la carpeta recipes y agregue este texto al archivo:

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

Deberá modificar el número de versión, la distribución y el nombre del repositorio para que coincida con la versión en la que está implementando y el canal que desea implementar.
A continuación, debe crear un onboard_mdatp.rb en la carpeta mdatp/recipies.  Agregue el texto siguiente a ese archivo:

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

Asegúrese de actualizar el nombre de la ruta de acceso a la ubicación del archivo de incorporación.
Para probar la implementación en la estación de trabajo de Chef, simplemente ejecute ``sudo chef-client -z -o mdatp`` .
Después de la implementación, debe considerar la posibilidad de crear e implementar un archivo de configuración en los servidores según establecer preferencias para  [Microsoft Defender para](/linux-preferences.md)endpoint en Linux .  
Después de crear y probar el archivo de configuración, puede colocarlo en la carpeta cookbook/mdatp/files donde también colocó el paquete de incorporación.  A continuación, puede crear un archivo settings_mdatp.rb en la carpeta mdatp/recipies y agregar este texto:

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

Para incluir este paso como parte de la receta, simplemente agregue include_recipe ":: settings_mdatp" al archivo default.rb dentro de la carpeta de recetas.
También puede usar crontab para programar actualizaciones automáticas Programe una actualización [de Microsoft Defender para Endpoint (Linux).](linux-update-MDE-Linux.md)

Desinstalar MDATP de recetas:

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

