---
title: Crear una directiva de tipo de información confidencial para la organización mediante cifrado de mensajes
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: 'Resumen: Directiva de cifrado de mensajes de Office 365 para tipos de información confidencial.'
ms.openlocfilehash: a36ab68eb649c84a46fa96de8ee400632c5c1d26
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626878"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a>Crear una directiva de tipo de información confidencial para la organización mediante cifrado de mensajes

Puede usar reglas de flujo de correo de Exchange o prevención de pérdida de datos (DLP) para crear una directiva de tipo de información confidencial con el cifrado de mensajes de Office 365. Para crear una regla de flujo de correo de Exchange, puede usar el centro de administración de Exchange (EAC) o PowerShell.

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>Para crear la Directiva mediante reglas de flujo de correo en el EAC

Inicie sesión en el centro de administración de Exchange (EAC) y vaya a**reglas**de **flujo** > de correo. En la página reglas, cree una regla que aplique el cifrado de mensajes de Office 365. Puede crear una regla basada en condiciones como la presencia de determinadas palabras clave o tipos de información confidencial en el mensaje o los datos adjuntos.

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>Para crear la Directiva mediante reglas de flujo de correo en PowerShell

Use una cuenta profesional o educativa que tenga permisos de administrador global en su organización, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](https://aka.ms/exopowershell). Use los cmdlets Set-IRMConfiguration y New-TransportRule para crear la Directiva.

## <a name="example-mail-flow-rule-created-with-powershell"></a>Ejemplo de regla de flujo de correo creada con PowerShell

Ejecute los siguientes comandos en PowerShell para crear una regla de flujo de correo de Exchange que cifre automáticamente los correos electrónicos enviados fuera de la organización con la directiva *de solo cifrado* si los mensajes de correo electrónico o sus datos adjuntos contienen los siguientes tipos de información confidencial:

- Número de enrutamiento ABA
- Número de tarjeta de crédito
- Número de la Agencia para la imposición de drogas (DEA)
- ESTADOS UNIDOS/REINO UNIDO passport number
- Número de cuenta bancaria de Estados Unidos
- Número de identificación de contribuyente individual (ITIN) de EE. UU.
- Número de seguridad social (SSN) de EE. UU.

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

Para más información, vea [set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-irmconfiguration?view=exchange-ps) y [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule?view=exchange-ps).

## <a name="how-recipients-access-attachments"></a>Acceso a datos adjuntos de destinatarios

Una vez que Microsoft cifra un mensaje, los destinatarios tienen acceso sin restricciones a los datos adjuntos cuando acceden y abren su correo electrónico cifrado.

## <a name="to-prepare-for-this-change"></a>Para prepararse para este cambio

Es posible que desee actualizar toda la documentación para el usuario final y los materiales de formación correspondientes para preparar a los usuarios de su organización para este cambio. Comparta estos recursos de cifrado de mensajes de Office 365 con los usuarios según corresponda:

- [Enviar, ver y responder mensajes cifrados en Outlook para PC](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980)
- [Vídeo de Microsoft 365 Essentials: cifrado de mensajes de Office](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>Ver estos cambios en el registro de auditoría

Microsoft 365 audita esta actividad y la pone a disposición de los administradores. La operación es ' New-TransportRule ' y un fragmento de código de una entrada de auditoría de la búsqueda del registro de auditoría en el centro de seguridad & cumplimiento se muestra a continuación:

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>Para deshabilitar o personalizar la Directiva de tipos de información confidencial

Una vez que haya creado la regla de flujo de correo de Exchange, puede [deshabilitarla o editarla](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) en**reglas** de **flujo** > de correo en el centro de administración de Exchange (EAC) y deshabilitar la regla "*cifrar correo electrónico confidencial saliente (regla" fuera de la caja ")*.
