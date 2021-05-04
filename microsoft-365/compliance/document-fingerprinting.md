---
title: Creación de huella digital de documento
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: ITPro
ms.topic: article
search.appverid: MET150
ms.service: exchange-online
ms.collection: M365-security-compliance
localization_priority: Normal
description: Los trabajadores de la información en su organización tratan con diversos tipos de información confidencial durante un día normal. La creación de huella digital de documento facilita la protección de esta información al identificar los formularios estándar que se usan en toda la organización. En este tema se describen los conceptos detrás de la huella digital de documentos y cómo crear uno mediante PowerShell.
ms.openlocfilehash: 392b42e779de249dddc0acb4c7c757a009f9f743
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086743"
---
# <a name="document-fingerprinting"></a>Creación de huella digital de documento

Los trabajadores de la información en su organización tratan con diversos tipos de información confidencial durante un día normal. En el Centro de cumplimiento de seguridad, la huella digital de documentos facilita la protección de esta información mediante la identificación de formularios estándar que se &amp; usan en toda la organización. En este tema se describen los conceptos detrás de la huella digital de documentos y cómo crear uno mediante PowerShell.
  
## <a name="basic-scenario-for-document-fingerprinting"></a>Escenario básico para la creación de huella digital de documento

La huella digital de documentos es una característica de prevención de pérdida de datos (DLP) que convierte un formulario estándar en un tipo de información confidencial, que puede usar en las reglas de las directivas DLP. Por ejemplo, puede crear una huella digital de documento con base en una plantilla de patente en blanco y después crear una directiva DLP que detecte y bloquee todas las plantillas de patente salientes que incluyan contenido confidencial. Opcionalmente, puede configurar [](use-notifications-and-policy-tips.md) sugerencias de directiva para notificar a los remitentes que podrían enviar información confidencial y el remitente debe comprobar que los destinatarios están cualificados para recibir las patentes. Este proceso funciona con cualquier formulario basado en texto que se use en la organización. Algunos ejemplos adicionales de formularios que puede cargar son:
  
- Formularios de gobierno
- Formularios de cumplimiento de Health Insurance Portability and Accountability Act (HIPAA)  
- Formularios de información sobre empleados para los departamentos de recursos humanos
- Formularios personalizados creados específicamente para la organización

Idealmente, la organización ya tiene una práctica de negocios establecida sobre el uso de determinados formularios para transmitir información confidencial. Después de cargar un formulario vacío para convertirlo en una huella digital de documento y configurar una directiva correspondiente, DLP detecta cualquier documento en el correo saliente que coincida con esa huella digital.

## <a name="how-document-fingerprinting-works"></a>Funcionamiento de la creación de huella digital de documento

Probablemente ya adivinó que los documentos no tienen huellas digitales reales, pero el nombre ayuda a explicar la característica. Del mismo modo que las huellas digitales de una persona tienen patrones únicos, los documentos tienen patrones de palabras únicos. Al cargar un archivo, DLP identifica el patrón de palabras único del documento, crea una huella digital de documento basada en ese patrón y usa esa huella digital del documento para detectar documentos salientes que contienen el mismo patrón. Por ello, la carga de un formulario o plantilla crea el tipo más efectivo de huella digital de documento. Todas las personas que rellenan un formulario usan el mismo conjunto de palabras original y después agregan sus propias palabras al documento. Siempre que el documento saliente no esté protegido con contraseña y contenga todo el texto del formulario original, DLP puede determinar si el documento coincide con la huella digital del documento.

> [!IMPORTANT]
> Por ahora, DLP puede usar la huella digital de documentos como método de detección Exchange en línea.

El siguiente ejemplo muestra qué sucede si crea una huella digital de documento con base en una plantilla de patente, pero puede usar cualquier formulario como base para crear una huella digital de documento.
  
### <a name="example-of-a-patent-document-matching-a-document-fingerprint-of-a-patent-template"></a>Ejemplo de documento de patente que coincide con una huella digital de documento de una plantilla de patente

![Diagrama de huella digital del documento.](../media/Document-Fingerprinting-diagram.png)
  
La plantilla de patente contiene los campos en blanco "Título de patente", "Inventores" y "Descripción" y descripciones para cada uno de esos campos, es decir, el patrón de palabras. Al cargar la plantilla de patente original, está en uno de los tipos de archivo admitidos y en texto sin formato. DLP convierte este patrón de palabras en una huella digital de documento, que es un pequeño archivo XML Unicode que contiene un valor hash único que representa el texto original, y la huella digital se guarda como una clasificación de datos en Active Directory. (Como medida de seguridad, el propio documento original no se almacena en el servicio; solo se almacena el valor hash y el documento original no se puede reconstruir a partir del valor hash). A continuación, la huella digital de patente se convierte en un tipo de información confidencial que puede asociar a una directiva DLP. Después de asociar la huella digital a una directiva DLP, DLP detecta cualquier correo electrónico saliente que contenga documentos que coincidan con la huella digital de patente y se ocupa de ellos de acuerdo con la directiva de su organización. 

