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
ms.openlocfilehash: 416fbd73d8412cf8697577df19f2fd2893b4ce96
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878825"
---
# <a name="configure-connection-filtering"></a>Configurar el filtrado de la conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


Si es un cliente de Microsoft 365 con buzones en Exchange Online o un cliente independiente de Exchange Online Protection (EOP) sin buzones de Exchange Online, use el filtrado de conexiones en EOP (específicamente, la directiva de filtro de conexión predeterminada) para identificar los servidores de correo electrónico de origen buenos o malos por sus direcciones IP. Los componentes clave de la directiva de filtro de conexión predeterminada son:

- **Lista de direcciones IP permitidos:** omitir el filtrado de correo no deseado para todos los mensajes entrantes de los servidores de correo electrónico de origen que especifique por dirección IP o intervalo de direcciones IP. Para ver escenarios en los que el filtrado de correo no deseado todavía puede producirse en los mensajes de estos orígenes, vea la sección [Escenarios](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) en los que los mensajes de orígenes de la lista de direcciones IP permitidos aún se filtran más adelante en este artículo. Para obtener más información acerca de cómo la lista de direcciones IP permitidos debe caber en la estrategia general de remitentes seguros, vea [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).

- **Lista de direcciones IP bloqueados:** bloquee todos los mensajes entrantes de los servidores de correo electrónico de origen que especifique por dirección IP o intervalo de direcciones IP. Los mensajes entrantes se rechazan, no se marcan como correo no deseado y no se produce ningún filtrado adicional. Para obtener más información acerca de cómo la lista de direcciones IP bloqueadas debe caber en la estrategia general de remitentes bloqueados, vea [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).

- **Caja fuerte:** la *lista segura* es una lista de permitidos dinámica en el centro de datos de Microsoft que no requiere ninguna configuración del cliente. Microsoft identifica estos orígenes de correo electrónico de confianza de las suscripciones a varias listas de terceros. Habilitar o deshabilitar el uso de la lista segura; no puede configurar los servidores de correo electrónico de origen en la lista segura. El filtrado de correo no deseado se omite en los mensajes entrantes de los servidores de correo electrónico de la lista segura.

En este artículo se describe cómo configurar la directiva de filtro de conexión predeterminada en el portal de Microsoft 365 Microsoft 365 Defender o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones Exchange Online). Para obtener más información acerca de cómo EOP usa el filtrado de conexiones forma parte de la configuración general contra correo no deseado de su [organización,](anti-spam-protection.md)vea Protección contra correo no deseado .

