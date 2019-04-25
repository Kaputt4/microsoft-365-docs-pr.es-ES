---
title: 'Paso 2: Proteger las identidades con privilegios'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure las cuentas de administrador para obtener la protección máxima.
ms.openlocfilehash: 4b4a8d01cdf71e30139fa448813a3ff7c43855c7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285168"
---
# <a name="step-2-secure-your-privileged-identities"></a>Paso 2: Proteger las identidades con privilegios

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a>Proteger las cuentas de administrador globales

*Esto es obligatorio y se aplica a las versiones de los E3 y E5 de Microsoft 365 Enterprise*

En esta sección, ayudará a evitar ataques digitales en su organización, asegurándose de que sus cuentas de administrador sean lo más seguras posible. Para ello, debe:

- Crear cuentas de administrador global dedicadas con [contraseñas muy seguras](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) y usarlas solo cuando sea necesario.
- Realice tareas de administración cotidianas al asignar roles de administrador específicos (como administrador de Exchange o administrador de contraseñas) a cuentas de usuario o personal de TI, según sea necesario.

Para las cuentas de administrador global dedicadas, también necesita:

1. Probar la configuración de autenticación multifactor (MFA) por cuenta de usuario o basado en el acceso condicional en una cuenta de usuario de prueba para garantizar que MFA funciona correctamente y de forma predecible. MFA exige una forma de autenticación secundaria, como un código de verificación enviado a un smartphone.
2. Configure MFA para todas las cuentas de administrador global de Office 365 dedicadas y use la forma más segura de autenticación secundaria disponible en su organización. Para obtener más información, vea [Autenticación multifactor](identity-multi-factor-authentication.md#identity-mfa).
2. Use una directiva de acceso condicional para exigir el uso de MFA en las cuentas de administrador global. Para obtener más información, vea [Proteger las cuentas de administrador](identity-access-prerequisites.md#protecting-administrator-accounts).
4. Use una directiva de Office 365 Cloud App Security para supervisar la actividad de las cuentas de administrador global. Para obtener más información, vea [Configurar una mayor seguridad para Office 365](infoprotect-configure-increased-security-office-365.md).

Para obtener más información sobre la configuración, vea [Proteger las cuentas de administrador global de Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts).

> [!Note]
> Las organizaciones tienen que usar identidades solo de nube con el fin de crear cuentas con privilegios (como administradores globales) para escenarios de acción rápida en emergencias, como un ciberataque. Para obtener más información, vea [Administrar cuentas administrativas de acceso de emergencias en Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).

Los resultados de esta sección son:

- Las únicas cuentas de usuario de su suscripción que tienen el rol de administrador global son aquellas pertenecientes al nuevo conjunto de cuentas de administrador global dedicadas. Para comprobarlo, use el siguiente comando de Active Directory de Azure PowerShell para Graph: 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- El resto de las cuentas de usuario habituales que administran la suscripción tienen asignados roles de administrador que están asociados con las funciones del puesto.

> [!Note]
> Vea [Conectarse a PowerShell de Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) para recibir instrucciones sobre la instalación del módulo Azure Active Directory PowerShell para Graph e iniciar sesión.

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía de laboratorio de pruebas: Proteger las cuentas de administrador global](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

Como control provisional, puede ver el [criterio de salida](identity-exit-criteria.md#crit-identity-global-admin) de esta sección.


<a name="identity-pim"></a>
## <a name="set-up-on-demand-global-administrators"></a>Configurar los administradores globales a petición

*Esto es opcional y solo se aplica a la versión E5 de Microsoft 365 Enterprise*

En esta sección, configurará la administración de identidades con privilegios de Azure AD (PIM) para reducir la cantidad de tiempo en el que sus cuentas de administrador global son vulnerables a ataques malintencionados. PIM proporciona una tarea a petición y just-in-time del rol de administrador global cuando sea necesario.  

En lugar de convertir sus cuentas de administrador global en un administrador permanente, se convierten en administradores válidos. El rol de administrador global está inactivo hasta que alguien lo necesita. Después, deberá completar un proceso de activación para agregar el rol de administrador global a la cuenta de administrador global durante un período de tiempo concreto. Cuando expira el tiempo, PIM quita el rol de administrador global de la cuenta de administrador global.

PIM está disponible con Azure Active Directory Premium P2, que se incluye con Microsoft 365 Enterprise E5. También puede comprar licencias individuales de Azure Active Directory Premium P2 para sus cuentas de administrador global.

Para habilitar Azure PIM para su espacio empresarial de Azure AD y sus cuentas de administrador global, vea los [pasos para configurar PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

Para desarrollar un plan completo a fin de proteger el acceso con privilegios frente a los ciberatacantes, vea [Protección del acceso con privilegios para las implementaciones híbridas y en la nube en Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

Como control provisional, puede ver el [criterio de salida](identity-exit-criteria.md#crit-identity-pim) de esta sección.


## <a name="next-step"></a>Paso siguiente

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [Configurar identidad híbrida](identity-azure-ad-connect.md) |

