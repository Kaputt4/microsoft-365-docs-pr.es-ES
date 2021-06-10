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
description: 'Resumen: información adicional del dispositivo sobre los servicios al pasar de Microsoft Cloud Germany (Microsoft Cloud Deutschland) a Office 365 servicios en la nueva región del centro de datos alemán.'
ms.openlocfilehash: 21188372f03af394fe1c0e227c1adeabbad02a85
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928161"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Información adicional del dispositivo para la migración desde Microsoft Cloud Deutschland

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**¿Cómo puedo saber si mi organización está afectada?**

Los administradores deben `https://portal.microsoftazure.de` comprobar si tienen dispositivos registrados. Si su organización tiene dispositivos registrados, se verá afectado.

**¿Cuál es el impacto en mis usuarios?**

Los usuarios de un dispositivo registrado ya no podrán iniciar sesión después de que la migración entre en la fase [finalizar la migración de Azure AD.](ms-cloud-germany-transition.md#how-is-the-migration-organized)  

Asegúrese de que todos los dispositivos estén registrados en el punto de conexión mundial antes de que su organización se desconecte de Microsoft Cloud Deutschland.
  
**¿Cuándo los usuarios vuelvan a registrar sus dispositivos?**

Es fundamental para el éxito que solo desinscribas y vuelvas a registrar los dispositivos durante la fase de migración Independiente [de Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)

**¿Cómo restaure el estado de mi dispositivo después de la migración?**

Para los dispositivos Windows híbridos unidos a Azure AD y propiedad de la compañía que están registrados en Azure AD, los administradores podrán administrar la migración de estos dispositivos a través de flujos de trabajo desencadenados de forma remota que anularán el registro de los estados de dispositivo antiguos.
  
Para todos los demás dispositivos, incluidos los dispositivos Windows personales que están registrados en Azure AD, el usuario final debe realizar estos pasos manualmente. Para los dispositivos unidos a Azure AD, los usuarios deben tener una cuenta de administrador local para anular el registro y volver a registrar sus dispositivos.

Microsoft publicará instrucciones sobre cómo restaurar correctamente el estado del dispositivo. 
 
**¿Cómo sé que todos mis dispositivos están registrados en la nube pública?**

Para comprobar si los dispositivos están registrados en la nube pública, debe exportar y descargar la lista de dispositivos del portal de Azure AD a una Excel de cálculo. A continuación, filtre los dispositivos registrados (mediante la columna _registeredTime)_ después de la fase de migración [Independiente de Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)

El registro del dispositivo se desactiva después de la migración del inquilino y no se puede habilitar ni deshabilitar. Si no se usa Intune, inicie sesión en la suscripción y ejecute este comando para volver a activar la opción:

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="hybrid-azure-ad-join"></a>Unión a Azure AD híbrido

### <a name="windows-down-level"></a>Windows nivel inferior

_Windows_ de nivel inferior son dispositivos Windows que actualmente ejecutan versiones anteriores de Windows (como Windows 8.1 o Windows 7) o que ejecutan versiones de servidor de Windows anteriores a 2019 y 2016. Si estos dispositivos se registraron antes, tendrás que anular el registro y volver a registrar esos dispositivos. 

Para determinar si un Windows de nivel inferior se unió previamente a Azure AD, use el siguiente comando en el dispositivo:

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

Si el dispositivo se unió previamente a Azure AD y si el dispositivo tiene conectividad de red con puntos de conexión globales de Azure AD, verá el resultado siguiente:

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

Los dispositivos afectados tendrán el "Estado del dispositivo" con el valor "Desconocido". Si el resultado es "Dispositivo no unido" o cuyo valor "Estado del dispositivo" es "Correcto", ignore las instrucciones siguientes.

Solo para dispositivos que muestran que el dispositivo está unido (en virtud de deviceId, huella digital, entre otros) y cuyo valor "Estado del dispositivo" es "Desconocido", los administradores deben ejecutar el siguiente comando en el contexto de un usuario de dominio que inicie sesión en un dispositivo de nivel inferior:

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

El comando anterior solo debe ejecutarse una vez por usuario de dominio que inicie sesión en Windows dispositivo de nivel inferior. Este comando debe ejecutarse en el contexto del inicio de sesión del usuario del dominio. 

Debe tenerse suficiente cuidado para no ejecutar este comando cuando el usuario inicia sesión posteriormente. Cuando se ejecute el comando anterior, borrará el estado unido del equipo híbrido local unido a Azure AD para el usuario que ha iniciado sesión. Y, si el equipo aún está configurado para que esté unido a Azure AD híbrido en el espacio empresarial, intentará unirse cuando el usuario vuelva a abrir sesión.

### <a name="windows-current"></a>Windows Actual

#### <a name="unjoin"></a>Unjoin

Para determinar si el Windows 10 se unió previamente a Azure AD, ejecute el siguiente comando en el dispositivo:

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

Si el resultado es "AzureAdJoined : No", ignore las instrucciones siguientes.

Solo para dispositivos que muestran que el dispositivo está unido a Azure AD, ejecute el siguiente comando como administrador para quitar el estado unido del dispositivo.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

El comando anterior solo debe ejecutarse una vez en un contexto administrativo en el Windows dispositivo.

#### <a name="hybrid-ad-joinre-registration"></a>Unión a AD híbrida\Nuevo registro

El dispositivo se une automáticamente a Azure AD sin intervención del usuario ni del administrador, siempre y cuando el dispositivo tenga conectividad de red con puntos de conexión globales de Azure AD. 


## <a name="azure-ad-join"></a>Unión a Azure AD

**IMPORTANTE:** La entidad de servicio de Intune se habilitará después de la migración comercial, lo que implica la activación del registro de dispositivos de Azure AD. Si bloqueó el registro de dispositivos de Azure AD antes de la migración, debe deshabilitar la entidad de servicio de Intune con PowerShell para deshabilitar de nuevo el registro de dispositivos de Azure AD con el portal de Azure AD. Puede deshabilitar la entidad de servicio de Intune con este comando en el Azure Active Directory PowerShell para Graph módulo.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a>Unjoin

Para determinar si el Windows 10 se unió previamente a Azure AD, el usuario o administrador puede ejecutar el siguiente comando en el dispositivo:

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

Si el resultado es "AzureAdJoined : NO", ignore las instrucciones siguientes.

Usuario: si el dispositivo está unido a Azure AD, un usuario puede unirse al dispositivo desde la configuración. Compruebe que hay una cuenta de administrador local en el dispositivo antes de deshacer el dispositivo de Azure AD. La cuenta de administrador local es necesaria para volver a iniciar sesión en el dispositivo.

Administrador: si el administrador de la organización quiere unirse a los dispositivos de los usuarios unidos a Azure AD, puede hacerlo ejecutando el siguiente comando en cada uno de los dispositivos mediante un mecanismo como la directiva de grupo. El administrador debe comprobar que hay una cuenta de administrador local en el dispositivo antes de deshacer el dispositivo de Azure AD. La cuenta de administrador local es necesaria para volver a iniciar sesión en el dispositivo.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

El comando anterior solo debe ejecutarse una vez en un contexto administrativo en el Windows dispositivo. 

### <a name="azure-ad-joinre-registration"></a>Unirse o volver a registrarse de Azure AD

El usuario puede unir el dispositivo a Azure AD desde Windows configuración: Configuración > cuentas > **Acceso a trabajo o escuela > Conectar**.
 

## <a name="azure-ad-registered-company-owned"></a>Azure AD Registrado (propiedad de la compañía)

Para determinar si el Windows 10 está registrado en Azure AD, ejecute el siguiente comando en el dispositivo:

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

- Para quitar la cuenta registrada de Azure AD en el dispositivo, use CleanupWPJ, una herramienta que puede descargar desde aquí: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).

