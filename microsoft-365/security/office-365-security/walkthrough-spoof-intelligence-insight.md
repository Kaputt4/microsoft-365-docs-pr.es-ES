---
title: Administrar remitentes suplantados mediante la directiva de inteligencia suplantada y la información de inteligencia suplantada
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a usar la directiva de inteligencia suplantada y la información de inteligencia suplantada para permitir o bloquear remitentes suplantados detectados.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 821488f79186e1b5c306b587764377989346eea5
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52530891"
---
# <a name="manage-spoofed-senders-using-the-spoof-intelligence-policy-and-spoof-intelligence-insight-in-eop"></a>Administrar remitentes suplantados con la directiva de inteligencia suplantada y la información de inteligencia suplantada en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> En este artículo se describe la experiencia de administración de remitentes suplantada anterior que se está reemplazando. Para obtener más información sobre la nueva experiencia, vea [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md)

En Microsoft 365 organizaciones con buzones en organizaciones de Exchange Online o independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online, los mensajes de correo electrónico entrantes se protegen automáticamente contra la suplantación de correo electrónico por parte de EOP a partir de octubre de 2018. EOP usa **la inteligencia de** suplantación de identidad como parte de la defensa general de su organización contra el phishing. Para obtener más información, vea Protección contra [la suplantación en EOP](anti-spoofing-protection.md).

La directiva de inteligencia de suplantación de identidad predeterminada (y **única)** ayuda a garantizar que el correo electrónico suplantado enviado por remitentes legítimos no se desentraña en los filtros de correo no deseado de EOP mientras protege a los usuarios de ataques de correo no deseado o suplantación de identidad. También puede usar  la información de inteligencia de suplantación de identidad para determinar rápidamente qué remitentes externos le envían legítimamente correo electrónico no autenticado (mensajes de dominios que no pasan comprobaciones de SPF, DKIM o DMARC).

Puede administrar la inteligencia de suplantación en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones de correo Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.
  - Para ir directamente a la página **Configuración contra correo no** deseado de la directiva de inteligencia suplantación de dominio, use <https://protection.office.com/antispam> .
  - Para ir directamente a la página **Panel de seguridad** para la información de inteligencia suplantación, use <https://protection.office.com/searchandinvestigation/dashboard> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Debe tener permisos asignados en **Exchange Online** antes de poder realizar los procedimientos de este artículo:
  - Para modificar la directiva de inteligencia suplantada o habilitar o deshabilitar la  inteligencia suplantada, debe ser miembro de los grupos de roles Administración de la organización o Administrador **de** seguridad.
  - Para obtener acceso de solo lectura a la directiva de inteligencia suplantada, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.

  Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Notas**:

  - Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios _y_ los permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Las opciones de inteligencia suplantación de identidad se describen en [Configuración de suplantación de identidad en directivas contra suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings).

- Puede habilitar, deshabilitar y configurar la configuración de la suplantación de identidad en las directivas contra suplantación de identidad. Para obtener instrucciones basadas en su suscripción, consulte uno de los siguientes temas:

  - [Configurar directivas contra suplantación de](configure-anti-phishing-policies-eop.md)identidad en EOP .
  - [Configurar directivas contra suplantación de](configure-atp-anti-phishing-policies.md)identidad en Microsoft Defender para Office 365 .

- Para obtener la configuración recomendada para la inteligencia de suplantación de identidad, consulte Configuración predeterminada de la directiva [contra suplantación de](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings)identidad de EOP.

## <a name="manage-spoofed-senders"></a>Administrar remitentes suplantados

Hay dos maneras de permitir y bloquear remitentes suplantados:

