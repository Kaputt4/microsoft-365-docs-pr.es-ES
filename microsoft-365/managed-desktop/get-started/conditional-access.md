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

Después de completar la inscripción en Microsoft Managed Desktop, es posible que deba ajustarse alguna configuración de administración. Para comprobar y ajustar si es necesario, siga estos pasos:

1. Revise la configuración de Microsoft Intune y Azure Active Directory que se describe en la sección siguiente.
2. Si alguno de los elementos se aplica al entorno, realice los ajustes descritos.
3. Si desea comprobar que todas las configuraciones son correctas, puede volver a ejecutar la herramienta de evaluación de preparación para asegurarse de que nada entre en conflicto con el Escritorio administrado de Microsoft. [](https://aka.ms/mmdart)

> [!NOTE]
> A medida que las operaciones continúan en los meses siguientes, si realiza cambios después de la inscripción en directivas de Microsoft Intune, Azure Active Directory o Microsoft 365 que afectan al Escritorio administrado de Microsoft, es posible que Microsoft Managed Desktop deje de funcionar correctamente. Para evitar problemas con el servicio, compruebe la configuración específica que se describe en [Corregir](../get-ready/readiness-assessment-fix.md) problemas encontrados por la herramienta de evaluación de preparación antes de cambiar las directivas enumeradas allí. También puede volver a ejecutar la herramienta de evaluación de preparación en cualquier momento.


## <a name="microsoft-intune-settings"></a>Configuración de Microsoft Intune

- Perfil de implementación de Autopilot: si usa alguna directiva de Autopilot, actualice cada una para excluir el grupo **Modern Workplace Devices -All** Azure AD. Para actualizarlos, en la sección **Grupos** **excluidos** de Asignaciones, seleccione el grupo **Modern Workplace Devices -All** Azure AD que se creó durante la inscripción de Microsoft Managed Desktop. Microsoft Managed Desktop también habrá creado un perfil de Autopilot, que tendrá "Modern Workplace" en el nombre (el perfil de **Modern Workplace Autopilot**). Al actualizar sus propios perfiles de  **Autopilot,** asegúrese de que no excluye el grupo Modern Workplace **Devices -All** Azure AD del perfil de Modern Workplace Autopilot creado por Microsoft Managed Desktop.

- Directivas de acceso condicional: si crea nuevas directivas de acceso condicional relacionadas con Azure AD, Microsoft Intune o Microsoft Defender para Endpoint después de la inscripción de Microsoft Managed Desktop, excluya el grupo cuentas de servicio de **Trabajo** moderno de Azure AD. Para ver los pasos, [vea Acceso condicional: Usuarios y grupos](/azure/active-directory/conditional-access/concept-conditional-access-users-groups). Microsoft Managed Desktop mantiene directivas de acceso condicional independientes para restringir el acceso a estas cuentas. Para revisar la directiva de acceso condicional de Microsoft Managed Desktop (**Modern Workplace – Secure Workstation**), vaya a Microsoft Endpoint Manager y vaya a Acceso **condicional** en **Endpoint Security**. No modifique ninguna directiva de acceso condicional de Azure AD creada por Microsoft Managed Desktop que tenga "Modern Workplace" en el nombre.

- Autenticación multifactor: si crea nuevos requisitos de autenticación multifactor en directivas de acceso condicional relacionadas con Azure AD, Intune o Microsoft Defender para Endpoint después de la inscripción de Microsoft Managed Desktop, excluya el grupo cuentas de **servicio** de trabajo modernas de Azure AD. Para ver los pasos, [vea Acceso condicional: Usuarios y grupos](/azure/active-directory/conditional-access/concept-conditional-access-users-groups). Microsoft Managed Desktop mantiene directivas de acceso condicional independientes para restringir el acceso a los miembros de este grupo. To review the Microsoft Managed Desktop conditional access policy (**Modern Workplace -**), go to Microsoft Endpoint Manager and navigate to Conditional **Access** in **Endpoint Security**. 

- Anillo de actualización de Windows 10: para cualquier directiva de anillo de actualización de Windows 10 que hayas creado, excluye el grupo Dispositivos modernos de Workplace **-Todos** los grupos de Azure AD de cada directiva. Para ver los pasos, [vea Crear y asignar anillos de actualización.](/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings) Microsoft Managed Desktop también habrá creado algunas directivas de anillo de actualización, todas las cuales tendrán "Modern Workplace" en el nombre (por ejemplo, Modern Workplace **Update Policy [Broad]**, **Modern Workplace Update Policy [Fast]**, **Modern Workplace Update Policy [First]** y **Modern Workplace Update Policy [Test]**). Cuando actualice sus propias directivas,  asegúrese de no excluir el grupo **Modern Workplace Devices -All** Azure AD de los que creó Microsoft Managed Desktop.


## <a name="azure-active-directory-settings"></a>Configuración de Azure Active Directory

Restablecimiento de contraseñas de autoservicio: si usa el restablecimiento de contraseñas de autoservicio para todos los usuarios, ajuste la asignación para excluir las cuentas de servicio de Escritorio administrado de Microsoft. Para ajustar esta asignación, cree un grupo dinámico de Azure AD para todos los usuarios excepto las cuentas de servicio de *Escritorio* administrado de Microsoft y, a continuación, use ese grupo para la asignación en lugar de "todos los usuarios".

Para ayudarle a buscar y excluir las cuentas de servicio, este es un ejemplo de una consulta dinámica que puede usar:

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

En esta consulta, reemplace @TENANT por el nombre de dominio del espacio empresarial.



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar con Microsoft Managed Desktop

1. [Agregar y verificar los contactos de administración en el portal de administración ](add-admin-contacts.md)
2. Ajustar la configuración después de la inscripción (este artículo)
3. [Asignar licencias](assign-licenses.md)
4. [Desplegar el portal de empresa de Intune](company-portal.md)
5. [Habilitar Enterprise State Roaming](enterprise-state-roaming.md)
6. [Instalar dispositivos](set-up-devices.md)
7. [Prepare a los usuarios para que usen los dispositivos](get-started-devices.md)
8. [Implementar aplicaciones](deploy-apps.md)