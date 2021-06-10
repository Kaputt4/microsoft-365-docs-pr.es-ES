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
ms.openlocfilehash: 760fcb94ec6d84a55fe4b8c3cb3540ae29994ae3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918447"
---
# <a name="adjust-settings-after-enrollment"></a>Ajustar la configuración después de la inscripción

Después de completar la inscripción en Escritorio administrado de Microsoft, es posible que deba ajustarse alguna configuración de administración. Para comprobar y ajustar si es necesario, siga estos pasos:

1. Revise la Microsoft Intune y Azure Active Directory de configuración descritas en la siguiente sección.
2. Si alguno de los elementos se aplica al entorno, realice los ajustes descritos.
3. Si desea comprobar que todas las configuraciones son correctas, puede volver a ejecutar la herramienta de evaluación de preparación para asegurarse de que nada entre en conflicto con Escritorio administrado de Microsoft. [](https://aka.ms/mmdart)

> [!NOTE]
> A medida que las operaciones continúan en los meses siguientes, si realiza cambios después de la inscripción en directivas de Microsoft Intune, Azure Active Directory o Microsoft 365 que afectan a Escritorio administrado de Microsoft, es posible que Escritorio administrado de Microsoft pueda dejar de funcionar correctamente. Para evitar problemas con el servicio, compruebe la configuración específica que se describe en [Corregir](../get-ready/readiness-assessment-fix.md) problemas encontrados por la herramienta de evaluación de preparación antes de cambiar las directivas enumeradas allí. También puede volver a ejecutar la herramienta de evaluación de preparación en cualquier momento.


## <a name="microsoft-intune-settings"></a>Microsoft Intune configuración

- Perfil de implementación de Autopilot: si usa alguna directiva de Autopilot, actualice cada una para excluir el grupo **Modern Workplace Devices -All** Azure AD. Para actualizarlos,  en la sección Grupos **excluidos** de Asignaciones, seleccione el grupo **Modern Workplace Devices -All** Azure AD que se creó durante Escritorio administrado de Microsoft inscripción. Escritorio administrado de Microsoft también habrá creado un perfil de Autopilot, que tendrá "Modern Workplace" en el nombre (el Perfil de **Autopilot de Modern Workplace**). Cuando actualice sus propios perfiles de  **Autopilot,** asegúrese de que no excluye el grupo **Modern Workplace Devices -All** Azure AD del Perfil de Autopilot de Modern Workplace creado por Escritorio administrado de Microsoft.

- Directivas de acceso condicional: si crea nuevas directivas de acceso condicional relacionadas con Azure AD, Microsoft Intune o Microsoft Defender para endpoint después de la inscripción Escritorio administrado de Microsoft, excluya el grupo cuentas de **servicio** de trabajo modernas de Azure AD de ellas. Para ver los pasos, [vea Acceso condicional: Usuarios y grupos](/azure/active-directory/conditional-access/concept-conditional-access-users-groups). Escritorio administrado de Microsoft mantiene directivas de acceso condicional independientes para restringir el acceso a estas cuentas. Para revisar la directiva Escritorio administrado de Microsoft de acceso condicional (**Modern Workplace – Secure Workstation**), vaya a Microsoft Endpoint Manager y vaya a **Acceso** condicional en **Endpoint Security**. No modifique ninguna directiva de acceso condicional de Azure AD creada por Escritorio administrado de Microsoft que tengan "Modern Workplace" en el nombre.

- Autenticación multifactor: si crea nuevos requisitos de autenticación multifactor en directivas de acceso condicional relacionadas con Azure AD, Intune o Microsoft Defender para Endpoint después de una inscripción Escritorio administrado de Microsoft, excluya el grupo cuentas de servicio de **trabajo** modernas de Azure AD. Para ver los pasos, [vea Acceso condicional: Usuarios y grupos](/azure/active-directory/conditional-access/concept-conditional-access-users-groups). Escritorio administrado de Microsoft mantiene directivas de acceso condicional independientes para restringir el acceso a los miembros de este grupo. Para revisar la directiva Escritorio administrado de Microsoft de acceso condicional (**Modern Workplace -**), vaya a Microsoft Endpoint Manager y vaya a Acceso **condicional** en **Endpoint Security**. 

- Windows 10 de actualización: para cualquier directiva de anillo de actualización Windows 10 que haya creado, excluya el grupo Dispositivos modernos de Workplace **-Todos** los grupos de Azure AD de cada directiva. Para ver los pasos, [vea Crear y asignar anillos de actualización.](/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings) Escritorio administrado de Microsoft también habrá creado algunas directivas de anillo de actualización, todas las cuales tendrán "Modern Workplace" en el nombre (por ejemplo, Modern Workplace **Update Policy [Broad]**, **Modern Workplace Update Policy [Fast]**, **Modern Workplace Update Policy [First]** y **Modern Workplace Update Policy [Test]**). Cuando actualice sus propias directivas,  asegúrese de que no excluya el grupo **Modern Workplace Devices -All** Azure AD de los que Escritorio administrado de Microsoft creados.


## <a name="azure-active-directory-settings"></a>Azure Active Directory configuración

Restablecimiento de contraseñas de autoservicio: si usa el restablecimiento de contraseñas de autoservicio para todos los usuarios, ajuste la asignación para excluir Escritorio administrado de Microsoft de servicio. Para ajustar esta asignación, cree un  grupo dinámico de Azure AD para todos los usuarios excepto Escritorio administrado de Microsoft cuentas de servicio y, a continuación, use ese grupo para la asignación en lugar de "todos los usuarios".

Para ayudarle a buscar y excluir las cuentas de servicio, este es un ejemplo de una consulta dinámica que puede usar:

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

En esta consulta, reemplace @TENANT por el nombre de dominio del espacio empresarial.



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar con Escritorio administrado de Microsoft

1. [Agregar y verificar los contactos de administración en el portal de administración ](add-admin-contacts.md)
2. Ajustar la configuración después de la inscripción (este artículo)
3. [Asignar licencias](assign-licenses.md)
4. [Desplegar el portal de empresa de Intune](company-portal.md)
5. [Habilitar Enterprise State Roaming](enterprise-state-roaming.md)
6. [Instalar dispositivos](set-up-devices.md)
7. [Prepare a los usuarios para que usen los dispositivos](get-started-devices.md)
8. [Implementar aplicaciones](deploy-apps.md)