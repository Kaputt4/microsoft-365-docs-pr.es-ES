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
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="dc7d7-103">Configurar la colección de certificados virtuales en Exchange Online para validar S/MIME</span><span class="sxs-lookup"><span data-stu-id="dc7d7-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="dc7d7-104">Como administrador, deberá configurar una colección de certificados virtuales en Exchange Online que se usará para validar certificados S/MIME.</span><span class="sxs-lookup"><span data-stu-id="dc7d7-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="dc7d7-105">Esta colección de certificados virtuales se configura como un almacén de certificados con una extensión de nombre de archivo SST.</span><span class="sxs-lookup"><span data-stu-id="dc7d7-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="dc7d7-106">El archivo SST contiene todos los certificados raíz e intermedios que se usan al validar un certificado S/MIME.</span><span class="sxs-lookup"><span data-stu-id="dc7d7-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="dc7d7-107">Crear y guardar un SST</span><span class="sxs-lookup"><span data-stu-id="dc7d7-107">Create and save an SST</span></span>

<span data-ttu-id="dc7d7-108">Puede crear este archivo de almacén de certificados de SST exportando los certificados de una máquina de confianza mediante el cmdlet **Export-Certificate** en Windows PowerShell y especificando el valor _Type_ como SST.</span><span class="sxs-lookup"><span data-stu-id="dc7d7-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="dc7d7-109">Para obtener instrucciones, [vea Export-Certificate](/powershell/module/pkiclient/export-certificate).</span><span class="sxs-lookup"><span data-stu-id="dc7d7-109">For instructions, see [Export-Certificate](/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="dc7d7-110">Una vez que tenga el archivo de almacén de certificados de SST, use la siguiente sintaxis en Exchange Online PowerShell para guardar el contenido del archivo SST en el almacén de certificados virtual de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dc7d7-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="dc7d7-111">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="dc7d7-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="dc7d7-112">En este ejemplo se importa el archivo SST C:\Mis documentos\Almacén de certificados exportado.sst.</span><span class="sxs-lookup"><span data-stu-id="dc7d7-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="dc7d7-113">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="dc7d7-113">For detailed syntax and parameter information, see [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="dc7d7-114">Garantizar que un certificado es válido</span><span class="sxs-lookup"><span data-stu-id="dc7d7-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="dc7d7-115">En Exchange Online, solo se usa el SST para la validación de certificados.</span><span class="sxs-lookup"><span data-stu-id="dc7d7-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="dc7d7-116">Más información</span><span class="sxs-lookup"><span data-stu-id="dc7d7-116">More Information</span></span>

[<span data-ttu-id="dc7d7-117">S/MIME para la firma y el cifrado de mensajes</span><span class="sxs-lookup"><span data-stu-id="dc7d7-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="dc7d7-118">Get-SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="dc7d7-118">Get-SmimeConfig</span></span>](/powershell/module/exchange/get-smimeconfig)