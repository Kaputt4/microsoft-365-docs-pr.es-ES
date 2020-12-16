---
title: Información adicional de dispositivos para la migración desde la nube de Microsoft Alemania
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
description: 'Resumen: información de dispositivos adicional sobre los servicios al cambiar de Microsoft Cloud Germany (Microsoft Cloud Alemania) a Office 365 Services en la nueva región del centro de datos en alemán.'
ms.openlocfilehash: 1bbb4bf39db61a93844c21cd6062a70699b5d6d7
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688660"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Información adicional de dispositivos para la migración desde la nube de Microsoft Alemania

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

**¿Cómo puedo saber si mi organización está afectada?**

Los administradores deben comprobar `https://portal.microsoftazure.de` si tienen algún dispositivo registrado. Si su organización tiene dispositivos registrados, su equipo está afectado.

**¿Cuál es el impacto en los usuarios?**

Los usuarios de un dispositivo registrado ya no podrán iniciar sesión después de que la migración se haya introducido en la fase finalizar la migración de [Azure ad](ms-cloud-germany-transition.md#how-is-the-migration-organized) .  

Asegúrese de que todos los dispositivos estén registrados con el extremo en todo el mundo antes de que su organización se desconecte de Microsoft Cloud Alemania.
  
**¿Cuándo pueden los usuarios volver a registrar sus dispositivos?**

Es esencial para su éxito que solo anule el registro y vuelva a registrar los dispositivos durante la fase [independiente de la migración de Microsoft Cloud Alemania](ms-cloud-germany-transition.md#how-is-the-migration-organized) .

**¿Cómo puedo restaurar mi estado del dispositivo después de la migración?**

En el caso de los dispositivos Windows híbridos de Azure AD Unidos y de propiedad de la empresa que se registran con Azure AD, los administradores podrán administrar la migración de estos dispositivos a través de flujos de trabajo desencadenados de forma remota que anularán el registro de los Estados de dispositivo anteriores.
  
Para todos los demás dispositivos, incluidos los dispositivos de Windows personales registrados en Azure AD, el usuario final debe realizar estos pasos de forma manual. Para los dispositivos Unidos a Azure AD, los usuarios deben tener una cuenta de administrador local para anular el registro y, a continuación, volver a registrar sus dispositivos.

Microsoft publicará instrucciones para restaurar correctamente el estado del dispositivo. 
 
**¿Cómo sé que todos mis dispositivos están registrados en la nube pública?**

Para comprobar si los dispositivos están registrados en la nube pública, debe exportar y descargar la lista de dispositivos desde el portal de Azure AD a una hoja de cálculo de Excel. A continuación, filtre los dispositivos que están registrados (mediante la columna _registeredTime_ ) después de la fase [de migración independiente de la nube de Microsoft Alemania](ms-cloud-germany-transition.md#how-is-the-migration-organized) .

El registro de dispositivos se desactiva después de la migración del espacio empresarial y no se puede habilitar o deshabilitar. Si no se usa Intune, inicie sesión en su suscripción y ejecute este comando para volver a activar la opción:

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a>Combinación de Windows híbrida de Azure AD

### <a name="windows-down-level"></a>Nivel inferior de Windows

Los _dispositivos de nivel inferior de Windows_ son dispositivos Windows que actualmente ejecutan versiones anteriores de Windows (como Windows 8,1 o Windows 7), o que ejecutan versiones de Windows Server anteriores a 2019 y 2016. Si estos dispositivos se registraron antes, tendrás que anular el registro y volver a registrar estos dispositivos. 

Para determinar si un dispositivo de Windows de nivel inferior se unió previamente a Azure AD, use el siguiente comando en el dispositivo:

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

Si el dispositivo se unió previamente a Azure AD y el dispositivo tiene conectividad de red a los puntos de conexión globales de Azure AD, vería el resultado siguiente:

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

Los dispositivos afectados tendrán el "estado de dispositivo" con el valor "desconocido". Si el resultado es "dispositivo no Unido" o el valor de "estado de dispositivo" es "correcto", ignore las siguientes instrucciones.

Solo para dispositivos que muestran que el dispositivo está unido (en virtud del deviceId, la huella digital, etc.) y cuyo valor de "estado de dispositivo" es "desconocido", los administradores deben ejecutar el siguiente comando en el contexto de un usuario de dominio que inicie sesión en dicho dispositivo de bajo nivel:

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

El comando anterior solo debe ejecutarse una vez por cada usuario de dominio que inicie sesión en el dispositivo de nivel inferior de Windows. Este comando debe ejecutarse en el contexto del usuario de dominio que inicia sesión. 

Debe tener cuidado suficiente para no ejecutar este comando cuando el usuario inicia sesión posteriormente. Cuando se ejecute el comando anterior, se borrará el estado de unión del equipo híbrido local de Azure AD para el usuario que inició sesión. Además, si el equipo sigue configurado para ser híbrido de Azure AD, se intentará unir cuando el usuario vuelva a iniciar sesión.

### <a name="windows-current"></a>Ventanas actualizadas

#### <a name="unjoin"></a>Unjoin

Para determinar si el dispositivo con Windows 10 se unió previamente a Azure AD, ejecute el siguiente comando en el dispositivo:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Si el dispositivo es una combinación híbrida de Azure AD, el administrador vería el siguiente resultado:

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

Si el resultado es "AzureAdJoined: no", ignore las siguientes instrucciones.

Solo para dispositivos que muestren que el dispositivo está unido a Azure AD, ejecute el siguiente comando como administrador para quitar el estado de unión del dispositivo.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

El comando anterior solo debe ejecutarse una vez en un contexto administrativo en el dispositivo Windows.

#### <a name="hybrid-ad-joinre-registration"></a>Join\Re-Registration de AD híbrido

El dispositivo se une automáticamente a Azure AD sin la intervención del usuario o del administrador siempre que el dispositivo tenga conectividad de red con los extremos globales de Azure AD. 


## <a name="windows-azure-ad-join"></a>Combinación de Windows Azure AD

**Importante:** La entidad de servicio de Intune se habilitará después de la migración de Commerce, lo que implica la activación del registro de dispositivos de Azure AD. Si ha bloqueado el registro de dispositivos de Azure AD antes de la migración, debe deshabilitar la entidad de servicio de Intune con PowerShell para deshabilitar el registro de dispositivos de Azure AD con el portal de Azure AD de nuevo. Puede deshabilitar la entidad de servicio de Intune con este comando en el módulo Azure Active Directory PowerShell para Graph.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a>Unjoin

Para determinar si el dispositivo de Windows 10 se unió previamente a Azure AD, el usuario o administrador puede ejecutar el siguiente comando en el dispositivo:

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

Si el resultado es "AzureAdJoined: NO", ignore las siguientes instrucciones.

Usuario: Si el dispositivo está unido a Azure AD, un usuario puede separar el dispositivo de la configuración. Compruebe que hay una cuenta de administrador local en el dispositivo antes de separar el dispositivo de Azure AD. La cuenta de administrador local es necesaria para volver a iniciar sesión en el dispositivo.

Administrador: Si el administrador de la organización desea separar los dispositivos de los usuarios que están Unidos a Azure AD, puede hacerlo ejecutando el siguiente comando en cada uno de los dispositivos mediante un mecanismo como la Directiva de grupo. El administrador debe comprobar que hay una cuenta de administrador local en el dispositivo antes de separar el dispositivo de Azure AD. La cuenta de administrador local es necesaria para volver a iniciar sesión en el dispositivo.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

El comando anterior solo debe ejecutarse una vez en un contexto administrativo en el dispositivo Windows. 

### <a name="azure-ad-joinre-registration"></a>Unirse/volver a registrar Azure AD

El usuario puede unir el dispositivo a Azure AD desde la configuración de Windows: **configuración > cuentas > Access trabajo o escuela > conectar**.
 

## <a name="windows-azure-ad-registered-company-owned"></a>Windows Azure AD registrado (propiedad de la empresa)

Para determinar si el dispositivo con Windows 10 está registrado en Azure AD, ejecute el siguiente comando en el dispositivo:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Si el dispositivo está registrado en Azure AD, vería el resultado siguiente:

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

Para quitar la cuenta existente de Azure AD registrada en el dispositivo:

- Para quitar la cuenta registrada de Azure AD en el dispositivo, use CleanupWPJ, una herramienta que puede descargar desde aquí: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).

- Extraiga el archivo ZIP y ejecute **WPJCleanup. cmd**. Esta herramienta iniciará el ejecutable adecuado en función de la versión de Windows en el dispositivo.

- Mediante el uso de un mecanismo como la Directiva de grupo, el administrador puede ejecutar el comando en el dispositivo en el contexto de cualquier usuario que haya iniciado sesión en el dispositivo.

Para deshabilitar los mensajes del administrador de cuentas web para registrar el dispositivo en Azure AD, agregue este valor del registro: 

- Ubicación: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin
- Tipo: DWORD (32 bits)
- Nombre: BlockAADWorkplaceJoin
- Datos del valor: 1

La presencia de este valor del registro debe bloquear el área de trabajo unirse y evitar que los usuarios vean mensajes para unirse al dispositivo.

## <a name="android"></a>Android

Para Android, los usuarios tendrán que anular el registro y volver a registrar sus dispositivos. Esto se puede hacer mediante la aplicación Microsoft Authenticator o la aplicación portal de empresa. 

- Desde la aplicación Microsoft Authenticator, los usuarios pueden ir a la **configuración > el registro de dispositivos**. Desde allí, los usuarios pueden anular el registro y volver a registrar el dispositivo.
 
- Desde el portal de empresa, los usuarios pueden ir a la ficha **dispositivos** y quitar el dispositivo. A continuación, vuelva a inscribir el dispositivo con el portal de la empresa.
 
- Los usuarios también pueden anular el registro y volver a registrarse quitando la cuenta de la página Configuración de la cuenta y, a continuación, volver a agregar la cuenta trabajo.

Para anular el registro y volver a registrar el dispositivo en Android mediante la aplicación Microsoft Authenticator:

1.  Abra la aplicación Microsoft Authenticator y vaya a **configuración**.
2.  Seleccione **registro de dispositivos**.
3.  Para anular el registro del dispositivo, seleccione **anular registro**.
4.  Para el **registro de dispositivos**, vuelva a registrar el dispositivo escribiendo su dirección de correo electrónico y, a continuación, seleccione **registrar**.

Para anular el registro y volver a registrar un dispositivo Android con la página de configuración de Android:

1.  Abra **configuración del dispositivo** y vaya a **cuentas**.
2.  Seleccione la cuenta profesional que quiera volver a registrar y seleccione **quitar cuenta**.
3.  Una vez quitada la cuenta, en la página **cuentas** , seleccione **Agregar cuenta > cuenta profesional**.
4.  En **Workplace join**, escriba su dirección de correo electrónico y seleccione **unirse** para finalizar el registro del dispositivo.

Para anular el registro y volver a registrar el dispositivo en Android desde el portal de empresa:

1.  Inicie portal de empresa y vaya a la pestaña **dispositivos** .
2.  Selecciona el dispositivo para ver los detalles del dispositivo.
3.  En el menú de puntos suspensivos (tres puntos), seleccione **quitar dispositivo** y complete la eliminación mediante la confirmación en el cuadro de diálogo.
4.  Ahora debe haber cerrado la sesión de la aplicación portal de empresa. Seleccione **iniciar sesión** para volver a registrar el dispositivo.

Para obtener más información acerca de las acciones necesarias durante la fase de migración de esta carga de trabajo, o el impacto en la administración o la utilización, revise la información sobre Azure Active Directory (Azure AD) en [información adicional de Azure ad para la migración desde la nube de Microsoft Alemania](ms-cloud-germany-transition-azure-ad.md).

## <a name="ios"></a>iOS

En dispositivos iOS, un usuario tendrá que quitar manualmente todas las cuentas almacenadas en caché del autenticador de Microsoft, anular el registro del dispositivo y cerrar la sesión de cualquier aplicación nativa en el dispositivo.

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>Paso 1: Si está presente, quitar la cuenta de la aplicación Microsoft Authenticator

1. Pulse la cuenta en la aplicación Microsoft Authenticator.
2. Pulse el icono **configuración** en la esquina superior derecha. Si no ve el icono de **configuración** , es posible que no esté usando la versión más reciente de Microsoft Authenticator.
3. Pulse el botón **quitar cuenta** .
4. Pulsa **todas las aplicaciones de este dispositivo**.
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>Paso 2: anular el registro del dispositivo desde la aplicación Microsoft Authenticator

1. Pulse el icono de menú en la esquina superior derecha.
2. Pulse **configuración** y, después, **registro de dispositivo**.
4. Si se muestra su cuenta, puntee en **quitar del registro el dispositivo** y en **continuar** en el cuadro de diálogo. No debería ver ninguna cuenta a continuación.
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>Paso 3: cerrar la sesión de aplicaciones individuales si es necesario

Los usuarios pueden ir a aplicaciones individuales como Outlook, Teams y OneDrive, y quitar cuentas de esas aplicaciones.

## <a name="more-information"></a>Más información

Introducción:

- [Migración desde Microsoft Cloud Alemania a Office 365 Services en las nuevas regiones del centro de administración de Office en alemán](ms-cloud-germany-transition.md)
- [Asistencia para la migración a Microsoft Cloud Alemania](https://aka.ms/germanymigrateassist)
- [Cómo participar en la migración](ms-cloud-germany-migration-opt-in.md)
- [Experiencia del cliente durante la migración](ms-cloud-germany-transition-experience.md)

Desplazarse por la transición:

- [Impactos y acciones de las fases de migración](ms-cloud-germany-transition-phases.md)
- [Pre-trabajo adicional](ms-cloud-germany-transition-add-pre-work.md)
- Información adicional para [Azure ad](ms-cloud-germany-transition-azure-ad.md), [dispositivos](ms-cloud-germany-transition-add-devices.md), [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicaciones en la nube:

- [Información del programa de migración de Dynamics 365](https://aka.ms/d365ceoptin)
- [Información del programa de migración de Power BI](https://aka.ms/pbioptin)
- [Introducción a su actualización de Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
