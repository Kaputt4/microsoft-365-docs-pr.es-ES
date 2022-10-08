---
title: Configuración de la directiva de filtro de conexión predeterminada
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- m365-security
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a configurar el filtrado de conexiones en Exchange Online Protection (EOP) para permitir o bloquear correos electrónicos de servidores de correo electrónico.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 5f6b654f44ca1af763c6e6034a6a49acf17ee546
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68055180"
---
# <a name="configure-connection-filtering"></a>Configurar el filtrado de la conexión

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Si es un cliente de Microsoft 365 con buzones en Exchange Online o un cliente independiente de Exchange Online Protection (EOP) sin Exchange Online buzones, usa el filtrado de conexiones en EOP (en concreto, la directiva de filtro de conexión predeterminada) para identificar los servidores de correo electrónico de origen correctos o incorrectos por sus direcciones IP. Los componentes clave de la directiva de filtro de conexión predeterminada son:

- **Lista de direcciones IP permitidas**: omita el filtrado de correo no deseado para todos los mensajes entrantes de los servidores de correo electrónico de origen que especifique por dirección IP o intervalo de direcciones IP. Para ver los escenarios en los que el filtrado de correo no deseado puede seguir produciendo en los mensajes de estos orígenes, consulte la sección [Escenarios en los que los mensajes de los orígenes de la lista de direcciones IP permitidas se siguen filtrando](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) más adelante en este artículo. Para obtener más información sobre cómo la lista de direcciones IP permitidas debe ajustarse a la estrategia general de remitentes seguros, consulte [Creación de listas de remitentes seguros en EOP](create-safe-sender-lists-in-office-365.md).

- **Lista de direcciones IP bloqueadas**: bloquee todos los mensajes entrantes de los servidores de correo electrónico de origen que especifique por dirección IP o intervalo de direcciones IP. Los mensajes entrantes se rechazan, no se marcan como correo no deseado y no se produce ningún filtrado adicional. Para obtener más información sobre cómo la lista de direcciones IP bloqueadas debe ajustarse a la estrategia general de remitentes bloqueados, consulte [Creación de listas de remitentes de bloques en EOP](create-block-sender-lists-in-office-365.md).

- **Lista segura**: la *lista segura* es una lista de permitidos dinámica en el centro de datos de Microsoft que no requiere ninguna configuración del cliente. Microsoft identifica estos orígenes de correo electrónico de confianza de suscripciones a varias listas de terceros. Habilite o deshabilite el uso de la lista segura; no puede configurar los servidores de correo electrónico de origen en la lista segura. El filtrado de correo no deseado se omite en los mensajes entrantes de los servidores de correo electrónico de la lista segura.

En este artículo se describe cómo configurar la directiva de filtro de conexión predeterminada en el portal de Microsoft 365 Defender de Microsoft 365 o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; PowerShell EOP independiente para organizaciones sin Exchange Online buzones). Para obtener más información sobre cómo usa EOP el filtrado de conexiones forma parte de la configuración general de antispam de la organización, consulte [Protección contra correo no deseado](anti-spam-protection.md).

