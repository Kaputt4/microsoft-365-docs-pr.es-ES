---
title: Configurar la inteligencia de suplantación
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre la inteligencia de suplantación de identidad en Exchange Online Protection (EOP), donde puede permitir o bloquear remitentes suplantados específicos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a65400d1b48abfc6ac0e4dd38a8245dd7b4f87b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289692"
---
# <a name="configure-spoof-intelligence-in-eop"></a>Configurar la inteligencia de suplantación de seguridad en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

En las organizaciones de Microsoft 365 con buzones en Exchange Online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, los mensajes de correo electrónico entrantes se protegen automáticamente contra la suplantación por parte de EOP a partir de octubre de 2018. EOP usa la inteligencia de suplantación de identidad como parte de la defensa general de su organización contra la suplantación de identidad. Para obtener más información, vea [Protección contra la suplantación en EOP.](anti-spoofing-protection.md)

Cuando un remitente suplanta una dirección de correo electrónico, parece que es un usuario de uno de los dominios de su organización o un usuario de un dominio externo que envía correo electrónico a su organización. Los atacantes que suplanten a los remitentes para enviar correo no deseado o correo de suplantación de identidad deben bloquearse. Sin embargo, existen escenarios en los que los remitentes legítimos están suplantando la identidad. Por ejemplo:

- Escenarios legítimos para suplantar dominios internos:

  - Los remitentes de terceros usan su dominio para enviar correo masivo a sus propios empleados para los sondeos de la empresa.
  - Una empresa externa genera y envía actualizaciones de productos o publicidad en tu nombre.
  - Un asistente debe enviar periódicamente correo electrónico a otra persona de la organización.
  - Una aplicación interna envía notificaciones por correo electrónico.

- Escenarios legítimos para suplantar dominios externos:

  - El remitente se encuentra en una lista de distribución de correo (también conocida como lista de discusión) y la lista de distribución retransmite el correo electrónico del remitente original a todos los participantes de la lista de distribución de correo.
  - Una compañía externa envía correo electrónico en nombre de otra compañía (por ejemplo, un informe automatizado o una compañía de software como servicio).

La inteligencia de suplantación de identidad y, específicamente, la directiva de inteligencia de suplantación de identidad predeterminada (y única), ayuda a garantizar que el correo electrónico suplantado enviado por remitentes legítimos no se detecta en filtros de correo no deseado de EOP o sistemas de correo electrónico externos, a la vez que protege a los usuarios de los ataques de correo no deseado o de suplantación de identidad.