- Extraiga el archivo ZIP y ejecute **WPJCleanup.cmd**. Esta herramienta iniciará el ejecutable correcto en función de la versión de Windows en el dispositivo.

- Mediante un mecanismo como la directiva de grupo, el administrador puede ejecutar el comando en el dispositivo en el contexto de cualquier usuario que haya iniciado sesión en el dispositivo.

Para deshabilitar los mensajes del Administrador de cuentas web para registrar el dispositivo en Azure AD, agregue este valor del Registro: 

- Ubicación: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin
- Tipo: DWORD (32 bits)
- Nombre: BlockAADWorkplaceJoin
- Datos de valor: 1

La presencia de este valor del Registro debe bloquear la unión al lugar de trabajo e impedir que los usuarios vean mensajes para unirse al dispositivo.

## <a name="android"></a>Android

Para Android, los usuarios tendrán que anular el registro y volver a registrar sus dispositivos. Esto se puede hacer a través de la Microsoft Authenticator o la Portal de empresa aplicación. 

- Desde la Microsoft Authenticator, los usuarios pueden ir a **Configuración > Registro de dispositivos.** Desde allí, los usuarios pueden anular el registro y volver a registrar su dispositivo.
 
- Desde el Portal de empresa, los usuarios pueden ir a la **pestaña Dispositivos** y quitar el dispositivo. Después, vuelva a inscribir el dispositivo mediante Portal de empresa.
 
