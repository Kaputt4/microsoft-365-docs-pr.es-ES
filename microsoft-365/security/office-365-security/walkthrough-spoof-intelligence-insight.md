---
title: Administración de remitentes suplantados mediante la directiva de inteligencia de suplantación de identidad y la información de inteligencia de suplantación de identidad
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a usar la directiva de inteligencia de suplantación de identidad y la información de inteligencia de suplantación de identidad para permitir o bloquear remitentes suplantados detectados.
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 59f52e7fe10030283601aad86a1aa49ed91255ab
ms.sourcegitcommit: 363bdc517bd2564c6420cf21f352e97079f950e0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2022
ms.locfileid: "65031831"
---
# <a name="manage-spoofed-senders-using-the-spoof-intelligence-policy-and-spoof-intelligence-insight-in-eop"></a>Administración de remitentes suplantados mediante la directiva de inteligencia de suplantación de identidad y la información de inteligencia de suplantación de identidad en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> En este artículo se describe la experiencia anterior de administración de remitentes suplantados que se va a reemplazar (la **directiva de inteligencia sobre suplantación** de identidad en la página **Directivas contra correo no deseado** ). Para obtener más información sobre la nueva experiencia (la pestaña **Suplantación** de identidad de la lista de permitidos o bloqueados de inquilinos), consulte [Información de inteligencia sobre suplantación de identidad en EOP](learn-about-spoof-intelligence.md).

En Microsoft 365 organizaciones con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online, los mensajes de correo electrónico entrantes se protegen automáticamente contra la suplantación de identidad por parte de EOP a partir de octubre de 2018. EOP usa **inteligencia de suplantación de identidad** como parte de la defensa general de su organización contra la suplantación de identidad (phishing). Para obtener más información, vea [Protección contra la suplantación de identidad en EOP](anti-spoofing-protection.md).

La **directiva de inteligencia** sobre suplantación de identidad predeterminada (y solo) ayuda a garantizar que el correo electrónico suplantado enviado por remitentes legítimos no se encuentre atrapado en los filtros de correo no deseado de EOP mientras protege a los usuarios de ataques de spam o phishing. También puede usar la **información de inteligencia sobre suplantación** de identidad para determinar rápidamente qué remitentes externos le envían legítimamente correo electrónico no autenticado (mensajes de dominios que no pasan comprobaciones de SPF, DKIM o DMARC).

