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
ms.openlocfilehash: ca919798480698f92bba094c3755b3eccce30888
ms.sourcegitcommit: c1f9a1b2a34146c51c9e33c4119a388b249ce7a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "49867975"
---
# <a name="adjust-settings-after-enrollment"></a>Ajustar la configuración después de la inscripción

Después de completar la inscripción en el Escritorio administrado de Microsoft, es posible que deba ajustarse alguna configuración de administración. Para comprobar y ajustar si es necesario, siga estos pasos:

1. Revisa la configuración de Microsoft Intune y Azure Active Directory que se describe en la sección siguiente.
2. Si alguno de los elementos se aplica a su entorno, realice los ajustes descritos.
3. Si desea comprobar de nuevo que todas las configuraciones [](https://aka.ms/mmdart) son correctas, puede volver a ejecutar la herramienta de evaluación de preparación para asegurarse de que nada entre en conflicto con el Escritorio administrado de Microsoft.

> [!NOTE]
> A medida que las operaciones continúen en los meses siguientes, si realiza cambios después de la inscripción en las directivas de Microsoft Intune, Azure Active Directory o Microsoft 365 que afectan al Escritorio administrado de Microsoft, es posible que el Escritorio administrado de Microsoft deje de funcionar correctamente. Para evitar problemas con el servicio, compruebe la configuración específica descrita en [Corregir](../get-ready/readiness-assessment-fix.md) problemas encontrados por la herramienta de evaluación de preparación antes de cambiar las directivas enumeradas allí. También puede volver a ejecutar la herramienta de evaluación de preparación en cualquier momento.


## <a name="microsoft-intune-settings"></a>Configuración de Microsoft Intune

- Perfil de implementación de Autopilot: si usas alguna directiva de Autopilot, actualiza cada una para excluir el grupo **Modern Workplace Devices -All** Azure AD. Para actualizarlos,  en la sección Grupos excluidos en Asignaciones, seleccione el grupo Dispositivos de trabajo **modernos** **-Todos** los grupos de Azure AD que se creó durante la inscripción en el Escritorio administrado de Microsoft. Escritorio administrado de Microsoft también habrá creado un perfil de Autopilot, que tendrá "Modern Workplace" en el nombre (el perfil **de Modern Workplace Autopilot**). Al actualizar sus propios perfiles de  Autopilot, asegúrese de no excluir el grupo Dispositivos de Área de trabajo modernos **:Todos** los grupos de Azure AD del perfil de Modern **Workplace Autopilot** creado por Escritorio administrado de Microsoft.

- Directivas de acceso condicional: si crea nuevas directivas de acceso condicional relacionadas con Azure AD, Microsoft Intune o Microsoft Defender para puntos de conexión después de la inscripción en el Escritorio administrado de Microsoft, excluya del grupo de Azure AD cuentas de servicio de **Área** de trabajo modernas. Para ver los pasos, [vea Acceso condicional: usuarios y grupos.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups) Escritorio administrado de Microsoft mantiene directivas de acceso condicional independientes para restringir el acceso a estas cuentas. Para revisar la directiva de acceso condicional de Escritorio administrado de Microsoft **(Modern Workplace – Secure Workstation),** vaya a Microsoft Endpoint Manager y vaya a **Acceso** condicional en **Endpoint Security.** No modifique ninguna directiva de acceso condicional de Azure AD creada por Escritorio administrado de Microsoft que tenga "Modern Workplace" en el nombre.

- Autenticación multifactor: si crea nuevos requisitos de autenticación multifactor en directivas de acceso condicional relacionadas con Azure AD, Intune o Microsoft Defender para puntos de conexión después de la inscripción en el Escritorio administrado de Microsoft, excluya del grupo cuentas de servicio de **Área** de trabajo modernas de Azure AD. Para ver los pasos, [vea Acceso condicional: usuarios y grupos.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups) Escritorio administrado de Microsoft mantiene directivas de acceso condicional independientes para restringir el acceso a los miembros de este grupo. Para revisar la directiva de acceso condicional de Escritorio administrado de Microsoft (**Modern Workplace -**), vaya a Microsoft Endpoint Manager y vaya a Acceso **condicional** en **Endpoint Security.** 

- Anillo de actualización de Windows 10: para cualquier directiva de anillo de actualización de Windows 10 que hayas creado, excluye los dispositivos de Área de trabajo modernos: todos los grupos de **Azure** AD de cada directiva. Para ver los pasos, [consulta Crear y asignar anillos de actualización.](https://docs.microsoft.com/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings) El Escritorio administrado de Microsoft también habrá creado algunas directivas de anillo de actualización, todas las cuales tendrán "Área de trabajo moderna" en el nombre (por ejemplo, Directiva de actualización de área de trabajo moderna **[Amplia]**, Directiva de actualización de área de trabajo **moderna [Rápido]**, Directiva de actualización de área de **trabajo moderna [Primero]** y Directiva de actualización de área de trabajo **moderna [Prueba]**). Al actualizar sus propias directivas,  asegúrese de no excluir el grupo Dispositivos de Área de trabajo modernos **:todos** los grupos de Azure AD de los que creó Escritorio administrado de Microsoft.


## <a name="azure-active-directory-settings"></a>Configuración de Azure Active Directory

Restablecimiento de contraseña de autoservicio: si usa el restablecimiento de contraseña de autoservicio para todos los usuarios, ajuste la asignación para excluir cuentas de servicio de Escritorio administrado de Microsoft. Para ajustar esta asignación, cree un grupo dinámico de Azure AD para todos los usuarios excepto las cuentas de servicio de Escritorio administrado de *Microsoft* y, a continuación, use ese grupo para la asignación en lugar de "todos los usuarios".

Para ayudarle a buscar y excluir las cuentas de servicio, este es un ejemplo de una consulta dinámica que puede usar:

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

En esta consulta, reemplace @TENANT por el nombre de dominio del espacio empresarial.



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar a usar el Escritorio administrado de Microsoft

1. [Agregar y verificar los contactos de administración en el portal de administración ](add-admin-contacts.md)
2. Ajustar la configuración después de la inscripción (este artículo)
3. [Asignar licencias](assign-licenses.md)
4. [Desplegar el portal de empresa de Intune](company-portal.md)
5. [Habilitar Enterprise State Roaming](enterprise-state-roaming.md)
6. [Instalar dispositivos](set-up-devices.md)
7. [Prepare a los usuarios para que usen los dispositivos](get-started-devices.md)
8. [Implementar aplicaciones](deploy-apps.md)
