---
title: Configurar la Directiva antiphishing predeterminada en EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre cómo modificar las opciones de configuración contra la suplantación de identidad disponibles en la Directiva antiphishing predeterminada en las organizaciones de Office 365 con buzones de Exchange Online.
ms.openlocfilehash: 1a8527a55796910e79fbf70b824de828ca48591b
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537538"
---
# <a name="configure-the-default-anti-phishing-policy-in-eop"></a>Configurar la Directiva antiphishing predeterminada en EOP

Office 365 organizaciones con buzones de Exchange Online y organizaciones independientes de Exchange Online Protection (EOP) sin buzones de correo de Exchange Online tienen una directiva antiphishing predeterminada. Esta Directiva contiene un número limitado de características de suplantación de identidad que están habilitadas de forma predeterminada. Para obtener más información, consulte [configuración de la suplantación de identidades en directivas antiphishing](set-up-anti-phishing-policies.md#spoof-settings).

Office 365 las organizaciones con buzones de correo de Exchange online pueden modificar la Directiva antiphishing predeterminada en el centro de seguridad & cumplimiento de Office 365 o en Exchange Online PowerShell. Las organizaciones de EOP independientes sin buzones de Exchange online no pueden modificar su Directiva antiphishing predeterminada.

Para obtener información sobre cómo crear y modificar las directivas de protección contra suplantación de identidad (ATP) más avanzadas disponibles en Office 365 Advanced Threat Protection, vea [Configure ATP anti-phishing policies in office 365](configure-atp-anti-phishing-policies.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página de **contra la suplantación de identidad (phishing** ), use. <https://protection.office.com/antiphishing>

- Para conectarse a PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

- Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos. Para agregar, modificar y eliminar directivas antiphishing, debe ser miembro de los grupos de roles administración de la **organización** o **Administrador de seguridad** . Para el acceso de solo lectura a las directivas antiphishing, debe ser miembro del grupo de roles **lector de seguridad** . Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md).

- Para conocer la configuración recomendada para la Directiva antiphishing predeterminada, consulte [EOP default anti-phishing Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).

- Espere hasta 30 minutos para que se aplique la directiva actualizada.

- Para obtener información sobre la aplicación de directivas contra la suplantación de identidad (phishing) en la canalización de filtros, consulte [Order and Precedence of email Protection in Office 365](how-policies-and-protections-are-combined.md).

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>Usar el centro de seguridad & cumplimiento para modificar la Directiva contra suplantación de identidad (phishing) predeterminada

La Directiva antiphishing predeterminada se denomina Office365 ANTIPHISH predeterminada y no aparece en la lista de directivas. Para modificar la Directiva de suplantación de identidad (phishing) predeterminada, siga estos pasos:

1. En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **anti-phishing**.

2. En la página **contra la suplantación de identidad** , haga clic en **directiva predeterminada**.

3. Aparecerá la página **editar la Directiva de ANTIPHISH predeterminada de Office365** . En la sección **suplantación** , haga clic en **Editar**.

   Tenga en cuenta que esta configuración es idéntica a la configuración de suplantación que está disponible en las directivas antiphishing de ATP.

   - **Configuración del filtro de suplantación de identidad**: el valor predeterminado es **activado**y se recomienda que lo deje activado. Para desactivarla, deslice el botón de alternancia a **desactivado**. Para obtener más información, consulte [configurar inteligencia de identidades en Office 365](learn-about-spoof-intelligence.md).

     > [!NOTE]
     > No es necesario deshabilitar la protección contra la suplantación de identidad si el registro MX no apunta a Office 365; en su lugar, se habilita el filtrado mejorado para los conectores. Para obtener instrucciones, vea [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   - **Habilitar la característica de remitente sin autenticar**: agrega un signo de interrogación a la foto del remitente si el mensaje no supera las comprobaciones de autenticación de correo electrónico. Para obtener más información, consulte [configuración de la suplantación de identidades en directivas antiphishing](set-up-anti-phishing-policies.md#spoof-settings). El valor predeterminado es **Activada**. Para desactivarla, deslice el botón de alternancia a **desactivado**.

   - **Acciones**: especificar la acción que se realizará en los mensajes que no superen la inteligencia de identidad:

     **Si el correo electrónico lo envía alguien que no tiene permiso para suplantar su dominio**:

     - **Mover mensaje a las carpetas de correo no deseado de los destinatarios** (este es el valor predeterminado).
     - **Poner en cuarentena el mensaje**

   - **Revise la configuración**: en lugar de hacer clic en cada paso individual, la configuración se muestra en un resumen.

     - Puede hacer clic en **Editar** en cada sección para volver a la página correspondiente.
     - Puede activar o **desactivar** la siguiente configuración **directamente en esta** página:

       - **Habilitar la protección contra la suplantación de identidad**
       - **Habilitar la característica de remitente sin autenticar**

   Cuando haya terminado, haga clic en **Guardar** en cualquier página.

4. De nuevo en la página **Editar directiva predeterminada de Office365 ANTIPHISH** , revise la configuración y, a continuación, haga clic en **cerrar**.

## <a name="use-the-security--compliance-center-to-view-the-default-anti-phishing-policy"></a>Usar el centro de seguridad & cumplimiento para ver la Directiva contra suplantación de identidad (phishing) predeterminada

1. En el centro de seguridad & cumplimiento y vaya a la **Directiva** \> de **Administración** \> de amenazas de **ATP anti-phishing**.

2. Haga clic en **directiva predeterminada** para ver la Directiva contra la suplantación de identidad predeterminada.

## <a name="use-exchange-online-powershell-to-configure-the-default-anti-phishing-policy"></a>Usar Exchange Online PowerShell para configurar la Directiva antiphishing predeterminada

### <a name="use-powershell-to-view-the-default-anti-phish-policy"></a>Usar PowerShell para ver la Directiva ANTIPHISH predeterminada

Para ver la Directiva ANTIPHISH predeterminada, ejecute el siguiente comando:

```PowerShell
Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).

### <a name="use-powershell-to-modify-the-default-anti-phish-policy"></a>Usar PowerShell para modificar la Directiva ANTIPHISH predeterminada

Para modificar la Directiva ANTIPHISH predeterminada, use la siguiente sintaxis:

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableAntispoofEnforcement <$true | $false>] [-EnableUnauthenticatedSender <$true | $false>]
```

En este ejemplo se cambia la acción de los mensajes suplantados que no superan la autenticación de las comprobaciones en cuarentena.

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" -AuthenticationFailAction Quarantine
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha configurado correctamente la Directiva de suplantación de identidad (phishing) predeterminada, realice uno de los siguientes pasos:

- En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **anti-phishing** \> haga clic en **directiva predeterminada** y vea los detalles en el control flotante.

- En Exchange Online PowerShell, ejecute el siguiente comando y Compruebe la configuración:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
  ```