Por ejemplo, es posible que desee configurar una directiva DLP que impida a los empleados regulares enviar mensajes salientes que contengan patentes. DLP usará la huella digital de la patente para detectar patentes y bloquear esos correos electrónicos. Como alternativa, es posible que desee permitir que su departamento jurídico pueda enviar patentes a otras organizaciones porque tiene una necesidad empresarial para hacerlo. Puede permitir que departamentos específicos envíen información confidencial creando excepciones para esos departamentos en la directiva DLP, o puede permitirles invalidar una sugerencia de directiva con una justificación empresarial.
  
### <a name="supported-file-types"></a>Tipos de archivo compatibles

La huella digital de documentos admite los mismos tipos de archivo que se admiten en las reglas de flujo de correo (también conocidas como reglas de transporte). Para obtener una lista de tipos de archivo admitidos, vea [Supported file types for mail flow rule content inspection](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection). Una nota rápida sobre los tipos de archivo: ni las reglas de flujo de correo ni la huella digital de documentos admiten el tipo de archivo .dotx, lo que puede resultar confuso porque es un archivo de plantilla en Word. Cuando ve la palabra "plantilla" en este y otros temas de creación de huella digital de documento, se refiere a un documento que se ha establecido como formulario estándar, no al tipo de archivo de plantilla.
  
#### <a name="limitations-of-document-fingerprinting"></a>Limitaciones de la creación de huella digital de documento

La huella digital de documentos no detectará información confidencial en los siguientes casos:
  
- Archivos protegidos por contraseña
- Archivos que solo contienen imágenes
- Documentos que no contienen todo el texto del formulario original utilizado para crear la huella digital de documento
- Archivos superiores a 10 MB

## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a>Usar PowerShell para crear un paquete de reglas de clasificación basado en la huella digital de documentos

Tenga en cuenta que actualmente solo puede crear una huella digital de documento mediante PowerShell en el Centro de &amp; seguridad y cumplimiento. Para conectarse, [consulte Conectar Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).

DLP usa paquetes de reglas de clasificación para detectar contenido confidencial. Para crear un paquete de reglas de clasificación basado en una huella digital de documento, use los cmdlets **New-DlpFingerprint** y **New-DlpSensitiveInformationType.** Dado que los resultados de **New-DlpFingerprint** no se almacenan fuera de la regla de clasificación de datos, siempre se ejecutan **New-DlpFingerprint** y **New-DlpSensitiveInformationType** o **Set-DlpSensitiveInformationType en** la misma sesión de PowerShell. En el ejemplo siguiente se crea una huella digital de documento nueva a partir del archivo C:\My Documents\Contoso Employee Template.docx. La nueva huella digital se almacena como variable para poder usarla con el cmdlet **New-DlpSensitiveInformationType** en la misma sesión de PowerShell.
  
```powershell
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

Ahora, crearemos una nueva regla de clasificación de datos llamada "Contoso Employee Confidential" que usa la huella digital de documento del archivo C:\My Documents\Contoso Customer Information Form.docx.
  
```powershell
$Customer_Form = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

Ahora puede usar el cmdlet **Get-DlpSensitiveInformationType** para buscar todos los paquetes de reglas de clasificación de datos DLP y, en este ejemplo, "Contoso Customer Confidential" forma parte de la lista de paquetes de reglas de clasificación de datos. 
  
Por último, agregue el paquete de regla de clasificación de datos "Contoso Customer Confidential" a una directiva DLP en el Centro de &amp; cumplimiento de seguridad. En este ejemplo se agrega una regla a una directiva DLP existente denominada "ConfidentialPolicy".

```powershell
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

También puede usar el paquete de reglas de clasificación de datos en las reglas de flujo de correo Exchange Online, como se muestra en el ejemplo siguiente. Para ejecutar este comando, primero debe Conectar [para Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Tenga en cuenta también que el paquete de reglas tarda tiempo en sincronizarse desde el Centro de seguridad &amp; y cumplimiento con el centro Exchange administración.
  
```powershell
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}
```

DLP ahora detecta documentos que coinciden con la huella digital del Form.docx contoso.
  
Para obtener información sobre la sintaxis y los parámetros, vea:

- [New-DlpFingerprint](/powershell/module/exchange/New-DlpFingerprint)
- [New-DlpSensitiveInformationType](/powershell/module/exchange/New-DlpSensitiveInformationType)
- [Remove-DlpSensitiveInformationType](/powershell/module/exchange/Remove-DlpSensitiveInformationType)
- [Set-DlpSensitiveInformationType](/powershell/module/exchange/Set-DlpSensitiveInformationType)
- [Get-DlpSensitiveInformationType](/powershell/module/exchange/Get-DlpSensitiveInformationType)
