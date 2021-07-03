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
ms.openlocfilehash: 9d2f9a95b3d5d90b79122d55477284083ea8332e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286890"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>Solucionar los problemas detectados por la herramienta de evaluación de la preparación

Para cada comprobación, la herramienta mostrará uno de los cuatro resultados posibles:


|Resultado  |Significado  |
|---------|---------|
|Listo     | No se requiere ninguna acción antes de completar la inscripción.        |
|Advertencia    | Siga los pasos de la herramienta o de este artículo para obtener la mejor experiencia con la inscripción y para los usuarios. Puedes *completar* la inscripción, pero debes solucionar estos problemas antes de implementar el primer dispositivo.        |
|No preparado | *La inscripción producirá un error si no se solucionan estos problemas.* Siga los pasos de la herramienta o de este artículo para resolverlos.        |
|Error | El Azure Active Directory (AD) que está usando no tiene permisos suficientes para ejecutar esta comprobación. |

> [!NOTE]
> Los resultados notificados por esta herramienta reflejan el estado de la configuración solo en el momento específico en el que la ejecutó. Si más adelante realiza cambios en las directivas de Microsoft Intune, Azure Active Directory o Microsoft 365, los elementos que estaban "Listos" pueden convertirse en "No listos". Para evitar problemas con Escritorio administrado de Microsoft operaciones, compruebe la configuración específica descrita en este artículo antes de cambiar las directivas.

## <a name="microsoft-intune-settings"></a>Microsoft Intune configuración

