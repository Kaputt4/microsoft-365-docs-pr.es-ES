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
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Los administradores pueden aprender a aplicar la configuración de directiva estándar y estricta en todas las características de protección de Exchange Online Protection (EOP) y Microsoft Defender para Office 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a557afd562c2b4d0127f69afec40c1909944968e
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61943165"
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

- Perfiles
- Directivas
- Configuración de la directiva

Además, el orden de prioridad es importante si se aplican varias directivas de seguridad preestablecidas y otras directivas a la misma persona.

### <a name="profiles-in-preset-security-policies"></a>Perfiles en directivas de seguridad preestablecidas

El perfil determina el nivel de protección. Los perfiles siguientes están disponibles:

- **Protección estándar**: un perfil básico de protección adecuado para la mayoría de los usuarios.
- **Protección estricta:** un perfil de protección más agresivo para usuarios seleccionados (destinos de alto valor o usuarios prioritarios).

  para **la protección estándar** y la **protección** estricta, se usan reglas con condiciones y excepciones que determinan a quién se aplican o no los perfiles.

  Las condiciones y excepciones disponibles son:

  - **Usuarios**: los buzones, usuarios de correo o contactos de correo especificados de su organización.
  - **Grupos**: los grupos de distribución, los grupos de seguridad habilitados para correo electrónico o los Grupos de Microsoft 365 especificados de la organización.
  - **Dominios**: todos los destinatarios de los [dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados en la organización.

  Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

- **Protección integrada (solo** Defender para Office 365): un perfil que habilita la protección de Caja fuerte vínculos y Caja fuerte de datos adjuntos. Esta configuración proporciona de forma eficaz directivas predeterminadas para Caja fuerte vínculos y Caja fuerte datos adjuntos, que nunca tenían directivas predeterminadas.

  > [!NOTE]
  > La **directiva de seguridad preestablecida** de protección integrada está actualmente en Versión preliminar, no está disponible en todas las organizaciones y está sujeta a cambios.

  Para **la protección integrada,** la directiva de seguridad preestablecida está predeterminada para todos los clientes de Defender Office 365 cliente. Aunque no se recomienda, también puede configurar excepciones basadas  en **Usuarios,** Grupos y Dominios para que la protección no se aplique a usuarios específicos.

Hasta que asigne las directivas a  los usuarios, las directivas de seguridad predeterminadas **Estándar** y Estricto no se asignan a nadie. En cambio, la **directiva de seguridad** preestablecida de protección integrada se asigna a todos los destinatarios de forma predeterminada, pero puede configurar excepciones.

### <a name="policies-in-preset-security-policies"></a>Directivas en directivas de seguridad preestablecidas

Las directivas de seguridad predefinidas usan las directivas correspondientes de las distintas características de protección de EOP y Microsoft Defender para Office 365. Estas directivas se crean _después de asignar_ las **directivas** de seguridad predeterminadas protección **estándar** o Protección estricta a los usuarios. No puede modificar la configuración de estas directivas.

- **Exchange Online Protection (EOP):** esto incluye organizaciones Microsoft 365 con buzones de correo Exchange Online y organizaciones independientes de EOP sin Exchange Online buzones de correo:

  - [Directivas contra correo no deseado](configure-your-spam-filter-policies.md) **denominadas Standard Preset Security Policy** y Strict Preset Security **Policy**.
  - [Directivas antimalware](configure-anti-malware-policies.md) **denominadas Standard Preset Security Policy** y Strict Preset Security **Policy**.
  - [Directivas contra suplantación de identidad de EOP](set-up-anti-phishing-policies.md#spoof-settings) **denominadas Standard Preset Security Policy** y Strict Preset Security **Policy** (configuración de suplantación de identidad).

- **Directivas de Microsoft Defender para Office 365:** esto incluye organizaciones con Microsoft 365 E5 o Defender para Office 365 de complementos:
  - Las directivas contra suplantación de identidad en Microsoft Defender para Office 365 denominada **Standard Preset Security Policy** y Strict Preset Security **Policy**, que incluyen:
    - La misma [configuración de suplantación](set-up-anti-phishing-policies.md#spoof-settings) de identidad que están disponibles en las directivas contra suplantación de identidad de EOP.
    - [Configuración de suplantación](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Umbrales avanzados de phishing](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - [Caja fuerte vincula directivas](set-up-safe-links-policies.md) **denominadas Standard Preset Security Policy**, Strict Preset Security **Policy** y **Built-in Protection Policy**.
  - [Caja fuerte de datos adjuntos](set-up-safe-attachments-policies.md) **denominados Standard Preset Security Policy**, Strict Preset Security **Policy** y **Built-in Protection Policy**.

Puede aplicar protecciones de EOP a diferentes usuarios que Microsoft Defender para Office 365 protección.

### <a name="policy-settings-in-preset-security-policies"></a>Configuración de directivas en directivas de seguridad preestablecidas

No puede modificar la configuración de directiva en los perfiles de protección. Los **valores de**  configuración de directiva de protección estándar, estricto y integrado se describen en Configuración recomendada para EOP y Microsoft Defender para Office 365 [seguridad.](recommended-settings-for-eop-and-office365.md) 

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Orden de prioridad para las directivas de seguridad preestablecidas y otras directivas

Cuando se aplican varias directivas a un usuario, se aplica el siguiente orden de prioridad máxima a prioridad más baja:

1. **Directiva de seguridad** preestablecida de protección estricta
2. **Directiva de seguridad** preestablecida de protección estándar
3. Directivas de seguridad personalizadas
4. **Directiva de seguridad predefinida de protección** integrada y directivas de seguridad predeterminadas

En otras palabras, la configuración de la  directiva de protección estricta invalida la configuración de la directiva de  protección estándar, que invalida la configuración de una directiva personalizada, que invalida la configuración de la directiva de seguridad preestablecida de protección integrada (vínculos Caja fuerte y datos adjuntos de Caja fuerte) y la directiva predeterminada (correo no deseado, antimalware y anti phishing). 

Por ejemplo, si existe una configuración de seguridad  en protección estándar y  un administrador ha habilitado la protección estándar para un usuario, la configuración de protección estándar se aplicará en lugar de lo que está configurado para esa configuración en una directiva personalizada o en la directiva predeterminada (para el mismo usuario).  Tenga en cuenta que es posible que tenga una  parte  de su organización a la que desee aplicar solo la directiva de protección estándar o estricta mientras aplica una directiva personalizada a otros usuarios de su organización para satisfacer necesidades específicas.

**La protección integrada no** afecta a los destinatarios de las directivas Caja fuerte vínculos o Caja fuerte datos adjuntos existentes. Si ya ha configurado directivas  de protección estándar, protección estricta o vínculos de  Caja fuerte  personalizados o datos adjuntos de Caja fuerte, dichas directivas siempre se aplican antes de la protección **integrada,** por lo que no hay ningún impacto en los destinatarios que ya están definidos en esas directivas predefinidas o personalizadas existentes. 

## <a name="assign-preset-security-policies-to-users"></a>Asignar directivas de seguridad preestablecidas a los usuarios

### <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Directivas de seguridad preestablecidas,** use <https://security.microsoft.com/presetSecurityPolicies> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Debe tener permisos asignados en la **Exchange Online** antes de poder realizar los procedimientos de este artículo:
  - Para configurar directivas de seguridad preestablecidas, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.
  - Para obtener acceso de solo lectura a directivas de seguridad preestablecidas, debe ser miembro del grupo de roles **Lector** global.

  Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Nota:** Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos y permisos necesarios para _otras_ características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

### <a name="use-the-microsoft-365-defender-portal-to-assign-standard-and-strict-preset-security-policies-to-users"></a>Usar el portal Microsoft 365 Defender para asignar directivas de seguridad predeterminadas estándar y estrictas a los usuarios

1. En el portal de Microsoft 365 Defender en , vaya a Correo electrónico & directivas de colaboración & Reglas de amenazas Preestablecidas Directivas de seguridad en la <https://security.microsofot.com>  \>  \>  \>  **sección Directivas con** plantilla. Para ir directamente a la página **Directivas de seguridad preestablecidas,** use <https://security.microsoft.com/presetSecurityPolicies> .

2. En la **página Directivas de seguridad preestablecidas,** haga clic en **Administrar** en las secciones **Protección estándar** **o** Protección estricta.

3. El **Asistente para aplicar protección estándar** o Aplicar protección **estricta** comienza en un control desplegable. En la **página Las protecciones de EOP** se aplican a la página, identifique los destinatarios internos a los que se aplican las protecciones [de EOP](#policies-in-preset-security-policies) (condiciones de destinatario):
   - **Users**
   - **Grupos**
   - **Dominios**

   Haga clic en el cuadro correspondiente, comience a escribir un valor y seleccione el valor que desee de los resultados. Repita este proceso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Icono Quitar.](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

   Para los usuarios o grupos, puede utilizar la mayoría de los identificadores (nombre, nombre para mostrar, alias, dirección de correo electrónico, nombre de la cuenta, etc.), pero el nombre para mostrar correspondiente se muestra en los resultados. Para los usuarios, introduzca un asterisco (\*) por sí mismo para ver todos los valores disponibles.

   - **Excluir estos usuarios, grupos y dominios**: para agregar excepciones para los destinatarios internos a los que se aplica la directiva (excepciones de destinatarios), seleccione esta opción y configure las excepciones. La configuración y el comportamiento son exactamente iguales a las condiciones.

   Cuando termine, haga clic en **Siguiente**.

4. En Microsoft Defender para organizaciones de Office 365, te llevaremos **a defender** para que las protecciones de Office 365 se apliquen a la página para identificar los destinatarios internos a los que se aplican las protecciones de Office 365 de Microsoft [Defender](#policies-in-preset-security-policies) (condiciones de destinatario).

   La configuración y el comportamiento son exactamente iguales a las protecciones **de EOP que** se aplican a la página en el paso anterior.

   Cuando termine, haga clic en **Siguiente**.

5. En la **página Revisar y confirmar los cambios,** compruebe las selecciones y, a continuación, haga clic en **Confirmar**.

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-standard-and-strict-preset-security-policies"></a>Usar el portal de Microsoft 365 Defender para modificar las asignaciones de directivas de seguridad predeterminadas estándar y estricta

Los pasos para modificar la asignación de la **directiva** de seguridad preestablecida de protección estándar o protección estricta son los mismos que cuando se asignaron inicialmente las directivas de seguridad preestablecidas [a los usuarios.](#use-the-microsoft-365-defender-portal-to-assign-standard-and-strict-preset-security-policies-to-users) 

Para deshabilitar las  **directivas** de seguridad preestablecidas de protección estándar o protección estricta mientras se conservan las condiciones y excepciones existentes, deslice el botón de alternancia a **Desactivado** ![ deshabilitado. ](../../media/scc-toggle-off.png) . Para habilitar las directivas, deslice el botón de alternancia a **Activado** ![ activar ](../../media/scc-toggle-on.png) .

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-the-built-in-protection-preset-security-policy"></a>Use el portal Microsoft 365 Defender para modificar las asignaciones de la directiva de seguridad preestablecida de protección integrada

Recuerde que la directiva de seguridad preestablecida de protección integrada se asigna a todos  los  destinatarios y no afecta a los destinatarios definidos en las directivas de seguridad predeterminadas de protección estándar o protección estricta, ni en las directivas de vínculos de Caja fuerte personalizadas o datos adjuntos Caja fuerte. 

Por lo tanto, normalmente no recomendamos excepciones a la **directiva de** seguridad preestablecida de protección integrada.

1. En el portal de Microsoft 365 Defender en , vaya a Correo electrónico & directivas de colaboración & Reglas de amenazas Preestablecidas Directivas de seguridad en la <https://security.microsofot.com>  \>  \>  \>  **sección Directivas con** plantilla. Para ir directamente a la página **Directivas de seguridad preestablecidas,** use <https://security.microsoft.com/presetSecurityPolicies> .

2. En la **página Directivas de seguridad preestablecidas,** seleccione Agregar **exclusiones (no recomendadas)** en **la** sección Protección integrada.

3. En **el** control desplegable Excluir de la protección integrada que aparece, identifique los destinatarios internos que se excluyen de la protección integrada Caja fuerte vínculos y Caja fuerte datos adjuntos:
   - **Users**
   - **Grupos**
   - **Dominios**

   Haga clic en el cuadro correspondiente, comience a escribir un valor y seleccione el valor que desee de los resultados. Repita este proceso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Icono Quitar.](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

   Para los usuarios o grupos, puede utilizar la mayoría de los identificadores (nombre, nombre para mostrar, alias, dirección de correo electrónico, nombre de la cuenta, etc.), pero el nombre para mostrar correspondiente se muestra en los resultados. Para los usuarios, introduzca un asterisco (\*) por sí mismo para ver todos los valores disponibles.

   Cuando haya terminado, haga clic en **Guardar**.

### <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha asignado  correctamente  la directiva de protección estándar o de seguridad de protección  estricta a un usuario,  use una configuración de protección en la que el valor predeterminado sea diferente de la configuración de protección estándar, que es diferente de la configuración de protección estricta.

Por ejemplo, para el correo electrónico detectado como correo no deseado (no correo no  deseado de elevada confianza) compruebe que el mensaje se entregue a la carpeta correo no deseado para los usuarios de protección estándar y se ponga en cuarentena para los usuarios de protección **estricta.**

O bien, en el caso del correo [masivo,](bulk-complaint-level-values.md)compruebe que el valor  de BCL 6 o posterior entrega el mensaje  a la carpeta correo no deseado para los usuarios de protección estándar y el valor de BCL 4 o superior pone en cuarentena el mensaje para usuarios de protección estricta.
