---
title: Configuración de la Directiva de filtro de conexión predeterminada
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a configurar el filtrado de conexiones en Exchange Online Protection (EOP) para permitir o bloquear los correos electrónicos de los servidores de correo electrónico.
ms.openlocfilehash: 675247ba1764cb928bec967c581083c6365f635a
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656796"
---
# <a name="configure-connection-filtering"></a>Configurar el filtrado de la conexión

Si es un cliente de 365 de Microsoft con buzones de correo en Exchange online o un cliente independiente de Exchange Online Protection (EOP) sin buzones de Exchange Online, use el filtrado de conexiones en EOP (específicamente, la Directiva de filtro de conexión predeterminada) para identificar los servidores de correo electrónico de origen válidos o incorrectos mediante sus direcciones IP. Los componentes clave de la Directiva de filtro de conexión predeterminada son:

- **Lista de direcciones IP permitidas**: omita el filtrado de correo no deseado para todos los mensajes entrantes de los servidores de correo electrónico de origen que especifique por dirección IP o intervalo de direcciones IP. Para escenarios en los que el filtrado de correo no deseado todavía puede producirse en los mensajes de estos orígenes, vea los escenarios en los [que los mensajes de orígenes en la lista de direcciones IP permitidas siguen filtrados](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) en la sección más adelante en este tema. Para obtener más información acerca de cómo la lista de direcciones IP permitidas debe ajustarse a su estrategia general de remitentes seguros, consulte [Create Safe Sender lists in EOP](create-safe-sender-lists-in-office-365.md).

- **Lista de direcciones IP bloqueadas**: bloquee todos los mensajes entrantes de los servidores de correo electrónico de origen que especifique por dirección IP o intervalo de direcciones IP. Los mensajes entrantes se rechazan, no se marcan como correo no deseado y no se produce ningún filtrado adicional. Para obtener más información acerca de cómo debe ajustarse la lista de direcciones IP bloqueadas en la estrategia general de remitentes bloqueados, vea [Create Block Sender lists in EOP](create-block-sender-lists-in-office-365.md).

- **Lista segura**: la *lista segura* es una lista de permitidos dinámicos en el centro de recursos de Microsoft que no requiere configuración de clientes. Microsoft identifica estos orígenes de correo electrónico de confianza de las suscripciones a varias listas de terceros. Puede habilitar o deshabilitar el uso de la lista segura; no puede configurar los servidores de correo electrónico de origen en la lista segura. El filtrado de correo no deseado se omite en los mensajes entrantes de los servidores de correo electrónico en la lista segura.

En este tema se describe cómo configurar la Directiva de filtro de conexión predeterminada en el centro de seguridad & cumplimiento o en PowerShell (Exchange Online PowerShell para Microsoft 365 organizaciones con buzones en Exchange Online; independiente de EOP para las organizaciones sin buzones de correo de Exchange Online). Para obtener más información acerca de cómo EOP usa el filtrado de conexiones como parte de la configuración general de correo no deseado de la organización, consulte See [anti-spam protection](anti-spam-protection.md).

> [!NOTE]
> La lista de direcciones IP permitidas, la lista segura y la lista de direcciones IP bloqueadas son una parte de la estrategia general para permitir o bloquear el correo electrónico en la organización. Para obtener más información, vea [crear listas de remitentes seguros](create-safe-sender-lists-in-office-365.md) y [crear listas de remitentes bloqueados](create-block-sender-lists-in-office-365.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página **Configuración contra correo no deseado**, use <https://protection.office.com/antispam>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Para poder realizar los procedimientos de este tema, deberá tener asignados los permisos necesarios:

  - Para modificar la Directiva de filtro de conexión predeterminada, debe pertenecer a uno de los siguientes grupos de roles:

    - **Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).
    - **Administración de la organización** o **Administración de higiene** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Para obtener acceso de solo lectura a la Directiva de filtro de conexión predeterminada, debe ser miembro de uno de los siguientes grupos de roles:

    - **Lector de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).
    - **Administración de la organización de solo visualización** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Para buscar las direcciones IP de origen de los servidores de correo electrónico (remitentes) que desea permitir o bloquear, puede comprobar el campo de encabezado de IP de conexión (**CIP**) en el encabezado del mensaje. Para ver un encabezado de mensaje en varios clientes de correo electrónico, consulte [Ver encabezados de mensajes de Internet en Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).

