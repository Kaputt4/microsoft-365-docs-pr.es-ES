---
title: Directivas de seguridad predefinidas
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a aplicar la configuración de directiva estándar y estricta en todas las características de protección de Exchange Online Protection (EOP) y Microsoft Defender para Office 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 24fe67a7465ec71451b649dbc5963c28e0dc7cf3
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879017"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>Directivas de seguridad predefinidas en EOP y Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Las directivas de seguridad predefinidas proporcionan una ubicación centralizada para aplicar todas las directivas de correo no deseado, malware y suplantación de identidad recomendadas a los usuarios a la vez. La configuración de directiva no se puede configurar. En su lugar, se establecen por nosotros y se basan en nuestras observaciones y experiencias en los centros de datos para un equilibrio entre mantener el contenido dañino alejado de los usuarios y evitar interrupciones innecesarias.

El resto de este artículo describe las directivas de seguridad preestablecidas y cómo configurarlas.

## <a name="what-preset-security-policies-are-made-of"></a>De qué están hechas las directivas de seguridad preestablecidas

Las directivas de seguridad preestablecidas constan de los siguientes elementos:

- Profiles
- Directivas
- Configuración de la directiva

Además, el orden de prioridad es importante si se aplican varias directivas de seguridad preestablecidas y otras directivas a la misma persona.

### <a name="profiles-in-preset-security-policies"></a>Perfiles en directivas de seguridad preestablecidas

Un perfil determina el nivel de protección. Los perfiles siguientes están disponibles:

- **Protección estándar:** un perfil de protección de línea base adecuado para la mayoría de los usuarios.
- **Protección estricta:** un perfil de protección más agresivo para usuarios seleccionados (destinos de alto valor o usuarios prioritarios).

Se usan reglas con condiciones y excepciones que determinan quiénes son los perfiles o no se aplican.

Las condiciones y excepciones disponibles son:

