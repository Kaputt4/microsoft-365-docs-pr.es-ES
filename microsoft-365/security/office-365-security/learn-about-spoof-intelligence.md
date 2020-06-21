---
title: Configurar la inteligencia de suplantación
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre inteligencia de suplantación de identidad en Exchange Online Protection (EOP), donde puede permitir o bloquear remitentes simulados específicos.
ms.openlocfilehash: e1c282076d054c338a02a50412ec376406f5ce98
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726737"
---
# <a name="configure-spoof-intelligence-in-eop"></a>Configurar inteligencia de identidades en EOP

En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, los mensajes de correo electrónico entrantes se protegen automáticamente contra la suplantación de EOP a través de EOP a partir de 2018 de octubre. EOP usa inteligencia simulada como parte de la defensa general de la organización contra el phishing. Para obtener más información, vea [protección contra la suplantación de identidad en EOP](anti-spoofing-protection.md).

Cuando un remitente suplanta una dirección de correo electrónico, parece ser un usuario en uno de los dominios de la organización o un usuario de un dominio externo que envía correo electrónico a su organización. Es necesario bloquear a los intrusos que suplantan a los remitentes para enviar correo no deseado o de suplantación de identidad. Pero hay escenarios en los que los remitentes legítimos son imitación. Por ejemplo:

- Escenarios legítimos para la suplantación de dominios internos:

  - Los remitentes de terceros usan el dominio para enviar correo masivo a sus propios empleados para los sondeos de la compañía.

  - Una compañía externa genera y envía actualizaciones de productos o publicidad en su nombre.

  - Un asistente necesita regularmente enviar correo electrónico a otra persona de la organización.

  - Una aplicación interna envía notificaciones de correo electrónico.

- Escenarios legítimos para imitar dominios externos:

  - El remitente está en una lista de correo (también denominada lista de discusión) y la lista de distribución retransmite el correo electrónico del remitente original a todos los participantes de la lista de distribución de correo.

  - Una compañía externa envía un correo electrónico en nombre de otra empresa (por ejemplo, un informe automatizado o una compañía de software como servicio).

Inteligencia de identidad suplantada, y concretamente la Directiva de inteligencia de identidad falsa predeterminada (y únicamente), ayuda a garantizar que el correo electrónico falso enviado por remitentes legítimos no se quede atrapado en los filtros de correo no deseado de EOP ni en los sistemas de correo electrónico externos, a la vez que protege a los usuarios de los ataques de phishing o spam.