Puede administrar la inteligencia de suplantación en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; EOP PowerShell independiente para organizaciones sin buzones de Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página **Configuración contra correo no deseado**, use <https://protection.office.com/antispam>. Para ir directamente a la **página contra la suplantación** de identidad, use <https://protection.office.com/antiphishing> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento para poder realizar los procedimientos de este artículo:
  - Para modificar la directiva de inteligencia de suplantación o habilitar o deshabilitar  la inteligencia de suplantación de seguridad, debe ser miembro de los grupos de roles Administración de la organización o Administrador **de** seguridad.
  - Para obtener acceso de solo lectura a la directiva de inteligencia de suplantación, debe ser miembro de los grupos de roles Lector **global** o **Lector de** seguridad.

  Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

  **Notas**:

  - Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Para obtener la configuración recomendada para la inteligencia de suplantación de identidad, vea la configuración predeterminada de la directiva [contra suplantación de identidad de EOP.](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>Usar el Centro de & cumplimiento para administrar remitentes suplantados

> [!NOTE]
> Si tiene una suscripción a Microsoft 365 Enterprise E5 o ha adquirido por separado un complemento de Microsoft Defender para Office 365, también puede administrar los remitentes que están suplantando su dominio a través de la información de inteligencia de suplantación de [identidad.](walkthrough-spoof-intelligence-insight.md)

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.

2. En la página **Configuración contra correo no** deseado, haga clic en el icono Expandir para expandir la directiva de inteligencia de ![ ](../../media/scc-expand-icon.png) **suplantación de seguridad.**

   ![Seleccionar la directiva de inteligencia de suplantación de seguridad](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. Realice una de las siguientes selecciones:

   - **Revisar nuevos remitentes**
   - **Mostrarme los remitentes que ya he revisado**

4. En el menú Decidir si estos remitentes pueden **suplantar** la identidad de los usuarios en el control desplegable que aparece, seleccione una de las siguientes pestañas:

   - **Sus dominios:** remitentes que suplanta a los usuarios en sus dominios internos.
   - **Dominios externos:** remitentes que suplanta a los usuarios en dominios externos.

5. Haga clic en el icono Expandir de la columna ¿Se ![ ](../../media/scc-expand-icon.png) permite **suplantación de identidad?** Elija **Sí** para permitir al remitente suplantado o **elija No** para marcar el mensaje como suplantado. La acción se controla mediante la directiva contra suplantación de identidad predeterminada o las directivas personalizadas contra suplantación de identidad (el valor predeterminado es Mover mensaje a la carpeta **correo no deseado).** Para obtener más información, vea [Configuración de suplantación de identidad en directivas contra suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings).

   ![Captura de pantalla que muestra el desplegable de remitentes suplantados y si el remitente puede suplantar la identidad](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   Las columnas y los valores que ve se explican en la siguiente lista:

   - **Usuario suplantado:** la cuenta de usuario suplantada. Este es el remitente del mensaje en la dirección De (también conocida como dirección) que `5322.From` se muestra en los clientes de correo electrónico. SPF no comprueba la validez de esta dirección.

     - En la **pestaña Dominios,** el valor contiene una sola dirección de correo electrónico, o si el servidor de correo electrónico de origen está suplantando varias cuentas de usuario, contiene **más de una.**

     - En la **pestaña Dominios externos,** el valor contiene el dominio del usuario suplantado, no la dirección de correo electrónico completa.

   - **Infraestructura de** envío: dominio encontrado en una búsqueda dns inversa (registro PTR) de la dirección IP del servidor de correo electrónico de origen. Si la dirección IP de origen no tiene ningún registro PTR, la infraestructura de envío se identifica como \<source IP\> /24 (por ejemplo, 192.168.100.100/24).

     Para obtener más información acerca de los orígenes de mensajes y los remitentes de mensajes, consulte Información general sobre los estándares de [mensajes de correo electrónico.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

   - **# de mensajes:** el número de mensajes de la infraestructura de envío a la organización que contienen el remitente o remitentes suplantados especificados en los últimos 30 días.

   - **# de quejas de usuario:** quejas presentada por los usuarios contra este remitente en los últimos 30 días. Las quejas suelen estar en forma de envíos de correo no deseado a Microsoft.

   - **Resultado de la** autenticación: uno de los siguientes valores:
      - **Pasado:** el remitente superó las comprobaciones de autenticación de correo electrónico del remitente (SPF o DKIM).
      - **Error:** el remitente no pudo comprobar la autenticación del remitente de EOP.
      - **Desconocido:** no se conoce el resultado de estas comprobaciones.

   - **Decisión establecida por:** muestra quién determinó si la infraestructura de envío tiene permiso para suplantación de nombre del usuario:
       - **Directiva de inteligencia de suplantación** de seguridad (automática)
       - **Administrador** (manual)

   - **Última vez** que se vio: la última fecha en la que se recibió un mensaje de la infraestructura de envío que contiene el usuario suplantado.

   - **¿Se permite la suplantación?**: Los valores que ve aquí son:
     - **Sí:** los mensajes de la combinación de usuario suplantado y la infraestructura de envío se permiten y no se tratan como correo electrónico suplantado.
     - **No:** los mensajes de la combinación de usuario suplantado y la infraestructura de envío se marcan como suplantados. La acción se controla mediante la directiva contra suplantación de identidad predeterminada o las directivas personalizadas contra suplantación de identidad (el valor predeterminado es Mover mensaje a la carpeta **correo no deseado).** Vea la sección siguiente para obtener más información.

     - **Algunos usuarios** **(solo la** pestaña Dominios): una infraestructura de envío está suplantando a varios usuarios, donde algunos usuarios suplantados están permitidos y otros no. Use la **pestaña Detallado** para ver las direcciones específicas.

6. En la parte inferior de la página, haga clic en **Guardar**.

## <a name="use-powershell-to-manage-spoofed-senders"></a>Usar PowerShell para administrar remitentes suplantados

Para ver remitentes permitidos y bloqueados en la inteligencia de suplantación de identidad, use la siguiente sintaxis:

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

En este ejemplo se devuelve información detallada sobre todos los remitentes que tienen permiso para suplantación de identidad de usuarios en sus dominios.

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).

Para configurar remitentes permitidos y bloqueados en inteligencia de suplantación de identidad, siga estos pasos:

1. Capture la lista actual de remitentes suplantados detectados escribiendo el resultado del cmdlet **Get-PhishFilterPolicy** en un archivo CSV:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Edite el archivo CSV para agregar o modificar los valores **SpoofedUser** (dirección de correo electrónico) y **AllowedToSpoof** (Sí o No). Guarde el archivo, lea el archivo y almacene el contenido como una variable denominada `$UpdateSpoofedSenders` :

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Use la `$UpdateSpoofedSenders` variable para configurar la directiva de inteligencia de suplantación de nombres:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>Usar el Centro de seguridad & cumplimiento para configurar la inteligencia de suplantación de seguridad

Las opciones de configuración para la inteligencia de suplantación de identidad se describen en la configuración de suplantación de identidad [en las directivas contra suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings).

Puede configurar las opciones de inteligencia de suplantación de identidad en la directiva contra suplantación de identidad predeterminada y también en las directivas personalizadas. Para obtener instrucciones basadas en su suscripción, consulte uno de los siguientes temas:

- [Configurar directivas contra la suplantación de identidad en EOP.](configure-anti-phishing-policies-eop.md)

- [Configurar directivas contra la suplantación de identidad en Microsoft Defender para Office 365.](configure-atp-anti-phishing-policies.md)

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha configurado la inteligencia de suplantación de identidad con remitentes que tienen permiso y no pueden suplantación de identidad y que ha configurado la configuración de inteligencia de suplantación de identidad, siga uno de estos pasos:

- In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** select Show me \> **senders I already reviewed** \> select the Your **Domains** or **External Domains** tab, and verify the Allowed **to spoof?** value for the sender.

- En PowerShell, ejecute los siguientes comandos para ver los remitentes que tienen permiso y no pueden suplantación de identidad:

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

- En el Centro de seguridad &  cumplimiento, vaya a Directiva de administración de amenazas contra suplantación de identidad o protección contra suplantación de identidad de ATP y siga uno de \>  \>  estos pasos:   

  - Seleccione una directiva de la lista. En el menú desplegable que aparece, compruebe los valores de la **sección Suplantación de** identidad.
  - Haga clic **en Directiva predeterminada.** En el menú desplegable que aparece, compruebe los valores de la **sección Suplantación de** identidad.

- En Exchange Online PowerShell, reemplace por Office365 AntiPhish Default o el nombre de una directiva personalizada y ejecute el siguiente comando \<Name\> para comprobar la configuración:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>Otras formas de administrar la suplantación de identidad y la suplantación de identidad

Sé cuidadoso sobre la protección contra la suplantación de identidad y la suplantación de identidad. Estas son las formas relacionadas de comprobar si los remitentes suplantan su dominio y ayudar a evitar que dañen la organización:

- Compruebe el **informe de suplantación de correo.** Puede usar este informe a menudo para ver y ayudar a administrar remitentes suplantados. Para obtener información, vea [el informe de detecciones de suplantación de seguridad.](view-email-security-reports.md#spoof-detections-report)

- Revise la configuración del marco de directivas de remitente (SPF). Para obtener una introducción rápida a SPF y configurarlo rápidamente, consulte [Configuración de SPF en Microsoft 365 para evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Para comprender en detalle cómo Office 365 usa SPF, o para la solución de problemas o las implementaciones no estándar (por ejemplo, implementaciones híbridas), comience con [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).

- Revise la configuración de DomainKeys Identified Mail (DKIM). Debe usar DKIM además de SPF y DMARC para ayudar a evitar que los atacantes envíen mensajes que parezcan procedentes de su dominio. DKIM le permite agregar una firma digital a los mensajes de correo electrónico en el encabezado del mensaje. Para obtener información, vea Usar DKIM para validar el correo electrónico saliente [enviado desde su dominio personalizado en Office 365.](use-dkim-to-validate-outbound-email.md)

- Revise la configuración de autenticación, informes y conformidad de mensajes (DMARC) basada en dominio. Implementar DMARC con SPF y DKIM ofrece protección adicional contra el correo electrónico de suplantación de identidad. DMARC permite a los sistemas que reciben los correos determinar qué hacer con los mensajes enviados desde su dominio que no superan las comprobaciones SPF o DKIM. Para obtener información, [vea Usar DMARC para validar el correo electrónico en Office 365.](use-dmarc-to-validate-email.md)
