---
title: Permitir que los dispositivos Windows 10 unidos a un dominio se administren mediante Microsoft 365 para empresas
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
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
description: Aprenda a habilitar Microsoft 365 para proteger dispositivos locales unidos a Active Directory Windows 10 en unos pocos pasos.
ms.openlocfilehash: de50fc8ac5ad3fe5d5f8cd5cfdfd781d94062358
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "65319099"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Habilitación de dispositivos Windows 10 unidos a un dominio para que los administre Microsoft 365 Empresa Premium

Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 Empresa Premium para proteger los dispositivos Windows 10, a la vez que mantiene el acceso a los recursos locales que requieren autenticación local.

Para configurar esta protección, puede implementar **Dispositivos unidos a Azure AD híbrido**. Estos dispositivos se unen tanto al Active Directory local como a Azure Active Directory.

> [!NOTE]
> Microsoft Defender para Empresas se implementará para los clientes de Microsoft 365 Empresa Premium a partir del 1 de marzo de 2022. Esta oferta proporciona características de seguridad adicionales para los dispositivos. [Más información sobre Defender para Empresas](../security/defender-business/mdb-overview.md).

## <a name="watch-configure-hybrid-azure-active-directory-join"></a>Vea: Configurar la unión a Azure Active Directory híbrido

En este vídeo se describen los pasos para configurar esto para el escenario más común, que también se detalla en los pasos siguientes.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="before-you-begin"></a>Antes de empezar

- Sincronice los usuarios con Azure AD mediante Azure AD Connect.
- Complete la sincronización de unidad organizativa (OU) de Azure AD Connect.
- Asegúrese de que todos los usuarios del dominio que sincronice tengan licencias para Microsoft 365 Empresa Premium.

Consulte [Sincronizar usuarios del dominio con Microsoft 365](../admin/setup/manage-domain-users.md) para ver los pasos.

## <a name="1-verify-mdm-authority-in-intune"></a>1. Compruebe la entidad de MDM en Intune

Vaya al Centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview)) y seleccione **Inscripción de dispositivos** y, en la página **Información general**, asegúrese de que **Entidad de MDM** sea **Intune**.

- Si **Entidad de MDM** es **Ninguna**, haga clic en **Entidad de MDM** para establecerla en **Intune**.
- Si **Entidad de MDM** es **Microsoft Office 365**, vaya a **Dispositivos** > **Inscribir dispositivos** y use el cuadro de diálogo **Agregar entidad de MDM** de la derecha para agregar la entidad de **MDM de Intune** (el cuadro de diálogo **Agregar entidad de MDM** solo está disponible si la **Entidad de MDM** está establecida en Microsoft Office 365).

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Compruebe que Azure AD está habilitado para los equipos que se unan

1. Vaya a la Centro de administración de Microsoft 365 en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> y seleccione **Azure Active Directory** (seleccione Mostrar todo si Azure Active Directory no está visible) en la lista **Centros de administración**. 

2. En el **centro de administración de Azure Active Directory**, vaya a **Azure Active Directory**, elija **Dispositivos** y, después, **Configuración del dispositivo**.

3. Compruebe que **Los usuarios pueden unir dispositivos a Azure AD** está habilitado 

    1. Para habilitar todos los usuarios, establézcalo en **Todos**.

    2. Para habilitar usuarios específicos, establezca esta opción en **Seleccionados** para habilitar un grupo específico de usuarios.

        - Agregue los usuarios de dominio deseados sincronizados en Azure AD a un [grupo de seguridad](../admin/create-groups/create-groups.md).

        - Elija **Seleccionar grupos** para habilitar el ámbito de usuario de MDM para ese grupo de seguridad.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Compruebe que Azure AD está habilitado para MDM

1. Vaya a la Centro de administración de Microsoft 365 en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> y seleccione **Administración de puntos de conexión** (seleccione **Mostrar todo** si **Endpoint Manager** no está visible).

2. En el **Centro de administración de Microsoft Endpoint Manager**, vaya a **Dispositivos** > **Windows** > **Inscripción de Windows** > **Inscripción automática**.