- **Usuarios**: los buzones, usuarios de correo o contactos de correo especificados de su organización.
- **Grupos**: los grupos de distribución, los grupos de seguridad habilitados para correo electrónico o los Grupos de Microsoft 365 especificados de la organización.
- **Dominios**: todos los destinatarios de los [dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados en la organización.

Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

### <a name="policies-in-preset-security-policies"></a>Directivas en directivas de seguridad preestablecidas

Las directivas de seguridad predefinidas usan las directivas correspondientes de las distintas características de protección de EOP y Microsoft Defender para Office 365. Estas directivas se crean _después de asignar_ las **directivas** de seguridad predeterminadas protección **estándar** o Protección estricta a los usuarios. No puede modificar estas directivas.

- **Exchange Online Protection (EOP):** esto incluye organizaciones Microsoft 365 con buzones de correo Exchange Online y organizaciones independientes de EOP sin Exchange Online buzones de correo:

  - [Directivas contra correo no deseado](configure-your-spam-filter-policies.md) **denominadas Standard Preset Security Policy** y Strict Preset Security **Policy**.
  - [Directivas antimalware](configure-anti-malware-policies.md) **denominadas Standard Preset Security Policy** y Strict Preset Security **Policy**.
  - [Directivas contra suplantación de identidad de EOP](set-up-anti-phishing-policies.md#spoof-settings) **denominadas Standard Preset Security Policy** y Strict Preset Security **Policy** (configuración de suplantación de identidad).

- **Directivas de Microsoft Defender para Office 365:** esto incluye organizaciones con Microsoft 365 E5 o Defender para Office 365 de complementos:

  - Las directivas contra suplantación de identidad en Microsoft Defender para Office 365 denominada **Standard Preset Security Policy** y Strict Preset Security **Policy**, que incluyen:

    - La misma [configuración de suplantación](set-up-anti-phishing-policies.md#spoof-settings) de identidad que están disponibles en las directivas contra suplantación de identidad de EOP.
    - [Configuración de suplantación](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Umbrales de suplantación de identidad avanzada](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Caja fuerte vincula directivas denominadas](set-up-safe-links-policies.md) **Standard Preset Security Policy** y Strict Preset Security **Policy**.

  - [Caja fuerte de datos adjuntos](set-up-safe-attachments-policies.md) denominado **Standard Preset Security Policy** y Strict Preset Security **Policy**.

Tenga en cuenta que puede aplicar protecciones de EOP a diferentes usuarios que Microsoft Defender para Office 365 protección.

### <a name="policy-settings-in-preset-security-policies"></a>Configuración de directivas en directivas de seguridad preestablecidas

No puede modificar la configuración de directiva en los perfiles de protección. Los **valores de** configuración de directiva Estándar y Estricto se describen en Configuración recomendada para EOP y Microsoft Defender para Office 365 [seguridad.](recommended-settings-for-eop-and-office365.md) 

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Orden de prioridad para las directivas de seguridad preestablecidas y otras directivas

Cuando se aplican varias directivas a un usuario, se aplica el siguiente orden de prioridad máxima a prioridad más baja:

1. **Directiva de seguridad** preestablecida de protección estricta
2. **Directiva de seguridad** preestablecida de protección estándar
3. Directivas de seguridad personalizadas
4. Directivas de seguridad predeterminadas

En otras palabras,  la configuración de la  directiva de protección estricta invalida la configuración de la directiva de protección estándar, que invalida la configuración de una directiva personalizada, que invalida la configuración de la directiva predeterminada.

## <a name="assign-preset-security-policies-to-users"></a>Asignar directivas de seguridad preestablecidas a los usuarios

### <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Abra el portal Microsoft 365 Defender en <https://security.microsoft.com> . Para ir directamente a la página **Directivas de seguridad preestablecidas,** use <https://security.microsoft.com/presetSecurityPolicies> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Debe tener permisos asignados en la **Exchange Online** antes de poder realizar los procedimientos de este artículo:
  - Para configurar directivas de seguridad preestablecidas, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.
  - Para obtener acceso de solo lectura a directivas de seguridad preestablecidas, debe ser miembro del grupo de roles **Lector** global.

  Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Nota:** Agregar usuarios al rol Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos y permisos necesarios para _otras_ características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

### <a name="use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users"></a>Usar el portal Microsoft 365 Defender para asignar directivas de seguridad preestablecidas a los usuarios

1. En el portal Microsoft 365 Defender, vaya a Email **& collaboration** Policies \> **& Rules** Threat \> **Policies** \> **Templated policies** section Preset Security \> **Policies**.

2. En **Protección estándar o** Protección **estricta,** haga clic **en Editar**.

3. Se **inicia el asistente** Aplicar protección estándar o Aplicar **protección** estricta. En la **página Las protecciones de EOP** se aplican a la página, identifique los destinatarios internos a los que se aplican las protecciones [de EOP](#policies-in-preset-security-policies) (condiciones de destinatario):
   - **Usuarios**
   - **Grupos**
   - **Dominios**

   Haga clic en el cuadro correspondiente, comience a escribir un valor y seleccione el valor que desee de los resultados. Repita este proceso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Icono de quitar](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

   Para los usuarios o grupos, puede usar la mayoría de los identificadores (nombre, nombre para mostrar, alias, dirección de correo electrónico, nombre de cuenta, etc.), pero el nombre para mostrar correspondiente se muestra en los resultados. Para los usuarios, escriba un asterisco (\*) para ver todos los valores disponibles.

   - **Excluir estos usuarios, grupos y dominios**: para agregar excepciones a los destinatarios internos a los que se aplica la directiva (excepciones de destinatarios), seleccione esta opción y configure las excepciones. La configuración y el comportamiento se muestran exactamente igual que las condiciones.

   Cuando termine, haga clic en **Siguiente**.

4. En Microsoft Defender para organizaciones de Office 365, te llevaremos **a defender** para que las protecciones de Office 365 se apliquen a la página para identificar los destinatarios internos a los que se aplican las protecciones de Office 365 de Microsoft [Defender](#policies-in-preset-security-policies) (condiciones de destinatario).

   La configuración y el comportamiento son exactamente iguales a las **protecciones de EOP que se aplican a la** página.

   Cuando termine, haga clic en **Siguiente**.

5. En la **página Revisar y confirmar los cambios,** compruebe las selecciones y, a continuación, haga clic en **Confirmar**.

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-preset-security-policies"></a>Usar el portal Microsoft 365 Defender para modificar las asignaciones de directivas de seguridad preestablecidas

Los pasos para modificar la asignación de la **directiva** de seguridad de protección estándar o de protección estricta son los mismos que cuando se asignaron inicialmente las directivas de seguridad preestablecidas [a los usuarios.](#use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users) 

Para deshabilitar las  **directivas de** seguridad Protección estándar o Protección estricta a la vez que se conservan las condiciones y excepciones existentes, deslice el botón de alternancia a **Desactivado.** ![ ](../../media/scc-toggle-off.png) Para habilitar las directivas, deslice el botón de alternancia a **Activado** ![ activar ](../../media/scc-toggle-on.png) .

### <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha asignado  correctamente  la directiva de protección estándar o de seguridad de protección  estricta a un usuario,  use una configuración de protección en la que el valor predeterminado sea diferente de la configuración de protección estándar, que es diferente de la configuración de protección estricta.

Por ejemplo, para el correo electrónico detectado como correo no deseado (no correo no  deseado de elevada confianza) compruebe que el mensaje se entregue a la carpeta correo no deseado para los usuarios de protección estándar y se ponga en cuarentena para los usuarios de protección **estricta.**

O bien, en el caso del correo [masivo,](bulk-complaint-level-values.md)compruebe que el valor  de BCL 6 o posterior entrega el mensaje  a la carpeta correo no deseado para los usuarios de protección estándar y el valor de BCL 4 o superior pone en cuarentena el mensaje para usuarios de protección estricta.