Puede acceder a la configuración de Intune en el centro Microsoft Endpoint Manager [administración.](https://endpoint.microsoft.com)

### <a name="autopilot-deployment-profile"></a>Perfil de implementación de Autopilot

No debes tener ningún perfil de Autopilot existente destinado a grupos dinámicos o asignados con Escritorio administrado de Microsoft dispositivos. Escritorio administrado de Microsoft autopilot para aprovisionar nuevos dispositivos.

**No preparado**

Tienes un perfil de Autopilot que está asignado a todos los dispositivos. Para ver los pasos, [consulte Inscribir Windows dispositivos en Intune mediante Windows Autopilot](/mem/autopilot/enrollment-autopilot). Después Escritorio administrado de Microsoft inscripción, establece la directiva de Autopilot para excluir el grupo **Modern Workplace Devices -All** Azure AD.

**Advertencia**

Asegúrese de que los perfiles de Autopilot están dirigidos a un grupo de Azure AD dinámico o asignado que no incluye Escritorio administrado de Microsoft dispositivos. Para ver los pasos, [consulte Inscribir Windows dispositivos en Intune mediante Windows Autopilot](/mem/autopilot/enrollment-autopilot). Después Escritorio administrado de Microsoft inscripción, establece los perfiles de Autopilot para excluir el grupo **Modern Workplace Devices -All** Azure AD.


### <a name="certificate-connectors"></a>Conectores de certificado

Si tiene algún conector de certificado que usarán los dispositivos en los que desea inscribirse Escritorio administrado de Microsoft, los conectores no deben tener errores. Solo se aplicará uno de los siguientes avisos a su situación, así que compróquelos cuidadosamente.

**Advertencia**

No hay conectores de certificado presentes. Es posible que no necesite ningún conector, pero debe evaluar si es posible que necesite algunos para la conectividad de red en los dispositivos Escritorio administrado de Microsoft dispositivos. Para obtener más información, vea [Prepare certificates and network profiles for Escritorio administrado de Microsoft](certs-wifi-lan.md).

**Advertencia**

Al menos un conector de certificado tiene un error. Si necesita este conector para proporcionar certificados a Escritorio administrado de Microsoft dispositivos, debe resolver el error. Para obtener más información, vea [Prepare certificates and network profiles for Escritorio administrado de Microsoft](certs-wifi-lan.md).


**Advertencia**

Tiene al menos un conector de certificado y no se notifican errores. Sin embargo, para preparar la implementación, es posible que deba crear un perfil para volver a usar el conector para Escritorio administrado de Microsoft dispositivos. Para obtener más información, vea [Prepare certificates and network profiles for Escritorio administrado de Microsoft](certs-wifi-lan.md).

### <a name="company-portal"></a>Portal de empresa

Escritorio administrado de Microsoft requiere que los administradores de TI instalen Portal de empresa de Intune para sus usuarios con Escritorio administrado de Microsoft dispositivos. 

**No preparado**

No tiene instalado Portal de empresa para los usuarios. Compra Portal de empresa y fuerza una sincronización entre Intune y Microsoft Store para Empresas. Para obtener más información, vea [Install Portal de empresa de Intune on devices](../get-started/company-portal.md).


### <a name="conditional-access-policies"></a>Directivas de acceso condicional

Las directivas de acceso condicional no deben impedir Escritorio administrado de Microsoft administrar la organización de Azure AD (inquilino) en Intune y Azure AD.

**No preparado**

Tiene al menos una directiva de acceso condicional dirigida a todos los usuarios. Durante la inscripción, excluiremos las Escritorio administrado de Microsoft de servicio de las directivas de acceso condicional relevantes y aplicaremos nuevas directivas de acceso condicional para restringir el acceso a estas cuentas. Después de la inscripción, puede revisar la Escritorio administrado de Microsoft de acceso condicional en Microsoft Endpoint Manager. Para obtener más información sobre estas cuentas de servicio, [vea Procedimientos operativos estándar](../service-description/operations-and-monitoring.md#standard-operating-procedures).

**Advertencia**

Tiene directivas de acceso condicional que podrían impedir Escritorio administrado de Microsoft administrar el Escritorio administrado de Microsoft servicio. Durante la inscripción, excluiremos las Escritorio administrado de Microsoft de servicio de las directivas de acceso condicional relevantes y aplicaremos nuevas directivas de acceso condicional para restringir el acceso a estas cuentas. Para obtener más información sobre estas cuentas de servicio, [vea Procedimientos operativos estándar](../service-description/operations-and-monitoring.md#standard-operating-procedures).

**Error**

El rol administrador de Intune no tiene permisos suficientes para esta comprobación. También necesitará cualquiera de estos roles de Azure AD asignados para ejecutar esta comprobación:

- Lector de seguridad
- Administrador de seguridad
- Administrador de acceso condicional
- Lector global
- Administrador de dispositivos


### <a name="device-compliance-policies"></a>Directivas de cumplimiento de dispositivos

Las directivas de cumplimiento de dispositivos de Intune en la organización de Azure AD pueden afectar Escritorio administrado de Microsoft dispositivos.

**No preparado**

Tiene al menos una directiva de cumplimiento dirigida a todos los usuarios. Escritorio administrado de Microsoft incluye directivas de cumplimiento que se dirigirán a los Escritorio administrado de Microsoft dispositivos.  Cambie la directiva para dirigirse a un grupo específico de Azure AD que no incluya ningún Escritorio administrado de Microsoft o dispositivos. Para ver los pasos, [vea Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).

**Advertencia**

Asegúrese de que las directivas de cumplimiento que tenga no se Escritorio administrado de Microsoft usuarios. Para ver los pasos, [vea Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).



### <a name="device-configuration-profiles"></a>Perfiles de configuración de dispositivos

Los perfiles de configuración de dispositivos de Intune en la organización de Azure AD no deben dirigirse a ningún dispositivo o usuario de Microsoft Manage Desktop.

**No preparado**

Tiene al menos un perfil de configuración dirigido a todos los usuarios, todos los dispositivos o ambos. Restablezca el perfil para dirigirse a un grupo específico de Azure AD que no incluya ningún Escritorio administrado de Microsoft dispositivos. Para ver los pasos, [vea Crear un perfil con configuración personalizada en Microsoft Intune](/mem/intune/configuration/custom-settings-configure).

**Advertencia**

Asegúrese de que las directivas de configuración que tenga no incluyan ningún Escritorio administrado de Microsoft o usuarios. Para ver los pasos, [vea Crear un perfil con configuración personalizada en Microsoft Intune](/mem/intune/configuration/custom-settings-configure).



### <a name="device-type-restrictions"></a>Restricciones de tipo de dispositivo

Escritorio administrado de Microsoft dispositivos deben poder inscribirse en Intune.

**No preparado**

Actualmente tiene al menos una directiva de restricción de inscripción configurada para impedir Windows dispositivos de inscripción en Intune. Siga los pasos descritos en [Establecer restricciones](/mem/intune/enrollment/enrollment-restrictions-set) de inscripción para cada directiva de restricción de inscripción dirigida Escritorio administrado de Microsoft usuarios y cambie la configuración **de Windows (MDM)** a **Permitir**. Sin embargo, puedes establecer cualquier dispositivo de propiedad **personal** **Windows (MDM)** en **Bloquear**. 


### <a name="enrollment-status-page"></a>Página estado de inscripción

Actualmente tiene habilitada la página de estado de inscripción (ESP). Si desea participar en la vista previa Escritorio administrado de Microsoft pública de esta característica, puede omitir este elemento. Para obtener más información, vea [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).

**No preparado**

Tienes el perfil predeterminado de ESP establecido en Mostrar el progreso de configuración de aplicaciones **y perfiles.** Deshabilite esta configuración o asegúrese de que las asignaciones a cualquier grupo de Azure AD no incluyan Escritorio administrado de Microsoft dispositivos siguiendo los pasos descritos en Configurar la página [estado de inscripción](/mem/intune/enrollment/windows-enrollment-status).

**Advertencia**

Asegúrese de que los perfiles que tienen la configuración Mostrar aplicación y progreso de configuración de perfiles no estén asignados a ningún grupo de Azure AD que incluya Escritorio administrado de Microsoft dispositivos.  Para obtener más información, vea [Set up the Enrollment Status Page](/mem/intune/enrollment/windows-enrollment-status).

### <a name="microsoft-store-for-business"></a>Microsoft Store para Empresas

Usamos Microsoft Store para Empresas e implementamos la aplicación Portal de empresa en Escritorio administrado de Microsoft para permitir que los usuarios instalen opcionalmente algunas aplicaciones, como Microsoft Project y Microsoft Visio (donde se permita).

**No preparado**

Microsoft Store para Empresas no está habilitado o no está sincronizado con Intune. Para obtener más información, vea [How to manage volume purchased apps from the Microsoft Store para Empresas with Microsoft Intune](/mem/intune/apps/windows-store-for-business) and Install Portal de empresa de Intune on [devices](../get-started/company-portal.md).

### <a name="multifactor-authentication"></a>Autenticación multifactor

La autenticación multifactor no debe impedir Escritorio administrado de Microsoft administrar la organización de Azure AD (inquilino) en Intune y Azure AD.


**No preparado**

Tiene algunas directivas de autenticación multifactor configuradas según **sea necesario** para las directivas de acceso condicional asignadas a todos los usuarios. Durante la inscripción, excluiremos las Escritorio administrado de Microsoft de servicio de las directivas de acceso condicional relevantes y aplicaremos nuevas directivas de acceso condicional para restringir el acceso a estas cuentas. Para obtener más información sobre estas cuentas de servicio, [vea Procedimientos operativos estándar](../service-description/operations-and-monitoring.md#standard-operating-procedures).

**Advertencia**

Tiene la autenticación multifactor necesaria en las directivas de acceso condicional que podrían impedir Escritorio administrado de Microsoft administrar el servicio Escritorio administrado de Microsoft condicional. Durante la inscripción, excluiremos las Escritorio administrado de Microsoft de servicio de las directivas de acceso condicional relevantes y aplicaremos nuevas directivas de acceso condicional para restringir el acceso a estas cuentas. Para obtener más información sobre estas cuentas de servicio, [vea Procedimientos operativos estándar](../service-description/operations-and-monitoring.md#standard-operating-procedures).

**Error**

El rol administrador de Intune no tiene permisos suficientes para esta comprobación. También necesitará cualquiera de estos roles de Azure AD asignados para ejecutar esta comprobación:

- Lector de seguridad
- Administrador de seguridad
- Administrador de acceso condicional
- Lector global
- Administrador de dispositivos


### <a name="powershell-scripts"></a>Scripts de PowerShell

Windows PowerShell no se pueden asignar scripts de una forma que se dirigiría a Escritorio administrado de Microsoft dispositivos.  

**Advertencia**

Asegúrese de que Windows PowerShell scripts de la organización de Azure AD no se dirige a ningún dispositivo o usuario de Microsoft Manage Desktop. No asigne un script de PowerShell para dirigirse a todos los usuarios, todos los dispositivos o ambos. Cambie la directiva para usar una asignación dirigida a un grupo específico de Azure AD que no incluya ningún Escritorio administrado de Microsoft o usuarios. Para obtener más información, vea [Use PowerShell scripts on Windows 10 devices in Intune](/mem/intune/apps/intune-management-extension).

### <a name="region"></a>Región

La región debe ser compatible con Escritorio administrado de Microsoft.

**No preparado**

La región de la organización de Azure AD no es compatible actualmente con Escritorio administrado de Microsoft. Para obtener más información, [vea Escritorio administrado de Microsoft regiones e idiomas admitidos.](../service-description/regions-languages.md)

**Advertencia**

Uno o varios de los países donde se encuentra la organización de Azure AD no son compatibles con Escritorio administrado de Microsoft. Para obtener más información, [vea Escritorio administrado de Microsoft regiones e idiomas admitidos.](../service-description/regions-languages.md)


### <a name="security-baselines"></a>Líneas base de seguridad

Las directivas de línea base de seguridad no deben dirigirse a Escritorio administrado de Microsoft dispositivos.

**No preparado**

Tiene un perfil de línea base de seguridad dirigido a todos los usuarios, todos los dispositivos o ambos. Cambie la directiva para usar una asignación dirigida a un grupo específico de Azure AD que no incluya ningún Escritorio administrado de Microsoft dispositivos. Para ver los pasos, consulte [Usar líneas base de seguridad para configurar Windows 10 dispositivos en Intune](/mem/intune/protect/security-baselines). Durante la inscripción, aplicamos una nueva línea base de seguridad a todos Escritorio administrado de Microsoft dispositivos. Después de la inscripción, puede revisar la directiva de línea base Escritorio administrado de Microsoft seguridad en el **área directiva de** configuración de Microsoft Endpoint Manager.

**Advertencia**

Asegúrese de que las directivas de línea base de seguridad que haya excluido Escritorio administrado de Microsoft dispositivos. Para ver los pasos, consulte [Usar líneas base de seguridad para configurar Windows 10 dispositivos en Intune](/mem/intune/protect/security-baselines). Durante la inscripción, aplicamos una nueva línea base de seguridad a todos Escritorio administrado de Microsoft dispositivos. El **grupo Modern Workplace Devices -All** Azure AD es un grupo dinámico que creamos al inscribirse en Escritorio administrado de Microsoft, por lo que tendrás que volver para excluir este grupo después de la inscripción. 


### <a name="windows-apps"></a>Windows aplicaciones

Revisa las aplicaciones que quieres que Escritorio administrado de Microsoft usuarios tengan.

**Advertencia**

Debes preparar un inventario de las aplicaciones que quieres que tengan Escritorio administrado de Microsoft usuarios. Dado que Intune debe implementar estas aplicaciones, evalúa volver a usar las aplicaciones existentes de Intune. Considera usar Portal de empresa (consulta [Instalar Portal de empresa de Intune en](../get-started/company-portal.md) dispositivos y Página de estado de inscripción (ESP) para distribuir aplicaciones a los usuarios. Para obtener más información, [vea Aplicaciones en Escritorio administrado de Microsoft](apps.md) experiencia de primera ejecución con [Autopilot y la página Estado de inscripción.](../get-started/esp-first-run.md)

Puede solicitar al representante de la cuenta microsoft una consulta en Microsoft Endpoint Configuration Manager para identificar aquellas aplicaciones que estén listas para migrar a Intune o necesiten ajustes.


### <a name="windows-hello-for-business"></a>Windows Hello para empresas

Escritorio administrado de Microsoft requiere que Windows Hello para empresas esté habilitada.

**No preparado**

Windows Hello para empresas está deshabilitado. Para habilitarla, siga los pasos descritos en [Crear una directiva Windows Hello para empresas](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**Advertencia**

Windows Hello para empresas no está configurado. Para habilitarla, siga los pasos descritos en [Crear una Windows Hello directiva para empresas](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).


### <a name="windows-10-update-rings"></a>Windows 10 anillos de actualización

La directiva de "Windows 10 de actualización" en Intune no debe dirigirse a ningún Escritorio administrado de Microsoft dispositivos.

**No preparado**

Tiene una directiva de "anillo de actualización" dirigida a todos los dispositivos, a todos los usuarios o a ambos. Cambie la directiva para usar una asignación dirigida a un grupo específico de Azure AD que no incluya ningún dispositivo Escritorio administrado de Microsoft asignación. Para ver los pasos, [consulte Manage Windows 10 software updates in Intune](/mem/intune/protect/windows-update-for-business-configure).

**Advertencia**

Asegúrese de que cualquier directiva de anillo de actualización que tenga excluya el grupo Dispositivos modernos del lugar de trabajo **-Todos los** grupos de Azure AD. Si ha asignado grupos de usuarios de Azure AD a estas directivas, asegúrese de que las directivas de anillo de actualización también han excluido el grupo **Modern Workplace -All** Azure AD al que agrega los usuarios de Escritorio administrado de Microsoft (o un grupo equivalente). Para ver los pasos, [consulte Manage Windows 10 software updates in Intune](/mem/intune/protect/windows-update-for-business-configure). Tanto los grupos **Modern Workplace Devices -All** y **Modern Workplace -All** Azure AD son grupos que creamos al inscribirse en Escritorio administrado de Microsoft, por lo que tendrás que volver para excluir este grupo después de la inscripción.


## <a name="azure-active-directory-settings"></a>Azure Active Directory configuración

Puede obtener acceso a Azure Active Directory configuración en [Azure Portal](https://portal.azure.com).

### <a name="intune-enrollment"></a>Inscripción en Intune

Windows 10 dispositivos de la organización de Azure AD deben poder inscribirse automáticamente en Intune.

**Advertencia**

Asegúrate de que **el ámbito de usuario MDM** esté establecido en **Algunos** o **Todos,** no **en Ninguno**. Si elige **Some**, vuelva después de la inscripción y  seleccione el grupo Modern **Workplace -All** Azure AD para grupos o un grupo equivalente dirigido a todos los usuarios Escritorio administrado de Microsoft usuario.  Consulta [Configurar la inscripción para Windows dispositivos mediante Microsoft Intune](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment).

### <a name="ad-hoc-subscriptions"></a>Suscripciones ad hoc

Aconseja cómo comprobar una configuración que (si se establece en "false") puede impedir que Enterprise estado móvil funcione correctamente.

**Advertencia**

Asegúrese de **que AllowAdHocSubscriptions** está establecido en **True**. De lo contrario, Enterprise podría no funcionar la itinerancia de estado. Para obtener más información, [vea Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings).


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

Enterprise La itinerancia de estado debe estar habilitada.

**Advertencia**

Asegúrese de que Enterprise itinerancia de estado está habilitada para **Todos** o para **grupos seleccionados.** Para obtener más información, vea [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).

### <a name="licenses"></a>Licencias

Se requiere una serie de licencias para usar Escritorio administrado de Microsoft.

**No listo**

No tiene todas las licencias que necesita para usar Escritorio administrado de Microsoft. Para obtener más información, [vea Escritorio administrado de Microsoft tecnologías y](../intro/technologies.md) más sobre las [licencias.](prerequisites.md#more-about-licenses)


### <a name="microsoft-managed-desktop-service-accounts"></a>Escritorio administrado de Microsoft de servicio

Algunos nombres de cuenta podrían tener conflicto con los nombres de cuenta creados por Escritorio administrado de Microsoft para administrar el Escritorio administrado de Microsoft cuenta.

**No preparado**

Tiene al menos un nombre de cuenta que entra en conflicto con los nombres de cuenta creados por Escritorio administrado de Microsoft. Trabaje con el representante de la cuenta microsoft para excluir estos nombres de cuenta. No enumeramos públicamente los nombres de cuenta para minimizar el riesgo de seguridad. 


### <a name="security-administrator-roles"></a>Roles de administrador de seguridad

Los usuarios con determinados roles de seguridad deben tener asignados esos roles en Microsoft Defender para endpoint.

**Advertencia**

Si tiene usuarios asignados a cualquiera de estos roles en su organización de Azure AD, asegúrese de que también tienen asignados estos roles en Microsoft Defender para endpoint. De lo contrario, los administradores con estos roles no podrán acceder al portal de administración.

- Operador de seguridad
- Lector global

Para obtener más información, vea [Create and manage roles for role-based access control](/windows/security/threat-protection/microsoft-defender-atp/user-roles).


### <a name="security-default"></a>Valor predeterminado de seguridad

Los valores predeterminados de seguridad Azure Active Directory impedirán Escritorio administrado de Microsoft administrar los dispositivos.

**No preparado**

Tiene activados los valores predeterminados de seguridad. Desactiva los valores predeterminados de seguridad y configura las directivas de acceso condicional. Para obtener más información, vea [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common).

### <a name="self-service-password-reset"></a>Restablecimiento de contraseñas de autoservicio

El restablecimiento de contraseñas de autoservicio (SSPR) se puede habilitar para todos los usuarios Escritorio administrado de Microsoft excepto Escritorio administrado de Microsoft de servicio. Para obtener más información, vea Tutorial: Permitir que los usuarios desbloqueen su cuenta o restablezcan contraseñas [mediante Azure Active Directory restablecimiento de contraseñas de autoservicio.](/azure/active-directory/authentication/tutorial-enable-sspr)

**Advertencia**

Asegúrese de que la configuración de SSPR **Selected** incluye Escritorio administrado de Microsoft usuarios, pero excluye Escritorio administrado de Microsoft cuentas de servicio. Escritorio administrado de Microsoft cuentas de servicio no pueden funcionar como se esperaba cuando SSPR está habilitado.  


### <a name="standard-user-role"></a>Rol de usuario estándar

Aparte de los usuarios a los que se les asignan roles de administrador global y administrador de dispositivos de Azure AD, Escritorio administrado de Microsoft usuarios serán usuarios estándar sin privilegios de administrador local. A todos los demás usuarios se les asignará un rol de usuario estándar cuando inicien su Escritorio administrado de Microsoft dispositivo.

**Advertencia**

Escritorio administrado de Microsoft usuarios no tendrán privilegios de administrador local en sus dispositivos Escritorio administrado de Microsoft después de inscribirse.

## <a name="microsoft-365-apps-for-enterprise"></a>Aplicaciones de Microsoft 365 para empresas

### <a name="onedrive"></a>OneDrive

La **configuración Permitir la sincronización solo en equipos unidos** a dominios específicos entra en conflicto con Escritorio administrado de Microsoft. Puede obtener acceso a OneDrive configuración en el centro OneDrive [administración.](https://admin.onedrive.com)

**Advertencia**

Está usando la configuración Permitir la sincronización solo en equipos **unidos a dominios específicos.** Esta configuración no funcionará con Escritorio administrado de Microsoft. Deshabilite esta configuración y, en su lugar, configure OneDrive para usar una directiva de acceso condicional. Consulte [Planear una implementación de acceso condicional](/azure/active-directory/conditional-access/plan-conditional-access) para obtener ayuda.
