---
title: 'Fase 2: Criterios de salida de infraestructura de identidades'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Asegúrese de que la configuración cumpla los criterios de Microsoft 365 Enterprise para la infraestructura y los servicios basados en identidades.
ms.openlocfilehash: 3fd4d0a1df50d55cb7a21668b609341d0c01aa35
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2020
ms.locfileid: "42544069"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a>Fase 2: Criterios de salida de infraestructura de identidades

![Fase 2-Identidad](../media/deploy-foundation-infrastructure/identity_icon-small.png)

Asegúrese de que su infraestructura de identidad cumpla los siguientes criterios necesarios y que ha considerado aquellos que son opcionales.

Vea también [Requisitos previos](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites) para obtener recomendaciones adicionales de infraestructuras de identidades.

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a>Obligatorio: Las cuentas de administrador global están protegidas 

Ha [protegido sus cuentas](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) de administrador global de Office 365 para combatir el compromiso de las credenciales por parte de atacantes que puedan ocasionar infracciones de la suscripción a Microsoft 365.

Si omite este requisito, las cuentas de administrador global pueden ser susceptibles a ataques y estar en peligro, lo que permitiría a un atacante obtener acceso a todo el sistema para recolectar, destruir o bloquear sus datos para pedir un rescate.

Si es necesario, el [Paso 1](identity-create-protect-global-admins.md#identity-global-admin) puede resultarle útil para cumplir este requisito.

### <a name="how-to-test"></a>Procedimiento de prueba

Siga estos pasos para comprobar que protegió las cuentas de administrador global:

1. Ejecute el siguiente comando de Active Directory de Azure PowerShell para Graph en el símbolo de sistema de PowerShell: Solo debería ver la lista de cuentas de administrador global dedicadas.
   ```powershell
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. Inicie sesión en Office 365 con cada una de las cuentas del paso 1. Cada inicio de sesión tiene que exigir la Azure Multi-Factor Authentication y el método más seguro de autenticación secundaria disponible en su organización.

> [!Note]
> Vea [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) (Conexión a PowerShell de Office 365) para obtener instrucciones de instalación de Azure Active Directory PowerShell para el módulo de Graph e inicio de sesión en Office 365.

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a>Opcional: configuró Privileged Identity Management para facilitar la asignación a petición del rol Administrador global

Siguió las instrucciones que se indican en [Configurar Azure AD Privileged Identity Management (PIM)](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) para habilitar PIM en el espacio empresarial de Azure AD y configuró las cuentas de administrador global como administradores aptos.

También siguió las recomendaciones que se indican en [Proteger el acceso con privilegios para implementaciones híbridas y de nube en Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) para elaborar un plan de desarrollo que proteja el acceso con privilegios frente a los ciberatacantes.

Si omite esta opción, las cuentas de administrador global estarán sujetas a ataques en línea continuados y, si se ponen en peligro, pueden permitir que un atacante recopile, destruya o impida el acceso a la información confidencial para pedir un rescate.

Si es necesario, el [paso 1](identity-create-protect-global-admins.md#identity-pim) puede ayudarle con esta opción.

<a name="crit-identity-pam"></a>
## <a name="optional-you-have-configure-privileged-access-management-in-office-365"></a>Opcional: ha configurado la administración del acceso con privilegios para Office 365

Ha usado la información en el tema [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) (Configuración de la administración del acceso con privilegios en Office 365) para habilitar el acceso con privilegios y crear una o más directivas de acceso con privilegios en su organización. Ha configurado estas directivas y el acceso Just-in-time está habilitado para el acceso a la información confidencial o el acceso a la configuración crítica.

Si es necesario, el [Paso 1](identity-create-protect-global-admins.md#identity-pam) puede resultarle útil para cumplir este requisito. 

<a name="crit-password-prot"></a>
## <a name="optional-azure-ad-password-protection-is-banning-the-use-of-weak-passwords"></a>Opcional: la protección con contraseña de Azure AD no permite el uso de contraseñas poco seguras

Ha habilitado la prohibición de contraseñas no válidas [en la nube](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) y para los [Servicios de dominio de Active Directory (AD DS) locales](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) para las contraseñas no permitidas globales y, opcionalmente, para los términos personalizados.

Si es necesario, el [paso 2](identity-secure-your-passwords.md#identity-password-prot) puede ayudarle con esta opción.

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a>Opcional: los usuarios pueden restablecer sus propias contraseñas

Usó la [implementación rápida de autoservicio de restablecimiento de contraseña de Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) para configurar el restablecimiento de contraseña de los usuarios.

Si no cumple esta condición, los usuarios tendrán que ponerse en contacto con los administradores de cuentas de usuario para restablecer sus contraseñas, lo que producirá una sobrecarga administrativa adicional para el personal de TI.

Si es necesario, el [paso 2](identity-secure-your-passwords.md#identity-pw-reset) puede ayudarle con esta opción.

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-azure-ad-seamless-single-sign-on"></a>Opcional: Los usuarios pueden iniciar sesión con el inicio de sesión único de conexión directa de Azure AD.

Habilitó [Azure AD Connect: Inicio de sesión único de conexión directa](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) en su organización para simplificar la forma en que los usuarios inician sesión en las aplicaciones basadas en la nube, como Office 365.

Si omite esta opción, es posible que se pida a sus usuarios que proporcionen credenciales cuando accedan a aplicaciones adicionales que utilicen su espacio empresarial de Azure AD.

Si es necesario, el [paso 2](identity-secure-your-passwords.md#identity-sso) puede ayudarle con esta opción.

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a>Opcional: La pantalla de inicio de sesión de Office 365 está personalizada para su organización

Siguió los pasos indicados en [Agregar personalización de marca de la compañía a las páginas de inicio de sesión y del panel de acceso](https://aka.ms/aadpaddbranding) para agregar la personalización de marca de su organización a la página de inicio de sesión de Office 365.

Si omitió esta opción, los usuarios verán una pantalla de inicio de sesión de Office 365 genérica y es posible que no estén seguros de si inician la sesión en el sitio de su organización.

Si es necesario, el [paso 2](identity-secure-your-passwords.md#identity-custom-sign-in) puede ayudarle con esta opción.


<a name="crit-identity-mfa"></a>
## <a name="optional-azure-multi-factor-authentication-is-enabled-for-your-users"></a>Opcional: La Azure Multi-Factor Authentication está habilitada para los usuarios

Usó [Plan para la Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) y las [directivas de acceso condicional](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) para habilitar la Azure Multi-Factor Authentication (MFA) de Azure para sus cuentas de usuario.

Si omite esta opción, las cuentas de usuario serán vulnerables a ciberatacantes que intenten apropiarse de las credenciales. Si la contraseña de una cuenta de usuario está en peligro, el atacante tendrá acceso todos los recursos y funciones de la cuenta (como los roles de administrador). Esto permite al atacante copiar, destruir o pedir un rescate por los documentos internos y otros datos.

Si es necesario, el [paso 3](identity-secure-user-sign-ins.md#identity-mfa) puede ayudarle con esta opción.

### <a name="how-to-test"></a>Procedimiento de prueba

1.  Cree una cuenta de usuario de prueba y asígnele una licencia. 
2.  Configure la Azure Multi-Factor Authentication para la cuenta de usuario de prueba con el método de verificación adicional que está utilizando para las cuentas de usuario reales, por ejemplo, el envío de un mensaje de texto a su teléfono. 
3.  Inicie sesión en el portal de Office 365 con la cuenta de usuario de prueba.
4.  Asegúrese de que MFA le pide la información de verificación adicional y que la autenticación se complete correctamente. 
5.  Elimine la cuenta de usuario de prueba.

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise-microsoft-365-e5-only"></a>Opcional: Azure AD Identity Protection está habilitado para proteger contra riesgos de credenciales (sólo Microsoft 365 E5)

Habilitó Azure AD Identity Protection para:

- Solucionar posibles vulnerabilidades de identidad.
- Detectar posibles intentos de uso ilícito de credenciales.
- Investigar y solucionar incidentes de identidad sospechosos y continuados.

Si omite esta opción, no podrá detectar ni combatir automáticamente intentos de acceso ilícito a credenciales, ni podrá investigar los incidentes de seguridad relacionados con identidades. Esto deja a su organización vulnerable ante posibles ataques de acceso ilícito a credenciales y la amenaza resultante para la información confidencial de su organización.

Si es necesario, el [paso 3](identity-secure-user-sign-ins.md#identity-ident-prot) puede ayudarle con esta opción.


### <a name="how-to-test"></a>Procedimiento de prueba

1. Cree una cuenta de usuario de prueba con una contraseña inicial.
2. Siga los pasos que se indican en [Dejar que los usuarios restablezcan sus propias contraseñas en Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) para restablecer la contraseña en la cuenta de usuario de prueba.
3. Cierre la sesión y, después, inicie sesión con la cuenta de usuario de prueba con la contraseña restablecida.
4. Elimine la cuenta de usuario de prueba.

<a name="crit-identity-sync"></a>
## <a name="required-for-hybrid-identity-users-and-groups-are-synchronized-with-azure-ad"></a>Obligatorio para la identidad híbrida: los usuarios y grupos se sincronizarán con Azure AD

Si ya usa un proveedor de identidades local, como Active Directory Domain Services (AD DS), quiere decir que usó Azure AD Connect para sincronizar las cuentas de usuario y los grupos de su proveedor de identidades local con el espacio empresarial de Azure AD.

Con la sincronización de directorios, los usuarios pueden iniciar sesión en Office 365 y en otros Servicios en la nube de Microsoft con las mismas credenciales que usen para iniciar sesión en sus equipos y para obtener acceso a recursos locales.

Si es necesario, el [Paso 4](identity-add-user-accounts.md#identity-sync) puede ayudarle a cumplir este requisito.

Si omite este requisito, tendrá dos conjuntos de cuentas de usuario y grupos:

- Cuentas de usuario y grupos que existen en AD DS local
- Cuentas de usuario y grupos que existen en el espacio empresarial de Azure AD

En este estado, es necesario que tanto los administradores de TI como los usuarios realicen el mantenimiento de forma manual de los dos conjuntos de cuentas de usuario y grupos. Sin duda, esto provocará cuentas, contraseñas y grupos no sincronizados.

### <a name="how-to-test"></a>Procedimiento de prueba
Para comprobar que la autenticación con las credenciales locales funcione correctamente, inicie sesión en el portal de Office con sus credenciales locales.

Para comprobar que la sincronización de directorios funcione correctamente, siga este procedimiento:

1.  Crear un nuevo grupo de prueba en AD DS.
2.  Espere hasta la hora de sincronización.
3.  Compruebe que el nuevo nombre de grupo de prueba se muestre en el espacio empresarial de Azure AD.

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a>Opcional: La sincronización de directorios se supervisa

Siguió los pasos indicados en [Azure AD Connect Health con sincronización](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (para la sincronización de contraseña) o [Usar Azure AD Connect Health con AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (para la autenticación federada) e implementó Azure AD Connect Health, lo que implica lo siguiente:

- La instalación del agente de Azure AD Connect Health en todos los servidores de identidades locales.
- Uso del portal de Azure AD Connect Health para supervisar el estado de la sincronización continuada.

Si omite esta opción, podrá evaluar con mayor precisión el estado de su infraestructura de identidades basada en la nube.

Si es necesario, el [paso 4](identity-add-user-accounts.md#identity-sync-health) puede resultarle útil con esta opción.

### <a name="how-to-test"></a>Procedimiento de prueba
El portal Azure AD Connect Health muestra el estado actual y correcto de sus controladores de dominio locales y la sincronización en curso.


<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a>Opcional: La escritura diferida de contraseñas está habilitada para los usuarios

Siguió las instrucciones que se indican en [SSPR de Azure AD con escritura diferida de contraseñas](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) para habilitar la escritura diferida de contraseñas para el espacio empresarial de Azure AD de su suscripción de Microsoft 365 Enterprise.

Si omite esta opción, los usuarios que no estén conectados a la red local tendrán que pedir a un administrador de TI que restablezca o desbloquee sus contraseñas de AD DS.

Si es necesario, el [paso 4](identity-add-user-accounts.md#identity-pw-writeback) puede ayudarle con esta opción.

>[!Note]
>La escritura diferida de contraseñas es necesaria para usar todas las características de protección Azure AD Identity Protection, como solicitar a los usuarios que cambien sus contraseñas locales cuando Azure AD detecte un alto riesgo de peligro para la cuenta.
>

### <a name="how-to-test"></a>Procedimiento de prueba

Puede probar la escritura diferida de contraseñas cambiando la contraseña en Office 365. Debería poder usar su cuenta y su contraseña nueva para acceder a los recursos locales de AD DS.

1. Cree una cuenta de usuario de prueba en su AD DS local, permita que se produzca la sincronización de directorios y, a continuación, conceda una licencia de Microsoft 365 Enterprise en el Centro de administración de Microsoft 365.
2. Desde un equipo remoto unido al dominio local de AD DS, inicie sesión en el equipo y en el portal de Office con las credenciales de la cuenta de usuario de prueba.
3. Seleccione **Configuración > Configuración de Office 365 > Contraseña > Cambiar contraseña**.
4. Escriba la contraseña actual, la nueva contraseña y la confirmación de contraseña.
5. Cierre la sesión del portal de Office y del equipo remoto e inicie sesión en el equipo con la cuenta de usuario de prueba y su contraseña nueva. Esto comprueba que puede cambiar la contraseña de una cuenta de usuario local de AD DS usando el espacio empresarial de Azure AD.

### <a name="how-to-test"></a>Procedimiento de prueba

Inicie sesión en el portal de Office 365 con el nombre de usuario de su cuenta y la Azure Multi-Factor Authentication. En la página de inicio de sesión, verá los elementos personalizados de su marca.


<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a>Opcional: La administración de grupos de autoservicio está habilitada para grupos específicos de Office 365 y seguridad de Azure AD

Determinó los grupos adecuados para la administración de autoservicio, informó a los propietarios de las responsabilidades y flujos de trabajo de administración de grupos, y [configuró la administración de autoservicio en Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) para esos grupos.

Si omite esta opción, los administradores de TI tendrán que realizar todas las tareas de administración de grupos de Azure AD.

Si necesita ayuda con esta opción, vea el [paso 5](identity-use-group-management.md#identity-self-service-groups).

### <a name="how-to-test"></a>Procedimiento de prueba
1.  Cree una cuenta de usuario de prueba en Azure AD con Azure Portal.
2.  Inicie sesión con la cuenta de usuario de prueba y cree un grupo de seguridad de Azure AD de prueba.
3.  Cierre la sesión y, después, inicie sesión con la cuenta de administrador de TI.
4.  Configure el grupo de seguridad de prueba para la administración de autoservicio de la cuenta de usuario de prueba.
5.  Cierre la sesión y, después, inicie sesión con la cuenta de usuario de prueba.
6.  Use Azure Portal para agregar miembros al grupo de seguridad de prueba.
7.  Elimine el grupo de seguridad de prueba y la cuenta de usuario de prueba.

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a>Opcional: La configuración de pertenencia a grupos dinámica agrega automáticamente cuentas de usuario a grupos basándose en los atributos de cuenta de usuario

Determinó el conjunto de grupos dinámicos de Azure AD y siguió las instrucciones que se indican en [Pertenencia a grupos dinámica basada en atributos en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) para crear los grupos y las reglas que determinan el conjunto de atributos de cuenta de usuario y los valores para la pertenencia a grupos.

Si omite esta opción, será necesario asignar la pertenencia a grupos de forma manual cuando se agreguen nuevas cuentas o cuando los atributos de cuenta de usuario cambien con el tiempo. Por ejemplo, si alguien cambia del Departamento de Ventas al Departamento de Contabilidad, tendrá que:

- Actualizar el valor del atributo “Departamento” de esa cuenta de usuario.
- Quitarlo de forma manual del grupo “Ventas”.
- Agregarlo de forma manual al grupo “Contabilidad”.

Si los grupos “Ventas” o “Contabilidad” fueran dinámicos, solo tendría que cambiar el valor de “Departamento” de la cuenta de usuario.

Si necesita ayuda con esta opción, vea el [paso 5](identity-use-group-management.md#identity-dyn-groups).

### <a name="how-to-test"></a>Procedimiento de prueba

1. Cree un grupo dinámico de prueba en Azure AD con Azure Portal y configure la regla para que “Departamento” sea igual a “prueba1”.
2. Cree una cuenta de usuario de prueba en Azure AD y establezca la propiedad “Departamento” en “prueba1”.
3. Examine las propiedades de la cuenta de usuario para asegurarse de que sea miembro del grupo dinámico de prueba.
4. Cambie el valor de la propiedad “Departamento” de la cuenta de usuario de prueba a “prueba2”.
5. Examine las propiedades de la cuenta de usuario para asegurarse de que ya no sea miembro del grupo dinámico de prueba.
6. Elimine el grupo dinámico de prueba y la cuenta de usuario de prueba.

<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a>Opcional: licencias basadas en grupos para asignar y quitar automáticamente licencias a cuentas de usuario basándose en la pertenencia a grupos

[Habilitó las licencias basadas en grupos](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) para los grupos de seguridad de Azure AD correspondientes para que se asignen o quiten automáticamente las licencias de Microsoft 365 Enterprise.

Si omite esta opción, tendrá que realizar estos pasos de forma manual:

- Asigne licencias a los nuevos usuarios a los que desea tener acceso.
- Anule la asignación de licencias de usuarios que ya no están en su organización o que no tienen acceso.

Si necesita ayuda con esta opción, vea el [paso 5](identity-use-group-management.md#identity-group-license).

### <a name="how-to-test"></a>Procedimiento de prueba

1. Cree un grupo de seguridad de prueba en Azure AD en el portal Azure y configure la licencia basada en grupos para asignar la licencia Microsoft 365 Enterprise.
2. Cree una cuenta de usuario de prueba en Azure AD y añádala al grupo de seguridad de prueba.
3. Examinar las propiedades de la cuenta de usuario en el centro de administración de Microsoft 365 para asegurarse de que se le asignó la licencia de Microsoft 365 Enterprise.
4. Elimine la cuenta de usuario de prueba del grupo de seguridad de prueba..
5. Examine las propiedades de la cuenta de usuario para asegurarse de que ya no tiene asignada la licencia de Microsoft 365 Enterprise.
6. Elimine el grupo de seguridad de prueba y la cuenta de usuario de prueba.


<a name="crit-identity-access-reviews"></a>
## <a name="optional-access-reviews-configured-and-being-used-to-monitor-access"></a>Opcional: Revisiones de acceso configuradas y en uso para controlar el acceso

Utilizó estos artículos para configurar distintos tipos de revisiones de acceso para supervisar la pertenencia a grupos, el acceso a aplicaciones empresariales y las asignaciones de funciones:

- [Grupos y aplicaciones](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Roles de Azure AD](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Roles de recursos de Azure](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

Si es necesario, el [paso 6](identity-configure-identity-governance.md#identity-access-reviews) puede ayudarle con esta opción.


## <a name="results-and-next-steps"></a>Resultados y siguientes pasos

La infraestructura de identidades en la nube de Microsoft 365 usa autenticación sólida, cuentas de administrador protegidas y administración y acceso simplificado de usuarios.

|||
|:-------|:-----|
|![Fase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| Si sigue las fases de la implementación de un extremo a otro de Microsoft 365 Enterprise, la siguiente fase es [Windows 10 Enterprise](windows10-infrastructure.md). |

