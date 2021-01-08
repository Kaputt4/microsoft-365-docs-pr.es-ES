---
title: Información adicional del dispositivo para la migración desde Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Resumen: información adicional del dispositivo sobre los servicios al pasar de Microsoft Cloud Alemania (Microsoft Cloud Deutschland) a los servicios de Office 365 en la nueva región del centro de datos alemán.'
ms.openlocfilehash: 151fcac882dc91d96df3ece000c28d1a7abe1d1f
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780301"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Información adicional del dispositivo para la migración desde Microsoft Cloud Deutschland

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

**¿Cómo puedo saber si mi organización se ve afectada?**

Los administradores deben `https://portal.microsoftazure.de` comprobar si tienen dispositivos registrados. Si su organización ha registrado dispositivos, se verá afectado.

**¿Cuál es el impacto en mis usuarios?**

Los usuarios de un dispositivo registrado ya no podrán iniciar sesión después de que la migración entre en la fase de migración de [Finalizar Azure AD.](ms-cloud-germany-transition.md#how-is-the-migration-organized)  

Asegúrate de que todos los dispositivos estén registrados con el punto de conexión mundial antes de que la organización se desconecte de Microsoft Cloud Deutschland.
  
**¿Cuándo los usuarios vuelven a registrar sus dispositivos?**

Es fundamental para su éxito que solo anula el registro y vuelva a registrar los dispositivos durante la fase de migración independiente [de Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)

**¿Cómo restaure el estado de mi dispositivo después de la migración?**

En el caso de los dispositivos Windows híbridos unidos a Azure AD y pertenecientes a la empresa que están registrados con Azure AD, los administradores podrán administrar la migración de estos dispositivos a través de flujos de trabajo activados de forma remota que anularán el registro de los estados de dispositivo antiguos.
  
Para todos los demás dispositivos, incluidos los dispositivos Personales de Windows registrados en Azure AD, el usuario final debe realizar estos pasos manualmente. Para los dispositivos unidos a Azure AD, los usuarios deben tener una cuenta de administrador local para anular el registro y volver a registrar sus dispositivos.

Microsoft publicará instrucciones sobre cómo restaurar correctamente el estado del dispositivo. 
 
**¿Cómo sé que todos mis dispositivos están registrados en la nube pública?**

Para comprobar si los dispositivos están registrados en la nube pública, debe exportar y descargar la lista de dispositivos desde el portal de Azure AD a una hoja de cálculo de Excel. A continuación, filtre los dispositivos registrados (mediante la columna _registeredTime)_ después de la fase de migración Independiente [de Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)

El registro de dispositivos se desactiva después de la migración del inquilino y no se puede habilitar ni deshabilitar. Si no se usa Intune, inicie sesión en la suscripción y ejecute este comando para volver a activar la opción:

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="hybrid-azure-ad-join"></a>Unión a Azure AD híbrido

### <a name="windows-down-level"></a>Nivel inferior de Windows

Los dispositivos de nivel inferior de _Windows_ son dispositivos Windows que actualmente ejecutan versiones anteriores de Windows (como Windows 8.1 o Windows 7) o que ejecutan versiones de Windows Server anteriores a 2019 y 2016. Si dichos dispositivos se registraron antes, tendrás que anular el registro y volver a registrar esos dispositivos. 

Para determinar si un dispositivo de nivel inferior de Windows se ha unido previamente a Azure AD, usa el siguiente comando en el dispositivo:

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

Si el dispositivo se unió previamente a Azure AD y el dispositivo tiene conectividad de red a puntos de conexión globales de Azure AD, vería los siguientes resultados:

```console
+----------------------------------------------------------------------+
| Device Details                                                       |
+----------------------------------------------------------------------+
         DeviceId : AEE2B956-DA62-48D0-BB47-046DD992A110
       Thumbprint : 00fdfa2de5c32feae57489873a13aa6a3ff7433b
             User : user1@<tenantname>.de
Private key state : Okay
     Device state : Unknown
```

Los dispositivos afectados tendrán el "Estado del dispositivo" con el valor "Desconocido". Si el resultado es "Dispositivo no unido" o cuyo valor de "Estado del dispositivo" es "Correcto", omite las siguientes instrucciones.

Solo para dispositivos que muestran que el dispositivo está unido (en virtud de deviceId, huella digital, entre otros) y cuyo valor de "Estado del dispositivo" es "Desconocido", los administradores deben ejecutar el siguiente comando en el contexto de un usuario de dominio que inicie sesión en un dispositivo de nivel inferior:

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

El comando anterior solo debe ejecutarse una vez por usuario de dominio que inicie sesión en el dispositivo de nivel inferior de Windows. Este comando debe ejecutarse en el contexto del inicio de sesión del usuario del dominio. 

Debe tenerse suficiente cuidado para no ejecutar este comando cuando el usuario inicia sesión posteriormente. Cuando se ejecute el comando anterior, borrará el estado unido del equipo híbrido local unido a Azure AD para el usuario que llegó a sesión. Además, si el equipo aún está configurado para unirse a Azure AD híbrido en el inquilino, intentará unirse cuando el usuario vuelva a inicio de sesión.

### <a name="windows-current"></a>Windows Current

#### <a name="unjoin"></a>Unjoin

Para determinar si el dispositivo Windows 10 se ha unido previamente a Azure AD, ejecuta el siguiente comando en el dispositivo:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Si el dispositivo está unido a Azure AD híbrido, el administrador vería el siguiente resultado:

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

Si el resultado es "AzureAdJoined : No", ignore las siguientes instrucciones.

Solo para dispositivos que muestran que el dispositivo está unido a Azure AD, ejecuta el siguiente comando como administrador para quitar el estado unido del dispositivo.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

El comando anterior solo debe ejecutarse una vez en un contexto administrativo en el dispositivo Windows.

#### <a name="hybrid-ad-joinre-registration"></a>Unión a AD híbrida\Nuevo registro

El dispositivo se une automáticamente a Azure AD sin la intervención del usuario o administrador, siempre y cuando el dispositivo tenga conectividad de red a los puntos de conexión globales de Azure AD. 


## <a name="azure-ad-join"></a>Unión a Azure AD

**IMPORTANTE:** La entidad de servicio de Intune se habilitará después de la migración comercial, lo que implica la activación del registro de dispositivos de Azure AD. Si bloqueó el registro de dispositivos de Azure AD antes de la migración, debe deshabilitar la entidad de servicio de Intune con PowerShell para volver a deshabilitar el registro de dispositivos de Azure AD con el portal de Azure AD. Puede deshabilitar la entidad de servicio de Intune con este comando en el módulo de Azure Active Directory PowerShell para Graph.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a>Unjoin

Para determinar si el dispositivo Windows 10 se unió anteriormente a Azure AD, el usuario o administrador puede ejecutar el siguiente comando en el dispositivo:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Si el dispositivo está unido a Azure AD, el usuario o administrador vería el siguiente resultado:

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

Si el resultado es "AzureAdJoined : NO", ignore las siguientes instrucciones.

Usuario: si el dispositivo está unido a Azure AD, un usuario puede deshacer la conexión del dispositivo de la configuración. Comprueba que hay una cuenta de administrador local en el dispositivo antes de deshacer la conexión del dispositivo desde Azure AD. La cuenta de administrador local es necesaria para volver a iniciar sesión en el dispositivo.

Administrador: si el administrador de la organización desea deshacer la conexión de los dispositivos de los usuarios que están unidos a Azure AD, puede hacerlo ejecutando el siguiente comando en cada uno de los dispositivos mediante un mecanismo como la directiva de grupo. El administrador debe comprobar que hay una cuenta de administrador local en el dispositivo antes de deshacer la conexión del dispositivo de Azure AD. La cuenta de administrador local es necesaria para volver a iniciar sesión en el dispositivo.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

El comando anterior solo debe ejecutarse una vez en un contexto administrativo en el dispositivo Windows. 

### <a name="azure-ad-joinre-registration"></a>Unión o nuevo registro de Azure AD

El usuario puede unir el dispositivo a Azure AD desde la configuración de Windows: Configuración > cuentas > acceso a trabajo **o escuela > conectarse.**
 

## <a name="azure-ad-registered-company-owned"></a>Azure AD Registrado (propiedad de la compañía)

Para determinar si el dispositivo windows 10 está registrado en Azure AD, ejecuta el siguiente comando en el dispositivo:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Si el dispositivo está registrado en Azure AD, verá el siguiente resultado:

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

Para quitar la cuenta registrada de Azure AD existente en el dispositivo:

- Para quitar la cuenta registrada de Azure AD en el dispositivo, usa CleanupWPJ, una herramienta que puedes descargar desde aquí: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).

