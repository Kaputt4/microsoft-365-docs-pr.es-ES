---
title: Dispositivos compartidos
description: Cómo y cuándo usar el modo de dispositivo compartido
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
ms.openlocfilehash: 8c8d79313ee858ebcac8754b96046b517a3f614a
ms.sourcegitcommit: 5eff41a350a01e18d9cdd572c9d8ff99d6c9563a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2022
ms.locfileid: "64835982"
---
# <a name="shared-devices"></a>Dispositivos compartidos

Microsoft Managed Desktop permite registrar dispositivos en "modo de dispositivo compartido", de forma similar al modo de dispositivo compartido que ofrece [Microsoft Intune](/mem/intune/configuration/shared-user-device-settings).

Los dispositivos en este modo están optimizados para situaciones en las que los usuarios no están vinculados a un solo escritorio y cambian con frecuencia. Por ejemplo, trabajadores de primera línea, como cajeros bancarios o personal de enfermería. Puede aplicar cualquiera de los [perfiles](profiles.md) de Microsoft Managed Desktop a los dispositivos en este modo. Los dispositivos registrados en este modo tienen algunas diferencias importantes:

- [El almacenamiento de](#device-storage) dispositivos está optimizado para usuarios compartidos.
- [Se eliminan las cuentas inactivas](#deletion-of-inactive-accounts) .
- [Las cuentas de invitado](#guest-accounts) no se admiten de forma predeterminada.
- [Microsoft 365 Aplicaciones](#microsoft-365-apps-for-enterprise) para licencias empresariales está optimizado para dispositivos compartidos.

Dado que elige usar el modo de dispositivo compartido en el punto de registro en Microsoft Managed Desktop, si desea cambiar de este modo más adelante, debe anular el registro y registrarlo de nuevo.

## <a name="when-to-use-shared-device-mode"></a>Cuándo usar el modo de dispositivo compartido

Use el modo de dispositivo compartido en situaciones en las que los usuarios cambian con frecuencia de dispositivos.

Por ejemplo, es posible que los cajeros bancarios estén en una ubicación que administre los depósitos, pero que se trasladen a una oficina para ayudar a los clientes con una hipoteca. En cada una de esas ubicaciones, el dispositivo ejecuta diferentes aplicaciones y está optimizado para esas tareas, aunque varias personas las usan.

Por lo general, el personal de enfermería se mueve entre salas y oficinas a medida que interactúa con los pacientes. Pueden iniciar sesión en una estación de trabajo en una oficina, pero conectarse a su escritorio remoto y tomar notas, y repetir este proceso en otra sala con un paciente diferente.

## <a name="when-not-to-use-shared-device-mode"></a>Cuándo no usar el modo de dispositivo compartido

El modo de dispositivo compartido no es una buena opción en estas situaciones:

- Cuando los archivos de un usuario deben almacenarse localmente en lugar de en la nube.
- Si la experiencia del usuario debe ser diferente para distintos usuarios en el dispositivo.
- Si el conjunto de aplicaciones que necesita cada usuario difiere mucho.

## <a name="register-new-devices-using-the-windows-autopilot-self-deploying-mode-profile-in-microsoft-managed-desktop"></a>Registro de nuevos dispositivos mediante el perfil de modo de implementación automática Windows Autopilot en Microsoft Managed Desktop

Tanto si usted como un asociado están controlando el registro de dispositivos, puede optar por usar el perfil de [modo de implementación automática Windows Autopilot](/mem/autopilot/self-deploying) en Microsoft Managed Desktop.

### <a name="before-you-begin"></a>Antes de empezar

Revise los requisitos de Windows modo de implementación automática de Autopilot:

> [!IMPORTANT]
> No se puede volver a inscribir automáticamente un dispositivo a través de Autopilot después de una implementación inicial en modo de implementación automática. En su lugar, elimine el registro del dispositivo en el [centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431). Para eliminar el registro de dispositivo del centro de administración, seleccione **DispositivosTodos** >  **los dispositivos** > seleccione los dispositivos que desea eliminar > **Eliminar**.  Para obtener más información, consulte [Actualizaciones de la experiencia de inicio de sesión e implementación de Windows Autopilot](https://techcommunity.microsoft.com/t5/intune-customer-success/updates-to-the-windows-autopilot-sign-in-and-deployment/ba-p/2848452).

#### <a name="trusted-platform-module"></a>Módulo de plataforma segura

El modo de implementación automática usa el hardware TPM 2.0 de un dispositivo para autenticar el dispositivo en el inquilino Azure Active Directory de una organización. Por lo tanto, los dispositivos sin TPM 2.0 no pueden usar este modo. Los dispositivos también deben admitir la atestación de dispositivos TPM. Todos los dispositivos Windows nuevos deben cumplir estos requisitos. El proceso de atestación de TPM también requiere acceso a un conjunto de direcciones URL HTTPS que son únicas para cada proveedor de TPM. Para obtener más información, consulte la entrada para el modo de autoimplementación de Autopilot y el aprovisionamiento previo de Autopilot en [Requisitos de red](/mem/autopilot/self-deploying#requirements). Para obtener más información sobre Windows requisitos de software de Autopilot, consulte [Windows requisitos de software de Autopilot](/mem/autopilot/software-requirements).

> [!TIP]
> Si intenta implementar el modo de implementación automática en un dispositivo que no tiene compatibilidad con TPM 2.0 o está en una máquina virtual, el proceso producirá un error al comprobar el dispositivo con el siguiente error: 0x800705B4 error de tiempo de espera (no se admiten los TPMs virtuales de Hyper-V). Tenga en cuenta también que Windows 10 versión 1903 o posterior es necesario usar el modo de implementación automática debido a problemas con la atestación de dispositivos TPM en Windows 10 versión 1809. Dado que Windows 10 Enterprise LTSC de 2019 se basa en Windows 10 versión 1809, el modo de implementación automática tampoco se admite en Windows 10 Enterprise LTSC de 2019.
>
> Para obtener más información sobre otros problemas conocidos y revisar soluciones, consulte [Windows problemas conocidos de Autopilot](/mem/autopilot/known-issues) y [Solución de problemas de importación e inscripción de dispositivos autopilot](/mem/autopilot/troubleshoot-device-enrollment).

### <a name="steps-to-register-devices-to-use-the-windows-autopilot-self-deploying-mode-profile"></a>Pasos para registrar dispositivos para usar el perfil Windows modo de implementación automática de Autopilot

Si está registrando dispositivos usted mismo, debe importar nuevos dispositivos en la hoja dispositivos Windows Autopilot.

**Para importar nuevos dispositivos en la hoja Windows Dispositivos Autopilot:**

1. Recopile el [hash de hardware](../get-started/manual-registration.md#obtain-the-hardware-hash) para los nuevos dispositivos a los que desea asignar el perfil Windows modo de implementación automática de Autopilot.
2. Vaya al [portal de Microsoft Endpoint Manager](https://endpoint.microsoft.com).
2. Seleccione **Dispositivos** en el menú de navegación izquierdo.
3. En la sección **Por plataforma**, seleccione **Windows**. A continuación, seleccione **Windows Inscripción**.
4. En la sección **programa Windows Autopilot Deployment**, seleccione **Dispositivos**.
5. [Importe](../get-started/manual-registration.md#register-devices-by-using-the-admin-portal) el archivo .CSV que contiene todos los hashes de hardware recopilados en el paso 1.
6. Después de cargar los dispositivos Windows Autopilot, debe editar el atributo de etiqueta de grupo de los dispositivos importados para que Microsoft Managed Desktop pueda registrarlos mediante el perfil de modo de autoimplementación Windows Autopilot. Consulte a continuación los atributos de etiqueta de grupo. Debe anexar **-Shared** a la etiqueta de grupo, como se muestra en la tabla siguiente:

| Perfil de dispositivo | Etiqueta de grupo de Autopilot (modo estándar) | Etiqueta de grupo (modo de dispositivo compartido) |
| ----- | ----- | ----- |
| Datos confidenciales | Microsoft365Managed_SensitiveData |  Microsoft365Managed_SensitiveData-Shared |
| Usuario avanzado | Microsoft365Managed_PowerUser | No admitido |
| Estándar  | Microsoft365Managed_Standard | Microsoft365Managed_Standard-Shared |

> [!WARNING]
> No intente editar el atributo de pestaña de grupo anexando **-Shared** a los dispositivos importados anteriormente a Windows Autopilot. Los dispositivos ya importados en Windows Autopilot, con una de las etiquetas de grupo de Microsoft Managed Desktop a partir de *Microsoft365Managed_*, pero sin **-Shared** anexado inicialmente, ya forman parte de un grupo de Azure Active Directory diferente. Este grupo de Azure Active Directory no tiene asignado el perfil de modo de implementación automática Windows Autopilot. Si debe volver a crear un dispositivo existente para que sea un dispositivo compartido, debe eliminar y volver a registrar el dispositivo en Windows Autopilot de nuevo.

Si tiene dispositivos de inscripción de asociados, siga los pasos descritos en [Registro de asociados](../get-started/partner-registration.md), pero anexe **-Shared** a la etiqueta de grupo, como se muestra en la tabla anterior.

## <a name="consequences-of-shared-device-mode"></a>Consecuencias del modo de dispositivo compartido

### <a name="device-storage"></a>Almacenamiento del dispositivo

Los usuarios de dispositivos compartidos deben hacer una copia de seguridad de sus datos en la nube para que puedan seguirlos a otros dispositivos. Una vez que haya registrado dispositivos en modo de dispositivo compartido, asegúrese de habilitar las características de redireccionamiento de [archivos a petición](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e#:~:text=%20Turn%20on%20Files%20On-Demand%20%201%20Make,files%20as%20you%20use%20them%20box.%20More%20) y [carpetas conocidas](/onedrive/redirect-known-folders) de OneDrive. Este enfoque minimiza el efecto que tiene cada perfil de usuario en el almacenamiento del dispositivo. Los dispositivos en modo de dispositivo compartido eliminan automáticamente los perfiles de usuario si el espacio libre en disco cae por debajo del 25 %. Esta actividad está programada para medianoche en la hora local del dispositivo, a menos que el almacenamiento se limite críticamente.

Microsoft Managed Desktop usa el CSP [de SharedPC](/mem/intune/configuration/shared-user-device-settings-windows) para realizar estas operaciones, así que asegúrese de no usar esos CSP usted mismo.

> [!IMPORTANT]
> Entrene a los usuarios que después de haber descargado un archivo grande deben confirmar que ven el icono de comprobación verde en el archivo antes de cerrar la sesión. Si su cuenta se elimina como parte de las operaciones de limpieza y el archivo no se carga por completo en OneDrive, el archivo se perderá permanentemente.

### <a name="deletion-of-inactive-accounts"></a>Eliminación de cuentas inactivas

El modo de dispositivo compartido quita las cuentas en las que no se ha iniciado sesión durante más de 30 días.

### <a name="guest-accounts"></a>Cuentas de invitado

Los dispositivos en modo de dispositivo compartido solo permiten cuentas que están unidas a un dominio. Si necesita cuentas de invitado en un dispositivo, puede presentar una [solicitud de cambio](../working-with-managed-desktop/admin-support.md) para solicitar que se habiliten.

### <a name="microsoft-365-apps-for-enterprise"></a>Aplicaciones de Microsoft 365 para empresas

[Aplicaciones Microsoft 365 para empresas](/microsoft-365/managed-desktop/get-started/m365-apps) normalmente permite a un usuario determinado instalar esas aplicaciones en solo cinco dispositivos al mismo tiempo. En el modo de dispositivo compartido, las aplicaciones no cuentan con respecto al límite, por lo que pueden usarlas durante la itinerancia entre dispositivos. La implementación y las actualizaciones de Aplicaciones Microsoft 365 para empresas funcionan como de costumbre.

### <a name="device-profiles"></a>Perfiles de dispositivo

En el modo de dispositivo compartido, solo puede tener un [perfil de dispositivo](profiles.md) en un dispositivo determinado. Además, el perfil de dispositivo de usuario avanzado no se admite actualmente en modo de dispositivo compartido.

### <a name="apps-and-policies-assigned-to-users"></a>Aplicaciones y directivas asignadas a los usuarios

En los dispositivos compartidos, debe asignar las aplicaciones o directivas que esté administrando a *los grupos de dispositivos*, no a los grupos de usuarios. La asignación a grupos de dispositivos garantiza que cada usuario tenga una experiencia más coherente. La excepción es [Portal de empresa](#deploying-apps-with-company-portal).

## <a name="limitations-of-shared-device-mode"></a>Limitaciones del modo de dispositivo compartido

### <a name="windows-hello"></a>Windows Hello

Windows Hello usa la emulación de tarjeta inteligente para almacenar en caché de forma segura [los PIN de usuario](/windows/security/identity-protection/hello-for-business/hello-faq), lo que minimiza el número de veces que los usuarios tienen que autenticarse. Sin embargo, Windows solo permite 10 tarjetas inteligentes a la vez en un dispositivo determinado. Cuando un usuario número 11 inicia sesión por primera vez, una de las cuentas existentes perderá su tarjeta inteligente. Podrán iniciar sesión, pero su PIN no se almacenará en caché.

### <a name="universal-print"></a>Impresión universal

Cuando Impresión universal instala una impresora para un único usuario en un dispositivo compartido, esa impresora está disponible para todos los usuarios de ese dispositivo. No hay ninguna manera de aislar las impresoras entre usuarios en dispositivos compartidos.

## <a name="limitations-of-shared-device-mode-in-the-public-preview-release"></a>Limitaciones del modo de dispositivo compartido en la versión preliminar pública

### <a name="primary-user"></a>Usuario principal

Cada dispositivo Microsoft Intune tiene un usuario principal, que se asigna cuando Autopilot configura un dispositivo. Pero cuando se comparten dispositivos, Intune requiere que se quite el usuario principal.

> [!IMPORTANT]
> Mientras el modo de dispositivo compartido está en versión preliminar pública, asegúrese de quitar el usuario principal siguiendo estos pasos: inicie sesión en el centro de administración de Microsoft Endpoint Manager, seleccione **DispositivosTodos**> **los dispositivos**, seleccione un dispositivo, **propiedadesRemover**> usuario principal y elimine el usuario que aparece allí.

### <a name="deploying-apps-with-company-portal"></a>Implementación de aplicaciones con Portal de empresa

Es probable que algunas aplicaciones no necesiten estar presentes en todos los dispositivos, por lo que es posible que prefiera que los usuarios solo instalen esas aplicaciones cuando las necesiten de [Portal de empresa](/mem/intune/user-help/install-apps-cpapp-windows).

Microsoft Managed Desktop deshabilita Portal de empresa de forma predeterminada para los dispositivos en modo de dispositivo compartido. Si desea que el Portal de empresa esté habilitado, puede presentar una solicitud de [cambio](../working-with-managed-desktop/admin-support.md). Sin embargo, debe tener en cuenta algunas limitaciones de esta característica en esta versión preliminar pública:

- Para que una aplicación esté disponible para los usuarios de Portal de empresa, [asigne un grupo de usuarios](/mem/intune/apps/apps-deploy) a esa aplicación en Intune y, a continuación, agregue cada usuario a ese grupo de usuarios.
- Los dispositivos no pueden tener un [usuario principal](#primary-user).
- Para desinstalar una aplicación que un usuario instaló a través de Portal de empresa, debe desinstalar la aplicación de todos los usuarios de ese dispositivo.

> [!CAUTION]
> Portal de empresa no admite aplicaciones asignadas a grupos de dispositivos como disponibles.

### <a name="redeployment-of-microsoft-365-apps-for-enterprise"></a>Reimplementación de Aplicaciones Microsoft 365 para Enterprise

Durante la versión preliminar pública, si se debe volver a implementar Aplicaciones Microsoft 365, los usuarios deben ponerse en contacto con el personal de soporte técnico local para solicitar que un agente eleve y vuelva a instalar Aplicaciones Microsoft 365 para empresas en ese dispositivo.

### <a name="microsoft-teams"></a>Microsoft Teams

Cuando un usuario inicia Teams por primera vez, se le pedirá que actualice la aplicación antes de poder usarla. Una vez que permiten la actualización, Teams se mantendrá actualizado en segundo plano.
