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
description: Obtenga información sobre cómo Microsoft 365 eDiscovery Tools administra documentos cifrados adjuntos a mensajes de correo electrónico.
ms.openlocfilehash: 91d5689bfb64d272c896c0e92422ce1f45fd5f72
ms.sourcegitcommit: 89f56c3e0b619a4700a75a21927d9ffc90658632
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "48984904"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Descifrado en las herramientas de eDiscovery de Microsoft 365

El cifrado es una parte importante de la estrategia de protección y protección de la información de archivos. Las organizaciones de todos los tipos usan tecnología de cifrado para proteger el contenido confidencial dentro de su organización y asegurarse de que solo las personas adecuadas tienen acceso a ese contenido.

Para ejecutar tareas de eDiscovery comunes en contenido cifrado, los administradores de eDiscovery eran necesarios para descifrar el contenido de los mensajes de correo electrónico a medida que se exportó desde búsquedas de contenido, casos de eDiscovery principales y casos de eDiscovery avanzados. El contenido cifrado con las tecnologías de cifrado de Microsoft no estaba disponible para revisión hasta que se exportó.

Para facilitar la administración del contenido cifrado en el flujo de trabajo de eDiscovery, las herramientas de eDiscovery de 365 de Microsoft incorporan ahora el descifrado de los archivos cifrados que se adjuntan a los mensajes de correo electrónico y se envían a Exchange Online. Antes de esta nueva capacidad, solo se descifraron el contenido de un mensaje de correo electrónico protegido por la administración de derechos (y no los archivos adjuntos). Ahora, si un archivo cifrado con una tecnología de cifrado de Microsoft se adjunta a un mensaje de correo electrónico que coincide con los criterios de búsqueda, el archivo cifrado se descifrará cuando los resultados de la búsqueda se hayan preparado para la revisión. Esto permite a los administradores de eDiscovery ver el contenido de los datos adjuntos de correo electrónico cifrados al obtener una vista previa de los resultados de búsqueda y revisarlos una vez que se han agregado a un conjunto de revisión en eDiscovery avanzado.

> [!NOTE]
> A partir de entonces, las herramientas de eDiscovery de Microsoft 365 admitirán documentos cifrados almacenados en SharePoint Online y OneDrive para la empresa. Esto incluirá los documentos que se cifran como resultado de las etiquetas de confidencialidad que se les aplican.

## <a name="supported-encryption-technologies"></a>Tecnologías de cifrado admitidas

Las herramientas de eDiscovery de Microsoft admiten elementos cifrados con tecnologías de cifrado de Microsoft. Estas tecnologías incluyen el cifrado de mensajes de Office y Azure Rights Management. Para obtener más información acerca de las tecnologías de cifrado de Microsoft, vea [Encryption](encryption.md). No se admite el contenido cifrado por tecnologías de cifrado de terceros. Esto no incluye compatibilidad para obtener una vista previa o exportación de contenido cifrado con tecnologías que no son de Microsoft.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>actividades de eDiscovery que admiten elementos cifrados

En la tabla siguiente se identifican las tareas realizadas en Microsoft 365 eDiscovery Tools que admiten el descifrado de los archivos cifrados adjuntados a los documentos retocados de correo electrónico. Las tareas de soporte se pueden realizar en un archivo cifrado que esté adjunto a un mensaje de correo electrónico que coincida con los criterios de una búsqueda. Un valor de "N/A" indica que la función no está disponible en la herramienta de eDiscovery correspondiente.

|tarea de eDiscovery  |Búsqueda de contenido  |Core eDiscovery  |eDiscovery avanzado  |
|:---------|:---------|:---------|:---------|
|Buscar contenido en archivos cifrados     |Sí      |Sí      |Sí      |
|Vista previa de archivos cifrados     |Sí      |Sí     |Sí       |
|Revisión de los archivos cifrados en un conjunto de revisión    |N/D      |N/D        | Sí        |
|Exportar archivos cifrados    |Sí       |Sí  |Sí    |

## <a name="requirements-for-decryption-in-ediscovery"></a>Requisitos para el descifrado en eDiscovery

Debe tener asignado el rol descifrado de RMS para obtener una vista previa, revisar y exportar archivos adjuntos cifrados con tecnologías de cifrado de Microsoft. También tiene que tener asignado este rol para revisar y consultar datos adjuntos de correo electrónico cifrados que se agregan a un conjunto de revisión en eDiscovery avanzado.

Este rol se asigna de forma predeterminada al grupo de roles eDiscovery Manager en el centro de seguridad & cumplimiento de Office 365. Para obtener más información acerca del rol de descifrado de RMS, consulte [asignar permisos de exhibición](assign-ediscovery-permissions.md#rms-decrypt)de documentos electrónicos.
