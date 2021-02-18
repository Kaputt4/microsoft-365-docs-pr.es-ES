---
title: Configurar la directiva de filtro de conexión predeterminada
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a configurar el filtrado de conexiones en Exchange Online Protection (EOP) para permitir o bloquear correos electrónicos de servidores de correo electrónico.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c6ec8b4adcdda692ee561f7d50bacf0511642269
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290050"
---
# <a name="configure-connection-filtering"></a>Configurar el filtrado de la conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)


Si es un cliente de Microsoft 365 con buzones en Exchange Online o un cliente independiente de Exchange Online Protection (EOP) sin buzones de Exchange Online, use el filtrado de conexiones en EOP (específicamente, la directiva de filtro de conexión predeterminada) para identificar servidores de correo electrónico de origen bueno o no deseado por sus direcciones IP. Los componentes clave de la directiva de filtro de conexión predeterminada son:

- **Lista de direcciones IP permitidos:** omita el filtrado de correo no deseado para todos los mensajes entrantes de los servidores de correo electrónico de origen que especifique por dirección IP o intervalo de direcciones IP. Para los escenarios en los que el filtrado de correo no deseado aún puede producirse en mensajes de estos orígenes, vea la sección Escenarios en los que los mensajes procedentes de orígenes de la lista de direcciones [IP permitidos](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) aún se filtran más adelante en este artículo. Para obtener más información acerca de cómo la lista de direcciones IP permitidos debe ajustarse a su estrategia general de remitentes seguros, vea Crear listas de remitentes seguros [en EOP.](create-safe-sender-lists-in-office-365.md)

- **Lista de direcciones IP no** válidas: bloquee todos los mensajes entrantes de los servidores de correo electrónico de origen que especifique por dirección IP o intervalo de direcciones IP. Los mensajes entrantes se rechazan, no se marcan como correo no deseado y no se produce ningún filtrado adicional. Para obtener más información acerca de cómo la lista de direcciones IP bloqueadas debe ajustarse a su estrategia general de remitentes bloqueados, vea Crear listas de remitentes bloqueados [en EOP.](create-block-sender-lists-in-office-365.md)

- **Lista segura:** la *lista segura es* una lista dinámica de permitidos en el centro de datos de Microsoft que no requiere ninguna configuración de cliente. Microsoft identifica estos orígenes de correo electrónico de confianza de suscripciones a varias listas de terceros. Habilitar o deshabilitar el uso de la lista segura; no puede configurar los servidores de correo electrónico de origen en la lista segura. El filtrado de correo no deseado se omite en los mensajes entrantes de los servidores de correo electrónico de la lista segura.

En este tema se describe cómo configurar la directiva de filtro de conexión predeterminada en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; EOP PowerShell independiente para organizaciones sin buzones de Exchange Online). Para obtener más información acerca de cómo EOP usa el filtrado de conexiones forma parte de la configuración general contra correo no deseado de su organización, vea Protección contra correo [no deseado.](anti-spam-protection.md)

