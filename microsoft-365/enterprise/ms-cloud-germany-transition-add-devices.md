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
ms.openlocfilehash: 27426a26befab85bf62a0a143861e447dd722724
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861311"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Información adicional del dispositivo para la migración desde Microsoft Cloud Deutschland

Los dispositivos unidos y registrados de Azure AD conectados a Microsoft Cloud Deutschland deben migrarse después de la fase 9 y antes de la fase 10. La migración de un dispositivo depende del tipo de dispositivo, el sistema operativo y la relación AAD. 

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

**¿Cómo puedo saber si mi organización está afectada?**

Los administradores deben comprobar si tienen dispositivos registrados o unidos `https://portal.microsoftazure.de` a Azure AD. Si su organización tiene dispositivos registrados, se verá afectado.

**¿Cuál es el impacto en mis usuarios?**

Los usuarios de un dispositivo registrado ya no podrán iniciar sesión después de que se haya completado la fase de migración [10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) y se hayan deshabilitado los puntos de conexión de Microsoft Cloud Deutschland.  

Asegúrese de que todos los dispositivos estén registrados en el punto de conexión mundial antes de que su organización se desconecte de Microsoft Cloud Deutschland.
  
**¿Cuándo los usuarios vuelvan a registrar sus dispositivos?**

Es fundamental para el éxito que solo desinscriba y vuelva a registrar los dispositivos una vez completada la [fase 9.](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) Debes finalizar el nuevo registro antes de que se inicie la fase 10, de lo contrario podrías perder el acceso al dispositivo.

**¿Cómo restaure el estado de mi dispositivo después de la migración?**

En el caso de los dispositivos Windows propiedad de la compañía que están registrados en Azure AD, los administradores podrán administrar la migración de estos dispositivos a través de flujos de trabajo desencadenados de forma remota que anularán el registro de los estados de dispositivo antiguos.
  
Para todos los demás dispositivos, incluidos los dispositivos Windows personales que están registrados en Azure AD, el usuario final debe realizar estos pasos manualmente. Para los dispositivos unidos a Azure AD, los usuarios deben tener una cuenta de administrador local para anular el registro y volver a registrar sus dispositivos.

Consulta instrucciones detalladas sobre cómo restaurar correctamente los estados del dispositivo a continuación. 
 
**¿Cómo sé que todos mis dispositivos están registrados en la nube pública?**

Para comprobar si los dispositivos están registrados en la nube pública, debe exportar y descargar la lista de dispositivos del portal de Azure AD a una Excel de cálculo. A continuación, filtre los dispositivos registrados (mediante la columna _registeredTime)_ después de la fase de migración [Independiente de Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)

## <a name="additional-considerations"></a>Consideraciones adicionales
El registro del dispositivo se desactiva después de la migración del inquilino y no se puede habilitar ni deshabilitar. 

Si no se usa Intune, inicie sesión en la suscripción y ejecute este comando para volver a activar la opción:

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```
**IMPORTANTE:** La entidad de servicio de Intune se habilitará después de la migración comercial, lo que implica la activación del registro de dispositivos de Azure AD. Si bloqueó el registro de dispositivos de Azure AD antes de la migración, debe deshabilitar la entidad de servicio de Intune con PowerShell para deshabilitar de nuevo el registro de dispositivos de Azure AD con el portal de Azure AD. Puede deshabilitar la entidad de servicio de Intune con este comando en el Azure Active Directory PowerShell para Graph módulo.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```


## <a name="azure-ad-join"></a>Unión a Azure AD
Esto se aplica a Windows 10 dispositivos. 

Si un dispositivo está unido a Azure AD, debe desconectarse de Azure AD y volver a conectarse. 

[![Azure AD Device Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)


Si el usuario es un administrador en el dispositivo Windows 10, el usuario puede anular el registro del dispositivo de Azure AD y volver a unirlo. Si no tiene privilegios de administrador, el usuario necesita credenciales de una cuenta de administrador local en este equipo. 


Un administrador puede crear una cuenta de administrador local en el dispositivo que sigue esta ruta de configuración:

*Configuración > cuentas > otras cuentas > credenciales desconocidas > Agregar usuario sin Microsoft-Account*

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a>Paso 1: Determinar si el dispositivo está unido a Azure ID.
1.  Inicie sesión con los usuarios Correo electrónico y contraseña.
2.  Vaya a Configuración > cuentas > Access Work Or School. 
3.  Busque un usuario en la lista con **conectado a ... 's Azure AD**. 
4.  Si existe un usuario conectado, continúe con el paso 2. Si no es así, no se requiere ninguna acción adicional.
### <a name="step-2-disconnect-the-device-from-azure-ad"></a>Paso 2: Desconectar el dispositivo de Azure AD
1.  Pulsa **Desconectar** en el trabajo conectado o cuenta educativa. 
2.  Confirme la desconexión dos veces. 
3.  Escriba el nombre de usuario y la contraseña del administrador local. El dispositivo está desconectado.
4.  Reinicie el dispositivo.
### <a name="step-3-join-the-device-to-azure-ad"></a>Paso 3: Unir el dispositivo a Azure AD
1.  el usuario inicia sesión con las credenciales del administrador local
2.  Vaya a **Configuración,** a **continuación, Cuentas** y **acceso a trabajo o escuela**
3.  Pulsa **Conectar**
4.  **IMPORTANTE:** Pulsa **Unirse a Azure AD**
5.  Escriba la dirección de correo electrónico y la contraseña del usuario. El dispositivo está conectado
6.  Reiniciar el dispositivo 
7.  firmar con su dirección de correo electrónico y contraseña

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