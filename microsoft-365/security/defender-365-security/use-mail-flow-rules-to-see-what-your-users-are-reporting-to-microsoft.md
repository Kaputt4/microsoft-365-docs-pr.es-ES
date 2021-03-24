---
title: Usar reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a usar reglas de flujo de correo (también conocidas como reglas de transporte) para recibir copias de los mensajes que los usuarios informan a Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e6428a228ae64562f0b529f6aa90ddc3be46fdc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069936"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Usar reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 con buzones en Exchange Online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, hay varias maneras de que los usuarios informen mensajes a Microsoft para su análisis, tal como se describe en Notificar mensajes y archivos a [Microsoft](report-junk-email-messages-to-microsoft.md).

Puede crear una regla de flujo de correo (también conocida como regla de transporte) que busca los mensajes que los usuarios notifican a Microsoft y puede configurar destinatarios CCO para que reciban copias de estos mensajes notificados.

Puede crear la regla de flujo de correo en el Centro de administración de Exchange (EAC) y PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; PowerShell EOP independiente para organizaciones sin buzones de Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Debe tener asignados permisos en Exchange Online o Exchange Online Protection antes de poder realizar los procedimientos descritos en este artículo. En concreto, necesita el rol **Reglas** de transporte, que se asigna a los grupos de roles **Administración** de la **organización,** Administración de cumplimiento (administradores globales) y Administración **de** registros de forma predeterminada.

  Para obtener más información, consulte los siguientes temas:

  - [Permisos de Exchange Online](/exchange/permissions-exo/permissions-exo)
  - [Permisos en EOP independiente](feature-permissions-in-eop.md)
  - [Usar el EAC modificar la lista de miembros en grupos de roles](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Para abrir el EAC en Exchange Online, vea [Centro de administración de Exchange en Exchange Online](/Exchange/exchange-admin-center). Para abrir el EAC en EOP independiente, vea Centro de [administración de Exchange en EOP independiente.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Para obtener más información acerca de las reglas de flujo de correo en Exchange Online y EOP independiente, consulte los temas siguientes:
  - [Reglas de flujo de correo (reglas de transporte) en Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [Condiciones y excepciones de reglas de flujo de correo (predicados) en Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [Acciones de regla de flujo de correo en Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Usar el EAC para crear una regla de flujo de correo para recibir copias de mensajes notificados

1. En el EAC, vaya a **Flujo de correo** \> **Reglas**.

2. Haga **clic en** Agregar icono Agregar ![ ](../../media/ITPro-EAC-AddIcon.png) **y, a continuación, seleccione Crear una nueva regla.**

3. En la ventana **Nueva regla** que se abre, configure las siguientes opciones:

   - **Nombre:** escriba un nombre descriptivo único para la regla. Por ejemplo, Mensajes CCO notificados a Microsoft.

   - Haga clic en **Más opciones**.

   - **Aplique** esta regla si : **Seleccione** La dirección del destinatario incluye cualquiera de estas palabras: en el cuadro de diálogo Especificar palabras o frases que aparece, escriba uno de los siguientes valores, haga clic en Agregar icono y repita hasta que haya escrito todos los \>    ![ ](../../media/ITPro-EAC-AddIcon.png) valores.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     Para editar una entrada, selecciónelo y haga clic **en Editar** icono ![ Editar ](../../media/ITPro-EAC-EditIcon.png) . Para quitar una entrada, selecciónelo y haga clic **en Quitar** icono ![ Quitar ](../../media/ITPro-EAC-DeleteIcon.png) .

     Cuando haya terminado, haga clic en **Aceptar**.

   - **Haga lo siguiente:** Seleccione **Agregar destinatarios** \> **al cuadro CCO**. En el cuadro de diálogo que aparece, busque y seleccione los destinatarios que desea agregar. Cuando haya terminado, haga clic en **Aceptar**.

4. Puede realizar selecciones adicionales para auditar la regla, probarla, activarla durante un período de tiempo específico y otras opciones de configuración. Se recomienda probar la regla antes de aplicarla.

5. Cuando haya terminado, haga clic en **Guardar**.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Usar PowerShell para crear una regla de flujo de correo para recibir copias de mensajes notificados

En este ejemplo se crea una nueva regla de flujo de correo denominada Mensajes CCO notificados a Microsoft que busca mensajes de correo electrónico notificados a Microsoft mediante los métodos descritos en este artículo y agrega los usuarios laura@contoso.com y julia@contoso.com como destinatarios CCO.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Para obtener información detallada acerca de la sintaxis y los parámetros, vea [New-TransportRule](/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se completó correctamente?

Para comprobar que ha configurado una regla de flujo de correo para recibir copias de los mensajes notificados, siga estos pasos:

- En el EAC, vaya a **Flujo** de correo Reglas seleccione la regla haga clic en \>  \> \> **Editar** icono Editar y compruebe ![ la ](../../media/ITPro-EAC-EditIcon.png) configuración.

- En PowerShell, ejecute el siguiente comando para comprobar la configuración:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Enviar mensajes de prueba a una de las direcciones de correo electrónico de informes y comprobar los resultados.