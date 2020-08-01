---
title: Habilitar los dispositivos Windows 10 Unidos a un dominio para que los administre Microsoft 365 para la empresa
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Obtenga información sobre cómo habilitar Microsoft 365 para proteger dispositivos Windows 10 locales Unidos a directorio activo en tan solo unos pocos pasos.
ms.openlocfilehash: 2eaf5aa76cae1680b93af008af615ae872e4fb20
ms.sourcegitcommit: fab425ea4580d1924fb421e6db233d135f5b7d19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533793"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Habilitar los dispositivos Windows 10 Unidos a un dominio para que los administre Microsoft 365 empresa Premium

Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 Business Premium para proteger sus dispositivos con Windows 10, a la vez que mantiene el acceso a los recursos locales que requieren autenticación local.
Para configurar esta protección, puede implementar dispositivos de **Azure ad Unidos híbridos**. Estos dispositivos se unen a su Active Directory local y a su Azure Active Directory.

Este vídeo describe los pasos para configurar esta configuración para el escenario más común, que también se detalla en los pasos siguientes.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>Antes de empezar, asegúrese de completar estos pasos:
- Sincronice los usuarios a Azure AD con Azure AD Connect.
- Complete la sincronización de la unidad organizativa (OU) de Azure AD Connect.
- Asegúrese de que todos los usuarios de dominio que sincronice tienen licencias para Microsoft 365 empresa Premium.

Consulte [sincronizar usuarios de dominio a Microsoft](manage-domain-users.md) para conocer los pasos.

## <a name="1-verify-mdm-authority-in-intune"></a>1. comprobar la autoridad de MDM en Intune

Vaya a portal.azure.com y, en la parte superior de la página, busque Intune.
En la página Microsoft Intune, seleccione **inscripción de dispositivo** y, en la página **información general** , asegúrese de que la **autoridad de MDM** es **Intune**.

- Si la **entidad de MDM** es **ninguna**, haga clic en la **entidad de MDM** para establecerla en **Intune**.
- Si **la entidad de MDM** es **Microsoft Office 365**, vaya a dispositivos de inscripción de **dispositivos**  >  **Enroll devices** y use el cuadro de diálogo **Agregar autoridad de MDM** que se encuentra a la derecha para agregar la autoridad de **Intune MDM** (el cuadro de diálogo **Agregar autoridad de MDM** solo está disponible si la autoridad de **MDM** está establecida en Microsoft Office 365).

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Compruebe que Azure AD esté habilitado para unirse a los equipos

- Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> y seleccione **Azure Active Directory** (seleccione Mostrar todo si Azure Active Directory no está visible) en la lista **centros de administración** . 
- En el **centro de administración de Azure Active**Directory, vaya a **Azure Active Directory** , elija **dispositivos** y, a continuación, **configuración de dispositivo**.
- Comprobar**que los usuarios pueden unirse a dispositivos a Azure ad** está habilitado 
    1. Para habilitar todos los usuarios, establezca en **todos**.
    2. Para habilitar usuarios específicos, defina como **seleccionado** para habilitar un grupo específico de usuarios.
        - Agregue los usuarios de dominio que desee sincronizar en Azure AD a un [grupo de seguridad](../admin/create-groups/create-groups.md).
        - Elija **seleccionar grupos** para habilitar el ámbito de usuario de MDM para ese grupo de seguridad.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. comprobar que Azure AD está habilitado para MDM

- Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> y seleccione seleccionar **extremo** **administradora** t (seleccionar **Mostrar todo** si el administrador de puntos de conexión no está visible).
- En el **centro de administración de Microsoft Endpoint Manager**, vaya a **dispositivos**  >  **Windows**inscripción automática de  >  **inscripción**  >  **Automatic Enrollment**.
- Compruebe que el ámbito de usuario de MDM esté habilitado.

    1. Para inscribir todos los equipos, establezca en **todos** para inscribir de forma automática a todos los equipos de los usuarios que se unen a Azure ad y a los nuevos equipos cuando los usuarios agregan una cuenta profesional a Windows.
    2. Establezca en **some** para inscribir los equipos de un grupo específico de usuarios.
        -  Agregue los usuarios de dominio que desee sincronizar en Azure AD a un [grupo de seguridad](../admin/create-groups/create-groups.md).
        -  Elija **seleccionar grupos** para habilitar el ámbito de usuario de MDM para ese grupo de seguridad.

## <a name="4-create-the-required-resources"></a>4. crear los recursos necesarios 

La realización de las tareas necesarias para [configurar la Unión híbrida de Azure ad](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) se ha simplificado mediante el uso del cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) que se encuentra en el módulo de PowerShell [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) . Al invocar este cmdlet, creará y configurará el punto de conexión de servicio y la Directiva de grupo necesarios.

Puede instalar este módulo invocando lo siguiente desde una instancia de PowerShell:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> Se recomienda instalar este módulo en el servidor Windows que ejecuta Azure AD Connect.

Para crear el punto de conexión de servicio y la Directiva de grupo necesarios, deberá invocar el cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) . Para llevar a cabo esta tarea, necesitará sus credenciales de administrador global de Microsoft 365 empresa Premium. Cuando esté listo para crear los recursos, invoque lo siguiente:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

El primer comando establecerá una conexión con la nube de Microsoft y, cuando se le solicite, especifique sus credenciales de administrador global de Microsoft 365 empresa Premium.

## <a name="5-link-the-group-policy"></a>5. vincular la Directiva de grupo

1. En la consola de administración de directivas de grupo (GPMC), haga clic con el botón secundario en la ubicación en la que desea vincular la Directiva y seleccione *vincular un GPO existente...* en el menú contextual.
2. Seleccione la directiva creada en el paso anterior y, a continuación, haga clic en **Aceptar**.

## <a name="get-the-latest-administrative-templates"></a>Obtener las plantillas administrativas más recientes

Si no ve la Directiva habilitar la **inscripción automática de MDM con credenciales de Azure ad predeterminadas**, puede deberse a que no tiene instalado ADMX para Windows 10, versión 1803, versión 1809 o versión 1903. Para solucionar el problema, siga estos pasos (Nota: la versión más reciente de MDM. ADMX es compatible con versiones anteriores):

1.  Descargar: [plantillas administrativas (. admx) para Windows 10 May 2019 actualización (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).
2.  Instale el paquete en el controlador de dominio principal (PDC).
3.  Navegue, en función de la versión de la carpeta: **c:\Archivos de programa (x86) \Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.
4.  Cambie el nombre de la carpeta de **definiciones de directiva** en la ruta de acceso anterior a **PolicyDefinitions**.
5.  Copie la carpeta **PolicyDefinitions** en **C:\Windows\SYSVOL\domain\Policies**. 
    -   Si tiene previsto usar una tienda de directivas central para todo el dominio, agregue allí el contenido de PolicyDefinitions.
6.  Reinicie el controlador de dominio principal para que la Directiva esté disponible. Este procedimiento también funcionará para versiones futuras.

En este momento, podrá ver la directiva **Habilitar la inscripción automática de MDM con credenciales de Azure ad predeterminadas** disponibles.
