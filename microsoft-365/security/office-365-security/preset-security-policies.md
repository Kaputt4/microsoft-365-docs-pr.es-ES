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
- m365-security
ms.custom: ''
description: Los administradores pueden aprender a aplicar la configuración de directiva estándar y estricta en las características de protección de Exchange Online Protection (EOP) y Microsoft Defender para Office 365
ms.subservice: mdo
ms.service: microsoft-365-security
search.appverid: met150
ms.openlocfilehash: b28c315ecfe8ee6513c8f45be6d89953d4908647
ms.sourcegitcommit: 0ca3ab2abe07810e9b2cc2d806e3c6b9f35b146c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2022
ms.locfileid: "68684766"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>Directivas de seguridad preestablecidas en Exchange Online Protection y Microsoft Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

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

  - **Usuarios**: los buzones de correo, los usuarios de correo o los contactos de correo especificados.
  - **Grupos**:
    - Miembros de los grupos de distribución o grupos de seguridad habilitados para correo especificados.
    - Los Grupos de Microsoft 365 especificados.

    > [!NOTE]
    >  No se admiten grupos de distribución dinámicos.

  - **Dominios**: todos los destinatarios de los [dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados en la organización.

  Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

  > [!IMPORTANT]
  > Los diferentes tipos de condiciones o excepciones no son aditivos; son inclusivos. La directiva de seguridad preestablecida _solo_ se aplica a los destinatarios que coinciden _con todos los_ filtros de destinatarios especificados. Por ejemplo, se configura una condición de filtro de destinatario en la directiva con los siguientes valores:
  >
  > - Usuarios: romain@contoso.com
  > - Grupos: Ejecutivos
  >
  > La directiva se aplica a romain@contoso.com _solo_ si también es miembro del grupo de Ejecutivos. Si no es miembro del grupo, la directiva no se le aplica.
  >
  > Asimismo, si utiliza el mismo filtro de destinatarios como excepción a la directiva, esta no se aplica a romain@contoso.com _solo_ si también es miembro del grupo de Ejecutivos. Si no es miembro del grupo, la directiva se le sigue aplicando.

- **Protección integrada** (solo Defender para Office 365): perfil que habilita solo la protección de vínculos seguros y datos adjuntos seguros. Este perfil proporciona de forma eficaz directivas predeterminadas para vínculos seguros y datos adjuntos seguros, que nunca tenían directivas predeterminadas.

  Para **la protección integrada**, la directiva de seguridad preestablecida está activada de forma predeterminada para todos los clientes Defender para Office 365. Aunque no se recomienda, también puede configurar excepciones basadas en **usuarios**, **grupos** y **dominios** para que la protección no se aplique a usuarios específicos.

Hasta que asigne las directivas a los usuarios, las directivas de seguridad preestablecidas **Estándar** y **Estricta** no se asignan a nadie. Por el contrario, la directiva de seguridad preestablecida **de protección integrada** se asigna a todos los destinatarios de forma predeterminada, pero puede configurar excepciones.

### <a name="policies-in-preset-security-policies"></a>Directivas en directivas de seguridad preestablecidas

Las directivas de seguridad preestablecidas usan las directivas correspondientes de las distintas características de protección de EOP y Microsoft Defender para Office 365. Estas directivas se crean _después de_ asignar las directivas de seguridad preestablecidas **Protección estándar** o **Protección estricta** a los usuarios. No puede modificar la configuración de estas directivas.

- **directivas de Exchange Online Protection (EOP):** estas directivas se encuentran en todas las organizaciones de Microsoft 365 con buzones de Exchange Online y organizaciones EOP independientes sin buzones de correo Exchange Online:

  - [Directivas contra correo no deseado](configure-your-spam-filter-policies.md) **denominadas Directiva de seguridad preestablecida estándar** y **Directiva de seguridad preestablecida estricta**.
  - [Directivas antimalware](configure-anti-malware-policies.md) **denominadas Directiva de seguridad preestablecida estándar** y **Directiva de seguridad preestablecida estricta**.
  - [Directivas contra suplantación de identidad (protección contra suplantación de identidad)](set-up-anti-phishing-policies.md#spoof-settings) **denominadas Directiva de seguridad preestablecida estándar** y **Directiva de seguridad preestablecida estricta** (configuración de suplantación de identidad).

  > [!NOTE]
  > Las directivas de correo no deseado saliente no forman parte de las directivas de seguridad preestablecidas. La directiva de correo no deseado saliente predeterminada protege automáticamente a los miembros de las directivas de seguridad preestablecidas. O bien, puede crear directivas de correo no deseado de salida personalizadas para personalizar la protección de los miembros de las directivas de seguridad preestablecidas. Para obtener más información, consulte [Configuración del filtrado de correo no deseado saliente en EOP](configure-the-outbound-spam-policy.md).

- **directivas de Microsoft Defender para Office 365**: estas directivas se encuentran en organizaciones con suscripciones de complementos de Microsoft 365 E5 o Defender para Office 365:
  - Las directivas contra suplantación de identidad en Defender para Office 365 **denominadas Directiva de seguridad preestablecida estándar** y **Directiva de seguridad preestablecida estricta**, que incluyen:
    - La misma [configuración de suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings) que está disponible en las directivas de protección contra suplantación de identidad (EOP).
    - [Configuración de suplantación](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Umbrales avanzados de phishing](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - [Directivas de vínculos seguros](set-up-safe-links-policies.md) **denominadas Directiva de seguridad preestablecida estándar**, **Directiva de seguridad preestablecida estricta** y Directiva **de protección integrada**.
  - [Directivas de datos adjuntos seguros](set-up-safe-attachments-policies.md) **denominadas Directiva de seguridad preestablecida estándar**, **Directiva de seguridad preestablecida estricta** y Directiva **de protección integrada**.

Puede aplicar protecciones EOP a usuarios diferentes de las protecciones de Defender para Office 365, o bien puede aplicar EOP y Defender para Office 365 a los mismos destinatarios.

### <a name="policy-settings-in-preset-security-policies"></a>Configuración de directivas en directivas de seguridad preestablecidas

No se puede modificar la configuración de directiva en los perfiles de protección. Los valores de configuración de directiva de protección **estándar**, **estricta** y integrada se describen **en** [Configuración recomendada para EOP y Microsoft Defender para Office 365 seguridad](recommended-settings-for-eop-and-office365.md).

> [!NOTE]
> En Defender para Office 365 protecciones, debe identificar los remitentes para la [protección de suplantación de usuario](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) y los dominios internos o externos para la [protección de suplantación de dominio](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).
>
> Todos los dominios que posee ([dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) reciben automáticamente protección de suplantación de dominio en directivas de seguridad preestablecidas.
>
> Todos los destinatarios reciben automáticamente protección de suplantación de [la inteligencia del buzón de correo](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) en las directivas de seguridad preestablecidas.

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Orden de precedencia de las directivas de seguridad preestablecidas y otras directivas

Cuando se aplican varias directivas a un usuario, el orden siguiente se aplica de la prioridad más alta a la prioridad más baja:

1. Directiva de seguridad preestablecida estricta.
2. Directiva de seguridad preestablecida estándar.
3. Directivas personalizadas. Las directivas personalizadas se aplican en función del valor de prioridad de la directiva.
4. Directiva de seguridad preestablecida de protección integrada para vínculos seguros y datos adjuntos seguros; directivas predeterminadas para el antimalware, el correo no deseado y la suplantación de identidad (phishing).

En otras palabras, la configuración de la directiva de seguridad preestablecida **Estricta** invalida la configuración de la directiva de seguridad preestablecida **Estándar** , que invalida la configuración de cualquier directiva personalizada, que invalida la configuración de la directiva de seguridad preestablecida **de protección integrada** para vínculos seguros y datos adjuntos seguros, y las directivas predeterminadas para antispam, antimalware y anti phishing.

Por ejemplo, existe una configuración de seguridad en **Protección estándar** y un administrador especifica un usuario para **la protección estándar**. La configuración **protección estándar** se aplica al usuario en lugar de a lo que se ha configurado para esa configuración en una directiva personalizada o en la directiva predeterminada para el mismo usuario.

Es posible que quiera aplicar las directivas de seguridad preestablecidas **Estándar** o **Estricta** a un subconjunto de usuarios y aplicar directivas personalizadas a otros usuarios de la organización para satisfacer necesidades específicas. Para cumplir este requisito, siga estos pasos:

- Configure los usuarios que deben obtener la configuración de la directiva de seguridad preestablecida **estándar** y las directivas personalizadas como excepciones en la directiva de seguridad preestablecida **Strict** .
- Configure los usuarios que deben obtener la configuración de las directivas personalizadas como excepciones en la directiva de seguridad preestablecida **estándar** .

**La protección integrada** no afecta a los destinatarios de las directivas de vínculos seguros o datos adjuntos seguros existentes. Si ya ha configurado la **protección estándar**, protección **estricta** o vínculos seguros personalizados o directivas de datos adjuntos seguros, esas directivas _siempre_ se aplican _antes_ de la **protección integrada**, por lo que no hay ningún impacto en los destinatarios que ya están definidos en esas directivas preestablecidas o personalizadas existentes.

## <a name="assign-preset-security-policies-to-users"></a>Asignación de directivas de seguridad preestablecidas a los usuarios

### <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Directivas de seguridad preestablecidas** , use <https://security.microsoft.com/presetSecurityPolicies>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Debe tener permisos asignados en la **Exchange Online** antes de poder realizar los procedimientos de este artículo:
  - Para configurar directivas de seguridad preestablecidas, debe ser miembro de los grupos de roles **Administración de la organización** o **Administrador de seguridad** .
  - Para el acceso de solo lectura a las directivas de seguridad preestablecidas, debe ser miembro del grupo de roles **Lector global** .

  Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Nota**: Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos _y_ permisos necesarios para otras características de Microsoft 365. Para más información, consulte[Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

### <a name="use-the-microsoft-365-defender-portal-to-assign-standard-and-strict-preset-security-policies-to-users"></a>Use el portal de Microsoft 365 Defender para asignar directivas de seguridad preestablecidas estándar y estricta a los usuarios

1. En el portal de Microsoft 365 Defender de <https://security.microsoft.com>, vaya a Email & Directivas de **colaboración** \> **& Directivas de amenazas**  \> de reglas \> **Directivas de seguridad preestablecidas** en la sección **Directivas con plantilla**. Para ir directamente a la página **Directivas de seguridad preestablecidas** , use <https://security.microsoft.com/presetSecurityPolicies>.

2. En la página **Directivas de seguridad preestablecidas** , haga clic en **Administrar** en las secciones **Protección estándar** o **Protección estricta** .

3. El asistente **Aplicar protección estándar** o **Aplicar protección estricta** se inicia en un control flotante.

   En la página **Aplicar Exchange Online Protection**, identifique los destinatarios internos a los que se aplican [las protecciones EOP](#policies-in-preset-security-policies) (condiciones de destinatario):
   - **Todos los destinatarios**
   - **Destinatarios específicos**:
     - **Usuarios**
     - **Grupos**:
       - Miembros de los grupos de distribución o grupos de seguridad habilitados para correo especificados.
       - Los Grupos de Microsoft 365 especificados.

       No se admiten grupos de distribución dinámicos.

   - **Dominios**

     Haga clic en el cuadro correspondiente, comience a escribir un valor y seleccione el valor que desee de los resultados. Repita este proceso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Icono Quitar.](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

     For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results. For users, enter an asterisk (\*) by itself to see all available values.

   - **Ninguna**

   - **Excluir estos destinatarios**: para agregar excepciones para los destinatarios internos a los que se aplica la directiva (excepciones de destinatarios), seleccione esta opción y configure las excepciones. La configuración y el comportamiento se muestran exactamente igual que las condiciones.

   Cuando termine, haga clic en **Siguiente**.

   > [!NOTE]
   > En las organizaciones sin Defender para Office 365, hacer clic en **Siguiente** le lleva a la página **Revisar**. Los pasos o páginas restantes antes de la página **Revisar** solo están disponibles en organizaciones con Defender para Office 365.

4. En la página **Aplicar protección Defender para Office 365**, identifique los destinatarios internos a los que se aplican [las protecciones de Defender para Office 365](#policies-in-preset-security-policies) (condiciones de destinatario).

   La configuración y el comportamiento son exactamente iguales **que las protecciones de EOP que se aplican a** la página del paso anterior.

   También puede seleccionar **Destinatarios seleccionados previamente** para usar los mismos destinatarios que seleccionó para la protección de EOP en la página anterior.

   Cuando termine, haga clic en **Siguiente**.

5. En la página **Protección contra suplantación** , haga clic en **Siguiente**.

6. En la página **Agregar direcciones de correo electrónico para marcar cuando los atacantes suplantan, agregue remitentes** internos y externos protegidos por la [protección de suplantación de usuario](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

   > [!NOTE]
   > Todos los destinatarios reciben automáticamente protección de suplantación de [la inteligencia del buzón de correo](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) en las directivas de seguridad preestablecidas.

   Cada entrada consta de un nombre para mostrar y una dirección de correo electrónico. Escriba cada valor en los cuadros y, a continuación, haga clic en **Agregar**. Repita este paso tantas veces como sea necesario.

   Puede especificar un máximo de 301 usuarios y no puede especificar el mismo usuario en la configuración de protección de suplantación de usuario en varias directivas.

   Para quitar una entrada existente de la lista, haga clic en ![Quitar al usuario del icono de protección contra suplantación.](../../media/m365-cc-sc-remove.png).

   Cuando termine, haga clic en **Siguiente**.

7. En la página **Agregar dominios para marcar cuando los atacantes suplantan** , agregue dominios internos y externos protegidos por la [protección de suplantación de dominio](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

   > [!NOTE]
   > Todos los dominios que posee ([dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) reciben automáticamente protección de suplantación de dominio en directivas de seguridad preestablecidas.

   Todos los remitentes de los dominios especificados están protegidos por la protección de suplantación de dominio.

   Escriba el dominio en el cuadro y, a continuación, haga clic en **Agregar**. Repita este paso tantas veces como sea necesario.

   Para quitar una entrada existente de la lista, seleccione la entrada y, a continuación, haga clic en ![Quitar dominio del icono de protección contra suplantación.](../../media/m365-cc-sc-remove.png).

   El número máximo de dominios que puede especificar para la protección de suplantación de dominio en todas las directivas contra suplantación de identidad es 50.

   Cuando termine, haga clic en **Siguiente**.

8. En la página **Add trusted email addresses and domains to not flag as impersonation (Agregar dominios y direcciones de correo electrónico de confianza para no marcar como suplantación** ), escriba las direcciones de correo electrónico del remitente y los dominios que desea excluir de la protección de suplantación. Los mensajes de estos remitentes nunca se marcarán como un ataque de suplantación, pero los remitentes siguen estando sujetos a examen por otros filtros en EOP y Defender para Office 365.

   Escriba la dirección de correo electrónico o el dominio en el cuadro y, a continuación, haga clic en **Agregar**. Repita este paso tantas veces como sea necesario.

   Para quitar una entrada existente de la lista, seleccione la entrada y, a continuación, haga clic en ![Quitar excepciones al icono de protección de suplantación.](../../media/m365-cc-sc-remove.png).

   Cuando termine, haga clic en **Siguiente**.

9. En la página **Revisar y confirmar esta directiva** , compruebe las selecciones y haga clic en **Confirmar**.

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-standard-and-strict-preset-security-policies"></a>Use el portal de Microsoft 365 Defender para modificar las asignaciones de directivas de seguridad preestablecidas estándar y estricta.

Los pasos para modificar la asignación de la directiva de seguridad preestablecida **protección estándar** o **protección estricta** son los mismos que cuando [se asignaron inicialmente las directivas de seguridad preestablecidas a los usuarios](#use-the-microsoft-365-defender-portal-to-assign-standard-and-strict-preset-security-policies-to-users).

Para deshabilitar las directivas de seguridad preestablecidas **Protección estándar** o **Protección estricta** mientras conserva las condiciones y excepciones existentes, deslice el botón de alternancia a **Desactivado**](../../media/scc-toggle-off.png) deshabilitado![. Para habilitar las directivas, deslice el botón de alternancia a **Activado**![.](../../media/scc-toggle-on.png)

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-the-built-in-protection-preset-security-policy"></a>Use el portal de Microsoft 365 Defender para modificar las asignaciones de la directiva de seguridad preestablecida de protección integrada.

Recuerde que la directiva de seguridad preestablecida **de protección integrada** se asigna a todos los destinatarios y no afecta a los destinatarios definidos en las directivas de seguridad preestablecidas **Protección estándar** o **Protección estricta** , ni a las directivas personalizadas de vínculos seguros o datos adjuntos seguros.

Por lo tanto, normalmente no se recomiendan excepciones a la directiva de seguridad preestablecida **de protección integrada** .

1. En el portal de Microsoft 365 Defender de <https://security.microsoft.com>, vaya a Email & Directivas de **colaboración** \> **& Directivas de amenazas**  \> de reglas \> **Directivas de seguridad preestablecidas** en la sección **Directivas con plantilla**. Para ir directamente a la página **Directivas de seguridad preestablecidas** , use <https://security.microsoft.com/presetSecurityPolicies>.

2. En la página **Directivas de seguridad preestablecidas** , seleccione **Agregar exclusiones (no recomendadas)** en la sección **Protección integrada** .

3. En el control flotante **Excluir de la protección integrada** que aparece, identifique los destinatarios internos que se excluyen de la protección integrada de vínculos seguros y datos adjuntos seguros:
   - **Usuarios**
   - **Grupos**:
       - Miembros de los grupos de distribución o grupos de seguridad habilitados para correo especificados.
       - Los Grupos de Microsoft 365 especificados.

     No se admiten grupos de distribución dinámicos.

   - **Dominios**

   Haga clic en el cuadro correspondiente, comience a escribir un valor y seleccione el valor que desee de los resultados. Repita este proceso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Quitar exclusiones del icono de protección integrada.](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

   For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results. For users, enter an asterisk (\*) by itself to see all available values.

   Cuando haya terminado, haga clic en **Guardar**.

### <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha asignado correctamente la directiva de seguridad **Protección estándar** o **Protección estricta** a un usuario, use una configuración de protección en la que el valor predeterminado sea diferente de la configuración **Protección estándar** , que es diferente a la configuración **Protección estricta** .

Por ejemplo, en el caso del correo electrónico que se detecta como correo no deseado (no correo no deseado de alta confianza), compruebe que el mensaje se entrega a la carpeta Junk Email para los usuarios de **protección estándar** y en cuarentena para los usuarios **de protección estricta**.

O bien, en el [caso del correo masivo](bulk-complaint-level-values.md), compruebe que el valor BCL 6 o superior entrega el mensaje a la carpeta junk Email para los usuarios de **protección estándar**, y el valor de BCL 4 o superior pone en cuarentena el mensaje para los usuarios **de protección estricta**.

## <a name="preset-security-policies-in-exchange-online-powershell"></a>Directivas de seguridad preestablecidas en Exchange Online PowerShell

En PowerShell, las directivas de seguridad preestablecidas constan de los siguientes elementos:

- **Directivas de seguridad individuales**: por ejemplo, directivas antimalware, directivas contra correo no deseado, directivas contra phishing, directivas de vínculos seguros y directivas de datos adjuntos seguros.

  > [!WARNING]
  > No intente crear, modificar ni quitar las directivas de seguridad individuales asociadas a las directivas de seguridad preestablecidas. El único método admitido para crear las directivas de seguridad individuales para las directivas de seguridad preestablecidas Estándar o Estricta es activar la directiva de seguridad preestablecida en el portal de Microsoft 365 Defender por primera vez.

- **Reglas**: las reglas independientes para la directiva de seguridad preestablecida estándar, la directiva de seguridad preestablecida Estricta y la directiva de seguridad preestablecida de protección integrada definen las condiciones de destinatario y las excepciones de las directivas (identifique los destinatarios a los que se aplican las protecciones de la directiva).

  En el caso de las directivas de seguridad preestablecidas Estándar y Estricta, estas reglas se crean la primera vez que activa la directiva de seguridad preestablecida en el portal de Microsoft 365 Defender. Si nunca ha activado la directiva de seguridad preestablecida, las reglas asociadas no existen. Al desactivar posteriormente la directiva de seguridad preestablecida, no se eliminan las reglas asociadas.

  La directiva de seguridad preestablecida de protección integrada tiene una sola regla que controla las excepciones a los vínculos seguros predeterminados y la protección de datos adjuntos seguros de la directiva.

  Las directivas de seguridad preestablecidas Estándar y Estricta tienen las siguientes reglas:

  - **Reglas para las protecciones de Exchange Online Protection (EOP):** la regla para la directiva de seguridad preestablecida estándar y la regla para la directiva de seguridad preestablecida estricta controla a quién se aplican las protecciones de EOP en la directiva (antimalware, antispam y anti-phishing) (las condiciones y excepciones de destinatarios para las protecciones EOP).
  - **Reglas para las protecciones de Defender para Office 365**: regla para la directiva de seguridad preestablecida estándar y la regla para los controles de directiva de seguridad preestablecida estricta a los que se aplican las protecciones de Defender para Office 365 en la directiva (vínculos seguros y datos adjuntos seguros) (las condiciones y excepciones del destinatario para Defender para Office 365 protecciones).

  Las reglas de las directivas de seguridad preestablecidas Estándar y Estricta también permiten activar o activar la directiva de seguridad preestablecida habilitando o deshabilitando las reglas asociadas a las directivas.

  Las reglas de las directivas de seguridad preestablecidas no están disponibles para los cmdlets de reglas normales que funcionan para directivas de seguridad individuales (por ejemplo, **Get-AntiPhishRule**). En su lugar, se requieren los siguientes cmdlets:

  - Directiva de seguridad preestablecida de protección integrada: **\*cmdlets -ATPBuiltInProtectionRule** .
  - Directivas de seguridad preestablecidas estándar y estrictas: **\*cmdlets -EOPProtectionPolicyRule** y **\*-ATPProtectionPolicyRule** .

En las secciones siguientes se describe cómo usar estos cmdlets en **escenarios admitidos**.

Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

### <a name="use-powershell-to-view-individual-security-policies-for-preset-security-policies"></a>Uso de PowerShell para ver directivas de seguridad individuales para directivas de seguridad preestablecidas

Recuerde que, si nunca ha activado la directiva de seguridad preestablecida Estándar o la directiva de seguridad preestablecida Estricta en el portal de Microsoft 365 Defender, las directivas de seguridad asociadas para la directiva de seguridad preestablecida no existen.

> [!WARNING]
> No intente crear, modificar ni quitar las directivas de seguridad individuales asociadas a las directivas de seguridad preestablecidas. El único método admitido para crear las directivas de seguridad individuales para las directivas de seguridad preestablecidas Estándar o Estricta es activar la directiva de seguridad preestablecida en el portal de Microsoft 365 Defender por primera vez.

- **Directiva de seguridad preestablecida de protección integrada**: las directivas asociadas se denominan Built-In Directiva de protección. El valor de la propiedad IsBuiltInProtection es True para estas directivas.

  Para ver las directivas de seguridad individuales de la directiva de seguridad preestablecida de protección integrada, ejecute el siguiente comando:

  ```powershell
  Write-Output -InputObject ("`r`n"*3),"Built-in protection Safe Attachments policy",("-"*79);Get-SafeAttachmentPolicy -Identity "Built-In Protection Policy" | Format-List; Write-Output -InputObject ("`r`n"*3),"Built-in protection Safe Links policy",("-"*79);Get-SafeLinksPolicy -Identity "Built-In Protection Policy" | Format-List
  ```

- **Directiva de seguridad preestablecida estándar**: las directivas asociadas se denominan `Standard Preset Security Policy<13-digit number>`. Por ejemplo, `Standard Preset Security Policy1622650008019`. El valor de la propiedad RecommendPolicyType es Standard.

  - **Organizaciones sin Defender para Microsoft 365**:

    Para ver las directivas de seguridad individuales de la directiva de seguridad preestablecida estándar en organizaciones sin Defender para Microsoft 365, ejecute el siguiente comando:

    ```powershell
    Write-Output -InputObject ("`r`n"*3),"Standard anti-malware policy",("-"*79);Get-MalwareFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"; Write-Output -InputObject ("`r`n"*3),"Standard anti-spam policy",("-"*79);Get-HostedContentFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"; Write-Output -InputObject ("`r`n"*3),"Standard anti-phishing policy",("-"*79);Get-AntiPhishPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"
    ```

  - **Organizaciones con Defender para Microsoft 365**:

    Para ver las directivas de seguridad individuales de la directiva de seguridad preestablecida estándar en organizaciones con Defender para Microsoft 365, ejecute el siguiente comando:

    ```powershell
    Write-Output -InputObject ("`r`n"*3),"Standard anti-malware policy",("-"*79);Get-MalwareFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"; Write-Output -InputObject ("`r`n"*3),"Standard anti-spam policy",("-"*79);Get-HostedContentFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"; Write-Output -InputObject ("`r`n"*3),"Standard anti-phishing policy",("-"*79);Get-AntiPhishPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"; Write-Output -InputObject ("`r`n"*3),"Standard Safe Attachments policy",("-"*79);Get-SafeAttachmentPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"; Write-Output -InputObject ("`r`n"*3),"Standard Safe Links policy",("-"*79);Get-SafeLinksPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"
    ```

- **Directiva de seguridad preestablecida estricta**: las directivas asociadas se denominan `Strict Preset Security Policy<13-digit number>`. Por ejemplo, `Strict Preset Security Policy1642034872546`. El valor de la propiedad RecommendPolicyType es Strict.

  - **Organizaciones sin Defender para Microsoft 365**:

    - Para ver las directivas de seguridad individuales de la directiva de seguridad preestablecida Estricta en organizaciones sin Defender para Microsoft 365, ejecute el siguiente comando:

      ```powershell
      Write-Output -InputObject ("`r`n"*3),"Strict anti-malware policy",("-"*79);Get-MalwareFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"; Write-Output -InputObject ("`r`n"*3),"Strict anti-spam policy",("-"*79);Get-HostedContentFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"; Write-Output -InputObject ("`r`n"*3),"Strict anti-phishing policy",("-"*79);Get-AntiPhishPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"
      ```

  - **Organizaciones con Defender para Microsoft 365**:

    - Para ver las directivas de seguridad individuales de la directiva de seguridad preestablecida estricta en organizaciones con Defender para Microsoft 365, ejecute el siguiente comando:

    ```powershell
    Write-Output -InputObject ("`r`n"*3),"Strict anti-malware policy",("-"*79);Get-MalwareFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"; Write-Output -InputObject ("`r`n"*3),"Strict anti-spam policy",("-"*79);Get-HostedContentFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"; Write-Output -InputObject ("`r`n"*3),"Strict anti-phishing policy",("-"*79);Get-AntiPhishPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"; Write-Output -InputObject ("`r`n"*3),"Strict Safe Attachments policy",("-"*79);Get-SafeAttachmentPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"; Write-Output -InputObject ("`r`n"*3),"Strict Safe Links policy",("-"*79);Get-SafeLinksPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"
    ```

### <a name="use-powershell-to-view-rules-for-preset-security-policies"></a>Uso de PowerShell para ver las reglas de las directivas de seguridad preestablecidas

Recuerde que, si nunca ha activado la directiva de seguridad preestablecida Estándar o la directiva de seguridad preestablecida Estricta en el portal de Microsoft 365 Defender, las reglas asociadas para esas directivas no existen.

- **Directiva de seguridad preestablecida de protección integrada**: la regla asociada se denomina ATP Built-In Regla de protección.

  Para ver la regla asociada a la directiva de seguridad preestablecida de protección integrada, ejecute el siguiente comando:

  ```powershell
  Get-ATPBuiltInProtectionRule
  ```

  Para obtener información detallada sobre la sintaxis y los parámetros, vea [Get-ATPBuiltInProtectionRule](/powershell/module/exchange/get-atpbuiltinprotectionrule).

- **Directiva de seguridad preestablecida estándar**: las reglas asociadas se denominan Directiva de seguridad preestablecida estándar.

  Use los siguientes comandos para ver las reglas asociadas a la directiva de seguridad preestablecida Estándar:

  - Para ver la regla asociada a las protecciones EOP en la directiva de seguridad preestablecida Estándar, ejecute el siguiente comando:

    ```powershell
    Get-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy"
    ```

  - Para ver la regla asociada a Defender para Office 365 protecciones en la directiva de seguridad preestablecida Estándar, ejecute el siguiente comando:

    ```powershell
    Get-ATPProtectionPolicyRule -Identity "Standard Preset Security Policy"
    ```

  - Para ver ambas reglas al mismo tiempo, ejecute el siguiente comando:

    ```powershell
    Write-Output -InputObject ("`r`n"*3),"EOP rule - Standard preset security policy",("-"*79);Get-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy"; Write-Output -InputObject ("`r`n"*3),"Defender for Office 365 rule - Standard preset security policy",("-"*79);Get-ATPProtectionPolicyRule -Identity "Standard Preset Security Policy"
    ```

- **Directiva de seguridad preestablecida estricta**: las reglas asociadas se denominan Directiva de seguridad preestablecida estricta.

  Use los siguientes comandos para ver las reglas asociadas a la directiva de seguridad preestablecida Strict:

  - Para ver la regla asociada a las protecciones de EOP en la directiva de seguridad preestablecida Strict, ejecute el siguiente comando:

    ```powershell
    Get-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy"
    ```

  - Para ver la regla asociada a Defender para Office 365 protecciones en la directiva de seguridad preestablecida Strict, ejecute el siguiente comando:

    ```powershell
    Get-ATPProtectionPolicyRule -Identity "Strict Preset Security Policy"
    ```

  - Para ver ambas reglas al mismo tiempo, ejecute el siguiente comando:

    ```powershell
    Write-Output -InputObject ("`r`n"*3),"EOP rule - Strict preset security policy",("-"*79);Get-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy"; Write-Output -InputObject ("`r`n"*3),"Defender for Office 365 rule - Strict preset security policy",("-"*79);Get-ATPProtectionPolicyRule -Identity "Strict Preset Security Policy"
    ```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Get-EOPProtectionPolicyRule](/powershell/module/exchange/get-eopprotectionpolicyrule) y [Get-ATPProtectionPolicyRule](/powershell/module/exchange/get-atpprotectionpolicyrule).

### <a name="use-powershell-to-turn-on-or-turn-off-preset-security-policies"></a>Uso de PowerShell para activar o desactivar directivas de seguridad preestablecidas

Como se describió anteriormente, para activar o desactivar las directivas de seguridad preestablecidas Estándar o Estricto, habilite o deshabilite las reglas asociadas a la directiva. El valor de la propiedad State de la regla muestra si la regla es Enabled o Disabled.

En función de si su organización tiene Defender para Office 365, es posible que tenga que habilitar o deshabilitar una regla (la regla para las protecciones EOP) o dos reglas (una regla para las protecciones EOP y una regla para Defender para Office 365 protecciones) para activar o desactivar la directiva de seguridad preestablecida.

- **Directiva de seguridad preestablecida estándar**:

  - **Organizaciones sin Defender para Office 365**:

    - En organizaciones sin Defender para Office 365, ejecute el siguiente comando para determinar si la regla de la directiva preestablecida Estándar está habilitada o deshabilitada actualmente:

      ```powershell
      Get-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy" | Format-Table Name,State
      ```

    - Ejecute el siguiente comando para desactivar la directiva de seguridad preestablecida Estándar si está activada:

      ```powershell
      Disable-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy"
      ```

    - Ejecute el siguiente comando para activar la directiva de seguridad preestablecida Estándar si está desactivada:

      ```powershell
      Enable-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy"
      ```

  - **Organizaciones con Defender para Office 365**:

    - En organizaciones con Defender para Office 365, ejecute el siguiente comando para determinar si las reglas de la directiva preestablecida Estándar están habilitadas o deshabilitadas actualmente:

      ```powershell
      Write-Output -InputObject ("`r`n"*3),"EOP rule - Standard preset security policy",("-"*63);Get-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy" | Format-Table Name,State; Write-Output -InputObject `r`n,"Defender for Office 365 rule - Standard preset security policy",("-"*63);Get-ATPProtectionPolicyRule -Identity "Standard Preset Security Policy" | Format-Table Name,State
      ```

    - Ejecute el siguiente comando para desactivar la directiva de seguridad preestablecida Estándar si está activada:

      ```powershell
      Disable-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy"; Disable-ATPProtectionPolicyRule -Identity "Standard Preset Security Policy"
      ```

    - Ejecute el siguiente comando para activar la directiva de seguridad preestablecida Estándar si está desactivada:

      ```powershell
      Enable-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy"; Enable-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy"
      ```

- **Directiva de seguridad preestablecida estricta**:

  - **Organizaciones sin Defender para Office 365**:

    - En organizaciones con Defender para Office 365, ejecute el siguiente comando para determinar si la regla de la directiva preestablecida Strict está habilitada o deshabilitada actualmente:

      ```powershell
      Get-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy" | Format-Table Name,State
      ```

    - Ejecute el siguiente comando para desactivar la directiva de seguridad preestablecida Strict si está activada:

      ```powershell
      Disable-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy"
      ```

    - Ejecute el siguiente comando para activar la directiva de seguridad preestablecida Strict si está desactivada:

      ```powershell
      Enable-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy"
      ```

  - **Organizaciones con Defender para Office 365**:

    - En organizaciones con Defender para Office 365, ejecute el siguiente comando para determinar si las reglas de la directiva preestablecida Strict están habilitadas o deshabilitadas actualmente:

      ```powershell
      Write-Output -InputObject ("`r`n"*3),"EOP rule - Strict preset security policy",("-"*63);Get-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy" | Format-Table Name,State; Write-Output -InputObject `r`n,"Defender for Office 365 rule - Strict preset security policy",("-"*63);Get-ATPProtectionPolicyRule -Identity "Strict Preset Security Policy" | Format-Table Name,State
      ```

    - Ejecute el siguiente comando para desactivar la directiva de seguridad preestablecida Strict si está activada:

      ```powershell
      Disable-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy"; Disable-ATPProtectionPolicyRule -Identity "Strict Preset Security Policy"
      ```

    - Ejecute el siguiente comando para activar la directiva de seguridad preestablecida Strict si está desactivada:

      ```powershell
      Enable-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy"; Enable-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy"
      ```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Enable-EOPProtectionPolicyRule](/powershell/module/exchange/enable-eopprotectionpolicyrule), [Enable-ATPProtectionPolicyRule](/powershell/module/exchange/enable-atpprotectionpolicyrule), [Disable-EOPProtectionPolicyRule](/powershell/module/exchange/disable-eopprotectionpolicyrule) y [Disable-ATPProtectionPolicyRule](/powershell/module/exchange/disable-atpprotectionpolicyrule).

### <a name="use-powershell-to-specify-recipient-conditions-and-exceptions-for-preset-security-policies"></a>Uso de PowerShell para especificar condiciones y excepciones de destinatarios para las directivas de seguridad preestablecidas

> [!IMPORTANT]
  > Los diferentes tipos de condiciones o excepciones no son aditivos; son inclusivos. La directiva de seguridad preestablecida _solo_ se aplica a los destinatarios que coinciden _con todos los_ filtros de destinatarios especificados. Por ejemplo, se configura una condición de filtro de destinatario en la directiva con los siguientes valores:
  >
  > - Usuarios: romain@contoso.com
  > - Grupos: Ejecutivos
  >
  > La directiva se aplica a romain@contoso.com _solo_ si también es miembro del grupo de Ejecutivos. Si no es miembro del grupo, la directiva no se le aplica.
  >
  > Asimismo, si utiliza el mismo filtro de destinatarios como excepción a la directiva, esta no se aplica a romain@contoso.com _solo_ si también es miembro del grupo de Ejecutivos. Si no es miembro del grupo, la directiva se le sigue aplicando.

Para la directiva de seguridad preestablecida de protección integrada, solo puede especificar excepciones de destinatario. Si todos los valores de parámetro de excepción están vacíos (`$null`), no hay ninguna excepción en la directiva.

En el caso de las directivas de seguridad preestablecidas Estándar y Estricta, puede especificar las condiciones y excepciones de destinatarios para las protecciones EOP y las protecciones de Defender para Office 365. Si todas las condiciones y los valores de parámetros de excepción están vacíos (`$null`), no hay condiciones de destinatario ni excepciones a las directivas de seguridad preestablecidas Estándar o Estricta.

Incluso si no hay condiciones de destinatario o excepciones aplicadas a una directiva de seguridad preestablecida, si la directiva se aplica a todos los destinatarios depende [del orden de precedencia de las directivas](#order-of-precedence-for-preset-security-policies-and-other-policies) , como se describió anteriormente en este artículo.

- **Directiva de seguridad preestablecida de protección integrada**:

  Utilice la siguiente sintaxis:

  ```powershell
  Set-ATPBuiltInProtectionRule -Identity "ATP Built-In Protection Rule" -ExceptIfRecipientDomainIs <"domain1","domain2",... | $null> -ExceptIfSentTo <"user1","user2",... | $null> -ExceptIfSentToMemberOf <"group1","group2",... | $null>
  ```

  En este ejemplo se quitan todas las excepciones de destinatarios de la directiva de seguridad preestablecida de protección integrada.

  ```powershell
  Set-ATPBuiltInProtectionRule -Identity "ATP Built-In Protection Rule" -ExceptIfRecipientDomainIs $null -ExceptIfSentTo $null -ExceptIfSentToMemberOf $null
  ```

  Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-ATPBuiltInProtectionRule](/powershell/module/exchange/set-atpbuiltinprotectionrule).

- **Directivas de seguridad preestablecidas estándar o estricta**

  Utilice la siguiente sintaxis:

  ```powershell
  <Set-EOPProtectionPolicyRule | SetAtpProtectionPolicyRule> -Identity "<Standard Preset Security Policy | Strict Preset Security Policy>" -SentTo <"user1","user2",... | $null> -ExceptIfSentTo <"user1","user2",... | $null> -SentToMemberOf <"group1","group2",... | $null> -ExceptIfSentToMemberOf <"group1","group2",... | $null> -RecipientDomainIs <"domain1","domain2",... | $null> -ExceptIfRecipientDomainIs <"domain1","domain2",... | $null>
  ```

  En este ejemplo se configuran las excepciones de las protecciones EOP en la directiva de seguridad preestablecida Estándar para los miembros del grupo de distribución denominado Ejecutivos.

  ```powershell
  Set-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy" -ExceptIfSentToMemberOf Executives
  ```

  En este ejemplo se configuran excepciones de las protecciones de Defender para Office 365 en la directiva de seguridad preestablecida Strict para los buzones de operaciones de seguridad (SecOps) especificados.

  ```powershell
  Set-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy" -ExceptIfSentTo "SecOps1","SecOps2"
  ```

  Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-EOPProtectionPolicyRule](/powershell/module/exchange/set-eopprotectionpolicyrule) y [Set-ATPProtectionPolicyRule](/powershell/module/exchange/Set-atpprotectionpolicyrule).