- La lista de direcciones IP permitidas tiene prioridad sobre la lista de direcciones IP bloqueadas (no se bloquea una dirección en ambas listas).

- La lista de IP permitidas y la lista de direcciones IP bloqueadas admiten un máximo de 1273 entradas, donde una entrada es una dirección IP única, un intervalo de direcciones IP o una IP de enrutamiento de interdominios sin clases (CIDR).

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>Usar el centro de seguridad & cumplimiento para modificar la Directiva de filtro de conexión predeterminada

1. En el centro de seguridad & cumplimiento y vaya a la Directiva de **Administración de amenazas** \> **Policy** \> **contra correo no deseado**.

2. En la página **configuración contra correo no deseado** , expanda **Directiva de filtro de conexión** haciendo clic en ![ expandir icono ](../../media/scc-expand-icon.png) y, a continuación, en **Editar Directiva**.

3. En el control flotante **predeterminado** que aparece, configure cualquiera de las siguientes opciones:

   - **Descripción**: escriba un texto descriptivo opcional.

   - **Lista de direcciones IP permitidas**: haga clic en **Editar**. En el control flotante de la lista de direcciones **IP permitidas** que aparece, escriba una dirección IPv4 en el cuadro **dirección o intervalo de direcciones** con la siguiente sintaxis:

     - IP única: por ejemplo, 192.168.1.1.

     - Intervalo IP: por ejemplo, 192.168.0.1-192.168.0.254.

     - IP CIDR: por ejemplo, 192.168.0.1/25. Los valores de máscara de red válidos son de/24 a/32. Para omitir el filtrado de correo no deseado para valores de máscara IP CIDR/1 a/23, vea la sección [omitir el filtrado de correo no deseado para una IP CIDR fuera de la sección de intervalo disponible](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) más adelante en este tema.

     Para agregar la dirección IP o el intervalo de direcciones, haga clic en **Agregar** ![ icono de agregar ](../../media/ITPro-EAC-AddIcon.png) . Para quitar una entrada, seleccione la entrada en **dirección IP permitida** y, a continuación, haga clic en **quitar** ![ ](../../media/scc-remove-icon.png) . Cuando haya terminado, haga clic en **Guardar**.

   - **Lista de direcciones IP bloqueadas**: haga clic en **Editar**. En el control flotante de la lista de direcciones **IP bloqueadas** que aparece, escriba una IP única, un intervalo IP o una IP CIDR en el cuadro **dirección o intervalo de direcciones** , como se ha descrito anteriormente en la configuración de la lista de direcciones **IP permitidas** .

     Para agregar la dirección IP o el intervalo de direcciones, haga clic en **Agregar** ![ icono de agregar ](../../media/ITPro-EAC-AddIcon.png) . Para quitar una entrada, seleccione la entrada en **dirección IP bloqueada** y, a continuación, haga clic en **quitar** ![ ](../../media/scc-remove-icon.png) . Cuando haya terminado, haga clic en **Guardar**.

   - **Activar la lista segura**: habilite o deshabilite el uso de la lista segura para identificar los remitentes conocidos y correctos que omitirán el filtrado de correo no deseado.

4. Cuando haya terminado, haga clic en **Guardar**.

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>Usar el centro de seguridad & cumplimiento para ver la Directiva de filtro de conexión predeterminada

1. En el centro de seguridad & cumplimiento y vaya a la Directiva de **Administración de amenazas** \> **Policy** \> **contra correo no deseado**.

