---
title: Crear una directiva de tipo de información confidencial con cifrado de mensajes de Office 365
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
description: Obtenga información sobre cómo crear una directiva de tipo de información confidencial para su organización mediante el cifrado de mensajes de Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 22aec87b149c58b2537f6921fb7c37552ef72f98
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741383"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a>Crear una directiva de tipo de información confidencial para su organización mediante cifrado de mensajes

Puede usar las reglas de flujo de correo de Exchange o prevención de pérdida de datos (DLP) para crear una directiva de tipo de información confidencial con cifrado de mensajes de Office 365. Para crear una regla de flujo de correo de Exchange, puede usar el Centro de administración de Exchange (EAC) o PowerShell.

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>Para crear la directiva mediante reglas de flujo de correo en el EAC

Inicie sesión en el Centro de administración de Exchange (EAC) y vaya a **Reglas de flujo de**  >  **correo**. En la página Reglas, cree una regla que aplique cifrado de mensajes de Office 365. Puede crear una regla en función de condiciones como la presencia de determinadas palabras clave o tipos de información confidencial en el mensaje o los datos adjuntos.

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>Para crear la directiva mediante reglas de flujo de correo en PowerShell

Use una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](https://aka.ms/exopowershell). Use los cmdlets Set-IRMConfiguration y New-TransportRule para crear la directiva.

## <a name="example-mail-flow-rule-created-with-powershell"></a>Regla de flujo de correo de ejemplo creada con PowerShell

Ejecute los siguientes comandos en PowerShell para crear una regla de flujo de correo de Exchange que cifre automáticamente los correos electrónicos enviados fuera de la organización con la opción de solo cifrado si los correos electrónicos o sus datos adjuntos contienen los siguientes tipos de información confidencial:

- Número de enrutamiento de ABA
- Número de tarjeta de crédito
- Número de agencia antidrogas (DEA)
- Ee.UU. / Reino Unido passport number
- Número de cuenta bancaria de EE. UU.
- Número de identificación de contribuyente individual (ITIN) de EE. UU.
- Número de seguridad social (SSN) de EE. UU.

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

Para obtener más información, [vea Set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-irmconfiguration) y [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-recipients-access-attachments"></a>Cómo los destinatarios acceden a datos adjuntos

Después de que Microsoft cifra un mensaje, los destinatarios tienen acceso sin restricciones a los datos adjuntos cuando acceden y abren su correo electrónico cifrado.

## <a name="to-prepare-for-this-change"></a>Para prepararse para este cambio

Es posible que desee actualizar cualquier documentación y materiales de aprendizaje del usuario final aplicables para preparar a los usuarios de su organización para este cambio. Comparta estos recursos de cifrado de mensajes de Office 365 con los usuarios según corresponda:

- [Enviar, ver y responder a mensajes cifrados en Outlook para PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Vídeo de Microsoft 365 Essentials: Cifrado de mensajes de Office](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>Ver estos cambios en el registro de auditoría

Microsoft 365 audita esta actividad y la pone a disposición de los administradores. La operación es "New-TransportRule" y a continuación se muestra un fragmento de código de una entrada de auditoría de ejemplo de la búsqueda de registros de auditoría en el Centro de seguridad & cumplimiento:

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>Para deshabilitar o personalizar la directiva de tipos de información confidencial

Una vez creada la regla de flujo [](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) de correo de Exchange, puede deshabilitar o editar la regla yendo a Reglas de flujo de correo en el Centro de administración de Exchange (EAC) y deshabilitando la regla " Cifrar correos electrónicos confidenciales salientes (regla de   >   *salida)*".
