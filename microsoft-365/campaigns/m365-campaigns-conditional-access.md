---
title: Activar valores predeterminados de seguridad
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo los valores predeterminados de seguridad pueden ayudar a proteger su organización de ataques relacionados con la identidad proporcionando una configuración de seguridad preconfigurada.
ms.openlocfilehash: ea36ba45af26a767b08ee1e75931dca54dacea64
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398301"
---
# <a name="turn-on-security-defaults"></a>Activar valores predeterminados de seguridad

Los valores predeterminados de seguridad ayudan a proteger su organización de ataques relacionados con la identidad proporcionando una configuración de seguridad preconfigurada que Microsoft administra en nombre de su organización. Estas opciones incluyen habilitar la autenticación multifactor (MFA) para todos los administradores y cuentas de usuario. Para la mayoría de las organizaciones, los valores predeterminados de seguridad ofrecen un buen nivel de seguridad de inicio de sesión adicional.

Para obtener más información acerca de los valores predeterminados de seguridad y las directivas que aplican, vea [¿Cuáles son los valores predeterminados de seguridad?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

Si la suscripción se creó el 22 de octubre de 2019 o después, es posible que los valores predeterminados de seguridad se hayan habilitado automáticamente para que compruebe la configuración para &mdash; confirmarla.

Para habilitar los valores predeterminados de seguridad en Azure Active Directory (Azure AD) o para comprobar si ya están habilitados:

1. Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a> con credenciales de administrador global.

2. En el panel izquierdo, seleccione **Mostrar todo y, a continuación,** en Centros de **administración,** **seleccione Azure Active Directory**.

3. En el panel izquierdo del Centro de **administración de Azure Active Directory,** seleccione Azure Active **Directory**.

4. En el menú izquierdo del panel, en la **sección Administrar,** seleccione **Propiedades**.

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="Captura de pantalla del Centro de administración de Azure Active Directory que muestra la ubicación del elemento de menú Propiedades.":::

5. En la parte inferior de la **página Propiedades,** seleccione **Administrar valores predeterminados de seguridad**.

6. En el panel derecho, verá la configuración Habilitar **valores predeterminados de** seguridad. Si **se** selecciona Sí, los valores predeterminados de seguridad ya están habilitados y no se requiere ninguna acción adicional. Si los valores predeterminados de seguridad no están habilitados actualmente, seleccione **Sí** para habilitarlos y, a continuación, **seleccione Guardar**.

> [!NOTE]
> Si ha estado usando directivas de acceso condicional, deberá desactivarlas antes de usar valores predeterminados de seguridad.
>
> Puede usar los valores predeterminados de seguridad o las directivas de acceso condicional, pero no puede usar ambas al mismo tiempo.

## <a name="consider-using-conditional-access"></a>Considere la posibilidad de usar el acceso condicional

Si su organización tiene requisitos de seguridad complejos o necesita un control más detallado sobre las directivas de seguridad, debe considerar el uso del acceso condicional en lugar de los valores predeterminados de seguridad para lograr una posición de seguridad similar o superior. 

El acceso condicional le permite crear y definir directivas que reaccionan a eventos de inicio de sesión y solicitan acciones adicionales antes de que un usuario obtenga acceso a una aplicación o servicio. Las directivas de acceso condicional pueden ser granulares y específicas, lo que permite a los usuarios ser productivos donde y cuando sea, pero también proteger su organización.

Los valores predeterminados de seguridad están disponibles para todos los clientes, mientras que el acceso condicional requiere una licencia para uno de los siguientes planes:

- Azure Active Directory Premium P1 o P2
- Microsoft 365 Empresa Premium
- Microsoft 365 E3 o E5
- Enterprise Mobility & Security E3 o E5

Si desea usar el acceso condicional para configurar directivas equivalentes a las habilitadas por los valores predeterminados de seguridad, consulte las siguientes guías paso a paso:

- [Requerir MFA para los administradores](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [Requerir MFA para la administración de Azure](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [Bloquear la autenticación heredada](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [Requerir MFA para todos los usuarios](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [Requerir el registro de MFA de Azure AD:](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) requiere Azure AD Identity Protection, que forma parte de Azure Active Directory Premium P2

Para obtener más información sobre el acceso condicional, vea [¿Qué es el acceso condicional?](/azure/active-directory/conditional-access/overview) Para obtener más información acerca de cómo crear directivas de acceso condicional, [vea Create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy).

> [!NOTE]
> Si tiene un plan o una licencia que proporciona acceso condicional pero aún no ha creado ninguna directiva de acceso condicional, puede usar valores predeterminados de seguridad. Sin embargo, deberá desactivar los valores predeterminados de seguridad antes de poder usar directivas de acceso condicional.