Puede administrar la inteligencia de suplantación de identidad en el portal de Microsoft 365 Defender o en PowerShell (Exchange Online PowerShell para organizaciones Microsoft 365 con buzones en Exchange Online; PowerShell EOP independiente para organizaciones sin Exchange Online  buzones).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Directivas contra correo no deseado**, use <https://security.microsoft.com/antispam>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Debe tener permisos asignados en **Exchange Online** antes de poder realizar los procedimientos de este artículo:
  - Para modificar la directiva de inteligencia de suplantación de identidad o habilitar o deshabilitar la inteligencia de suplantación de identidad, debe ser miembro de 
    -   **Administración de organizaciones**
    -   **Administrador de seguridad** <u>y</u> **Configuración de solo vista** o **Administración de la organización de solo vista**.
  - Para obtener acceso de solo lectura a la directiva de inteligencia de suplantación de identidad, debe ser miembro de los grupos de roles **Lector global** o **Lector de seguridad** .

  Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Notas**:

  - La adición de usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios _y_ los permisos para otras características de Microsoft 365. Para obtener más información, consulte [Acerca de los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Las opciones de inteligencia sobre suplantación de identidad se describen en [Configuración de suplantación de identidad en directivas contra suplantación de identidad (phishing).](set-up-anti-phishing-policies.md#spoof-settings)

- Puede habilitar, deshabilitar y configurar los valores de inteligencia de suplantación de identidad en las directivas contra suplantación de identidad (phishing). Para obtener instrucciones basadas en su suscripción, consulte uno de los temas siguientes:

  - [Configurar directivas contra suplantación de identidad (phishing) en EOP](configure-anti-phishing-policies-eop.md).
  - [Configure las directivas contra phishing en Microsoft Defender para Office 365](configure-mdo-anti-phishing-policies.md).

- Para ver nuestra configuración recomendada para la inteligencia de suplantación de identidad, consulte Configuración de la [directiva de suplantación de identidad (EOP).](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)

## <a name="manage-spoofed-senders"></a>Administración de remitentes suplantados

Hay dos maneras de permitir y bloquear remitentes suplantados:

- [Uso de la directiva de inteligencia de suplantación de identidad](#manage-spoofed-senders-in-the-spoof-intelligence-policy)
- [Uso de la información de inteligencia de suplantación de identidad](#manage-spoofed-senders-in-the-spoof-intelligence-insight)

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-policy"></a>Administración de remitentes suplantados en la directiva de inteligencia de suplantación de identidad

> [!IMPORTANT]
> En este artículo se describe la experiencia anterior de administración de remitentes suplantados que se va a reemplazar (la **directiva de inteligencia sobre suplantación** de identidad en la página **Directivas contra correo no deseado** ). Para obtener más información sobre la nueva experiencia (la pestaña **Suplantación** de identidad de la lista de permitidos o bloqueados de inquilinos), consulte [Información de inteligencia sobre suplantación de identidad en EOP](learn-about-spoof-intelligence.md).

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Correo electrónico y colaboración** \> **Directivas y reglas** \> **Directivas de amenazas** \> **Correo electrónico no deseado** en la sección **Directivas**. Para ir directamente a la página **Directivas contra correo no deseado**, use <https://security.microsoft.com/antispam>.

2. En la página **Directivas contra correo no deseado** , seleccione **Directiva de inteligencia de suplantación** de identidad haciendo clic en el nombre.

   :::image type="content" source="../../media/anti-spam-settings-spoof-intelligence-policy.png" alt-text="La opción para seleccionar la directiva de inteligencia de suplantación de identidad" lightbox="../../media/anti-spam-settings-spoof-intelligence-policy.png":::

3. En el control flotante **De la directiva de inteligencia de** suplantación que aparece, realice una de las siguientes selecciones:
   - **Mostrar los remitentes que ya he revisado**
   - **Revisión de nuevos remitentes**

4. En el control flotante **Decidir si estos remitentes pueden suplantar a los usuarios** que aparece, seleccione una de las pestañas siguientes:
   - **Dominios**: remitentes que suplantan a los usuarios en los dominios internos.
   - **Dominios externos**: remitentes que suplantan usuarios en dominios externos.

5. Haga clic en ![el icono Expandir.](../../media/scc-expand-icon.png) en la columna **Allowed to spoof? (¿Permitido suplantar?** ) y realizar una de las siguientes selecciones:
   - **Sí**: permitir el remitente suplantado.
   - **No**: marque el mensaje como suplantado. La acción se controla mediante la directiva de anti-phishing predeterminada o las directivas anti-phishing personalizadas. Para obtener más información, consulte [Configuración de suplantación de identidad en las directivas contra phishing](set-up-anti-phishing-policies.md#spoof-settings).

   :::image type="content" source="../../media/spoof-allow-block-flyout.png" alt-text="El control flotante de remitentes suplantados y si el remitente tiene permiso para suplantar" lightbox="../../media/spoof-allow-block-flyout.png":::

   Las columnas y los valores que ve se explican en la lista siguiente:

   - **Usuario suplantado**: la cuenta de usuario que se está suplantando. Este es el remitente del mensaje en la dirección De (también conocida como dirección `5322.From` ) que se muestra en los clientes de correo electrónico. SPF no comprueba la validez de esta dirección.
     - En la pestaña **Dominios** , el valor contiene una única dirección de correo electrónico o, si el servidor de correo electrónico de origen está suplantando varias cuentas de usuario, contiene **Más de una**.
     - En la pestaña **Dominios externos** , el valor contiene el dominio del usuario suplantado, no la dirección de correo electrónico completa.

   - **Infraestructura de envío**: dominio que se encuentra en una búsqueda inversa de DNS (registro PTR) de la dirección IP del servidor de correo electrónico de origen. Si la dirección IP de origen no tiene ningún registro PTR, la infraestructura de envío se identifica como \<source IP\>/24 (por ejemplo, 192.168.100.100/24).

     Para obtener más información sobre los orígenes de mensajes y los remitentes de mensajes, consulte [Introducción a los estándares de mensajes de correo electrónico](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).

   - **# de mensajes**: el número de mensajes de la infraestructura de envío a su organización que contienen el remitente o remitentes suplantados especificados en los últimos 30 días.

   - **# de quejas de usuario**: quejas presentadas por los usuarios contra este remitente en los últimos 30 días. Las quejas suelen estar en forma de envíos no deseados a Microsoft.

   - **Resultado de la autenticación**: uno de los valores siguientes:
      - **Pasado**: el remitente pasó las comprobaciones de autenticación de correo electrónico del remitente (SPF o DKIM).
      - **Error**: error en las comprobaciones de autenticación del remitente de EOP.
      - **Desconocido**: no se conoce el resultado de estas comprobaciones.

   - **Última vez que se ha visto**: la última fecha en que se recibió un mensaje de la infraestructura de envío que contiene el usuario suplantado.

   - **¿Se permite suplantar?**: Los valores que se ven aquí son:
     - **Sí**: los mensajes de la combinación de la infraestructura de envío y el usuario suplantado se permiten y no se tratan como correo electrónico suplantado.
     - **No**: los mensajes de la combinación de la infraestructura de envío y el usuario suplantado se marcan como suplantados. La acción se controla mediante la directiva de anti phishing predeterminada o las directivas de anti phishing personalizadas (el valor predeterminado es **Mover mensaje a la carpeta Correo electrónico no deseado**). Consulte la sección siguiente para obtener más información.

     - **Algunos usuarios** (solo la pestaña **Dominios** ): una infraestructura de envío está suplantando a varios usuarios, donde se permiten algunos usuarios suplantados y otros no. Use la pestaña **Detalles** para ver las direcciones específicas.

6. Cuando haya terminado, haga clic en **Guardar**.

#### <a name="use-powershell-to-manage-spoofed-senders"></a>Uso de PowerShell para administrar remitentes suplantados

> [!IMPORTANT]
> En este artículo se describe la experiencia anterior de administración de remitentes suplantados que se va a reemplazar (la **directiva de inteligencia sobre suplantación** de identidad en la página **Directivas contra correo no deseado** ). Para obtener más información sobre la nueva experiencia (la pestaña **Suplantación** de identidad de la lista de permitidos o bloqueados de inquilinos), consulte [Información de inteligencia sobre suplantación de identidad en EOP](learn-about-spoof-intelligence.md).

Para ver los remitentes permitidos y bloqueados en la inteligencia de suplantación de identidad, use la sintaxis siguiente:

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

En este ejemplo se devuelve información detallada sobre todos los remitentes que pueden suplantar a los usuarios de los dominios.

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).

Para configurar remitentes permitidos y bloqueados en inteligencia de suplantación de identidad, siga estos pasos:

1. Capture la lista actual de remitentes suplantados detectados escribiendo la salida del cmdlet **Get-PhishFilterPolicy** en un archivo CSV mediante la ejecución del siguiente comando:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Edite el archivo CSV para agregar o modificar los valores siguientes:
   - **Remitente** (dominio en el registro PTR del servidor de origen o dirección IP/24)
   - **SpoofedUser**: uno de los valores siguientes:
     - Dirección de correo electrónico del usuario interno.
     - Dominio de correo electrónico del usuario externo.
     - Valor en blanco que indica que desea bloquear o permitir todos y cada uno de los mensajes suplantados del **remitente** especificado, independientemente de la dirección de correo electrónico suplantada.
   - **AllowedToSpoof** (Sí o No)
   - **SpoofType** (interno o externo)

   Guarde el archivo, lea el archivo y almacene el contenido como una variable denominada `$UpdateSpoofedSenders` mediante la ejecución del siguiente comando:

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Use la `$UpdateSpoofedSenders` variable para configurar la directiva de inteligencia de suplantación de identidad mediante la ejecución del siguiente comando:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-insight"></a>Administración de remitentes suplantados en la información de inteligencia sobre suplantación de identidad

> [!IMPORTANT]
> En este artículo se describe la experiencia anterior de administración de remitentes suplantados que se va a reemplazar (la **directiva de inteligencia sobre suplantación** de identidad en la página **Directivas contra correo no deseado** ). Para obtener más información sobre la nueva experiencia (la pestaña **Suplantación** de identidad de la lista de permitidos o bloqueados de inquilinos), consulte [Información de inteligencia sobre suplantación de identidad en EOP](learn-about-spoof-intelligence.md).

1. En el Centro de cumplimiento de seguridad &, vaya al **Panel** **de administración de** \> amenazas.

2. En la **fila Ideas**, busque uno de los siguientes elementos:

   - **Es probable que haya dominios suplantados en los últimos siete días**: esta información indica que la inteligencia de suplantación de identidad está habilitada (está habilitada de forma predeterminada).
   - **Habilitar protección contra suplantación** de identidad: esta información indica que la inteligencia de suplantación de identidad está deshabilitada y hacer clic en ella le permite habilitar la inteligencia de suplantación de identidad.

3. La información del panel muestra información como esta:

   :::image type="content" source="../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png" alt-text="La información de inteligencia de suplantación de identidad" lightbox="../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png":::

   Esta información tiene dos modos:

   - **Modo de información**: si la inteligencia de suplantación está habilitada, la información muestra cuántos mensajes se vieron afectados por nuestras capacidades de inteligencia de suplantación de identidad en los últimos siete días.
   - **Modo What if**: si la inteligencia de suplantación está deshabilitada, la información muestra cuántos mensajes *se habrían* visto afectados por nuestras capacidades de inteligencia de suplantación de identidad en los últimos siete días.

   En cualquier caso, los dominios suplantados que se muestran en la información se dividen en dos categorías: **dominios sospechosos** y **dominios no sospechosos**.

   - **Dominios sospechosos**:
     - **Suplantación de confianza alta**: en función de los patrones de envío históricos y la puntuación de reputación de los dominios, estamos muy seguros de que los dominios son suplantados y los mensajes de estos dominios son más propensos a ser malintencionados.
     - **Suplantación de confianza moderada**: en función de los patrones de envío históricos y la puntuación de reputación de los dominios, estamos moderadamente seguros de que los dominios son suplantados y de que los mensajes enviados desde estos dominios son legítimos. Los falsos positivos son más probables en esta categoría que la suplantación de confianza alta.
   - **Dominios no sospechosos**: el dominio no pudo realizar comprobaciones de autenticación explícita de correo electrónico [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md) y [DMARC](use-dmarc-to-validate-email.md). Sin embargo, el dominio pasó nuestras comprobaciones implícitas de autenticación de correo electrónico ([autenticación compuesta](email-validation-and-authentication.md#composite-authentication)). Como resultado, no se realizó ninguna acción contra la suplantación de identidad en el mensaje.

#### <a name="view-detailed-information-about-suspicious-and-nonsuspicious-domains"></a>Ver información detallada sobre dominios sospechosos y no sospechosos

1. En la información de inteligencia de suplantación de identidad, haga clic en **Dominios sospechosos** o **Dominios no sospechosos** para ir a la página **Información de inteligencia de suplantación** . La página **información de Spoof Intelligence** contiene la siguiente información:

   - **Dominio suplantado**: dominio del usuario suplantado que se muestra en el cuadro **De** en los clientes de correo electrónico. Esta dirección también se conoce como dirección `5322.From` .
   - **Infraestructura**: también conocida como _infraestructura de envío_. Dominio encontrado en una búsqueda dns inversa (registro PTR) de la dirección IP del servidor de correo electrónico de origen. Si la dirección IP de origen no tiene ningún registro PTR, la infraestructura de envío se identifica como \<source IP\>/24 (por ejemplo, 192.168.100.100/24).
   - **Recuento** de mensajes: el número de mensajes de la infraestructura de envío a la organización que contienen el dominio suplantado especificado en los últimos 7 días.
   - **Última vez que se ha visto**: la última fecha en que se recibió un mensaje de la infraestructura de envío que contiene el dominio suplantado.
   - **Tipo de suplantación**: este valor es **Externo**.
   - **¿Se permite suplantar?**: Los valores que se ven aquí son:
     - **Sí**: los mensajes de la combinación del dominio del usuario suplantado y la infraestructura de envío se permiten y no se tratan como correo electrónico suplantado.
     - **No**: los mensajes de la combinación del dominio del usuario suplantado y la infraestructura de envío se marcan como suplantados. La acción se controla mediante la directiva de anti phishing predeterminada o las directivas de anti phishing personalizadas (el valor predeterminado es **Mover mensaje a la carpeta Correo electrónico no deseado**).

2. Seleccione un elemento de la lista para ver detalles sobre el par de infraestructura de dominio o envío en un control flotante. La información incluye:
   - Por qué lo capturamos.
   - Lo que tienes que hacer.
   - Un resumen de dominio.
   - WhoIs datos sobre el remitente.
   - Mensajes similares que hemos visto en el inquilino desde el mismo remitente.

   Desde aquí, también puede elegir agregar o quitar el par de infraestructura de dominio o envío de la lista **permitido para suplantar al** remitente. Simplemente establezca el botón de alternancia en consecuencia.

   :::image type="content" source="../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png" alt-text="Un dominio en el panel Detalles de información de inteligencia de suplantación" lightbox="../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png":::

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha configurado inteligencia de suplantación de identidad con remitentes a los que se les permite y no se les permite suplantar, siga estos pasos:

- Colaboración \> **& por correo electrónico** **Directivas & reglas** \> **Directivas de amenazas** \> En **la sección** \> \> **Directivas**, **antispam**, seleccione **Mostrar remitentes que ya he revisado**\>, seleccione la pestaña **Dominios** o **dominios externos** y compruebe el valor **¿Permitido suplantar?** para el remitente.

- En PowerShell, ejecute los siguientes comandos para ver los remitentes a los que se permite y no se les permite suplantar:

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
