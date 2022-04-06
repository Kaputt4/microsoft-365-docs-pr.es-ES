---
title: Habilitar dispositivos de Windows 10 unidos al dominio para que los Microsoft 365 para empresas
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
description: Obtenga información sobre cómo habilitar Microsoft 365 proteger los dispositivos locales unidos a Active-Directory Windows 10 en unos pocos pasos.
ms.openlocfilehash: b57d9f4f13985d5d67b39d6486df089b82f4f05c
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "64635505"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Habilitar dispositivos de Windows 10 unidos al dominio para que los Microsoft 365 Business Premium

> [!NOTE]
> Microsoft Defender für Unternehmen se está implementando para Microsoft 365 Business Premium clientes, a partir del 1 de marzo de 2022. Esta oferta proporciona características de seguridad adicionales para dispositivos. [Obtenga más información sobre Defender para empresas](../security/defender-business/mdb-overview.md).

Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 Business Premium para proteger los dispositivos Windows 10, al tiempo que mantiene el acceso a los recursos locales que requieren autenticación local.
Para configurar esta protección, puedes implementar **dispositivos híbridos Azure AD unidos**. Estos dispositivos se unen tanto al Active Directory local como al Azure Active Directory.

## <a name="watch-configure-hybrid-azure-active-directory-join"></a>Watch: Configure Hybrid Azure Active Directory join

En este vídeo se describen los pasos para configurar esto para el escenario más común, que también se detalla en los pasos siguientes.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="before-you-begin"></a>Antes de empezar

- Sincronizar usuarios para Azure AD con Azure AD Conectar.
- Complete Azure AD Conectar sincronización de unidad organizativa (OU).
- Asegúrese de que todos los usuarios de dominio que sincronice tienen licencias para Microsoft 365 Business Premium.

Consulte [Synchronize domain users to Microsoft 365](../admin/setup/manage-domain-users.md) para ver los pasos.

## <a name="1-verify-mdm-authority-in-intune"></a>1. Compruebe la entidad MDM en Intune

