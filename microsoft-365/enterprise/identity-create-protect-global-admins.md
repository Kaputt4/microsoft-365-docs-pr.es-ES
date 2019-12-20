---
title: 'Paso 1: crea y proteja sus cuentas de administrador global'
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
description: Las cuentas de administrador global necesitan un tratamiento especial para proteger la integridad de sus credenciales.
ms.openlocfilehash: 1a0274967798e6c2ba6048e5a2cfd70e73cb0671
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801835"
---
# <a name="step-1-create-and-protect-your-global-admin-accounts"></a>Paso 1: crea y proteja sus cuentas de administrador global

![Fase 2-Identidad](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a>Proteger las cuentas de administrador globales

*Esto es obligatorio y se aplica a las versiones de los E3 y E5 de Microsoft 365 Enterprise*

En esta sección, ayudará a evitar ataques digitales en su organización, asegurándose de que sus cuentas de administrador sean lo más seguras posible. Para ello, debe:

- Cree más de una cuenta de administrador global dedicada con [contraseñas seguras](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) y úselas solo cuando sea necesario.
- Realice tareas de administración cotidianas al asignar roles de administrador específicos (como administrador de Exchange o administrador de contraseñas) a otras cuentas dedicadas para esos roles o cuentas de usuario o personal de TI, según sea necesario.

Para las cuentas de administrador global dedicadas, también necesita:

1. Probar la configuración de Azure Multi-Factor Authentication (MFA) por cuenta de usuario o basado en el acceso condicional en una cuenta de usuario de prueba para garantizar que MFA funciona correctamente y de forma predecible. La MFA obliga al uso de una forma de autenticación secundaria, como un código de comprobación enviado a un smartphone.
2. Cree y habilite directivas de acceso condicional para las cuentas de administrador global y use la forma más segura de autenticación secundaria disponible en la organización. Consulte [Azure Multi-Factor Authentication](identity-access-prerequisites.md#protecting-administrator-accounts) para obtener más información.

Para obtener protección adicional, consulte [Proteger las cuentas de administrador global de Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations).

> [!Note]
> Las cuentas de emergencia para casos urgentes, como un ciberataque, deben basarse exclusivamente en la nube. Sí es posible tener cuentas de administrador global (aptas o permanentes) que no sean solo de la nube. Para más información, consulte [Administración de cuentas administrativas de acceso de emergencia en Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).

Los resultados de esta sección son:

- Las únicas cuentas de usuario de su suscripción que tienen el rol de administrador global son las cuentas de administrador global dedicadas. Para comprobarlo, use el siguiente comando de Active Directory de Azure PowerShell para Graph: 
  ```powershell
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- El resto de cuentas de usuario que administran los servicios de suscripción tienen asignados roles de administrador que están asociados con las funciones del puesto.

> [!Note]
> Vea [Conectarse a PowerShell de Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) para recibir instrucciones sobre la instalación del módulo Azure Active Directory PowerShell para Graph e iniciar sesión.

|||
|:-------|:-----|
|![Guías del entorno de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Para poner en práctica esta configuración en un entorno de prueba, consulte la [Guía de entorno de pruebas para proteger cuentas de administrador global](protect-global-administrator-accounts-microsoft-365-test-environment.md). |
|||

Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-global-admin) correspondientes a esta sección.


<a name="identity-pim"></a>
## <a name="set-up-on-demand-administrators"></a>Configure administradores a petición

*Esto es opcional y solo se aplica a la versión E5 de Microsoft 365 Enterprise*

En esta sección, configurará Azure AD Privileged Identity Management (PIM) para reducir la cantidad de tiempo en el que sus cuentas de administrador son vulnerables a ataques malintencionados. PIM proporciona una tarea a petición y just-in-time del rol de administrador cuando sea necesario.  

Sus cuentas de administrador pasan de ser administradores permanentes a ser administradores aptos. El rol de administrador permanece inactivo hasta que lo necesite. Luego completará un proceso de activación para agregar el rol de administrador a la cuenta de administrador durante un período de tiempo determinado. Cuando la hora expire, PIM quita el rol de administrador de la cuenta de administrador.

PIM está disponible con Azure Active Directory Premium P2, que se incluye con Microsoft 365 E5. Como alternativa, puede comprar licencias individuales de Azure Active Directory Premium P2 para las cuentas de administrador.

Para habilitar Azure PIM para su espacio empresarial de Azure AD y sus cuentas de administrador, vea los [pasos para configurar PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

Para desarrollar un plan completo a fin de proteger el acceso con privilegios frente a los ciberatacantes, vea [Protección del acceso con privilegios para las implementaciones híbridas y en la nube en Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-pim) correspondientes a esta sección.


<a name="identity-pam"></a>
## <a name="privileged-access-management"></a>Privileged Access Management

La administración del acceso con privilegios se habilita configurando directivas que especifiquen el acceso puntual para actividades basadas en tareas en el inquilino de Office 365. Permite proteger la organización ante infracciones que puedan usar las cuentas existentes de administrador con privilegios y acceso permanente para acceder a datos confidenciales o acceder a opciones de configuración críticas. Por ejemplo, puede configurar una directiva de administración del acceso con privilegios que requiera una autorización explícita para acceder a la configuración del buzón de correo del inquilino de Office 365 y modificar la misma.

En este paso, habilitará la administración del acceso con privilegios en el inquilino de Office 365 y configurará directivas de acceso con privilegios que proporcionen seguridad adicional para el acceso basado en tareas a los datos y las opciones de configuración de Office 365 de la organización. Para empezar con el acceso con privilegios en la organización de Office 365, debe seguir estos tres pasos básicos:

- Crear un grupo de aprobadores
- Habilitar el acceso con privilegios
- Crear directivas de aprobación

Una vez configurada, la administración del acceso con privilegios permitirá a la organización trabajar sin privilegios permanentes y proporcionará un nivel de defensa contra las vulnerabilidades derivadas de dicho acceso administrativo. El acceso con privilegios requiere aprobaciones para ejecutar cualquier tarea a la que se haya asociado una directiva definida de aprobación. Los usuarios que necesiten ejecutar tareas incluidas en la directiva de aprobación deberán solicitar y obtener la aprobación de acceso para tener los permisos necesarios para ejecutar las tareas definidas en la directiva.

Para habilitar la administración del acceso con privilegios de Office 365, vea el tema [Configurar la administración del acceso con privilegios en Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).

Para obtener más información, vea el tema [Administración del acceso con privilegios en Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).


|||
|:-------|:-----|
|![Guías del entorno de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Para poner en práctica esta configuración en un entorno de prueba, consulte [Guía de gestión de acceso privilegiado en un entorno de pruebas](privileged-access-microsoft-365-enterprise-dev-test-environment.md). |
|||

Como punto de control provisional, vea los [criterios de salida](identity-exit-criteria.md#crit-identity-pam) correspondientes a este paso.

## <a name="next-step"></a>Siguiente paso

|||
|:-------|:-----|
|![Paso 2](./media/stepnumbers/Step2.png)| [Proteja sus contraseñas](identity-secure-your-passwords.md) |