- Extraiga el archivo ZIP y ejecute **WPJCleanup.cmd**. Esta herramienta iniciará el archivo ejecutable correcto en función de la versión de Windows en el dispositivo.

- Mediante el uso de un mecanismo como la directiva de grupo, el administrador puede ejecutar el comando en el dispositivo en el contexto de cualquier usuario que haya iniciado sesión en el dispositivo.

Para deshabilitar los mensajes del Administrador de cuentas web para registrar el dispositivo en Azure AD, agrega este valor del Registro: 

- Ubicación: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin
- Tipo: DWORD (32 bits)
- Nombre: BlockAADWorkplaceJoin
- Datos de valor: 1

La presencia de este valor del Registro debe bloquear la unión al lugar de trabajo e impedir que los usuarios vean avisos para unirse al dispositivo.

## <a name="android"></a>Android

Para Android, los usuarios tendrán que anular el registro y volver a registrar sus dispositivos. Esto se puede hacer a través de la aplicación Microsoft Authenticator o la aplicación Portal de empresa. 

- Desde la aplicación Microsoft Authenticator, los usuarios pueden ir **a Configuración > registro de dispositivos.** Desde allí, los usuarios pueden anular el registro y volver a registrar su dispositivo.
 
- Desde el Portal de empresa, los usuarios pueden ir a **la pestaña Dispositivos** y quitar el dispositivo. Después, vuelve a inscribir el dispositivo mediante el Portal de empresa.
 