> [!NOTE]
> La lista de direcciones IP permitidas, la lista segura y la lista de direcciones IP bloqueadas forman parte de la estrategia general para permitir o bloquear el correo electrónico en su organización. Para obtener más información, vea [Crear listas de remitentes seguros](create-safe-sender-lists-in-office-365.md) y [Crear listas de remitentes bloqueados](create-block-sender-lists-in-office-365.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Directivas contra correo no deseado**, use <https://security.microsoft.com/antispam>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Debe tener permisos asignados en **Exchange Online** antes de poder realizar los procedimientos de este artículo:
  - Para modificar la directiva de filtro de conexión predeterminada, debe ser miembro de los grupos de roles **Administración de la organización** o **Administrador de seguridad** .
  - Para obtener acceso de solo lectura a la directiva de filtro de conexión predeterminada, debe ser miembro de los grupos de roles **Lector global** o **Lector de seguridad** .

  Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Notas**:

  - Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365. For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Para buscar las direcciones IP de origen de los servidores de correo electrónico (remitentes) que desea permitir o bloquear, puede comprobar el campo de encabezado ip de conexión (**CIP**) en el encabezado del mensaje. Para ver un encabezado de mensaje en varios clientes de correo electrónico, vea [Ver encabezados de mensajes de Internet en Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).

- La lista de direcciones IP permitidas tiene prioridad sobre la lista de direcciones IP bloqueadas (no se bloquea una dirección en ambas listas).

- La lista de direcciones IP permitidas y la lista de direcciones IP bloqueadas admiten un máximo de 1273 entradas, donde una entrada es una única dirección IP, un intervalo de direcciones IP o una dirección IP de enrutamiento de interdominios sin clase (CIDR).

## <a name="use-the-microsoft-365-defender-portal-to-modify-the-default-connection-filter-policy"></a>Uso del portal de Microsoft 365 Defender para modificar la directiva de filtro de conexión predeterminada

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Correo electrónico y colaboración** \> **Directivas y reglas** \> **Directivas de amenazas** \> **Correo electrónico no deseado** en la sección **Directivas**. Para ir directamente a la página **Directivas contra correo no deseado**, use <https://security.microsoft.com/antispam>.

2. En la página **Directivas contra correo no deseado** , seleccione **Directiva de filtro de conexión (predeterminada)** en la lista haciendo clic en el nombre de la directiva.

3. En el control flotante de detalles de la directiva que aparece, configure cualquiera de los siguientes valores:

   - **Sección Descripción** : haga clic en **Editar nombre y descripción**. En el control flotante **Editar nombre y descripción** que aparece, escriba texto descriptivo opcional en el cuadro **Descripción** .

     Cuando haya terminado, haga clic en **Guardar**.

   - **Sección de filtrado de conexiones**: haga clic en Editar directiva de **filtro de conexión**. En el control flotante que aparece, configure los siguientes valores:

     - **Permitir siempre mensajes de las siguientes direcciones IP o intervalo de direcciones**: esta es la lista de direcciones IP permitidas. Haga clic en el cuadro, escriba un valor y, a continuación, presione Entrar o seleccione el valor completo que se muestra debajo del cuadro. Los valores válidos son:
       - Ip única: por ejemplo, 192.168.1.1.
       - Intervalo IP: por ejemplo, 192.168.0.1-192.168.0.254.
       - IP CIDR: por ejemplo, 192.168.0.1/25. Los valores de máscara de subred válidos son /24 a /32. Para omitir el filtrado de correo no deseado de /1 a /23, consulte la sección [Omitir filtrado de correo no deseado para una dirección IP CIDR fuera del intervalo disponible](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) más adelante en este artículo.

       Repita este paso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Icono Quitar.](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

     Para agregar la dirección IP o el intervalo de direcciones, haga clic en el cuadro y escriba en **Agregar** ![icono](../../media/ITPro-EAC-AddIcon.png). Para quitar una entrada, seleccione la entrada en **Dirección IP permitida** y, a continuación, haga clic en **Quitar**![](../../media/scc-remove-icon.png). Cuando haya terminado, haga clic en **Guardar**.

   - **Bloquear siempre los mensajes de las siguientes direcciones IP o intervalo de direcciones**: esta es la lista de direcciones IP bloqueadas. Escriba una única dirección IP, intervalo IP o IP CIDR en el cuadro tal como se describió anteriormente en la configuración **Permitir siempre mensajes de las siguientes direcciones IP o intervalo de direcciones** .

   - **Activar lista segura**: habilite o deshabilite el uso de la lista segura para identificar los remitentes conocidos y correctos que omitirán el filtrado de correo no deseado. Para usar la lista segura, active la casilla .

   Cuando haya terminado, haga clic en **Guardar**.

4. De nuevo en el control flotante de detalles de la directiva, haga clic en **Cerrar**.

## <a name="use-the-microsoft-365-defender-portal-to-view-the-default-connection-filter-policy"></a>Use el portal de Microsoft 365 Defender para ver la directiva de filtro de conexión predeterminada.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Correo electrónico y colaboración** \> **Directivas y reglas** \> **Directivas de amenazas** \> **Correo electrónico no deseado** en la sección **Directivas**. Para ir directamente a la página **Directivas contra correo no deseado**, use <https://security.microsoft.com/antispam>.

2. En la página **Directivas contra correo no deseado** , se muestran las siguientes propiedades en la lista de directivas:

   - **Nombre**: este valor es **Directiva de filtro de conexión (valor predeterminado)** para la directiva de filtro de conexión predeterminada.
   - **Estado**: este valor está **siempre activado** para la directiva de filtro de conexión predeterminada.
   - **Prioridad**: este valor es **El más bajo** para la directiva de filtro de conexión predeterminada.
   - **Tipo**: este valor está en blanco para la directiva de filtro de conexión predeterminada.

3. Al seleccionar la directiva de filtro de conexión predeterminada, la configuración de la directiva se muestra en un control flotante.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Use Exchange Online PowerShell o PowerShell EOP independiente para modificar la directiva de filtro de conexión predeterminada.

Utilice la siguiente sintaxis:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Notas**:

- Los valores de intervalo de direcciones o direcciones IP válidos son:
  - Ip única: por ejemplo, 192.168.1.1.
  - Intervalo IP: por ejemplo, 192.168.0.1-192.168.0.254.
  - IP CIDR: por ejemplo, 192.168.0.1/25. Los valores de máscara de red válidos son /24 a /32.
- Para *sobrescribir* las entradas existentes con los valores especificados, use la sintaxis siguiente: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN`.
- Para *agregar o quitar* direcciones IP o intervalos de direcciones sin afectar a otras entradas existentes, use la sintaxis siguiente: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}`.
- Para vaciar la lista de direcciones IP permitidas o la lista de direcciones IP bloqueadas, use el valor `$null`.

En este ejemplo se configuran la lista de direcciones IP permitidas y la lista de direcciones IP bloqueadas con las direcciones IP y los intervalos de direcciones especificados.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

En este ejemplo se agregan y quitan las direcciones IP y los intervalos de direcciones especificados de la lista de direcciones IP permitidas.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-HostedConnectionFilterPolicy](/powershell/module/exchange/set-hostedconnectionfilterpolicy).

## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Para comprobar que ha modificado correctamente la directiva de filtro de conexión predeterminada, siga estos pasos:

- En la página **Antispam** del portal de Microsoft 365 Defender en <https://security.microsoft.com/antispam>, seleccione Directiva de **filtro de conexión (valor predeterminado)** en la lista haciendo clic en el nombre de la directiva y compruebe la configuración.

- En Exchange Online PowerShell o PowerShell EOP independiente, ejecute el siguiente comando y compruebe la configuración:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Envíe un mensaje de prueba desde una entrada en la lista de direcciones IP permitidas.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Consideraciones adicionales para la lista de direcciones IP permitidas

En las secciones siguientes se identifican elementos adicionales que debe conocer al configurar la lista de direcciones IP permitidas.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Omitir el filtrado de correo no deseado para una dirección IP CIDR fuera del intervalo disponible

Como se describió anteriormente en este artículo, solo puede usar una dirección IP CIDR con la máscara de red /24 a /32 en la lista de direcciones IP permitidas. Para omitir el filtrado de correo no deseado en los mensajes de los servidores de correo electrónico de origen del intervalo /1 a /23, debe usar reglas de flujo de correo de Exchange (también conocidas como reglas de transporte). Sin embargo, se recomienda no hacerlo si es posible, ya que los mensajes se bloquearán si aparece una dirección IP en el intervalo IP de CIDR /1 a /23 en cualquiera de las listas de bloques propietarias o de terceros de Microsoft.

Ahora que es totalmente consciente de los posibles problemas, puede crear una regla de flujo de correo con la siguiente configuración (como mínimo) para asegurarse de que los mensajes de estas direcciones IP omitirán el filtrado de correo no deseado:

- Condición de regla: **aplique esta regla si** \> **la** **dirección IP del remitente está en cualquiera de estos intervalos o coincide** \> exactamente (escriba la dirección IP de CIDR con una máscara de red /1 a /23).\>
- Acción de regla: **modifique las propiedades** \> del mensaje **Establezca el nivel de confianza de correo no deseado (SCL)** \> **omita el filtrado de correo no deseado**.