2. En la página **configuración contra correo no deseado** , haga clic en la lista desplegable junto a la directiva predeterminada denominada **Directiva de filtro de conexión**.

3. La configuración de la Directiva se muestra en la lista desplegable que se abre.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Usar Exchange Online PowerShell o PowerShell independiente de EOP para modificar la Directiva de filtro de conexión predeterminada

Utilice la sintaxis siguiente:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Notas**:

- Los valores válidos de dirección IP o intervalo de direcciones son:

  - IP única: por ejemplo, 192.168.1.1.

  - Intervalo IP: por ejemplo, 192.168.0.1-192.168.0.254.

  - IP CIDR: por ejemplo, 192.168.0.1/25. Los valores de máscara de red válidos son de/24 a/32.

- Para *sobrescribir* las entradas existentes con los valores que especifique, use la siguiente sintaxis: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` .

- Para *Agregar o quitar* direcciones IP o intervalos de direcciones sin afectar a las entradas existentes, use la siguiente sintaxis: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` .

- Para vaciar la lista de direcciones IP permitidas o de direcciones IP bloqueadas, use el valor `$null` .

En este ejemplo se configuran la lista de direcciones IP permitidas y la lista de direcciones IP bloqueadas con las direcciones IP y los intervalos de direcciones especificados.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

En este ejemplo se agregan y se quitan las direcciones IP y los intervalos de direcciones especificados de la lista de direcciones IP permitidas.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy).

## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Para comprobar que la Directiva de filtro de conexión predeterminada se modificó correctamente, siga uno de estos pasos:

- En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración de amenazas** \> **Policy** \> **contra correo no deseado** , \> haga clic en la lista desplegable junto a **Directiva de filtro de conexión (Always on**) y Compruebe la configuración.

- En Exchange Online PowerShell o PowerShell independiente de EOP, ejecute el siguiente comando y Compruebe la configuración:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Envíe un mensaje de prueba desde una entrada en la lista de direcciones IP permitidas.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Consideraciones adicionales para la lista de direcciones IP permitidas

En las siguientes secciones se identifican los elementos adicionales que necesita conocer al configurar la lista de direcciones IP permitidas.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Omitir el filtrado de correo no deseado para una IP CIDR fuera del intervalo disponible

Como se describió anteriormente en este tema, solo puede usar una IP de CIDR con la máscara de red/24 a/32 en la lista de direcciones IP permitidas. Para omitir el filtrado de correo no deseado en los mensajes de los servidores de correo electrónico de origen en el intervalo de/1 a/23, debe usar reglas de flujo de correo de Exchange (también conocidas como reglas de transporte). Pero, se recomienda no hacerlo si es posible, ya que los mensajes se bloquearán si aparece una dirección IP en el intervalo de IP de CIDR a/23 en cualquiera de las listas de bloqueo propias o de terceros de Microsoft.

Ahora que ya conoce los posibles problemas, puede crear una regla de flujo de correo con la siguiente configuración (como mínimo) para asegurarse de que los mensajes de estas direcciones IP omitirán el filtrado de correo no deseado:

- Condición de regla: **aplique esta regla si** \> **la** \> **dirección IP del remitente se encuentra en cualquiera de estos intervalos o si coincide exactamente** \> (escriba la IP de CIDR con una máscara de red de/1 a/23).

- Acción de regla: **modifique las propiedades del mensaje** \> **establecer el nivel de confianza contra correo no deseado (SCL)** \> **pasar por alto el filtrado de correo no deseado**.

