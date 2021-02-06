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
ms.openlocfilehash: ff2ef15f93cef5255e8c8113facf51b833eff77d
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122365"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>Solucionar los problemas detectados por la herramienta de evaluación de la preparación

Para cada comprobación, la herramienta mostrará uno de los cuatro resultados posibles:


|Resultado  |Significado  |
|---------|---------|
|Listo     | No se requiere ninguna acción antes de completar la inscripción.        |
|Aviso    | Siga los pasos de la herramienta o este artículo para obtener la mejor experiencia con la inscripción y para los usuarios. Puedes *completar* la inscripción, pero debes solucionar estos problemas antes de implementar el primer dispositivo.        |
|No preparado | *Si no solucionas estos problemas, se producirá un error en la inscripción.* Siga los pasos de la herramienta o de este artículo para resolverlos.        |
|Error | El rol de Azure Active Directory (AD) que está usando no tiene permisos suficientes para ejecutar esta comprobación. |

> [!NOTE]
> Los resultados notificados por esta herramienta reflejan el estado de la configuración solo en el momento específico en el que la ejecutó. Si más adelante realiza cambios en las directivas de Microsoft Intune, Azure Active Directory o Microsoft 365, los elementos que estaban "Listos" pueden convertirse en "No listos". Para evitar problemas con las operaciones de Escritorio administrado de Microsoft, compruebe la configuración específica descrita en este artículo antes de cambiar las directivas.

## <a name="microsoft-intune-settings"></a>Configuración de Microsoft Intune

