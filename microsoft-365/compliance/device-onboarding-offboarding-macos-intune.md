---
title: Incorporación y descarga de dispositivos macOS en soluciones de Microsoft Purview mediante Microsoft Intune
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Obtenga información sobre cómo incorporar y desconectar dispositivos macOS en soluciones de Microsoft Purview mediante Microsoft Intune
ms.openlocfilehash: f71cc8f5ef0a0d9a251dca0b8da5e7797f553e0f
ms.sourcegitcommit: ab32c6e19af08837aaa84a058653c3a209d366ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2022
ms.locfileid: "67444971"
---
# <a name="onboard-and-offboard-macos-devices-into-microsoft-purview-solutions-using-intune"></a>Incorporar y desactivar dispositivos macOS en soluciones de Microsoft Purview mediante Intune

Puede usar Intune para incorporar dispositivos macOS a las soluciones de Microsoft Purview.

> [!IMPORTANT]
> Use este procedimiento si ***no*** tiene Microsoft Defender para punto de conexión (MDE) implementados en los dispositivos macOS.

**Se aplica a:**

- [Prevención de perdida de datos en el punto de conexión (DLP)](./endpoint-dlp-learn-about.md)
- [Administración de riesgos internos](insider-risk-management.md)

## <a name="before-you-begin"></a>Antes de empezar

