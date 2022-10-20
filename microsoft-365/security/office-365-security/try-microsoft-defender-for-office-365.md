---
title: Pruebe a evaluar Defender para Office 365
description: Obtenga información sobre cómo evaluar y probar las funcionalidades de Microsoft Defender para Office 365 sin afectar al flujo de correo existente.
keywords: Pruebe, evalúe, pruebe, evalúe Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- m365-security
ms.custom: ''
ms.subservice: mdo
ms.service: microsoft-365-security
ROBOTS: ''
ms.openlocfilehash: 297435fbea9e70ba0b23401a17bbb756b638ff4c
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68621988"
---
# <a name="try-microsoft-defender-for-office-365"></a>Pruebe Microsoft Defender para Office 365

Como cliente existente de Microsoft 365, las páginas **Pruebas** y **evaluación** del portal de Microsoft 365 Defender de <https://security.microsoft.com> permiten probar las características de Microsoft Defender para Office 365 Plan 2 antes de comprar.

Antes de probar Defender para Office 365 plan 2, hay algunas preguntas clave que debe plantearse a sí mismo:

- ¿Quiero observar pasivamente lo que Defender para Office 365 Plan 2 puede hacer por mí (*auditoría*), o quiero Defender para Office 365 Plan 2 para tomar medidas directas sobre los problemas que encuentra (*bloquear*)?
- En cualquier caso, ¿cómo puedo saber lo que Defender para Office 365 Plan 2 está haciendo por mí?
- ¿Cuánto tiempo tengo antes de tomar la decisión de mantener Defender para Office 365 Plan 2?

Este artículo le ayudará a responder a esas preguntas para que pueda probar Defender para Office 365 plan 2 de forma que satisfaga mejor las necesidades de su organización.

Para obtener una guía complementaria sobre cómo usar la prueba, consulte Cuaderno de estrategias de [prueba: Microsoft Defender para Office 365](trial-playbook-defender-for-office-365.md).

## <a name="overview-of-defender-for-office-365"></a>Introducción a Defender para Office 365

Defender para Office 365 ayuda a las organizaciones a proteger su empresa al ofrecer una lista completa de funcionalidades. Para obtener más información, consulte [Microsoft Defender para Office 365](defender-for-office-365.md).

También puede obtener más información sobre Defender para Office 365 en esta [guía interactiva](https://aka.ms/MS365D.InteractiveGuide).

![Microsoft Defender para Office 365 diagrama conceptual.](../../media/microsoft-defender-for-office-365.png)

Vea este breve vídeo para obtener más información sobre cómo puede hacer más en menos tiempo con Microsoft Defender para Office 365.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMmIe]

## <a name="how-trials-and-evaluations-work-for-defender-for-office-365"></a>Cómo funcionan las pruebas y evaluaciones para Defender para Office 365

### <a name="policies"></a>Directivas

Defender para Office 365 incluye las características de Exchange Online Protection (EOP), que están presentes en todas las organizaciones de Microsoft 365 con buzones de Exchange Online, y características exclusivas de Defender para Office 365.

Las características de protección de EOP y Defender para Office 365 se implementan mediante directivas. **Las directivas exclusivas de Defender para Office 365 se crean automáticamente según sea necesario**:

