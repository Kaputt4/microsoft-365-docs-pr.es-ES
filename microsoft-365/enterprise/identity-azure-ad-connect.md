---
title: 'Paso 7: Sincronizar las identidades'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/09/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda las opciones de identidad y configure Azure AD Connect para sincronizar la instancia local de Windows Server AD con Azure AD.
ms.openlocfilehash: 2391ee11a1706bbbfdeb248c5967822d3ea68f72
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871233"
---
# <a name="step-7-synchronize-identities"></a>Paso 7: Sincronizar las identidades

*Este paso es obligatorio para los entornos híbridos y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

En este paso, sincronizará su instancia local de Windows Server Active Directory (AD) con el espacio empresarial de Azure Active Directory (AD) que usan sus suscripciones a Office 365 y Enterprise Mobility + Security (EMS).

Azure AD Connect es la herramienta compatible de Microsoft que le guiará por el proceso de sincronizar solo las identidades que necesita desde entornos de Windows Server AD de bosque único o bosques múltiples a su espacio empresarial de Azure AD.

![Cómo sincroniza Azure AD Connect su directorio local con Azure AD](./media/identity-azure-ad-connect/azure-ad-connect.png)

*Cómo sincroniza Azure AD Connect su directorio local con Azure AD*

La primera decisión en su solución de identidad híbrida es el requisito de autenticación. Las siguientes opciones son:

- Con la **autenticación administrada**, Azure AD controla el proceso de autenticación de inicio de sesión del usuario. Hay dos métodos de autenticación administrada: 
    - **Sincronización de hash de contraseñas (PHS)** [recomendado y obligatorio para algunas características premium]. Esta es la forma más sencilla de habilitar la autenticación para objetos del directorio local en Azure AD. Azure AD Connect extrae la contraseña con hash de Windows Server AD, aplica un procesamiento de seguridad adicional en la contraseña y la guarda en Azure AD. Para obtener más información, vea [Implementación de la sincronización de hash de contraseñas con la sincronización de Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).
    - La **autenticación de paso a través (PTA)** proporciona una solución de validación de contraseña simple para los servicios basados en Azure AD. PTA usa un agente que se ejecuta en uno o varios servidores locales para validar las autenticaciones de los usuarios directamente con su instancia local de Windows Server AD. Para obtener más información, vea [Inicio de sesión del usuario con la autenticación de paso a través de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).
- Con la **autenticación federada**, el proceso de autenticación se redirige a otro proveedor de identidades a través de un servidor de federación de identidades, como Servicios de federación de Active Directory (AD FS), para el inicio de sesión de un usuario. El proveedor de identidades puede proporcionar métodos de autenticación adicionales, como la autenticación basada en tarjeta inteligente. Para obtener más información, vea [Elegir el método de autenticación adecuado para la solución de identidad híbrida de Azure Active Directory](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).

Una vez que haya determinado la solución de identidad híbrida, descargue y ejecute la [herramienta de corrección de errores de DirSync IdFix](https://www.microsoft.com/download/details.aspx?id=36832) para analizar los problemas de Windows Server AD.

Después de resolver todos los problemas que haya identificado la herramienta IdFix, vea [Implementar la sincronización de hash de contraseñas](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) para obtener instrucciones sobre cómo instalar la herramienta Azure AD Connect y configurar la sincronización de directorios entre la instancia local de Windows Server AD y el espacio empresarial de Azure AD para sus suscripciones a Office 365 y EMS. Después de que se inicie la sincronización, mantendrá sus cuentas de usuario y grupos con su proveedor de identidades local, como Windows Server AD.

Microsoft proporciona un conjunto de recomendaciones para el [acceso a identidades y dispositivos](microsoft-365-policies-configurations.md) para asegurar la seguridad y la productividad de los empleados. 
- Para ver los requisitos recomendados para entornos híbridos, consulte la columna **Active Directory con sincronización de contraseñas hash** en [requisitos previos](identity-access-prerequisites.md#prerequisites). 

- Para ver los requisitos recomendados para entornos de solo nube, consulte la columna **solo nube** en [requisitos previos](identity-access-prerequisites.md#prerequisites).

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía de laboratorio de pruebas: sincronización de hash de contraseñas](password-hash-sync-m365-ent-test-environment.md)<br> [Guía de laboratorio de pruebas: autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md) |
|||

Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-sync) correspondientes a este paso.

## <a name="next-step"></a>Siguiente paso

|||
|:-------|:-----|
|![](./media/stepnumbers/Step8.png)| [Supervisar el estado de sincronización](identity-azure-ad-connect-health.md) |

