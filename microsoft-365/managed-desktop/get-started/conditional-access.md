---
title: Ajustar la configuración después de la inscripción
description: Cómo excluir determinadas cuentas de Microsoft
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e78f0123c909c90ff90be913e8775cc1e5b30313
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777104"
---
# <a name="adjust-settings-after-enrollment"></a>Ajustar la configuración después de la inscripción

Una vez completada la inscripción en el escritorio administrado de Microsoft, debe ajustar la configuración de Microsoft Intune y Azure Active Directory (Azure AD) especificada en este artículo para permitir la administración y mantener la seguridad. Establezca la siguiente configuración para excluir grupos de Azure AD específicos que contengan usuarios y dispositivos de escritorio administrados por Microsoft. Para conocer los pasos para excluir grupos, consulte [acceso condicional: usuarios y grupos](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users).

> [!NOTE]
> Si realiza cambios después de la inscripción a directivas en Microsoft Intune, Azure Active Directory o Microsoft 365, es posible que el escritorio administrado de Microsoft deje de funcionar correctamente. Para evitar problemas con las operaciones de escritorio administradas de Microsoft, Compruebe la configuración específica que se describe en [solucionar problemas encontrados por la herramienta Readiness Assessment antes de](../get-ready/readiness-assessment-fix.md) cambiar las directivas.


## <a name="microsoft-intune-settings"></a>Configuración de Microsoft Intune

- Perfil de implementación de AutoPilot: para los perfiles de AutoPilot creados por los administradores de su empresa, excluya los **dispositivos modernos Workplace-todos los** grupos de Azure ad. Para conocer los pasos, vea [inscribir dispositivos Windows en Intune mediante Windows AutoPilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot). No excluya los **dispositivos modernos Workplace-todos los** grupos de Azure ad de las directivas de implementación creadas por el escritorio administrado por Microsoft que tengan "espacio de trabajo moderno" en el nombre (por ejemplo, **Perfil del área de trabajo autopiloto moderna**). 
- Directivas de acceso condicional: para directivas de acceso condicional creadas por administradores en su empresa, excluya el grupo de Azure AD de las **cuentas de servicio del lugar de trabajo moderno** . Para conocer los pasos, consulte el [acceso condicional: usuarios y grupos](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups). No excluya los **dispositivos del área de trabajo modernos-todos los** grupos de Azure ad de las directivas creadas por el escritorio administrado por Microsoft que tengan "espacio de trabajo moderno" en el nombre (por ejemplo, **estación de trabajo segura de trabajo moderno**).
- Autenticación multifactor: Asegúrese de que las directivas de acceso condicional creadas por los administradores de la compañía que requieren la autenticación multifactor excluyan el grupo de Azure AD de las **cuentas de servicio del lugar de trabajo moderno** . Para obtener más información, consulte [directivas de acceso condicional](../get-ready/readiness-assessment-fix.md#conditional-access-policies) y [acceso condicional: solicitar MFA para todos los usuarios](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).
- Baseline Security: para las directivas de línea base de seguridad creadas por los administradores de su empresa, excluya los **dispositivos modernos Workplace-todos los**  grupos de Azure ad. Para conocer los pasos, consulte [usar líneas de base de seguridad para configurar dispositivos Windows 10 en Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines). No excluya los **dispositivos modernos Workplace-todos los** grupos de Azure ad de las directivas creadas por el escritorio administrado por Microsoft que tengan "espacio de trabajo moderno" en el nombre (por ejemplo, **línea base de seguridad del área de trabajo moderna**).
- Windows 10 Update ring: para las directivas de Windows 10 Update Ring creadas por los administradores en su empresa, excluya los **dispositivos modernos Workplace-todos los**  grupos de Azure ad. Para conocer los pasos, consulte [administrar las actualizaciones de software de Windows 10 en Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure). No excluya los **dispositivos modernos Workplace-todos los** grupos de Azure ad de las directivas creadas por el escritorio administrado por Microsoft que tengan "espacio de trabajo moderno" en el nombre (por ejemplo, la directiva **moderna de actualización del espacio de trabajo** ).


## <a name="azure-active-directory-settings"></a>Configuración de Azure Active Directory

Autoservicio de restablecimiento de contraseña: elija la opción **seleccionado** y seleccione **dispositivos de área de trabajo modernos: todos los grupos de** Azure ad. Para obtener más información, vea [Tutorial: permitir a los usuarios desbloquear su cuenta o restablecer contraseñas con el restablecimiento de contraseña de autoservicio de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar a trabajar con el escritorio administrado de Microsoft

1. [Agregar y verificar los contactos de administración en el portal de administración ](add-admin-contacts.md)
2. Ajustar la configuración después de la inscripción (este artículo)
3. [Asignar licencias](assign-licenses.md)
4. [Desplegar el portal de empresa de Intune](company-portal.md)
5. [Habilitar Enterprise State Roaming](enterprise-state-roaming.md)
6. [Instalar dispositivos](set-up-devices.md)
7. [Prepare a los usuarios para que usen los dispositivos](get-started-devices.md)
8. [Implementar aplicaciones](deploy-apps.md)
