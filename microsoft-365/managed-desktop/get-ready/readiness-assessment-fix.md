---
title: Solucionar los problemas detectados por la herramienta de evaluación de la preparación
description: Acciones detalladas que se deben realizar para cada problema que encuentre la herramienta
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 5a22996ce9e39dc16191ddddc6aa9393de557bbc
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579415"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>Solucionar los problemas detectados por la herramienta de evaluación de la preparación

Para cada comprobación, la herramienta mostrará uno de los cuatro resultados posibles:


|Resultado  |Significado  |
|---------|---------|
|Listo     | No se requiere ninguna acción antes de completar la inscripción.        |
|Advertencia    | Siga los pasos de la herramienta o de este artículo para obtener la mejor experiencia con la inscripción y para los usuarios. Puedes *completar* la inscripción, pero debes solucionar estos problemas antes de implementar el primer dispositivo.        |
|No preparado | *La inscripción producirá un error si no se solucionan estos problemas.* Siga los pasos de la herramienta o de este artículo para resolverlos.        |
|Error | El rol de Azure Active Directory (AD) que está usando no tiene permisos suficientes para ejecutar esta comprobación. |

> [!NOTE]
> Los resultados notificados por esta herramienta reflejan el estado de la configuración solo en el momento específico en el que la ejecutó. Si más adelante realiza cambios en las directivas de Microsoft Intune, Azure Active Directory o Microsoft 365, los elementos que estaban "Listos" pueden convertirse en "No listos". Para evitar problemas con las operaciones de Escritorio administrado de Microsoft, compruebe la configuración específica descrita en este artículo antes de cambiar las directivas.

## <a name="microsoft-intune-settings"></a>Configuración de Microsoft Intune

