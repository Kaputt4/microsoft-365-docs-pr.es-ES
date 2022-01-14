---
title: Ajustar la configuración después de la inscripción
description: Cómo excluir determinadas cuentas de Microsoft
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: a9d218c40d7aafef7de293381b639515c84439f8
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2022
ms.locfileid: "62034658"
---
# <a name="adjust-settings-after-enrollment"></a>Ajustar la configuración después de la inscripción

Después de completar la inscripción en Microsoft Managed Desktop, es posible que deba ajustarse alguna configuración de administración. Para comprobar y ajustar si es necesario, siga estos pasos:

1. Revise la Microsoft Intune y Azure Active Directory de configuración descritas en la siguiente sección.
2. Si alguno de los elementos se aplica al entorno, realice los ajustes descritos.
3. Si desea comprobar que todas las configuraciones son correctas, puede volver a ejecutar la herramienta de evaluación de preparación para asegurarse de que nada entre en conflicto con el Escritorio administrado de Microsoft. [](https://aka.ms/mmdart)

> [!NOTE]
> A medida que las operaciones continúen en los meses siguientes, si realiza cambios después de la inscripción en directivas de Microsoft Intune, Azure Active Directory o Microsoft 365 que afectan al Escritorio administrado de Microsoft, es posible que Microsoft Managed Desktop deje de funcionar correctamente. Para evitar problemas con el servicio, compruebe la configuración específica que se describe en [Corregir](../get-ready/readiness-assessment-fix.md) problemas encontrados por la herramienta de evaluación de preparación antes de cambiar las directivas enumeradas allí. También puede volver a ejecutar la herramienta de evaluación de preparación en cualquier momento.


## <a name="microsoft-intune-settings"></a>Microsoft Intune configuración

- Perfil de implementación de Autopilot: si usa alguna directiva de Autopilot, actualice cada una de ellas para excluir el grupo Dispositivos modernos de workplace **-All** Azure AD usuario. Para actualizarlos,  en la sección Grupos **excluidos** de Asignaciones, seleccione el grupo Modern **Workplace Devices -All** Azure AD que se creó durante la inscripción de Microsoft Managed Desktop. Microsoft Managed Desktop también habrá creado un perfil de Autopilot, que tendrá "Modern Workplace" en el nombre (el perfil de **Modern Workplace Autopilot**). Cuando actualices tus propios perfiles de  **Autopilot,** asegúrate de no excluir el grupo Modern **Workplace Devices -All** Azure AD del Perfil de Autopilot de Modern Workplace creado por Microsoft Managed Desktop.

- Directivas de acceso condicional: si crea nuevas directivas de acceso condicional relacionadas con Azure AD, Microsoft Intune o Microsoft Defender para Endpoint después de la inscripción de Microsoft Managed Desktop, excluya el grupo Cuentas de servicio modernas del lugar de trabajo **Azure AD** de ellas. Para ver los pasos, [vea Acceso condicional: Usuarios y grupos](/azure/active-directory/conditional-access/concept-conditional-access-users-groups). Microsoft Managed Desktop mantiene directivas de acceso condicional independientes para restringir el acceso a estas cuentas. Para revisar la directiva de acceso condicional de Microsoft Managed Desktop (**Modern Workplace – Secure Workstation**), vaya a Microsoft Endpoint Manager y vaya a Acceso **condicional** en **Endpoint Security**. No modifique ninguna directiva de Azure AD de acceso condicional creada por Microsoft Managed Desktop que tenga "Modern Workplace" en el nombre.

- Autenticación multifactor: si crea nuevos requisitos de autenticación multifactor en las directivas de acceso condicional relacionadas con Azure AD, Intune o Microsoft Defender para Endpoint después de la inscripción de Microsoft Managed Desktop, excluya el grupo Cuentas de servicio modernas del lugar de trabajo **Azure AD** de ellos. Para ver los pasos, [vea Acceso condicional: Usuarios y grupos](/azure/active-directory/conditional-access/concept-conditional-access-users-groups). Microsoft Managed Desktop mantiene directivas de acceso condicional independientes para restringir el acceso a los miembros de este grupo. Para revisar la directiva de acceso condicional de Microsoft Managed Desktop (**Modern Workplace -**), vaya a Microsoft Endpoint Manager y vaya a Acceso **condicional** en **Endpoint Security**. 

- Windows 10 anillo de actualización: para cualquier Windows 10 de anillo de actualización que haya creado, excluya el grupo **Modern Workplace Devices -All** Azure AD de cada directiva. Para ver los pasos, [vea Crear y asignar anillos de actualización.](/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings) Microsoft Managed Desktop también habrá creado algunas directivas de anillo de actualización, todas las cuales tendrán "Modern Workplace" en el nombre (por ejemplo, Modern Workplace **Update Policy [Broad]**, **Modern Workplace Update Policy [Fast]**, **Modern Workplace Update Policy [First]** y **Modern Workplace Update Policy [Test]**). Al actualizar sus propias directivas,  asegúrese de no excluir el grupo **Modern Workplace Devices -All** Azure AD de los que creó Microsoft Managed Desktop.


## <a name="azure-active-directory-settings"></a>Azure Active Directory configuración

Restablecimiento de contraseñas de autoservicio: si usa el restablecimiento de contraseñas de autoservicio para todos los usuarios, ajuste la asignación para excluir las cuentas de servicio de Escritorio administrado de Microsoft. Para ajustar esta asignación, cree un grupo dinámico Azure AD todos los usuarios excepto las cuentas de servicio de *Escritorio* administrado de Microsoft y, a continuación, use ese grupo para la asignación en lugar de "todos los usuarios".

Para ayudarle a buscar y excluir las cuentas de servicio, este es un ejemplo de una consulta dinámica que puede usar:

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

En esta consulta, reemplace @TENANT por el nombre de dominio del espacio empresarial.



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar con Microsoft Managed Desktop

1. Acceder al [portal de administrador](access-admin-portal.md).
1. [Agregar y verificar los contactos de administración en el portal de administrador](add-admin-contacts.md).
1. Ajuste la configuración después de la inscripción (en este artículo).
1. Implementar y asignar el [Portal de empresa de Intune](company-portal.md).
1. [Asignar las licencias](assign-licenses.md).
1. [Implementar las aplicaciones](deploy-apps.md).
1. [Configurar los dispositivos](set-up-devices.md).
1. Configurar la [experiencia de primera ejecución con el Autopilot y la página de estado de inscripción](esp-first-run.md).
1. [Habilitar las características de soporte técnico para el usuario](enable-support.md).
1. [Preparar a los usuarios para que usen los dispositivos](get-started-devices.md).
1. [Comenzar a usar el control de aplicaciones](get-started-app-control.md).