Ve al Centro Microsoft Endpoint Manager administración ([https://endpoint.microsoft.com](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview)) y selecciona Inscripción de dispositivos **y,** a continuación,  en la página Información general, asegúrate de que la entidad de **mdma esté Intune**.

- Si **la entidad MDM** **es None**, haz clic en la **entidad mdma** para establecerla **en Intune**.
- Si  la entidad de MDM es **Microsoft Office 365**, ve a   DispositivosEnrollar  >  dispositivos y usa el cuadro de diálogo Agregar entidad **mdma a** la derecha para agregar una entidad mdma Intune (el cuadro de diálogo Agregar entidad mdma solo está disponible si la entidad de **MDM** está establecida en Microsoft Office 365).

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Compruebe Azure AD está habilitado para unir equipos

1. Vaya a la Centro de administración de Microsoft 365 y <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> seleccione **Azure Active Directory** (seleccione Mostrar todo si Azure Active Directory no está visible) en la lista **Centros de** administración. 

2. En el **centro Azure Active Directory administración**, vaya **a Azure Active Directory** , elija **Dispositivos** y, a continuación, **Configuración del dispositivo**.

3. **VerifyUsers puede unir dispositivos a Azure AD** está habilitado 

    1. Para habilitar todos los usuarios, establezca en **Todos**.

    2. Para habilitar usuarios específicos, establezca en **Seleccionado** para habilitar un grupo específico de usuarios.

        - Agregue los usuarios de dominio deseados sincronizados en Azure AD a un [grupo de seguridad](../admin/create-groups/create-groups.md).

        - Elige **Seleccionar grupos para** habilitar el ámbito de usuario MDM para ese grupo de seguridad.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Comprobar Azure AD está habilitado para MDM

1. Vaya a la Centro de administración de Microsoft 365 en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> y seleccione **Administración** de extremos (seleccione **Mostrar** todo **si Endpoint Manager** no está visible)

2. En el **centro Microsoft Endpoint Manager administración**, vaya a **Dispositivos** >  **Windows** >  **Windows** **EnrollmentAutomatic** >  Enrollment.

3. Compruebe que el ámbito de usuario MDM está habilitado.

    1. Para inscribir todos los equipos, establezca  en Todos para inscribir automáticamente todos los equipos de usuario que estén unidos a Azure AD y equipos nuevos cuando los usuarios agreguen una cuenta de trabajo a Windows.
  
    2. Se establece **en Algunos** para inscribir los equipos de un grupo específico de usuarios.
  
        -  Agregue los usuarios de dominio deseados sincronizados en Azure AD a un [grupo de seguridad](/admin/create-groups/create-groups.md).
  
       -  Elige **Seleccionar grupos para** habilitar el ámbito de usuario MDM para ese grupo de seguridad.

## <a name="4-create-the-required-resources"></a>4. Crear los recursos necesarios 

La realización de las tareas necesarias para configurar la Azure AD [híbrida](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) se ha simplificado mediante el uso del cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) que se encuentra en el módulo [de PowerShell de SecMgmt](https://www.powershellgallery.com/packages/SecMgmt). Al invocar este cmdlet, creará y configurará el punto de conexión de servicio y la directiva de grupo necesarios.

Puede instalar este módulo invocando lo siguiente desde una instancia de PowerShell:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> Instale este módulo en el servidor Windows que ejecuta Azure AD Conectar.

Para crear el punto de conexión de servicio y la directiva de grupo necesarios, invocará el cmdlet  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) . Necesitará sus credenciales de Microsoft 365 Business Premium de administración global al realizar esta tarea. Cuando esté listo para crear los recursos, invoque lo siguiente:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

El primer comando establecerá una conexión con la nube de Microsoft y, cuando se le solicite, especifique las Microsoft 365 Business Premium de administración global.

## <a name="5-link-the-group-policy"></a>5. Vincular el directiva de grupo

1. En la Consola de administración de directiva de grupo (GPMC), haga clic con el botón secundario en la ubicación donde desea vincular la directiva y seleccione Vincular un *GPO existente...* en el menú contextual.

2. Seleccione la directiva creada en el paso anterior y, a continuación, haga clic en **Aceptar**.

## <a name="get-the-latest-administrative-templates"></a>Obtener las plantillas administrativas más recientes

Si no ves la directiva Habilitar la inscripción automática de MDM con credenciales predeterminadas de Azure AD, puede deberse **a** que no tienes el ADMX instalado para Windows 10, versión 1803 o posterior. Para solucionar el problema, siga estos pasos (Nota: la mdm.admx más reciente es compatible con versiones anteriores):

1. Descargar: [Plantillas administrativas (.admx) para Windows 10 actualización de octubre de 2020 (20H2).](https://www.microsoft.com/download/102157).

2. Instale el paquete en un controlador de dominio.

3. Navegue, según la versión de plantillas administrativas a la carpeta: **C:\Program Files (x86)\Microsoft directiva de grupo\Windows 10 October 2020 Update (20H2)**.

4. Cambie el **nombre de la carpeta Definiciones de** directiva de la ruta de acceso anterior **a PolicyDefinitions**.

5. Copie la **carpeta PolicyDefinitions** en el recurso compartido SYSVOL, ubicado de forma predeterminada en `C:\Windows\SYSVOL\domain\Policies`.

   Si planea usar un almacén de directivas central para todo el dominio, agregue allí el contenido de PolicyDefinitions.

6. En caso de que tenga varios controladores de dominio, espere a que SYSVOL se replique para que las directivas estén disponibles. Este procedimiento también funcionará para cualquier versión futura de las plantillas administrativas.

En este punto, deberías poder ver la directiva Habilitar la inscripción **automática de MDM con las Azure AD predeterminadas** disponibles.

## <a name="related-content"></a>Contenido relacionado

- [Sincronizar usuarios de dominio Microsoft 365](../admin/setup/manage-domain-users.md)(artículo)\

- [Crear un grupo en el Centro de administración](../admin/create-groups/create-groups.md) (artículo)\

- [Tutorial: Configurar la combinación Azure Active Directory híbrida para dominios administrados](/azure/active-directory/devices/hybrid-azuread-join-managed-domains) (artículo)

- [Principales 10 formas de proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)
