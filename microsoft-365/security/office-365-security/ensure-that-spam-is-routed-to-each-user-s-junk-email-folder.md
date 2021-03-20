---
title: Configurar EOP para correo no deseado en entornos híbridos
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a enrutar el correo no deseado a las carpetas de correo no deseado del usuario en un entorno híbrido de Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae6ee551d04b242891c9638d6d99d79240480d27
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910863"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>Configurar EOP independiente para entregar correo no deseado a la carpeta correo no deseado en entornos híbridos

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
-  [Exchange Online Protection independiente](exchange-online-protection-overview.md)

> [!IMPORTANT]
> Este tema es solo para clientes independientes de EOP en entornos híbridos. Este tema no se aplica a los clientes de Microsoft 365 con buzones de Exchange Online.

Si es un cliente independiente de Exchange Online Protection (EOP) en un entorno híbrido, debe configurar su organización de Exchange local para reconocer y traducir los veredictos de filtrado de correo no deseado de EOP, de modo que la regla de correo no deseado del buzón local pueda mover los mensajes a la carpeta correo no deseado.

En concreto, debe crear reglas de flujo de correo (también conocidas como reglas de transporte) en su organización de Exchange local con condiciones que encuentren mensajes con cualquiera de los siguientes encabezados y valores de correo no deseado de EOP, y acciones que establezcan el nivel de confianza de correo no deseado (SCL) de esos mensajes en 6:

- `X-Forefront-Antispam-Report: SFV:SPM` (mensaje marcado como correo no deseado por el filtrado de correo no deseado)

- `X-Forefront-Antispam-Report: SFV:SKS` (mensaje marcado como correo no deseado por las reglas de flujo de correo en EOP antes del filtrado de correo no deseado)

- `X-Forefront-Antispam-Report: SFV:SKB` (Mensaje marcado como correo no deseado por el filtrado de correo no deseado debido a que la dirección de correo electrónico o el dominio de correo electrónico del remitente están en la lista de remitentes bloqueados o en la lista de dominios bloqueados en EOP)

Para obtener más información acerca de estos valores de encabezado, vea [Encabezados de mensaje contra correo no deseado](anti-spam-message-headers.md).

En este tema se describe cómo crear estas reglas de flujo de correo en el Centro de administración de Exchange (EAC) y en el Shell de administración de Exchange (Exchange PowerShell) en la organización local de Exchange.

> [!TIP]
> En lugar de entregar los mensajes a la carpeta correo no deseado del usuario local, puede configurar directivas contra correo no deseado en EOP para poner en cuarentena los mensajes de correo no deseado en EOP. Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Debe tener asignados permisos en el entorno de Exchange local antes de poder realizar estos procedimientos. En concreto, debe tener  asignado el rol Reglas de transporte, que se  asigna a los roles Administración de la **organización,** Administración de cumplimiento y Administración de registros de forma predeterminada.  Para obtener más información, vea [Agregar miembros a un grupo de roles](/Exchange/permissions/role-group-members#add-members-to-a-role-group).

- Si y cuando se entrega un mensaje a la carpeta correo no deseado de una organización de Exchange local, se controla mediante una combinación de la siguiente configuración:

  - Valor _del parámetro SCLJunkThreshold_ en el cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) en el Shell de administración de Exchange. El valor predeterminado es 4, lo que significa que un SCL de 5 o superior debe entregar el mensaje a la carpeta de correo electrónico no deseado del usuario.

  - Valor _del parámetro SCLJunkThreshold_ en el cmdlet [Set-Mailbox](/powershell/module/exchange/set-mailbox) en el Shell de administración de Exchange. El valor predeterminado está en blanco ($null), lo que significa que se usa la configuración de la organización.

  Para obtener más información, vea Umbrales de nivel de confianza de correo no deseado [(SCL) de Exchange.](/Exchange/antispam-and-antimalware/antispam-protection/scl)

  - Si la regla de correo no deseado está habilitada en el buzón (el valor del parámetro _Enabled_ $true en el cmdlet [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration) en el Shell de administración de Exchange). Es la regla de correo no deseado la que mueve el mensaje a la carpeta correo no deseado después de la entrega. De forma predeterminada, la regla de correo no deseado está habilitada en los buzones. Para obtener más información, vea [Configure Exchange antispam settings on mailboxes](/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).