Puede auditar la regla, probarla, activarla durante un período de tiempo específico y otras selecciones. Recomendamos probar la regla durante un tiempo antes de aplicarla. Para obtener más información, vea [Administrar reglas de flujo de correo en Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Omitir el filtrado de correo no deseado en dominios de correo electrónico selectivos desde el mismo origen

Normalmente, agregar una dirección IP o un intervalo de direcciones a la lista de direcciones IP permitidas significa que confía en todos los mensajes entrantes de ese origen de correo electrónico. ¿Pero qué ocurre si ese origen envía correo electrónico desde varios dominios y quiere omitir el filtrado de correo no deseado para algunos de esos dominios, pero no para otros? No puede usar la lista de direcciones IP permitidas solo para hacerlo, pero puede usar la lista de direcciones IP permitidas en combinación con una regla de flujo de correo.

Por ejemplo, el servidor de correo electrónico de origen 192.168.1.25 envía correo electrónico desde los dominios contoso.com, fabrikam.com y tailspintoys.com, pero solo quiere omitir el filtrado de correo no deseado para los mensajes de los remitentes de fabrikam.com. Para hacerlo, siga estos pasos:

1. Agregue 192.168.1.25 a la lista de direcciones IP permitidas.

2. Configure una regla de flujo de correo con los siguientes valores (como mínimo):
   - Condición de regla: **aplique esta regla si** \> **la** **dirección IP del remitente está en cualquiera de estos intervalos o coincide** \> exactamente con 192.168.1.25 (la misma dirección IP o intervalo de direcciones que agregó a la lista de direcciones IP permitidas en el paso anterior).\>
   - Acción de regla: **modifique las propiedades** \> del mensaje **Establezca el nivel de confianza de correo no deseado (SCL)** \> **0**.
   - Excepción de regla: **el dominio del remitente** \> **es** \> fabrikam.com (solo el dominio o dominios que desea omitir el filtrado de correo no deseado).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Escenarios en los que los mensajes de los orígenes de la lista de direcciones IP permitidas siguen filtrados

Los mensajes de un servidor de correo electrónico de la lista de direcciones IP permitidas siguen estando sujetos al filtrado de correo no deseado en los siguientes escenarios:

- Una dirección IP de la lista de direcciones IP permitidas también se configura en un conector de entrada local basado en IP en *cualquier* inquilino de Microsoft 365 (vamos a llamar a este inquilino A) **y** el inquilino A y el servidor EOP que encuentran primero el mensaje se encuentran en *el mismo* bosque de Active Directory en los centros de datos de Microsoft. En este escenario, **IPV:CAL** *se* agrega a los [encabezados de mensajes antispam](anti-spam-message-headers.md) del mensaje (lo que indica que el mensaje omitió el filtrado de correo no deseado), pero el mensaje sigue estando sujeto al filtrado de correo no deseado.

- El inquilino que contiene la lista de direcciones IP permitidas y el servidor EOP que encuentra primero el mensaje se encuentran en *bosques de* Active Directory diferentes en los centros de datos de Microsoft. En este escenario, **IPV:CAL** *no se* agrega a los encabezados de mensaje, por lo que el mensaje sigue sujeto al filtrado de correo no deseado.

Si encuentra cualquiera de estos escenarios, puede crear una regla de flujo de correo con la siguiente configuración (como mínimo) para asegurarse de que los mensajes de las direcciones IP problemáticas omitirán el filtrado de correo no deseado:

- Condición de **regla: aplique esta regla si** \> la dirección IP del **remitente** \> **está en cualquiera de estos intervalos o coincide** \> exactamente (su dirección IP o direcciones).
- Acción de regla: **modifique las propiedades** \> del mensaje **Establezca el nivel de confianza de correo no deseado (SCL)** \> **omita el filtrado de correo no deseado**.

## <a name="new-to-microsoft-365"></a>¿Es nuevo en Microsoft 365?

****

![Icono corto de LinkedIn Learning.](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **¿Es nuevo en Microsoft 365?** Descubra cursos de vídeo **gratuitos para administradores y profesionales de TI de Microsoft 365**, que LinkedIn Learning le ofrece.