Puedes acceder a la configuración de Intune en el Centro de administración de Microsoft Endpoint [Manager.](https://endpoint.microsoft.com)

### <a name="autopilot-deployment-profile"></a>Perfil de implementación de Autopilot

No debe tener ningún perfil de Autopilot existente destinado a grupos dinámicos o asignados con dispositivos de Escritorio administrado de Microsoft. Escritorio administrado de Microsoft usa Autopilot para aprovisionar nuevos dispositivos.

**No preparado**

Tienes un perfil de Autopilot asignado a todos los dispositivos. Para ver los pasos, [consulta Inscribir dispositivos Windows en Intune con Windows Autopilot.](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot) Después de la inscripción en el Escritorio administrado de Microsoft, establece la directiva de Autopilot para excluir el grupo Dispositivos de Área de **trabajo modernos: todos los** grupos de Azure AD.

**Aviso**

Asegúrate de que los perfiles de Autopilot están destinados a un grupo de Azure AD asignado o dinámico que no incluye dispositivos de Escritorio administrado de Microsoft. Para ver los pasos, [consulta Inscribir dispositivos Windows en Intune con Windows Autopilot.](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot) Después de la inscripción en el Escritorio administrado de Microsoft, establece los perfiles de Autopilot para excluir el grupo Dispositivos de Área de **trabajo modernos: todos los** grupos de Azure AD.


### <a name="certificate-connectors"></a>Conectores de certificados

Si tiene algún conector de certificado que usarán los dispositivos que desea inscribir en el Escritorio administrado de Microsoft, los conectores no deben tener ningún error. Solo uno de los siguientes avisos se aplicará a su situación, así que compróquelos cuidadosamente.

**Aviso**

No hay conectores de certificado presentes. Es posible que no necesite ningún conector, pero debe evaluar si puede necesitar algunos para la conectividad de red en los dispositivos de Escritorio administrado de Microsoft. Para obtener más información, vea Preparar certificados [y perfiles de red para escritorio administrado de Microsoft.](certs-wifi-lan.md)

**Aviso**

Al menos un conector de certificado tiene un error. Si necesita este conector para proporcionar certificados a dispositivos de Escritorio administrado de Microsoft, debe resolver el error. Para obtener más información, vea Preparar certificados [y perfiles de red para escritorio administrado de Microsoft.](certs-wifi-lan.md)


**Aviso**

Tiene al menos un conector de certificado y no se notifican errores. Sin embargo, en preparación para la implementación, es posible que deba crear un perfil para volver a usar el conector para dispositivos de escritorio administrado de Microsoft. Para obtener más información, vea Preparar certificados [y perfiles de red para escritorio administrado de Microsoft.](certs-wifi-lan.md)


### <a name="conditional-access-policies"></a>Directivas de acceso condicional

Las directivas de acceso condicional no deben impedir que el Escritorio administrado de Microsoft administre su organización de Azure AD (inquilino) en Intune y Azure AD.

**No preparado**

Tiene al menos una directiva de acceso condicional dirigida a todos los usuarios. Durante la inscripción, excluiremos las cuentas de servicio de Escritorio administrado de Microsoft de las directivas de acceso condicional relevantes y aplicaremos nuevas directivas de acceso condicional para restringir el acceso a estas cuentas. Después de la inscripción, puedes revisar la directiva de acceso condicional de Escritorio administrado de Microsoft en Microsoft Endpoint Manager. Para obtener más información acerca de estas cuentas de servicio, vea [Procedimientos operativos estándar.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Aviso**

Tiene directivas de acceso condicional que podrían impedir que El Escritorio administrado de Microsoft pueda administrar el servicio de Escritorio administrado de Microsoft. Durante la inscripción, excluiremos las cuentas de servicio de Escritorio administrado de Microsoft de las directivas de acceso condicional relevantes y aplicaremos nuevas directivas de acceso condicional para restringir el acceso a estas cuentas. Para obtener más información acerca de estas cuentas de servicio, vea [Procedimientos operativos estándar.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Error**

El rol de administrador de Intune no tiene permisos suficientes para esta comprobación. También necesitará cualquiera de estos roles de Azure AD asignados para ejecutar esta comprobación:

- Lector de seguridad
- Administrador de seguridad
- Administrador de acceso condicional
- Lector global
- Administrador de dispositivos


### <a name="device-compliance-policies"></a>Directivas de cumplimiento de dispositivos

Las directivas de cumplimiento de dispositivos de Intune en la organización de Azure AD pueden afectar a los dispositivos de Escritorio administrado de Microsoft.

**No preparado**

Tiene al menos una directiva de cumplimiento que está dirigida a todos los usuarios. Escritorio administrado de Microsoft incluye directivas de cumplimiento destinadas a los dispositivos de Escritorio administrado de Microsoft.  Cambie la directiva para dirigirse a un grupo específico de Azure AD que no incluya ningún dispositivo o usuario de Escritorio administrado de Microsoft. Para ver los pasos, [consulte Crear una directiva de cumplimiento en Microsoft Intune.](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)

**Aviso**

Asegúrese de que las directivas de cumplimiento que tenga no tengan como destino ningún usuario de Escritorio administrado de Microsoft. Para ver los pasos, [consulte Crear una directiva de cumplimiento en Microsoft Intune.](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)



### <a name="device-configuration-profiles"></a>Perfiles de configuración de dispositivos

Los perfiles de configuración de dispositivos de Intune en la organización de Azure AD no deben dirigirse a ningún dispositivo o usuario de Microsoft Manage Desktop.

**No preparado**

Tiene al menos un perfil de configuración que está dirigido a todos los usuarios, todos los dispositivos o ambos. Restablezca el perfil para dirigirse a un grupo específico de Azure AD que no incluya ningún dispositivo de Escritorio administrado de Microsoft. Para ver los pasos, [consulta Crear un perfil con configuración personalizada en Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)

**Aviso**

Asegúrese de que las directivas de configuración que tenga no incluyan ningún dispositivo o usuario de Escritorio administrado de Microsoft. Para ver los pasos, [consulta Crear un perfil con configuración personalizada en Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)



### <a name="device-type-restrictions"></a>Restricciones de tipo de dispositivo

Los dispositivos de Escritorio administrado de Microsoft deben tener permiso para inscribirse en Intune.

**No preparado**

Actualmente tiene al menos una directiva de restricción de inscripción configurada para impedir que los dispositivos Windows se insinste en Intune. Sigue los pasos descritos en [Establecer restricciones](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) de inscripción para cada directiva de restricción de inscripción dirigida a los usuarios de Escritorio administrado de Microsoft y cambia la configuración de **Windows (MDM)** a **Permitir.** Sin embargo, puedes establecer cualquier dispositivo de **Windows (MDM)** de propiedad **personal** en **Bloquear.** 


### <a name="enrollment-status-page"></a>Página de estado de inscripción

Actualmente tiene habilitada la página de estado de inscripción (ESP). Si desea participar en la vista previa pública de Escritorio administrado de Microsoft de esta característica, puede omitir este elemento. Para obtener más información, consulta [la experiencia de primera ejecución con Autopilot y la página de estado de inscripción.](../get-started/esp-first-run.md)

**No preparado**

Tiene el perfil predeterminado ESP establecido en **Mostrar el progreso de la configuración de aplicaciones y perfiles.** Deshabilite esta configuración o asegúrese de que las asignaciones a cualquier grupo de Azure AD no incluyan dispositivos de Escritorio administrado de Microsoft siguiendo los pasos descritos en Configurar la página de estado [de inscripción.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)

**Aviso**

Asegúrate de que los perfiles que tengan la opción Mostrar la aplicación y el progreso de la configuración de perfiles no estén asignados a ningún grupo de Azure AD que incluya dispositivos de Escritorio administrado de Microsoft.  Para obtener más información, consulta [Configurar la página de estado de inscripción.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)

### <a name="microsoft-store-for-business"></a>Microsoft Store para Empresas

Usamos la Microsoft Store para Empresas e implementamos la aplicación Portal de empresa en escritorio administrado de Microsoft para permitir a los usuarios instalar opcionalmente algunas aplicaciones, como Microsoft Project y Microsoft Visio (cuando se permite).

**No preparado**

La Microsoft Store para Empresas no está habilitada o no está sincronizada con Intune. Para obtener más información, consulta Cómo administrar las aplicaciones compradas por volumen de la [Microsoft Store](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) para Empresas con Microsoft Intune e Instalar el Portal de empresa de Intune en [dispositivos.](../get-started/company-portal.md)

### <a name="multifactor-authentication"></a>Autenticación multifactor

La autenticación multifactor no debe impedir que el Escritorio administrado de Microsoft administre la organización de Azure AD (inquilino) en Intune y Azure AD.


**No preparado**

Tiene algunas directivas de autenticación multifactor establecidas según sea **necesario** para las directivas de acceso condicional asignadas a todos los usuarios. Durante la inscripción, excluiremos las cuentas de servicio de Escritorio administrado de Microsoft de las directivas de acceso condicional relevantes y aplicaremos nuevas directivas de acceso condicional para restringir el acceso a estas cuentas. Para obtener más información acerca de estas cuentas de servicio, vea [Procedimientos operativos estándar.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Aviso**

La autenticación multifactor es necesaria en las directivas de acceso condicional que podrían impedir que El Escritorio administrado de Microsoft pueda administrar el servicio de Escritorio administrado de Microsoft. Durante la inscripción, excluiremos las cuentas de servicio de Escritorio administrado de Microsoft de las directivas de acceso condicional relevantes y aplicaremos nuevas directivas de acceso condicional para restringir el acceso a estas cuentas. Para obtener más información acerca de estas cuentas de servicio, vea [Procedimientos operativos estándar.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Error**

El rol de administrador de Intune no tiene permisos suficientes para esta comprobación. También necesitará cualquiera de estos roles de Azure AD asignados para ejecutar esta comprobación:

- Lector de seguridad
- Administrador de seguridad
- Administrador de acceso condicional
- Lector global
- Administrador de dispositivos


### <a name="powershell-scripts"></a>Scripts de PowerShell

Windows PowerShell los scripts no se pueden asignar de forma que se desasigne a dispositivos de Escritorio administrado de Microsoft.  

**Aviso**

Asegúrese de que Windows PowerShell scripts de la organización de Azure AD no se dirige a ningún dispositivo o usuario de Microsoft Manage Desktop. No asigne un script de PowerShell para dirigirse a todos los usuarios, todos los dispositivos o ambos. Cambie la directiva para usar una asignación dirigida a un grupo específico de Azure AD que no incluya ningún dispositivo o usuario de Escritorio administrado de Microsoft. Para obtener más información, consulta [Usar scripts de PowerShell en dispositivos windows 10 en Intune.](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)

### <a name="region"></a>Región

Su región debe ser compatible con el Escritorio administrado de Microsoft.

**No preparado**

La región de la organización de Azure AD no es compatible actualmente con escritorio administrado de Microsoft. Para obtener más información, vea [idiomas y regiones compatibles con](../service-description/regions-languages.md)escritorio administrado de Microsoft.

**Aviso**

Uno o varios de los países donde se encuentra la organización de Azure AD no son compatibles con el Escritorio administrado de Microsoft. Para obtener más información, vea [idiomas y regiones compatibles con](../service-description/regions-languages.md)escritorio administrado de Microsoft.


### <a name="security-baselines"></a>Líneas base de seguridad

Las directivas de línea base de seguridad no deben dirigirse a ningún dispositivo de Escritorio administrado de Microsoft.

**No preparado**

Tiene un perfil de línea base de seguridad dirigido a todos los usuarios, todos los dispositivos o ambos. Cambie la directiva para usar una asignación dirigida a un grupo específico de Azure AD que no incluya ningún dispositivo de Escritorio administrado de Microsoft. Para ver los pasos, [consulta Usar líneas base de seguridad para configurar dispositivos Windows 10 en Intune.](https://docs.microsoft.com/mem/intune/protect/security-baselines) Durante la inscripción, aplicamos una nueva línea base de seguridad a todos los dispositivos de Escritorio administrado de Microsoft. Después de la inscripción, puedes revisar la directiva de línea base de seguridad de Escritorio administrado de Microsoft en el área **de** directiva de configuración de Microsoft Endpoint Manager.

**Aviso**

Asegúrese de que las directivas de línea base de seguridad que haya excluido los dispositivos de Escritorio administrado de Microsoft. Para ver los pasos, [consulta Usar líneas base de seguridad para configurar dispositivos Windows 10 en Intune.](https://docs.microsoft.com/mem/intune/protect/security-baselines) Durante la inscripción, aplicamos una nueva línea base de seguridad a todos los dispositivos de Escritorio administrado de Microsoft. El **grupo Modern Workplace Devices -All** Azure AD es un grupo dinámico que creamos cuando te inscribes en el Escritorio administrado de Microsoft, por lo que tendrás que volver para excluir este grupo después de la inscripción. 


### <a name="windows-apps"></a>Aplicaciones de Windows

Revise las aplicaciones que desea que tengan los usuarios de Escritorio administrado de Microsoft.

**Aviso**

Debe preparar un inventario de las aplicaciones que desea que tengan los usuarios de Escritorio administrado de Microsoft. Dado que Intune debe implementar estas aplicaciones, evalúa la reusación de las aplicaciones existentes de Intune. Considera la posibilidad de usar el Portal de empresa (consulta Instalar el Portal de empresa [de Intune](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) en dispositivos y la página de estado de inscripción (ESP) para distribuir aplicaciones a los usuarios. Para obtener más información, vea Aplicaciones en escritorio administrado de [Microsoft](apps.md) y experiencia de primera ejecución [con Autopilot y la página estado de inscripción.](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run)

Puedes solicitar al representante de tu cuenta de Microsoft una consulta en Microsoft Endpoint Configuration Manager para identificar las aplicaciones que están listas para migrar a Intune o que necesitan ajustes.


### <a name="windows-hello-for-business"></a>Windows Hello para empresas

Escritorio administrado de Microsoft requiere que Windows Hello para empresas esté habilitado.

**No preparado**

Windows Hello para empresas está deshabilitado. Para habilitarla, siga los pasos descritos [en Crear una directiva de Windows Hello para empresas](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**Aviso**

Windows Hello para empresas no está configurado. Para habilitarla, siga los pasos de [Crear una directiva de Windows Hello para empresas.](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)


### <a name="windows-10-update-rings"></a>Anillos de actualización de Windows 10

La directiva "Anillo de actualización de Windows 10" en Intune no debe dirigirse a ningún dispositivo de Escritorio administrado de Microsoft.

**No preparado**

Tienes una directiva de "anillo de actualización" dirigida a todos los dispositivos, todos los usuarios o ambos. Cambia la directiva para usar una asignación dirigida a un grupo específico de Azure AD que no incluya ningún dispositivo de Escritorio administrado de Microsoft. Para ver los pasos, consulta Administrar actualizaciones de software de [Windows 10 en Intune.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)

**Aviso**

Asegúrese de que todas las directivas de anillo de actualización que tenga excluyan el grupo **Dispositivos de Área de trabajo modernos: todos los** grupos de Azure AD. Si has asignado grupos de usuarios de Azure AD a estas directivas, asegúrate de que cualquier directiva de anillo de actualización que también haya excluido el grupo **Modern Workplace -All** Azure AD al que agregas los usuarios de Escritorio administrado de Microsoft (o un grupo equivalente). Para ver los pasos, consulta Administrar actualizaciones de software de [Windows 10 en Intune.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure) Tanto los dispositivos de área de trabajo modernos **:todos** como los grupos de **Azure** AD son grupos que creamos cuando se inscribe en el escritorio administrado de Microsoft, por lo que tendrá que volver para excluir este grupo después de la inscripción.


## <a name="azure-active-directory-settings"></a>Configuración de Azure Active Directory

Puede acceder a la configuración de Azure Active Directory en [Azure Portal.](https://portal.azure.com)

### <a name="intune-enrollment"></a>Inscripción de Intune

Los dispositivos Windows 10 de la organización de Azure AD deben poder inscribirse automáticamente en Intune.

**Aviso**

Asegúrate de que **el ámbito de usuario de MDM** esté establecido en **Algunos** o **todos,** no en **Ninguno.** Si elige **Algunos,** vuelva después de la inscripción y seleccione  el grupo **Modern Workplace -All** Azure AD para grupos o un grupo equivalente destinado a todos los usuarios de Escritorio administrado de Microsoft.  Consulta [Configurar la inscripción para dispositivos Windows con Microsoft Intune.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)


### <a name="ad-hoc-subscriptions"></a>Suscripciones ad hoc

Indica cómo comprobar una configuración que (si se establece en "false") podría impedir que enterprise State Roaming funcione correctamente.

**Aviso**

Asegúrese de **que AllowAdHocSubscriptions** está establecido en **True**. De lo contrario, es posible que la itinerancia de estado empresarial no funcione. Para obtener más información, [vea Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

La itinerancia de estado de empresa debe estar habilitada.

**Aviso**

Asegúrate de que Enterprise State Roaming está habilitado para **todos o** para **los grupos** seleccionados. Para obtener más información, vea [Habilitar Enterprise State Roaming en Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)

### <a name="licenses"></a>Licencias

Se requieren varias licencias para usar el Escritorio administrado de Microsoft.

**No listo**

No tiene todas las licencias que necesita para usar el Escritorio administrado de Microsoft. Para obtener más información, vea [Tecnologías de Escritorio administrado de Microsoft](../intro/technologies.md) y Más información sobre las [licencias.](prerequisites.md#more-about-licenses)


### <a name="microsoft-managed-desktop-service-accounts"></a>Cuentas de servicio de Escritorio administrado de Microsoft

Algunos nombres de cuenta podrían estar en conflicto con los nombres de cuenta creados por Escritorio administrado de Microsoft para administrar el servicio de Escritorio administrado de Microsoft.

**No preparado**

Tiene al menos un nombre de cuenta que entra en conflicto con los nombres de cuenta creados por el Escritorio administrado de Microsoft. Trabaje con su representante de cuenta de Microsoft para excluir estos nombres de cuenta. No enumeramos públicamente los nombres de cuenta para minimizar el riesgo de seguridad. 


### <a name="security-administrator-roles"></a>Roles de administrador de seguridad

Los usuarios con determinados roles de seguridad deben tener esos roles asignados en Microsoft Defender para Endpoint.

**Aviso**

Si tienes usuarios asignados a cualquiera de estos roles en tu organización de Azure AD, asegúrate de que también tengan estos roles asignados en Microsoft Defender para Endpoint. De lo contrario, los administradores con estos roles no podrán acceder al portal de administración.

- Operador de seguridad
- Lector global

Para obtener más información, vea [Crear y administrar roles para el control de acceso basado en roles.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)


### <a name="security-default"></a>Valor predeterminado de seguridad

Los valores predeterminados de seguridad en Azure Active Directory impedirán que el Escritorio administrado de Microsoft gestione los dispositivos.

**No preparado**

Tiene activados los valores predeterminados de seguridad. Desactive los valores predeterminados de seguridad y configure las directivas de acceso condicional. Para obtener más información, vea [Directivas comunes de acceso condicional.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)

### <a name="self-service-password-reset"></a>Autoservicio de restablecimiento de contraseña

El autoservicio de restablecimiento de contraseña (SSPR) se puede habilitar para todos los usuarios de Escritorio administrado de Microsoft, excepto las cuentas de servicio de Escritorio administrado de Microsoft. Para obtener más información, vea tutorial: permitir a los usuarios desbloquear su cuenta o restablecer contraseñas mediante el restablecimiento de contraseña de autoservicio de [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)

**Aviso**

Asegúrese de que la  configuración seleccionada de SSPR incluya usuarios de Escritorio administrado de Microsoft, pero excluya las cuentas de servicio de Escritorio administrado de Microsoft. Las cuentas de servicio de Escritorio administrado de Microsoft no pueden funcionar como se esperaba cuando SSPR está habilitado.  


### <a name="standard-user-role"></a>Rol de usuario estándar

Aparte de los usuarios que tienen asignados roles de Administrador global y Administrador de dispositivos de Azure AD, los usuarios de Escritorio administrado de Microsoft serán usuarios estándar sin privilegios de administrador local. A todos los demás usuarios se les asignará un rol de usuario estándar cuando inicien su dispositivo de Escritorio administrado de Microsoft.

**Aviso**

Los usuarios de Escritorio administrado de Microsoft no tendrán privilegios de administrador local en sus dispositivos de Escritorio administrado de Microsoft después de inscribirse.

## <a name="microsoft-365-apps-for-enterprise"></a>Aplicaciones de Microsoft 365 para empresas

### <a name="onedrive"></a>OneDrive

La **opción Permitir sincronización solo en equipos unidos** a dominios específicos entra en conflicto con el Escritorio administrado de Microsoft. Puede acceder a la configuración de OneDrive en el Centro de [administración de OneDrive.](https://admin.onedrive.com)

**Aviso**

Usa la opción Permitir sincronización solo en equipos unidos a **dominios específicos.** Esta configuración no funcionará con el Escritorio administrado de Microsoft. Deshabilite esta configuración y, en su lugar, configure OneDrive para usar una directiva de acceso condicional. Vea [La planeación de una implementación de acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) para obtener ayuda.
