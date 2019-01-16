---
title: Implementar Enterprise del 10 de Windows para dispositivos existentes como una actualización en contexto
description: Proporciona orientación sobre configuración e implementación de una imagen de Windows 10 Enterprise con System Center Configuration Manager como una actualización en contexto.
keywords: Implementación de Microsoft 365, 365 Enterprise de Microsoft, Microsoft 365 documentación, Windows 10 Enterprise, actualización en contexto, Configuration Manager, System Center Configuration Manager
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
ms.author: greglin
ms.openlocfilehash: 3df76c0de7b5a8b12c063113c79f9efa4e33b4c1
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871681"
---
# <a name="step-2-deploy-windows-10-enterprise-for-existing-devices-as-an-in-place-upgrade"></a>Paso 2: Implementar Enterprise del 10 de Windows para dispositivos existentes como una actualización en contexto

*En este artículo se aplica a la E3 y E5 versiones de Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

La ruta de acceso más simple para actualizar equipos que ejecutan actualmente Windows 7 o Windows 8.1 a 10 de Windows es a través de una actualización en contexto. Puede usar una secuencia de tareas de System Center Configuration Manager (Administrador de configuración) para automatizar completamente el proceso. 

Si tiene equipos existentes que ejecutan Windows 7 o Windows 8.1, se recomienda esta ruta de acceso si la organización va a implementar Windows 10. Esto aprovecha el programa de instalación de Windows (Setup.exe) para realizar una actualización en contexto, que automáticamente conserva todos los datos, configuración, las aplicaciones, y los controladores de la versión del sistema operativo existente. Esto requiere el mínimo esfuerzo de TI, debido a que no es necesario para cualquier infraestructura de implementación compleja.

Siga estos pasos para configurar e implementar una imagen de Windows 10 Enterprise mediante el Administrador de configuración como una actualización en contexto.

## <a name="part-1-verify-readiness-to-upgrade-windows"></a>Parte 1: Comprobar la preparación para la actualización de Windows

En primer lugar, use la capacidad de actualización de preparación de análisis de Windows para proporcionar conocimientos eficaces y recomendaciones acerca de los equipos, aplicaciones y controladores de la organización, sin ningún costo adicional y sin requisitos de infraestructura adicional. Este nuevo servicio le guía a través de la actualización y la característica de actualizar los proyectos con un flujo de trabajo en función de las prácticas recomendada de Microsoft. Datos de inventario actualizada le permite equilibrar costo y los riesgos en los proyectos de actualización.

