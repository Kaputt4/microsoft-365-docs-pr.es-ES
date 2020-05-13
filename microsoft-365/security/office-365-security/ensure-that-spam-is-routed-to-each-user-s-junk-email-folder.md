---
title: Configurar EOP a correo no deseado en entornos híbridos
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre cómo enrutar correo no deseado a las carpetas de correo no deseado del usuario en un entorno híbrido de protección de Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a5b4d16c864b25c4d47910f0dd69f0ed3e71a0de
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209480"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>Configurar un EOP independiente para enviar correo no deseado a la carpeta de correo no deseado en entornos híbridos

> [!IMPORTANT]
> Este tema es solo para clientes de EOP independientes en entornos híbridos. Este tema no se aplica a los clientes de Microsoft 365 con buzones de correo de Exchange Online.

Si es cliente independiente de Exchange Online Protection (EOP) en un entorno híbrido, debe configurar la organización de Exchange local para que reconozca y traduzca los veredictos del filtrado de correo no deseado de EOP, por lo que la regla de correo no deseado del buzón local puede mover mensajes a la carpeta de correo electrónico no deseado.

En concreto, debe crear reglas de flujo de correo (también conocidas como reglas de transporte) en su organización de Exchange local con condiciones que encuentren mensajes con cualquiera de los siguientes valores y encabezados de correo no deseado de EOP, así como acciones que establezcan el nivel de confianza contra correo no deseado (SCL) de esos mensajes en 6:

- `X-Forefront-Antispam-Report: SFV:SPM`(mensaje marcado como correo no deseado por el filtrado de correo no deseado)

- `X-Forefront-Antispam-Report: SFV:SKS`(mensaje marcado como correo no deseado por reglas de flujo de correo en EOP antes del filtrado de correo no deseado)

- `X-Forefront-Antispam-Report: SFV:SKB`(mensaje marcado como correo no deseado por el filtrado de correo no deseado debido a la dirección de correo electrónico o al dominio de correo electrónico del remitente en la lista de remitentes bloqueados o en la lista de dominios bloqueados en EOP)

Para obtener más información acerca de estos valores de encabezado, consulte [anti-spam Message headers](anti-spam-message-headers.md).

En este tema se describe cómo crear estas reglas de flujo de correo en el centro de administración de Exchange (EAC) y en el shell de administración de Exchange (Exchange PowerShell) en la organización de Exchange local.