- Los usuarios también pueden anular el registro y volver a registrarse quitando la cuenta de la página de configuración de la cuenta y, a continuación, agregando de nuevo la cuenta de trabajo.

Para anular el registro y volver a registrar el dispositivo en Android mediante la aplicación Microsoft Authenticator:

1.  Abra la aplicación Microsoft Authenticator y vaya a **Configuración.**
2.  Seleccione **Registro de dispositivos.**
3.  Anula el registro del dispositivo seleccionando **Anular registro.**
4.  Para **el registro de** dispositivos, vuelva a registrar el dispositivo escribiendo su dirección de correo electrónico y, a continuación, seleccione **Registrar.**

Para anular el registro y volver a registrar un dispositivo Android con la página Configuración de Android:

1.  Abra **Configuración del dispositivo** y vaya a **Cuentas.**
2.  Seleccione la cuenta de trabajo que desea volver a registrar y seleccione **Quitar cuenta.**
3.  Después de quitar la cuenta, en la **página Cuentas,** seleccione Agregar **cuenta > cuenta de trabajo.**
4.  Para **Workplace Join,** escriba su dirección de correo electrónico y seleccione **Unirse** para completar el registro del dispositivo.

Para anular el registro y volver a registrar el dispositivo en Android desde el Portal de empresa:

1.  Inicie el Portal de empresa y vaya a **la pestaña Dispositivos.**
2.  Selecciona el dispositivo para ver los detalles del dispositivo.
3.  En el menú de puntos suspensivos (tres puntos), selecciona Quitar dispositivo y completa la eliminación confirmando en el cuadro de diálogo. 
4.  Ahora debería haber cerrado sesión en la aplicación Portal de empresa. Selecciona **Iniciar sesión** para volver a registrar el dispositivo.

Para obtener más información sobre las acciones necesarias durante la fase de migración de esta carga de trabajo, o el impacto en la administración o el uso, revise la información sobre Azure Active Directory (Azure AD) en información adicional de Azure AD para la migración desde [Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).

## <a name="ios"></a>iOS

En dispositivos iOS, un usuario tendrá que quitar manualmente las cuentas almacenadas en caché de Microsoft Authenticator, anular el registro del dispositivo y cerrar la sesión de cualquier aplicación nativa del dispositivo.

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>Paso 1: Si está presente, quite la cuenta de la aplicación Microsoft Authenticator

1. Pulse la cuenta en la aplicación Microsoft Authenticator.
2. Puntee en **el icono** Configuración de la esquina superior derecha. Si no ve el icono **Configuración,** es posible que no esté usando la versión más reciente de Microsoft Authenticator.
3. Pulsa el **botón Quitar** cuenta.
4. Pulsa **Todas las aplicaciones en este dispositivo.**
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>Paso 2: Anular el registro del dispositivo de la aplicación Microsoft Authenticator

1. Pulse el icono de menú en la esquina superior derecha.
2. Pulsa **Configuración y,** a continuación, **Registro de dispositivos.**
4. Si se muestra tu cuenta, pulsa **Anular registro del dispositivo** y **continuar** en el cuadro de diálogo. No debería ver ninguna cuenta después de eso.
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>Paso 3: Cerrar sesión de aplicaciones individuales si es necesario

Los usuarios pueden ir a aplicaciones individuales como Outlook, Teams y OneDrive, y quitar cuentas de esas aplicaciones.

## <a name="more-information"></a>Más información

Introducción:

- [Migración de Microsoft Cloud Deutschland a los servicios de Office 365 en las nuevas regiones del centro de datos alemán](ms-cloud-germany-transition.md)
- [Asistencia para la migración a Microsoft Cloud Alemania](https://aka.ms/germanymigrateassist)
- [Cómo participar en la migración](ms-cloud-germany-migration-opt-in.md)
- [Experiencia del cliente durante la migración](ms-cloud-germany-transition-experience.md)

Pasar por la transición:

- [Impactos y acciones de las fases de migración](ms-cloud-germany-transition-phases.md)
- [Trabajo previo adicional](ms-cloud-germany-transition-add-pre-work.md)
- Información adicional para [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Aplicaciones en la nube:

- [Información del programa de migración de Dynamics 365](https://aka.ms/d365ceoptin)
- [Información del programa de migración de Power BI](https://aka.ms/pbioptin)
- [Introducción a su actualización de Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