- Los usuarios también pueden anular el registro y volver a registrarse quitando la cuenta de la página de configuración de la cuenta y, a continuación, agregando de nuevo la cuenta de trabajo.

Para anular el registro y volver a registrar el dispositivo en Android mediante la Microsoft Authenticator aplicación:

1.  Abre la Microsoft Authenticator y ve **a Configuración**.
2.  Seleccione **Registro de dispositivos**.
3.  Anula el registro del dispositivo **seleccionando Anular registro**.
4.  Para **registro de dispositivos,** vuelva a registrar el dispositivo escribiendo la dirección de correo electrónico y, a continuación, **seleccione Registrar**.

Para anular el registro y volver a registrar un dispositivo Android con la Configuración Android:

1.  Abra **Device Configuración** y vaya a **Cuentas**.
2.  Seleccione la cuenta de trabajo que desea volver a registrar y seleccione **Quitar cuenta**.
3.  Después de quitar la cuenta, en la **página Cuentas,** seleccione **Agregar cuenta > cuenta de trabajo**.
4.  En **Workplace Join**, escriba su dirección de correo electrónico y seleccione **Unirse** para completar el registro del dispositivo.

Para anular el registro y volver a registrar el dispositivo en Android desde Portal de empresa:

1.  Inicie Portal de empresa y vaya a **la pestaña Dispositivos.**
2.  Selecciona el dispositivo para ver los detalles del dispositivo.
3.  En el menú puntos suspensivos (tres puntos), selecciona **Quitar** dispositivo y completa la eliminación confirmando en el cuadro de diálogo.
4.  Ahora debes haber cerrado sesión en la Portal de empresa aplicación. Selecciona **Iniciar sesión** para volver a registrar el dispositivo.

Para obtener más información sobre las acciones necesarias durante la fase de migración de esta carga de trabajo, o el impacto en la administración o el uso, revise la información sobre Azure Active Directory (Azure AD) en Información adicional de Azure AD para la migración desde [Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).

## <a name="ios"></a>iOS

En dispositivos iOS, un usuario tendrá que quitar manualmente las cuentas almacenadas en caché del Microsoft Authenticator, anular el registro del dispositivo y cerrar sesión de cualquier aplicación nativa del dispositivo.

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>Paso 1: Si está presente, quite la cuenta de la Microsoft Authenticator aplicación

1. Pulsa la cuenta en la Microsoft Authenticator aplicación.
2. Pulsa el **Configuración** en la esquina superior derecha. Si no ve el  icono Configuración, es posible que no esté usando la versión más reciente de Microsoft Authenticator.
3. Pulsa el **botón Quitar cuenta.**
4. Pulsa **Todas las aplicaciones en este dispositivo**.
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>Paso 2: Anular el registro del dispositivo desde la Microsoft Authenticator aplicación

1. Pulsa el icono del menú en la esquina superior derecha.
2. Pulsa **Configuración** y, a continuación, **Registro de dispositivos**.
4. Si se muestra tu cuenta, pulsa **Anular registro del dispositivo** y **Continuar** en el cuadro de diálogo. No debería ver ninguna cuenta después de eso.
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>Paso 3: Cerrar sesión de aplicaciones individuales si es necesario

Los usuarios pueden ir a aplicaciones individuales como Outlook, Teams y OneDrive y quitar cuentas de esas aplicaciones.

## <a name="more-information"></a>Más información

Introducción:

- [Migración de Microsoft Cloud Deutschland a Office 365 servicios en las nuevas regiones del centro de datos alemán](ms-cloud-germany-transition.md)
- [Asistencia para la migración a Microsoft Cloud Alemania](https://aka.ms/germanymigrateassist)
- [Cómo participar en la migración](ms-cloud-germany-migration-opt-in.md)
- [Experiencia del cliente durante la migración](ms-cloud-germany-transition-experience.md)

Pasar a través de la transición:

- [Impactos y acciones de las fases de migración](ms-cloud-germany-transition-phases.md)
- [Pre-work adicional](ms-cloud-germany-transition-add-pre-work.md)
- Información adicional para [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicaciones en la nube:

- [Información del programa de migración de Dynamics 365](/dynamics365/get-started/migrate-data-german-region)
- [Información del programa de migración de Power BI](/power-bi/admin/service-admin-migrate-data-germany)
- [Introducción a su actualización de Microsoft Teams](/microsoftteams/upgrade-start-here)