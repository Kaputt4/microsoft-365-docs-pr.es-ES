---
title: Pruebe Microsoft Defender para Office 365
description: ''
keywords: ''
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: bda7d0cc95132f1f421fc49e5fc6e7453267c4b0
ms.sourcegitcommit: bcbcbd4ddc72ad2fed629619d23fac5827d072bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2022
ms.locfileid: "64507277"
---
# <a name="try-microsoft-defender-for-office-365"></a>Pruebe Microsoft Defender para Office 365

> [!NOTE]
> La característica que se describe en este artículo está en Versión preliminar, no está disponible en todas las organizaciones y está sujeta a cambios.

El portal **de pruebas** unificado del portal de Microsoft 365 Defender proporciona un único punto de entrada para las experiencias de prueba y evaluación separadas anteriormente para Microsoft Defender para Office 365. El objetivo es permitirle probar las características de Defender para Office 365 Plan 2 durante 30 días antes de comprometerse completamente con él. Sin embargo, hay diferencias en las experiencias de evaluación basadas en la naturaleza de su Microsoft 365 organización:

- Ya tienes Microsoft 365 buzones de correo, pero actualmente estás usando un servicio o dispositivo de terceros para la protección de correo electrónico. El correo de Internet fluye a través del servicio de protección antes de la entrega a Microsoft 365 organización. Microsoft 365 protección contra malware es lo más baja posible (nunca está completamente desactivada; por ejemplo, siempre se aplica la protección contra malware).

  ![El correo fluye desde Internet a través del dispositivo o servicio de protección de terceros antes de la entrega Microsoft 365.](../../media/mdo-migration-before.png)

  En estos entornos, solo puede probar Defender para Office 365 en *modo auditoría*. No es necesario cambiar el flujo de correo (registros MX) para intentar Defender para Office 365.

