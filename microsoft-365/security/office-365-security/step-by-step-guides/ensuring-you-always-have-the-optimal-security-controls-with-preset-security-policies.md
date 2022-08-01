---
title: Asegurarse de que siempre tiene los controles de seguridad óptimos con directivas de seguridad preestablecidas
description: Los pasos para asegurarse de que siempre tiene los mejores controles de seguridad con directivas de seguridad preestablecidas. Las directivas preestablecidas permiten seleccionar un perfil de seguridad estándar o estricto. Microsoft administrará y mantendrá los controles de seguridad en Microsoft Defender para Office 365 automáticamente.
search.product: ''
search.appverid: ''
ms.prod: m365-security
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
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
ms.openlocfilehash: 383023ea03e9b1634664b3311e7f698ce946608b
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2022
ms.locfileid: "67107357"
---
# <a name="ensuring-you-always-have-the-optimal-security-controls-with-preset-security-policies"></a>Asegurarse de que siempre tiene los controles de seguridad óptimos con directivas de seguridad preestablecidas

Las directivas de seguridad preestablecidas le permiten seleccionar un perfil de seguridad estándar o estricto, y hacer que Microsoft administre y mantenga los controles de seguridad en Microsoft Defender para Office 365 automáticamente.

A medida que se agregan nuevos controles o si la configuración de procedimientos recomendados para un control de seguridad cambia con el panorama de amenazas en constante evolución, Microsoft actualizará automáticamente la configuración de control de seguridad para los usuarios asignados a una directiva de seguridad preestablecida estándar o estricta. Mediante el uso de directivas de valores preestablecidos de seguridad, siempre tendrá la configuración recomendada y recomendada de Microsoft para los usuarios.

## <a name="what-you-will-need"></a>Lo que necesitará
- Microsoft Defender para Office 365 plan 1 o superior (incluido en E5)
- Permisos suficientes (rol administrador de seguridad)
- 5 minutos para realizar los pasos siguientes.

## <a name="choosing-between-standard-and-strict-policies"></a>Elección entre directivas estándar y estrictas

Nuestra directiva de seguridad preestablecida estricta tiene límites y configuraciones más agresivos para los controles de seguridad que darán lugar a detecciones más agresivas e implicarán al administrador en la toma de decisiones sobre qué correos electrónicos bloqueados se publican a los usuarios finales.

- Recopile la lista de usuarios que requieren detecciones más agresivas, incluso si significa que se marcará como sospechoso un correo más bueno. Suelen ser el personal ejecutivo, el personal de soporte técnico ejecutivo y los usuarios históricamente altamente dirigidos.

- Asegúrese de que los usuarios seleccionados tengan cobertura de administrador para revisar y publicar correos electrónicos si el usuario final piensa que el correo puede ser bueno y solicita que se les publique el mensaje.

- Si se cumplen los criterios anteriores, el usuario debe colocarse en la directiva de seguridad preestablecida Strict. De lo contrario, el usuario debe colocarse en la directiva de seguridad preestablecida Estándar.

> [!TIP]
> Para obtener información sobre qué son las directivas de seguridad estándar y estricta, consulte este [artículo](../../office-365-security/recommended-settings-for-eop-and-office365.md).

## <a name="enable-security-presets"></a>Habilitar valores preestablecidos de seguridad

Una vez que haya elegido entre las directivas preestablecidas de seguridad estándar y estricta para los usuarios, se requieren algunos pasos adicionales para asignar usuarios a cada valor preestablecido.

1. Identifique los usuarios, grupos o dominios que desea incluir en los valores preestablecidos de seguridad Estándar y Estricto.
1. Inicie sesión en el portal de seguridad de Microsoft en https://security.microsoft.com.
1. En el panel de navegación izquierdo, en **Email & colaboración**, seleccione **Directivas & reglas**.
1. Seleccione **Directivas de amenazas**.
1. Seleccione **Directivas de seguridad preestablecidas** debajo del encabezado **Directivas con plantilla** .
1. Seleccione **Administrar** debajo del valor preestablecido Protección estándar.
1. Seleccione **Todos los destinatarios** para aplicar Exchange Online Protection inquilino en todo el inquilino o seleccione **Destinatarios específicos a los** que agregar manualmente usuarios, grupos o dominios a los que desea aplicar la directiva de protección. Haga clic en el botón **Siguiente** .
1. Seleccione **Todos los destinatarios** para aplicar Defender para Office 365 Protección en todo el inquilino o seleccione **Destinatarios específicos** para agregar manualmente usuarios, grupos o dominios a los que quiera aplicar la directiva de protección. Haga clic en el botón **Siguiente** .
1. En la sección **Protección contra suplantación**, agregue direcciones de correo electrónico & dominios para protegerse frente a ataques de suplantación y, a continuación, agregue los remitentes y dominios de confianza a los que no quiera que se aplique la protección de suplantación y, a continuación, presione **Siguiente**.
3. Haga clic en el botón **Confirmar** .
4. Seleccione el vínculo **Administrar** en el valor preestablecido Protección estricta.
5. Repita los pasos del 7 al 10 de nuevo, pero para los usuarios se debe aplicar una protección estricta. (si procede)
7. Haga clic en el botón **Confirmar** .

> [!TIP]
> Para más información sobre las directivas preestablecidas, haga clic [aquí](../../office-365-security/preset-security-policies.md).

## <a name="next-steps"></a>Pasos siguientes

Use el analizador de configuración para determinar si los usuarios están configurados según los procedimientos recomendados de Microsoft.

> [!TIP]
> El analizador de configuración permite a los administradores buscar y corregir directivas de seguridad donde la configuración está por debajo de la configuración del perfil de protección estándar o estricta en las directivas de seguridad preestablecidas. Obtenga más información sobre el analizador de configuración [aquí](../../office-365-security/configuration-analyzer-for-security-policies.md).

Los valores preestablecidos seguros siempre se sugieren porque garantiza que siempre está ejerciendo los procedimientos recomendados de Microsoft. Sin embargo, en algunos casos se requieren configuraciones personalizadas. Obtenga información sobre las directivas personalizadas [aquí](../../office-365-security/tenant-wide-setup-for-increased-security.md).

