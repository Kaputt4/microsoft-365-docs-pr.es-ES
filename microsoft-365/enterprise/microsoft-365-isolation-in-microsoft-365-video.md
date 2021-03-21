---
title: Aislamiento del inquilino en Office 365 Video
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: En este artículo, busque una explicación de cómo el aislamiento de inquilinos mantiene separados los vídeos almacenados de cada inquilino en Office 365 Video.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fc67b17aa40b3bca9ce6d73ebb7e18319e780339
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918935"
---
# <a name="tenant-isolation-in-office-365-video"></a>Aislamiento del inquilino en Office 365 Video

> [!NOTE]
> Office 365 Video se reemplazará por Microsoft Stream. Para obtener más información sobre el nuevo servicio de vídeo empresarial que agrega inteligencia a la colaboración en vídeo y obtener información sobre los planes de transición para los clientes actuales de Vídeo de Microsoft [365, vea Office 365 Video transition to Microsoft Stream overview](/stream/migrate-from-office-365).

## <a name="introduction"></a>Introducción

Azure Storage se usa para almacenar datos para varios servicios de Office 365, incluidos Office 365 Video y Sway. Azure Storage incluye almacenamiento de blobs, que es un almacén de objetos en la nube altamente escalable y basado en REST que se usa para almacenar datos no estructurados. Azure Storage usa un modelo de control de acceso simple; cada suscripción de Azure puede crear una o más cuentas de almacenamiento. Cada cuenta de almacenamiento tiene una sola clave secreta que se usa para controlar el acceso a todos los datos de esa cuenta de almacenamiento. Esto admite el escenario típico en el que el almacenamiento está asociado a aplicaciones y esas aplicaciones tienen control total sobre sus datos asociados; por ejemplo, Sway almacenando contenido en Azure Storage. Todo el contenido del cliente para Sway se almacena en cuentas compartidas de Azure Storage. El contenido de cada usuario se encuentra en un árbol de directorios independiente de blobs en Azure Storage.

Los sistemas que administran el acceso a entornos de clientes (por ejemplo, Azure Portal, SMAPI, etc.) están aislados en una aplicación de Azure operada por Microsoft. Esto separa lógicamente la infraestructura de acceso de clientes de las aplicaciones de cliente y la capa de almacenamiento.

## <a name="tenant-isolation-in-office-365-video"></a>Aislamiento del inquilino en Office 365 Video

[Office 365 Video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) es un portal empresarial que proporciona a las organizaciones un destino altamente seguro para toda la organización para publicar, compartir y descubrir contenido de vídeo. En Office 365 Video, los vídeos de cada inquilino se mantienen aislados y cifrados en todas las ubicaciones y solo están disponibles para los usuarios autenticados que tienen acceso y permisos a los vídeos de la organización. Office 365 Video usa una combinación de tecnologías para lograr esto:

- SharePoint Online se usa para almacenar el archivo de vídeo y los metadatos (título del vídeo, descripción, etc.). También proporciona la capa de seguridad y cumplimiento (incluida la autenticación) y las características de búsqueda.
- Azure Media Services proporciona funciones de transcodificación, streaming adaptable, entrega segura (mediante cifrado AES) y características de miniatura.

[Azure Media Services es](https://azure.microsoft.com/services/media-services/) una oferta de plataforma como servicio para habilitar flujos de trabajo multimedia de extremo a extremo en la nube. La plataforma proporciona una API de REST para cargar, codificar, cifrar (con PlayReady) y entregar medios a través de centros de datos de Azure en todo el mundo.

Todas las cargas de Vídeo de Office 365 se producen a través de HTTPS. Cuando se carga un archivo de vídeo, se almacena en SharePoint Online y se envía una copia del archivo a través de un canal cifrado a Azure Media Services. Azure Media Services transcodifica el vídeo en varios formatos optimizados para la experiencia de visualización (por ejemplo, móvil, ancho de banda bajo, ancho de banda alto, etc.). Estos archivos, junto con el archivo original adquirido durante la carga, se almacenan en Azure Blob Storage. Los archivos se cifran mediante AES 128 según el algoritmo de empaquetado MPEG Common Encryption (o una versión anterior de PlayReady) para la reproducción y se cifran con el cifrado de almacenamiento de AES 256 antes de almacenarse en Azure Blob Storage. (Con el SDK de cliente de Azure Media Services, los clientes pueden controlar qué cifrado se usa. Por ejemplo, un cliente podría aplicar el cifrado de almacenamiento de Azure Media Services (AES 256) a un activo multimedia de alto valor antes de cargarlo Azure Blob Storage).

Azure Media Services también genera una miniatura para el vídeo, que transmite junto con metadatos en miniatura a SharePoint Online a través de un canal cifrado.