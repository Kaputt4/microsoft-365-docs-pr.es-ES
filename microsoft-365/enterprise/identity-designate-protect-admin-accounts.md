---
title: 'Paso 2: Proteger las cuentas de administrador global'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure las cuentas de administrador para obtener la protección máxima.
ms.openlocfilehash: ccab7c8526817ee5140a5315c56f6f8a42f085d2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871796"
---
# <a name="step-2-protect-global-administrator-accounts"></a>Paso 2: Proteger las cuentas de administrador global

*Este paso es obligatorio y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

En este paso, contribuirá a impedir ataques digitales en su organización al comprobar que las cuentas de administrador sean lo más seguras posible. Para hacerlo, necesita:

- Crear cuentas de administrador global dedicadas con [contraseñas muy seguras](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) y usarlas solo cuando sea necesario.
- Realice tareas de administración cotidianas al asignar roles de administrador específicos (como administrador de Exchange o administrador de contraseñas) a cuentas de usuario o personal de TI, según sea necesario.

Para las cuentas de administrador global dedicadas, también necesita:

1. Probar la configuración de autenticación multifactor (MFA) por cuenta de usuario o basado en el acceso condicional en una cuenta de usuario de prueba para garantizar que MFA funciona correctamente y de forma predecible. MFA exige una forma de autenticación secundaria, como un código de verificación enviado a un smartphone.
2. Configure MFA para todas las cuentas de administrador global de Office 365 dedicadas y use la forma más segura de autenticación secundaria disponible en su organización. Para obtener más información, vea [Autenticación multifactor](identity-multi-factor-authentication.md).
2. Use una directiva de acceso condicional para exigir el uso de MFA en las cuentas de administrador global. Para obtener más información, vea [Proteger las cuentas de administrador](identity-access-prerequisites.md#protecting-administrator-accounts).
4. Use una directiva de Office 365 Cloud App Security para supervisar la actividad de las cuentas de administrador global. Para obtener más información, vea [Configurar una mayor seguridad para Office 365](infoprotect-configure-increased-security-office-365.md).

Para obtener más información sobre la configuración, vea [Proteger las cuentas de administrador global de Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts).

> [!Note]
> Las organizaciones tienen que usar identidades solo de nube con el fin de crear cuentas con privilegios (como administradores globales) para escenarios de acción rápida en emergencias, como un ciberataque. Para obtener más información, vea [Administrar cuentas administrativas de acceso de emergencias en Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).

Los resultados de este paso son:

- Las únicas cuentas de usuario de la suscripción que tienen el rol de administrador global son las que pertenecen al nuevo conjunto de cuentas de administrador global dedicadas. Compruebe esto con el siguiente comando de PowerShell de Microsoft Azure AD V2: 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- El resto de las cuentas de usuario habituales que administran la suscripción tienen asignados roles de administrador que están asociados con las funciones del puesto.

> [!Note]
> Para obtener instrucciones sobre cómo instalar el módulo de PowerShell de Azure AD V2 e iniciar sesión, vea [Conectarse a PowerShell de Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas en Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía de laboratorio de pruebas: Proteger las cuentas de administrador global](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

Como punto de control provisional, puede ver los [criterios de salida](identity-exit-criteria.md#crit-identity-global-admin) de este paso.

## <a name="next-step"></a>Paso siguiente

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [Configurar los administradores globales a petición](identity-privileged-identity-management.md) |

