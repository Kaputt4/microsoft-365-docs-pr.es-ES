---
title: Valores predeterminados de seguridad y acceso condicional
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
ms.date: 08/05/2022
ms.collection:
- M365-Campaigns
- m365solution-smb
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo los valores predeterminados de seguridad pueden ayudar a proteger su organización frente a ataques relacionados con la identidad proporcionando una preconfiguración de seguridad para Microsoft 365 Empresa Premium.
ms.openlocfilehash: 7c73b40d73ec022b2047ceb3998b7d82ceab56e8
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67276008"
---
# <a name="security-defaults-and-multi-factor-authentication"></a>Valores predeterminados de seguridad y autenticación multifactor

Microsoft 365 Empresa Premium se diseñó para ayudar a proteger las cuentas de usuario de su empresa con la configuración de seguridad preconfigurada. Esta configuración incluye la habilitación de la autenticación multifactor (MFA) para todos los administradores y cuentas de usuario. En la mayoría de las organizaciones, los valores predeterminados de seguridad ofrecen un buen nivel de seguridad adicional de inicio de sesión.

Para obtener más información sobre los valores predeterminados de seguridad y las directivas que aplican, consulte [¿Qué son los valores predeterminados de seguridad?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

En este artículo se proporciona información acerca de:

- **[Valores predeterminados de seguridad](#security-defaults)** (adecuados para la mayoría de las empresas)
- **[Acceso condicional](#conditional-access)** (para empresas con requisitos de seguridad más estrictos)

> [!NOTE]
> Si ha estado usando directivas de acceso condicional, deberá desactivarlas antes de usar los valores predeterminados de seguridad. Puede usar los valores predeterminados de seguridad o las directivas de acceso condicional, pero no puede usar ambos al mismo tiempo.

## <a name="security-defaults"></a>Valores predeterminados de seguridad

Los valores predeterminados de seguridad se diseñaron para ayudar a proteger las cuentas de usuario de su empresa desde el principio. Cuando se activan, los valores predeterminados de seguridad proporcionan una configuración predeterminada segura que ayuda a mantener la seguridad de su empresa de la siguiente forma:

- Requerir que todos los usuarios y administradores se registren en MFA mediante la aplicación Microsoft Authenticator.
- Poner una prueba a los usuarios con MFA, sobre todo cuando aparecen en un nuevo dispositivo o aplicación, pero con más frecuencia para roles y tareas críticos.
- Deshabilitar la autenticación de los clientes de autenticación heredados que no pueden hacer MFA.
- Proteger a los administradores mediante un requisito de autenticación adicional cada vez que inicien sesión.

MFA es un primer paso importante para proteger su empresa, y los valores predeterminados de seguridad facilitan la implementación de MFA. Si la suscripción se creó el 22 de octubre de 2019 o después, es posible que los valores predeterminados de seguridad se hayan habilitado automáticamente&mdash;debe comprobar la configuración para confirmar.

> [!TIP]
> Para obtener más información sobre los valores predeterminados de seguridad y las directivas que aplican, consulte [¿Qué son los valores predeterminados de seguridad?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

### <a name="to-enable-security-defaults-or-confirm-theyre-already-enabled"></a>Para habilitar los valores predeterminados de seguridad (o confirmar que ya están habilitados)

1. Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a> con credenciales de administrador de seguridad, administrador de acceso condicional o administrador global.

2. En el panel izquierdo, seleccione **Mostrar todos** y, a continuación, en **Centros de administración**, seleccione **Azure Active Directory**.

3. En el panel izquierdo del centro de administración de **Azure Active Directory,** seleccione **Azure Active Directory**.

4. En el menú izquierdo del panel, en la sección **Administración**, seleccione **Propiedades**.

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="Recorte de pantalla del centro de administración de Azure Active Directory que muestra la ubicación del elemento menú Propiedades.":::

5. En la parte inferior de la página **Propiedades**, seleccione **Administrar valores predeterminados de seguridad**.

6. En el panel derecho, verá la configuración **Habilitar de valores predeterminados de seguridad**. Si está seleccionada la configuración **Sí**, los valores predeterminados de seguridad ya están habilitados y no se requiere ninguna otra acción. Si los valores predeterminados de seguridad no están habilitados actualmente, seleccione la opción **Sí** para habilitarlos y, a continuación, seleccione **Guardar**.

## <a name="conditional-access"></a>Acceso condicional

> [!NOTE]
> Si ha estado usando los valores predeterminados de seguridad, deberá desactivarlos antes de usar el acceso condicional. Puede usar los valores predeterminados de seguridad o las directivas de acceso condicional, pero no puede usar ambos al mismo tiempo.

Si su empresa o negocio tiene requisitos de seguridad complejos o necesita un control más pormenorizado de las directivas de seguridad, debe considerar la posibilidad de usar el acceso condicional en lugar de los valores predeterminados de seguridad para lograr una posición de seguridad similar o superior.

El acceso condicional le permite crear y definir directivas que reaccionan a eventos de inicio de sesión y solicitan acciones adicionales antes de otorgar acceso a un usuario a una aplicación o a un servicio. Las directivas de acceso condicional pueden ser granulares y específicas, para que los usuarios puedan ser productivos en cualquier lugar y en cualquier momento y para proteger también a la organización.

Los valores predeterminados de seguridad están disponibles para todos los clientes, mientras que el acceso condicional requiere uno de los siguientes planes:

- Prueba de Azure Active Directory Premium P1 o P2
- Microsoft 365 Empresa Premium
- Microsoft 365 E3 o E5
- Enterprise Mobility + Security E3 o E5

Si desea usar el acceso condicional para configurar directivas, consulte las siguientes guías paso a paso:

- [Requerir MFA para los administradores](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [Requerir MFA para la administración de Azure](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [Bloquear la autenticación heredada](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [Requerir MFA para todos los usuarios](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [Requerir registro de MFA de Azure AD](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy): requiere Azure AD Identity Protection, que forma parte de Azure Active Directory Premium P2

Para obtener más información sobre el acceso condicional, consulte [¿Qué es el acceso condicional?](/azure/active-directory/conditional-access/overview) Para obtener más información sobre cómo crear directivas de acceso condicional, consulte [Crear una directiva de acceso condicional](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy).

> [!NOTE]
> Si tiene un plan o una licencia que proporciona acceso condicional, pero aún no ha creado ninguna directiva de acceso condicional, puede usar los valores predeterminados de seguridad. Sin embargo, deberá desactivar los valores predeterminados de seguridad para poder usar las directivas de acceso condicional.

## <a name="next-objective"></a>Siguiente objetivo

[Proteger las cuentas de administrador en Microsoft 365 Empresa Premium](m365bp-protect-admin-accounts.md)
