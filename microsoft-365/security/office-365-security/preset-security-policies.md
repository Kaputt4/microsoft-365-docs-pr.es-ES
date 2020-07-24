---
title: Directivas de seguridad preestablecidas
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a aplicar opciones de directiva estándar y estrictas en las características de protección de Exchange Online Protection (EOP) y Office 365 Advanced Threat Protection (ATP)
ms.openlocfilehash: 34445c617d2dda59a65b197db2f42324d0085ab3
ms.sourcegitcommit: 688d62a8c52e4fb0feb721bb92b535effc278f54
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "45389881"
---
# <a name="preset-security-policies-in-eop-and-office-365-atp"></a>Directivas de seguridad preestablecidas en EOP y Office 365 ATP

Las directivas de seguridad preestablecidas proporcionan una ubicación centralizada para aplicar todas las directivas recomendadas de correo no deseado, malware y de suplantación de identidad a los usuarios a la vez. La configuración de la Directiva no se puede configurar. En su lugar, están establecidos por nosotros y se basan en nuestras observaciones y experiencias en los centros de datos para conseguir un equilibrio entre el mantenimiento del contenido peligroso de los usuarios sin interrumpir su trabajo.

En el resto de este tema se describen las directivas de seguridad preestablecidas y cómo configurarlas.

## <a name="what-preset-security-policies-are-made-of"></a>¿Qué directivas de seguridad preestablecidas están hechas de

Las directivas de seguridad preestablecidas constan de los siguientes elementos:

- Perfiles
- Directivas
- Configuración de directivas

Además, el orden de prioridad es importante si se aplican varias directivas de seguridad preestablecidas y otras directivas a la misma persona.

### <a name="profiles-in-preset-security-policies"></a>Perfiles en directivas de seguridad predeterminadas

Un perfil determina el nivel de protección. Están disponibles los siguientes perfiles:

- **Protección estándar**: Perfil de protección de línea de base adecuado para la mayoría de los usuarios.
- **Protección estricta**: un perfil de protección más agresivo para los usuarios seleccionados (objetivos de valor alto o usuarios con prioridad).

Las reglas se usan con condiciones y excepciones que determinan a quién se aplican o qué perfiles.

Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

Las condiciones y excepciones disponibles son:

- **Los destinatarios son**: buzones de correo, usuarios de correo o contactos de correo de su organización.
- **Los destinatarios son miembros de**: grupos de su organización.
- **Los dominios de destinatarios son**: dominios aceptados que están configurados en Microsoft 365.

### <a name="policies-in-preset-security-policies"></a>Directivas en directivas de seguridad predefinidas

Las directivas de seguridad preestablecidas usan las directivas correspondientes de las diversas características de protección de EOP y Office 365 ATP. Estas directivas se crean _después_ de asignar directivas de seguridad de **protección estándar** o de **protección estricta** a los usuarios. No puede modificar estas directivas.