- [Protección contra suplantación en directivas antiphishing](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
- [Datos adjuntos seguros para mensajes de correo electrónico](safe-attachments.md)
- [Vínculos seguros para mensajes de correo electrónico y Microsoft Teams](safe-links.md)
  - Vínculos seguros detona las direcciones URL durante el flujo de correo. Para evitar que se detonen direcciones URL específicas, use permitir entradas para direcciones URL en la lista de permitidos o bloqueados de inquilinos. Para obtener más información, vea [Administrar la lista de permitidos o bloqueados de inquilinos](manage-tenant-allow-block-list.md).
  - Vínculos seguros no encapsula los vínculos URL en los cuerpos de mensajes de correo electrónico.

Su elegibilidad para una evaluación o evaluación significa que ya tiene EOP. **No se crean directivas EOP nuevas o especiales para la evaluación o evaluación de Defender para Office 365 Plan 2**. Las directivas de EOP existentes en la organización de Microsoft 365 pueden actuar sobre los mensajes (por ejemplo, enviar mensajes a la carpeta Email no deseado o poner en cuarentena):

- [Directivas antimalware](anti-malware-protection.md)
- [Protección contra correo no deseado entrante](anti-spam-protection.md)
- [Protección contra la suplantación de identidad en directivas contra suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings)

Las directivas predeterminadas para estas características de EOP siempre están activadas, se aplican a todos los destinatarios y siempre se aplican por última vez después de las directivas personalizadas.

### <a name="audit-mode-vs-blocking-mode-for-defender-for-office-365"></a>Modo de auditoría frente a modo de bloqueo para Defender para Office 365

¿Desea que su experiencia de Defender para Office 365 sea activa o pasiva? Estos son los dos modos entre los que puede seleccionar:

- **Modo de auditoría**: se crean *directivas de evaluación* especiales para la protección contra suplantación de identidad (que incluye protección contra suplantación), datos adjuntos seguros y vínculos seguros. Estas directivas de evaluación están configuradas para *detectar* solo amenazas. Defender para Office 365 detecta mensajes dañinos para los informes, pero los mensajes no se actúan sobre ellos (por ejemplo, los mensajes detectados no se ponen en cuarentena). La configuración de estas directivas de evaluación se describe en la sección [Directivas en modo de auditoría](#policies-in-audit-mode) más adelante en este artículo.

  El modo auditoría proporciona acceso a informes personalizados para las amenazas detectadas por Defender para Office 365 en la página **Modo de evaluación** en <https://security.microsoft.com/atpEvaluation>.

- **Modo de bloqueo**: la plantilla Estándar para [directivas de seguridad preestablecidas](preset-security-policies.md) se activa y se usa para la prueba, y los usuarios que especifique incluir en la prueba se agregan a la directiva de seguridad preestablecida Estándar. Defender para Office 365 detecta y *toma medidas en* los mensajes *dañinos* (por ejemplo, los mensajes detectados están en cuarentena).

  La selección predeterminada y recomendada es limitar estas directivas de Defender para Office 365 a todos los usuarios de la organización. Pero durante o después de la configuración de la prueba, puede cambiar la asignación de directiva a usuarios, grupos o dominios de correo electrónico específicos en el portal de Microsoft 365 Defender o en [Exchange Online PowerShell](#policy-settings-associated-with-defender-for-office-365-trials).

  El modo de bloqueo no proporciona informes personalizados para las amenazas detectadas por Defender para Office 365. En su lugar, la información está disponible en los informes normales y las características de investigación de Defender para Office 365 Plan 2.

Un factor clave en el modo de auditoría frente al modo de bloqueo es cómo se entrega el correo electrónico a la organización de Microsoft 365:

- El correo de Internet fluye directamente en Microsoft 365, pero la suscripción actual solo tiene [Exchange Online Protection (EOP)](exchange-online-protection-overview.md) o [Defender para Office 365 Plan 1](overview.md#microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet).

  ![El correo fluye desde Internet a Microsoft 365, con protección contra EOP o Defender para Office 365 Plan 1.](../../media/mdo-trial-mail-flow.png)

  En estos entornos, puede seleccionar **el modo de auditoría** o **el modo de bloqueo**.

- Actualmente usa un servicio o dispositivo de terceros para la protección por correo electrónico de los buzones de Microsoft 365. El correo de Internet fluye a través del servicio de protección antes de su entrega a la organización de Microsoft 365. La protección de Microsoft 365 es lo más baja posible (nunca está completamente desactivada; por ejemplo, siempre se aplica la protección contra malware).

  ![El correo fluye desde Internet a través del dispositivo o servicio de protección de terceros antes de su entrega a Microsoft 365.](../../media/mdo-migration-before.png)

  En estos entornos, solo puede seleccionar **el modo de auditoría** . No es necesario cambiar el flujo de correo (registros MX).

### <a name="evaluation-vs-trial-for-defender-for-office-365"></a>Evaluación frente a prueba para Defender para Office 365

¿Cuál es la diferencia entre una evaluación y una evaluación de Defender para Office 365 Plan 2? ¿No son lo mismo? Bueno, sí y no. Esto es lo que necesita saber:

- Si aún no tiene licencias de Defender para Office 365 Plan 2 (por ejemplo, EOP independiente, Microsoft 365 E3, Microsoft 365 Empresa Premium o Defender para Office 365 Plan 1), puede iniciar la prueba desde el **Página de pruebas de Microsoft 365** en o en <https://security.microsoft.com/trialHorizontalHub> la página **Modo de evaluación** en <https://security.microsoft.com/atpEvaluation> el portal de Microsoft 365 Defender. En cualquier ubicación, puede seleccionar **el modo permitir** (directiva de seguridad preestablecida estándar) o el **modo de bloqueo** (directivas de evaluación) como se describió anteriormente.

  Independientemente de la ubicación que use, aprovisionaremos automáticamente las licencias de prueba necesarias Defender para Office 365 Plan 2 cuando se inscriba. Ya no se requieren pasos manuales o externos para obtener y asignar licencias del plan 2 en el Centro de administración de Microsoft 365. Las licencias de prueba son válidas durante 90 días:

  - Para las organizaciones sin Defender para Office 365 (por ejemplo, EOP independiente o Microsoft 365 E3) las características (en particular, las directivas) de Defender para Office 365 están disponibles durante el período de prueba.

  - Las organizaciones con Defender para Office 365 plan 1 (por ejemplo, Microsoft 365 Empresa Premium o suscripciones de complementos) tienen exactamente las mismas directivas que las organizaciones con Defender para Office 365  Plan 2 (protección contra suplantación en directivas anti phishing, directivas de datos adjuntos seguros y directivas de vínculos seguros). Las directivas de seguridad del **modo allow** (directiva de seguridad preestablecida estándar) o **del modo de bloqueo** (directivas de evaluación) no expiran ni dejan de funcionar después de 90 días. Lo que termina después de 90 días para estas organizaciones son las [funcionalidades de automatización, investigación, corrección y educación](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) del Plan 2 que no están presentes en el Plan 1.

- Si ya tiene Defender para Office 365 plan 2 (por ejemplo, como parte de una suscripción Microsoft 365 E5), nunca verá **Defender para Office 365** en la página **de pruebas de Microsoft 365** en <https://security.microsoft.com/trialHorizontalHub>. En su lugar, inicia la evaluación de Defender para Office 365 Plan a en la página **Modo de evaluación** en <https://security.microsoft.com/atpEvaluation> modo **permitido** (directiva de seguridad preestablecida estándar) o **modo de bloqueo** (directivas de evaluación).

  Por definición, estas organizaciones no requieren licencias de prueba de Defender para Office 365 Plan 2, por lo que sus evaluaciones tienen una duración ilimitada.

La información de la lista anterior se resume en la tabla siguiente:

|Organización|Modos disponibles|Inscríbase desde<br/>¿Página de evaluación?|Inscríbase desde<br/>¿Página de pruebas?|Evaluation<br/>period|
|---|---|:---:|:---:|---|
|EOP independiente<br/>(sin buzones de Exchange Online) <br/><br/> Microsoft 365 E3|Modo de auditoría <br/> Modo de bloqueo|Sí|Sí|90 días|
|Defender para Office 365 Plan 1 <br/><br/> Microsoft 365 Empresa Premium|Modo de auditoría <br/> Modo de bloqueo|Sí|Sí|Ilimitado<sup>\*</sup>|
|Microsoft 365 E5|Modo de auditoría <br/> Modo de bloqueo|Yes|No|Ilimitado|

<sup>\*</sup> Las directivas de seguridad del **modo allow** (directiva de seguridad preestablecida estándar) o **del modo de bloqueo** (directivas de evaluación) no expiran ni dejan de funcionar después de 90 días. Solo las [funcionalidades de automatización, investigación, corrección y educación](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) exclusivas de Defender para Office 365 Plan 2 dejan de funcionar después de 90 días.

## <a name="set-up-an-evaluation-or-trial-in-audit-mode"></a>Configuración de una evaluación o evaluación en modo de auditoría

Recuerde que, al evaluar Defender para Office 365 en modo de auditoría, se crean directivas de evaluación especiales para que Defender para Office 365 puedan detectar amenazas. La configuración de estas directivas de evaluación se describe en la sección [Directivas en modo de auditoría](#policies-in-audit-mode) más adelante en este artículo.

1. Inicie la evaluación en cualquiera de las ubicaciones disponibles en el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Por ejemplo:
   - En el banner de la parte superior de cualquier página de características de Defender para Office 365, haga clic en **Iniciar evaluación gratuita**.
   - En la página **de pruebas de Microsoft 365** en <https://security.microsoft.com/trialHorizontalHub>, busque y seleccione **Defender para Office 365**.
   - En la página **Modo de evaluación** de <https://security.microsoft.com/atpEvaluation>, haga clic en **Iniciar evaluación**.

2. En el cuadro de diálogo **Activar protección** , seleccione **No, Solo quiero informes** y, a continuación, haga clic en **Continuar**.

3. En el cuadro de diálogo **Seleccionar los usuarios que desea incluir** , configure los siguientes valores:

   - **Todos los usuarios**: esta es la opción predeterminada y recomendada.
   - **Seleccionar usuarios**: si selecciona esta opción, debe seleccionar los destinatarios internos a los que se aplica la evaluación:
     - **Usuarios**: los buzones de correo, los usuarios de correo o los contactos de correo especificados.
     - **Grupos**:
       - Miembros de los grupos de distribución o grupos de seguridad habilitados para correo especificados.
       - Los Grupos de Microsoft 365 especificados.
       - **Dominios**: todos los destinatarios de los [dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados en la organización.

     Haga clic en el cuadro correspondiente, comience a escribir un valor y seleccione el valor que desee de los resultados. Repita este proceso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Icono Quitar.](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

     For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results. For users, enter an asterisk (\*) by itself to see all available values.

   > [!NOTE]
   > Puede cambiar estas selecciones después de finalizar la configuración de la prueba, tal como se describe en la sección [Administrar la evaluación](#manage-your-evaluation-or-trial-of-defender-for-office-365) .
   >
   > Los diferentes tipos de condiciones o excepciones no son aditivos; son inclusivos. La evaluación o evaluación *solo* se aplica a los destinatarios que coinciden *con todos los* filtros de destinatarios especificados. Por ejemplo, configure una condición con los siguientes valores:
   >
   > - **Usuarios**: romain@contoso.com
   > - **Grupos**: Ejecutivos
   >
   > La evaluación o evaluación se aplica a romain@contoso.com *solo* si también es miembro del grupo Ejecutivos. Si no es miembro del grupo, no se le aplica la evaluación o el juicio.
   >
   > Del mismo modo, si usa el mismo filtro de destinatario como excepción, la evaluación o evaluación no se aplica a romain@contoso.com *solo* si también es miembro del grupo Ejecutivos. Si no es miembro del grupo, la evaluación o el juicio todavía se aplica a él.

   Cuando haya terminado, haga clic en **Continuar**.

4. En el cuadro de diálogo **Help us understand your mail flow (Ayudarnos a comprender el flujo de correo** ), configure las siguientes opciones:

   - Una de las siguientes opciones se selecciona automáticamente en función de la detección del registro MX para su dominio:

     - **Estoy usando un proveedor de servicios local o de terceros**: el registro MX de los puntos de dominio en otro lugar distinto de Microsoft 365. Esta selección requiere la siguiente configuración adicional después de hacer clic en **Siguiente**:

       1. En el cuadro de diálogo **Configuración de terceros o local** , configure las siguientes opciones:

          - **Seleccione un proveedor de servicios de terceros**: seleccione uno de los valores siguientes:
            - **Barracuda**
            - **Ironport**
            - **Mimecast**
            - **Punto de prueba**
            - **Sophos**
            - **Symantec**
            - **Trend Micro**
            - **Otros**

          - **Conector al que se va a aplicar esta evaluación**: seleccione el conector que se usa para el flujo de correo en Microsoft 365.

            [El filtrado mejorado para conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) (también conocido como *lista de omisión*) se configura automáticamente en el conector que especifique.

            Cuando un dispositivo o servicio de terceros se encuentra delante del correo electrónico que fluye a Microsoft 365, el filtrado mejorado para conectores identifica correctamente el origen de los mensajes de Internet y mejora en gran medida la precisión de la pila de filtrado de Microsoft (especialmente la [inteligencia de suplantación de identidad](anti-spoofing-protection.md), así como las funcionalidades posteriores a la vulneración en [el Explorador de amenazas](threat-explorer.md) y la [respuesta de & de investigación automatizada (AIR).](automated-investigation-response-office.md)

          - **Enumerar cada dirección IP de puerta de enlace a través de la que pasan los mensajes**: esta configuración solo está disponible si seleccionó **Otro** para **Seleccionar un proveedor de servicios de terceros**. Escriba una lista separada por comas de las direcciones IP que usa el servicio o dispositivo de protección de terceros para enviar correo a Microsoft 365.

          Cuando termine, haga clic en **Siguiente**.

       2. En el cuadro de diálogo **Reglas de flujo de correo de Exchange**, decida si necesita una regla de flujo de correo Exchange Online (también conocida como regla de transporte) que omita el filtrado de correo no deseado para los mensajes entrantes desde el dispositivo o servicio de protección de terceros.

          Es probable que ya tenga una regla de flujo de correo SCL=-1 en Exchange Online que permita que todo el correo entrante del servicio de protección omita (la mayoría) el filtrado de Microsoft 365. Muchos servicios de protección fomentan este método de regla de flujo de correo de nivel de confianza de correo no deseado (SCL) para los clientes de Microsoft 365 que usan sus servicios.

          Como se explicó en el paso anterior, el filtrado mejorado para conectores se configura automáticamente en el conector que especifique como origen de correo del servicio de protección.

          Activar el filtrado mejorado para conectores sin una regla SCL=-1 para el correo entrante desde el servicio de protección mejorará enormemente las capacidades de detección de las características de protección de EOP, como la [inteligencia de suplantación](anti-spoofing-protection.md) de identidad, y podría afectar a la entrega de esos mensajes recién detectados (por ejemplo, pasar a la carpeta Email correo no deseado o poner en cuarentena). Este impacto se limita a las directivas de EOP; como se explicó anteriormente, las directivas de Defender para Office 365 se crean en modo de auditoría.

          Para crear una regla de flujo de correo SCL=-1 o para revisar las reglas existentes, haga clic en el botón **Ir al Centro de administración de Exchange** de la página. Para obtener más información, consulte [Uso de reglas de flujo de correo para establecer el nivel de confianza de correo no deseado (SCL) en los mensajes de Exchange Online](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

          Cuando haya terminado, haga clic en **Finalizar**.

     - **Solo estoy usando Microsoft Exchange Online**: los registros MX de su dominio apuntan a Microsoft 365. No queda nada que configurar, por lo que haga clic en **Finalizar**.

   - **Compartir datos con Microsoft**: esta opción no está seleccionada de forma predeterminada, pero puede activar la casilla si lo desea.

5. Aparece un cuadro de diálogo de progreso cuando se configura la evaluación. Una vez completada la configuración, haga clic en **Listo**.

## <a name="set-up-an-evaluation-or-trial-in-blocking-mode"></a>Configuración de una evaluación o evaluación en modo de bloqueo

Recuerde que, al intentar Defender para Office 365 en modo de bloqueo, la seguridad preestablecida Estándar está activada y los usuarios especificados (algunos o todos) se incluyen en la directiva de seguridad preestablecida Estándar. Para obtener más información sobre la directiva de seguridad preestablecida estándar, consulte [Directivas de seguridad preestablecidas](preset-security-policies.md).

1. Inicie la prueba en cualquiera de las ubicaciones disponibles en el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Por ejemplo:
   - En el banner de la parte superior de cualquier página de características de Defender para Office 365, haga clic en **Iniciar evaluación gratuita**.
   - En la página **de pruebas de Microsoft 365** en <https://security.microsoft.com/trialHorizontalHub>, busque y seleccione **Defender para Office 365**.
   - En la página **Modo de evaluación** de <https://security.microsoft.com/atpEvaluation>, haga clic en **Iniciar evaluación**.

2. En el cuadro de diálogo **Activar protección** , seleccione **Sí, proteja mi organización mediante el bloqueo de amenazas** y, a continuación, haga clic en **Continuar**.

3. En el cuadro de diálogo **Seleccionar los usuarios que desea incluir** , configure los siguientes valores:

   - **Todos los usuarios**: esta es la opción predeterminada y recomendada.
   - **Seleccionar usuarios**: si selecciona esta opción, debe seleccionar los destinatarios internos a los que se aplica la prueba:
     - **Usuarios**: los buzones de correo, los usuarios de correo o los contactos de correo especificados.
     - **Grupos**:
       - Miembros de los grupos de distribución o grupos de seguridad habilitados para correo especificados.
       - Los Grupos de Microsoft 365 especificados.
     - **Dominios**: todos los destinatarios de los [dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados en la organización.

     Haga clic en el cuadro correspondiente, comience a escribir un valor y seleccione el valor que desee de los resultados. Repita este proceso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Icono Quitar.](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

     For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results. For users, enter an asterisk (\*) by itself to see all available values.

   > [!NOTE]
   > Puede cambiar estas selecciones después de finalizar la configuración de la prueba, tal como se describe en la sección [Administrar la evaluación](#manage-your-evaluation-or-trial-of-defender-for-office-365) .
   >
   > Los diferentes tipos de condiciones o excepciones no son aditivos; son inclusivos. La evaluación o evaluación *solo* se aplica a los destinatarios que coinciden *con todos los* filtros de destinatarios especificados. Por ejemplo, configure una condición con los siguientes valores:
   >
   > - **Usuarios**: romain@contoso.com
   > - **Grupos**: Ejecutivos
   >
   > La evaluación o evaluación se aplica a romain@contoso.com *solo* si también es miembro del grupo Ejecutivos. Si no es miembro del grupo, no se le aplica la evaluación o el juicio.
   >
   > Del mismo modo, si usa el mismo filtro de destinatario como excepción, la evaluación o evaluación no se aplica a romain@contoso.com *solo* si también es miembro del grupo Ejecutivos. Si no es miembro del grupo, la evaluación o el juicio todavía se aplica a él.

   Cuando haya terminado, haga clic en **Continuar**.

4. Aparece un cuadro de diálogo de progreso cuando se configura la evaluación. Una vez completada la instalación, haga clic en **Listo**.

## <a name="manage-your-evaluation-or-trial-of-defender-for-office-365"></a>Administrar la evaluación o evaluación de Defender para Office 365

Después de configurar la evaluación o evaluación en modo de auditoría o modo de bloqueo, la página <https://security.microsoft.com/atpEvaluation> **Modo de evaluación** en es la ubicación central para obtener información sobre cómo probar Defender para Office 365 Plan 2.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a Email & **directivas de** **colaboración** \> & reglas \> **Directivas** \> de amenazas, seleccione **Modo de evaluación** en la sección **Otros**. O bien, para ir directamente a la página **de evaluación de Microsoft Defender para Office 365**, use <https://security.microsoft.com/atpEvaluation>.

2. En la página **Microsoft Defender para Office 365 evaluación**, puede realizar las siguientes tareas:

   - Haga clic en **Comprar una suscripción de pago** para comprar Defender para Office 365 Plan 2.

   - Haga clic en **Administrar**. En el **control flotante Microsoft Defender para Office 365 evaluación** que aparece, puede realizar las siguientes tareas:

     - Cambie a quién se aplica la evaluación o evaluación, como se describió anteriormente en [Configuración de una evaluación o evaluación en modo de auditoría](#set-up-an-evaluation-or-trial-in-audit-mode) y [Configuración de una evaluación o evaluación en modo de bloqueo](#set-up-an-evaluation-or-trial-in-blocking-mode).

     - Para cambiar del **modo de auditoría** (directivas de evaluación) al modo de bloqueo (directiva de seguridad preestablecida estándar), haga clic en **Convertir a protección estándar** y, a continuación, haga clic en **Continuar** en el cuadro de diálogo que parece que se va a llevar al Asistente para **aplicar protección estándar** en la página **Directivas de seguridad preestablecidas** . Los destinatarios incluidos y excluidos existentes se copian. Para obtener más información, consulte [Uso del portal de Microsoft 365 Defender para asignar directivas de seguridad preestablecidas Estándar y Estricta a los usuarios](preset-security-policies.md#use-the-microsoft-365-defender-portal-to-assign-standard-and-strict-preset-security-policies-to-users).

       **Notas**:

       - Las directivas de la directiva de seguridad preestablecida Estándar tienen una prioridad mayor que las directivas de evaluación, lo que significa que las directivas de la seguridad preestablecida estándar siempre se aplican *antes* que las directivas de evaluación, incluso si ambas están presentes y activadas. Para desactivar las directivas de evaluación, use el botón **Desactivar** .
       - No hay ninguna manera automática de pasar del **modo de bloqueo** al **modo de auditoría**. Los pasos manuales son:
         1. Desactive la directiva de seguridad preestablecida estándar en la página **Directivas de seguridad preestablecidas** .
         2. Después de hacer clic en **Administrar** en la página **Microsoft Defender para Office 365 evaluación**, compruebe la presencia del botón **Desactivar**, que indica que las directivas de evaluación están activadas. Si ve el botón **Activar** , haga clic en él para activar las directivas de evaluación.
         3. Compruebe los usuarios a los que se aplica la evaluación.

     - Para desactivar las directivas de evaluación, haga clic en **Desactivar**. Para volver a activarlos, haga clic en **Activar**.

     Cuando haya terminado en el control flotante, haga clic en **Guardar**.

## <a name="reports-for-your-evaluation-or-trial-of-defender-for-office-365"></a>Informes para la evaluación o evaluación de Defender para Office 365

En esta sección se describen los informes que están disponibles en modo de auditoría y modo de bloqueo.

### <a name="reports-for-blocking-mode"></a>Informes para el modo de bloqueo

En **el modo de bloqueo**, los informes siguientes muestran detecciones por Defender para Office 365:

- La [vista Flujo de correo para el informe de estado de Mailflow](view-email-security-reports.md#mailflow-view-for-the-mailflow-status-report):

  - Los mensajes detectados como suplantación de usuario o suplantación de dominio por directivas anti phishing aparecen en el **bloque Suplantación**.
  - Los mensajes detectados durante la detonación de archivos o direcciones URL por directivas de datos adjuntos seguros o directivas de vínculos seguros aparecen en el **bloque Detonación**.

- Informe [de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report):

  - [Visualización de datos por información general](view-email-security-reports.md#view-data-by-overview):

    Puede filtrar la mayoría de las vistas por el **MDO** **Protegido por** valor para ver los efectos de Defender para Office 365.

  - [Visualización de datos por Email \> phish y desglose de gráficos por tecnología de detección](view-email-security-reports.md#view-data-by-email--phish-and-chart-breakdown-by-detection-technology)

    - Los mensajes [detectados por las campañas](campaigns.md) aparecen en **Campaña**.
    - Los mensajes detectados por datos adjuntos seguros aparecen en **Detonación de archivos** y **Reputación de detonación de archivos**.
    - Los mensajes detectados por la protección de suplantación de usuario en las directivas contra suplantación de identidad aparecen en **el dominio de suplantación**, **el usuario de suplantación** y la **suplantación de inteligencia de buzones**.
    - Los mensajes detectados por vínculos seguros aparecen en **la reputación de detonación de direcciones URL** y **detonación de direcciones URL**.

  - [Visualización de datos por Email \> malware y desglose de gráficos por tecnología de detección](view-email-security-reports.md#view-data-by-email--malware-and-chart-breakdown-by-detection-technology)

    - Los mensajes [detectados por las campañas](campaigns.md) aparecen en **Campaña**.
    - Los mensajes detectados por datos adjuntos seguros aparecen en **Detonación de archivos** y **Reputación de detonación de archivos**.
    - Los mensajes detectados por vínculos seguros aparecen en **la reputación de detonación de direcciones URL** y **detonación de direcciones URL**.

  - [Visualización de datos por Email \> spam y desglose de gráficos por tecnología de detección](view-email-security-reports.md#view-data-by-email--spam-and-chart-breakdown-by-detection-technology)

    Los mensajes detectados por vínculos seguros aparecen en **la reputación malintencionada de la dirección URL**.

  - [Desglose del gráfico por tipo de directiva](view-email-security-reports.md#chart-breakdown-by-policy-type)

    Los mensajes detectados por datos adjuntos seguros aparecen en **Datos adjuntos seguros**

  - [Visualización de datos por malware de contenido \>](view-email-security-reports.md#view-data-by-content--malware)

    Los archivos [malintencionados detectados por datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) aparecen en **la detonación de MDO**.

  - Informe [de remitentes y destinatarios principales](view-email-security-reports.md#top-senders-and-recipients-report)

    **Mostrar datos para los principales destinatarios de malware (MDO)** y **Mostrar datos para los principales destinatarios de phish (MDO).**

  - Informe [de protección de direcciones URL](view-reports-for-mdo.md#url-protection-report)

### <a name="reports-for-audit-mode"></a>Informes para el modo de auditoría

En **el modo de auditoría**, los informes siguientes muestran detecciones por Defender para Office 365:

- El [informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report) tiene **Evaluation: Yes/No** como una propiedad filtrable en las vistas siguientes:
  - [Visualización de datos por Email \> phish y desglose de gráficos por tecnología de detección](view-email-security-reports.md#view-data-by-email--phish-and-chart-breakdown-by-detection-technology)
  - [Visualización de datos por Email \> malware y desglose de gráficos por tecnología de detección](view-email-security-reports.md#view-data-by-email--malware-and-chart-breakdown-by-detection-technology)
  - [Visualización de datos por Email \> spam y desglose de gráficos por tecnología de detección](view-email-security-reports.md#view-data-by-email--spam-and-chart-breakdown-by-detection-technology)

- [El Explorador de amenazas](threat-explorer.md) muestra el siguiente banner en los detalles de detección de mensajes en la pestaña **Análisis** de **datos adjuntos incorrectos**, **url de correo no deseado + malware**, **dirección URL de Phish** y mensajes de **suplantación** detectados por la evaluación de Defender para Office 365 muestran el siguiente banner en los detalles de la entrada:

  ![Banner de notificación en los detalles del mensaje que la evaluación de Defender para Office 365 detectó un mensaje de correo electrónico malintencionado.](../../media/evalv2-detection-banner.png)

La **página de evaluación Microsoft Defender para Office 365** de <https://security.microsoft.com/atpEvaluation> consolida los informes de las directivas de la evaluación:

- Vínculos seguros
- Archivos adjuntos seguros
- Protección contra suplantación en directivas antiphishing

De forma predeterminada, los gráficos muestran datos de los últimos 30 días, pero puede filtrar el intervalo de fechas haciendo clic en ![el icono Calendario.](../../media/m365-cc-sc-add-internal-icon.png) **30 días** y seleccionando entre los siguientes valores adicionales que son inferiores a 30 días:

- 24 horas
- 7 días
- 14 días
- Intervalo de fechas personalizado

Puede hacer clic en el ![icono Descargar.](../../media/m365-cc-sc-download-icon.png) **Descargue** para descargar los datos del gráfico en un archivo .csv.

## <a name="required-permissions"></a>Permisos necesarios

Los permisos siguientes son necesarios en **Azure AD** para configurar una evaluación o evaluación de Defender para Microsoft 365:

- **Crear, modificar o eliminar una evaluación o evaluación**: Administrador de seguridad o Administrador global.
- **Ver directivas e informes de evaluación en modo de auditoría**: Administrador de seguridad o Lector de seguridad.

Para obtener más información sobre los permisos de Azure AD en el portal de Microsoft 365 Defender, consulte [Roles de Azure AD en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md#azure-ad-roles-in-the-microsoft-365-defender-portal).

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="q-do-i-need-to-manually-get-or-activate-trial-licenses"></a>P: ¿Es necesario obtener o activar manualmente licencias de prueba?

R: No. La prueba aprovisiona automáticamente las licencias Defender para Office 365 plan 2 si las necesita, como se describió anteriormente.

### <a name="q-how-do-i-extend-the-trial"></a>P: मैले कसरी ampliar la prueba?

R: Consulte [Ampliación de la prueba](/microsoft-365/commerce/try-or-buy-microsoft-365#extend-your-trial).

### <a name="q-what-happens-to-my-data-after-the-trial-expires"></a>P: ¿Qué ocurre con mis datos después de que expire la prueba?

R: Una vez que expire la prueba, tendrá acceso a los datos de prueba (datos de características de Defender para Office 365 que no tenía anteriormente) durante 30 días. Después de este período de 30 días, se eliminarán todas las directivas y datos asociados a la Defender para Office 365 prueba.

### <a name="q-how-many-times-can-i-use-the-defender-for-office-365-trial-in-my-organization"></a>P: ¿Cuántas veces puedo usar la prueba de Defender para Office 365 en mi organización?

R: Un máximo de 2 veces. Si la primera prueba expira, debe esperar al menos 30 días después de la fecha de expiración para poder inscribirse de nuevo en la Defender para Office 365 prueba. Después de la segunda prueba, no puede inscribirse en otra prueba.

### <a name="q-in-audit-mode-are-there-scenarios-where-defender-for-office-365-will-act-on-messages"></a>P: En el modo de auditoría, ¿hay escenarios en los que Defender para Office 365 actuarán en los mensajes?

R: Sí. Nadie en ningún programa o SKU puede desactivar o omitir la acción en los mensajes clasificados como malware o suplantación de identidad de alta confianza por parte del servicio.

En el modo de auditoría, la [protección contra la suplantación de identidad en EOP](set-up-anti-phishing-policies.md#spoof-settings) también toma medidas en los mensajes. Para evitar que la protección contra la suplantación de identidad actúe en los mensajes, cree una regla de flujo de correo de Exchange (también conocida como regla de transporte) en la que el correo electrónico entrante omita todos los tipos de filtrado que se pueden omitir (incluida la protección contra la suplantación de identidad). Para obtener instrucciones, consulte [Uso de reglas de flujo de correo para establecer el nivel de confianza de correo no deseado (SCL) en los mensajes de Exchange Online](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

### <a name="q-in-what-order-are-policies-evaluated"></a>P: ¿En qué orden se evalúan las directivas?

R: Consulte [Orden de precedencia para las directivas de seguridad preestablecidas y otras directivas](preset-security-policies.md#order-of-precedence-for-preset-security-policies-and-other-policies).

## <a name="reference"></a>Referencia

### <a name="policy-settings-associated-with-defender-for-office-365-trials"></a>Configuración de directiva asociada a las pruebas de Defender para Office 365

#### <a name="policies-in-audit-mode"></a>Directivas en modo de auditoría

> [!WARNING]
> No intente crear, modificar ni quitar las directivas de seguridad individuales asociadas a la evaluación de Defender para Office 365. El único método admitido para crear las directivas de seguridad individuales para la evaluación es iniciar la evaluación o la prueba en modo de auditoría en el portal de Microsoft 365 Defender por primera vez.

[Como se describió anteriormente](#audit-mode-vs-blocking-mode-for-defender-for-office-365), al elegir el modo de auditoría para su evaluación o evaluación, las directivas de evaluación con la configuración necesaria para observar pero no realizar acciones en los mensajes se crean automáticamente.

Para ver estas directivas y su configuración, ejecute el siguiente comando en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):

```powershell
Write-Output -InputObject ("`r`n"*3),"Evaluation anti-phishing policy",("-"*79);Get-AntiPhishPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Evaluation"; Write-Output -InputObject ("`r`n"*3),"Evaluation Safe Attachments policy",("-"*79);Get-SafeAttachmentPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Evaluation"; Write-Output -InputObject ("`r`n"*3),"Evaluation Safe Links policy",("-"*79);Get-SafeLinksPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Evaluation"
```

La configuración también se describe en las tablas siguientes.

##### <a name="anti-phishing-evaluation-policy-settings"></a>Configuración de directivas de evaluación contra suplantación de identidad (phishing)

|Configuración|Valor|
|---|---|
|Nombre|Directiva de evaluación|
|AdminDisplayName|Directiva de evaluación|
|AuthenticationFailAction|MoveToJmf|
|Habilitado|Verdadero|
|EnableFirstContactSafetyTips|Falso|
|EnableMailboxIntelligence|Verdadero|
|EnableMailboxIntelligenceProtection|Verdadero|
|EnableOrganizationDomainsProtection|Falso|
|EnableSimilarDomainsSafetyTips|Falso|
|EnableSimilarUsersSafetyTips|Falso|
|EnableSpoofIntelligence|Verdadero|
|EnableSuspiciousSafetyTip|Falso|
|EnableTargetedDomainsProtection|Falso|
|EnableTargetedUserProtection|Falso|
|EnableUnauthenticatedSender|Verdadero|
|EnableUnusualCharactersSafetyTips|Falso|
|EnableViaTag|Verdadero|
|ExcludedDomains|{}|
|ExcludedSenders|{}|
|ImpersonationProtectionState|Manual|
|IsDefault|Falso|
|MailboxIntelligenceProtectionAction|NoAction|
|MailboxIntelligenceProtectionActionRecipients|{}|
|MailboxIntelligenceQuarantineTag|DefaultFullAccessPolicy|
|PhishThresholdLevel|1|
|PolicyTag|Blanco|
|RecommendedPolicyType|Evaluation|
|SpoofQuarantineTag|DefaultFullAccessPolicy|
|TargetedDomainActionRecipients|{}|
|TargetedDomainProtectionAction|NoAction|
|TargetedDomainQuarantineTag|DefaultFullAccessPolicy|
|TargetedDomainsToProtect|{}|
|TargetedUserActionRecipients|{}|
|TargetedUserProtectionAction|NoAction|
|TargetedUserQuarantineTag|DefaultFullAccessPolicy|
|TargetedUsersToProtect|{}|

##### <a name="safe-attachments-evaluation-policy-settings"></a>Configuración de directivas de evaluación de datos adjuntos seguros

|Configuración|Valor|
|---|---|
|Nombre|Directiva de evaluación|
|Acción|Permitir|
|ActionOnError|Verdadero|
|AdminDisplayName|Directiva de evaluación|
|ConfidenceLevelThreshold|80|
|Habilitación|Verdadero|
|EnableOrganizationBranding|Falso|
|IsBuiltInProtection|Falso|
|IsDefault|Falso|
|OperationMode|Delay|
|QuarantineTag|AdminOnlyAccessPolicy|
|RecommendedPolicyType|Evaluation|
|Redirect|Falso|
|RedirectAddress|Blanco|
|ScanTimeout|30|

##### <a name="safe-links-evaluation-policy-settings"></a>Configuración de directivas de evaluación de vínculos seguros

|Configuración|Valor|
|---|---|
|Nombre|Directiva de evaluación|
|AdminDisplayName|Directiva de evaluación|
|AllowClickThrough|Verdadero|
|CustomNotificationText|Blanco|
|DeliverMessageAfterScan|Verdadero|
|DisableUrlRewrite|Verdadero|
|DoNotRewriteUrls|{}|
|EnableForInternalSenders|Falso|
|EnableOrganizationBranding|Falso|
|EnableSafeLinksForEmail|Verdadero|
|EnableSafeLinksForOffice|Falso|
|EnableSafeLinksForTeams|Falso|
|IsBuiltInProtection|Falso|
|LocalizedNotificationTextList|{}|
|RecommendedPolicyType|Evaluation|
|ScanUrls|Verdadero|
|TrackClicks|Verdadero|

##### <a name="use-powershell-to-configure-recipient-conditions-and-exceptions-to-the-evaluation-in-audit-mode"></a>Uso de PowerShell para configurar las condiciones de destinatario y las excepciones a la evaluación en modo de auditoría

Una regla asociada a las directivas de evaluación de Defender para Office 365 controla las condiciones y excepciones del destinatario a la evaluación.

Para ver la regla asociada a la evaluación, ejecute el siguiente comando en Exchange Online PowerShell:

```powershell
Get-ATPEvaluationRule
```

Para usar Exchange Online PowerShell para modificar a quién se aplica la evaluación, use la sintaxis siguiente:

```powershell
Set-ATPEvaluationRule -Identity "Evaluation Rule" -SentTo <"user1","user2",... | $null> -ExceptIfSentTo <"user1","user2",... | $null> -SentToMemberOf <"group1","group2",... | $null> -ExceptIfSentToMemberOf <"group1","group2",... | $null> -RecipientDomainIs <"domain1","domain2",... | $null> -ExceptIfRecipientDomainIs <"domain1","domain2",... | $null>
```

En este ejemplo se configuran las excepciones de la evaluación para los buzones de operaciones de seguridad (SecOps) especificados.

```powershell
Set-ATPEvaluationRule -Identity "Evaluation Rule" -ExceptIfSentTo "SecOps1","SecOps2"
```

##### <a name="use-powershell-to-turn-on-or-turn-off-the-evaluation-in-audit-mode"></a>Uso de PowerShell para activar o desactivar la evaluación en modo de auditoría

Para activar o desactivar la evaluación en modo de auditoría, habilite o deshabilite la regla asociada a la evaluación. El valor de la propiedad State de la regla de evaluación muestra si la regla es Enabled o Disabled.

Ejecute el siguiente comando para determinar si la evaluación está habilitada o deshabilitada actualmente:

```powershell
Get-ATPEvaluationRule -Identity "Evaluation Rule" | Format-Table Name,State
```

Ejecute el siguiente comando para desactivar la evaluación si está activada:

```powershell
Disable-ATPEvaluationRule -Identity "Evaluation Rule"
```

Ejecute el siguiente comando para activar la evaluación si está desactivada:

```powershell
Enable-ATPEvaluationRule -Identity "Evaluation Rule"
```

#### <a name="policies-and-rules-in-block-mode"></a>Directivas y reglas en modo de bloque

[Como se describió anteriormente](#audit-mode-vs-blocking-mode-for-defender-for-office-365), al elegir el modo de bloqueo para la prueba, las directivas se crean mediante la plantilla Estándar para [las directivas de seguridad preestablecidas](preset-security-policies.md).

Para usar Exchange Online PowerShell para ver las directivas de seguridad individuales asociadas a la directiva de seguridad preestablecida Estándar y para usar Exchange Online PowerShell para ver y configurar las condiciones y excepciones de destinatarios para la directiva de seguridad [preestablecida, consulte Directivas de seguridad preestablecidas en Exchange Online PowerShell](preset-security-policies.md#preset-security-policies-in-exchange-online-powershell).
