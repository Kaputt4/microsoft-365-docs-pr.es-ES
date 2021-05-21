---
title: Permitir que los dispositivos de Windows 10 unidos a un dominio se puedan administrar Microsoft 365 para empresas
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: Obtenga información sobre cómo habilitar Microsoft 365 proteger los dispositivos locales unidos a Active-Directory Windows 10 en unos pocos pasos.
ms.openlocfilehash: f16962dd3c33c3c228da507bc5c4a902d76a8a08
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593901"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Habilitar dispositivos de Windows 10 unidos a un dominio para que los pueda administrar Microsoft 365 Empresa Premium

Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 Empresa Premium para proteger los dispositivos Windows 10 y mantener el acceso a los recursos locales que requieren autenticación local.
Para configurar esta protección, puede implementar **dispositivos híbridos unidos a Azure AD**. Estos dispositivos se unen a su Active Directory local y a su Azure Active Directory.

En este vídeo se describen los pasos para configurar esto para el escenario más común, que también se detalla en los pasos siguientes.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>Antes de empezar, asegúrese de completar estos pasos:
- Sincronizar usuarios con Azure AD con Azure AD Conectar.
- Complete la sincronización Conectar unidad organizativa (OU) de Azure AD.
- Asegúrese de que todos los usuarios de dominio que sincronice tengan licencias para Microsoft 365 Empresa Premium.

Consulta [Sincronizar usuarios de dominio con Microsoft](manage-domain-users.md) para ver los pasos.

## <a name="1-verify-mdm-authority-in-intune"></a>1. Comprobar la entidad MDM en Intune

Vaya [a Endpoint Manager y,](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) en la página Microsoft Intune, seleccione Inscripción  de dispositivos **y,** a continuación, en la página Información general, asegúrese de que la entidad de **MDM** es **Intune**.

- Si **la entidad MDM** es **None,** haz clic en la **entidad MDM** para establecerla en **Intune**.
- Si  la entidad MDM es **Microsoft Office 365,** ve a Dispositivos Inscribir dispositivos y usa el cuadro de diálogo Agregar entidad mdma a la derecha para agregar la autoridad MDM de Intune (el cuadro de diálogo Agregar entidad mdma solo está disponible si la entidad mdma está establecida en   >   Microsoft Office 365).    

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Comprobar que Azure AD está habilitado para unir equipos

- Vaya al Centro de administración en y seleccione Azure Active Directory (seleccione Mostrar todo si Azure Active Directory no está visible) en la lista <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **Centros de** administración.  
- En el **Azure Active Directory de administración,** vaya **a Azure Active Directory** , elija **Dispositivos** y, a continuación, **Configuración del dispositivo.**
- Comprobar **que los usuarios pueden unir dispositivos a Azure AD** está habilitado 
    1. Para habilitar todos los usuarios, establezca en **Todos**.
    2. Para habilitar usuarios específicos, establezca en **Seleccionado** para habilitar un grupo específico de usuarios.
        - Agregue los usuarios de dominio deseados sincronizados en Azure AD a un [grupo de seguridad.](../admin/create-groups/create-groups.md)
        - Elige **Seleccionar grupos para** habilitar el ámbito de usuario MDM para ese grupo de seguridad.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Comprobar que Azure AD está habilitado para MDM

- Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> y seleccione **Administradores de puntos** de conexión t (seleccione **Mostrar** todo si **Endpoint Manager** no está visible)
- En el **Centro Microsoft Endpoint Manager administración,** vaya a **Dispositivos**  >  **Windows**  >  **Windows Inscripción**  >  **automática**.
- Compruebe que el ámbito de usuario MDM está habilitado.

    1. Para inscribir todos los  equipos, establezca en Todos para inscribir automáticamente todos los equipos de usuario unidos a Azure AD y los equipos nuevos cuando los usuarios agreguen una cuenta de trabajo a Windows.
    2. Se establece **en Algunos** para inscribir los equipos de un grupo específico de usuarios.
        -  Agregue los usuarios de dominio deseados sincronizados en Azure AD a un [grupo de seguridad.](../admin/create-groups/create-groups.md)
        -  Elige **Seleccionar grupos para** habilitar el ámbito de usuario MDM para ese grupo de seguridad.

## <a name="4-create-the-required-resources"></a>4. Crear los recursos necesarios 

La realización de las tareas necesarias para configurar la combinación híbrida de [Azure AD](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) se ha simplificado mediante el uso del cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) que se encuentra en el módulo [De PowerShell de SecMgmt.](https://www.powershellgallery.com/packages/SecMgmt) Al invocar este cmdlet, creará y configurará el punto de conexión de servicio y la directiva de grupo necesarios.

Puede instalar este módulo invocando lo siguiente desde una instancia de PowerShell:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> Se recomienda instalar este módulo en el servidor Windows que ejecuta Azure AD Conectar.

Para crear el punto de conexión de servicio y la directiva de grupo necesarios, invocará el cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) Necesitará sus credenciales de Microsoft 365 Empresa Premium de administración global al realizar esta tarea. Cuando esté listo para crear los recursos, invoque lo siguiente:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

El primer comando establecerá una conexión con la nube de Microsoft y, cuando se le solicite, especifique sus Microsoft 365 Empresa Premium de administración global.

## <a name="5-link-the-group-policy"></a>5. Vincular la directiva de grupo

1. En la Consola de administración de directivas de grupo (GPMC), haga clic con el botón secundario en la ubicación donde desea vincular la directiva y seleccione Vincular un *GPO existente...* en el menú contextual.
2. Seleccione la directiva creada en el paso anterior y, a continuación, haga clic en **Aceptar**.

## <a name="get-the-latest-administrative-templates"></a>Obtener las plantillas administrativas más recientes

Si no ve la directiva Habilitar la inscripción automática de MDM con credenciales predeterminadas de **Azure AD,** puede deberse a que no tiene el ADMX instalado para Windows 10, versión 1803 o posterior. Para solucionar el problema, siga estos pasos (Nota: la mdm.admx más reciente es compatible con versiones anteriores):

1.  Descargar: [Plantillas administrativas (.admx) para Windows 10 actualización de octubre de 2020 (20H2).](https://www.microsoft.com/download/102157)
2.  Instale el paquete en un controlador de dominio.
3.  Navegue, según la versión de plantillas administrativas a la carpeta: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.
4.  Cambie el nombre de la carpeta **Definiciones de** directiva de la ruta de acceso anterior **a PolicyDefinitions**.
5.  Copie la **carpeta PolicyDefinitions** en el recurso compartido SYSVOL, ubicado de forma predeterminada en **C:\Windows\SYSVOL\domain\Policies**. 
    -   Si planea usar un almacén de directivas central para todo el dominio, agregue allí el contenido de PolicyDefinitions.
6.  En caso de que tenga varios controladores de dominio, espere a que SYSVOL se replique para que las directivas estén disponibles. Este procedimiento también funcionará para cualquier versión futura de las plantillas administrativas.

En este punto, debería poder ver la directiva Habilitar la inscripción **automática de MDM con las credenciales predeterminadas de Azure AD** disponibles.

## <a name="related-content"></a>Contenido relacionado

[Sincronizar usuarios de dominio Microsoft 365](manage-domain-users.md) (artículo)

[Crear un grupo en el Centro de administración](../admin/create-groups/create-groups.md) (artículo)

[Tutorial: Configurar la combinación Azure Active Directory híbrida para dominios administrados](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (artículo)