Consulte [las actualizaciones de administración de Windows con la preparación de la actualización](https://docs.microsoft.com/windows/deployment/upgrade/manage-windows-upgrades-with-upgrade-readiness) a más información, empezar a trabajar, usar y solucionar problemas de preparación de actualización.

A continuación, siga la guía para usar System Center Configuration Manager (rama actual) para actualizar Windows 7 o sistema operativo posterior a 10 de Windows. Al igual que con cualquier implementación de alto riesgo, se recomienda la copia de seguridad de datos de usuario antes de continuar. Almacenamiento de OneDrive en la nube está listo para usarse para los usuarios con licencia de Microsoft 365 y se puede usar para almacenar sus archivos de forma segura. Para obtener más información, vea la [Guía de inicio rápido de OneDrive](https://aka.ms/ODfBquickstartguide). Para obtener acceso a esta página, debe iniciar sesión como un administrador de inquilinos o administrador global en un inquilino de Office 365 o Microsoft 365.

Para obtener una lista de las versiones de Configuration Manager y las correspondientes versiones del cliente 10 de Windows que son compatibles, consulte el [soporte técnico para Windows 10 para System Center Configuration Manager](https://aka.ms/supportforwin10sccm).

**Para comprobar la disponibilidad para la actualización de Windows**

Revise estos requisitos antes de iniciar la implementación de Windows 10:

- **Actualización de las ediciones de Windows optan** - los dispositivos deben ejecutar las ediciones de Windows 7 o Windows 8.1 que son aptos para la actualización a Windows 10 Enterprise. Para obtener una lista de las versiones compatibles, vea [rutas de actualización de Windows 10](https://aka.ms/win10upgradepaths). 
- **Dispositivos compatibles** - mayoría de los equipos que son compatibles con Windows 8.1 será compatible con Windows 10. Es posible que necesite instalar controladores actualizados en Windows 10 para los dispositivos que funcione correctamente. Para obtener más información, vea [las especificaciones del 10 de Windows](https://aka.ms/windows10specifications) .
- **Preparación de la implementación** - Asegúrese de que dispone de lo siguiente antes de empezar a configurar la implementación:
    - Medios de instalación de Windows 10 - los medios de instalación deben estar ubicados en una unidad independiente, con la especificación ISO ya montado. Puede obtener el ISO de [Descargas de suscriptores de MSDN](https://aka.ms/msdn-subscriber-downloads) o desde el [Centro de servicio de licencias por volumen](https://aka.ms/mvlsc).
    - Copias de seguridad de datos de usuario: aunque se van a migrar datos de usuario en la actualización, procedimiento recomendado consiste en configurar un escenario de copia de seguridad. Por ejemplo, exportar todos los datos de usuario a una cuenta de OneDrive, una unidad flash USB cifrado BitLocker To Go o un servidor de archivos de red. Para obtener más información, vea [copia de seguridad o transferir los datos de Windows](https://aka.ms/backuptransferdatawindows).
- **Preparación del entorno** - va a usar una estructura de servidor del Administrador de configuración existente a la preparación para la implementación de sistema operativo. Además de la configuración básica, deben hacerse las siguientes configuraciones en el entorno de Configuration Manager:
    1. [Ampliar el esquema de Active Directory](https://aka.ms/extendadschema) y [crear un contenedor de administración del sistema](https://aka.ms/createsysmancontainer).
    2. Bosque de Active Directory de habilitar la detección y descubrimiento del sistema de Active Directory. Para obtener más información, vea [Configure los métodos de descubrimiento para System Center Configuration Manager](https://aka.ms/configurediscoverymethods).
    3. Crear los límites de intervalo IP y el grupo límite de asignación de sitio y contenido. Para obtener más información, vea [definir los límites del sitio y los grupos de límite para System Center Configuration Manager](https://aka.ms/definesiteboundaries).
    4. Agregar y configurar el Administrador de configuración de reporting services punto de rol. Para obtener más información, vea [Configuración de informes en el Administrador de configuración](https://aka.ms/configurereporting).
    5. Crear una estructura de carpetas del sistema de archivos para los paquetes de.
    6. Crear una estructura de carpetas de la consola de Configuration Manager para los paquetes de.
    7. Instale las actualizaciones de System Center Configuration Manager (rama actual) y los requisitos previos de Windows 10 adicionales.

## <a name="part-2-add-a-windows-10-os-image-using-configuration-manager"></a>Parte 2: Agregar una imagen de sistema operativo del 10 de Windows mediante el Administrador de configuración
Ahora que necesitará para crear un paquete de actualización de sistema operativo que contiene los medios de instalación de Windows 10 completos. En los siguientes pasos, debe usar el Administrador de configuración para crear un paquete de actualización para Windows 10 Enterprise x64.

**Para agregar una imagen de sistema operativo del 10 de Windows mediante el Administrador de configuración**

1. Uso de la consola de Configuration Manager, en el área de trabajo de la **Biblioteca de Software** , haga clic en el nodo de **Paquetes de actualización del sistema operativo** y, a continuación, seleccione **Agregar paquete de actualización del sistema operativo**.
2. En la página de **Origen de datos** , especifique la ruta de acceso UNC a los medios de Windows 10 Enterprise x64 y, a continuación, seleccione **siguiente**.
3. En la página **General** , especifique la **actualización de Windows 10 Enterprise x64**y, a continuación, seleccione **siguiente**. 
4. En la página de **Resumen** , seleccione **siguiente**y, a continuación, seleccione **Cerrar**. 
5. Haga clic en el paquete de **actualización de Windows 10 Enterprise x64** creado y, a continuación, seleccione **Distribuir contenido**. 
6. Elija el punto de distribución.

## <a name="part-3-configure-deployment-settings"></a>Parte 3: Configurar las opciones de implementación
En este paso, configurará una secuencia de tareas de actualización que contiene la configuración para la actualización de Windows 10. Aquí, a continuación, identifique los dispositivos para actualizar y, a continuación, implementar la secuencia de tareas en esos dispositivos.

### <a name="create-a-task-sequence"></a>Crear una secuencia de tareas
Para crear una secuencia de tareas de actualización, realice los pasos siguientes:
  
1. En la consola de Configuration Manager, en el área de trabajo de la **Biblioteca de Software** , expanda **sistemas operativos**. 
2. Haga clic en el nodo de **Secuencias de tareas** y, a continuación, seleccione **Crear secuencia de tareas**.
3. En la página **crear una nueva secuencia de tareas** , seleccione **actualizar un sistema operativo desde el paquete de actualización**y, a continuación, seleccione **siguiente**.
4. En la página **Información de la secuencia de tareas** , especifique la **actualización de Windows 10 Enterprise x64**y, a continuación, seleccione **siguiente**.
5. En la página **actualizar el sistema operativo de Windows** , seleccione **Examinar** y elija el **paquete de actualización del sistema operativo de la actualización Windows 10 Enterprise x64**, haga **clic en Aceptar**y, a continuación, seleccione **siguiente**.
6. Continúe con las páginas restantes del asistente y, a continuación, seleccione **Cerrar**.

### <a name="create-a-device-collection"></a>Crear una colección de dispositivo
Después de crear la secuencia de tareas de actualización, debe crear una colección que contiene los dispositivos que se va a actualizar.

> [!NOTE]
> Use la siguiente configuración para probar la implementación en un único dispositivo. Puede usar las reglas de pertenencia diferentes para incluir grupos de dispositivos cuando esté listo. Para obtener más información, vea [cómo crear colecciones en System Center Configuration Manager](https://aka.ms/sccm-create-collections).

1. En la consola de Configuration Manager, en el área de trabajo **activos y cumplimiento** , haga clic en **Las colecciones de dispositivo**y, a continuación, seleccione **Crear colección de dispositivo**. 
2. En el Asistente para crear la colección de dispositivo, en la página **General** , escriba las siguientes opciones y, a continuación, seleccione **siguiente**:
    - Nombre: Windows 10 Enterprise x64 actualización
    - Colección de límites: Todos los sistemas de
3. En la página **Reglas de pertenencia** , seleccione **Agregar regla de** > **regla directa** para iniciar el Asistente para crear reglas de pertenencia directa.
4. En la página de **bienvenida** del Asistente para crear reglas de pertenencia directa, seleccione **siguiente**.
5. En la página de **búsqueda de recursos** , especifique la siguiente configuración, reemplazando el texto del **valor** del marcador de posición con el nombre del dispositivo que se va a actualizar: 
    - Clase de recurso: Recursos del sistema
    - Nombre de atributo: nombre
    - Valor: *PC0003*
6. En la página **Seleccionar recursos** , seleccione el dispositivo y seleccione **siguiente**.
7. Complete el Asistente para crear reglas de pertenencia directa y el Asistente para crear la colección de dispositivo.  
8. Revisión de la colección de actualización de Windows 10 Enterprise x64. No continúe hasta que vea las máquinas que agregó en la colección.

### <a name="create-an-operating-system-deployment"></a>Creación de una implementación de sistema operativo
Siga estos pasos para crear una implementación de la secuencia de tareas.

1. En la consola de Configuration Manager, en el área de trabajo de la **Biblioteca de Software** , haga clic en la secuencia de tareas que creó en un paso anterior y, a continuación, seleccione **implementar**.
2. En la página **General** , seleccione la colección **Windows 10 Enterprise x64 de actualización** y, a continuación, seleccione **siguiente**.
3. En la página de **contenido** , seleccione **siguiente**.
4. En la página **Configuración de la distribución** , seleccione las siguientes opciones y, a continuación, seleccione **siguiente**:

    > [!NOTE]
    > Para esta implementación de prueba, se configuran el propósito a **disponible**, lo que requiere la intervención del usuario para iniciar la implementación. En un entorno de producción, es posible que desee automatizar la implementación con el propósito necesario, que consiste en configurar opciones adicionales, como la programación cuando se ejecute la implementación. 

    - Acción: instalar
    - Propósito: disponibles

5. En la página **programación** , acepte la configuración predeterminada y, a continuación, seleccione **siguiente**.
6. En la página de la **Experiencia del usuario** , acepte la configuración predeterminada y, a continuación, seleccione **siguiente**.
7. En la página **alertas** , acepte la configuración predeterminada y, a continuación, seleccione **siguiente**.
8. En la página de **Resumen** , seleccione **siguiente**y, a continuación, seleccione **Cerrar**.

## <a name="part-5-start-the-windows-10-upgrade-task-sequence"></a>Parte 5: Secuencia de actualización de tareas de inicio el 10 de Windows
Siga estos pasos para iniciar la secuencia de tareas de Windows 10 Upgrade en el dispositivo que va a actualizar.
 
1. Inicie sesión en el equipo de Windows e inicie el **Centro de Software**.
2. Seleccione la secuencia de tareas que ha creado en un paso anterior y, a continuación, seleccione **instalar**.
3. Cuando se inicia la secuencia de tareas, inicia automáticamente el proceso de actualización en contexto al invocar el programa de instalación de Windows (Setup.exe) con los parámetros de línea de comandos necesarios para llevar a cabo una actualización automatizada, que conserva todos los datos, configuración, aplicaciones, y controladores.
4. Una vez completada correctamente la secuencia de tareas, el equipo se actualizarán totalmente a 10 de Windows.

Si experimenta problemas con el 10 de Windows en un entorno empresarial, puede consultar [las mejores soluciones de soporte técnico de Microsoft para los problemas más comunes](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions). Estos recursos incluyen artículos KB, actualizaciones y artículos de la biblioteca.

Durante la implantación de las actualizaciones a través de su organización, use la capacidad de actualización de cumplimiento de normas de análisis de Windows para proporcionar una vista integral de cumplimiento de normas de actualización del sistema operativo, progreso de actualización de la implementación y error de solución de problemas de dispositivos de Windows 10. Este nuevo servicio usa datos incluidos progreso de la instalación, configuración de Windows Update y otra información de diagnóstico para proporcionar dichas perspectivas, sin ningún costo adicional y sin requisitos de infraestructura adicional. Si se usa con Windows Update para profesionales u otras herramientas de administración, puede estar seguro de que sus dispositivos se actualizan correctamente.

Consulte [Monitor de actualizaciones de Windows y Windows Defender Antivirus con compatibilidad con las actualizaciones a obtener más información, empezar a usar la compatibilidad con las actualizaciones.](https://docs.microsoft.com/windows/deployment/update/update-compliance-monitor)

Como control provisional, puede consultar los [criterios de salida](windows10-exit-criteria.md#crit-windows10-step2) correspondientes a este paso.

## <a name="next-step"></a>Paso siguiente

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [Implementar Enterprise del 10 de Windows para los nuevos dispositivos con piloto automático de Windows](windows10-deploy-autopilot.md) |



<!--

| Phases | Description |
|:--- |:--- |
| [Phase 1: Consideration phase](#phase-1-consideration-phase) | TBD |
| [Phase 2: Testing phase](#phase-2-testing-phase) | TBD |
| [Phase 3: Deployment phase](#phase-3-deployment-phase) | TBD |

## Phase 1: Consideration phase
Before upgrading an OS in an enterprise environment, take the following technical aspects into account:
* [Infrastructure](#step-1-infrastructure)
* [Apps](#step-2-apps)
* [Governance and business processes](#step-3-governance-and-business-processes)

This guide is meant only to provide Microsoft's best recommendations around these assumptions by providing links to existing documentation.

### Step 1: Infrastructure
Consider your organization's collection of hardware, software, policies, networks, and other related technologies as part of the deployment process.

For in-place upgrade with Configuration Manager, these are the infrastructure you need to take into account:

#### Group Policy
Windows 10 introduces many new features and removes and changes many others in Windows 7 and 8.1, including new Group Policy settings which you need to test and implement as part of a Windows 10 migration. Use the examples from the following resources to assess current group policies for Windows, including Group Policy Objects in the Active Directory structure:
* [Manage Windows 10 with administrative templates](https://go.microsoft.com/fwlink/?linkid=860226) - Get step-by-step info on how to manage Windows 10 with administrative templates
* [Group Policy settings that apply to Windows 10](https://docs.microsoft.com/windows/client-management/group-policies-for-enterprise-and-education-editions) - Find out which Group Policy settings apply only to Windows 10 Enterprise

> [!NOTE]
> If you are considering moving to modern management by using MDM instead of Group Policy to manage device configurations, you can start by using the [MDM Migration Analysis Tool (MMAT)](https://github.com/WindowsDeviceManagement/MMAT) to determine what Group Policies are set on the device and report the corresponding settings, if available.

#### Data management
Although in-place upgrades shouldn’t affect user data and apps, a best practice is to configure a backup scenario and back up user data. For example, export all user data to a OneDrive for Business account, BitLocker To Go-encrypted USB flash drive, or network file server. For more details, see:
* [How to back up or transfer your data on a Windows-based computer](https://go.microsoft.com/fwlink/?linkid=860230) - Get step-by-step info on how to manually back up your personal files and settings.
* [Redirect known folders to OneDrive for Business](https://go.microsoft.com/fwlink/?linkid=846620) - Learn how to set a policy at the domain level to make sure users all sync to the same folder when they install the OneDrive sync client and how you can set additional policies to redirect the Documents folder to that sync location.

#### System Center Configuration Manager
This guide assumes you are following Microsoft recommendations and have one of the following versions of System Center Configuration Manager 2012 onward:
* System Center 2012 Configuration Manager with SP2
* System Center 2012, 2012 R2 Configuration Manager with SP1, Current Branch, 1706
    * [Run an in-place upgrade to the latest Configuration Manager](https://go.microsoft.com/fwlink/?linkid=839406)
    * [Updates for Configuration Manager](https://go.microsoft.com/fwlink/?linkid=620343)
* Core Configuration Manager configuration:
    * CONFIGURATION MANAGER accounts
    * Active Directory permissions
    * Source folder structure
    * Active Directory schema
* Configure the following [necessary Configuration Manager components for Windows 10 deployment](https://go.microsoft.com/fwlink/?linkid=860245):
    * **State migration point** - Stores user state migration data during computer replace scenarios
    * **Distribution point** - Stores all packages in Configuration Manager
    * **Software update point** - Updates an OS as part of the deployment process
    * **Reporting services point** - Monitors the OS deployment process
    * **Boot images** - Are Windows Preinstallation Environment (PE) images used by Configuration Manager to start deployments
    * **OS images** - Denotes the production deployment image (mounted OS)
    * **OS installers** - Creates reference images using Microsoft Deployment Toolkit (MDT) Light Touch
    * **Drivers** - Denotes a repository of managed device drivers
    * **Task Sequence** - Is delivered automatically to the client as a policy

#### Network bandwidth
This guide assumes you have enough network bandwidth to support the deployment of Windows 10 Enterprise and Office 365 ProPlus as a unit. As a bundle, network bandwidth is a significant factor.

#### Client machines and in-place upgrade scenario
* Disk encryption - Third-party disk encryption isn't supported in an in-place upgrade scenario.
* User profiles - Only the standard user profile type is supported.
* Legacy BIOS to Unified Extensible Firmware Interface (UEFI) booting - Changing from legacy BIOS to UEFI booting isn't supported.
* Dual-boot - This scenario is not covered in the guide. If you have the FastTrack Benefit, it only covers devices running a single OS.
* Virtual desktop infrastructure (VDI) environments - This scenario is not covered in the guide. If you have the FastTrack Benefit, it doesn't cover configuration or deployment on VDI environments.
* x64 and x86 - Changing from a 32-bit OS to a 64-bit isn't supported. For more info, see [Windows 10 deployment scenario > In-place upgrade](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios#in-place-upgrade).

### Step 2: Apps

#### Security
Security clients (like antivirus, anti-malware, and anti-spam) are typically found on all PCs within an organization. Because these programs hook into the deeper levels of the OS, you may need to perform a compatibility assessment before starting any Windows 10 migrations. You may need to upgrade, reconfigure, or even replace Some software. Not performing this assessment can lead to:
* Native app compatibility checks failing and preventing an in-place upgrade from starting.
* Broken functionality in the security software.
* Instability after upgrading to Windows 10 (like crashing and reduced performance)

**Antivirus**

Assess current antivirus software. Windows 10 comes with Windows Defender Antivirus to protect devices from malware, viruses, and security threats. We recommend Windows Defender Antivirus. To enable Windows Defender Antivirus, see [Windows Defender Antivirus](windows10-enable-security-features.md#windows-defender-antivirus) and [Protect devices with Windows Defender Antivirus](https://go.microsoft.com/fwlink/?linkid=860254).

To learn about antivirus solutions from other providers, see [Consumer antivirus software providers for Windows](https://go.microsoft.com/fwlink/?linkid=67345).

#### App readiness
Each Windows 10 release provides improved app compatibility. However, some apps may not be compatible. Depending on the app, you may need to only do a simple upgrade or configuration update before upgrading to Windows 10. In other circumstances, you may need to remove an app entirely.

Be sure to assess business critical apps and understand the impact of upgrading to the next OS. Prioritize the workloads that impact the least number of people during deployment. 

See the following Upgrade Readiness resources to help with app inventory, driver compatibility issues, and usage information:
* [Manage Windows Upgrades with Upgrade Readiness](https://go.microsoft.com/fwlink/?linkid=860255) - Learn about the tools to help you plan and manage the upgrade process end to end, which allow you to adopt new Windows releases more quickly.
* [Configure Windows diagnostic data](https://go.microsoft.com/fwlink/?linkid=859970) - Find out about the importance of Windows diagnostic data and how Microsoft protects that data.

> [!NOTE]
> Upgrade Readiness may not be able to assess compatibility for custom and line-of-business (LOB) apps in an organization.

#### Language packs
In-place upgrades have have limitations when it comes to language packs. The language stays consistent throughout the upgrade. Verify the language version and make sure it stays consistent. For example, Windows 7 with English as the default won’t change when upgraded to Windows 10. For more info, see:
* [Default language pack on your OS](https://go.microsoft.com/fwlink/?linkid=860282)
* [Finding language packs on each Windows 10 deployment](https://go.microsoft.com/fwlink/?linkid=860283)

For a Microsoft 365 powered device, you'll also need to download Office 365 ProPlus language packs that applies to the client. These come in 32-bit (x86) or 64-bit (x64). A specific language must be installed as the default. You can install other languages later. For more info, see:
* [Choose between 64-bit or 32-bit version of Office](https://go.microsoft.com/fwlink/?linkid=862361) - Helps you decide which version of Office is right for you.
* [Language accessory pack for Office](https://go.microsoft.com/fwlink/?linkid=860280) - Follow the steps to install the language accessory pack for Office.
* [Add an additional language pack](https://go.microsoft.com/fwlink/?linkid=860281) - Get step-by-step info on adding a language or setting language preferences in Office.

### Step 3: Governance and business processes

#### Windows as a service
Windows 10 introduced the concept of Windows as a service. This greatly changes the frequency and style of updates to Windows. Instead of new versions being released every 3-5 years, a more incremental model is used where two smaller updates (Feature Updates) are released yearly. For more info, see:
* [Windows as a service on the Windows IT Pro Center](https://www.microsoft.com/itpro/windows-10/windows-as-a-service)
* [Overview of Windows as a service](https://go.microsoft.com/fwlink/?linkid=860288)
* [Update Windows 10 in the enterprise](https://go.microsoft.com/fwlink/?linkid=860285)

#### Pilot users and deployment rings
Be sure to have a pilot group of users selected from different parts of the business. If you have Microsoft 365 powered devices, Windows 10 and Office 365 ProPlus users should be in these deployment rings. This affects future Windows updates as well (including features and quality). You need to create and edit device collections by deployment rings to help minimize the effect on network bandwidth and simplify future updates. 

For the group of pilot users, create a device collection on Configuration Manager. The list of devices should correspond to the list of the first users upgraded to Windows 10. 

**Windows 10 deployment rings**

There are three servicing channels for OS deployment rings:
* Windows Insider Program - Provides organizations with the opportunity to test and provide feedback on features that are shipped in the next feature update.
* Semi-Annual Channel - Provides new functionality with twice-per-year feature update releases. Organizations can choose when to deploy updates from the Semi-Annual Channel.
* Long-Term Servicing Channel (LTSC) - Used for specialized devices and receives new feature releases about every three years.

For more info, see:
* [Windows Insider Program, Semi-Annual Channel, and Long-Term Servicing Channel](https://go.microsoft.com/fwlink/?linkid=860293)
* [Build deployment rings for Windows 10 updates](https://go.microsoft.com/fwlink/?linkid=860294)
* [Manage software updates using Intune in Azure Portal](https://docs.microsoft.com/intune/windows-update-for-business-configure)

**Office 365 ProPlus**

For Microsoft 365 powered devices, you must also be able to support the six-month update channel for both IT and business users. One way to do so is to have three groups:
* Current Channel
* Deferred Channel
* First-release for Deferred Channel

Each group has different configuration files, as users from the Current Channel are used as a pilot to test earlier updates. For more info, see:
* [Update process for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860299)
* [Manage updates to Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860300)
* [Configure update settings for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860301)
* [Update channels for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860302)
* [Version and build numbers of update channel releases](https://go.microsoft.com/fwlink/?linkid=860304)

For more info, see [Phase 4: Office 365 ProPlus infrastructure for Microsoft 365 Enterprise](office365proplus-infrastructure.md).

## Phase 2: Testing phase
Once you've completed the scenarios and requirements in [Step 1: Consideration phase](#step-1-consideration-phase), you can move to this stage.
* [Networking](#step-1-networking)
* [Identity](#step-2-identity)
* [Client readiness](#step-3-client-readiness)
* [System Center Configuration Manager](#step-4-system-center-configuration-manager)
* [Diagnostic data](#step-5-diagnostic-data)

### Step 1: Networking
Ports to the client need to be opened for Office 365 ProPlus (for a Microsoft 365 powered device) and Configuration Manager. For more details about setting up your Microsoft 365 Enterprise networking infrastructure, see [Phase 1: Networking](networking-infrastructure.md).

When setting up your networking infrastructure as part your in-place upgrade, make sure you complete these steps:
1. Read the best practices for [network planning and improving migration performance for Office 365](http://go.microsoft.com/fwlink/?LinkId=733655).
2. [Plan for network devices that connect to Office 365 services](http://go.microsoft.com/fwlink/?LinkId=733652).
3. [Review network impact of directory synchronization](http://go.microsoft.com/fwlink/?LinkId=733652).
4. Calculate the number of clients to use per IP address and understand [Network Address Translation (NAT) support with Office 365](http://go.microsoft.com/fwlink/?LinkId=733653) and how it impacts the number of users and client devices you can serve with a single IP address.
5. If your organization restricts computers on your network from connecting to the Internet, you'll need to understand the [endpoints (fully qualified domain names (FQDNs), ports, URLs, IPv4, and IPv6 address ranges)](http://go.microsoft.com/fwlink/?LinkID=280129) that you should include in your outbound allow lists to ensure your computers can successfully use Office 365 services.
6. [Create domain name system records for Office 365 at any Domain Name System hosting provider](http://go.microsoft.com/fwlink/?LinkId=733656).
7. [Reduce mail exchange (MX) DNS record time to live (TTL) value](http://go.microsoft.com/fwlink/?LinkId=733656).

### Step 2: Identity
Intelligent security for Microsoft 365 Enterprise, in which the right users have access to the right resources with an appropriate level of access, begins with identity management. For more details about setting up your Microsoft 365 Enterprise identity infrastructure, see [Phase 2: Identity](identity-infrastructure.md).

When setting up your identity infrastructure as part of your in-place upgrade, make sure you complete these tasks:
1. [Add a domain and users to Office 365](http://go.microsoft.com/fwlink/?LinkID=526338).
2. [Install and run the Office 365 IdFix tool](http://go.microsoft.com/fwlink/?LinkId=733662), which scans your on-premises Active Directory environment and identifies problems that might impact directory synchronization and slow your migration to Office 365.
3. Configure Active Directory for directory synchronization with Office 365 and [integrate on-premises directories with Azure AD](http://go.microsoft.com/fwlink/?LinkId=733661).
4. [Prepare to provision users through directory synchronization to Office 365](http://go.microsoft.com/fwlink/?LinkId=733659).
5. Know the [prerequisites for Azure AD Connect](http://go.microsoft.com/fwlink/?LinkId=733663), then install and run the Azure AD Connect tool to synchronize your on-premises Active Directory to the Azure AD service used by Office 365.
6. Determine custom installation of Azure AD Connect (full version of SQL Server for directory synchronization, if required).
7. [Integrate your on-premises identities with Azure AD](http://go.microsoft.com/fwlink/?LinkID=733485).
8. [Sync a list of required attributes with AD Connect](https://go.microsoft.com/fwlink/?linkid=860363) to get all the features in Office 365 and Windows 10.
9. Activate Windows 10 Enterprise licenses, which are checked based on Azure AD credentials.

    This provides a systematic way to assign licenses to end users and groups in your organization. For more info, see [Windows 10 Subscription Activation](https://go.microsoft.com/fwlink/?linkid=860365) and [Deploy Windows 10 licenses](https://go.microsoft.com/fwlink/?linkid=860367).

### Step 3: Client readiness

#### System requirements for Office 365
Confirm that Windows 10 works with Office 365. Be sure you're using the latest OS version and browsers with Office 365 and have updated them with the latest service packs. For more info on Office requirements, see [System requirements for Office](http://go.microsoft.com/fwlink/?LinkID=394412).

### Step 4: System Center Configuration Manager
See [System Center Configuration Manager](#system-center-configuration-manager).

### Step 5: Diagnostic data
Microsoft uses diagnostic data to help keep Windows devices secure by identifying malware trends and other threats and to help us improve the quality of Windows and Microsoft services. You must ensure that the diagnostics service is enabled at a minimum level of Basic on all endpoints in your organization. **By default, this service is enabled and set to the Enhanced level.** However, it’s good practice to check and ensure that they are receiving sensor data. Setting levels through policies overrides device-level settings. 

**Windows 10 operating system diagnostic data levels**

You can configure your operating system diagnostic data settings using the management tools you’re already using, such as Group Policy, MDM, or Windows Provisioning. You can also manually change your settings using Registry Editor. Setting your diagnostic data levels through a management policy overrides any device level settings.

Use the appropriate value in the table below when you configure the management policy.

| Level | Data gathered | Value |
|:--- |:--- |:--- |
| Security | Security data only. | 0 |
| Basic | Security data, and basic system and quality data. | 1 |
| Enhanced | Security data, basic system and quality data, and enhanced insights and advanced reliability data. | 2 |
| Full | Security data, basic system and quality data, enhanced insights and advanced reliability data, and full diagnostics data. | 3 |

You can enable diagnostics data through these methods:
* Microsoft Intune - If you plan to use Intune to manage your devices, you can create a configuration policy to enable diagnostic data by configuring the <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a> system policy. For more info on setting up configuration policies, see [Manage settings and features on your devices with Microsoft Intune policies](https://aka.ms/intuneconfigpolicies).
* Registry Editor - You can use the Registry Editor to manually enable diagnostic data on each device in your organization, or write a script to edit the registry. If a management policy already exists, such as Group Policy or MDM, it will override this registry setting.
* Group Policy - If you do not plan to enroll devices in Intune, you can use a Group Policy object to set your organization’s diagnostic data level.
* Command prompt - You can set Windows 10 diagnostics data and service to automatically start with the command prompt. This method is best if you are testing the service on only a few devices. Enabling the service to start automatically with this command will not configure the diagnostic data level. If you have not configured a diagnostic data level using management tools, the service will operate with the default Enhanced level.

See [Configure Windows diagnostic data in your organization](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) to learn more about Windows diagnostic data and how you can enable it based on the method that you choose.

## Phase 3: Deployment phase
When ready, complete these:
* [In-place upgrade to Windows 10 Enterprise](#31-in-place-upgrade-to-windows-10-enterprise)
* [Windows Defender Antivirus](#32-windows-defender-antivirus)

### Step 1: In-place upgrade to Windows 10 Enterprise
1. Integrate System Center Configuration Manager with Microsoft Deployment Tool.

    Be sure to use the Microsoft Deployment Toolkit (MDT) in conjunction with Configuration Manager when deploying an updated version of Windows 10. MDT brings Zero Touch Installation and Light Touch Installation enhancements to help with deployments at no cost to the customer. For more info, see:
    * [Download the latest MDT](https://go.microsoft.com/fwlink/?linkid=860465)
    * [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://go.microsoft.com/fwlink/?linkid=860466)

2. Prepare for zero touch installation.

    As part of zero touch installation, you are responsible for preparing the following:
    * Configuration Manager service accounts
    * Active Directory permissions
    * Source folder structure

    Then, [integrate Configuration Manager with MDT](https://go.microsoft.com/fwlink/?linkid=860035).

3. Create a custom Windows Preinstallation Environment boot image.

    Windows Preinstallation Environment (PE) is a pre-installation environment required for OS deployments. It’s used to prepare a client machine for Windows installation, to copy disk images from a network file server, and to initiate Windows Setup. It’s used for Windows 10 Enterprise editions. For more info, see:
    * [Overview of Windows PE](https://go.microsoft.com/fwlink/?linkid=860468)
    * [Windows PE features, hardware requirements, and limitations](https://go.microsoft.com/fwlink/?linkid=860469)
    * [Create a custom Windows PE boot image with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860470)

4. Add a Windows 10 OS upgrade image.

    You need to create a Windows 10 reference image with MDT (as needed). Reference images are the foundation of what each of the client machine’s OS looks like. The image should be in a separate folder located with the already-mounted ISO file. The task sequence looks for and then runs “setup.exe”. 

    Follow the steps to create and add a Windows 10 OS upgrade image on Configuration Manager:
    * [Create a Windows 10 reference image](https://go.microsoft.com/fwlink/?linkid=860500)
    * [Add a Windows 10 OS image using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860501)

5. Create an app to deploy with Windows 10.

    For a Microsoft 365 powered device, you can deploy Office 365 ProPlus with Windows 10 Enterprise using Configuration Manager. You can also add other apps as needed.

    To deploy Office 365 ProPlus, follow the steps in [Phase 4: Office 365 ProPlus infrastructure for Microsoft 365 Enterprise](office365proplus-infrastructure.md). During this phase, make sure you complete these steps:
    
    1. Download the Office 2016 Deployment Tool (ODT) in conjunction with Configuration Manager to help with Office 365 ProPlus deployments. 
    2. Edit the configuration XML file to fit specific deployment needs (like version, language, and product element). 
    
    You can then create apps with Configuration Manager. For more info, see:
    * [Configuration options for ODT](https://go.microsoft.com/fwlink/?linkid=860504)
    * [Create apps in Configuration Manager](https://go.microsoft.com/fwlink/?linkid=761079)
    * [Deploy Office 365 ProPlus with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860506)

6. Add drivers to a Windows 10 deployment using Windows PE.

    Network drivers need to be created for both Windows PE and Windows 10 to connect deployment shares and storage drivers with local storage on a client computer. Use Configuration Manager to create these drivers required for deployment. For more info, see [Add drivers to a Windows 10 deployment with Windows PE using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860036).

7. Create a task sequence.

    A task sequence (a collection of commands) is required for MDT Lite Touch Installation (LTI). You need to create and then edit the task sequence for optimal deployment experience. One of the configurations enable support for Unified Extensible Firmware Interface (UEFI). The UEFI environment is a minimal boot OS where devices are booted and the Windows 10 OS runs. For more info, see:
    * [Overview of Windows Boot Manager](https://go.microsoft.com/fwlink/?linkid=860696)
    * [Create the task sequence in Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697)

8. Finalize the OS configuration for Windows 10 deployment.

    **To finalize the OS configuration**

    1. Enable MDT monitoring
    2. Create and share the Logs folder
    3. Configure the rules
    4. Distribute content to the distribution point (a server running Configuration Manager)
    5. Create a deployment for the task sequence

   For more info, see [Finalize OS configuration with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697).

9. Deploy the Windows 10 Enterprise image to a UEFI machine.

    For more info, see [Deploy Windows 10 using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697).

10. Monitor the Windows 10 deployment.

    Use Configuration Manager and MDT to monitor your deployment. Deployment Workbench enables access to the computer remotely using the Diagnostics and Recovery Toolset (DaRT) (optional). Deployments can be monitored in Configuration Manager. For more info, see [Monitor the Windows 10 deployment with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860705).

### Step 2: Windows Defender Antivirus
See [Enable Windows 10 Enterprise security features > Windows Defender Antivirus](windows10-enable-security-features.md#windows-defender-antivirus)

-->
