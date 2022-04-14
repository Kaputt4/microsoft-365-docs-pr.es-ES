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
description: Los administradores pueden aprender a aplicar la configuración de directiva estándar y estricta en las características de protección de Exchange Online Protection (EOP) y Microsoft Defender para Office 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a74fce0242f0206218d6f7f2f13e61d9f0a3b6f
ms.sourcegitcommit: a7e1d155939e862337271fbe38bf26f62bd49bdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2022
ms.locfileid: "64847123"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>Directivas de seguridad preestablecidas en Exchange Online Protection y Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Las directivas de seguridad preestablecidas proporcionan una ubicación centralizada para aplicar todas las directivas recomendadas de spam, malware y phishing a los usuarios a la vez. La configuración de directiva no se puede configurar. En su lugar, los establecemos nosotros y se basan en nuestras observaciones y experiencias en los centros de datos para lograr un equilibrio entre mantener el contenido dañino alejado de los usuarios y evitar interrupciones innecesarias.

En el resto de este artículo se describen las directivas de seguridad preestablecidas y cómo configurarlas.

## <a name="what-preset-security-policies-are-made-of"></a>De qué directivas de seguridad preestablecidas están hechas

Las directivas de seguridad preestablecidas constan de los siguientes elementos:

- Perfiles
- Directivas
- Configuración de la directiva

Además, el orden de precedencia es importante si se aplican varias directivas de seguridad preestablecidas y otras directivas a la misma persona.

### <a name="profiles-in-preset-security-policies"></a>Perfiles en directivas de seguridad preestablecidas

El perfil determina el nivel de protección. Los perfiles siguientes están disponibles:

