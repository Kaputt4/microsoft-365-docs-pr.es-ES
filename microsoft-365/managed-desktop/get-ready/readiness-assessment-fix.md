---
title: Solucionar problemas encontrados por la herramienta de evaluación de preparación
description: Acciones detalladas que se deben realizar para cada problema que encuentra la herramienta
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2c9638dc7b8c6d095b87cf81114f3812c8362597
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656156"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>Solucionar problemas encontrados por la herramienta de evaluación de preparación

Para cada comprobación, la herramienta informará de uno de los tres resultados posibles:


|Resultado  |Significado  |
|---------|---------|
|Listo     | No es necesario realizar ninguna acción antes de completar la inscripción.        |
|Consejo    | Siga los pasos de la herramienta o este artículo para obtener la mejor experiencia con la inscripción y para los usuarios. *Puede* completar la inscripción, pero debe solucionar estos problemas antes de implementar el primer dispositivo.        |
|No preparado | *Se producirá un error en la inscripción si no soluciona estos problemas.* Siga los pasos de la herramienta o este artículo para resolverlos.        |

## <a name="microsoft-intune-settings"></a>Configuración de Microsoft Intune

### <a name="autopilot-deployment-profile"></a>Perfil de implementación de piloto automático

No debe tener ningún perfil de AutoPilot existente destinado a grupos dinámicos o asignados que use el escritorio administrado de Microsoft. Microsoft Managed Desktop usa AutoPilot para aprovisionar nuevos dispositivos.

**No preparado**

Tiene un perfil de AutoPilot asignado a todos los dispositivos. Para conocer los pasos, vea [inscribir dispositivos Windows en Intune mediante Windows AutoPilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot). Después de la inscripción de escritorio administrada de Microsoft, establezca su Directiva de AutoPilot para excluir los **dispositivos del área de trabajo modernos: todos los grupos de** Azure ad.

**Consejo**

Asegúrese de que los perfiles de AutoPilot están destinados a un grupo de Azure AD asignado o dinámico que no incluye los dispositivos de escritorio administrados por Microsoft que se crearán durante la inscripción. Para conocer los pasos, vea [inscribir dispositivos Windows en Intune mediante Windows AutoPilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot). Después de la inscripción de escritorio administrada de Microsoft, establezca su Directiva de AutoPilot para excluir los **dispositivos del área de trabajo modernos: todos los grupos de** Azure ad.


### <a name="certificate-connectors"></a>Conectores de certificados

Si tiene algún conector de certificados usado por los dispositivos que desea inscribir en el escritorio administrado de Microsoft, los conectores no pueden tener errores. Solo uno de los siguientes avisos se aplicará a su situación, por lo que debe comprobarlos cuidadosamente.

**Consejo**

No hay conectores de certificado presentes. Es posible que no necesite ningún conector, pero debe evaluar si es posible que necesite alguna conectividad de red para los dispositivos de escritorio administrados por Microsoft. Para obtener más información, vea [preparar certificados y perfiles de red para el escritorio administrado por Microsoft](certs-wifi-lan.md).

**Consejo**

Al menos un conector de certificado tiene un error. Si necesita este conector para la conectividad con dispositivos de escritorio administrados por Microsoft, debe resolver el error. Para obtener más información, vea [preparar certificados y perfiles de red para el escritorio administrado por Microsoft](certs-wifi-lan.md).


**Consejo**

Tiene al menos un conector de certificados y no se ha notificado ningún error. Sin embargo, es posible que deba crear un perfil para volver a usar el conector para dispositivos de escritorio administrados por Microsoft. Para obtener más información, vea [preparar certificados y perfiles de red para el escritorio administrado por Microsoft](certs-wifi-lan.md).


### <a name="conditional-access-policies"></a>Directivas de acceso condicional

Las directivas de acceso condicional en su organización de Azure AD no deben dirigirse a ningún usuario de escritorio de Microsoft Manage.

**No preparado**

Tiene al menos una directiva de acceso condicional dirigida a todos los usuarios. Restablezca la Directiva para dirigirse a un grupo específico de Azure AD que no incluya el grupo de Azure AD de las cuentas de servicio de escritorio administrado por Microsoft que se crearán en la inscripción. Para conocer los pasos, consulte el [acceso condicional: usuarios y grupos](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).

**Consejo**

Asegúrese de que las directivas de acceso condicional que haya excluido excluyan el grupo de Azure AD de las **cuentas de servicio del lugar de trabajo moderno** . Para conocer los pasos, consulte [ajustar el acceso condicional](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access). El grupo de Azure AD de las **cuentas de servicio del lugar de trabajo modernos** es un grupo dinámico que creamos para el servicio al inscribirse. Tendrá que volver a excluir este grupo después de la inscripción. Para obtener más información acerca de estas cuentas de servicio, consulte [Standard Operations Procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).