- [Usar la directiva de inteligencia suplantación](#manage-spoofed-senders-in-the-spoof-intelligence-policy)
- [Usar la información de inteligencia suplantación](#manage-spoofed-senders-in-the-spoof-intelligence-insight)

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-policy"></a>Administrar remitentes suplantados en la directiva de inteligencia suplantación de identidad

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.

2. En la **página Configuración contra correo** no deseado, haga clic en Expandir icono para expandir La directiva de inteligencia de ![ ](../../media/scc-expand-icon.png) **suplantación.**

   ![Seleccionar la directiva de inteligencia suplantación](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. Realice una de las siguientes selecciones:

   - **Revisar nuevos remitentes**
   - **Mostrarme remitentes que ya revisé**

4. En decidir si estos remitentes pueden **suplantar** el control de los usuarios que aparece, seleccione una de las siguientes pestañas:

   - **Dominios:** remitentes que suplanta a los usuarios de los dominios internos.
   - **Dominios externos:** remitentes que suplanta a los usuarios en dominios externos.

5. Haga clic en Expandir icono en la columna ![ ](../../media/scc-expand-icon.png) **¿Permitido suplantación de identidad?** Elija **Sí** para permitir al remitente suplantado o **elija No** para marcar el mensaje como suplantado. La acción está controlada por la directiva anti phishing predeterminada o las directivas personalizadas contra suplantación de identidad (el valor predeterminado es Mover mensaje a la carpeta **correo no deseado**). Para obtener más información, vea [Configuración de suplantación de identidad en directivas contra suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings).

   ![Captura de pantalla que muestra el flyout de remitentes suplantados y si el remitente puede suplantar](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   Las columnas y valores que se muestran se explican en la siguiente lista:

   - **Usuario suplantado:** la cuenta de usuario que se está suplantado. Este es el remitente del mensaje en la dirección De (también conocida como la dirección) que `5322.From` se muestra en los clientes de correo electrónico. SPF no comprueba la validez de esta dirección.
     - En la **pestaña Dominios,** el valor contiene una sola dirección de correo electrónico, o si el servidor de correo electrónico de origen está suplantando varias cuentas de usuario, contiene **más de una**.
     - En la **pestaña Dominios externos,** el valor contiene el dominio del usuario suplantado, no la dirección de correo electrónico completa.

   - **Infraestructura de** envío: dominio encontrado en una búsqueda DNS inversa (registro PTR) de la dirección IP del servidor de correo electrónico de origen. Si la dirección IP de origen no tiene ningún registro PTR, la infraestructura de envío se identifica como \<source IP\> /24 (por ejemplo, 192.168.100.100/24).

     Para obtener más información acerca de los orígenes de mensajes y los remitentes de mensajes, vea [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).

   - **# de mensajes:** número de mensajes de la infraestructura de envío a la organización que contienen el remitente o remitentes suplantados especificados en los últimos 30 días.

   - **# de quejas de usuario:** quejas que los usuarios han presentado contra este remitente en los últimos 30 días. Las quejas suelen estar en forma de envíos de correo no deseado a Microsoft.

   - **Resultado de autenticación:** uno de los siguientes valores:
      - **Pasado:** el remitente pasó las comprobaciones de autenticación de correo electrónico del remitente (SPF o DKIM).
      - **Error:** el remitente ha fallado las comprobaciones de autenticación del remitente EOP.
      - **Desconocido:** el resultado de estas comprobaciones no se conoce.

   - **Decisión establecida por:** muestra quién determinó si la infraestructura de envío puede suplantación de suplantación al usuario:
       - **Directiva de inteligencia suplantación** (automática)
       - **Administrador** (manual)

   - **Última vista:** la última fecha en la que se recibió un mensaje de la infraestructura de envío que contiene el usuario suplantado.

   - **¿Se permite suplantación?**: Los valores que se ven aquí son:
     - **Sí:** los mensajes de la combinación de usuario suplantado y la infraestructura de envío se permiten y no se tratan como correo electrónico suplantado.
     - **No:** los mensajes de la combinación de usuario suplantado y la infraestructura de envío se marcan como suplantados. La acción está controlada por la directiva anti phishing predeterminada o las directivas personalizadas contra suplantación de identidad (el valor predeterminado es Mover mensaje a la carpeta **correo no deseado**). Vea la siguiente sección para obtener más información.

     - **Algunos usuarios** **(solo pestaña** Dominios): una infraestructura de envío está suplantando a varios usuarios, donde algunos usuarios suplantados están permitidos y otros no. Use la **pestaña Detallado** para ver las direcciones específicas.

6. En la parte inferior de la página, haga clic en **Guardar**.

#### <a name="use-powershell-to-manage-spoofed-senders"></a>Usar PowerShell para administrar remitentes suplantados

Para ver remitentes permitidos y bloqueados en la inteligencia de suplantación de identidad, use la siguiente sintaxis:

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

En este ejemplo se devuelve información detallada sobre todos los remitentes que tienen permiso para suplantación de identidad de usuarios en los dominios.

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).

Para configurar remitentes permitidos y bloqueados en la inteligencia de suplantación de identidad, siga estos pasos:

1. Capture la lista actual de remitentes suplantados detectados escribiendo el resultado del cmdlet **Get-PhishFilterPolicy** en un archivo CSV ejecutando el siguiente comando:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Edite el archivo CSV para agregar o modificar los siguientes valores:
   - **Remitente** (dominio en el registro PTR del servidor de origen o dirección IP/24)
   - **SpoofedUser:** uno de los siguientes valores:
     - Dirección de correo electrónico del usuario interno.
     - Dominio de correo electrónico del usuario externo.
     - Un valor en blanco que indica que desea bloquear o permitir todos los mensajes suplantados del **remitente** especificado, independientemente de la dirección de correo electrónico suplantada.
   - **AllowedToSpoof** (Sí o No)
   - **SpoofType** (interno o externo)

   Guarde el archivo, lea el archivo y almacene el contenido como una variable denominada `$UpdateSpoofedSenders` ejecutando el siguiente comando:

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Use la variable para configurar la directiva de inteligencia de `$UpdateSpoofedSenders` suplantación ejecutando el siguiente comando:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-insight"></a>Administrar remitentes suplantados en la información de inteligencia suplantada

1. En el Centro de & cumplimiento, vaya al Panel **de administración de** \> **amenazas.**

2. En la **fila Insights,** busque uno de los siguientes elementos:

   - **Probable suplantación** de dominio en los últimos siete días: esta información indica que la inteligencia suplantada está habilitada (está habilitada de forma predeterminada).
   - **Habilitar protección contra** suplantación: esta información indica que la inteligencia de suplantación está deshabilitada y hacer clic en la información le permite habilitar la inteligencia de suplantación.

3. La información del panel muestra información como esta:

   ![Captura de pantalla de información de inteligencia suplantación](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Esta información tiene dos modos:

   - **Modo de información:** si la suplantación de inteligencia está habilitada, la información muestra cuántos mensajes se han afectado por nuestras capacidades de inteligencia suplantada en los últimos siete días.
   - **Modo de** suplantación: si la inteligencia suplantada está  deshabilitada, la información muestra cuántos mensajes se habrían visto afectados por nuestras capacidades de inteligencia suplantada en los últimos siete días.

   En cualquier caso, los dominios suplantados que se muestran en la información se separan en dos categorías: **dominios** sospechosos y **dominios no sospechosos.**

   - **Dominios sospechosos**:
     - Suplantación de confianza **alta:** en función de los patrones de envío históricos y la puntuación de reputación de los dominios, estamos muy seguros de que los dominios están suplantando la suplantación y es más probable que los mensajes de estos dominios sean malintencionados.
     - **Suplantación** de confianza moderada: en función de los patrones de envío históricos y la puntuación de reputación de los dominios, estamos moderadamente seguros de que los dominios están suplantando y que los mensajes enviados desde estos dominios son legítimos. Los falsos positivos son más probables en esta categoría que la suplantación de confianza alta.
   - **Dominios no sospechosos:** el dominio no pudo comprobar la autenticación explícita de correo [electrónico SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)y [DMARC](use-dmarc-to-validate-email.md)). Sin embargo, el dominio pasó nuestras comprobaciones implícitas de autenticación de correo electrónico ([autenticación compuesta](email-validation-and-authentication.md#composite-authentication)). Como resultado, no se ha realizado ninguna acción contra la suplantación en el mensaje.

#### <a name="view-detailed-information-about-suspicious-and-nonsuspicious-domains"></a>Ver información detallada sobre dominios sospechosos y no sospechosos

1. En la información de inteligencia suplantada, haga clic en **Dominios** sospechosos o Dominios no sospechosos para ir a la **página Spoof intelligence insight.**  La **página Spoof Intelligence insight** contiene la siguiente información:

   - **Dominio suplantado:** dominio del usuario suplantado que se muestra en el **cuadro** De de los clientes de correo electrónico. Esta dirección también se conoce como `5322.From` la dirección.
   - **Infraestructura:** también conocida como la _infraestructura de envío_. El dominio encontrado en una búsqueda DNS inversa (registro PTR) de la dirección IP del servidor de correo electrónico de origen. Si la dirección IP de origen no tiene ningún registro PTR, la infraestructura de envío se identifica como \<source IP\> /24 (por ejemplo, 192.168.100.100/24).
   - **Recuento de** mensajes: el número de mensajes de la infraestructura de envío a la organización que contienen el dominio suplantado especificado en los últimos 7 días.
   - **Vista por última** vez: la última fecha en la que se recibió un mensaje de la infraestructura de envío que contiene el dominio suplantado.
   - **Tipo de suplantación:** este valor es **Externo**.
   - **¿Se permite suplantación?**: Los valores que se ven aquí son:
     - **Sí:** los mensajes de la combinación del dominio del usuario suplantado y la infraestructura de envío se permiten y no se tratan como correo electrónico suplantado.
     - **No:** los mensajes de la combinación del dominio del usuario suplantado y la infraestructura de envío se marcan como suplantados. La acción está controlada por la directiva anti phishing predeterminada o las directivas personalizadas contra suplantación de identidad (el valor predeterminado es Mover mensaje a la carpeta **correo no deseado**).

2. Seleccione un elemento de la lista para ver detalles sobre el par de infraestructura de dominio y envío en un menú desplegable. La información incluye:
   - Por qué lo capturamos.
   - Lo que necesita hacer.
   - Un resumen de dominio.
   - WhoIs datos sobre el remitente.
   - Mensajes similares que hemos visto en el inquilino del mismo remitente.

   Desde aquí, también puede elegir agregar o quitar el par de infraestructura dominio/envío de la lista permitido para **suplantación** de remitente. Simplemente establece la alternancia según corresponda.

   ![Captura de pantalla de un dominio en el panel de detalles de Spoof intelligence insight](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha configurado la inteligencia suplantación de identidad con remitentes a los que se les permite y no se les permite suplantación de identidad, siga uno de los pasos siguientes:

- En el Centro de seguridad y  cumplimiento de &, vaya a Directiva de administración de amenazas \>  \> **Antispam** \>  \>  \>    expanda Directiva de inteligencia de suplantación de identidad seleccione Mostrarme remitentes que ya revisé seleccione la pestaña Dominios o Dominios externos y compruebe el valor ¿Permitido suplantar? para el remitente.

- En PowerShell, ejecute los siguientes comandos para ver los remitentes a los que se les permite suplantación de identidad:

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