- Asegúrese de que [los dispositivos macOS están incorporados a Intune](/mem/intune/fundamentals/deployment-guide-platform-macos) y están inscritos en la [aplicación de Portal de empresa](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp). 
- Asegúrese de que tiene acceso al [Centro de Endpoint Manager de Microsoft](https://endpoint.microsoft.com/#home).
- Esto admite tres versiones principales más recientes de macOS.
- Cree los grupos de usuarios a los que va a asignar las actualizaciones de configuración.
- Instalar el explorador v95+ Edge en los dispositivos macOS 


## <a name="onboard-macos-devices-into-microsoft-purview-solutions-using-microsoft-intune"></a>Incorporación de dispositivos macOS a soluciones de Microsoft Purview mediante Microsoft Intune

La incorporación de un dispositivo macOS a las soluciones de cumplimiento es un proceso de varias fases.

1. [Creación de perfiles de configuración del sistema](#create-system-configuration-profiles)
1. [Obtención del paquete de incorporación de dispositivos](#get-the-device-onboarding-package)
1. [Implementación de mobileconfig y paquetes de incorporación](#deploy-the-mobileconfig-and-onboarding-packages)
1. [Publicar aplicación](#publish-application)
<!--1. [Enable system extension](#enable-system-extension)-->


### <a name="create-system-configuration-profiles"></a>Creación de perfiles de configuración del sistema

1. Necesitará estos archivos para este procedimiento. 

|archivo necesario para |source |
|---------|---------|
Archivo de configuración móvil del sistema | [mdatp-nokext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig) Copie y pegue el contenido en un archivo de texto. Guarde el archivo solo con la extensión **mobileconfig** ; no se reconocerá si tiene la extensión .txt.|
Preferencias de MDE| [com.microsoft.wdav.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/data_loss_prevention/com.microsoft.wdav.mobileconfig). Copie y pegue el contenido en un archivo de texto. Guarde el archivo solo con la extensión **mobileconfig** ; no se reconocerá si tiene la extensión .txt.

### <a name="get-the-device-onboarding-package"></a>Obtención del paquete de incorporación de dispositivos

1. En el **Centro de cumplimiento de Microsoft Purview** , abra **Configuración** > **Incorporación de dispositivos** y elija **Incorporación**.
 
1. En **Seleccionar sistema operativo para iniciar el proceso de incorporación** , elija **macOS**.
 
1. En **Método de implementación**, elija **Mobile Administración de dispositivos/Microsoft Intune**.
 
1. Elija **Descargar paquete de incorporación**. 

1. Extraiga el archivo ZIP y abra la carpeta *Intune*. Contiene el código de incorporación en el archivo *DeviceComplianceOnboarding.xml* .

<!--|accessibility |[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
full disk access     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|
|Network filer| [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig)]
|System extensions |[sysext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/sysext.mobileconfig)
|MDE preference     |[com.microsoft.wdav.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/data_loss_prevention/com.microsoft.wdav.mobileconfig)|
|MAU preference|[com.microsoft.autoupdate2.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/microsoft_auto_update/com.microsoft.autoupdate2.mobileconfig)|
|Installation package     |downloaded from the compliance portal **Installation package**, file name *\*wdav.pkg*\* |

> [!TIP]
> You can download the *.mobileconfig* files individually or in [single combined file](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig) that contains:
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
> - netfilter.mobileconfig
> - system extensions
>
>If any of these individual files is updated, you'd need to download the either the combined file again or the single updated file individually.-->

### <a name="deploy-the-mobileconfig-and-onboarding-packages"></a>Implementación de mobileconfig y paquetes de incorporación

1. Abra los **perfiles de configuración** de **dispositivos** >  del **centro** >  de Microsoft Endpoint Manager.

1. Elegir: **Crear perfil** 

1. Elegir:
    1. **Plataforma = macOS**
    1. **Tipo de perfil = Plantillas**
    1. **Nombre de plantilla = Personalizado**

1. Elija **Crear**

1. Elija un nombre para el perfil, como *SystemMobileConfig* en este ejemplo. Elija **Siguiente**.

1. Elija el archivo **mdatp-nokext.mobileconfig** que copió y guardó en el paso 1 como archivo de perfil de configuración.

1. Elija **Siguiente**

1. En la pestaña **Asignaciones** , agregue el grupo en el que desea implementar estas configuraciones y elija **Siguiente**.

1. Revise la configuración y elija **Crear** para implementar la configuración.

1. Repita los pasos del 2 al 9 para crear perfiles para:
    1. **DeviceComplianceOnboarding.xml** archivo. Asígnele el nombre *Purview Device Onboarding Package*
    1. **archivo com.microsoft.wdav.mobileconfig** . Asígnele el nombre *Preferencias de dispositivo de punto de conexión*
 
1. Abra Los **perfiles de configuración de** **dispositivos** > , debería ver los perfiles creados allí.

1. En la página **Perfiles de configuración** , elija el perfil que acaba de crear, por ejemplo *SystemMobileConfig* y elija **Estado del dispositivo** para ver una lista de dispositivos y el estado de implementación del perfil de configuración.

### <a name="publish-application"></a>Publicar aplicación

DLP de punto de conexión de Microsoft se instala como componente de Microsoft Defender para punto de conexión (MDE) en macOS. Este procedimiento se aplica a la incorporación de dispositivos a soluciones de Microsoft Purview

1. En el [Centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com/), abra **Aplicaciones**.

1. Seleccione Por plataforma > macOS > Agregar.

1. Elija **Tipo**= de **aplicación macOS** y haga clic en **Seleccionar**.

1. Mantenga los valores predeterminados, haga clic en **Siguiente**.

1. Agregue asignaciones y haga clic en **Siguiente**.

1. Revisar y **crear**.

1. Puede visitar **Aplicaciones** \> **por plataforma** \> **macOS** para verlo en la lista de todas las aplicaciones.

<!--## Offboard macOS devices using Intune PINGING PG FOR THIS PROCEDURE

> [!NOTE]
> Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to six months.

1. In **Microsoft Endpoint Manager center**, open **Devices** > **Configuration profiles**, you should see your created profiles there.

1. In the **Configuration profiles** page, choose the *wdav.pkg.intunemac* profile.

1. Choose **Device status** to see a list of devices and the deployment status of the configuration profile

1. Open **Properties** and **Assignments**

1. Remove the group from the assignment. This will uninstall the *wdav.pkg.intunemac* package and offboard the macOS device from Compliance solutions.-->
