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
description: Los administradores pueden aprender a aplicar la configuración de directiva estándar y estricta en las características de protección de Exchange Online Protection (EOP) y Microsoft Defender para Office 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f57b388716eca02741ba48b3e6b47b7cf9f28884
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150090"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>Directivas de seguridad preestablecidas en EOP y Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plan 1 y plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Las directivas de seguridad preestablecidas proporcionan una ubicación centralizada para aplicar todas las directivas recomendadas de correo no deseado, malware y suplantación de identidad a los usuarios a la vez. La configuración de directiva no se puede configurar. En su lugar, se establecen por nosotros y se basan en nuestras observaciones y experiencias en los centros de datos para un equilibrio entre mantener contenido peligroso lejos de los usuarios sin interrumpir su trabajo.

En el resto de este tema se describen las directivas de seguridad preestablecidas y cómo configurarlas.

## <a name="what-preset-security-policies-are-made-of"></a>De qué están hechas las directivas de seguridad preestablecidas

Las directivas de seguridad preestablecidas constan de los siguientes elementos:

- Perfiles
- Directivas
- Configuración de directivas

Además, el orden de prioridad es importante si se aplican varias directivas de seguridad preestablecidas y otras directivas a la misma persona.

### <a name="profiles-in-preset-security-policies"></a>Perfiles en directivas de seguridad preestablecidas

Un perfil determina el nivel de protección. Están disponibles los siguientes perfiles:

- **Protección estándar:** un perfil de protección de línea base que es adecuado para la mayoría de los usuarios.
- **Protección estricta:** un perfil de protección más agresivo para los usuarios seleccionados (destinos de alto valor o usuarios de prioridad).

Las reglas se usan con condiciones y excepciones que determinan a quién se aplican o no los perfiles.

Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

Las condiciones y excepciones disponibles son:

- **Los destinatarios son: buzones** de correo, usuarios de correo o contactos de correo de su organización.
- **Los destinatarios son miembros de**: Grupos de la organización.
- **Los dominios de destinatario son:** dominios aceptados que están configurados en Microsoft 365.

### <a name="policies-in-preset-security-policies"></a>Directivas en directivas de seguridad preestablecidas

Las directivas de seguridad preestablecidas usan las directivas correspondientes de las distintas características de protección de EOP y Microsoft Defender para Office 365. Estas directivas se crean _después de asignar_ las directivas de seguridad preestablecidas protección estándar o Protección estricta a los usuarios.   No puede modificar estas directivas.