- Para abrir el EAC en un Exchange Server, vea Centro de [administración de Exchange en Exchange Server](/Exchange/architecture/client-access/exchange-admin-center). Para abrir el Shell de administración de Exchange, consulte [Abrir el Shell de administración de Exchange](/powershell/exchange/open-the-exchange-management-shell).

- Para obtener más información acerca de las reglas de flujo de correo en Exchange local, vea los siguientes temas:

  - [Reglas de flujo de correo en Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Condiciones y excepciones de reglas de flujo de correo (predicados) en Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Acciones de regla de flujo de correo en Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Usar el EAC para crear reglas de flujo de correo que establezcan el SCL de mensajes de correo no deseado de EOP

1. En el EAC, vaya a **Flujo de correo** \> **Reglas**.

2. Haga **clic en** Agregar icono Agregar y seleccione Crear una nueva ![ ](../../media/ITPro-EAC-AddIcon.png) **regla** en la lista desplegable que aparece.

3. En la ventana **Nueva regla** que se abre, configure las siguientes opciones:

   - **Nombre:** escriba un nombre descriptivo único para la regla. Por ejemplo:

     - EOP SFV:SPM a SCL 6

     - EOP SFV:SKS a SCL 6

     - EOP SFV:SKB a SCL 6

   - Haga clic en **Más opciones**.

   - **Aplique esta regla si**: Select **A message header** includes any of \> **these words**.

     En el **encabezado de texto Entrar incluye Escribir oración** de palabras que aparece, siga estos pasos:

     - Haga **clic en Escribir texto**. En el **cuadro de diálogo** Especificar nombre de encabezado que aparece, escriba **X-Forefront-Antispam-Report** y, a continuación, haga clic en **Aceptar**.

     - Haga  **clic en Escribir palabras**. En  el cuadro de diálogo Especificar palabras o frases que aparece, escriba uno de los valores de encabezado de correo  no deseado de EOP (**SFV:SPM**, **SFV:SKS** o **SFV:SKB**), haga clic en Agregar icono y, a continuación, haga clic en ![ ](../../media/ITPro-EAC-AddIcon.png) **Aceptar**.

   - **Haga lo siguiente:** Seleccione **Modificar las propiedades del mensaje** Establecer el nivel de confianza de correo no deseado \> **(SCL).**

     En el cuadro de diálogo Especificar **SCL** que aparece, seleccione **6** (el valor predeterminado es **5**).

   Cuando haya terminado, haga clic en **Guardar**

Repita estos pasos para los valores de veredicto de correo no deseado de EOP restantes (**SFV:SPM**, **SFV:SKS** o **SFV:SKB**).

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Usar el Shell de administración de Exchange para crear reglas de flujo de correo que establezcan el SCL de los mensajes de correo no deseado de EOP

Use la siguiente sintaxis para crear las tres reglas de flujo de correo:

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

Por ejemplo:

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

Para obtener información detallada acerca de la sintaxis y los parámetros, vea [New-TransportRule](/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se completó correctamente?

Para comprobar que ha configurado correctamente EOP independiente para entregar correo no deseado a la carpeta correo no deseado en un entorno híbrido, siga estos pasos:

- En el EAC, vaya a **Flujo** de correo Reglas , seleccione la regla y, a continuación, haga clic \>  **en Editar** icono Editar para comprobar ![ la ](../../media/ITPro-EAC-EditIcon.png) configuración.

- En el Shell de administración de Exchange, reemplace por el nombre de la regla de flujo de correo y rul el \<RuleName\> siguiente comando para comprobar la configuración:

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- En un sistema de correo electrónico externo que no analiza los mensajes salientes en busca de **correo** no deseado, envíe un mensaje de prueba genérica para correo electrónico masivo no solicitado (GTUBE) a un destinatario afectado y confirme que se ha entregado a su carpeta correo no deseado. Un mensaje GTUBE es similar al archivo de texto del European Institute of Computer virus Research (EICAR) para probar la configuración de malware.

  Para enviar un mensaje de GTUBE, incluya el siguiente texto en el cuerpo de un mensaje de correo electrónico en una sola línea, sin espacios ni saltos de línea:

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```