Puede acceder a la configuración de Intune en el Centro de administración de Microsoft Endpoint [Manager.](https://endpoint.microsoft.com)

### <a name="autopilot-deployment-profile"></a>Perfil de implementación de Autopilot

No debe tener perfiles de Autopilot existentes destinados a grupos dinámicos o asignados con dispositivos de Escritorio administrado de Microsoft. Microsoft Managed Desktop usa Autopilot para aprovisionar nuevos dispositivos.

**No preparado**

Tienes un perfil de Autopilot que está asignado a todos los dispositivos. Para ver los pasos, consulta [Inscribir dispositivos Windows en Intune mediante Windows Autopilot](/mem/autopilot/enrollment-autopilot). Después de la inscripción de Microsoft Managed Desktop, establece la directiva de Autopilot para excluir el grupo **Modern Workplace Devices -All** Azure AD.

**Advertencia**

Asegúrese de que los perfiles de Autopilot están destinados a un grupo de Azure AD dinámico o asignado que no incluya dispositivos de Escritorio administrado de Microsoft. Para ver los pasos, consulta [Inscribir dispositivos Windows en Intune mediante Windows Autopilot](/mem/autopilot/enrollment-autopilot). Después de la inscripción de Microsoft Managed Desktop, establece los perfiles de Autopilot para excluir el **grupo Modern Workplace Devices -All** Azure AD.


### <a name="certificate-connectors"></a>Conectores de certificado

Si tiene algún conector de certificado que usarán los dispositivos que desea inscribir en Microsoft Managed Desktop, los conectores no deben tener errores. Solo se aplicará uno de los siguientes avisos a su situación, así que compróquelos cuidadosamente.

**Advertencia**

No hay conectores de certificado presentes. Es posible que no necesite ningún conector, pero debe evaluar si es posible que necesite algunos para la conectividad de red en los dispositivos de Escritorio administrado de Microsoft. Para obtener más información, vea [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).

**Advertencia**

Al menos un conector de certificado tiene un error. Si necesita este conector para proporcionar certificados a dispositivos de Escritorio administrado de Microsoft, debe resolver el error. Para obtener más información, vea [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).


**Advertencia**

Tiene al menos un conector de certificado y no se notifican errores. Sin embargo, para preparar la implementación, es posible que deba crear un perfil para reutilizar el conector para dispositivos de Escritorio administrado de Microsoft. Para obtener más información, vea [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).


### <a name="conditional-access-policies"></a>Directivas de acceso condicional

Las directivas de acceso condicional no deben impedir que Microsoft Managed Desktop administre su organización de Azure AD (inquilino) en Intune y Azure AD.

**No preparado**

Tiene al menos una directiva de acceso condicional dirigida a todos los usuarios. Durante la inscripción, excluiremos las cuentas de servicio de Escritorio administrado de Microsoft de las directivas de acceso condicional relevantes y aplicaremos nuevas directivas de acceso condicional para restringir el acceso a estas cuentas. Después de la inscripción, puede revisar la directiva de acceso condicional de Microsoft Managed Desktop en Microsoft Endpoint Manager. Para obtener más información sobre estas cuentas de servicio, [vea Procedimientos operativos estándar](../service-description/operations-and-monitoring.md#standard-operating-procedures).

**Advertencia**

Tiene directivas de acceso condicional que podrían impedir que Microsoft Managed Desktop administrara el servicio de Escritorio administrado de Microsoft. Durante la inscripción, excluiremos las cuentas de servicio de Escritorio administrado de Microsoft de las directivas de acceso condicional relevantes y aplicaremos nuevas directivas de acceso condicional para restringir el acceso a estas cuentas. Para obtener más información sobre estas cuentas de servicio, [vea Procedimientos operativos estándar](../service-description/operations-and-monitoring.md#standard-operating-procedures).

**Error**

El rol administrador de Intune no tiene permisos suficientes para esta comprobación. También necesitará cualquiera de estos roles de Azure AD asignados para ejecutar esta comprobación:

- Lector de seguridad
- Administrador de seguridad
- Administrador de acceso condicional
- Lector global
- Administrador de dispositivos


### <a name="device-compliance-policies"></a>Directivas de cumplimiento de dispositivos

Las directivas de cumplimiento de dispositivos de Intune en la organización de Azure AD pueden afectar a los dispositivos de Escritorio administrado de Microsoft.

**No preparado**

Tiene al menos una directiva de cumplimiento dirigida a todos los usuarios. Microsoft Managed Desktop incluye directivas de cumplimiento destinadas a los dispositivos de Escritorio administrado de Microsoft.  Cambie la directiva para dirigirse a un grupo específico de Azure AD que no incluya ningún dispositivo o usuario de Escritorio administrado de Microsoft. Para ver los pasos, [consulte Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).

**Advertencia**

Asegúrese de que las directivas de cumplimiento que tenga no están dirigidas a usuarios de Escritorio administrado de Microsoft. Para ver los pasos, [consulte Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).



### <a name="device-configuration-profiles"></a>Perfiles de configuración de dispositivos

Los perfiles de configuración de dispositivos de Intune en la organización de Azure AD no deben dirigirse a ningún dispositivo o usuario de Microsoft Manage Desktop.

**No preparado**

Tiene al menos un perfil de configuración dirigido a todos los usuarios, todos los dispositivos o ambos. Restablezca el perfil para dirigirse a un grupo específico de Azure AD que no incluya ningún dispositivo de Escritorio administrado de Microsoft. Para ver los pasos, [consulta Crear un perfil con configuración personalizada en Microsoft Intune](/mem/intune/configuration/custom-settings-configure).

**Advertencia**

Asegúrese de que las directivas de configuración que tenga no incluyan ningún dispositivo o usuario de Escritorio administrado de Microsoft. Para ver los pasos, [consulta Crear un perfil con configuración personalizada en Microsoft Intune](/mem/intune/configuration/custom-settings-configure).



### <a name="device-type-restrictions"></a>Restricciones de tipo de dispositivo

Los dispositivos de Escritorio administrado de Microsoft deben tener permiso para inscribirse en Intune.

**No preparado**

Actualmente tiene al menos una directiva de restricción de inscripción configurada para impedir que los dispositivos Windows se inscripción en Intune. Siga los pasos descritos en [Establecer restricciones](/mem/intune/enrollment/enrollment-restrictions-set) de inscripción para cada directiva de restricción de inscripción dirigida a los usuarios de Escritorio administrado de Microsoft y cambie la configuración de **Windows (MDM)** a **Permitir**. Sin embargo, puedes establecer cualquier dispositivo de **Windows (MDM)** de propiedad **personal** en **Bloquear**. 


### <a name="enrollment-status-page"></a>Página estado de inscripción

Actualmente tiene habilitada la página de estado de inscripción (ESP). Si desea participar en la vista previa pública de Escritorio administrado de Microsoft de esta característica, puede omitir este elemento. Para obtener más información, vea [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).

**No preparado**

Tienes el perfil predeterminado de ESP establecido en Mostrar el progreso de configuración de aplicaciones **y perfiles.** Deshabilite esta configuración o asegúrese de que las asignaciones a cualquier grupo de Azure AD no incluyan dispositivos de Escritorio administrado de Microsoft siguiendo los pasos descritos en Configurar la página [estado de inscripción](/mem/intune/enrollment/windows-enrollment-status).

**Advertencia**

Asegúrese de que los perfiles que tienen la configuración Mostrar aplicación y progreso de configuración de perfiles no estén asignados a ningún grupo de Azure AD que incluya dispositivos de Escritorio administrado de Microsoft.  Para obtener más información, vea [Set up the Enrollment Status Page](/mem/intune/enrollment/windows-enrollment-status).

### <a name="microsoft-store-for-business"></a>Microsoft Store para Empresas

Usamos Microsoft Store para empresas e implementamos la aplicación Portal de empresa en Microsoft Managed Desktop para permitir que los usuarios instalen opcionalmente algunas aplicaciones, como Microsoft Project y Microsoft Visio (cuando se permita).

**No preparado**

Microsoft Store para empresas no está habilitada o no está sincronizada con Intune. Para obtener más información, vea [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](/mem/intune/apps/windows-store-for-business) e Install Intune Company Portal on [devices](../get-started/company-portal.md).

### <a name="multifactor-authentication"></a>Autenticación multifactor

La autenticación multifactor no debe impedir que Microsoft Managed Desktop administre su organización de Azure AD (inquilino) en Intune y Azure AD.


**No preparado**

Tiene algunas directivas de autenticación multifactor configuradas según **sea necesario** para las directivas de acceso condicional asignadas a todos los usuarios. Durante la inscripción, excluiremos las cuentas de servicio de Escritorio administrado de Microsoft de las directivas de acceso condicional relevantes y aplicaremos nuevas directivas de acceso condicional para restringir el acceso a estas cuentas. Para obtener más información sobre estas cuentas de servicio, [vea Procedimientos operativos estándar](../service-description/operations-and-monitoring.md#standard-operating-procedures).

**Advertencia**

Tiene la autenticación multifactor necesaria en las directivas de acceso condicional que podrían impedir que Microsoft Managed Desktop administrara el servicio de Escritorio administrado de Microsoft. Durante la inscripción, excluiremos las cuentas de servicio de Escritorio administrado de Microsoft de las directivas de acceso condicional relevantes y aplicaremos nuevas directivas de acceso condicional para restringir el acceso a estas cuentas. Para obtener más información sobre estas cuentas de servicio, [vea Procedimientos operativos estándar](../service-description/operations-and-monitoring.md#standard-operating-procedures).

**Error**

El rol administrador de Intune no tiene permisos suficientes para esta comprobación. También necesitará cualquiera de estos roles de Azure AD asignados para ejecutar esta comprobación:

- Lector de seguridad
- Administrador de seguridad
- Administrador de acceso condicional
- Lector global
- Administrador de dispositivos


### <a name="powershell-scripts"></a>Scripts de PowerShell

Windows PowerShell no se pueden asignar scripts de una forma que se dirigiría a dispositivos de Escritorio administrado de Microsoft.  

**Advertencia**

Asegúrese de que Windows PowerShell scripts de la organización de Azure AD no se dirige a ningún dispositivo o usuario de Microsoft Manage Desktop. No asigne un script de PowerShell para dirigirse a todos los usuarios, todos los dispositivos o ambos. Cambie la directiva para usar una asignación dirigida a un grupo específico de Azure AD que no incluya ningún dispositivo o usuario de Escritorio administrado de Microsoft. Para obtener más información, vea [Use PowerShell scripts on Windows 10 devices in Intune](/mem/intune/apps/intune-management-extension).

### <a name="region"></a>Región

Su región debe ser compatible con Microsoft Managed Desktop.

**No preparado**

La región de la organización de Azure AD no es compatible actualmente con Microsoft Managed Desktop. Para obtener más información, vea Regiones e [idiomas admitidos](../service-description/regions-languages.md)por Microsoft Managed Desktop.

**Advertencia**

Uno o varios de los países donde se encuentra la organización de Azure AD no son compatibles con Microsoft Managed Desktop. Para obtener más información, vea Regiones e [idiomas admitidos](../service-description/regions-languages.md)por Microsoft Managed Desktop.


### <a name="security-baselines"></a>Líneas base de seguridad

Las directivas de línea base de seguridad no deben dirigirse a ningún dispositivo de Escritorio administrado de Microsoft.

**No preparado**

Tiene un perfil de línea base de seguridad dirigido a todos los usuarios, todos los dispositivos o ambos. Cambie la directiva para usar una asignación dirigida a un grupo específico de Azure AD que no incluya ningún dispositivo de Escritorio administrado de Microsoft. Para ver los pasos, consulta [Usar líneas base de seguridad para configurar dispositivos Windows 10 en Intune.](/mem/intune/protect/security-baselines) Durante la inscripción, aplicamos una nueva línea base de seguridad a todos los dispositivos de Escritorio administrado de Microsoft. Después de la inscripción, puede revisar la directiva de línea base de seguridad de Escritorio administrado de Microsoft en el **área directiva de** configuración de Microsoft Endpoint Manager.

**Advertencia**

Asegúrese de que las directivas de línea base de seguridad que haya excluido los dispositivos de Escritorio administrado de Microsoft. Para ver los pasos, consulta [Usar líneas base de seguridad para configurar dispositivos Windows 10 en Intune.](/mem/intune/protect/security-baselines) Durante la inscripción, aplicamos una nueva línea base de seguridad a todos los dispositivos de Escritorio administrado de Microsoft. El **grupo Modern Workplace Devices -All** Azure AD es un grupo dinámico que creamos al inscribirse en Microsoft Managed Desktop, por lo que tendrás que volver para excluir este grupo después de la inscripción. 


### <a name="windows-apps"></a>Aplicaciones de Windows

Revisa las aplicaciones que quieres que tengan los usuarios de Escritorio administrado de Microsoft.

**Advertencia**

Debes preparar un inventario de las aplicaciones que quieres que tengan los usuarios de Escritorio administrado de Microsoft. Dado que Intune debe implementar estas aplicaciones, evalúa volver a usar las aplicaciones existentes de Intune. Considera el uso del Portal de empresa (consulta [Instalar Intune Company Portal en dispositivos](../get-started/company-portal.md) y Página de estado de inscripción (ESP) para distribuir aplicaciones a los usuarios. Para obtener más información, vea [Aplicaciones de Escritorio](apps.md) administrado de Microsoft y Experiencia de primera ejecución con [Autopilot y la página Estado de inscripción.](../get-started/esp-first-run.md)

Puede solicitar al representante de la cuenta de Microsoft una consulta en Microsoft Endpoint Configuration Manager para identificar aquellas aplicaciones que estén listas para migrar a Intune o necesiten ajustes.


### <a name="windows-hello-for-business"></a>Windows Hello para empresas

Microsoft Managed Desktop requiere que Windows Hello para empresas esté habilitado.

**No preparado**

Windows Hello para empresas está deshabilitado. Para habilitarla, siga los pasos descritos [en Crear una directiva de Windows Hello para empresas](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**Advertencia**

Windows Hello para empresas no está configurado. Para habilitarla, siga los pasos descritos [en Crear una directiva de Windows Hello para empresas](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).


### <a name="windows-10-update-rings"></a>Anillos de actualización de Windows 10

La directiva "Anillo de actualización de Windows 10" en Intune no debe dirigirse a ningún dispositivo de Escritorio administrado de Microsoft.

**No preparado**

Tiene una directiva de "anillo de actualización" dirigida a todos los dispositivos, a todos los usuarios o a ambos. Cambie la directiva para usar una asignación dirigida a un grupo específico de Azure AD que no incluya ningún dispositivo de Escritorio administrado de Microsoft. Para ver los pasos, consulta Administrar actualizaciones de software de [Windows 10 en Intune](/mem/intune/protect/windows-update-for-business-configure).

**Advertencia**

Asegúrese de que cualquier directiva de anillo de actualización que tenga excluya el grupo Dispositivos modernos del lugar de trabajo **-Todos los** grupos de Azure AD. Si ha asignado grupos de usuarios de Azure AD a estas directivas, asegúrese de que las directivas de anillo de actualización también han excluido el grupo **Modern Workplace -All** Azure AD al que agrega los usuarios de Escritorio administrado de Microsoft (o un grupo equivalente). Para ver los pasos, consulta Administrar actualizaciones de software de [Windows 10 en Intune](/mem/intune/protect/windows-update-for-business-configure). Los grupos Modern **Workplace Devices -All** y **Modern Workplace -All** Azure AD son grupos que creamos al inscribirse en Microsoft Managed Desktop, por lo que tendrás que volver a excluir este grupo después de la inscripción.


## <a name="azure-active-directory-settings"></a>Configuración de Azure Active Directory

Puede acceder a la configuración de Azure Active Directory en [Azure Portal.](https://portal.azure.com)

### <a name="intune-enrollment"></a>Inscripción en Intune

Los dispositivos Windows 10 de la organización de Azure AD deben poder inscribirse automáticamente en Intune.

**Advertencia**

Asegúrate de que **el ámbito de usuario MDM** esté establecido en **Algunos** o **Todos,** no **en Ninguno**. Si elige **Some**, vuelva después de la inscripción y  seleccione el grupo Modern **Workplace -All** Azure AD para grupos o un grupo equivalente destinado a todos los usuarios de Escritorio administrado de Microsoft.  Consulta [Configurar la inscripción para dispositivos Windows con Microsoft Intune](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment).


### <a name="ad-hoc-subscriptions"></a>Suscripciones ad hoc

Aconseja cómo comprobar una configuración que (si se establece en "false") podría impedir que la itinerancia de estado de empresa funcione correctamente.

**Advertencia**

Asegúrese de **que AllowAdHocSubscriptions** está establecido en **True**. De lo contrario, es posible que la itinerancia de estado de empresa no funcione. Para obtener más información, [vea Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

La itinerancia de estado de empresa debe estar habilitada.

**Advertencia**

Asegúrese de que enterprise state roaming está habilitado para **todos** o para **los grupos seleccionados.** Para obtener más información, vea [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).

### <a name="licenses"></a>Licencias

Se necesitan varias licencias para usar Microsoft Managed Desktop.

**No listo**

No tiene todas las licencias que necesita para usar Microsoft Managed Desktop. Para obtener más información, vea [Tecnologías de Escritorio administrado de Microsoft](../intro/technologies.md) y Más información sobre las [licencias.](prerequisites.md#more-about-licenses)


### <a name="microsoft-managed-desktop-service-accounts"></a>Cuentas de servicio de Escritorio administrado de Microsoft

Algunos nombres de cuenta podrían estar en conflicto con los nombres de cuenta creados por Microsoft Managed Desktop para administrar el servicio de Escritorio administrado de Microsoft.

**No preparado**

Tiene al menos un nombre de cuenta que entra en conflicto con los nombres de cuenta creados por Microsoft Managed Desktop. Trabaje con el representante de la cuenta microsoft para excluir estos nombres de cuenta. No enumeramos públicamente los nombres de cuenta para minimizar el riesgo de seguridad. 


### <a name="security-administrator-roles"></a>Roles de administrador de seguridad

Los usuarios con determinados roles de seguridad deben tener asignados esos roles en Microsoft Defender para endpoint.

**Advertencia**

Si tiene usuarios asignados a cualquiera de estos roles en su organización de Azure AD, asegúrese de que también tienen asignados estos roles en Microsoft Defender para endpoint. De lo contrario, los administradores con estos roles no podrán acceder al portal de administración.

- Operador de seguridad
- Lector global

Para obtener más información, vea [Create and manage roles for role-based access control](/windows/security/threat-protection/microsoft-defender-atp/user-roles).


### <a name="security-default"></a>Valor predeterminado de seguridad

Los valores predeterminados de seguridad en Azure Active Directory impedirán que Microsoft Managed Desktop gestione los dispositivos.

**No preparado**

Tiene activados los valores predeterminados de seguridad. Desactiva los valores predeterminados de seguridad y configura las directivas de acceso condicional. Para obtener más información, vea [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common).

### <a name="self-service-password-reset"></a>Restablecimiento de contraseñas de autoservicio

El restablecimiento de contraseñas de autoservicio (SSPR) se puede habilitar para todos los usuarios de Escritorio administrado de Microsoft, excepto las cuentas de servicio de Escritorio administrado de Microsoft. Para obtener más información, vea Tutorial: Permitir que los usuarios desbloqueen su cuenta o restablezcan contraseñas con [Azure Active Directory self-service password reset](/azure/active-directory/authentication/tutorial-enable-sspr).

**Advertencia**

Asegúrese de que la configuración de SSPR **Selected** incluye usuarios de Escritorio administrado de Microsoft, pero excluye las cuentas de servicio de Escritorio administrado de Microsoft. Las cuentas de servicio de Escritorio administrado de Microsoft no pueden funcionar como se esperaba cuando SSPR está habilitado.  


### <a name="standard-user-role"></a>Rol de usuario estándar

Aparte de los usuarios a los que se les asignan roles de administrador global y administrador de dispositivos de Azure AD, los usuarios de Escritorio administrado de Microsoft serán usuarios estándar sin privilegios de administrador local. A todos los demás usuarios se les asignará un rol de usuario estándar cuando inicien su dispositivo de Escritorio administrado de Microsoft.

**Advertencia**

Los usuarios de Escritorio administrado de Microsoft no tendrán privilegios de administrador local en sus dispositivos de Escritorio administrado de Microsoft después de inscribirse.

## <a name="microsoft-365-apps-for-enterprise"></a>Aplicaciones de Microsoft 365 para empresas

### <a name="onedrive"></a>OneDrive

La **configuración Permitir la sincronización solo en equipos unidos** a dominios específicos entra en conflicto con El escritorio administrado de Microsoft. Puede acceder a la configuración de OneDrive en el Centro de [administración de OneDrive.](https://admin.onedrive.com)

**Advertencia**

Está usando la configuración Permitir la sincronización solo en equipos **unidos a dominios específicos.** Esta configuración no funcionará con Microsoft Managed Desktop. Deshabilite esta configuración y, en su lugar, configure OneDrive para usar una directiva de acceso condicional. Consulte [Planear una implementación de acceso condicional](/azure/active-directory/conditional-access/plan-conditional-access) para obtener ayuda.