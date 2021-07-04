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
ms.openlocfilehash: 684af01b2d90f44b2cda1cf050d1e4db70f92915
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289444"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Información adicional del dispositivo para la migración desde Microsoft Cloud Deutschland

Los dispositivos unidos y registrados de Azure AD conectados a Microsoft Cloud Deutschland deben migrarse después de la fase 9 y antes de la fase 10. La migración de un dispositivo depende del tipo de dispositivo, el sistema operativo y la relación de Azure AD.

## <a name="azure-ad-joined-windows-10-devices"></a>Dispositivos unidos Windows 10 Azure AD
Si un Windows 10 está unido a Azure AD, debe desconectarse de Azure AD y debe conectarse de nuevo.

[![Azure AD Device Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)


Si el usuario es un administrador en el dispositivo Windows 10, el usuario puede anular el registro del dispositivo de Azure AD y volver a unirlo en tres pasos.

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a>Paso 1: Determinar si el dispositivo está unido a Azure ID.

1. Inicie sesión con su cuenta profesional.
2. Vaya a **Configuración**  >  **cuentas acceso** a trabajo o  >  **escuela**.
3. Buscar una cuenta en la lista con **conectado a [...]' s Azure AD**.
4. Si existe una cuenta conectada, continúe con el paso 2.

### <a name="step-2-disconnect-the-device-from-azure-ad"></a>Paso 2: Desconectar el dispositivo de Azure AD

1. Haga **clic en** Desconectar en el trabajo conectado o cuenta educativa.
2. Confirme la desconexión dos veces.
3. Escriba un nombre de usuario y una contraseña de administrador local. El dispositivo está desconectado.
4. Reinicie el dispositivo.

### <a name="step-3-join-the-device-to-azure-ad"></a>Paso 3: Unir el dispositivo a Azure AD

1. Inicie sesión con las credenciales del administrador local.
2. Vaya a **Configuración**  >  **cuentas acceso** a trabajo o  >  **escuela**.
3. Haga clic en **Conectar**.
4. **IMPORTANTE:** Haga clic **en Unirse a Azure AD**.
5. Escriba la dirección de correo electrónico y la contraseña de su cuenta de trabajo. El dispositivo está conectado.
6. Reinicie el dispositivo.
7. Inicie sesión con la dirección de correo electrónico y la contraseña de su cuenta de trabajo.

Si el usuario no es un administrador del dispositivo, un administrador global de Azure AD puede crear la cuenta de administrador local en el dispositivo siguiendo esta ruta de configuración y deshacer la conexión del dispositivo:

*Configuración > cuentas > otras cuentas > credenciales desconocidas > Agregar usuario sin Microsoft-Account*

Para volver a unirse, las credenciales de cualquier cuenta de trabajo de su organización se pueden usar en este paso.

Ten en cuenta que la cuenta de trabajo usada para unirse al dispositivo se promocionará automáticamente como administrador del dispositivo.
Cualquier otra cuenta de trabajo de la organización puede iniciar sesión en el dispositivo, pero no tiene privilegios de administrador.

## <a name="azure-ad-registered-workplace-joined-windows-10-devices"></a>Azure AD registrado (unido al lugar de trabajo) Windows 10 dispositivos

Si un Windows 10 está registrado en Azure AD, debe desconectarse de Azure AD y conectarse de nuevo.

[![Azure AD Device Re-Registration Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReRegistration-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)

### <a name="step-1-determine-if-the-device-is-azure-id-registered"></a>Paso 1: Determinar si el dispositivo está registrado en Azure ID.

1. Inicie sesión con el usuario.
2. Vaya a **Configuración**  >  **cuentas acceso** a trabajo o  >  **escuela**.
3. Descubrir la cuenta de trabajo en la lista y comprobar si está **conectada a [...]' s Azure AD**.

    Si la cuenta de trabajo está en la lista pero NO está conectada a azure AD, continúe con el paso 2.

    De lo contrario, el dispositivo es un dispositivo unido a Azure AD y tiene que hacer referencia a [Azure AD Joined Windows 10 devices](#azure-ad-joined-windows-10-devices).

### <a name="step-2-disconnect-the-device-from-azure-ad"></a>Paso 2: Desconectar el dispositivo de Azure AD

1. Haz clic en tu cuenta de trabajo. Aparecen los botones *Información* *y* Desconectar.
2. Haga clic **en Desconectar**.
3. Para confirmar la eliminación de la cuenta del dispositivo, haga clic **en Sí**.

### <a name="step-3-connect-the-device-to-azure-ad"></a>Paso 3: Conectar el dispositivo a Azure AD

1. Haga clic en **Conectar**.
2. Escriba la dirección de correo electrónico de su cuenta de trabajo y haga clic **en Siguiente**.
3. Escriba la contraseña de su cuenta de trabajo y haga clic **en Iniciar sesión.**
4. Confirme haciendo clic en **Listo**. La cuenta de trabajo aparece de nuevo.

## <a name="android"></a>Android

Para Android, los usuarios tendrán que anular el registro y volver a registrar sus dispositivos. Esto se puede hacer a través de la Microsoft Authenticator o la Portal de empresa aplicación.

- Desde la Microsoft Authenticator, los usuarios pueden ir a **Configuración > Registro de dispositivos.** Desde allí, los usuarios pueden anular el registro y volver a registrar su dispositivo.

- Desde el Portal de empresa, los usuarios pueden ir a la **pestaña Dispositivos** y quitar el dispositivo. Después, vuelva a inscribir el dispositivo mediante Portal de empresa.

- Los usuarios también pueden anular el registro y volver a registrarse quitando la cuenta de la página de configuración de la cuenta y, a continuación, agregando de nuevo la cuenta de trabajo.

Para anular el registro y volver a registrar el dispositivo en Android mediante la Microsoft Authenticator aplicación:

1. Abre la Microsoft Authenticator y ve **a Configuración**.
2. Seleccione **Registro de dispositivos**.
3. Anula el registro del dispositivo **seleccionando Anular registro**.
4. Para **registro de dispositivos,** vuelva a registrar el dispositivo escribiendo la dirección de correo electrónico y, a continuación, **seleccione Registrar**.

Para anular el registro y volver a registrar un dispositivo Android con la Configuración Android:

1. Abra **Device Configuración** y vaya a **Cuentas**.
2. Seleccione la cuenta de trabajo que desea volver a registrar y seleccione **Quitar cuenta**.
3. Después de quitar la cuenta, en la **página Cuentas,** seleccione **Agregar cuenta > cuenta de trabajo**.
4. En **Workplace Join**, escriba su dirección de correo electrónico y seleccione **Unirse** para completar el registro del dispositivo.

Para anular el registro y volver a registrar el dispositivo en Android desde Portal de empresa:

1. Inicie Portal de empresa y vaya a **la pestaña Dispositivos.**
2. Selecciona el dispositivo para ver los detalles del dispositivo.
3. En el menú puntos suspensivos (tres puntos), selecciona **Quitar** dispositivo y completa la eliminación confirmando en el cuadro de diálogo.
4. Ahora debes haber cerrado sesión en la Portal de empresa aplicación. Selecciona **Iniciar sesión** para volver a registrar el dispositivo.

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
3. Si se muestra tu cuenta, pulsa **Anular registro del dispositivo** y **Continuar** en el cuadro de diálogo. No debería ver ninguna cuenta después de eso.

### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>Paso 3: Cerrar sesión de aplicaciones individuales si es necesario

Los usuarios pueden ir a aplicaciones individuales como Outlook, Teams y OneDrive y quitar cuentas de esas aplicaciones.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**¿Cómo puedo saber si mi organización está afectada?**

Los administradores deben comprobar si tienen dispositivos de Azure AD registrados o unidos `https://portal.microsoftazure.de` a Azure AD. Si su organización tiene dispositivos de Azure AD registrados o unidos a Azure AD, la organización debe seguir las instrucciones de esta página.

**¿Cuándo los usuarios vuelvan a registrar sus dispositivos?**

Es fundamental para el éxito que solo desinscriba y vuelva a registrar los dispositivos una vez completada la [fase 9.](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) Debes finalizar el nuevo registro antes de que se inicie la fase 10, de lo contrario podrías perder el acceso al dispositivo.

**¿Cómo sé que todos mis dispositivos están registrados en la nube pública?**

Para comprobar si los dispositivos están registrados en la nube pública, debe exportar y descargar la lista de dispositivos del portal de Azure AD a una Excel de cálculo. A continuación, filtre los dispositivos registrados (mediante la columna _registeredTime)_ después de la fecha en que la organización ha pasado la [fase 9 del proceso de migración](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization).

## <a name="additional-considerations"></a>Consideraciones adicionales

> [!IMPORTANT]
> La entidad de servicio de Intune se habilitará después de la [fase 3](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer)del proceso de migración, lo que implica la activación del registro de dispositivos de Azure AD. Si bloqueó el registro de dispositivos de Azure AD antes de la migración, debe deshabilitar la entidad de servicio de Intune con PowerShell para deshabilitar de nuevo el registro de dispositivos de Azure AD con el portal de Azure AD. Puede deshabilitar la entidad de servicio de Intune con este comando en el Azure Active Directory PowerShell para Graph módulo.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

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