Puede auditar la regla, probarla, activar la regla durante un período de tiempo específico y otras selecciones. Recomendamos probar la regla durante un tiempo antes de aplicarla. Para obtener más información, consulte [Manage mail Flow Rules in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Omitir el filtrado de correo no deseado en dominios de correo electrónico selectivos del mismo origen

Normalmente, agregar una dirección IP o un intervalo de direcciones a la lista de direcciones IP permitidas significa que confía en todos los mensajes entrantes de ese origen de correo electrónico. Pero, ¿qué ocurre si el origen envía correo electrónico desde varios dominios y desea omitir el filtrado de correo no deseado para algunos de esos dominios, pero no otros? No puede usar la lista de direcciones IP permitidas solo para hacer esto, pero puede usar la lista de direcciones IP permitidas en combinación con una regla de flujo de correo.

Por ejemplo, el servidor de correo electrónico de origen 192.168.1.25 envía correo electrónico desde los dominios contoso.com, fabrikam.com y tailspintoys.com, pero solo desea omitir el filtrado de correo no deseado para los mensajes de remitentes en fabrikam.com. Para ello, siga estos pasos:

1. Agregue 192.168.1.25 a la lista de direcciones IP permitidas.

2. Configure una regla de flujo de correo con la siguiente configuración (como mínimo):

   - Condición de regla: **aplique esta regla si** \> **la** \> **dirección IP del remitente se encuentra en cualquiera de estos intervalos o si coincide exactamente con** \> 192.168.1.25 (la misma dirección IP o intervalo de direcciones que agregó a la lista de direcciones IP permitidas en el paso anterior).

   - Acción de regla: **modificar las propiedades del mensaje** \> **establecer el nivel de confianza contra correo no deseado (SCL)** \> **0**.

   - Excepción de regla: **el dominio del remitente** \> **es** \> fabrikam.com (solo el dominio o los dominios que desea omitir el filtrado de correo no deseado).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Escenarios en los que los mensajes de orígenes en la lista de direcciones IP permitidas todavía se filtran

Los mensajes de un servidor de correo electrónico de la lista de direcciones IP permitidas siguen estando sujetos al filtrado de correo no deseado en los siguientes escenarios:

- Una dirección IP de la lista de direcciones IP permitidas también se configura en un conector de entrada basado en IP local en *cualquier* espacio empresarial de Microsoft 365 (vamos a llamar a este inquilino a), **y** el inquilino a y el servidor de EOP que encuentra el mensaje en primer lugar en el *mismo* bosque de Active Directory en los centros de recursos de Microsoft. En este escenario, **IPV: cal** *se* agrega a los encabezados de los [mensajes contra correo no deseado](anti-spam-message-headers.md) del mensaje (lo que indica que el mensaje ha omitido el filtrado de correo no deseado), pero el mensaje sigue sujeto al filtrado de correo no deseado.

- El espacio empresarial que contiene la lista de direcciones IP permitidas y el servidor de EOP que en primer lugar encuentra el mensaje que se encuentra en *diferentes* bosques de Active Directory en los centros de recursos de Microsoft. En este escenario, **IPV: cal** *no se* agrega a los encabezados de los mensajes, por lo que el mensaje sigue sujeto al filtrado de correo no deseado.

Si se encuentra en cualquiera de estos escenarios, puede crear una regla de flujo de correo con la siguiente configuración (como mínimo) para asegurarse de que los mensajes de las direcciones IP problemáticas omitirán el filtrado de correo no deseado:

- Condición de regla: **aplique esta regla si** \> **la** \> **dirección IP del remitente está en cualquiera de estos intervalos o coincide exactamente con** \> la dirección o las direcciones IP.

- Acción de regla: **modifique las propiedades del mensaje** \> **establecer el nivel de confianza contra correo no deseado (SCL)** \> **pasar por alto el filtrado de correo no deseado**.

## <a name="new-to-microsoft-365"></a>¿Es la novedad de Microsoft 365?

|<!-- a -->|
|---|
|![El icono corto de LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New a Microsoft 365?** Descubra los cursos de vídeo gratuitos para **administradores y profesionales de ti**, que le ha ofrecido LinkedIn Learning.|
|
