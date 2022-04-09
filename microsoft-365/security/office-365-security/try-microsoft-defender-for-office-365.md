---
title: Pruebe a evaluar Defender para Office 365
description: Obtenga información sobre cómo evaluar y probar las funcionalidades de Microsoft Defender para Office 365 sin afectar al flujo de correo existente.
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
ROBOTS: ''
ms.openlocfilehash: 95cc11956dfe597b70f18954723f914e057193a6
ms.sourcegitcommit: dd5fc139affb4cba4089cbdb2c478968b680699a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2022
ms.locfileid: "64746710"
---
# <a name="try-microsoft-defender-for-office-365"></a>Pruebe Microsoft Defender para Office 365

> [!NOTE]
> La característica que se describe en este artículo está en versión preliminar, no está disponible en todas las organizaciones y está sujeta a cambios.

El portal **de pruebas** unificadas del portal de Microsoft 365 Defender proporciona un único punto de entrada para las experiencias de evaluación y evaluación anteriormente independientes para Microsoft Defender para Office 365. La intención es permitirle probar las características de Defender para Office 365 Plan 2 durante 90 días antes de confirmarlo por completo. Sin embargo, hay diferencias en las experiencias de evaluación basadas en la naturaleza de la organización Microsoft 365:

- Ya tiene Microsoft 365 buzones, pero actualmente usa un servicio o dispositivo de terceros para la protección de correo electrónico. El correo de Internet fluye a través del servicio de protección antes de la entrega a la organización de Microsoft 365. Microsoft 365 protección es lo más baja posible (nunca está completamente desactivada; por ejemplo, la protección contra malware siempre se aplica).

  ![El correo fluye desde Internet a través del servicio o dispositivo de protección de terceros antes de la entrega en Microsoft 365.](../../media/mdo-migration-before.png)

  En estos entornos, solo puede probar Defender para Office 365 en modo *de auditoría*. No es necesario cambiar el flujo de correo (registros MX) para intentar Defender para Office 365.