### <a name="device-compliance-policies"></a>Directivas de cumplimiento de dispositivos

Las directivas de cumplimiento de dispositivos de Intune en su organización de Azure AD no deben dirigirse a ningún usuario de escritorio administrado por Microsoft.

**No preparado**

Tiene al menos una directiva de cumplimiento que tiene como objetivo todos los usuarios. Restablezca la Directiva para dirigirse a un grupo específico de Azure AD que no incluya ningún usuario de escritorio administrado por Microsoft. Para conocer los pasos, consulte [crear una directiva de cumplimiento en Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).

**Consejo**

Asegúrese de que las directivas de cumplimiento que tenga no incluyan ningún usuario de escritorio administrado por Microsoft. Para conocer los pasos, consulte [crear una directiva de cumplimiento en Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).



### <a name="device-configuration-policies"></a>Directivas de configuración de dispositivo

Las directivas de configuración de dispositivo de Intune en la organización de Azure AD no deben dirigirse a ningún usuario o dispositivo de escritorio de Microsoft Manage.

**No preparado**

Tiene al menos una directiva de configuración que tiene como objetivo todos los usuarios, todos los dispositivos o ambos. Restablezca la Directiva para dirigirse a un grupo específico de Azure AD que no incluya ningún dispositivo de escritorio administrado por Microsoft. Para conocer los pasos, consulte [crear una directiva de cumplimiento en Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).

**Consejo**

Asegúrese de que las directivas de cumplimiento que tenga no incluyan ningún usuario o dispositivo de escritorio administrado por Microsoft. Para conocer los pasos, consulte [crear una directiva de cumplimiento en Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).



### <a name="device-type-restrictions"></a>Restricciones de tipo de dispositivo

Los dispositivos de escritorio administrados por Microsoft deben estar autorizados para inscribirse en Intune.

**No preparado**

Siga los pasos de [establecer restricciones de inscripción](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) para cambiar la configuración a **permitir**.


### <a name="enrollment-status-page"></a>Página de estado de inscripción

Actualmente tiene la página de estado de inscripción (ESP) habilitada. Si está participando en la versión preliminar pública de esta característica, puede omitir este elemento. Para obtener más información, vea [experiencia de primera ejecución con AutoPilot y página de estado de inscripción](../get-started/esp-first-run.md).

**No preparado**

Tiene el perfil predeterminado ESP configurado para mostrar el progreso de la configuración de la **aplicación y el perfil**. Para deshabilitar esta configuración, siga los pasos de la [Página configurar el estado de inscripción](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).

**Consejo**

Asegúrese de que los perfiles que tienen la configuración **Mostrar progreso de configuración de aplicación y perfil** no se asignan a ningún grupo de Azure ad que incluya dispositivos de escritorio administrados por Microsoft. Para obtener más información, consulte [configurar la página de estado de inscripción](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).

### <a name="intune-enrollment"></a>Inscripción de Intune

Los dispositivos con Windows 10 en la organización de Azure AD deben inscribirse automáticamente en Intune.

**No preparado**

Los usuarios de la organización de Azure AD no se inscriben automáticamente en Microsoft Intune. Cambie el **ámbito de usuario** de MDM a **todos o todos**. Si elige. Algunos * *, regresan después de la inscripción y seleccionan el **lugar de trabajo moderno: todos los** grupos de Azure ad para los **grupos**.


### <a name="microsoft-store-for-business"></a>Microsoft Store para Empresas

Usamos Microsoft Store for Business para que pueda descargar el portal de la empresa para implementar algunas aplicaciones, como Microsoft Project y Microsoft Visio.

**No preparado**

Microsoft Store para empresas ya no está habilitado o no está sincronizado con Intune. Para obtener más información, consulte [How to Manage Volume adquiried apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) e [install Intune Company Portal in on Devices](../get-started/company-portal.md).

### <a name="multi-factor-authentication"></a>Autenticación multifactor

La autenticación multifactor no se debe aplicar por accidente a las cuentas de servicio de escritorio administradas por Microsoft.


**No preparado**

