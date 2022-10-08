---
title: Implementación de Defender para punto de conexión en Linux con Chef
description: Aprenda a implementar Defender para punto de conexión en Linux con Chef
keywords: microsoft, defender, atp, linux, scans, antivirus, microsoft defender para punto de conexión (linux)
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: fbd2abe360443e8a96da87e49553307768c05a7a
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68225820"
---
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a>Implementar Defender para punto de conexión en Linux con Chef

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Antes de comenzar: instale descomprimir si aún no está instalado.

Los componentes de Chef ya están instalados y existe un repositorio de Chef (repositorio \<reponame\>generado por Chef) para almacenar el libro de recetas que se usará para implementar en Defender para punto de conexión en servidores Linux administrados por Chef.

Puede crear un nuevo libro de recetas en el repositorio existente ejecutando el siguiente comando desde dentro de la carpeta cookbooks que se encuentra en el repositorio de Chef:

```bash
chef generate cookbook mdatp
```

Este comando creará una nueva estructura de carpetas para el nuevo libro de recetas denominado mdatp. También puede usar un libro de recetas existente si ya tiene uno que le gustaría usar para agregar la implementación de MDE.
Una vez creado el libro de recetas, cree una carpeta de archivos dentro de la carpeta del libro de recetas que acaba de crear:

```bash
mkdir mdatp/files
```

Transfiera el archivo zip de incorporación del servidor Linux que se puede descargar desde el portal de Microsoft 365 Defender a esta nueva carpeta de archivos.

En la estación de trabajo de Chef, vaya a la carpeta mdatp/recipes. Esta carpeta se crea cuando se generó el libro de recetas. Use el editor de texto que prefiera (como vi o nano) para agregar las siguientes instrucciones al final del archivo default.rb:

- include_recipe "::onboard_mdatp"
- include_recipe "::install_mdatp"

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
   uri                "https://packages.microsoft.com/config/ubuntu/20.04/prod"
 end
 apt_package "mdatp"
when 'rhel'
 yum_repository 'microsoft-prod' do
   baseurl            "https://packages.microsoft.com/config/rhel/7/prod/"
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

Tendrá que modificar el número de versión, la distribución y el nombre del repositorio para que coincidan con la versión en la que se va a implementar y el canal en el que desea implementar.
A continuación, debe crear un archivo onboard_mdatp.rb en la carpeta mdatp/recipies. Agregue el texto siguiente a ese archivo:

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
Para probar la implementación en la estación de trabajo de Chef, ejecute ``sudo chef-client -z -o mdatp``.
Después de la implementación, debe considerar la posibilidad de crear e implementar un archivo de configuración en los servidores en función de [establecer preferencias para Microsoft Defender para punto de conexión en Linux](/microsoft-365/security/defender-endpoint/linux-preferences).
Después de crear y probar el archivo de configuración, puede colocarlo en la carpeta cookbook/mdatp/files donde también ha colocado el paquete de incorporación. A continuación, puede crear un archivo settings_mdatp.rb en la carpeta mdatp/recipies y agregar este texto:

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

Para incluir este paso como parte de la receta, solo tiene que agregar include_recipe ":: settings_mdatp" al archivo default.rb dentro de la carpeta recipe.
También puede usar crontab para programar actualizaciones [automáticas Programar una actualización de la Microsoft Defender para punto de conexión (Linux).](linux-update-MDE-Linux.md)

Desinstale el libro de recetas de MDATP:

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
