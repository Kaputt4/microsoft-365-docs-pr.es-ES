---
title: Habilitar dispositivos Windows 10 unidos a un dominio para que sean administrados por Microsoft 365 para empresas
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
description: Aprende a habilitar Microsoft 365 para proteger los dispositivos Windows 10 locales unidos a Active Directory en tan solo unos pasos.
ms.openlocfilehash: 6275c6c4be9cd9631ab095f8b0e1b39683022bb2
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560851"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Habilitar dispositivos Windows 10 unidos a un dominio para que sean administrados por Microsoft 365 Empresa Premium

Si tu organización usa Windows Server Active Directory local, puedes configurar Microsoft 365 Empresa Premium para proteger los dispositivos Windows 10, a la vez que mantienes el acceso a los recursos locales que requieren autenticación local.
Para configurar esta protección, puede implementar dispositivos unidos **a Azure AD híbrido.** Estos dispositivos se unen a active directory local y a Azure Active Directory.

En este vídeo se describen los pasos para configurarlo para el escenario más común, que también se detalla en los pasos siguientes.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>Antes de empezar, asegúrese de completar estos pasos:
- Sincronizar usuarios con Azure AD con Azure AD Connect.
- Complete la sincronización de la unidad organizativa (OU) de Azure AD Connect.
- Asegúrese de que todos los usuarios de dominio que sincronice tengan licencias para Microsoft 365 Empresa Premium.

Consulte [Sincronizar usuarios de dominio con Microsoft](manage-domain-users.md) para ver los pasos.

## <a name="1-verify-mdm-authority-in-intune"></a>1. Comprobar la autoridad MDM en Intune

Ve a [Endpoint Manager y,](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) en la página de  Microsoft Intune, selecciona **Inscripción** de dispositivos y, a continuación, en la página Información general, asegúrate de que la entidad **de MDM** sea **Intune.**

- Si **la entidad de MDM** es **Ninguna,** haz clic en la autoridad **MDM** para establecerla en **Intune.**
- Si  la entidad de MDM es Microsoft Office  **365,** ve a Dispositivos Inscribir dispositivos y usa el cuadro de diálogo Agregar entidad de mdma de la derecha para agregar la autoridad MDM de Intune (el cuadro de diálogo Agregar entidad de mdma solo está disponible si la entidad de MDM está establecida en  >   Microsoft Office 365).    

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Comprobar que Azure AD está habilitado para unirse a equipos

- Vaya al centro de administración y seleccione Azure Active Directory (seleccione Mostrar todo si Azure Active Directory no está visible) en la lista <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **Centros de** administración.  
- En el **Centro de administración de Azure Active Directory,** vaya a Azure Active **Directory,** elija **Dispositivos** y, a continuación, Configuración **de dispositivos.**
- Comprobar **que los usuarios pueden unir dispositivos a Azure AD** está habilitado 
    1. Para habilitar todos los usuarios, establezca en **Todos**.
    2. Para habilitar usuarios específicos, establezca el valor **seleccionado** para habilitar un grupo específico de usuarios.
        - Agregue los usuarios de dominio deseados sincronizados en Azure AD a un [grupo de seguridad.](../admin/create-groups/create-groups.md)
        - Elige **Seleccionar grupos para** habilitar el ámbito de usuario MDM para ese grupo de seguridad.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Comprobar que Azure AD está habilitado para MDM

- Ve al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  y selecciona **Endpoint Managemen** t (selecciona **Mostrar** todo si **Endpoint Manager** no está visible)
- En el Centro **de administración de Microsoft Endpoint Manager,** vaya a **Dispositivos** windows inscripción automática  >    >  **de Windows**  >  .
- Comprueba que el ámbito de usuario MDM está habilitado.

    1. Para inscribir todos los  equipos, esta establece en Todos para inscribir automáticamente todos los equipos de usuario que están unidos a Azure AD y los equipos nuevos cuando los usuarios agregan una cuenta de trabajo a Windows.
    2. Se establece **en Algunos** para inscribir los equipos de un grupo específico de usuarios.
        -  Agregue los usuarios de dominio deseados sincronizados en Azure AD a un [grupo de seguridad.](../admin/create-groups/create-groups.md)
        -  Elige **Seleccionar grupos para** habilitar el ámbito de usuario MDM para ese grupo de seguridad.

## <a name="4-create-the-required-resources"></a>4. Crear los recursos necesarios 

La realización de las tareas necesarias para configurar la unión híbrida de [Azure AD](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) se ha simplificado mediante el uso del cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) que se encuentra en el módulo [de PowerShell SecMgmt.](https://www.powershellgallery.com/packages/SecMgmt) Al invocar este cmdlet, se creará y configurará el punto de conexión de servicio y la directiva de grupo necesarios.

Puede instalar este módulo invocando lo siguiente desde una instancia de PowerShell:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> Se recomienda instalar este módulo en Windows Server que ejecuta Azure AD Connect.

Para crear el punto de conexión de servicio y la directiva de grupo necesarios, invocará el cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) Necesitará sus credenciales de administrador global de Microsoft 365 Empresa Premium al realizar esta tarea. Cuando esté listo para crear los recursos, invoque lo siguiente:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

El primer comando establecerá una conexión con la nube de Microsoft y, cuando se le solicite, especifique sus credenciales de administrador global de Microsoft 365 Empresa Premium.

## <a name="5-link-the-group-policy"></a>5. Vincular la directiva de grupo

1. En la Consola de administración de directivas de grupo (GPMC), haz clic con el botón derecho en la ubicación donde quieres vincular la directiva y selecciona Vincular un *GPO existente...* en el menú contextual.
2. Seleccione la directiva creada en el paso anterior y, a continuación, haga clic en **Aceptar.**

## <a name="get-the-latest-administrative-templates"></a>Obtener las plantillas administrativas más recientes

Si no ves la directiva Habilitar la inscripción automática de MDM con credenciales predeterminadas de **Azure AD,** puede deberse a que no tienes el ADMX instalado para Windows 10, versión 1803, versión 1809 o versión 1903. Para solucionar el problema, sigue estos pasos (Nota: el mdm.admx más reciente es compatible con versiones anteriores):

1.  Descarga: [Plantillas administrativas (.admx) para Windows 10 May 2019 Update (1903).](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all)
2.  Instale el paquete en el controlador de dominio principal (PDC).
3.  Navegue, según la versión a la carpeta: C:\Archivos de programa **(x86)\Directiva de grupo de Microsoft\Windows 10 May 2019 Update (1903) v3**.
4.  Cambie el nombre **de la carpeta Definiciones de** directiva de la ruta de acceso anterior a **PolicyDefinitions**.
5.  Copie **la carpeta PolicyDefinitions** en **C:\Windows\SYSVOL\domain\Policies**. 
    -   Si planea usar un almacén de directivas central para todo el dominio, agregue allí el contenido de PolicyDefinitions.
6.  Reinicie el controlador de dominio principal para que la directiva esté disponible. Este procedimiento también funcionará para cualquier versión futura.

En este punto, deberías poder ver la directiva Habilitar la inscripción automática de MDM con las credenciales predeterminadas **de Azure AD disponibles.**
