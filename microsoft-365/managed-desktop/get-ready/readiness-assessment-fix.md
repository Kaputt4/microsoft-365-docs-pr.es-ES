---
title: Solucionar los problemas detectados por la herramienta de evaluación de la preparación
description: Acciones detalladas que se deben realizar para cada problema que encuentre la herramienta
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: badf2d65f2b29e265a1312cb1d5f4802a44f3cb3
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2022
ms.locfileid: "62766553"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>Solucionar los problemas detectados por la herramienta de evaluación de la preparación

Para cada comprobación, la herramienta mostrará uno de los cuatro resultados posibles:

| Resultado  | Significado |
| ----- | ----- |
| Listo | No se requiere ninguna acción antes de completar la inscripción. |
| Advertencia | Siga los pasos de la herramienta o de este artículo para obtener la mejor experiencia con la inscripción y para los usuarios. <br><br> Puedes *completar* la inscripción, pero debes solucionar estos problemas antes de implementar el primer dispositivo. |
| No preparado | **La inscripción producirá un error si no se solucionan estos problemas.** <br><br> Siga los pasos de la herramienta o de este artículo para resolverlos. |
| Error | El Azure Active Directory (AD) que está usando no tiene permisos suficientes para ejecutar esta comprobación. |

> [!NOTE]
> Los resultados notificados por esta herramienta reflejan el estado de la configuración solo en el momento en que la ejecutó. Si realiza cambios más adelante en las directivas de Microsoft Intune, Azure Active Directory o Microsoft 365, los elementos que estaban "Listos" pueden convertirse en "No listos". Para evitar problemas con las operaciones de Escritorio administrado de Microsoft, compruebe la configuración específica descrita en este artículo antes de cambiar las directivas.

## <a name="microsoft-intune-settings"></a>Microsoft Intune configuración

