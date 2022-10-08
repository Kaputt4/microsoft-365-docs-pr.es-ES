---
author: LanaChin
ms.author: v-lanachin
ms.date: ''
ms.topic: include
audience: admin
ms.service: microsoft-365-frontline
ms.openlocfilehash: f3a764a66f3be2fc553581b45dead569ffda1fb6
ms.sourcegitcommit: 99b174a8d431092b3cf7d650593248671297fd91
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68301848"
---
Antes de empezar, asegúrese de que tiene los siguientes requisitos previos:

- Nombre de la cuenta de servicio de UKG Dimensions, contraseña y direcciones URL de servicio:

  - Dirección URL de la interfaz del programa de aplicación
  - Clave de aplicación
  - Id. de cliente
  - Secreto de cliente
  - Dirección URL de inicio de sesión único

  Si no tiene esta información, póngase en contacto con el soporte técnico de UKG Dimensions.
- La autenticación federada de inicio de sesión único (SSO) está habilitada en el entorno de UKG Dimensions. </br>Azure Active Directory (Azure AD) es el proveedor de identidades admitido para el inicio de sesión único. Para habilitar el inicio de sesión único, configure la integración entre Azure AD y UKG Dimensions. Para ver un tutorial paso a paso, consulte [Tutorial: Integración del inicio de sesión único de Azure AD con Kronos Workforce Dimensions](/azure/active-directory/saas-apps/kronos-workforce-dimensions-tutorial). Si necesita ayuda o más información sobre cómo configurar el inicio de sesión único, póngase en contacto con el soporte técnico de UKG Dimensions.

    Una vez configurada la integración, configure los usuarios como cuentas federadas en su página de perfil en UkG Dimensions.
- Al menos un equipo configurado en Teams.
- Ha agregado una cuenta del sistema de Microsoft 365 como propietario del equipo a todos los equipos que desea asignar.</br> [Cree esta cuenta en Microsoft 365](/microsoft-365/admin/add-users/add-users) y asígnele una licencia de Microsoft 365. Después, agregue la cuenta como propietario de un equipo a todos los equipos que quiera asignar. El conector Shifts usa esta cuenta al sincronizar Cambios cambios de las dimensiones de UKG.

    Se recomienda crear una cuenta específicamente para este propósito y no usar su cuenta de usuario.
