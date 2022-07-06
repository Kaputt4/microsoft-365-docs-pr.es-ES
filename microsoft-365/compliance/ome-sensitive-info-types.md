---
title: Creación de una directiva de tipo de información confidencial mediante Office 365 cifrado de mensajes
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: ''
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: Obtenga información sobre cómo crear una directiva de tipo de información confidencial para su organización mediante Office 365 cifrado de mensajes.
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
ms.openlocfilehash: 0974c30882177eb9fc46c2a2fcf65bc2edb43078
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66633441"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a>Creación de una directiva de tipo de información confidencial para su organización mediante el cifrado de mensajes

Puede usar reglas de flujo de correo de Exchange o prevención de pérdida de datos (DLP) de Microsoft Purview para crear una directiva de tipo de información confidencial con Office 365 cifrado de mensajes. Para crear una regla de flujo de correo de Exchange, puede usar el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange (EAC)</a> o PowerShell.

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>Para crear la directiva mediante reglas de flujo de correo en el EAC

Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a> y vaya a **Reglas** de **flujo** >  de correo. En la página Reglas, cree una regla que se aplique Office 365 cifrado de mensajes. Puede crear una regla basada en condiciones como la presencia de ciertas palabras clave o tipos de información confidencial en el mensaje o los datos adjuntos.

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>Para crear la directiva mediante reglas de flujo de correo en PowerShell

Use una cuenta profesional o educativa que tenga permisos de administrador global en su organización y conéctese a Exchange Online PowerShell. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Use los cmdlets Set-IRMConfiguration y New-TransportRule para crear la directiva.

## <a name="example-mail-flow-rule-created-with-powershell"></a>Regla de flujo de correo de ejemplo creada con PowerShell

Ejecute los siguientes comandos en PowerShell para crear una regla de flujo de correo de Exchange que cifre automáticamente los correos electrónicos enviados fuera de la organización con la opción de solo cifrado si los correos electrónicos o sus datos adjuntos contienen los siguientes tipos de información confidencial:

- Número de enrutamiento de ABA
- Número de tarjeta de crédito
- Número de la Agencia antidrogas (DEA)
- Estados Unidos/ Reino Unido passport number
- Número de cuenta bancaria de EE. UU.
- Número de identificación de contribuyente individual (ITIN) de EE. UU.
- Número de seguridad social (SSN) de EE. UU.

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

Para obtener más información, vea [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) y [New-TransportRule](/powershell/module/exchange/new-transportrule).

## <a name="how-recipients-access-attachments"></a>Cómo acceden los destinatarios a los datos adjuntos

Una vez que Microsoft cifra un mensaje, los destinatarios tienen acceso sin restricciones a los datos adjuntos cuando acceden y abren su correo electrónico cifrado.

## <a name="to-prepare-for-this-change"></a>Para prepararse para este cambio

Es posible que quiera actualizar cualquier documentación de usuario final y materiales de aprendizaje aplicables para preparar a los usuarios de su organización para este cambio. Comparta estos recursos Office 365 cifrado de mensajes con los usuarios según corresponda:

- [Envío, visualización y respuesta a mensajes cifrados en Outlook para PC](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Vídeo de Microsoft 365 Essentials: Cifrado de mensajes](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>Visualización de estos cambios en el registro de auditoría

Microsoft 365 audita esta actividad y la pone a disposición de los administradores. La operación es "New-TransportRule" y a continuación se muestra un fragmento de una entrada de auditoría de ejemplo de la búsqueda de registros de auditoría en el Centro de cumplimiento de & de seguridad:

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"...etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>Para deshabilitar o personalizar la directiva de tipos de información confidencial

Una vez que haya creado la regla de flujo de correo de Exchange, puede [deshabilitar o editar la regla](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) si va a **Reglas** de **flujo** >  de correo en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a> y deshabilita la regla "*Cifrar correos electrónicos confidenciales salientes (regla predefinida)*".