- **Directivas de Exchange Online Protection (EOP)**: Esto incluye a Microsoft 365 organizaciones con buzones de Exchange Online y organizaciones independientes de EOP sin buzones de Exchange Online:
  
  - [Directivas contra correo no deseado](configure-your-spam-filter-policies.md) que se denominan **Directiva de seguridad preestablecida estándar** y **estricta**.
  - [Directivas antimalware](configure-anti-malware-policies.md) denominadas **Directiva de seguridad preestablecida estándar** y **estricta Directiva de seguridad preestablecida**.
  - [Las directivas de suplantación de identidad de EOP](set-up-anti-phishing-policies.md#spoof-settings) denominadas **Directiva de seguridad preestablecida estándar** y **estricta Directiva de seguridad preestablecida** (configuración de falsificación).

- **Directivas de protección contra amenazas avanzada (ATP) de Office 365**: Esto incluye a las organizaciones con suscripciones de complementos de ATP de Microsoft 365 E5 u Office 365:

  - Las directivas antiphishing de ATP denominadas **Directiva de seguridad preestablecida estándar** y **estricta Directiva de seguridad preestablecida**, que incluye:

    - La misma [configuración de suplantación](set-up-anti-phishing-policies.md#spoof-settings) de identidad que están disponibles en las directivas de protección contra suplantación de EOP.
    - [Configuración de suplantación](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [Umbrales de suplantación de identidad avanzada](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - [Directivas de vínculos a prueba](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users) de errores denominada **Directiva de seguridad predeterminada estándar** y **estricta Directiva de seguridad preestablecida**.

  - [Directivas de datos adjuntos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users) denominada **Directiva de seguridad predeterminada estándar** y **estricta Directiva de seguridad preestablecida**.

Tenga en cuenta que puede aplicar protecciones de EOP a diferentes usuarios que las protecciones de ATP.

### <a name="policy-settings-in-preset-security-policies"></a>Configuración de directivas en directivas de seguridad predeterminadas

No puede modificar la configuración de la Directiva en los perfiles de protección. Los valores de configuración de directiva **estándar** y **estricta** se describen en [configuración recomendada para EOP y Office 365 ATP Security](recommended-settings-for-eop-and-office365-atp.md).

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Orden de prioridad de las directivas de seguridad preestablecidas y otras directivas

Cuando se aplican varias directivas a un usuario, se aplica el siguiente orden de la prioridad más alta a la menor:

1. Directiva de seguridad predeterminada de **protección estricta**
2. Directiva de seguridad preestablecida de **protección estándar**
3. Cualquier otra directiva relacionada.

Es decir, la configuración de la Directiva de **protección estricta** reemplaza la configuración de la Directiva de **protección estándar** , que reemplaza la configuración de otras directivas relacionadas.

## <a name="assign-preset-security-policies-to-users"></a>Asignar directivas de seguridad preestablecidas a los usuarios

### <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página **directivas de seguridad preestablecidas** , use <https://protection.office.com/presetSecurityPolicies> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Para poder realizar los procedimientos de este tema, deberá tener asignados los permisos necesarios:

  - Para configurar directivas de seguridad preestablecidas, debe pertenecer a uno de los siguientes grupos de roles:

    - **Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).
    - **Administración de la organización** o **Administración de higiene** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Para obtener acceso de solo lectura a directivas de seguridad preestablecidas, debe ser miembro de uno de los siguientes grupos de roles:

    - **Lector de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).
    - **Administración de la organización de solo visualización** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>Usar el centro de seguridad & cumplimiento para asignar directivas de seguridad preestablecidas a los usuarios

1. En el centro de seguridad & cumplimiento, vaya **Threat management** a directivas de \> **Policy** \> **seguridad preestablecidas**de directiva de administración de amenazas.

2. En **protección estándar** o **protección estricta**, haga clic en **Editar**.

3. Se inicia el Asistente para **aplicar protección estándar** o **aplicar protección estricta** . En las **protecciones de EOP se aplican al** paso, identifique los destinatarios internos a los que se aplican las [protecciones de EOP](#policies-in-preset-security-policies) :

   1. Haga clic en **Agregar condición**. En la lista desplegable que aparece, seleccione una condición en **aplicado si**:

      - **Los destinatarios son**
      - **Los destinatarios son miembros de**
      - **Los dominios de destinatarios son**

      Solo se puede usar una condición una vez, pero se pueden especificar varios valores para la condición. Varios valores de la misma condición uso o lógica (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_ ).

   2. La condición seleccionada aparece en una sección sombreada. En esa sección, haga clic en el cuadro **cualquiera de estos** . Si espera un momento, aparecerá una lista para que pueda seleccionar un valor. O bien, puede empezar a escribir un valor para filtrar la lista y seleccionar un valor. Repita este paso tantas veces como sea necesario. Para quitar un valor individual, haga clic en **quitar** ![ icono quitar ](../../media/scc-remove-icon.png) en el valor. Para quitar toda la condición, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación en la condición.

   3. Para agregar otra condición, haga clic en **Agregar condición** y seleccione una de las condiciones restantes. La lógica y el uso de diferentes condiciones (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_ ).

      Repita el paso anterior para agregar valores a la condición y repita el paso tantas veces como sea necesario o hasta que se agoten las condiciones.

   4. Para agregar una excepción, haga clic en **Agregar condición**. En la lista desplegable que aparece, seleccione una condición en **excepto cuando**. La configuración y el comportamiento se muestran exactamente igual que las condiciones.

   Cuando termine, haga clic en **Siguiente**.

4. Si su organización tiene Office 365 ATP, se le ha dado a las **protecciones de ATP que se aplican al** paso para identificar a los destinatarios internos a los que se aplican las [protecciones atp de Office 365](#policies-in-preset-security-policies) .

   La configuración y el comportamiento son exactamente iguales **a las protecciones de EOP que se aplican al** paso.

   Cuando termine, haga clic en **Siguiente**.

5. En el paso **confirmar** , compruebe las selecciones y, a continuación, haga clic en **confirmar**.

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>Usar el centro de seguridad & cumplimiento para modificar las asignaciones de directivas de seguridad preestablecidas

Los pasos para modificar la asignación de la Directiva de seguridad de protección **estándar** o **estricta** son los mismos que cuando se [asignaron inicialmente las directivas de seguridad preestablecidas para los usuarios](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).

Para deshabilitar las directivas de seguridad de protección **estándar** o **protección estricta** mientras se conservan las condiciones y excepciones existentes, deslice el botón de alternancia a **deshabilitado**. Para habilitar las directivas, deslice el botón de alternancia a **habilitado**.

### <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha asignado correctamente la Directiva de seguridad de protección **estándar** o **estricta protección** a un usuario, use una configuración de protección donde el valor predeterminado sea diferente al de la configuración de **protección estándar** , que es diferente de la configuración de **protección estricta** .

Por ejemplo, para el correo electrónico que se detecta como correo no deseado (correo no deseado de alta confianza), compruebe que el mensaje se entrega a la carpeta de correo no deseado para los usuarios de **protección estándar** y que se pone en cuarentena para los usuarios de **protección estricta** .

O bien, para el [correo electrónico masivo](bulk-complaint-level-values.md), compruebe que el valor de BCL 6 o superior entrega el mensaje a la carpeta de correo electrónico no deseado para los usuarios de **protección estándar** y el valor de BCL 4 o superior pone en cuarentena el mensaje para los usuarios de **protección estrictos** .