Puede administrar inteligencia de identidad en el centro de seguridad & cumplimiento o en PowerShell (Exchange Online PowerShell para Microsoft 365 organizaciones con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones de correo de Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página **Configuración contra correo no deseado**, use <https://protection.office.com/antispam>. Para ir directamente a la página de **contra la suplantación de identidad (phishing** ), use <https://protection.office.com/antiphishing> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Debe tener permisos asignados para poder realizar los procedimientos de este tema:

  - Para modificar la Directiva de inteligencia de suplantación o habilitar o deshabilitar la inteligencia de identidad, debe pertenecer a uno de los siguientes grupos de roles:

    - **Administración** de la organización o **Administrador de seguridad** en el [centro de seguridad & cumplimiento](permissions-in-the-security-and-compliance-center.md).
    - Administración de la administración de la **organización** o administración de la **higiene** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Para obtener acceso de solo lectura a la Directiva de inteligencia empresarial de suplantación de identidad, debe ser miembro de uno de los siguientes grupos de roles:

    - **Lector de seguridad** en el [centro de seguridad & cumplimiento](permissions-in-the-security-and-compliance-center.md).
    - **View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Para conocer la configuración recomendada para inteligencia de identidad, consulte [configuración predeterminada de la Directiva de protección contra suplantación de EOP](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>Usar el centro de seguridad & cumplimiento para administrar los remitentes suplantados

> [!NOTE]
> Si tiene una suscripción de Microsoft 365 Enterprise E5 o ha comprado por separado un complemento de protección contra amenazas avanzada de Office 365 (ATP de Office 365), también puede administrar a los remitentes que están suplantando su dominio mediante el [conocimiento de inteligencia de suplantación de identidad](walkthrough-spoof-intelligence-insight.md).

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.

2. En la página **configuración contra correo no deseado** , haga clic en ![ expandir icono ](../../media/scc-expand-icon.png) para expandir la **Directiva de inteligencia empresarial de suplantación**.

   ![Seleccionar la Directiva de inteligencia de suplantación](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. Realice una de las siguientes selecciones:

   - **Revisión de los nuevos remitentes**
   - **Mostrar los remitentes que ya he revisado**

4. En el control flotante **decidir si estos remitentes pueden suplantar a los usuarios** que aparecen, seleccione una de las siguientes pestañas:

   - **Sus dominios**: los remitentes suplantan a los usuarios de los dominios internos.
   - **Dominios externos**: remitentes de suplantación de usuarios en dominios externos.

5. Haga clic en ![ expandir icono ](../../media/scc-expand-icon.png) en la columna **¿se permite la suplantación?** . Elija **sí** para permitir el remitente suplantado o elija **no** para marcar el mensaje como falsificado. La acción se controla mediante la Directiva antiphishing predeterminada o las directivas antiphishing personalizadas de ATP (el valor predeterminado es **mover mensaje a la carpeta de correo no deseado**). Para obtener más información, consulte [configuración de la suplantación de identidades en directivas antiphishing](set-up-anti-phishing-policies.md#spoof-settings).

   ![Captura de pantalla que muestra el control flotante de remitentes suplantados y si se permite que el remitente suplante](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   En la lista siguiente se explican las columnas y los valores que se ven:

   - **Usuario suplantado**: la cuenta de usuario que se va a imitar. Este es el remitente del mensaje en la dirección de (también denominada `5322.From` dirección) que se muestra en los clientes de correo electrónico. SPF no comprueba la validez de esta dirección.

     - En la ficha **sus dominios** , el valor contiene una sola dirección de correo electrónico o, si el servidor de correo electrónico de origen imita varias cuentas de usuario, contiene **más de una**.

     - En la ficha **dominios externos** , el valor contiene el dominio del usuario falso, no la dirección de correo electrónico completa.

   - **Infraestructura de envío**: el dominio que se encuentra en una búsqueda DNS inversa (registro PTR) de la dirección IP del servidor de correo electrónico de origen o en la dirección IP si el origen no tiene registro PTR.

     Para obtener más información acerca de los orígenes de mensajes y los remitentes de mensajes, vea [información general sobre los estándares de mensajes de correo electrónico](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).

   - **n.º de mensajes**: el número de mensajes de la infraestructura de envío a su organización que contienen los remitentes suplantados que se han especificado en los últimos 30 días.

   - **número de quejas del usuario**: quejas archivadas por los usuarios con este remitente en los últimos 30 días. Las quejas suelen estar en forma de envíos de correo no deseado a Microsoft.

   - **Resultado de autenticación**: uno de los siguientes valores:

      - **Passed**: el remitente ha superado las comprobaciones de autenticación de correo electrónico del remitente (SPF o DKIM).
      - **Error**: el remitente no pudo realizar comprobaciones de autenticación de remitente de EOP.
      - **Desconocido**: no se conoce el resultado de estas comprobaciones.

   - **Decisión definida por**: muestra quién ha determinado si la infraestructura de envío tiene permiso para suplantar al usuario:

       - **Directiva de inteligencia de identidad** (automática)
       - **Administrador** (manual)

   - **Último visto**: la última fecha en la que se recibió un mensaje de la infraestructura de envío que contiene al usuario suplantado.

   - ¿Se **permite la suplantación?**: los valores que aparecen aquí son los siguientes:

     - **Sí**: los mensajes de la combinación de usuario falsificado y la infraestructura de envío están permitidos y no se tratan como correo electrónico falsificado.

     - **No**: los mensajes de la combinación de usuario falsificado y infraestructura de envío se marcan como falseados. La acción se controla mediante la Directiva antiphishing predeterminada o las directivas antiphishing personalizadas de ATP (el valor predeterminado es **mover mensaje a la carpeta de correo no deseado**). Vea la sección siguiente para obtener más información.

     - **Algunos usuarios** (**la ficha dominios** solamente): una infraestructura de envío imita a varios usuarios, donde se permiten algunos usuarios suplantados y otros no. Use la pestaña **detalles** para ver las direcciones específicas.

6. En la parte inferior de la página, haga clic en **Guardar**.

## <a name="use-powershell-to-manage-spoofed-senders"></a>Usar PowerShell para administrar los remitentes suplantados

Para ver los remitentes permitidos y bloqueados en inteligencia de suplantación de identidad, use la siguiente sintaxis:

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

En este ejemplo se devuelve información detallada sobre todos los remitentes a los que se les permite suplantar usuarios en los dominios.

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).

Para configurar los remitentes permitidos y bloqueados en inteligencia de identidad, siga estos pasos:

1. Para capturar la lista actual de los remitentes suplantados detectados, escriba el resultado del cmdlet **Get-PhishFilterPolicy** en un archivo CSV:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Edite el archivo CSV para agregar o modificar los valores de **SpoofedUser** (dirección de correo electrónico) y **AllowedToSpoof** (sí o no). Guarde el archivo, lea el archivo y almacene el contenido como una variable llamada `$UpdateSpoofedSenders` :

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Use la `$UpdateSpoofedSenders` variable para configurar la Directiva de inteligencia de suplantación de identidad:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>Usar el centro de seguridad & cumplimiento para configurar la inteligencia de identidad

Las opciones de configuración para inteligencia de suplantación se describen en configuración de suplantación [de identidades en directivas antiphishing](set-up-anti-phishing-policies.md#spoof-settings).

Puede configurar las opciones de inteligencia contra la suplantación de identidad en la Directiva de antiphishing predeterminada y también en las directivas personalizadas. Para obtener instrucciones basadas en su suscripción, consulte uno de los siguientes temas:

- [Configure las directivas contra la suplantación de identidad en EOP](configure-anti-phishing-policies-eop.md).

- [Configure las directivas antiphishing de ATP en Microsoft 365](configure-atp-anti-phishing-policies.md).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha configurado inteligencia de suplantación con remitentes a los que se permite y no se permite la suplantación, y que ha configurado la configuración de inteligencia de suplantación de identidad, siga uno de estos pasos:

- En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **anti-spam** \> expanda la **Directiva inteligencia empresarial** \> seleccionar **Mostrar los remitentes que ya he revisado** \> Seleccione la pestaña **dominios** o dominios **externos** y compruebe el valor **se permite la suplantación de identidad** para el remitente.

- En PowerShell, ejecute los siguientes comandos para ver los remitentes a los que se les permite la suplantación:

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- En PowerShell, ejecute el siguiente comando para exportar la lista de todos los remitentes suplantados a un archivo CSV:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **anti-** phishing o **ATP anti-phishing**y realice uno de los siguientes pasos:  

  - Seleccione una directiva de la lista. En el control flotante que aparece, compruebe los valores de la sección **suplantación de identidad** .
  - Haga clic en **directiva predeterminada**. En el control flotante que aparece, compruebe los valores de la sección **suplantación de identidad** .

- En Exchange Online PowerShell, reemplace \<Name\> con la opción predeterminada de Office365 ANTIPHISH o el nombre de una directiva personalizada, y ejecute el siguiente comando para comprobar la configuración:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableAntiSpoofEnforcement,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>Otras formas de administrar la suplantación de identidad (phishing)

Sea Diligent sobre la suplantación de identidad y la protección contra phishing. A continuación, se incluyen formas relacionadas de comprobar si los remitentes suplantan el dominio y ayudar a evitar que dañen la organización:

- Compruebe el **Informe de correo falsificado**. Puede usar este informe con frecuencia para ver y ayudar a administrar los remitentes suplantados. Para obtener información, consulte [Informe de detecciones de suplantación de identidad](view-email-security-reports.md#spoof-detections-report).

- Revise la configuración del marco de directivas de remitente (SPF). Para obtener una introducción rápida a SPF y configurarlo rápidamente, consulte [Configuración de SPF en Microsoft 365 para evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Para comprender en detalle cómo Office 365 usa SPF, o para la solución de problemas o las implementaciones no estándar (por ejemplo, implementaciones híbridas), comience con [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).

- Revise la configuración de DomainKeys Identified Mail (DKIM). Debe usar DKIM además de SPF y DMARC para ayudar a evitar que los atacantes envíen mensajes que parecen provenir de su dominio. DKIM le permite agregar una firma digital a los mensajes de correo electrónico en el encabezado del mensaje. Para obtener más información, vea [usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md).

- Revise la configuración de autenticación de mensajes basada en el dominio, informes y conformidad (DMARC). Implementar DMARC con SPF y DKIM ofrece protección adicional contra el correo electrónico de suplantación de identidad. DMARC permite a los sistemas que reciben los correos determinar qué hacer con los mensajes enviados desde su dominio que no superan las comprobaciones SPF o DKIM. Para obtener más información, vea [usar DMARC para validar el correo electrónico en Office 365](use-dmarc-to-validate-email.md).
