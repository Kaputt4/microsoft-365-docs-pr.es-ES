---
title: Pasos para configurar rápidamente las directivas de seguridad preestablecidas estándar o estricta para Microsoft Defender para Office 365
description: Paso a paso para configurar directivas de seguridad preestablecidas en Microsoft Defender para Office 365 para que tenga la seguridad recomendada por el producto. Las directivas preestablecidas establecen un perfil de seguridad *estándar* o *estricto*. Establézcalos y Microsoft Defender para Office 365 administrará y mantendrá estos controles de seguridad automáticamente.
search.product: ''
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-guidance-templates
- m365-security
- tier3
ms.topic: how-to
ms.subservice: mdo
search.appverid: met150
ms.openlocfilehash: 927fbd7c8e2e6b9a671ab18abda4d190544f1b79
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68222212"
---
# <a name="set-up-steps-for-the-standard-or-strict-preset-security-policies-in-microsoft-defender-for-office-365"></a>Configure los pasos para las directivas de seguridad preestablecidas estándar o estricta en Microsoft Defender para Office 365

¿Microsoft Defender para Office 365 le proporcionó una manera de aplicar las directivas de seguridad que luego mantendría?

¿Sabía que cuando cambia un procedimiento recomendado para un control de seguridad debido al panorama de amenazas en constante evolución, o a medida que se agregan nuevos controles, Microsoft actualiza *automáticamente* la configuración de control de seguridad para los usuarios asignados a una directiva de seguridad preestablecida *estándar* o *estricta* ?

Mediante el uso de directivas de seguridad preestablecidas (*estándar* o *estricta*), siempre tendrá la *configuración recomendada y recomendada* de Microsoft para los usuarios.

**Siga estos pasos** para aplicar directivas de seguridad preestablecidas y hacer que Microsoft Defender para Office 365 administre y mantenga los controles *de seguridad automáticamente*.

## <a name="what-you-will-need"></a>Lo que necesitará
- Microsoft Defender para Office 365 plan 1 o superior (incluido en E5)
- Permisos suficientes (rol administrador de seguridad)
- 5 minutos para realizar los pasos siguientes.

## <a name="choose-between-standard-and-strict-policies"></a>Elegir entre directivas estándar y estrictas

Nuestra directiva de seguridad preestablecida estricta tiene límites y configuraciones más agresivos para los controles de seguridad que darán lugar a detecciones más agresivas e implicarán al administrador en la toma de decisiones sobre qué correos electrónicos bloqueados se publican a los usuarios finales.

- Recopile la lista de usuarios que requieren detecciones más agresivas, incluso si significa que se marcará como sospechoso un correo más bueno. Suelen ser el personal ejecutivo, el personal de soporte técnico ejecutivo y los usuarios históricamente altamente dirigidos.

- Asegúrese de que los usuarios seleccionados tengan cobertura de administrador para revisar y publicar correos electrónicos si el usuario final piensa que el correo puede ser bueno y solicita que se les publique el mensaje.

- Si se cumplen los criterios anteriores, el usuario debe colocarse en la directiva de seguridad preestablecida Strict. De lo contrario, el usuario debe colocarse en la directiva de seguridad preestablecida Estándar.

> [!TIP]
> Para obtener información sobre qué son las directivas de seguridad estándar y estricta, consulte este [artículo](../../office-365-security/recommended-settings-for-eop-and-office365.md).

## <a name="enable-security-presets-in-microsoft-defender-for-office-365"></a>Habilitar valores preestablecidos de seguridad en Microsoft Defender para Office 365

Una vez que haya elegido entre las directivas preestablecidas de seguridad estándar y estricta para los usuarios, se requieren algunos pasos adicionales para asignar usuarios a cada valor preestablecido.

1. Identifique los usuarios, grupos o dominios que desea incluir en los valores preestablecidos de seguridad Estándar y Estricto.
1. Inicie sesión en el portal de seguridad de Microsoft en https://security.microsoft.com.
1. En el panel de navegación izquierdo, en **Email & colaboración**, seleccione **Directivas & reglas**.
1. Seleccione **Directivas de amenazas**.
1. Seleccione **Directivas de seguridad preestablecidas** debajo del encabezado **Directivas con plantilla** .
1. Seleccione **Administrar** debajo del valor preestablecido Protección estándar.
1. Seleccione **Todos los destinatarios** para aplicar Exchange Online Protection inquilino en todo el inquilino o seleccione **Destinatarios específicos a los** que agregar manualmente usuarios, grupos o dominios a los que desea aplicar la directiva de protección. Haga clic en el botón **Siguiente** .
1. Seleccione **Todos los destinatarios** para aplicar Defender para Office 365 Protección en todo el inquilino o seleccione **Destinatarios específicos** para agregar manualmente usuarios, grupos o dominios a los que quiera aplicar la directiva de protección. Haga clic en el botón **Siguiente** .
1. En la sección **Protección contra suplantación** , agregue direcciones de correo electrónico & dominios para protegerse frente a ataques de suplantación y, a continuación, agregue los remitentes y dominios de confianza a los que no quiera que se aplique la protección de suplantación y, a continuación, presione **Siguiente**.
1. Haga clic en el botón **Confirmar** .
1. Seleccione el vínculo **Administrar** en el valor preestablecido Protección estricta.
1. Repita los pasos del 7 al 10 de nuevo, pero para los usuarios se debe aplicar una protección estricta. (si procede)
1. Haga clic en el botón **Confirmar** .

> [!TIP]
> Para más información sobre las directivas preestablecidas, haga clic [aquí.](../../office-365-security/preset-security-policies.md)

## <a name="your-next-step-is-config-analyzer"></a>El siguiente paso es El analizador de configuración

Use el analizador de configuración para determinar si los usuarios están configurados según los procedimientos recomendados de Microsoft.

> [!TIP]
> El analizador de configuración permite a los administradores buscar y corregir directivas de seguridad donde la configuración está por debajo de la configuración del perfil de protección estándar o estricta en las directivas de seguridad preestablecidas. Obtenga más información sobre el analizador de configuración [aquí](../../office-365-security/configuration-analyzer-for-security-policies.md).

Los valores preestablecidos seguros siempre se recomiendan porque *garantiza que los* administradores ejerzan los procedimientos recomendados de Microsoft. Sin embargo, en algunos casos se requieren configuraciones personalizadas. Obtenga información sobre las directivas personalizadas [aquí](../../office-365-security/tenant-wide-setup-for-increased-security.md).

