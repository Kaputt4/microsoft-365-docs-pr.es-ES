---
title: Cifrado de datos en OneDrive para la Empresa y SharePoint Online
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 9/20/2021
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- purview-compliance
- SPO_Content
- tier2
description: Entienda los elementos básicos del cifrado de seguridad de datos en OneDrive para la Empresa y SharePoint Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b33bbe22e5bf606bcc71b6308c5fce3e0c68a542
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68621772"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a>Cifrado de datos en OneDrive para la Empresa y SharePoint Online

Entienda los elementos básicos del cifrado de seguridad de datos en OneDrive para la Empresa y SharePoint Online.
  
[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="security-and-data-encryption-in-office-365"></a>Seguridad y cifrado de datos en Office 365

Microsoft 365 es un entorno muy seguro que ofrece una amplia protección en varias capas: seguridad física del centro de datos, seguridad de red, seguridad de acceso, seguridad de aplicaciones y seguridad de datos. Este artículo se centra específicamente en el lado del cifrado en tránsito y en reposo de la seguridad de datos para OneDrive para la Empresa y SharePoint Online.
  
Vea cómo funciona el cifrado de datos en el siguiente vídeo.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a>Cifrado de datos en tránsito

En OneDrive para la Empresa y SharePoint Online, hay dos escenarios en los que los datos entran y salen de los centros de datos.
  
- **Client communication with the server** Communication to OneDrive for Business across the Internet uses SSL/TLS connections. All SSL connections are established using 2048-bit keys.

- **Data movement between datacenters** The primary reason to move data between datacenters is for geo-replication to enable disaster recovery. For instance, SQL Server transaction logs and blob storage deltas travel along this pipe. While this data is already transmitted by using a private network, it is further protected with best-in-class encryption. 

## <a name="encryption-of-data-at-rest"></a>Cifrado de datos en reposo

El cifrado en reposo incluye dos componentes: cifrado de nivel de disco de BitLocker y cifrado por archivo del contenido del cliente.
  
BitLocker se implementa para OneDrive para la Empresa y SharePoint Online en todo el servicio. El cifrado por archivo también está en OneDrive para la Empresa y SharePoint Online en varios inquilinos de Microsoft 365 y nuevos entornos dedicados que se basan en la tecnología multiinquilino.
  
Mientras que BitLocker cifra todos los datos en un disco, el cifrado por archivo va más allá al incluir una clave de cifrado única para cada archivo. Además, la actualización de cada archivo se cifra mediante su propia clave de cifrado. Las claves del contenido cifrado se almacenan en una ubicación físicamente independiente del contenido. Cada paso de este cifrado usa el Estándar de cifrado avanzado (AES) con claves de 256 bits y cumple el Estándar federal de procesamiento de información (FIPS) 140-2. El contenido cifrado se distribuye entre varios contenedores en el centro de datos y cada contenedor tiene credenciales exclusivas. Estas credenciales se almacenan en una ubicación física independiente del contenido o de las claves de contenido.
  
Para obtener más información sobre el cumplimiento de FIPS 140-2, consulte [Cumplimiento con FIPS 140-2](/previous-versions/sql/sql-server-2008-r2/bb326611(v=sql.105)).
  
File-level encryption at rest takes advantage of blob storage to provide for virtually unlimited storage growth and to enable unprecedented protection. All customer content in OneDrive for Business and SharePoint Online will be migrated to blob storage. Here's how that data is secured:
  
1. All content is encrypted, potentially with multiple keys, and distributed across the datacenter. Each file to be stored is broken into one or more chunks, depending its size. Then, each chunk is encrypted using its own unique key. Updates are handled similarly: the set of changes, or deltas, submitted by a user is broken into chunks, and each is encrypted with its own key.

2. All of these chunks—files, pieces of files, and update deltas—are stored as blobs in our blob store. They also are randomly distributed across multiple blob containers.

3. El "mapa" que se usa para volver a ensamblar el archivo a partir de sus componentes se almacena en la base de datos de contenido.

4. Each blob container has its own unique credentials per access type (read, write, enumerate, and delete). Each set of credentials is held in the secure Key Store and is regularly refreshed.

En otras palabras, hay tres tipos diferentes de almacenes implicados en el cifrado por archivo en reposo, cada uno con una función distinta:
  
- Content is stored as encrypted blobs in the blob store. The key to each chunk of content is encrypted and stored separately in the content database. The content itself holds no clue as to how it can be decrypted.

- The Content Database is a SQL Server database. It holds the map required to locate and reassemble all of the content blobs held in the blob store as well as the keys needed to decrypt those blobs.

Each of these three storage components—the blob store, the Content Database, and the Key Store—is physically separate. The information held in any one of the components is unusable on its own. This provides an unprecedented level of security. Without access to all three it is impossible to retrieve the keys to the chunks, decrypt the keys to make them usable, associate the keys with their corresponding chunks, decrypt any chunk, or reconstruct a document from its constituent chunks.
