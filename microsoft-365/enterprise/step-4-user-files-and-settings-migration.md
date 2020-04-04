---
title: 'Paso 4: Migración de los archivos y la configuración del usuario'
f1.keywords:
- NOCSH
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
description: Obtenga información sobre cómo migrar los archivos y la configuración de los usuarios.
ms.openlocfilehash: f17b11efe889359f97087ac5d96ffa968ca8cd88
ms.sourcegitcommit: 9ca28ae8f7804eb488cf76ca4b09fe88787e0a49
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "43113546"
---
# <a name="step-4-user-files-and-settings-migration"></a>Paso 4: Migración de los archivos y la configuración del usuario

Mover archivos y la configuración de los usuarios a los equipos nuevos o actualizados es un proceso crítico en el que no se admiten errores. Puede migrar manualmente cada equipo o elegir uno de los distintos métodos para automatizar el proceso. Independientemente del método de migración que elija, hay tres aspectos principales que deberá abordar: la transferencia de archivos de los usuarios, su configuración y la gestión de inicio de Windows 10 y de los diseños de barra de tareas.

![](../media/step-4-user-files-and-settings-migration-media/step-4-user-files-and-settings-migration-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-7.png" alt="Step 4" height="135" width="135" /></td>
<td><p><strong>Paso 4: Archivos y configuración del usuario</strong></p>
<p>Al actualizar o reemplazar los equipos, puede ahorrar tiempo si automatiza la copia de seguridad del estado del usuario y la restauración. Las nuevas opciones de sincronización de archivos en la nube permiten aplicar la sincronización, por cada usuario, de las carpetas Escritorio, Documentos e Imágenes en OneDrive para acceder a los archivos de forma directa desde las nuevas instalaciones de Windows.</p></td>
<td><a href="https://aka.ms/ddev4" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-17.png" alt="Step 4" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>Aunque puede seguir utilizando los procesos de migración que ha usado en el pasado, con el cambio a Office 365 ProPlus se recomienda usar "Mover carpeta conocida" de OneDrive (ver a continuación). Para ver el proceso de implementación de escritorio completo, visite el [Centro de implementación de escritorio](https://aka.ms/HowToShift).
>

Una de las tareas más difíciles y a menudo más manuales de una implementación a gran escala es la transferencia de los archivos y la configuración de los usuarios. En este artículo se tratarán las opciones disponibles para migrar los usuarios a equipos nuevos, actualizados y renovados.

## <a name="manual-migration"></a>Migración manual

A la hora de decidir qué se va a mantener al migrar a un equipo nuevo o una versión de Windows nueva, es posible que algunos usuarios quieran conservarlo todo, mientras que otros quieran aprovechar la oportunidad para limpiar sus unidades. Por este motivo, algunos departamentos de TI eligen administrar de forma manual la migración de los archivos del usuario, y en ocasiones los equipos de soporte visitan a los usuarios; en otros casos, se crean centros de soporte técnico para que los usuarios lleven sus equipos al personal de soporte técnico. En cualquier caso, los usuarios pueden participar a la hora de decidir lo que se va a transferir y a descartar.

Disponer de esta opción en la organización dependerá de la escala de la migración que se esté planeando. Evidentemente, existe una limitación temporal y física relacionada con trabajar directamente con los usuarios, entender sus necesidades y copiar los archivos a un equipo nuevo o recién actualizado.

Si opta por una migración manual, considere la posibilidad de usar una de las opciones automatizadas siguientes o de solicitar más personas para ayudarle.

## <a name="automated-migration-using-usmt"></a>Migración automatizada con USMT 

Para las implementaciones a gran escala puede automatizar gran parte del proceso mediante herramientas de automatización de la implementación basadas en secuencias de tareas como Microsoft Endpoint Configuration Manager o Microsoft Deployment Toolkit (MDT). En ambas soluciones se usa la Herramienta de migración de estado de usuario (USMT) como parte del proceso de implementación integral. USMT forma parte del [Windows Assessment and Deployment Kit (Windows ADK)](https://docs.microsoft.com/windows-hardware/get-started/adk-install).

USMT captura las cuentas y los archivos del usuario, la configuración del sistema operativo y la aplicación, y lo migra a una instalación nueva de Windows. También ofrece al administrador de TI el control exacto de lo que se va a migrar y, opcionalmente, permite excluir tipos de archivos no deseados, como archivos ejecutables, de vídeo o audio.

Durante el proceso de migración, necesitará capacidad de almacenamiento de servidor suficiente que actúe de almacén de migración temporal. Aquí USMT ofrece dos características importantes. En primer lugar, puede calcular, por equipo, la cantidad de almacenamiento que va a necesitar. En segundo lugar, permite cifrar los almacenes de migración, lo que reduce el riesgo de que los datos se pongan en peligro mientras se almacenan en servidores de archivo.

Al realizar una actualización del equipo sin formatear la partición de Windows principal, también tiene la posibilidad de usar un almacén de migración de vínculo físico con USMT. Este proceso conserva el estado del usuario en el equipo mientras se eliminan y actualizan el sistema operativo anterior y las aplicaciones. Como el proceso de restauración procede de la misma partición local, esta opción ofrece mejoras significativas en el rendimiento y reduce el tráfico de red.

[Introducción de la Herramienta de migración de estado de usuario (USMT)](https://docs.microsoft.com/windows/deployment/usmt/usmt-overview)

## <a name="onedrive-known-folder-move"></a>Mover carpeta conocida de OneDrive

Si los usuarios se encuentran en OneDrive o se va a agregar OneDrive como parte de esta implementación, hay una nueva opción disponible. Usando la nube para sincronizar los archivos de usuario, la característica "Mover carpeta conocida" de OneDrive proporciona un nivel de flexibilidad imposible con las opciones de migración de archivos basadas en la red local. Si se habilita antes de la migración, proporciona acceso seguro a los equipos nuevos o actualizados, y elimina la necesidad de crear almacenes de migración temporales en servidores propios. Además, tiene la capacidad de ser completamente transparente para el usuario.

[Redirigir y mover las carpetas conocidas de Windows a OneDrive](https://docs.microsoft.com/onedrive/redirect-known-folders)

Si ya usa OneDrive, sabrá que los usuarios pueden seleccionar las carpetas y ubicaciones que quieren sincronizar desde OneDrive o SharePoint con su dispositivo, pero eso coloca la carga de configuración en el usuario final. Con Mover carpeta conocida, se pueden seleccionar como destino las carpetas Documentos, Escritorio e Imágenes de un perfil de usuario y protegerlas en OneDrive. El usuario puede hacerlo por su cuenta o, lo que es importante en este escenario, se puede [aplicar mediante la configuración de directiva de grupo](https://docs.microsoft.com/onedrive/use-group-policy?redirectSourcePath=%252fen-us%252farticle%252fUse-Group-Policy-to-control-OneDrive-sync-client-settings-0ecb2cf5-8882-42b3-a6e9-be6bda30899c).

Con Mover carpeta conocida, los usuarios no cambian el flujo de trabajo: todo tiene el mismo aspecto antes, durante y después de que finalice la sincronización con OneDrive. Mediante la directiva de grupo, incluso se puede elegir si se notifica o no a los usuarios que sus documentos, imágenes y escritorio están protegidos en OneDrive. Si se elige que no, el proceso se realiza en modo silencioso en segundo plano. Los usuarios solo se darán cuenta cuando se entregue un equipo nuevo o se actualice su equipo. En cuanto inicien sesión en su cuenta de OneDrive, los archivos volverán a estar disponibles y se restaurarán en el equipo nuevo. Y por supuesto, OneDrive significa que también podrán acceder a los archivos de forma segura en cualquier momento desde sus teléfonos y otros dispositivos.

Autenticación para OneDrive con tecnología de Azure Active Directory, de forma que para ofrecer seguridad adicional, puede habilitar fácilmente la autenticación multifactor y establecer directivas para controlar el ancho de banda de carga y descarga que OneDrive usa para limitar la actividad de red.

No es necesario migrar a todos los usuarios al mismo tiempo. Se recomienda distribuir en fases la implementación de la configuración de directiva de grupo, o bien [limitar la sincronización de los archivos a los equipos unidos a un dominio](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenantSyncClientRestriction?view=sharepoint-ps).

## <a name="start-menu-and-task-bar-customization"></a>Personalización del menú Inicio y la barra de tareas

OneDrive está diseñado para sincronizar y proteger archivos y carpetas; no sincroniza la configuración de las aplicaciones o de Windows. Para hacer esto en el pasado, es posible que usara el método de copia de perfil para configurar diseños estándar para los menús Inicio y la barra de tareas de los usuarios. En Windows 10 Pro, Enterprise y Education, se puede usar la Directiva de grupo, MDM, PowerShell, o bien aprovisionar paquetes, para implementar [diseños personalizados para el menú Inicio y la barra de tareas](https://docs.microsoft.com/windows/configuration/windows-10-start-layout-options-and-policies). No es necesario volver a crear imágenes y, para actualizar el diseño, simplemente se sobrescribe el archivo .xml que lo contiene.

Para crear un diseño, simplemente configure un sistema de ejemplo y use el cmdlet [Export-StartLayout](https://docs.microsoft.com/powershell/module/startlayout/export-startlayout?view=win10-ps) de PowerShell para generar un archivo XML; después, coloque el archivo en un recurso compartido de red o guárdelo en la caché local como parte de la secuencia de implementación; solo debe ser accesible como archivo de solo lectura cuando el usuario inicie sesión. Luego, puede usar la directiva o el cmdlet [Import-StartLayout](https://docs.microsoft.com/powershell/module/startlayout/import-startlayout?view=win10-ps) para hacer referencia a este archivo.

## <a name="removing-unwanted-in-box-apps"></a>Eliminación de las aplicaciones incluidas no deseadas

En Windows 10 se incluyen muchas aplicaciones integradas útiles como parte de la instalación estándar, pero es posible que quiera quitar algunas de los equipos administrados e incluso configurar la instalación para impedir que vuelvan, como XBOX o Zune Música. Puede obtener una lista de esas aplicaciones mediante los comandos [Get-AppxPackage de PowerShell](https://technet.microsoft.com/library/hh856044.aspx) y quitar las que no quiera usar con el comando [Remove-AppxPackage](https://technet.microsoft.com/library/hh856038.aspx). Como alternativa, puede montar el archivo de imagen (.img) de Windows sin conexión antes de la implementación, y extraer los paquetes que no quiera usar con la herramienta de línea de comandos [Administración y mantenimiento de imágenes de implementación (DISM)](https://docs.microsoft.com/windows-hardware/manufacture/desktop/what-is-dism) y el comando [Remove-AppxProvisionedPackage](https://docs.microsoft.com/powershell/module/dism/remove-appxprovisionedpackage?view=win10-ps).

## <a name="next-step"></a>Siguiente paso

## <a name="step-5-security-and-compliance-considerations"></a>[Paso 5: Consideraciones de seguridad y cumplimiento](https://aka.ms/mdd5)

## <a name="previous-step"></a>Paso anterior

## <a name="step-3-office-and-lob-app-delivery"></a>[Paso 3: Entrega de aplicaciones de Office y de LOB](https://aka.ms/mdd3)