- **Directivas de Exchange Online Protection (EOP):** esto incluye organizaciones de Microsoft 365 con buzones de Exchange Online y organizaciones EOP independientes sin buzones de Exchange Online:

  - [Directivas contra correo no deseado denominadas](configure-your-spam-filter-policies.md) **Directiva de seguridad preestablecida estándar** y Directiva de seguridad **preestablecida estricta.**
  - [Directivas antimalware](configure-anti-malware-policies.md) **denominadas Directiva de seguridad preestablecida estándar** y **Directiva de seguridad preestablecida estricta.**
  - [Directivas de protección contra suplantación de](set-up-anti-phishing-policies.md#spoof-settings) identidad de EOP denominadas Directiva de seguridad preestablecida **estándar** y Directiva de seguridad preestablecida **estricta** (configuración de suplantación de identidad).

- Directivas de Microsoft Defender para **Office 365:** esto incluye las organizaciones con suscripciones de complemento de Microsoft 365 E5 o Defender para Office 365:

  - Las directivas contra suplantación de identidad en Microsoft Defender para Office 365 **denominadas Directiva** de seguridad preestablecida estándar y Directiva de seguridad preestablecida estricta, que incluyen: 

    - La misma [configuración de suplantación](set-up-anti-phishing-policies.md#spoof-settings) de identidad que están disponibles en las directivas contra la suplantación de identidad de EOP.
    - [Configuración de suplantación](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Umbrales avanzados de suplantación de identidad](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Directivas de vínculos seguros](set-up-atp-safe-links-policies.md) **denominadas Directiva de seguridad preestablecida estándar** y **Directiva de seguridad preestablecida estricta.**

  - [Directivas de datos adjuntos seguros](set-up-atp-safe-attachments-policies.md) **denominadas Directiva de seguridad preestablecida estándar** y **Directiva de seguridad preestablecida estricta.**

Tenga en cuenta que puede aplicar protecciones de EOP a distintos usuarios que a Microsoft Defender para las protecciones de Office 365.

### <a name="policy-settings-in-preset-security-policies"></a>Configuración de directiva en directivas de seguridad preestablecidas

No puede modificar la configuración de directiva en los perfiles de protección. Los **valores de** configuración **de** directiva Estándar y Estricto se describen en Configuración recomendada para EOP y Microsoft Defender para la seguridad de [Office 365.](recommended-settings-for-eop-and-office365-atp.md)

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Orden de prioridad para las directivas de seguridad preestablecidas y otras directivas

Cuando se aplican varias directivas a un usuario, se aplica el siguiente orden de prioridad más alta a prioridad más baja:

1. **Directiva de seguridad** preestablecida de protección estricta
2. **Directiva de seguridad** preestablecida de protección estándar
3. Directivas de seguridad personalizadas
4. Directivas de seguridad predeterminadas

En otras palabras, la configuración de la  directiva de protección **Estricta** invalida la configuración de la directiva de protección estándar, que reemplaza la configuración de una directiva personalizada, que invalida la configuración de la directiva predeterminada.

## <a name="assign-preset-security-policies-to-users"></a>Asignar directivas de seguridad preestablecidas a los usuarios

### <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página **Directivas de seguridad preestablecidas,** use <https://protection.office.com/presetSecurityPolicies> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento para poder realizar los procedimientos de este artículo:
  - Para configurar directivas de seguridad preestablecidas, debe ser miembro de los grupos de roles Administración de la organización o **Administrador de** seguridad. 
  - Para obtener acceso de solo lectura a las directivas de seguridad preestablecidas, debe ser miembro del grupo de roles **Lector** global.

  Para más información, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

  **Nota:** agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft  365 proporciona a los usuarios los permisos necesarios en el Centro de seguridad & Cumplimiento y permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>Usar el Centro de & cumplimiento para asignar directivas de seguridad preestablecidas a los usuarios

1. En el Centro de seguridad & cumplimiento, vaya **a** Directivas de seguridad preestablecidas de la directiva \>  \> **de administración de amenazas.**

2. En **Protección estándar o** Protección **estricta,** haga clic **en Editar**.

3. Se **inicia el Asistente para aplicar** protección estándar o Aplicar estricta protección.  En las **protecciones de EOP se aplican a** paso, identifique los destinatarios internos a los que se aplican las protecciones de [EOP:](#policies-in-preset-security-policies)

   1. Haga **clic en Agregar una condición.** En la lista desplegable que aparece, seleccione una condición en **Aplicada si:**

      - **Los destinatarios son**
      - **Los destinatarios son miembros de**
      - **Los dominios de destinatario son**

      Solo puede usar una condición una vez, pero puede especificar varios valores para la condición. Varios valores de la misma condición usan lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_ ).

   2. La condición seleccionada aparece en una sección sombreada. En esa sección, haga clic en **el cuadro Cualquiera de estos.** Si espera un momento, aparecerá una lista para que pueda seleccionar un valor. O bien, puede empezar a escribir un valor para filtrar la lista y seleccionar un valor. Repita este paso tantas veces como sea necesario. Para quitar un valor individual, haga clic **en el** icono Quitar ![ del ](../../media/scc-remove-icon.png) valor. Para quitar toda la condición, haga clic **en el** icono Quitar de ![ la ](../../media/scc-remove-icon.png) condición.

   3. Para agregar otra condición, haga clic **en Agregar una condición** y seleccione entre las condiciones restantes. Diferentes condiciones usan lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_ ).

      Repita el paso anterior para agregar valores a la condición y repita este paso tantas veces como sea necesario o hasta que se quedas sin condiciones.

   4. Para agregar una excepción, haga clic **en Agregar una condición.** En la lista desplegable que aparece, seleccione una condición en **Excepto cuando**. La configuración y el comportamiento se muestran exactamente igual que las condiciones.

   Cuando termine, haga clic en **Siguiente**.

4. Si su organización tiene Microsoft Defender para Office 365, se le aplicarán las protecciones de **ATP** para identificar los destinatarios internos a los que se aplican las protecciones de Microsoft Defender para [Office 365.](#policies-in-preset-security-policies)

   La configuración y el comportamiento son exactamente iguales que **las protecciones de EOP se aplican a los** pasos.

   Cuando termine, haga clic en **Siguiente**.

5. En el **paso Confirmar,** compruebe las selecciones y, a continuación, haga clic en **Confirmar**.

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>Usar el Centro de & cumplimiento para modificar las asignaciones de directivas de seguridad preestablecidas

Los pasos para modificar  la asignación de la directiva de seguridad de protección estándar o protección estricta son los mismos que cuando asignó inicialmente las directivas de seguridad preestablecidas [a los usuarios.](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users) 

Para deshabilitar la protección **estándar** o las **directivas** de seguridad de protección estricta a la vez que se conservan las condiciones y excepciones existentes, deslice el botón de alternancia a **Deshabilitado**. Para habilitar las directivas, deslice el botón de alternancia a **Habilitado**.

### <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que asignó  correctamente  la directiva de protección estándar o de seguridad de protección  estricta a un usuario,  use una configuración de protección en la que el valor predeterminado sea diferente de la configuración de protección estándar, que es diferente de la configuración de protección Estricta.

Por ejemplo, para el correo electrónico que se detecta como correo no deseado (no  correo no deseado de confianza alta) compruebe que el mensaje se entrega en la carpeta correo no deseado para los usuarios de protección estándar y se pone en cuarentena para los usuarios de protección **estricta.**

O bien, en el caso del correo electrónico [masivo,](bulk-complaint-level-values.md)compruebe que el  valor de BCL 6 o superior entrega el  mensaje a la carpeta correo no deseado para los usuarios de protección estándar y que el valor de BCL 4 o superior pone en cuarentena el mensaje para los usuarios de protección estricta.
