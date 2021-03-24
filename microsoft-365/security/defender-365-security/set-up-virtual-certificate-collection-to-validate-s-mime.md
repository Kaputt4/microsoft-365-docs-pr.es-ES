---
title: 'Configurar la colección de certificados virtuales: Exchange Online'
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
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: Los administradores pueden aprender a crear una colección de certificados virtuales que se usará para validar certificados S/MIME en Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a5dad897ce58b8496551535cc28e03c7a1fa964
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072555"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>Configurar la colección de certificados virtuales en Exchange Online para validar S/MIME

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Como administrador, deberá configurar una colección de certificados virtuales en Exchange Online que se usará para validar certificados S/MIME. Esta colección de certificados virtuales se configura como un almacén de certificados con una extensión de nombre de archivo SST. El archivo SST contiene todos los certificados raíz e intermedios que se usan al validar un certificado S/MIME.

## <a name="create-and-save-an-sst"></a>Crear y guardar un SST

Puede crear este archivo de almacén de certificados de SST exportando los certificados de una máquina de confianza mediante el cmdlet **Export-Certificate** en Windows PowerShell y especificando el valor _Type_ como SST. Para obtener instrucciones, [vea Export-Certificate](/powershell/module/pkiclient/export-certificate).

Una vez que tenga el archivo de almacén de certificados de SST, use la siguiente sintaxis en Exchange Online PowerShell para guardar el contenido del archivo SST en el almacén de certificados virtual de Exchange Online. Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

En este ejemplo se importa el archivo SST C:\Mis documentos\Almacén de certificados exportado.sst.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).

## <a name="ensuring-a-certificate-is-valid"></a>Garantizar que un certificado es válido

En Exchange Online, solo se usa el SST para la validación de certificados.

## <a name="more-information"></a>Más información

[S/MIME para la firma y el cifrado de mensajes](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig)