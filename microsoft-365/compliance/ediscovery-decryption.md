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
description: Obtenga información sobre cómo Microsoft 365 eDiscovery Tools administra documentos cifrados adjuntos a mensajes de correo electrónico y almacenados en SharePoint Online y OneDrive para la empresa.
ms.openlocfilehash: df2ff218e5c62e103661889fc8c66950a4d25cab
ms.sourcegitcommit: 6759e619c45a5f8e775ad456a5dfb18c08f13f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/18/2020
ms.locfileid: "49713271"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Descifrado en las herramientas de eDiscovery de Microsoft 365

El cifrado es una parte importante de la estrategia de protección y protección de la información de archivos. Las organizaciones de todos los tipos usan tecnología de cifrado para proteger el contenido confidencial dentro de su organización y asegurarse de que solo las personas adecuadas tienen acceso a ese contenido.

Para ejecutar tareas de eDiscovery comunes en contenido cifrado, los administradores de eDiscovery eran necesarios para descifrar el contenido de los mensajes de correo electrónico a medida que se exportó desde búsquedas de contenido, casos de eDiscovery principales y casos de eDiscovery avanzados. El contenido cifrado con las tecnologías de cifrado de Microsoft no estaba disponible para revisión hasta que se exportó.

Para facilitar la administración del contenido cifrado en el flujo de trabajo de eDiscovery, las herramientas de eDiscovery de 365 de Microsoft incorporan ahora el descifrado de los archivos cifrados que se adjuntan a los mensajes de correo electrónico y se envían a Exchange Online. Además, los documentos cifrados almacenados en SharePoint Online y OneDrive para la empresa se descifran en eDiscovery avanzado. 

Antes de esta nueva capacidad, solo se descifraron el contenido de un mensaje de correo electrónico protegido por la administración de derechos (y no los archivos adjuntos). Los documentos cifrados en SharePoint y OneDrive no se pudieron descifrar durante el flujo de trabajo de eDiscovery. Ahora, si un archivo cifrado con una tecnología de cifrado de Microsoft se adjunta a un mensaje de correo electrónico o se encuentra en una cuenta de SharePoint o de OneDrive, esos elementos cifrados se descifran cuando los resultados de la búsqueda se preparan para la vista previa, se agregan a un conjunto de revisión en eDiscovery avanzado y se exportan. Esto permite a los administradores de eDiscovery ver el contenido de los documentos adjuntos de correo electrónico cifrados y los documentos del sitio al obtener una vista previa de los resultados de búsqueda, y revisarlos después de que se hayan agregado a un conjunto de revisión en eDiscovery avanzado.

## <a name="supported-encryption-technologies"></a>Tecnologías de cifrado admitidas

Las herramientas de eDiscovery de Microsoft admiten elementos cifrados con tecnologías de cifrado de Microsoft. Estas tecnologías incluyen el cifrado de mensajes de Office, Azure Rights Management y Microsoft Information Protection (específicamente, las etiquetas de confidencialidad). Para obtener más información acerca de las tecnologías de cifrado de Microsoft, vea [Encryption](encryption.md). No se admite el contenido cifrado por tecnologías de cifrado de terceros. Por ejemplo, no se admite la vista previa o la exportación de contenido cifrado con tecnologías que no son de Microsoft.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>actividades de eDiscovery que admiten elementos cifrados

En la siguiente tabla se identifican las tareas compatibles que se pueden realizar en las herramientas de exhibición de documentos electrónicos de Microsoft 365 en archivos cifrados adjuntas a retocamientos de correo electrónico y documentos cifrados en SharePoint y OneDrive. Estas tareas admitidas se pueden realizar en los archivos cifrados que coinciden con los criterios de una búsqueda. Un valor de "N/A" indica que la funcionalidad no está disponible en la herramienta de eDiscovery correspondiente.

|tarea de eDiscovery  |Búsqueda de contenido  |Core eDiscovery  |eDiscovery avanzado  |
|:---------|:---------|:---------|:---------|
|Buscar contenido en archivos cifrados en el correo electrónico y los sitios     |Sí      |Sí      |Sí      |
|Vista previa de archivos cifrados adjuntos a correo electrónico     |Sí      |Sí     |Sí       |
|Obtener una vista previa de documentos cifrados en SharePoint y OneDrive|No      |No    |Sí       |
|Revisión de los archivos cifrados en un conjunto de revisión    |N/D      |N/D        | Sí        |
|Exportar archivos cifrados adjuntos al correo electrónico    |Sí       |Sí  |Sí    |
|Exportar documentos cifrados en SharePoint y OneDrive    |No       |No  |Sí    |
|||||

## <a name="requirements-for-decryption-in-ediscovery"></a>Requisitos para el descifrado en eDiscovery

Debe tener asignado el rol de descifrado de RMS para obtener una vista previa, revisar y exportar archivos cifrados con tecnologías de cifrado de Microsoft. También tiene que tener asignado este rol para revisar y consultar archivos cifrados que se agregan a un conjunto de revisión en la exhibición avanzada de documentos electrónicos.

Este rol se asigna de forma predeterminada al grupo de roles eDiscovery Manager en la página de **permisos** del centro de seguridad & cumplimiento de Office 365. Para obtener más información acerca del rol de descifrado de RMS, consulte [asignar permisos de exhibición](assign-ediscovery-permissions.md#rms-decrypt)de documentos electrónicos.
