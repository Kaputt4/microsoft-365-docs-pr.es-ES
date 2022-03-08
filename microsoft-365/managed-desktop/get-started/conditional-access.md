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
ms.openlocfilehash: a5ff8a9a662eb442b7a18726463f14e914d4a133
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63317547"
---
# <a name="adjust-settings-after-enrollment"></a>Ajustar la configuración después de la inscripción

Después de completar la inscripción en Microsoft Managed Desktop, es posible que deba ajustarse alguna configuración de administración. Para comprobar y ajustar si es necesario, siga estos pasos:

1. Revise la Microsoft Intune y Azure Active Directory de configuración descritas en la siguiente sección.
2. Si alguno de los elementos se aplica al entorno, realice los ajustes como se describe.
3. Si desea comprobar que todas las configuraciones son correctas, puede volver a ejecutar la herramienta [](https://aka.ms/mmdart) de evaluación de preparación para asegurarse de que nada entre en conflicto con Microsoft Managed Desktop.

> [!NOTE]
> A medida que las operaciones continúen en los meses siguientes, si realiza cambios después de la inscripción en las directivas de Microsoft Intune, Azure Active Directory o Microsoft 365 que afectan al Escritorio administrado de Microsoft, es posible que Microsoft Managed Desktop deje de funcionar correctamente. Para evitar problemas con el servicio, compruebe la configuración específica que se describe en [Corregir](../get-ready/readiness-assessment-fix.md) problemas encontrados por la herramienta de evaluación de preparación antes de cambiar las directivas enumeradas allí. También puede volver a ejecutar la herramienta de evaluación de preparación en cualquier momento.

## <a name="microsoft-intune-settings"></a>Microsoft Intune configuración

| Configuración | Descripción |
| ------ | ------ |
| Perfil de implementación de Autopilot | Si usas alguna directiva de Autopilot, actualiza cada una para excluir el grupo **Modern Workplace Devices -All** Azure AD. <br><br> **Para actualizar las directivas de Autopilot:** <br><br> En **Asignaciones**, en **los grupos** excluidos, seleccione el grupo **Modern Workplace Devices -All** Azure AD que se creó durante la inscripción de Microsoft Managed Desktop. <br><br> Microsoft Managed Desktop también habrá creado un perfil de Autopilot, que tendrá "Modern Workplace" en el nombre (el Perfil de **Piloto automático de Modern Workplace**). Al actualizar sus propios perfiles de Autopilot, asegúrese de  que no excluya el grupo Modern **Workplace Devices -All** Azure AD del perfil de **Modern Workplace Autopilot** creado por Microsoft Managed Desktop. |
| Directivas de acceso condicional | Si crea nuevas directivas de acceso condicional relacionadas con Azure AD, Microsoft Intune o Microsoft 365 Defender para Endpoint después de la inscripción de Microsoft Managed Desktop, excluya el grupo Cuentas de servicio modernas del lugar de **trabajo Azure AD de** ellos. Para obtener más información, vea [Acceso condicional: usuarios y grupos](/azure/active-directory/conditional-access/concept-conditional-access-users-groups). Microsoft Managed Desktop mantiene directivas de acceso condicional independientes para restringir el acceso a estas cuentas. <br><br> **Para revisar la directiva de acceso condicional de Microsoft Managed Desktop (Modern Workplace – Secure Workstation):** <br><br> Vaya a Microsoft Endpoint Manager y vaya a **Acceso condicional en** **Endpoint Security**. No modifique ninguna directiva de Azure AD de acceso condicional creada por Microsoft Managed Desktop que tenga "Modern Workplace" en el nombre. |
| Autenticación multifactor | Si crea nuevos requisitos de autenticación multifactor en las directivas de acceso condicional relacionadas con Azure AD, Intune o Microsoft 365 Defender para Endpoint después de la inscripción de Microsoft Managed Desktop, excluya el grupo Cuentas de servicio modernas del lugar de **trabajo Azure AD de** ellos. Para obtener más información, vea [Acceso condicional: usuarios y grupos](/azure/active-directory/conditional-access/concept-conditional-access-users-groups). Microsoft Managed Desktop mantiene directivas de acceso condicional independientes para restringir el acceso a los miembros de este grupo. <br><br> **Para revisar la directiva de acceso condicional de Microsoft Managed Desktop (Modern Workplace -):** <br><br> Vaya a Microsoft Endpoint Manager y vaya a **Acceso condicional en** **Endpoint Security**.
| Windows 10 de actualización | Para cualquier Windows 10 de anillo de actualización que haya creado, excluya el grupo **Modern Workplace Devices -All** Azure AD de cada directiva. Para obtener más información, vea [Crear y asignar anillos de actualización](/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings). <br><br> Microsoft Managed Desktop también habrá creado algunas directivas de anillo de actualización, todas las cuales tendrán "Modern Workplace" en el nombre. Por ejemplo: <ul><li>Directiva de actualización moderna de workplace [Broad]</li><li>Directiva de actualización moderna de Workplace [Rápido]</li><li>Directiva de actualización moderna de workplace [First]</li><li>Directiva de actualización moderna del lugar de trabajo [Prueba]</li></ul> <br>Cuando actualice sus propias directivas, asegúrese de que  no excluya el grupo **Modern Workplace Devices -All** Azure AD de los que creó Microsoft Managed Desktop. |

## <a name="azure-active-directory-settings"></a>Azure Active Directory configuración

Restablecimiento de contraseñas de autoservicio: si usa el restablecimiento de contraseñas de autoservicio para todos los usuarios, ajuste la asignación para excluir las cuentas de servicio de Escritorio administrado de Microsoft.

**Para ajustar esta asignación:**

1. Crear un grupo Azure AD dinámico para todos los usuarios *excepto las* cuentas de servicio de Escritorio administrado de Microsoft
1. Use ese grupo para la asignación en lugar de "todos los usuarios".

Para ayudarle a buscar y excluir las cuentas de servicio, este es un ejemplo de una consulta dinámica que puede usar:

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

En esta consulta, reemplace por `@TENANT` el nombre de dominio del inquilino.

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar con Microsoft Managed Desktop

1. Acceder al [portal de administrador](access-admin-portal.md).
1. [Agregar y verificar los contactos de administración en el portal de administrador](add-admin-contacts.md).
1. Ajuste la configuración después de la inscripción (en este artículo).
1. Implementar y asignar el [Portal de empresa de Intune](company-portal.md).
1. [Asignar las licencias](assign-licenses.md).
1. [Implementar las aplicaciones](deploy-apps.md).
1. [Preparar dispositivos](prepare-devices.md).
1. Configurar la [experiencia de primera ejecución con el Autopilot y la página de estado de inscripción](esp-first-run.md).
1. [Habilitar las características de soporte técnico para el usuario](enable-support.md).
1. [Preparar a los usuarios para que usen los dispositivos](get-started-devices.md).
1. [Comenzar a usar el control de aplicaciones](get-started-app-control.md).