- Ya tiene una organización Microsoft 365. El correo de Internet fluye directamente Microsoft 365, pero la suscripción actual solo tiene [Exchange Online Protection (EOP)](exchange-online-protection-overview.md) o [Defender para Office 365 Plan 1](overview.md#microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet).

  ![El correo fluye desde Internet a Microsoft 365, con protección contra EOP o Defender para Office 365 Plan 1.](../../media/mdo-trial-mail-flow.png)

  En estos entornos, puede probar Defender para Office 365 en modo *de auditoría* o en *modo de bloqueo*.

Se le invita a iniciar la prueba en varias ubicaciones de características de Defender para Office 365 en el portal de Microsoft 365 Defender en <https://security.microsoft.com>. La ubicación centralizada para iniciar la prueba se encuentra en la página **Pruebas** en <https://security.microsoft.com/atpEvaluation>.

En el resto de este artículo se explica la diferencia entre el modo de bloqueo del modo de auditoría, cómo configurar las evaluaciones y otros detalles.

## <a name="overview-of-defender-for-office-365"></a>Introducción a Defender para Office 365

Defender para Office 365 ayuda a las organizaciones a proteger su empresa al ofrecer una lista completa de funcionalidades. Para obtener más información, consulte [Microsoft Defender para Office 365](defender-for-office-365.md).

También puede obtener más información sobre Defender para Office 365 en esta [guía interactiva](https://aka.ms/MS365D.InteractiveGuide).

![Microsoft Defender para Office 365 diagrama conceptual.](../../media/microsoft-defender-for-office-365.png)

## <a name="policies-in-blocking-mode-or-audit-mode"></a>Directivas en modo de bloqueo o modo de auditoría

Al evaluar Defender para Office 365, están presentes las directivas que controlan las características de protección de Microsoft 365:

- **Exchange Online Protection (EOP):** no se crean directivas nuevas o especiales. Las directivas de EOP existentes pueden actuar sobre los mensajes (por ejemplo, enviar mensajes a la carpeta Correo no deseado o poner en cuarentena):

  - [Directivas antimalware](anti-malware-protection.md)
  - [Protección contra correo no deseado entrante](anti-spam-protection.md)
  - [Protección contra la suplantación de identidad en directivas contra suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings)

  Las directivas predeterminadas para estas características siempre están activadas, se aplican a todos los destinatarios y siempre se aplican en último lugar (después de las directivas personalizadas).

- **Defender para Office 365**: Se crean directivas exclusivas de Defender para Office 365 para la evaluación de Defender para Office 365:

  - [Protección contra suplantación en directivas antiphishing](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - [datos adjuntos de Caja fuerte para mensajes de correo electrónico](safe-attachments.md)
  - [vínculos de Caja fuerte para mensajes de correo electrónico y Microsoft Teams](safe-links.md)

  Sin embargo, la naturaleza de estas directivas es diferente en modo de bloqueo y modo de auditoría:

  - **Modo de auditoría**: se crean directivas regulares, pero las directivas solo están configuradas para *detectar* amenazas. Defender para Office 365 detecta mensajes dañinos para los informes, pero los mensajes no se actúan sobre ellos (por ejemplo, los mensajes detectados no se ponen en cuarentena).

  - **Modo de bloqueo**: las directivas se crean mediante la plantilla Estándar para [las directivas de seguridad preestablecidas](preset-security-policies.md). Defender para Office 365 detecta y *toma medidas en* los mensajes *dañinos* (por ejemplo, los mensajes detectados están en cuarentena).

  La selección predeterminada y recomendada es limitar estas directivas de Defender para Office 365 a todos los usuarios de la organización. Pero durante o después de la instalación, puede cambiar la asignación de directivas a usuarios, grupos o dominios de correo electrónico específicos.

**Notas**:

- Caja fuerte Vínculos detonará las direcciones URL en el flujo de correo. Para evitar que se detonen direcciones URL específicas, use la lista de permitidos o bloqueados de inquilinos. Para obtener más información, vea [Administrar la lista de permitidos o bloqueados de inquilinos](tenant-allow-block-list.md).
- Caja fuerte Vínculos no encapsula los vínculos URL en los cuerpos de mensajes de correo electrónico.
- La configuración de la directiva de evaluación se describe en la sección [Configuración de directivas de evaluación](#evaluation-policy-settings) más adelante en este artículo.

## <a name="set-up-an-evaluation-in-audit-mode"></a>Configuración de una evaluación en modo de auditoría

1. Haga clic en **Iniciar evaluación**.

2. En el cuadro de diálogo **Activar protección** , seleccione **No, Solo quiero informes** y, a continuación, haga clic en **Continuar**.

3. En el cuadro de diálogo **Seleccionar los usuarios que desea incluir** , configure los siguientes valores:

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

4. En el cuadro de diálogo **Help us understand your mail flow (Ayudarnos a comprender el flujo de correo** ), configure las siguientes opciones:

   - **Compartir datos con Microsoft**: esta opción está seleccionada de forma predeterminada, pero puede desactivar la casilla si lo desea.

   - Una de las siguientes opciones se selecciona automáticamente en función de la detección del registro MX para su dominio:

     - **Estoy usando un proveedor de servicios local o de terceros**: el registro MX de los puntos de dominio en otro lugar que no sea Microsoft 365. Esta selección requiere la siguiente configuración adicional después de hacer clic en **Siguiente**:

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

            Cuando un servicio o dispositivo de terceros se encuentra en de Microsoft 365, el filtrado mejorado para conectores identifica correctamente el origen de los mensajes de Internet y mejora en gran medida la precisión de la pila de filtrado de Microsoft (especialmente la [inteligencia de suplantación de identidad](anti-spoofing-protection.md), así como las funcionalidades posteriores a la vulneración en [el Explorador de amenazas](threat-explorer.md) y la [investigación automatizada & Respuesta (AIR)](automated-investigation-response-office.md)).

          - **Enumerar cada dirección IP de puerta de enlace a través de la que pasan los mensajes**: esta configuración solo está disponible si seleccionó **Otro** para **Seleccionar un proveedor de servicios de terceros**. Escriba una lista separada por comas de las direcciones IP que usa el servicio o dispositivo de protección de terceros para enviar correo a Microsoft 365.

          Cuando termine, haga clic en **Siguiente**.

       2. En el cuadro de diálogo **Exchange reglas de flujo de correo**, decida si necesita una regla de flujo de correo Exchange Online (también conocida como regla de transporte) que omita el filtrado de correo no deseado para los mensajes entrantes desde el servicio o dispositivo de protección de terceros.

          Es probable que ya tenga una regla de flujo de correo SCL=-1 en Exchange Online que permita que todo el correo entrante del servicio de protección omita (la mayoría) Microsoft 365 filtrado. Muchos servicios de protección fomentan este método de regla de flujo de correo de nivel de confianza de correo no deseado (SCL) para Microsoft 365 clientes que usan sus servicios.

          Como se explicó en el paso anterior, el filtrado mejorado para conectores se configura automáticamente en el conector que especifique como origen de correo del servicio de protección.

          Activar el filtrado mejorado para conectores sin una regla SCL=-1 para el correo entrante desde el servicio de protección mejorará enormemente las capacidades de detección de las características de protección de EOP, como la [inteligencia de suplantación](anti-spoofing-protection.md) de identidad, y podría afectar a la entrega de esos mensajes recién detectados (por ejemplo, pasar a la carpeta Correo no deseado o poner en cuarentena). Este impacto se limita a las directivas de EOP; como se explicó anteriormente, las directivas de Defender para Office 365 se crean en modo de auditoría.

          Para crear una regla de flujo de correo SCL=-1 o para revisar las reglas existentes, haga clic en el botón **Ir a Exchange centro de administración** de la página. Para obtener más información, consulte [Uso de reglas de flujo de correo para establecer el nivel de confianza de correo no deseado (SCL) en los mensajes de Exchange Online](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

          Cuando haya terminado, haga clic en **Finalizar**.

     - **Solo estoy usando Microsoft Exchange Online**: los registros MX de su dominio apuntan a Microsoft 365. No queda nada que configurar, por lo que haga clic en **Finalizar**.

5. Aparece un cuadro de diálogo de progreso cuando se configura la evaluación. Una vez completada la configuración, haga clic en **Listo**.

## <a name="set-up-an-evaluation-in-blocking-mode"></a>Configuración de una evaluación en modo de bloqueo

1. Haga clic en **Iniciar evaluación**.

2. En el cuadro de diálogo **Activar protección** , seleccione **Sí, proteja mi organización mediante el bloqueo de amenazas** y, a continuación, haga clic en **Continuar**.

3. En el cuadro de diálogo **Seleccionar los usuarios que desea incluir** , configure los siguientes valores:

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

4. Aparece un cuadro de diálogo de progreso cuando se configura la evaluación. Una vez completada la instalación, haga clic en **Listo**.

## <a name="reporting-in-audit-mode"></a>Informes en modo de auditoría

- El [informe de estado de protección contra](view-email-security-reports.md#threat-protection-status-report) amenazas muestra las detecciones por Defender para Office 365 en las vistas siguientes:
  - [Visualización de datos por correo electrónico \> Malware y desglose de gráficos por tecnología de detección](view-email-security-reports.md#view-data-by-email--malware-and-chart-breakdown-by-detection-technology)
  - [Visualización de datos por correo electrónico \> y desglose de gráficos por tecnología de detección](view-email-security-reports.md#view-data-by-email--phish-and-chart-breakdown-by-detection-technology)

- En [el Explorador de amenazas](threat-explorer.md), los mensajes detectados por la evaluación de Defender para Office 365 muestran el siguiente banner en los detalles de la entrada:

  ![Banner de notificación en los detalles del mensaje que la evaluación de Defender para Office 365 detectó un mensaje de correo electrónico malintencionado.](../../media/evalv2-detection-banner.png)

<!--- This stuff is likely not applicable for V2 reporting --->

La **página de evaluación Microsoft Defender para Office 365** de <https://security.microsoft.com/atpEvaluation> consolida los informes de las directivas de la evaluación:

- Protección contra suplantación en directivas antiphishing
- Vínculos seguros
- Archivos adjuntos seguros

De forma predeterminada, los gráficos muestran datos de los últimos 30 días, pero puede filtrar el intervalo de fechas haciendo clic en ![el icono Calendario.](../../media/m365-cc-sc-add-internal-icon.png) **30 días** y seleccionando entre los siguientes valores adicionales que son inferiores a 30 días:

- 24 horas
- 7 días
- 14 días
- Intervalo de fechas personalizado

Puede hacer clic en el ![icono Descargar.](../../media/m365-cc-sc-download-icon.png) **Descargue** para descargar los datos del gráfico en un archivo .csv.

## <a name="required-permissions"></a>Permisos necesarios

Los permisos necesarios en **Azure AD** para configurar una evaluación de Defender para Microsoft 365 se describen en la lista siguiente:

- **Crear, modificar o eliminar una evaluación**: Administrador de seguridad o Administrador global.
- **Ver directivas e informes de evaluación**: Administrador de seguridad o Lector de seguridad.

Para obtener más información sobre los permisos de Azure AD en el portal de Microsoft 365 Defender, consulte [roles de Azure AD en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md#azure-ad-roles-in-the-microsoft-365-defender-portal).

## <a name="evaluation-policy-settings"></a>Configuración de la directiva de evaluación

La configuración de la Defender para Office 365 creada específicamente para la evaluación se describe en las tablas siguientes:

**Configuración de directivas de evaluación contra phishing**:

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
|Guid|Valor DE GUID|
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
|AntiPhishPolicyLevelDataList|Blanco|
|AntiSpoofEnforcementType|Alto|
|AuthenticationSafetyTipText|Blanco|
|AuthenticationSoftPassSafetyTipText|Blanco|
|EnableAuthenticationSafetyTip|False|
|EnableAuthenticationSoftPassSafetyTip|False|
|PolicyTag|Blanco|
|SimilarUsersSafetyTipsCustomText|Blanco|
|TreatSoftPassAsAuthenticated|True|
|UnusualCharactersSafetyTipsCustomText|Blanco|
|||
|ExcludedDomains|{}|
|ExcludedSenders|{}|
|TargetedDomainsToProtect|{}|
|TargetedUsersToProtect|{}|

**Caja fuerte configuración de la directiva de evaluación de datos adjuntos**:

|Configuración|Valor|
|---|---|
|Action|Permitir|
|ActionOnError|True|
|AdminDisplayName|Directiva de evaluación|
|ConfidenceLevelThreshold|80|
|Habilitación|True|
|EnableOrganizationBranding|False|
|Guid|Valor DE GUID|
|IsBuiltInProtection|False|
|IsDefault|False|
|Nombre|Directiva de evaluación|
|OperationMode|Delay|
|QuarantineTag|AdminOnlyAccessPolicy|
|RecommendedPolicyType|Evaluation|
|Redirect|False|
|RedirectAddress|{}|
|ScanTimeout|30|

**Caja fuerte Configuración de directivas de evaluación de vínculos**:

|Configuración|Valor|
|---|---|
|AdminDisplayName|Directiva de evaluación|
|AllowClickThrough|False|
|CustomNotificationText|Blanco|
|DeliverMessageAfterScan|True|
|DisableUrlRewrite|True|
|DoNotRewriteUrls|{}|
|EnableForInternalSenders|False|
|EnableOrganizationBranding|False|
|EnableSafeLinksForTeams|True|
|Guid|Valor DE GUID|
|IsBuiltInProtection|False|
|IsDefault|False|
|IsEnabled|True|
|LocalizedNotificationTextList|{}|
|Nombre|"EvaluationPolicy"|
|RecommendedPolicyType|Evaluation|
|ScanUrls|True|
|TrackClicks|True|
|||
|DoNotAllowClickThrough|Blanco|
|DoNotTrackUserClicks|False|
|EnableSafeLinksForEmail|True|
|EnableSafeLinksForOffice|True|
|ExcludedUrls|{}|
|WhiteListedUrls|Blanco|