> [!TIP]
> En lugar de entregar los mensajes a la carpeta de correo no deseado del usuario local, puede configurar directivas contra correo no deseado en EOP para poner en cuarentena los mensajes de correo no deseado en EOP. Para obtener más información, vea [configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Debe tener asignados permisos en el entorno local de Exchange para poder realizar estos procedimientos. En concreto, debe tener asignado el rol **reglas de transporte** , que se asigna a las **funciones administración**de la organización, **Administración del cumplimiento**y administración de **registros** de forma predeterminada. Para obtener más información, vea [Agregar miembros a un grupo de funciones](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).

- Si un mensaje se entrega a la carpeta de correo no deseado en una organización de Exchange local y se controla mediante una combinación de las siguientes opciones de configuración:

  - El valor del parámetro _SCLJunkThreshold_ en el cmdlet [set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) del shell de administración de Exchange. El valor predeterminado es 4, lo que significa que un SCL de 5 o superior debe entregar el mensaje en la carpeta de correo no deseado del usuario.

  - El valor del parámetro _SCLJunkThreshold_ en el cmdlet [set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) en el shell de administración de Exchange. El valor predeterminado está en blanco ($null), lo que significa que se usa la configuración de la organización.

  Para obtener información detallada, consulte [umbrales de nivel de confianza contra correo no deseado (SCL) de Exchange](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).

  - Si la regla de correo no deseado está habilitada en el buzón (el valor del parámetro _Enabled_ se $true en el cmdlet [set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration) en el shell de administración de Exchange). Es la regla de correo no deseado que realmente mueve el mensaje a la carpeta correo electrónico no deseado después de la entrega. De forma predeterminada, la regla de correo no deseado está habilitada en los buzones. Para obtener más información, consulte [configurar las opciones de correo no deseado de Exchange en buzones](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).
  
- Para abrir el EAC en un servidor de Exchange, vea [centro de administración de Exchange en Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center). Para abrir el shell de administración de Exchange, consulte [https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) .

- Para obtener más información acerca de las reglas de flujo de correo en Exchange local, consulte los siguientes temas:

  - [Reglas de flujo de correo en Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Excepciones (predicados) y condiciones de reglas de flujo de correo en Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Acciones de las reglas de flujo de correo en Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Usar el EAC para crear reglas de flujo de correo que establezcan el SCL de los mensajes de correo no deseado de EOP

1. En el EAC, vaya a **Flujo de correo** \> **Reglas**.

2. Haga clic en **Agregar** ![ icono Agregar ](../../media/ITPro-EAC-AddIcon.png) y seleccione **crear una nueva regla** en la lista desplegable que aparece.

3. En la ventana **Nueva regla** que se abre, configure las siguientes opciones:

   - **Name**: escriba un nombre único y descriptivo para la regla. Por ejemplo:

     - EOP SFV: SPM a SCL 6

     - EOP SFV: SKS a SCL 6

     - EOP SFV: SKB a SCL 6

   - Haga clic en **Más opciones**.

   - **Aplicar esta regla si**: seleccione **un encabezado** \> **de mensaje incluye alguna de estas palabras**.

     En la frase **Escriba el encabezado de texto incluye escribir palabras** , siga estos pasos:

     - Haga clic en **escribir texto**. En el cuadro de diálogo **especificar nombre de encabezado** que aparece, escriba **X-Forefront-antispam-Report** y, a continuación, haga clic en **Aceptar**.

     - Haga clic en **escribir palabras**. En el cuadro de diálogo **especificar palabras o frases** que aparece, escriba uno de los valores de encabezado de correo no deseado de EOP (**SFV: SPM**, **SFV: SKS**o **SFV: SKB**), haga clic en **Agregar** ![ icono Agregar ](../../media/ITPro-EAC-AddIcon.png) y, a continuación, haga clic en **Aceptar**.

   - **Haga lo siguiente**: seleccione **modificar las propiedades del mensaje** \> **establecer el nivel de confianza contra correo no deseado (SCL)**.

     En el cuadro de diálogo **especificar SCL** que aparece, seleccione **6** (el valor predeterminado es **5**).

   Cuando haya terminado, haga clic en **Guardar** .

Repita estos pasos para los demás valores de veredicto de correo no deseado de EOP (**SFV: SPM**, **SFV: SKS**o **SFV: SKB**).

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Usar el shell de administración de Exchange para crear reglas de flujo de correo que establezcan el SCL de los mensajes de correo no deseado de EOP

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

Para obtener información detallada acerca de la sintaxis y los parámetros, vea [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se completó correctamente?

Para comprobar que configuró correctamente EOP independiente para entregar el correo no deseado en la carpeta de correo no deseado en un entorno híbrido, realice uno de los siguientes pasos:

- En el EAC, vaya a reglas de **flujo de correo** \> **Rules**, seleccione la regla y, a continuación, haga clic en **Editar** ![ icono ](../../media/ITPro-EAC-EditIcon.png) de edición para comprobar la configuración.

- En el shell de administración de Exchange, reemplace \< RuleName \> por el nombre de la regla de flujo de correo y regla el siguiente comando para comprobar la configuración:

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- En un sistema de correo electrónico externo **que no analiza los mensajes salientes en busca de correo no deseado**, envíe una prueba genérica de mensaje de correo electrónico masivo no solicitado (GTUBE) a un destinatario afectado y confirme que se entrega a su carpeta de correo electrónico no deseado. Un mensaje GTUBE es similar al archivo de texto del European Institute of Computer virus Research (EICAR) para probar la configuración de malware.

  Para enviar un mensaje GTUBE, incluya el siguiente texto en el cuerpo de un mensaje de correo electrónico en una sola línea, sin espacios ni saltos de línea:

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