Puedes acceder a la configuración de Intune en el centro Microsoft Endpoint Manager [administración](https://endpoint.microsoft.com).

### <a name="autopilot-deployment-profile"></a>Perfil de implementación de Autopilot

No debe tener perfiles de Autopilot existentes destinados a grupos dinámicos o asignados con dispositivos de Escritorio administrado de Microsoft. Microsoft Managed Desktop usa Autopilot para configurar nuevos dispositivos. Si tienes un perfil de implementación de Autopilot existente, la configuración Convertir todos los dispositivos de destino en **Autopilot** debe establecerse en **No** para que la prueba de preparación de Microsoft Managed Desktop Autopilot se haga correctamente.

| Resultado  | Significado |
| ----- | ----- |
| No preparado | Tienes un perfil de Autopilot que está asignado a todos los dispositivos. <br><br> Para obtener más información, vea [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot). Después de la inscripción de Microsoft Managed Desktop, establece la directiva de Autopilot para excluir el **grupo Modern Workplace Devices - All** Azure AD.
| Advertencia | Asegúrese de que los perfiles de Autopilot están destinados a un grupo de Azure AD asignado o dinámico que no incluya dispositivos de Escritorio administrado de Microsoft. <br><br> Para obtener más información, vea [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot). Después de la inscripción de Microsoft Managed Desktop, establece los perfiles de Autopilot para excluir el **grupo Modern Workplace Devices - All** Azure AD. |

### <a name="certificate-connectors"></a>Conectores de certificado

Si tienes algún conector de certificado que usarás los dispositivos que quieras inscribir en Microsoft Managed Desktop, los conectores no deben tener ningún error. Solo se aplicará uno de los siguientes avisos a su situación, así que compróquelos cuidadosamente.

| Resultado  | Significado |
| ----- | ----- |
| Advertencia | No hay conectores de certificado presentes. Es posible que no necesite ningún conector, pero debe evaluar si es posible que necesite algunos para la conectividad de red en los dispositivos de Escritorio administrado de Microsoft. <br><br> Para obtener más información, vea [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md). |
| Advertencia | Al menos un conector de certificado tiene un error. Si necesita este conector para proporcionar certificados a dispositivos de Escritorio administrado de Microsoft, debe resolver el error. <br><br> Para obtener más información, vea [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md). |
| Advertencia | Tiene al menos un conector de certificado y no se notifican errores. Sin embargo, para preparar la implementación, es posible que deba crear un perfil para reutilizar el conector para dispositivos de Escritorio administrado de Microsoft. <br><br> Para obtener más información, vea [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md). |

### <a name="company-portal"></a>Portal de empresa

Microsoft Managed Desktop requiere que los administradores de TI instalen Portal de empresa de Intune para sus usuarios con dispositivos de Escritorio administrado de Microsoft.

| Resultado  | Significado |
| ----- | ----- |
| No preparado | No tiene instalado Portal de empresa para los usuarios. Compra Portal de empresa y fuerza una sincronización entre Intune y Microsoft Store para Empresas. <br><br> Para obtener más información, [consulta Instalar Portal de empresa de Intune dispositivos](../get-started/company-portal.md).

### <a name="conditional-access-policies"></a>Directivas de acceso condicional

Las directivas de acceso condicional no pueden impedir que Microsoft Managed Desktop administre su Azure AD (inquilino) en Intune y Azure AD.

| Resultado  | Significado |
| ----- | ----- |
| No preparado | Tiene al menos una directiva de acceso condicional dirigida a todos los usuarios. <br><br> Durante la inscripción, excluiremos las cuentas de servicio de Escritorio administrado de Microsoft de las directivas de acceso condicional relevantes y aplicaremos nuevas directivas de acceso condicional para restringir el acceso a estas cuentas. <br><br> Después de la inscripción, puede revisar la directiva de acceso condicional de Microsoft Managed Desktop en Microsoft Endpoint Manager. Para obtener más información sobre estas cuentas de servicio, vea [Procedimientos operativos estándar](../service-description/operations-and-monitoring.md#standard-operating-procedures). |
| Advertencia | Tiene directivas de acceso condicional que podrían impedir que Microsoft Managed Desktop administrara el servicio de Escritorio administrado de Microsoft. <br><br> Durante la inscripción, excluiremos las cuentas de servicio de Escritorio administrado de Microsoft de las directivas de acceso condicional relevantes y aplicaremos nuevas directivas de acceso condicional para restringir el acceso a estas cuentas. <br><br> Para obtener más información acerca de estas cuentas de servicio, vea [Procedimientos operativos estándar](../service-description/operations-and-monitoring.md#standard-operating-procedures). |
| Error | El rol administrador de Intune no tiene permisos suficientes para esta comprobación. También necesitará tener asignados estos Azure AD roles para ejecutar esta comprobación: <ul><li>Lector de seguridad</li><li>Administrador de seguridad</li><li>Administrador de acceso condicional</li><li>Lector global</li><li>Administrador de dispositivos</li></ul>
### <a name="device-compliance-policies"></a>Directivas de cumplimiento de dispositivos

Las directivas de cumplimiento de dispositivos de Intune en Azure AD organización podrían afectar a los dispositivos de Escritorio administrado de Microsoft.

| Resultado  | Significado |
| ----- | ----- |
| Advertencia | Tiene al menos una directiva de cumplimiento que aplica a todos los usuarios. Microsoft Managed Desktop también incluye directivas de cumplimiento que se aplicarán a los dispositivos de Escritorio administrado de Microsoft. Revise todas las directivas de cumplimiento creadas por su organización que se aplican a los dispositivos de Escritorio administrado de Microsoft para asegurarse de que no haya conflictos. <br><br> Para obtener más información, vea [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy). |

### <a name="device-configuration-profiles"></a>Perfiles de configuración de dispositivos

Los perfiles de configuración de dispositivos de Intune Azure AD organización no pueden dirigirse a ningún dispositivo o usuario de Microsoft Manage Desktop.

| Resultado  | Significado |
| ----- | ----- |
| No preparado | Tiene al menos un perfil de configuración que se aplica a todos los usuarios, todos los dispositivos o ambos. Restablezca el perfil para que se aplique a un grupo de Azure AD específico que no incluya ningún dispositivo de Escritorio administrado de Microsoft. <br><br> Para obtener más información, vea [Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure). |
| Advertencia | Asegúrese de que las directivas de configuración que tenga no incluyan ningún dispositivo o usuario de Escritorio administrado de Microsoft. <br><br> Para obtener más información, vea [Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure). |

### <a name="device-type-restrictions"></a>Restricciones de tipo de dispositivo

Los dispositivos de Escritorio administrado de Microsoft deben tener permiso para inscribirse en Intune.

| Resultado  | Significado |
| ----- | ----- |
| No preparado | Actualmente tiene al menos una directiva de restricción de inscripción configurada para impedir Windows dispositivos de inscripción en Intune. <br><br> Siga los pasos descritos en [Establecer restricciones](/mem/intune/enrollment/enrollment-restrictions-set) de inscripción para cada directiva de restricción de inscripción dirigida a los usuarios de Escritorio administrado de Microsoft y cambie la configuración **de Windows (MDM)** a **Permitir**. Sin embargo, puedes establecer cualquier dispositivo **de** **Windows (MDM)** de propiedad personal en **Bloquear**. |

### <a name="enrollment-status-page"></a>Página de estado de inscripción

Actualmente tiene habilitada la página de estado de inscripción (ESP). Si desea participar en la vista previa pública de Escritorio administrado de Microsoft de esta característica, puede omitir este elemento. Para obtener más información, consulte [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).

| Resultado  | Significado |
| ----- | ----- |
| No preparado | Tienes el perfil predeterminado de ESP establecido en **Mostrar el progreso de configuración de aplicaciones y perfiles**. <br><br> Deshabilite esta configuración o asegúrese de que las asignaciones a cualquier grupo Azure AD no incluyan dispositivos de Escritorio administrado de Microsoft siguiendo los pasos descritos en Configurar la página [de estado de inscripción](/mem/intune/enrollment/windows-enrollment-status). |
| Advertencia | Asegúrate de que los perfiles que tienen la  configuración Mostrar aplicación y progreso de configuración de perfil no están asignados a ningún grupo de Azure AD que incluya dispositivos de Escritorio administrado de Microsoft. <br><br> Para obtener más información, vea [Configurar la página de estado de inscripción](/mem/intune/enrollment/windows-enrollment-status). |

### <a name="microsoft-store-for-business"></a>Microsoft Store para Empresas

Usamos Microsoft Store para Empresas e implementamos la aplicación Portal de empresa en Microsoft Managed Desktop. Este método permite a los usuarios instalar opcionalmente algunas aplicaciones, como Microsoft Project y Microsoft Visio (donde se permita).

| Resultado  | Significado |
| ----- | ----- |
| No preparado | Microsoft Store para Empresas no está habilitado o no está sincronizado con Intune. <br><br> Para obtener más información, consulta [How to manage volume purchased apps from the Microsoft Store para Empresas with Microsoft Intune](/mem/intune/apps/windows-store-for-business) and [Install Portal de empresa de Intune on devices](../get-started/company-portal.md). |

### <a name="multi-factor-authentication"></a>Autenticación multifactor

La autenticación multifactor no puede impedir que Microsoft Managed Desktop administre su organización de Azure AD (inquilino) en Intune y Azure AD.

| Resultado  | Significado |
| ----- | ----- |
| No preparado | Tiene algunas directivas de autenticación multifactor establecidas según sea **necesario** para las directivas de acceso condicional asignadas a todos los usuarios. <br><br> Durante la inscripción, excluiremos las cuentas de servicio de Escritorio administrado de Microsoft de las directivas de acceso condicional relevantes y aplicaremos nuevas directivas de acceso condicional para restringir el acceso a estas cuentas. <br><br> Para obtener más información acerca de estas cuentas de servicio, vea [Procedimientos operativos estándar](../service-description/operations-and-monitoring.md#standard-operating-procedures). |
| Advertencia | Tiene la autenticación multifactor necesaria en las directivas de acceso condicional que podrían impedir que Microsoft Managed Desktop administrara el servicio de Escritorio administrado de Microsoft. <br><br> Durante la inscripción, excluya bien las cuentas de servicio de Escritorio administrado de Microsoft de las directivas de acceso condicional relevantes y aplique nuevas directivas de acceso condicional para restringir el acceso a estas cuentas. Para obtener más información acerca de estas cuentas de servicio, vea [Procedimientos operativos estándar](../service-description/operations-and-monitoring.md#standard-operating-procedures). |
| Error | El rol administrador de Intune no tiene permisos suficientes para esta comprobación. También necesitará tener asignados estos Azure AD roles para ejecutar esta comprobación: <ul><li>Lector de seguridad</li><li>Administrador de seguridad</li><li>Administrador de acceso condicional</li><li>Lector global</li><li>Administrador de dispositivos</li></ul>

### <a name="powershell-scripts"></a>Scripts de PowerShell

Windows PowerShell los scripts no se pueden asignar de forma que se asigne a dispositivos de Escritorio administrado de Microsoft.

| Resultado  | Significado |
| ----- | ----- |
| Advertencia | Asegúrese de que Windows PowerShell scripts de su Azure AD no se dirige a ningún dispositivo o usuario de Microsoft Manage Desktop. No asigne un script de PowerShell para dirigirse a todos los usuarios, todos los dispositivos o ambos. Cambie la directiva para usar una asignación dirigida a un grupo de Azure AD específico que no incluya ningún dispositivo o usuario de Escritorio administrado de Microsoft. <br><br> Para obtener más información, vea [Use PowerShell scripts on Windows 10 devices in Intune](/mem/intune/apps/intune-management-extension). |

### <a name="region"></a>Región

Su región debe ser compatible con Microsoft Managed Desktop.

| Resultado  | Significado |
| ----- | ----- |
| No preparado | La región Azure AD organización no es compatible actualmente con Microsoft Managed Desktop. <br><br> Para obtener más información, consulte [Regiones e idiomas admitidos por Microsoft Managed Desktop](../service-description/regions-languages.md). |
| Advertencia | Uno o varios de los países donde se encuentra Azure AD organización no es compatible con Microsoft Managed Desktop. <br><br> Para obtener más información, consulte [Regiones e idiomas admitidos por Microsoft Managed Desktop](../service-description/regions-languages.md). |

### <a name="security-baselines"></a>Líneas base de seguridad

Las directivas de línea base de seguridad no deben dirigirse a ningún dispositivo de Escritorio administrado de Microsoft.

| Resultado  | Significado |
| ----- | ----- |
| No preparado | Tiene un perfil de línea base de seguridad dirigido a todos los usuarios, todos los dispositivos o ambos. Cambie la directiva para usar una asignación dirigida a un grupo de Azure AD específico que no incluya ningún dispositivo de Escritorio administrado de Microsoft. <br><br> Para obtener más información, consulta [Usar líneas base de seguridad para configurar Windows 10 dispositivos en Intune](/mem/intune/protect/security-baselines). Durante la inscripción, aplicamos una nueva línea base de seguridad a todos los dispositivos de Escritorio administrado de Microsoft. Después de la inscripción, puede revisar la directiva de línea base de seguridad de Escritorio administrado de Microsoft en el **área Directiva de** configuración de Microsoft Endpoint Manager. |
| Advertencia | Asegúrese de que las directivas de línea base de seguridad que haya excluido los dispositivos de Escritorio administrado de Microsoft. Para obtener más información, consulta [Usar líneas base de seguridad para configurar Windows 10 dispositivos en Intune](/mem/intune/protect/security-baselines). <br><br> Durante la inscripción, aplicamos una nueva línea base de seguridad a todos los dispositivos de Escritorio administrado de Microsoft. **Dispositivos modernos del** lugar de trabajo: Azure AD grupo es un grupo dinámico que creamos al inscribirse en Microsoft Managed Desktop. Tendrás que volver para excluir este grupo después de la inscripción. |

### <a name="unlicensed-admins"></a>Administradores sin licencia

Esta configuración debe habilitarse para evitar un error de "falta de permisos" al interactuar con su Azure AD organización.

| Resultado  | Significado |
| ----- | ----- |
| No preparado | **Permitir el acceso a administradores sin** licencia debe estar habilitado. Para obtener más información, vea [Prerequisites for guest accounts](/microsoft-365/managed-desktop/get-ready/guest-accounts). |

### <a name="windows-apps"></a>Windows aplicaciones

Revisa las aplicaciones que quieres que tengan los usuarios de Escritorio administrado de Microsoft.

| Resultado  | Significado |
| ----- | ----- |
| Advertencia | Debes preparar un inventario de las aplicaciones que quieres que tengan los usuarios de Escritorio administrado de Microsoft. Dado que Intune debe implementar estas aplicaciones, evalúa volver a usar las aplicaciones existentes de Intune. Considera usar Portal de empresa (consulta [Instalar Portal de empresa de Intune en](../get-started/company-portal.md) dispositivos y Página de estado de inscripción (ESP) para distribuir aplicaciones a los usuarios. <br><br> Para obtener más información, consulta [Aplicaciones de Escritorio](apps.md) administrado de Microsoft y Experiencia de primera ejecución [con Autopilot y la página Estado de inscripción](../get-started/esp-first-run.md). <br><br> Puede solicitar al representante de la cuenta microsoft una consulta en Microsoft Endpoint Configuration Manager para identificar aquellas aplicaciones que estén listas para migrar a Intune o necesiten ajustes. |

### <a name="windows-hello-for-business"></a>Windows Hello para empresas

Microsoft Managed Desktop requiere que Windows Hello para empresas esté habilitada.

| Resultado  | Significado |
| ----- | ----- |
| Advertencia | Windows Hello para empresas está deshabilitado o no está configurado. Para habilitarla, siga los pasos descritos en [Crear una Windows Hello directiva para empresas](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy). |

### <a name="windows-10-update-rings"></a>Windows 10 anillos de actualización

La directiva de "Windows 10 de actualización" en Intune no debe dirigirse a ningún dispositivo de Escritorio administrado de Microsoft.

| Resultado  | Significado |
| ----- | ----- |
| No preparado | Tiene una directiva de "anillo de actualización" dirigida a todos los dispositivos, a todos los usuarios o a ambos. Cambie la directiva para usar una asignación dirigida a un grupo de Azure AD específico que no incluya ningún dispositivo de Escritorio administrado de Microsoft. <br><br> Para obtener más información, consulte [Manage Windows 10 software updates in Intune](/mem/intune/protect/windows-update-for-business-configure). |
| Advertencia | Asegúrese de que las directivas de anillo de actualización que haya excluido los dispositivos modernos de **workplace: todos** los Azure AD grupo. Si ha asignado Azure AD grupos de usuarios Azure AD estas directivas, asegúrese de que las directivas de anillo de actualización también han excluido el grupo **Modern Workplace:** Todos Azure AD al que agregue los usuarios de Escritorio administrado de Microsoft (o un grupo equivalente). <br><br> Para obtener más información, consulte [Manage Windows 10 software updates in Intune](/mem/intune/protect/windows-update-for-business-configure). Dispositivos **modernos del lugar** de trabajo : todos y lugares de trabajo modernos **:** todos los grupos Azure AD son grupos que creamos al inscribirse en Microsoft Managed Desktop. Tendrás que volver para excluir este grupo después de la inscripción. |

## <a name="azure-active-directory-settings"></a>Azure Active Directory configuración

Puede obtener acceso a Azure Active Directory configuración en [Azure Portal](https://portal.azure.com).

### <a name="intune-enrollment"></a>Con una inscripción de Intune

Windows 10 dispositivos de Azure AD organización deben poder inscribirse automáticamente en Intune.

| Resultado  | Significado |
| ----- | ----- |
| Advertencia | Asegúrate de que **el ámbito de usuario mdm** esté establecido en **Algunos** o **todos**, no **en Ninguno**. <br><br> Si elige **Some**, vuelva después de la inscripción y seleccione el grupo **Modern Workplace - All** Azure AD para **Grupos** o un grupo equivalente destinado a todos los usuarios de Escritorio administrado de Microsoft. <br><br> Para obtener más información, consulta [Configurar la inscripción para Windows dispositivos mediante Microsoft Intune](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment). |

### <a name="ad-hoc-subscriptions"></a>Suscripciones ad hoc

Indica cómo comprobar una configuración que, si se establece en "false", puede impedir que Enterprise estado móvil funcione correctamente.

| Resultado  | Significado |
| ----- | ----- |
| Advertencia | Asegúrese de **que AllowAdHocSubscriptions** está establecido en **True**. De lo contrario, Enterprise podría no funcionar la itinerancia de estado. <br><br> Para obtener más información, [vea Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings). |

### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

Enterprise debe habilitarse la itinerancia de estado.

| Resultado  | Significado |
| ----- | ----- |
| Advertencia | Asegúrese de que Enterprise itinerancia de estado está habilitada para **todos** o para **grupos seleccionados**. <br><br> Para obtener más información, [vea Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable). |

### <a name="guest-invitation-settings"></a>Configuración de invitación de invitado

Microsoft Managed Desktop recomienda ajustar la configuración de invitación de invitado, ya que la configuración predeterminada permite que todos los usuarios e invitados del directorio inviten invitados.

| Resultado  | Significado |
| ----- | ----- |
| Advertencia | **Los usuarios miembros y los usuarios asignados a roles de administrador específicos** pueden invitar a invitados, incluidos los invitados con permisos de miembro. <br><br> Para obtener más información, vea [Prerequisites for guest accounts](/microsoft-365/managed-desktop/get-ready/guest-accounts). |

### <a name="guest-user-access"></a>Acceso de usuario invitado

Microsoft Managed Desktop recomienda ajustar el acceso de invitado, ya que la configuración predeterminada permite que todos los invitados del directorio tengan el mismo acceso que los miembros.

| Resultado  | Significado |
| ----- | ----- |
| Advertencia | **Los usuarios invitados tienen acceso limitado a las propiedades y las pertenencias a** objetos de directorio deben estar habilitadas. <br><br> Para obtener más información, vea [Prerequisites for guest accounts](/microsoft-365/managed-desktop/get-ready/guest-accounts). |

### <a name="licenses"></a>Licencias

Se necesitan muchas licencias para usar Microsoft Managed Desktop.

| Resultado  | Significado |
| ----- | ----- |
| No listo | No tiene todas las licencias que necesita para usar Microsoft Managed Desktop. <br><br> Para obtener más información, vea [Tecnologías de Escritorio administrado de Microsoft](../intro/technologies.md) y [Más información sobre las licencias](prerequisites.md#more-about-licenses). |

### <a name="microsoft-managed-desktop-service-accounts"></a>Cuentas de servicio de Escritorio administrado de Microsoft

Algunos nombres de cuenta podrían estar en conflicto con los nombres de cuenta creados por Microsoft Managed Desktop para administrar el servicio de Escritorio administrado de Microsoft.

| Resultado  | Significado |
| ----- | ----- |
| No preparado | Tiene al menos un nombre de cuenta que entra en conflicto con los nombres de cuenta creados por Microsoft Managed Desktop. Trabaje con el representante de la cuenta microsoft para excluir estos nombres de cuenta. No enumeramos públicamente los nombres de cuenta para minimizar el riesgo de seguridad.

### <a name="security-administrator-roles"></a>Roles de administrador de seguridad

Los usuarios con determinados roles de seguridad deben tener asignados esos roles en Microsoft Defender para endpoint.

| Resultado  | Significado |
| ----- | ----- |
| Advertencia | Si tienes usuarios asignados a cualquiera de estos roles en tu Azure AD organización, asegúrate de que también tengan estos roles asignados en Microsoft Defender para endpoint. De lo contrario, los administradores con estos roles no podrán acceder al portal de administración. <ul><li>Operador de seguridad</li><li>Lector global</li></ul> <br> Para obtener más información, vea [Create and manage roles for role-based access control](/windows/security/threat-protection/microsoft-defender-atp/user-roles).

### <a name="security-default"></a>Valor predeterminado de seguridad

Los valores predeterminados de seguridad Azure Active Directory impedirán que Microsoft Managed Desktop gestione los dispositivos.

| Resultado  | Significado |
| ----- | ----- |
| No preparado | Tiene activados los valores predeterminados de seguridad. Desactiva los valores predeterminados de seguridad y configura las directivas de acceso condicional. <br><br> Para obtener más información, vea [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common). |

### <a name="self-service-password-reset"></a>Restablecimiento de contraseñas de autoservicio

El restablecimiento de contraseñas de autoservicio (SSPR) se puede habilitar para todos los usuarios de Escritorio administrado de Microsoft, excepto las cuentas de servicio de Escritorio administrado de Microsoft. <br><br> Para obtener más información, vea Tutorial: Permitir que los usuarios desbloqueen su cuenta o restablezcan contraseñas [Azure Active Directory restablecimiento de contraseñas de autoservicio](/azure/active-directory/authentication/tutorial-enable-sspr).

| Resultado  | Significado |
| ----- | ----- |
| Advertencia | Asegúrese de que la configuración de SSPR **Selected** incluye usuarios de Escritorio administrado de Microsoft, pero excluye las cuentas de servicio de Escritorio administrado de Microsoft. Las cuentas de servicio de Escritorio administrado de Microsoft no pueden funcionar como se esperaba cuando SSPR está habilitado. |

### <a name="standard-user-role"></a>Rol de usuario estándar

Aparte de los usuarios que tienen asignados roles de administrador global y administrador de dispositivos Azure Active Directory, los usuarios de Escritorio administrado de Microsoft serán usuarios estándar sin privilegios de administrador local. A todos los demás usuarios se les asignará un rol de usuario estándar cuando inicien su dispositivo de Escritorio administrado de Microsoft.

| Resultado  | Significado |
| ----- | ----- |
| Advertencia | Los usuarios de Escritorio administrado de Microsoft no tendrán privilegios de administrador local en sus dispositivos de Escritorio administrado de Microsoft después de inscribirse. |

## <a name="microsoft-365-apps-for-enterprise"></a>Aplicaciones de Microsoft 365 para empresas

### <a name="onedrive"></a>OneDrive

La **configuración Permitir la sincronización solo en equipos unidos** a dominios específicos entra en conflicto con El escritorio administrado de Microsoft. Puede obtener acceso a OneDrive configuración en el centro OneDrive [administración](https://admin.onedrive.com).

| Resultado  | Significado |
| ----- | ----- |
| Advertencia | Está usando la configuración **Permitir la sincronización solo en equipos unidos a dominios específicos** . Esta configuración no funcionará con Microsoft Managed Desktop. Deshabilite esta configuración. En su lugar, configure OneDrive para usar una directiva de acceso condicional. <br><br> Para obtener más información, vea [Plan a Conditional Access deployment](/azure/active-directory/conditional-access/plan-conditional-access) for help. |