- **Protección estándar**: un perfil básico de protección adecuado para la mayoría de los usuarios.
- **Protección estricta**: un perfil de protección más agresivo para los usuarios seleccionados (destinos de alto valor o usuarios prioritarios).

  para **protección estándar** y **protección estricta**, se usan reglas con condiciones y excepciones para determinar los destinatarios internos a los que se aplica la directiva (condiciones de destinatario).

  Las condiciones y excepciones disponibles son:

  - **Usuarios**: buzones, usuarios de correo o contactos de correo especificados.
  - **Grupos**:
    - Miembros de los grupos de distribución especificados o grupos de seguridad habilitados para correo.
    - El Grupos de Microsoft 365 especificado.
  - **Dominios**: todos los destinatarios de los [dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados en la organización.

  Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

- **Protección integrada** (solo Defender para Office 365): perfil que habilita solo Caja fuerte vínculos y Caja fuerte protección de datos adjuntos. Este perfil proporciona de forma eficaz directivas predeterminadas para Caja fuerte Vínculos y datos adjuntos de Caja fuerte, que nunca tenían directivas predeterminadas.

  Para **la protección integrada**, la directiva de seguridad preestablecida está activada de forma predeterminada para todos los clientes Defender para Office 365. Aunque no se recomienda, también puede configurar excepciones basadas en **usuarios**, **grupos** y **dominios** para que la protección no se aplique a usuarios específicos.

Hasta que asigne las directivas a los usuarios, las directivas de seguridad preestablecidas **Estándar** y **Estricta** no se asignan a nadie. Por el contrario, la directiva de seguridad preestablecida **de protección integrada** se asigna a todos los destinatarios de forma predeterminada, pero puede configurar excepciones.

### <a name="policies-in-preset-security-policies"></a>Directivas en directivas de seguridad preestablecidas

Las directivas de seguridad preestablecidas usan las directivas correspondientes de las distintas características de protección de EOP y Microsoft Defender para Office 365. Estas directivas se crean _después de_ asignar las directivas de seguridad preestablecidas **Protección estándar** o **Protección estricta** a los usuarios. No puede modificar la configuración de estas directivas.

- **directivas de Exchange Online Protection (EOP**): esto incluye Microsoft 365 organizaciones con buzones de Exchange Online y organizaciones EOP independientes sin Exchange Online buzones:

  - [Directivas contra correo no deseado](configure-your-spam-filter-policies.md) **denominadas Directiva de seguridad preestablecida estándar** y **Directiva de seguridad preestablecida estricta**.
  - [Directivas antimalware](configure-anti-malware-policies.md) **denominadas Directiva de seguridad preestablecida estándar** y **Directiva de seguridad preestablecida estricta**.
  - [Directivas de protección contra suplantación de identidad (EOP)](set-up-anti-phishing-policies.md#spoof-settings) **denominadas Directiva de seguridad preestablecida estándar** y **Directiva de seguridad preestablecida estricta** (configuración de suplantación de identidad).

- **directivas de Microsoft Defender para Office 365**: esto incluye organizaciones con suscripciones de complemento de Microsoft 365 E5 o Defender para Office 365:
  - Las directivas contra suplantación de identidad en Microsoft Defender para Office 365 **denominadas Directiva de seguridad preestablecida estándar** y **Directiva de seguridad preestablecida estricta**, que incluyen:
    - La misma [configuración de suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings) que está disponible en las directivas de protección contra suplantación de identidad (EOP).
    - [Configuración de suplantación](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Umbrales avanzados de phishing](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - [Caja fuerte Vincula directivas](set-up-safe-links-policies.md) denominadas **Directiva de seguridad preestablecida estándar**, **Directiva de seguridad preestablecida estricta** y Directiva **de protección integrada**.
  - [Caja fuerte directivas de datos adjuntos](set-up-safe-attachments-policies.md) **denominadas Directiva de seguridad preestablecida estándar**, **Directiva de seguridad preestablecida estricta** y Directiva **de protección integrada**.

Puede aplicar protecciones EOP a usuarios diferentes de las protecciones de Microsoft Defender para Office 365.

### <a name="policy-settings-in-preset-security-policies"></a>Configuración de directivas en directivas de seguridad preestablecidas

No se puede modificar la configuración de directiva en los perfiles de protección. Los valores de configuración de directiva de protección **estándar**, **estricta** y integrada se describen **en** [Configuración recomendada para EOP y Microsoft Defender para Office 365 seguridad](recommended-settings-for-eop-and-office365.md).

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Orden de precedencia de las directivas de seguridad preestablecidas y otras directivas

Cuando se aplican varias directivas a un usuario, el orden siguiente se aplica de la prioridad más alta a la prioridad más baja:

1. Directiva de seguridad preestablecida **de protección estricta**
2. Directiva de seguridad preestablecida **de protección estándar**
3. Directivas de seguridad personalizadas
4. Directiva de seguridad preestablecida **de protección integrada** y directivas de seguridad predeterminadas

En otras palabras, la configuración de la directiva de **protección estricta** invalida la configuración de la directiva de **protección estándar**, que invalida la configuración de una directiva personalizada, que invalida la configuración de la directiva de seguridad preestablecida **de protección integrada** (Caja fuerte Vínculos y datos adjuntos Caja fuerte) y la directiva predeterminada (antispam, antimalware y anti phishing).

Por ejemplo, si existe una configuración de seguridad en **Protección estándar** y un administrador ha habilitado la **protección estándar** para un usuario, se aplicará la configuración **Protección estándar** en lugar de lo que está configurado para esa configuración en una directiva personalizada o en la directiva predeterminada (para el mismo usuario). Tenga en cuenta que es posible que tenga alguna parte de la organización a la que quiera aplicar solo la directiva **de protección estándar** o **estricta** mientras aplica una directiva personalizada a otros usuarios de la organización para satisfacer necesidades específicas.

**La protección integrada** no afecta a los destinatarios de las directivas de vínculos de Caja fuerte o datos adjuntos de Caja fuerte existentes. Si ya ha configurado la **protección estándar**, **la protección estricta** o las directivas de vínculos de Caja fuerte personalizados o de datos adjuntos de Caja fuerte, esas directivas _siempre_ se aplican _antes_ de la **protección integrada**, por lo que no hay ningún impacto en los destinatarios que ya están definidos en esas directivas preestablecidas o personalizadas existentes.

## <a name="assign-preset-security-policies-to-users"></a>Asignación de directivas de seguridad preestablecidas a los usuarios

### <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Directivas de seguridad preestablecidas** , use <https://security.microsoft.com/presetSecurityPolicies>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Debe tener permisos asignados en la **Exchange Online** antes de poder realizar los procedimientos de este artículo:
  - Para configurar directivas de seguridad preestablecidas, debe ser miembro de los grupos de roles **Administración de la organización** o **Administrador de seguridad** .
  - Para el acceso de solo lectura a las directivas de seguridad preestablecidas, debe ser miembro del grupo de roles **Lector global** .

  Para obtener más información, vea los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Nota**: Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos _y_ permisos necesarios para otras características de Microsoft 365. Para más información, consulte[Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

### <a name="use-the-microsoft-365-defender-portal-to-assign-standard-and-strict-preset-security-policies-to-users"></a>Use el portal de Microsoft 365 Defender para asignar directivas de seguridad preestablecidas estándar y estricta a los usuarios

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas de colaboración** \> & correo electrónico **& Directivas de** **amenazas** \> de reglas \> **Directivas de seguridad preestablecidas** en la sección **Directivas con plantilla**. Para ir directamente a la página **Directivas de seguridad preestablecidas** , use <https://security.microsoft.com/presetSecurityPolicies>.

2. En la página **Directivas de seguridad preestablecidas** , haga clic en **Administrar** en las secciones **Protección estándar** o **Protección estricta** .

3. El asistente **Aplicar protección estándar** o **Aplicar protección estricta** se inicia en un control flotante. En la página **Protecciones EOP se aplican a** , identifique los destinatarios internos a los que se aplican [las protecciones EOP](#policies-in-preset-security-policies) (condiciones de destinatario):
   - **Usuarios**
   - **Grupos**
   - **Dominios**

   Haga clic en el cuadro correspondiente, comience a escribir un valor y seleccione el valor que desee de los resultados. Repita este proceso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Icono Quitar.](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

   Para los usuarios o grupos, puede utilizar la mayoría de los identificadores (nombre, nombre para mostrar, alias, dirección de correo electrónico, nombre de la cuenta, etc.), pero el nombre para mostrar correspondiente se muestra en los resultados. Para los usuarios, introduzca un asterisco (\*) por sí mismo para ver todos los valores disponibles.

   - **Excluir estos usuarios, grupos y dominios**: para agregar excepciones para los destinatarios internos a los que se aplica la directiva (excepciones de destinatarios), seleccione esta opción y configure las excepciones. La configuración y el comportamiento son exactamente iguales a las condiciones.

   Cuando termine, haga clic en **Siguiente**.

4. En Microsoft Defender para Office 365 organizaciones, se le llevará a la página **de Defender para Office 365 protecciones** para identificar los destinatarios internos a los que se aplican las [protecciones de Microsoft Defender para Office 365](#policies-in-preset-security-policies). a (condiciones de destinatario).

   La configuración y el comportamiento son exactamente iguales **que las protecciones de EOP que se aplican a** la página del paso anterior.

   Cuando termine, haga clic en **Siguiente**.

5. En la página **Revisar y confirmar los cambios** , compruebe las selecciones y haga clic en **Confirmar**.

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-standard-and-strict-preset-security-policies"></a>Use el portal de Microsoft 365 Defender para modificar las asignaciones de directivas de seguridad preestablecidas estándar y estricta.

Los pasos para modificar la asignación de la directiva de seguridad preestablecida **protección estándar** o **protección estricta** son los mismos que cuando [se asignaron inicialmente las directivas de seguridad preestablecidas a los usuarios](#use-the-microsoft-365-defender-portal-to-assign-standard-and-strict-preset-security-policies-to-users).

Para deshabilitar las directivas de seguridad preestablecidas **Protección estándar** o **Protección estricta** mientras conserva las condiciones y excepciones existentes, deslice el botón de alternancia a **Desactivado**](../../media/scc-toggle-off.png) deshabilitado![. Para habilitar las directivas, deslice el botón de alternancia a **Activado**![.](../../media/scc-toggle-on.png)

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-the-built-in-protection-preset-security-policy"></a>Use el portal de Microsoft 365 Defender para modificar las asignaciones de la directiva de seguridad preestablecida de protección integrada.

Recuerde que la directiva de seguridad preestablecida **de protección integrada** se asigna a todos los destinatarios y no afecta a los destinatarios definidos en las directivas de seguridad preestablecidas **Protección estándar** o **Protección estricta**, ni a las directivas personalizadas de vínculos Caja fuerte o Caja fuerte datos adjuntos.

Por lo tanto, normalmente no se recomiendan excepciones a la directiva de seguridad preestablecida **de protección integrada** .

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas de colaboración** \> & correo electrónico **& Directivas de** **amenazas** \> de reglas \> **Directivas de seguridad preestablecidas** en la sección **Directivas con plantilla**. Para ir directamente a la página **Directivas de seguridad preestablecidas** , use <https://security.microsoft.com/presetSecurityPolicies>.

2. En la página **Directivas de seguridad preestablecidas** , seleccione **Agregar exclusiones (no recomendadas)** en la sección **Protección integrada** .

3. En el control flotante **Excluir de la protección integrada** que aparece, identifique los destinatarios internos que se excluyen de la protección integrada Caja fuerte Links y Caja fuerte Attachments:
   - **Usuarios**
   - **Grupos**
   - **Dominios**

   Haga clic en el cuadro correspondiente, comience a escribir un valor y seleccione el valor que desee de los resultados. Repita este proceso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Icono Quitar.](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

   Para los usuarios o grupos, puede utilizar la mayoría de los identificadores (nombre, nombre para mostrar, alias, dirección de correo electrónico, nombre de la cuenta, etc.), pero el nombre para mostrar correspondiente se muestra en los resultados. Para los usuarios, introduzca un asterisco (\*) por sí mismo para ver todos los valores disponibles.

   Cuando haya terminado, haga clic en **Guardar**.

### <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha asignado correctamente la directiva de seguridad **Protección estándar** o **Protección estricta** a un usuario, use una configuración de protección en la que el valor predeterminado sea diferente de la configuración **Protección estándar** , que es diferente a la configuración **Protección estricta** .

Por ejemplo, para el correo electrónico que se detecta como correo no deseado (no correo no deseado de alta confianza), compruebe que el mensaje se entrega a la carpeta Correo electrónico no deseado para los usuarios de **protección estándar** y en cuarentena para los usuarios **de protección estricta** .

O bien, en el [caso del correo masivo](bulk-complaint-level-values.md), compruebe que el valor de BCL 6 o superior entrega el mensaje a la carpeta Correo no deseado para los usuarios de **protección estándar** , y el valor BCL 4 o superior pone en cuarentena el mensaje para los usuarios **de protección estricta** .