3. Compruebe que el ámbito de usuario de MDM está habilitado.

    1. Para inscribir todos los equipos, establezca esta opción en **Todos** para inscribir automáticamente todos los equipos de usuario unidos a Azure AD y equipos nuevos cuando los usuarios agreguen una cuenta profesional a Windows.
  
    2. Establézcalo en **Algunos** para inscribir los equipos de un grupo específico de usuarios.
  
        -  Agregue los usuarios de dominio deseados sincronizados en Azure AD a un [grupo de seguridad](/admin/create-groups/create-groups.md).
  
       -  Elija **Seleccionar grupos** para habilitar el ámbito de usuario de MDM para ese grupo de seguridad.

## <a name="4-create-the-required-resources"></a>4. Cree los recursos necesarios 

La realización de las tareas necesarias para [configurar la unión de Azure AD híbrido](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) se ha simplificado mediante el uso del cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) en el módulo de PowerShell [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt). Al invocar este cmdlet, se creará y configurarán el punto de conexión de servicio y la directiva de grupo necesarios.

Puede instalar este módulo invocando lo siguiente desde una instancia de PowerShell:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> Instale este módulo en la instancia de Windows Server que ejecuta Azure AD Connect.

Para crear el punto de conexión de servicio y la directiva de grupo necesarios, invocará el cmdlet  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md). Necesitará sus credenciales de administrador global de Microsoft 365 Empresa Premium al realizar esta tarea. Cuando esté listo para crear los recursos, invoque lo siguiente:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

El primer comando establecerá una conexión con la nube de Microsoft y, cuando se le solicite, especifique sus credenciales de administrador global de Microsoft 365 Empresa Premium.

## <a name="5-link-the-group-policy"></a>5. Vincule la directiva de grupo

1. En el Consola de administración de directivas de grupo (GPMC), haga clic con el botón derecho en la ubicación donde quiere vincular la directiva y seleccione *Vincular un GPO existente...* en el menú contextual.

2. Seleccione la directiva creada en el paso anterior y haga clic en **Aceptar**.

## <a name="get-the-latest-administrative-templates"></a>Obtener la versión de Plantillas administrativas más reciente

Si no ve la directiva **Habilitar la inscripción automática de MDM con las credenciales de Azure AD predeterminadas**, puede deberse a que no tiene ADMX instalado para Windows 10, versión 1803 o posterior. Para corregir el problema, siga estos pasos (nota: la versión más reciente de MDM.admx es compatible con versiones anteriores):

1. Descargue: [Plantillas administrativas (.admx) para la actualización de Windows 10 de octubre de 2020 (20H2)](https://www.microsoft.com/download/102157).

2. Instale el paquete en un controlador de dominio.

3. Navegue, según la versión de Plantillas administrativas a la carpeta: **C:\Archivos de programa (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.

4. Cambie el nombre de la carpeta **Definiciones de directiva** en la ruta de acceso anterior a **PolicyDefinitions**.

5. Copie la carpeta **PolicyDefinitions** en el recurso compartido SYSVOL, que se encuentra de forma predeterminada en `C:\Windows\SYSVOL\domain\Policies`.

   Si tiene previsto usar un almacén de directivas central para todo el dominio, agregue allí el contenido de PolicyDefinitions.

6. En caso de que tenga varios controladores de dominio, espere a que SYSVOL se replique para que las directivas estén disponibles. Este procedimiento también funcionará para cualquier versión futura de Plantillas administrativas.

En este momento, debería poder ver disponible la directiva **Habilitar la inscripción automática de MDM con las credenciales de Azure AD predeterminadas**.

## <a name="related-content"></a>Contenido relacionado

- [Sincronizar usuarios del dominio con Microsoft 365](../admin/setup/manage-domain-users.md)

- [Crear un grupo en el centro de administración](../admin/create-groups/create-groups.md) 

- [Tutorial: Configurar la unión a Azure Active Directory híbrido para dominios administrados](/azure/active-directory/devices/hybrid-azuread-join-managed-domains) 

- [Configurar las contraseñas de autoservicio](../admin/add-users/let-users-reset-passwords.md)

- [Configurar la administración de grupos de autoservicio](/azure/active-directory/enterprise-users/groups-self-service-management)

- [Procedimientos recomendados para proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)

## <a name="next-objective"></a>Siguiente objetivo:

[Prepararse para la implementación del cliente Office](m365bp-prepare-for-office-client-deployment.md)