---
title: 'Paso 3: configuración de identidad híbrida'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Conozca las opciones de identidad y configure Azure AD Connect para sincronizar la instancia local de Active Directory Domain Services con Azure AD.
ms.openlocfilehash: 0b494047f984d9fd830e840d2d1f4fafa06fe8ab
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073830"
---
# <a name="step-3-configure-hybrid-identity"></a>Paso 3: configuración de identidad híbrida

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-sync"></a>
## <a name="synchronize-identities"></a>Sincronizar las identidades

*Este paso es obligatorio para los entornos híbridos y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

En esta sección, sincronizará su instancia local de Active Directory Domain Services (AD DS) con el espacio empresarial de Azure Active Directory (Azure AD) que usan sus suscripciones a Office 365 y Enterprise Mobility + Security (EMS).

Azure AD Connect es la herramienta compatible de Microsoft que le guiará durante el proceso de sincronizar solo las identidades que necesita desde entornos de AD DS de bosque único o bosques múltiples a su espacio empresarial de Azure AD. La siguiente figura muestra el proceso básico para la sincronización de Azure AD Connect.

![Cómo sincroniza Azure AD Connect su directorio local con Azure AD](./media/identity-azure-ad-connect/azure-ad-connect.png)

1. Azure AD Connect ejecutado en un servidor busca cambios en las cuentas, grupos y contactos de AD DS.
2. Azure AD Connect envía los cambios al espacio empresarial de Azure AD de su suscripción de Microsoft 365.

La primera decisión en su solución de identidad híbrida es el requisito de autenticación. Las siguientes opciones son:

- Con la **autenticación administrada**, Azure AD controla el proceso de autenticación de inicio de sesión del usuario. Hay dos métodos de autenticación administrada: 
    - **Sincronización de hash de contraseña (PHS)** (recomendado y necesario para algunas características premium). Esta es la forma más sencilla de habilitar la autenticación para los objetos del directorio local en Azure AD. Azure AD Connect extrae la contraseña con hash de AD DS, realiza procesamientos de seguridad adicionales en ella y la guarda en Azure AD. Para obtener más información, vea [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) (Implementación de la sincronización de hash de contraseñas mediante la sincronización de Azure AD Connect).
    - La **autenticación de paso a través (PTA)** proporciona una sencilla solución de validación de contraseñas para servicios basados en Azure AD. PTA usa un agente que se ejecuta en uno o más servidores locales para validar las autenticaciones de usuario directamente con AD DS local. Para obtener más información, vea [User sign-in with Azure Active Directory Pass-through Authentication](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication) (Inicio de sesión de usuario con autenticación de paso a través de Azure Active Directory).
- Con la **autenticación federada**, el proceso de autenticación se redirige a otro proveedor de identidades a través de un servidor de federación de identidades, como Servicios de federación de Active Directory (AD FS), para el inicio de sesión de un usuario. El proveedor de identidades puede proporcionar métodos de autenticación adicionales, como la autenticación basada en tarjeta inteligente. Para obtener más información, vea [Elegir el método de autenticación adecuado para la solución de identidad híbrida de Azure Active Directory](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).

Una vez que haya determinado la solución de identidad híbrida, descargue y ejecute la [IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) (herramienta de corrección de errores de sincronización de directorios IdFix) para analizar los problemas de AD DS.

Después de resolver todos los problemas que haya identificado la herramienta IdFix, vea [Implement password hash synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) (Implementación de sincronización de hash de contraseñas) para obtener instrucciones sobre cómo instalar la herramienta Azure AD Connect y configurar la sincronización de directorios entre la instancia local de AD DS y el espacio empresarial de Azure AD para sus suscripciones a Office 365 y EMS. Después de que se inicie la sincronización, mantendrá sus cuentas de usuario y grupos con su proveedor de identidades local, como AD DS.

Microsoft proporciona un conjunto de recomendaciones para el [acceso a identidades y dispositivos](microsoft-365-policies-configurations.md) para asegurar la seguridad y la productividad de los empleados. 

- Para ver los requisitos recomendados para entornos híbridos, consulte la columna **Active Directory con sincronización de contraseñas hash** en [requisitos previos](identity-access-prerequisites.md#prerequisites). 

- Para ver los requisitos recomendados para entornos de solo nube, consulte la columna **solo nube** en [requisitos previos](identity-access-prerequisites.md#prerequisites).

Una vez que los usuarios y los grupos locales estén en Azure AD, podrá empezar a asignar licencias y usar Exchange Online. Para implementar Exchange Online a los usuarios y migrar los buzones locales, vea [Deploy Exchange Online for Microsoft 365 Enterprise](exchangeonline-workload.md) (Implementación de Exchange Online para Microsoft 365 Enterprise).

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía de laboratorio de pruebas: sincronización de hash de contraseñas](password-hash-sync-m365-ent-test-environment.md)<br> [Guía de laboratorio de pruebas: autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md) |
|||

Como control provisional, puede ver [Fase 2: Criterios de salida de infraestructura de identidades](identity-exit-criteria.md#crit-identity-sync), que corresponde a esta sección.

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a>Supervisión del estado de sincronización

*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*

En esta sección, deberá instalar a un agente de Azure AD Connect Health en cada uno de los servidores de identidad local para supervisar su infraestructura de identidades y los servicios de sincronización proporcionados por Azure AD Connect. En el portal de Azure AD Connect Health podrá consultar la información de supervisión, y se pueden ver alertas, supervisión del rendimiento y análisis de uso, entre otros datos.

![Componentes de Azure AD Connect Health](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

La decisión de diseño clave sobre cómo usar Azure AD Connect Health se basa en la forma en que use Azure AD Connect:

- Si usa la opción de **autenticación administrada**, vea primero [Usar Azure AD Connect Health con sincronización](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) para comprender y configurar Azure AD Connect Health.
- Si solo sincroniza los nombres de las cuentas y los grupos mediante la **autenticación federada** con Servicios de federación de Active Directory (AD FS), empiece con [Usar Azure AD Connect Health con AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) para comprender y configurar Azure AD Connect Health.

Cuando complete este paso, tendrá:

- El agente de Azure AD Connect Health instalado en los servidores de proveedor de identidades locales.
- En el portal de Azure AD Connect Health, se mostrará el estado actual de la infraestructura local y las actividades de sincronización con el espacio empresarial de Azure AD para sus suscripciones de Office 365 y EMS.

Como control provisional, puede ver [Fase 2: Criterios de salida de infraestructura de identidades](identity-exit-criteria.md#crit-identity-sync-health), que corresponde a esta sección.

## <a name="next-step"></a>Siguiente paso

|||
|:-------|:-----|
![](./media/stepnumbers/Step4.png)| [Configuración de autenticación segura de usuario](identity-multi-factor-authentication.md)