> [!NOTE]
> La lista de direcciones IP permitidos, la lista segura y la lista de direcciones IP no seguras forman parte de la estrategia general para permitir o bloquear el correo electrónico en la organización. Para obtener más información, vea [Crear listas de remitentes seguros](create-safe-sender-lists-in-office-365.md) y Crear listas de [remitentes bloqueados.](create-block-sender-lists-in-office-365.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página **Configuración contra correo no deseado**, use <https://protection.office.com/antispam>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento para poder realizar los procedimientos de este artículo:
  - Para modificar la directiva de filtro de conexión  predeterminada, debe ser miembro de los grupos de roles Administración de la organización o **Administrador de** seguridad.
  - Para obtener acceso de solo lectura a la directiva de filtro de conexión predeterminada, debe ser miembro de los grupos de roles Lector **global** o **Lector de** seguridad.

  Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

  **Notas**:

  - Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Para buscar las direcciones IP de origen de los servidores de correo electrónico (remitentes) que desea permitir o bloquear, puede comprobar el campo de encabezado IP **(CIP)** de conexión en el encabezado del mensaje. Para ver un encabezado de mensaje en varios clientes de correo electrónico, vea [Ver encabezados de mensajes de Internet en Outlook.](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)

- La lista de direcciones IP bloqueadas tiene prioridad sobre la lista de direcciones IP bloqueadas (no se bloquea una dirección en ambas listas).

- La lista de direcciones IP compatibles y la lista de direcciones IP no compatibles admiten un máximo de 1273 entradas, donde una entrada es una sola dirección IP, un intervalo de direcciones IP o una DIRECCIÓN IP de enrutamiento de interdominios sin clases (CIDR).

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>Usar el Centro de seguridad & cumplimiento para modificar la directiva de filtro de conexión predeterminada

1. En el Centro de seguridad & cumplimiento y vaya a Directiva **contra** correo no deseado de administración \>  \> **de amenazas.**

2. En la página **Configuración contra correo no** deseado, expanda Directiva de filtro de conexión haciendo clic en el icono Expandir y, a continuación, haga clic en Editar  ![ ](../../media/scc-expand-icon.png) **directiva.**

3. En el **menú** desplegable Predeterminado que aparece, configure cualquiera de las siguientes opciones:

   - **Descripción:** escriba un texto descriptivo opcional.

   - **Lista de direcciones IP permitidos:** haga clic **en Editar**. En el **control desplegable Lista** de direcciones IP permitidos  que aparece, escriba una dirección IPV4 en el cuadro Dirección o intervalo de direcciones con la siguiente sintaxis:

     - IP única: por ejemplo, 192.168.1.1.

     - Intervalo IP: por ejemplo, 192.168.0.1-192.168.0.254.

     - IP CIDR: por ejemplo, 192.168.0.1/25. Los valores válidos de máscara de red son de /24 a /32. Para omitir el filtrado de correo no deseado para los valores de máscara IP CIDR de /1 a /23, vea la sección Omitir filtrado de correo no deseado para una [DIRECCIÓN IP CIDR](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) fuera de la sección de intervalo disponible más adelante en este artículo.

     Para agregar la dirección IP o el intervalo de direcciones, haga clic **en Agregar** ![ ](../../media/ITPro-EAC-AddIcon.png) icono. Para quitar una entrada, seleccione la entrada en **Dirección IP permitida** y, a continuación, haga clic en  ![ ](../../media/scc-remove-icon.png) Quitar. Cuando haya terminado, haga clic en **Guardar**.

   - **Lista de direcciones IP bloques:** haga clic **en Editar**. En el control desplegable Lista de direcciones **IP** no válidas que aparece, escriba una sola IP, intervalo IP o CIDR en el cuadro Dirección o intervalo de direcciones, tal como se describió anteriormente en la configuración lista de direcciones **IP** permitidos. 

     Para agregar la dirección IP o el intervalo de direcciones, haga clic **en Agregar** ![ ](../../media/ITPro-EAC-AddIcon.png) icono. Para quitar una entrada, seleccione la entrada en **Dirección IP bloqueada** y, a continuación, haga clic en  ![ ](../../media/scc-remove-icon.png) Quitar. Cuando haya terminado, haga clic en **Guardar**.

   - **Activar lista segura:** habilite o deshabilite el uso de la lista segura para identificar remitentes conocidos y buenos que omitirán el filtrado de correo no deseado.

4. Cuando haya terminado, haga clic en **Guardar**.

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>Usar el Centro de seguridad & cumplimiento para ver la directiva de filtro de conexión predeterminada

1. En el Centro de seguridad & cumplimiento y vaya a Directiva **contra** correo no deseado de administración \>  \> **de amenazas.**

2. En la **página Configuración contra correo no** deseado, haga clic en la lista desplegable junto a la directiva predeterminada denominada Directiva de filtro de **conexión.**

3. La configuración de directiva se muestra en la lista desplegable que se abre.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Usar Exchange Online PowerShell o EOP PowerShell independiente para modificar la directiva de filtro de conexión predeterminada

Utilice la sintaxis siguiente:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Notas**:

- Los valores válidos de la dirección IP o del intervalo de direcciones son:

  - IP única: por ejemplo, 192.168.1.1.

  - Intervalo IP: por ejemplo, 192.168.0.1-192.168.0.254.

  - IP CIDR: por ejemplo, 192.168.0.1/25. Los valores válidos de máscara de red son de /24 a /32.

- Para *sobrescribir* las entradas existentes con los valores especificados, use la siguiente sintaxis: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` .

- Para *agregar o quitar direcciones* IP o intervalos de direcciones sin que ello afecte a otras entradas existentes, use la siguiente sintaxis: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` .

- Para vaciar la lista de direcciones IP permitidos o la lista de direcciones IP bloques, use el valor `$null` .

En este ejemplo se configura la lista de direcciones IP permitidos y la lista de direcciones IP no válidas con las direcciones IP e intervalos de direcciones especificados.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

En este ejemplo se agregan y quitan las direcciones IP e intervalos de direcciones especificados de la lista de direcciones IP permitidos.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy).

## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se completó correctamente?

Para comprobar que ha modificado correctamente la directiva de filtro de conexión predeterminada, siga uno de estos pasos:

- En el Centro de seguridad &  cumplimiento, vaya a Directiva contra correo no deseado de administración de amenazas y haga clic en la lista desplegable situada junto a Directiva de filtro de conexión \>  \>  \> **(siempre** ACTIVA) y compruebe la configuración.

- En Exchange Online PowerShell o en EOP PowerShell independiente, ejecute el siguiente comando y compruebe la configuración:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Enviar un mensaje de prueba desde una entrada en la lista de direcciones IP permitidos.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Consideraciones adicionales para la lista de direcciones IP permitidos

En las secciones siguientes se identifican los elementos adicionales que debe conocer al configurar la lista de direcciones IP permitidos.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Omitir el filtrado de correo no deseado para una DIRECCIÓN IP CIDR fuera del intervalo disponible

Como se ha descrito anteriormente en este artículo, solo puede usar una DIRECCIÓN IP CIDR con la máscara de red de /24 a /32 en la lista de direcciones IP permitidos. Para omitir el filtrado de correo no deseado en mensajes de servidores de correo electrónico de origen del intervalo de /1 a /23, debe usar reglas de flujo de correo de Exchange (también conocidas como reglas de transporte). Sin embargo, le recomendamos que no lo haga si es posible, ya que los mensajes se bloquearán si una dirección IP del intervalo IP CIDR de /1 a /23 aparece en cualquiera de las listas de bloqueados de propiedad de Microsoft o de terceros.

Ahora que conoce perfectamente los posibles problemas, puede crear una regla de flujo de correo con la siguiente configuración (como mínimo) para asegurarse de que los mensajes de estas direcciones IP omitirán el filtrado de correo no deseado:

- Condición de **regla:** aplique esta regla si la dirección IP del remitente se encuentra en cualquiera de estos intervalos o coincide exactamente (escriba su IP CIDR con una máscara de red \>  \>  \> de /1 a /23).

- Acción de regla: **modificar las propiedades del mensaje** Establecer el nivel de confianza contra correo no deseado \> **(SCL) Omitir** el filtrado de correo no \> **deseado.**

Puede auditar la regla, probarla, activarla durante un período de tiempo específico y otras selecciones. Recomendamos probar la regla durante un tiempo antes de aplicarla. Para obtener más información, vea [Administrar reglas de flujo de correo en Exchange Online.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Omitir el filtrado de correo no deseado en dominios de correo electrónico selectivo del mismo origen

Normalmente, agregar una dirección IP o un intervalo de direcciones a la lista de direcciones IP permitidos significa que confía en todos los mensajes entrantes de ese origen de correo electrónico. Pero, ¿qué ocurre si ese origen envía correo electrónico desde varios dominios y desea omitir el filtrado de correo no deseado para algunos de esos dominios, pero no para otros? No puede usar la lista de direcciones IP permitidos solo para ello, pero puede usar la lista de direcciones IP permitidos en combinación con una regla de flujo de correo.

Por ejemplo, el servidor de correo electrónico de origen 192.168.1.25 envía correo electrónico desde los dominios contoso.com, fabrikam.com y tailspintoys.com, pero solo desea omitir el filtrado de correo no deseado para los mensajes de remitentes de fabrikam.com. Para ello, siga estos pasos:

1. Agregue 192.168.1.25 a la lista de direcciones IP permitidos.

2. Configure una regla de flujo de correo con las siguientes opciones (como mínimo):

   - Condición de **regla:** aplique esta regla si la dirección IP del remitente se encuentra en cualquiera de estos intervalos o coincide exactamente con \>  \> 192.168.1.25 (la misma dirección IP o intervalo de direcciones que agregó a la lista de direcciones IP **permitidos** en el paso \> anterior).

   - Acción de regla: **modificar las propiedades del mensaje** Establecer el nivel de confianza contra correo no deseado \> **(SCL)** \> **0**.

   - Excepción de regla: **el dominio** del remitente fabrikam.com (solo el dominio o dominios que desea omitir el filtrado \>  \> de correo no deseado).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Escenarios en los que los mensajes procedentes de orígenes de la lista de direcciones IP permitidos se siguen filtrando

Los mensajes de un servidor de correo electrónico de la lista de direcciones IP permitidos siguen estando sujetos al filtrado de correo no deseado en los siguientes escenarios:

- También se configura una dirección IP en la lista de direcciones IP  permitidos en un conector entrante local basado en IP en cualquier inquilino de Microsoft 365 (vamos a llamar a este inquilino **A)** y el inquilino A y el servidor EOP que primero encuentra el mensaje se encuentran en el mismo bosque de *Active* Directory en los centros de datos de Microsoft. En este escenario, **IPV:CAL**  se agrega a los encabezados de mensajes contra correo no deseado del mensaje [(lo](anti-spam-message-headers.md) que indica que el mensaje omitió el filtrado de correo no deseado), pero el mensaje sigue sujeto al filtrado de correo no deseado.

- El inquilino que contiene la lista de direcciones IP permitidos y el servidor de EOP que encuentra por primera vez el mensaje se encuentran en diferentes bosques de *Active* Directory en los centros de datos de Microsoft. En este escenario, **IPV:CAL** *no* se agrega a los encabezados del mensaje, por lo que el mensaje sigue sujeto al filtrado de correo no deseado.

Si encuentra cualquiera de estos escenarios, puede crear una regla de flujo de correo con la siguiente configuración (como mínimo) para asegurarse de que los mensajes de las direcciones IP problemáticas omitirán el filtrado de correo no deseado:

- Condición de regla: **aplique esta regla** si la dirección IP del remitente se encuentra en cualquiera de estos intervalos o coincide exactamente \>  \>  \> (su dirección IP o direcciones).

- Acción de regla: **modificar las propiedades del mensaje** Establecer el nivel de confianza contra correo no deseado \> **(SCL) Omitir** el filtrado de correo no \> **deseado.**

## <a name="new-to-microsoft-365"></a>¿Es nuevo en Microsoft 365?

****

![¿El icono corto de LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Nuevo en Microsoft 365?** Descubra cursos de vídeo gratuitos para administradores de **Microsoft 365** y profesionales de TI, que LinkedIn Learning le ofrece.