Tiene algunas directivas de multi-factor Authentication (MFA) establecidas como "necesarias" para las directivas de acceso condicional asignadas a todos los usuarios. Cambie la Directiva para usar una asignación que tenga como destino un grupo específico de Azure AD que no incluya ningún dispositivo de escritorio administrado por Microsoft. Para obtener más información, consulte [directivas de acceso condicional](#conditional-access-policies) y [acceso condicional: solicitar MFA para todos los usuarios](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).

**Consejo**

Asegúrese de que las directivas de acceso condicional que requieran MFA excluyan el **lugar de trabajo moderno: todos los grupos de** Azure ad. Para obtener más información, consulte [directivas de acceso condicional](#conditional-access-policies) y [acceso condicional: solicitar MFA para todos los usuarios](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa). El **área de trabajo moderna: todo** grupo de Azure ad es un grupo dinámico que creamos al inscribirse en el escritorio administrado de Microsoft, por lo que tendrá que volver a excluir este grupo después de la inscripción.



### <a name="powershell-scripts"></a>Scripts de PowerShell

Los scripts de Windows PowerShell no se pueden asignar de una manera que se dirija a los dispositivos de escritorio administrados por Microsoft.  

**Consejo**

Asegúrese de que los scripts de Windows PowerShell de la organización de Azure AD no tienen como objetivo ningún usuario o dispositivo de escritorio administrado por Microsoft. Para obtener más información, vea [usar scripts de PowerShell en dispositivos Windows 10 en Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).

### <a name="region"></a>Región

Su región debe ser compatible con el escritorio administrado por Microsoft.

**No preparado**

Actualmente, la región de la organización de Azure AD no es compatible con el escritorio administrado por Microsoft. Para obtener más información, consulte [regiones e idiomas admitidos por Microsoft Managed Desktop](../service-description/regions-languages.md).

**Consejo**

Uno o más de los países en los que se encuentra su organización de Azure AD no es compatible con el escritorio administrado por Microsoft. Para obtener más información, consulte [regiones e idiomas admitidos por Microsoft Managed Desktop](../service-description/regions-languages.md).


### <a name="security-baselines"></a>Líneas de base de seguridad

Las directivas de línea de base de seguridad no deben dirigirse a ningún dispositivo de escritorio administrado por Microsoft.

**No preparado**

Tiene un perfil de línea de base de seguridad destinado a todos los usuarios, todos los dispositivos o ambos. Cambie la Directiva para usar una asignación que tenga como destino un grupo específico de Azure AD que no incluya ningún dispositivo de escritorio administrado por Microsoft. Para conocer los pasos, consulte [usar líneas de base de seguridad para configurar dispositivos Windows 10 en Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).

**Consejo**

Asegúrese de que todas las directivas de línea base de seguridad que haya excluido sean dispositivos de escritorio administrados por Microsoft. Para conocer los pasos, consulte [usar líneas de base de seguridad para configurar dispositivos Windows 10 en Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines). Los **dispositivos modernos del área de trabajo: todos los** grupos de Azure ad son un grupo dinámico que creamos al inscribirse en el escritorio administrado de Microsoft, por lo que tendrá que volver a excluir este grupo después de la inscripción.


### <a name="windows-apps"></a>Aplicaciones de Windows

Revise las aplicaciones que desea que tengan los usuarios de escritorio administrado por Microsoft.

**Consejo**

Debe preparar un inventario de las aplicaciones que desea que tengan los usuarios de escritorio administrado por Microsoft. Asegúrese de que estas aplicaciones se pueden implementar con Intune. Para obtener más información, vea [aplicaciones en el escritorio administrado de Microsoft](apps.md).

Puede pedir a su representante de su cuenta de Microsoft una consulta en Microsoft Endpoint Configuration Manager para identificar las aplicaciones que están preparadas para la migración a Intune o el ajuste necesario.


### <a name="windows-hello-for-business"></a>Windows Hello para empresas

El escritorio administrado de Microsoft requiere que Windows Hello para empresas esté habilitado.

**No preparado**

Windows Hello para empresas está deshabilitado. Habilítelo siguiendo los pasos de [crear una directiva de Windows Hello para empresas](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**Consejo**

Windows Hello para empresas no está configurado. Para habilitarla, siga los pasos de [crear una directiva de Windows Hello para empresas](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).


### <a name="windows-10-update-rings"></a>Anillos de actualización de Windows 10

La Directiva "Windows 10 Update Ring" en Intune no debe dirigirse a ningún dispositivo de escritorio administrado por Microsoft.

**No preparado**

Tiene una directiva "actualizar anillo" que tiene como objetivo todos los dispositivos, todos los usuarios o ambos. Cambie la Directiva para usar una asignación que tenga como destino un grupo específico de Azure AD que no incluya ningún dispositivo de escritorio administrado por Microsoft. Para conocer los pasos, consulte [administrar las actualizaciones de software de Windows 10 en Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).

**Consejo**

Asegúrese de que todas las directivas de Update Ring que tiene excluyan el **lugar de trabajo moderno: todos los grupos de** Azure ad. Para conocer los pasos, consulte [administrar las actualizaciones de software de Windows 10 en Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure). Los **dispositivos modernos del área de trabajo: todos los** grupos de Azure ad son un grupo dinámico que creamos al inscribirse en el escritorio administrado de Microsoft, por lo que tendrá que volver a excluir este grupo después de la inscripción.


## <a name="azure-active-directory-settings"></a>Configuración de Azure Active Directory


### <a name="ad-hoc-subscriptions"></a>Suscripciones ad hoc

Aconseja comprobar una opción que (si se establece en "false") impedir que la itinerancia del estado de la empresa funcione correctamente.

**Consejo**

Asegúrese de que **AllowAdHocSubscriptions** está establecido en **true**. De lo contrario, es posible que la itinerancia del estado de la empresa no funcione. Para obtener más información, vea [set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

La itinerancia del estado de la empresa debe estar habilitada.

**Consejo**

Asegúrese de que la itinerancia del estado de la empresa esté habilitada para todos o para **los** grupos **seleccionados** . Para obtener más información, consulte [Habilitar la itinerancia del estado de la empresa en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).

### <a name="licenses"></a>Licencias

Se necesita un número de licencias para usar el escritorio administrado por Microsoft.

**No está listo**

No tiene todas las licencias que necesita para usar Microsoft Managed Desktop. Para obtener más información, consulte [tecnologías de escritorio administradas de Microsoft](../intro/technologies.md) y más información [sobre licencias](prerequisites.md#more-about-licenses).


### <a name="security-account-names"></a>Nombres de cuenta de seguridad

Algunos nombres de cuentas de seguridad podrían entrar en conflicto con los creados por el escritorio administrado por Microsoft.

**No preparado**

Tiene al menos un nombre de cuenta que entrará en conflicto con los creados por el escritorio administrado por Microsoft. Trabaje con el representante de su cuenta de Microsoft para excluir estos nombres de cuenta.


### <a name="security-administrator-roles"></a>Roles de administrador de seguridad

Los usuarios con determinados roles de seguridad deben tener los asignados en Microsoft defender para el punto de conexión.

**Consejo**

Si tiene cualquiera de estos roles asignados en su organización de Azure AD, asegúrese de que también tengan estos roles asignados en Microsoft defender para el punto de conexión. De lo contrario, los administradores con estos roles no podrán obtener acceso al portal de administración.

- Lector de seguridad
- Operador de seguridad
- Lector global

Para obtener más información, vea [Create and Manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).


### <a name="security-default"></a>Seguridad predeterminada

Los valores predeterminados de seguridad de Azure Active Directory impedirán que Microsoft administre el escritorio de sus dispositivos.

**No preparado**

Tiene los valores predeterminados de seguridad activados. Desactivar los valores predeterminados de seguridad y configurar directivas de acceso condicional. Para obtener más información, consulte [directivas de acceso condicional comunes](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).

### <a name="self-service-password-reset"></a>Restablecimiento de contraseña de autoservicio

Debe estar habilitado el restablecimiento de contraseña de autoservicio (SSPR).

**No preparado**

SSPR debe estar habilitado para todos los usuarios. Si no es así, las cuentas de servicio de escritorio administradas de Microsoft no pueden funcionar. Para obtener más información, vea [Tutorial: permitir a los usuarios desbloquear su cuenta o restablecer contraseñas con el restablecimiento de contraseña de autoservicio de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).

**Consejo**

Asegúrese de que la configuración de SSPR **seleccionada** incluye dispositivos de escritorio administrados por Microsoft.

### <a name="standard-user-role"></a>Rol de usuario estándar

Los usuarios de escritorio administrados de Microsoft deben ser usuarios estándar sin privilegios de administrador local. Se les asignará un rol de usuario estándar cuando inicien su dispositivo de escritorio administrado por Microsoft.

**Consejo**

Los usuarios de escritorio administrado de Microsoft no deben tener privilegios de administrador local antes de inscribirse.

## <a name="microsoft-365-apps-for-enterprise"></a>Aplicaciones de Microsoft 365 para empresas

### <a name="onedrive-for-business"></a>OneDrive para la Empresa

La opción **permitir sincronización solo en equipos Unidos a dominios específicos** entrará en conflicto con el escritorio administrado de Microsoft.

**Consejo**

Está usando la opción **permitir sincronización solo en equipos Unidos a dominios específicos** . Esta configuración no funcionará con Microsoft Managed Desktop. Deshabilite esta opción y, en su lugar, configure OneDrive para la empresa para usar una directiva de acceso condicional. Consulte [planear una implementación de acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) para obtener ayuda.