> [!NOTE]
> La lista de direcciones IP permitidos, la lista segura y la lista de direcciones IP bloqueados son una parte de la estrategia general para permitir o bloquear el correo electrónico en su organización. Para obtener más información, vea [Crear listas de remitentes seguros](create-safe-sender-lists-in-office-365.md) y Crear listas de [remitentes bloqueados.](create-block-sender-lists-in-office-365.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Abra el portal Microsoft 365 Defender en <https://security.microsoft.com> . Para ir directamente a la página **Directivas contra correo no deseado**, use <https://security.microsoft.com/antispam>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Debe tener permisos asignados en **Exchange Online** antes de poder realizar los procedimientos de este artículo:
  - Para modificar la directiva de filtro de conexión predeterminada, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.
  - Para obtener acceso de solo lectura a la directiva de filtro de conexión predeterminada, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.

  Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Notas**:

  - Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios _y_ los permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Para buscar las direcciones IP de origen de los servidores de correo electrónico (remitentes) que desea permitir o bloquear, puede comprobar el campo de encabezado IP de conexión **(CIP)** en el encabezado del mensaje. Para ver un encabezado de mensaje en varios clientes de correo electrónico, vea [Ver encabezados](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)de mensajes de Internet en Outlook .

- La lista de direcciones IP permitidos tiene prioridad sobre la lista de direcciones IP bloqueadas (no se bloquea una dirección en ambas listas).

- La lista de direcciones IP permitidos y la lista de direcciones IP bloqueados admiten un máximo de 1273 entradas, donde una entrada es una sola dirección IP, un intervalo de direcciones IP o una DIRECCIÓN IP de enrutamiento de interdominios sin clases (CIDR).

## <a name="use-the-microsoft-365-defender-portal-to-modify-the-default-connection-filter-policy"></a>Usar el portal Microsoft 365 Defender para modificar la directiva de filtro de conexión predeterminada

1. En el portal de Microsoft 365 Defender, vaya a **Correo** electrónico & directivas de colaboración & directivas de amenazas de reglas \>  \>  \>  sección Directivas contra correo \> **no deseado.**

2. En la **página Directivas contra correo** no deseado, seleccione Directiva de filtro de conexión **(Predeterminada)** de la lista haciendo clic en el nombre de la directiva.

3. En el menú desplegable de detalles de la directiva que aparece, configure cualquiera de las siguientes opciones:

   - **Sección Descripción:** haga clic **en Editar nombre y descripción.** En el control desplegable **Editar nombre y** descripción que aparece, escriba texto descriptivo opcional en el **cuadro** Descripción.

     Cuando haya terminado, haga clic en **Guardar**.

   - **Sección Filtrado de conexiones:** Haga **clic en Editar directiva de filtro de conexión.** En el menú desplegable que aparece, configure las siguientes opciones:

     - **Permitir siempre mensajes de las siguientes direcciones IP o intervalo** de direcciones: esta es la lista de direcciones IP permitidos. Haga clic en el cuadro, escriba un valor y, a continuación, presione Entrar o seleccione el valor completo que se muestra debajo del cuadro. Los valores válidos son:
       - IP única: por ejemplo, 192.168.1.1.
       - Intervalo IP: por ejemplo, 192.168.0.1-192.168.0.254.
       - IP cidr: por ejemplo, 192.168.0.1/25. Los valores válidos de máscara de subred son de /24 a /32. Para omitir el filtrado de correo no deseado para /1 a /23, vea la sección Omitir filtrado de correo no deseado para una [DIRECCIÓN IP cidr](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) fuera del intervalo disponible más adelante en este artículo.

       Repita este paso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Icono de quitar](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

     Para agregar la dirección IP o el intervalo de direcciones, haga clic en el cuadro y escriba itclick **Add** ![ Add Icon ](../../media/ITPro-EAC-AddIcon.png) . Para quitar una entrada, seleccione la entrada en **Dirección IP permitida** y, a continuación, haga clic en **Quitar** ![ quitar ](../../media/scc-remove-icon.png) . Cuando haya terminado, haga clic en **Guardar**.

   - **Siempre bloquee los mensajes de las siguientes direcciones IP o intervalo de direcciones:** se trata de la lista de direcciones IP bloqueados. Escriba una sola IP, intervalo IP o IP CIDR en el cuadro tal como se describió anteriormente en la configuración Permitir siempre mensajes de las siguientes direcciones IP o intervalo **de direcciones.**

   - **Activar lista segura:** habilite o deshabilite el uso de la lista segura para identificar remitentes conocidos y buenos que omitirán el filtrado de correo no deseado. Para usar la lista segura, active la casilla.

   Cuando haya terminado, haga clic en **Guardar**.

4. De nuevo en el control flotante de detalles de la directiva, haga clic en **Cerrar**.

## <a name="use-the-microsoft-365-defender-portal-to-view-the-default-connection-filter-policy"></a>Usar el portal Microsoft 365 Defender para ver la directiva de filtro de conexión predeterminada

1. En el portal de Microsoft 365 Defender, vaya a **Correo** electrónico & directivas de colaboración & directivas de amenazas de reglas \>  \>  \>  sección Directivas contra correo \> **no deseado.**

2. En la **página Directivas contra correo** no deseado, se muestran las siguientes propiedades en la lista de directivas:

   - **Nombre:** este valor es **La directiva de filtro de conexión (Valor predeterminado)** para la directiva de filtro de conexión predeterminada.
   - **Estado:** este valor está **siempre en la** directiva de filtro de conexión predeterminada.
   - **Prioridad:** este valor es **el más bajo para** la directiva de filtro de conexión predeterminada.
   - **Tipo:** este valor está en blanco para la directiva de filtro de conexión predeterminada.

3. Al seleccionar la directiva de filtro de conexión predeterminada, la configuración de directiva se muestra en un menú desplegable.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Usar Exchange Online PowerShell o PowerShell de EOP independiente para modificar la directiva de filtro de conexión predeterminada

Utilice la siguiente sintaxis:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Notas**:

- Los valores válidos de dirección IP o intervalo de direcciones son:
  - IP única: por ejemplo, 192.168.1.1.
  - Intervalo IP: por ejemplo, 192.168.0.1-192.168.0.254.
  - IP cidr: por ejemplo, 192.168.0.1/25. Los valores válidos de máscara de red son de /24 a /32.
- Para *sobrescribir* las entradas existentes con los valores especificados, use la siguiente sintaxis: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` .
- Para *agregar o quitar direcciones* IP o intervalos de direcciones sin afectar a otras entradas existentes, use la sintaxis siguiente: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` .
- Para vaciar la lista de direcciones IP permitidos o la lista de direcciones IP bloqueados, use el valor `$null` .

En este ejemplo se configuran la lista de direcciones IP permitidos y la lista de direcciones IP bloqueadas con las direcciones IP y los intervalos de direcciones especificados.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

En este ejemplo se agregan y quitan las direcciones IP especificadas y los intervalos de direcciones de la lista de direcciones IP permitidos.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-HostedConnectionFilterPolicy](/powershell/module/exchange/set-hostedconnectionfilterpolicy).

## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se completó correctamente?

Para comprobar que ha modificado correctamente la directiva de filtro de conexión predeterminada, siga estos pasos:

- En el portal de Microsoft 365 Defender, vaya **a** Correo electrónico & Directivas de colaboración & Directivas de amenazas de reglas sección Directivas contra correo no deseado seleccione Directiva de filtro de conexión \>  \>  \>  \>  \> **(predeterminada)** de la lista haciendo clic en el nombre de la directiva y compruebe la configuración.

- En Exchange Online PowerShell o PowerShell independiente de EOP, ejecute el siguiente comando y compruebe la configuración:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Enviar un mensaje de prueba desde una entrada en la lista de direcciones IP permitidos.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Consideraciones adicionales para la lista de direcciones IP permitidos

En las secciones siguientes se identifican los elementos adicionales que debe conocer al configurar la lista de direcciones IP permitidos.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Omitir el filtrado de correo no deseado para una DIRECCIÓN IP cidr fuera del intervalo disponible

Como se describió anteriormente en este artículo, solo puede usar una IP cidr con la máscara de red /24 a /32 en la lista de direcciones IP permitidos. Para omitir el filtrado de correo no deseado en los mensajes de los servidores de correo electrónico de origen en el intervalo de /1 a /23, debe usar Exchange reglas de flujo de correo (también conocidas como reglas de transporte). Pero, le recomendamos que no haga esto si es posible, ya que los mensajes se bloquearán si una dirección IP del intervalo IP de CIDR de /1 a /23 aparece en cualquiera de las listas de bloqueo de terceros o propietarias de Microsoft.

Ahora que conoce los posibles problemas, puede crear una regla de flujo de correo con la siguiente configuración (como mínimo) para asegurarse de que los mensajes de estas direcciones IP omitirán el filtrado de correo no deseado:

- Condición de regla: **aplique** esta regla si la dirección IP del remitente está en cualquiera de estos intervalos o coincide exactamente (escriba su IP cidr con una máscara de red \>  \>  \> de /1 a /23).
- Acción de regla: **modificar las propiedades del mensaje** Establecer el nivel de confianza de correo no deseado \> **(SCL) Omitir** filtrado de correo no \> **deseado**.