- Ya tiene una Microsoft 365 organización. El correo de Internet fluye directamente Microsoft 365, pero la suscripción actual solo tiene Exchange Online Protection [(EOP)](exchange-online-protection-overview.md) o [Defender para Office 365 plan 1](overview.md#microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet).

  ![El correo fluye de Internet a Microsoft 365, con protección de EOP o Defender para Office 365 Plan 1.](../../media/mdo-trial-mail-flow.png)

  En estos entornos, puede probar Defender para Office 365 en modo *auditoría* o en *modo de bloqueo*.

Se le invita a iniciar la prueba en varias Defender para Office 365 de características en el portal Microsoft 365 Defender en <https://security.microsoft.com>. La ubicación centralizada para iniciar la prueba se encuentra en la página **Pruebas** en <https://security.microsoft.com/atpEvaluation>.

El resto de este artículo explica la diferencia entre el modo de bloqueo del modo de auditoría, cómo configurar evaluaciones y otros detalles.

## <a name="overview-of-defender-for-office-365"></a>Información general sobre Defender para Office 365

Defender para Office 365 ayuda a las organizaciones a proteger su empresa ofreciendo una lista completa de capacidades. Para obtener más información, [vea Microsoft Defender para Office 365](defender-for-office-365.md).

También puede obtener más información sobre Defender para Office 365 en esta [guía interactiva](https://aka.ms/MS365D.InteractiveGuide).

![Microsoft Defender para Office 365 diagrama conceptual.](../../media/microsoft-defender-for-office-365.png)

## <a name="policies-in-blocking-mode-or-audit-mode"></a>Directivas en modo de bloqueo o modo de auditoría

Al evaluar la Defender para Office 365, las directivas que controlan las características de protección en Microsoft 365 están presentes:

- **Exchange Online Protection (EOP):** No se crean directivas nuevas o especiales. Las directivas de EOP existentes pueden actuar en mensajes (por ejemplo, enviar mensajes a la carpeta correo no deseado o poner en cuarentena):

  - [Directivas antimalware](anti-malware-protection.md)
  - [Protección contra correo no deseado entrante](anti-spam-protection.md)
  - [Protección contra la suplantación de identidad en directivas contra suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings)

  Las directivas predeterminadas para estas características siempre están en, se aplican a todos los destinatarios y siempre se aplican en último lugar (después de cualquier directiva personalizada).

- **Defender para Office 365**: Las directivas que son exclusivas de Defender para Office 365 se crean para la evaluación de Defender para Office 365:

  - [Protección contra suplantación en directivas antiphishing](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - [Caja fuerte datos adjuntos para mensajes de correo electrónico](safe-attachments.md)
  - [Caja fuerte vínculos para mensajes de correo electrónico y Microsoft Teams](safe-links.md)

  Sin embargo, la naturaleza de estas directivas es diferente en el modo de bloqueo y el modo de auditoría:

  - **Modo auditoría**: se crean directivas regulares, pero las directivas solo están configuradas para *detectar amenazas* . Defender para Office 365 detecta mensajes dañinos para los informes, pero los mensajes no se actúan (por ejemplo, los mensajes detectados no se ponen en cuarentena).

  - **Modo de bloqueo**: las directivas se crean con la plantilla Estándar para directivas [de seguridad preestablecidas](preset-security-policies.md). Defender para Office 365 detecta y *realiza acciones en mensajes* dañinos (por ejemplo, los mensajes *detectados* se ponen en cuarentena).

  La selección predeterminada y recomendada es el ámbito de estas Defender para Office 365 directivas para todos los usuarios de la organización. Pero durante o después de la instalación, puede cambiar la asignación de directiva a usuarios, grupos o dominios de correo electrónico específicos.

**Notas**:

- Caja fuerte los vínculos detonarán las direcciones URL en el flujo de correo. Para evitar que se detonen direcciones URL específicas, use la lista de inquilinos permitidos o bloqueados. Para obtener más información, vea [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).
- Caja fuerte vínculos no encapsulan los vínculos url en los cuerpos de mensajes de correo electrónico.
- La configuración de la directiva de evaluación se describe en la [sección Configuración de directiva de evaluación](#evaluation-policy-settings) más adelante en este artículo.

## <a name="set-up-an-evaluation-in-audit-mode"></a>Configurar una evaluación en modo auditoría

1. Haga clic **en Iniciar evaluación**.

2. En el **cuadro de diálogo Activar protección** , seleccione **No, solo quiero** informes y, a continuación, haga clic en **Continuar**.

3. En el **cuadro de diálogo Seleccionar los usuarios que desea incluir** , configure las siguientes opciones:

   - **Todos los usuarios**: esta es la opción predeterminada y recomendada.
   - **Seleccionar usuarios**: si selecciona esta opción, debe seleccionar a quién se aplica la evaluación:
     - **Usuarios**: los buzones, usuarios de correo o contactos de correo especificados de su organización.
     - **Grupos**: los grupos de distribución, los grupos de seguridad habilitados para correo electrónico o los Grupos de Microsoft 365 especificados de la organización.
     - **Dominios**: todos los destinatarios de los [dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados en la organización.

     Haga clic en el cuadro correspondiente, comience a escribir un valor y seleccione el valor que desee de los resultados. Repita este proceso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Icono Quitar.](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

     Para los usuarios o grupos, puede utilizar la mayoría de los identificadores (nombre, nombre para mostrar, alias, dirección de correo electrónico, nombre de la cuenta, etc.), pero el nombre para mostrar correspondiente se muestra en los resultados. Para los usuarios, introduzca un asterisco (\*) por sí mismo para ver todos los valores disponibles.

   > [!NOTE]
   > Puede cambiar estas selecciones después de finalizar la configuración de la evaluación.

   Cuando haya terminado, haga clic en **Continuar**.

4. En el **cuadro de diálogo Ayuda para comprender el flujo de** correo, configure las siguientes opciones:

   - **Compartir datos con Microsoft**: esta opción está seleccionada de forma predeterminada, pero puedes borrar la casilla si quieres.

   - Una de las siguientes opciones se selecciona automáticamente en función de nuestra detección del registro MX para su dominio:

     - **Estoy usando un proveedor** de servicios local o de terceros: el registro MX de los puntos de dominio en otro lugar que no sea Microsoft 365. Esta selección requiere la siguiente configuración adicional después de hacer clic en **Siguiente**:

       1. En el **cuadro de diálogo Configuración de terceros o local** , configure las siguientes opciones:

          - **Seleccionar un proveedor de servicios de terceros**: seleccione uno de los siguientes valores:
            - **Barracuda**
            - **IronPort**
            - **Mimecast**
            - **Proofpoint**
            - **Sophos**
            - **Symantec**
            - **Trend Micro**
            - **Otros**

          - **Conector para aplicar esta evaluación** a: Seleccione el conector que se usa para el flujo de correo en Microsoft 365.

            [El filtrado mejorado para conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) (también conocido como *listado* de omitir) se configura automáticamente en el conector que especifique.

            Cuando un servicio o dispositivo de terceros se encuentra desde Microsoft 365, el filtrado mejorado para conectores identifica correctamente el origen de los mensajes de Internet y mejora en gran medida la precisión de la pila de filtrado de Microsoft (especialmente la inteligencia de suplantación[, así](anti-spoofing-protection.md) como las capacidades posteriores a la [](threat-explorer.md) infracción en el Explorador de amenazas y la respuesta & de investigación automatizada [(AIR)](automated-investigation-response-office.md)).

          - **Enumerar cada dirección IP de** puerta de enlace por la que pasan los mensajes: esta configuración solo está disponible si seleccionó **Otro** para **Seleccionar un proveedor de servicios de terceros**. Escriba una lista separada por comas de las direcciones IP que usa el dispositivo o el servicio de protección de terceros para enviar correo a Microsoft 365.

          Cuando termine, haga clic en **Siguiente**.

       2. En el cuadro de diálogo reglas de flujo de correo de **Exchange**, decida si necesita una regla de flujo de correo de Exchange Online (también conocida como regla de transporte) que omite el filtrado de correo no deseado para los mensajes entrantes del dispositivo o servicio de protección de terceros.

          Es probable que ya tenga una regla de flujo de correo SCL=-1 en Exchange Online que permita que todo el correo entrante del servicio de protección omita (la mayoría) Microsoft 365 filtrado. Muchos servicios de protección fomentan este método de regla de flujo de correo de nivel de confianza de correo no deseado (SCL) para Microsoft 365 clientes que usan sus servicios.

          Como se explicó en el paso anterior, el filtrado mejorado para conectores se configura automáticamente en el conector que especifique como origen de correo del servicio de protección.

          Activar el filtrado mejorado para conectores sin una regla SCL=-1 para el correo entrante del servicio de protección mejorará enormemente las capacidades de detección de características de protección de EOP, como la inteligencia suplantada [, y](anti-spoofing-protection.md) podría afectar a la entrega de esos mensajes recién detectados (por ejemplo, moverse a la carpeta correo no deseado o a la cuarentena). Este impacto se limita a las directivas de EOP; como se explicó anteriormente, Defender para Office 365 directivas se crean en modo auditoría.

          Para crear una regla de flujo de correo SCL=-1 o para revisar las reglas existentes, haga clic en el botón Ir a **Exchange** centro de administración de la página. Para obtener más información, vea [Use mail flow rules to set the spam confidence level (SCL) in messages in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

          Cuando haya terminado, haga clic en **Finalizar**.

     - **Solo estoy usando Microsoft Exchange Online**: los registros MX de Yhe para el dominio apuntan a Microsoft 365. No queda nada que configurar, por lo que haga clic en **Finalizar**.

5. Aparece un cuadro de diálogo de progreso cuando se configura la evaluación. Cuando se haya completado la configuración, haga clic **en Listo**.

## <a name="set-up-an-evaluation-in-blocking-mode"></a>Configurar una evaluación en modo de bloqueo

1. Haga clic **en Iniciar evaluación**.

2. En el **cuadro de diálogo Activar protección** , seleccione **Sí, proteja mi organización** bloqueando las amenazas y, a continuación, haga clic en **Continuar**.

3. En el **cuadro de diálogo Seleccionar los usuarios que desea incluir** , configure las siguientes opciones:

   - **Todos los usuarios**: esta es la opción predeterminada y recomendada.
   - **Seleccionar usuarios**: si selecciona esta opción, debe seleccionar a quién se aplica la evaluación:
     - **Usuarios**: los buzones, usuarios de correo o contactos de correo especificados de su organización.
     - **Grupos**: los grupos de distribución, los grupos de seguridad habilitados para correo electrónico o los Grupos de Microsoft 365 especificados de la organización.
     - **Dominios**: todos los destinatarios de los [dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados en la organización.

     Haga clic en el cuadro correspondiente, comience a escribir un valor y seleccione el valor que desee de los resultados. Repita este proceso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Icono Quitar.](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

     Para los usuarios o grupos, puede utilizar la mayoría de los identificadores (nombre, nombre para mostrar, alias, dirección de correo electrónico, nombre de la cuenta, etc.), pero el nombre para mostrar correspondiente se muestra en los resultados. Para los usuarios, introduzca un asterisco (\*) por sí mismo para ver todos los valores disponibles.

   > [!NOTE]
   > Puede cambiar estas selecciones después de finalizar la configuración de la evaluación.

   Cuando haya terminado, haga clic en **Continuar**.

4. Aparece un cuadro de diálogo de progreso cuando se configura la evaluación. Cuando finalice la instalación, haga clic **en Listo**.

## <a name="reporting-in-audit-mode"></a>Informes en modo auditoría

- El [informe de estado de protección](view-email-security-reports.md#threat-protection-status-report) contra amenazas muestra las detecciones Defender para Office 365 en las siguientes vistas:
  - [Ver datos por malware de \> correo electrónico y desglose de gráficos por tecnología de detección](view-email-security-reports.md#view-data-by-email--malware-and-chart-breakdown-by-detection-technology)
  - [Ver datos por correo electrónico no \> deseado y desglose de gráficos por tecnología de detección](view-email-security-reports.md#view-data-by-email--spam-and-chart-breakdown-by-detection-technology)
  - [Ver datos por phishing de \> correo electrónico y desglose de gráficos por tecnología de detección](view-email-security-reports.md#view-data-by-email--phish-and-chart-breakdown-by-detection-technology)

- En [el Explorador de](threat-explorer.md) amenazas, los mensajes detectados por la evaluación Defender para Office 365 muestran el siguiente banner en los detalles de la entrada:

  ![Banner de notificación en los detalles del mensaje en el que se Defender para Office 365 evaluación detectó un mensaje de correo electrónico malintencionado.](../../media/evalv2-detection-banner.png)

<!--- This stuff is likely not applicable for V2 reporting --->

La **Microsoft Defender para Office 365 de evaluación** en <https://security.microsoft.com/atpEvaluation> consolida los informes de las directivas de la evaluación:

- Protección contra suplantación en directivas antiphishing
- Vínculos seguros
- Archivos adjuntos seguros

De forma predeterminada, los gráficos muestran datos de los últimos 30 días, pero puede filtrar el intervalo de fechas haciendo clic en ![Icono de calendario.](../../media/m365-cc-sc-add-internal-icon.png) **30 días y** selección de los siguientes valores adicionales que son inferiores a 30 días:

- 24 horas
- 7 días
- 14 días
- Intervalo de fechas personalizado

Puede hacer clic en ![Descargar icono.](../../media/m365-cc-sc-download-icon.png) **Descargar** para descargar los datos del gráfico en un .csv archivo.

## <a name="required-permissions"></a>Permisos necesarios

Los permisos necesarios en Azure AD para  configurar una evaluación de Defender para Microsoft 365 se describen en la siguiente lista:

- **Crear, modificar o eliminar una evaluación**: Administrador de seguridad o Administrador global.
- **Ver directivas e informes de evaluación**: Administrador de seguridad o Lector de seguridad.

Para obtener más información acerca Azure AD permisos en el portal de Microsoft 365 Defender, vea Azure AD [roles en el portal Microsoft 365 Defender web](permissions-microsoft-365-security-center.md#azure-ad-roles-in-the-microsoft-365-defender-portal)

## <a name="evaluation-policy-settings"></a>Configuración de directiva de evaluación

La configuración del Defender para Office 365 que se crea específicamente para la evaluación se describe en las tablas siguientes:

**Configuración de directiva de evaluación contra suplantación de identidad**:

|Configuración|Valor|
|---|---|
|AdminDisplayName|Directiva de evaluación|
|AuthenticationFailAction|MoveToJmf|
|Habilitado|True|
|EnableFirstContactSafetyTips|False|
|EnableMailboxIntelligence|True|
|EnableMailboxIntelligenceProtection|True|
|EnableOrganizationDomainsProtection|False|
|EnableSimilarDomainsSafetyTips|False|
|EnableSimilarUsersSafetyTips|False|
|EnableSpoofIntelligence|True|
|EnableSuspiciousSafetyTip|False|
|EnableTargetedDomainsProtection|False|
|EnableTargetedUserProtection|False|
|EnableUnauthenticatedSender|True|
|EnableUnusualCharactersSafetyTips|False|
|EnableViaTag|True|
|Guid|Valor GUID|
|ImpersonationProtectionState|Manual|
|IsDefault|False|
|MailboxIntelligenceProtectionAction|NoAction|
|MailboxIntelligenceProtectionActionRecipients|{}|
|MailboxIntelligenceQuarantineTag|DefaultFullAccessPolicy|
|Nombre|Directiva de evaluación|
|PhishThresholdLevel|1|
|RecommendedPolicyType|Evaluation|
|SpoofQuarantineTag|DefaultFullAccessPolicy|
|TargetedDomainActionRecipients|{}|
|TargetedDomainProtectionAction|NoAction|
|TargetedDomainQuarantineTag|DefaultFullAccessPolicy|
|TargetedUserActionRecipients|{}|
|TargetedUserProtectionAction|NoAction|
|TargetedUserQuarantineTag|DefaultFullAccessPolicy|
|||
|AntiPhishPolicyLevelDataList|en blanco|
|AntiSpoofEnforcementType|Alta|
|AuthenticationSafetyTipText|en blanco|
|AuthenticationSoftPassSafetyTipText|en blanco|
|EnableAuthenticationSafetyTip|False|
|EnableAuthenticationSoftPassSafetyTip|False|
|PolicyTag|en blanco|
|SimilarUsersSafetyTipsCustomText|en blanco|
|TreatSoftPassAsAuthenticated|True|
|UnusualCharactersSafetyTipsCustomText|en blanco|
|||
|ExcludedDomains|{}|
|ExcludedSenders|{}|
|TargetedDomainsToProtect|{}|
|TargetedUsersToProtect|{}|

**Caja fuerte de directiva de evaluación de datos adjuntos**:

|Configuración|Valor|
|---|---|
|Action|Permitir|
|ActionOnError|True|
|AdminDisplayName|Directiva de evaluación|
|ConfidenceLevelThreshold|80|
|Habilitación|True|
|EnableOrganizationBranding|False|
|Guid|Valor GUID|
|IsBuiltInProtection|False|
|IsDefault|False|
|Nombre|Directiva de evaluación|
|OperationMode|Delay|
|QuarantineTag|AdminOnlyAccessPolicy|
|RecommendedPolicyType|Evaluation|
|Redirect|False|
|RedirectAddress|{}|
|ScanTimeout|30|

**Caja fuerte de directiva de evaluación de vínculos**:

|Configuración|Valor|
|---|---|
|AdminDisplayName|Directiva de evaluación|
|AllowClickThrough|False|
|CustomNotificationText|en blanco|
|DeliverMessageAfterScan|True|
|DisableUrlRewrite|True|
|DoNotRewriteUrls|{}|
|EnableForInternalSenders|False|
|EnableOrganizationBranding|False|
|EnableSafeLinksForTeams|True|
|Guid|Valor GUID|
|IsBuiltInProtection|False|
|IsDefault|False|
|IsEnabled|True|
|LocalizedNotificationTextList|{}|
|Nombre|"EvaluationPolicy"|
|RecommendedPolicyType|Evaluation|
|ScanUrls|True|
|TrackClicks|True|
|||
|DoNotAllowClickThrough|en blanco|
|DoNotTrackUserClicks|False|
|EnableSafeLinksForEmail|True|
|EnableSafeLinksForOffice|True|
|ExcludedUrls|{}|
|WhiteListedUrls|en blanco|
