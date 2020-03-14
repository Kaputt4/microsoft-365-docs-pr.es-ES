---
title: 'Paso 4: Agregar las cuentas de usuario'
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
description: Agregue cuentas de usuario y grupos directamente en la nube o a través de la sincronización con el directorio local.
ms.openlocfilehash: 324d4662f868a4a92693b43c6bc0f75c11f20519
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633108"
---
# <a name="step-4-add-your-user-accounts"></a>Paso 4: Agregar las cuentas de usuario

![Fase 2-Identidad](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-cloud-only"></a>
## <a name="create-your-user-accounts-for-cloud-only-identity"></a>Crear cuentas de usuario para identidades solo de nube

Para la identidad solo de nube, cree los usuarios y grupos en Azure Active Directory (Azure AD). Puede utilizar:

- Centro de administración de Microsoft 365
- Microsoft Azure Portal
- Azure PowerShell

<a name="identity-sync"></a>
## <a name="synchronize-identities-for-hybrid-identity"></a>Sincronizar identidades para identidades híbridas

*Este paso es obligatorio para los entornos híbridos y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

En esta sección, sincronizará su instancia local de Active Directory Domain Services (AD DS) con el espacio empresarial de Azure AD que usan sus suscripciones a Office 365, Microsoft Intune y otros servicios basados en la nube incluidos con Microsoft 365 Enterprise.

Azure AD Connect es la herramienta compatible de Microsoft que le guiará durante el proceso de sincronizar solo las identidades que necesita desde entornos de AD DS de bosque único o bosques múltiples a su espacio empresarial de Azure AD. La siguiente figura muestra el proceso básico para la sincronización de Azure AD Connect.

![Cómo sincroniza Azure AD Connect su directorio local con Azure AD](../media/identity-add-user-accounts/azure-ad-connect.png)

1. Azure AD Connect ejecutado en un servidor busca cambios en las cuentas, grupos y contactos de AD DS.
2. Azure AD Connect envía los cambios al espacio empresarial de Azure AD de su suscripción de Microsoft 365.

La primera decisión en su solución de identidad híbrida es el requisito de autenticación. Las siguientes opciones son:

- Con la **autenticación administrada**, Azure AD controla el proceso de autenticación de inicio de sesión del usuario. Hay dos métodos de autenticación administrada: 
    - **Sincronización de hash de contraseña (PHS)** (recomendado y necesario para algunas características premium). Esta es la forma más sencilla de habilitar la autenticación para los objetos del directorio local en Azure AD. Azure AD Connect extrae la contraseña con hash de AD DS, realiza procesamientos de seguridad adicionales en el hash de contraseña y la sincroniza con Azure AD. Para obtener más información, vea [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) (Implementación de la sincronización de hash de contraseñas mediante la sincronización de Azure AD Connect).
    - La **autenticación de paso a través (PTA)** proporciona una sencilla solución de validación de contraseñas para servicios basados en Azure AD. PTA usa un agente que se ejecuta en uno o más servidores locales para validar las autenticaciones de usuario directamente con AD DS local. Para obtener más información, vea [User sign-in with Azure Active Directory Pass-through Authentication](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication) (Inicio de sesión de usuario con autenticación de paso a través de Azure Active Directory).
- Con la **autenticación federada**, el proceso de autenticación se redirige a otro proveedor de identidades a través de un servidor de federación de identidades, como Servicios de federación de Active Directory (AD FS), para el inicio de sesión de un usuario. El proveedor de identidades puede proporcionar métodos de autenticación adicionales, como la autenticación basada en tarjeta inteligente. Para obtener más información, vea [Elegir el método de autenticación adecuado para la solución de identidad híbrida de Azure Active Directory](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).

Vea este vídeo para obtener una introducción a los modelos de identidad y autenticación de Microsoft 365 Enterprise.

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

Una vez que haya determinado la solución de identidad híbrida, descargue y ejecute la [IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) (herramienta de corrección de errores de sincronización de directorios IdFix) para analizar los problemas de AD DS.

Después de resolver todos los problemas que haya identificado la herramienta IdFix, vea [Implement password hash synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) (Implementación de sincronización de hash de contraseñas) para obtener instrucciones sobre cómo instalar la herramienta Azure AD Connect y configurar la sincronización de directorios entre la instancia local de AD DS y el espacio empresarial de Azure AD para sus suscripciones a Microsoft 365. Después de que se inicie la sincronización, mantendrá sus cuentas de usuario y grupos con su proveedor de identidades local, como AD DS.

Microsoft proporciona un conjunto de recomendaciones para el [acceso a identidades y dispositivos](microsoft-365-policies-configurations.md) para asegurar la seguridad y la productividad de los empleados. 

- Para ver los requisitos recomendados para entornos híbridos, consulte la columna **Active Directory con sincronización de contraseñas hash** en [requisitos previos](identity-access-prerequisites.md#prerequisites). 

- Para ver los requisitos recomendados para entornos de solo nube, consulte la columna **solo nube** en [requisitos previos](identity-access-prerequisites.md#prerequisites).

Una vez que existan usuarios y grupos locales en Azure AD, podrá empezar a asignar licencias y usar cargas de trabajo de productividad como OneDrive para la Empresa y Exchange Online.

|||
|:-------|:-----|
|![Guías del entorno de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía de laboratorio de pruebas: sincronización de hash de contraseñas](password-hash-sync-m365-ent-test-environment.md)<br> [Guía de laboratorio de pruebas: autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md) |
|||

Como control provisional, puede ver [Fase 2: Criterios de salida de infraestructura de identidades](identity-exit-criteria.md#crit-identity-sync), que corresponde a esta sección.

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a>Supervisión del estado de sincronización

*Este paso es opcional y se aplica a las versiones E3 y E5 de Microsoft 365*

En esta sección, deberá instalar a un agente de Azure AD Connect Health en cada uno de los controladores de dominio AD DS locales para supervisar su infraestructura de identidades y los servicios de sincronización proporcionados por Azure AD Connect. En el portal de Azure AD Connect Health podrá consultar la información de supervisión, y se pueden ver alertas, supervisión del rendimiento y análisis de uso, entre otros datos.

![Componentes de Azure AD Connect Health](../media/identity-add-user-accounts/identity-azure-ad-connect-health.png)

La decisión de diseño clave sobre cómo usar Azure AD Connect Health se basa en la forma en que use Azure AD Connect:

- Si usa la opción de **autenticación administrada**, vea primero [Usar Azure AD Connect Health con sincronización](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) para comprender y configurar Azure AD Connect Health.
- Si solo sincroniza los nombres de las cuentas y los grupos mediante la **autenticación federada** con Servicios de federación de Active Directory (AD FS), empiece con [Usar Azure AD Connect Health con AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) para comprender y configurar Azure AD Connect Health.

Cuando complete este paso, tendrá:

- El agente de Azure AD Connect Health instalado en los servidores de proveedor de identidades locales.
- En el portal de Azure AD Connect Health, se mostrará el estado actual de la infraestructura local y las actividades de sincronización con el espacio empresarial de Azure AD para su suscripción de Microsoft 365.

Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-sync-health) correspondientes a esta sección.



<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a>Simplificación de actualizaciones de contraseña

*Esta función es opcional para los entornos híbridos y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

En esta sección, permitirá a los usuarios restablecer sus contraseñas a través de Azure Active Directory (Azure AD), que se replicarán en el Active Directory Domain Services (AD DS) local. Este proceso se conoce como reescritura de contraseña. Con la escritura diferida de contraseñas, los usuarios no necesitan actualizar las contraseñas mediante AD DS local donde se almacenan las cuentas de usuario y sus atributos. Esto resulta útil para los usuarios móviles o remotos que no disponen de una conexión de acceso remoto a la red local.

La escritura diferida de contraseñas es necesaria para utilizar por completo las capacidades de Azure AD Identity Protection, como solicitar a los usuarios que cambien sus contraseñas locales cuando se haya detectado un alto riesgo de que la cuenta se haya visto comprometida.

Para obtener más información e instrucciones de configuración, vea [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback) (SSPR de Azure AD con escritura diferida de contraseñas).

>[!Note]
>Actualice a la última versión de Azure AD Connect para garantizar que tiene la mejor experiencia posible y nuevas características cuando se publican. Para obtener más información, vea [Instalación personalizada de Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía del entorno de pruebas: reescritura de contraseñas](password-writeback-m365-ent-test-environment.md) |
|||

Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-pw-writeback) correspondientes a esta sección.

|||
|:-------|:-----|
|![Paso 5](../media/stepnumbers/Step5.png)| [Use grupos para administración](identity-use-group-management.md) |
