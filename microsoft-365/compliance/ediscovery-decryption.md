---
title: Descifrado en eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo Microsoft 365 eDiscovery Tools administra documentos cifrados adjuntos a mensajes de correo electrónico.
ms.openlocfilehash: 89e6457015289055c56278f5f8650ce022ecf081
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920735"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Descifrado en las herramientas de eDiscovery de Microsoft 365

Las organizaciones usan tecnología de cifrado para proteger el contenido confidencial dentro de su organización y garantizar que solo los usuarios adecuados tengan acceso a ese contenido. Las organizaciones usan varios tipos de cifrado, tanto tecnologías de cifrado de Microsoft como tecnologías de terceros para cumplir sus requisitos de seguridad y proteger la información confidencial.

Hasta la fecha, la administración del contenido cifrado del flujo de trabajo de eDiscovery en Microsoft 365 requiere un control especial de los elementos cifrados según el tipo de cifrado usado y la fase específica del flujo de trabajo. Esto se consiguió principalmente mediante el descifrado del contenido de los mensajes de correo electrónico cuando se exportó de búsquedas de contenido, casos de eDiscovery principales y casos de eDiscovery avanzados. No se pudo obtener una vista previa del contenido cifrado con las tecnologías de cifrado de Microsoft hasta que se exportó. En la exhibición avanzada de documentos electrónicos, el contenido cifrado se marcó con un error de procesamiento, que requirió descargar el elemento cifrado, descifrarlo y, a continuación, carga el archivo descifrado en un conjunto de revisión.

Para facilitar la administración del contenido cifrado en el flujo de trabajo de eDiscovery, las herramientas de exhibición de documentos electrónicos de 365 de Microsoft pueden descifrar archivos cifrados que se adjuntan a mensajes de correo electrónico y se envían a Exchange Online. Antes de esta nueva capacidad, solo se descifró el contenido de un mensaje de correo electrónico protegido por la administración de derechos (y no los archivos adjuntos). Ahora, si un archivo cifrado con una tecnología de cifrado de Microsoft se adjunta a un mensaje de correo electrónico que coincide con los criterios de búsqueda, el archivo cifrado se descifrará cuando los resultados de la búsqueda se hayan preparado para la vista previa. Esto permite a los administradores de eDiscovery ver el contenido de los datos adjuntos de correo electrónico cifrados al obtener una vista previa de los resultados de búsqueda.

> [!NOTE]
> A partir de 2021 de enero, las herramientas de eDiscovery de Microsoft 365 admitirán documentos cifrados almacenados en SharePoint Online y OneDrive para la empresa.

## <a name="supported-encryption-technologies"></a>Tecnologías de cifrado admitidas

Las herramientas de eDiscovery de Microsoft admiten elementos cifrados con tecnologías de cifrado de Microsoft. Estas tecnologías incluyen el cifrado de mensajes de Office, la protección de información de Microsoft (etiquetas de confidencialidad) y Azure Rights Management. Para obtener más información acerca de las tecnologías de cifrado de Microsoft, vea [Encryption](encryption.md). No se admite el contenido cifrado por tecnologías de cifrado de terceros. Esto no incluye compatibilidad para obtener una vista previa o exportación de contenido cifrado con tecnologías que no son de Microsoft.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>actividades de eDiscovery que admiten elementos cifrados

En la tabla siguiente se identifican las tareas realizadas en Microsoft 365 eDiscovery Tools que admiten el descifrado de los archivos cifrados adjuntados a los documentos retocados de correo electrónico. Las tareas de soporte se pueden realizar en un archivo cifrado que esté adjunto a un mensaje de correo electrónico que coincida con los criterios de una búsqueda. Un valor de "N/A" indica que la función no está disponible en la herramienta de eDiscovery correspondiente.

|tarea de eDiscovery  |Búsqueda de contenido  |Core eDiscovery  |eDiscovery avanzado  |
|:---------|:---------|:---------|:---------|
|Buscar contenido en archivos cifrados     |No      |No      |No      |
|Vista previa de archivos cifrados     |Sí      |Sí     |Sí       |
|Revisión de los archivos cifrados en un conjunto de revisión    |N/D      |N/D        | Sí        |
|Exportar archivos cifrados    |Sí       |Sí  |Sí    |

## <a name="requirements-for-decryption-in-ediscovery"></a>Requisitos para el descifrado en eDiscovery

Debe tener asignado el rol descifrado de RMS para obtener una vista previa, revisar y exportar archivos adjuntos cifrados con tecnologías de cifrado de Microsoft. También tiene que tener asignado este rol para revisar y consultar datos adjuntos de correo electrónico cifrados que se agregan a un conjunto de revisión en eDiscovery avanzado.

Este rol se asigna de forma predeterminada al grupo de roles eDiscovery Manager en el centro de seguridad & cumplimiento de Office 365. Para obtener más información acerca del rol de descifrado de RMS, consulte [asignar permisos de exhibición](assign-ediscovery-permissions.md#rms-decrypt)de documentos electrónicos.