Puede auditar la regla, probarla, activarla durante un período de tiempo específico y otras selecciones. Recomendamos probar la regla durante un tiempo antes de aplicarla. Para obtener más información, vea [Manage mail flow rules in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Omitir el filtrado de correo no deseado en dominios de correo electrónico selectivo del mismo origen

Normalmente, agregar una dirección IP o un intervalo de direcciones a la lista de direcciones IP permitidos significa que confía en todos los mensajes entrantes de ese origen de correo electrónico. Pero, ¿qué sucede si ese origen envía correo electrónico desde varios dominios y desea omitir el filtrado de correo no deseado para algunos de esos dominios, pero no para otros? No puede usar la lista de direcciones IP permitidos solo para ello, pero puede usar la lista de direcciones IP permitidos en combinación con una regla de flujo de correo.

Por ejemplo, el servidor de correo electrónico de origen 192.168.1.25 envía correo electrónico de los dominios contoso.com, fabrikam.com y tailspintoys.com, pero solo desea omitir el filtrado de correo no deseado para mensajes de remitentes en fabrikam.com. Para ello, siga estos pasos:

1. Agregue 192.168.1.25 a la lista de direcciones IP permitidos.

2. Configure una regla de flujo de correo con las siguientes opciones (como mínimo):
   - Condición de **regla:** aplique esta regla si la dirección IP del remitente está en cualquiera de estos intervalos o coincide exactamente con \>  \>  192.168.1.25 (la misma dirección IP o intervalo de direcciones que agregó a la lista de direcciones IP permitidos en el \> paso anterior).
   - Acción de regla: **modificar las propiedades del mensaje** Establecer el nivel de confianza de correo no deseado \> **(SCL)** \> **0**.
   - Excepción de regla: **el dominio** del remitente fabrikam.com (solo el dominio o dominios que \>  \> desea omitir el filtrado de correo no deseado).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Escenarios en los que los mensajes de orígenes de la lista de direcciones IP permitidos se siguen filtrando

Los mensajes de un servidor de correo electrónico de la lista de direcciones IP permitidos siguen estando sujetos al filtrado de correo no deseado en los siguientes escenarios:

- Una dirección IP en la lista de direcciones IP permitidos también  se configura en un conector de entrada local basado en IP en cualquier inquilino de Microsoft 365 (vamos a llamar a este inquilino **A)** y el inquilino A y el servidor EOP que encuentra por primera vez el mensaje que ambos se encuentran en el mismo bosque de *Active* Directory en los centros de datos de Microsoft. En este escenario, **IPV:CAL**  se agrega a los encabezados de mensajes contra correo no deseado del mensaje [(lo](anti-spam-message-headers.md) que indica el filtrado de correo no deseado omitido del mensaje), pero el mensaje aún está sujeto al filtrado de correo no deseado.

- El espacio empresarial que contiene la lista de direcciones IP permitidos y el servidor EOP que encuentra por primera vez el mensaje se encuentran en bosques de *Active* Directory diferentes en los centros de datos de Microsoft. En este escenario, **IPV:CAL** *no* se agrega a los encabezados de mensaje, por lo que el mensaje aún está sujeto al filtrado de correo no deseado.

Si encuentra cualquiera de estos escenarios, puede crear una regla de flujo de correo con la siguiente configuración (como mínimo) para asegurarse de que los mensajes de las direcciones IP problemáticas omitirán el filtrado de correo no deseado:

- Condición de regla: **aplique esta regla si** la dirección IP del remitente está en cualquiera de estos intervalos o coincide \>  \> **exactamente** \> (su dirección IP o direcciones).
- Acción de regla: **modificar las propiedades del mensaje** Establecer el nivel de confianza de correo no deseado \> **(SCL) Omitir** filtrado de correo no \> **deseado**.

## <a name="new-to-microsoft-365"></a>¿Es nuevo Microsoft 365?

****

![El icono corto de LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?** Descubra cursos de vídeo gratuitos **para Microsoft 365 administradores** y profesionales de TI, que LinkedIn Learning le ha presentado.
