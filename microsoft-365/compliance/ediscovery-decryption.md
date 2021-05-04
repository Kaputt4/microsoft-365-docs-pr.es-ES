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
description: Obtenga información sobre cómo Microsoft 365 herramientas de exhibición de documentos electrónicos administran documentos cifrados adjuntos a mensajes de correo electrónico y almacenados en SharePoint Online y OneDrive para la Empresa.
ms.openlocfilehash: b87d87b7b0e870d6f396d87dc693fb8f41d5826b
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51750032"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Descifrado en Microsoft 365 herramientas de exhibición de documentos electrónicos

El cifrado es una parte importante de la estrategia de protección de archivos y protección de la información. Las organizaciones de todos los tipos usan tecnología de cifrado para proteger el contenido confidencial dentro de su organización y garantizar que solo las personas correctas tengan acceso a ese contenido.

Para ejecutar tareas comunes de exhibición de documentos electrónicos en contenido cifrado, los administradores de exhibición de documentos electrónicos tenían que descifrar el contenido de los mensajes de correo electrónico cuando se exportaba desde búsquedas de contenido, casos principales de exhibición de documentos electrónicos y Advanced eDiscovery casos. El contenido cifrado con tecnologías de cifrado de Microsoft no estaba disponible para su revisión hasta después de exportarlo.

Para facilitar la administración del contenido cifrado en el flujo de trabajo de exhibición de documentos electrónicos, Microsoft 365 las herramientas de exhibición de documentos electrónicos ahora incorporan el descifrado de archivos cifrados adjuntos a mensajes de correo electrónico y enviados Exchange Online. <sup>1</sup> Además, los documentos cifrados almacenados en SharePoint Online y OneDrive para la Empresa se descifran en Advanced eDiscovery.

Antes de esta nueva funcionalidad, solo se descifraba el contenido de un mensaje de correo electrónico protegido por la administración de derechos (y no los archivos adjuntos). Los documentos cifrados SharePoint y OneDrive no se pudieron descifrar durante el flujo de trabajo de exhibición de documentos electrónicos. Ahora, los archivos cifrados con una tecnología de cifrado de Microsoft se encuentran en una cuenta de SharePoint o OneDrive que se pueden buscar y descifrar cuando los resultados de la búsqueda se preparan para la vista previa, se agregan a un conjunto de revisión de Advanced eDiscovery y se exportan. Además, se pueden buscar documentos cifrados SharePoint y OneDrive que se adjuntan a un mensaje de correo electrónico. Esta funcionalidad de descifrado permite a los administradores de exhibición de documentos electrónicos ver el contenido de los datos adjuntos de correo electrónico cifrado y los documentos del sitio al obtener una vista previa de los resultados de la búsqueda y revisarlos después de que se hayan agregado a un conjunto de revisión en Advanced eDiscovery.

## <a name="supported-encryption-technologies"></a>Tecnologías de cifrado compatibles

Las herramientas de exhibición de documentos electrónicos de Microsoft admiten elementos cifrados con tecnologías de cifrado de Microsoft. Estas tecnologías son Azure Rights Management y Microsoft Information Protection (específicamente etiquetas de confidencialidad). Para obtener más información acerca de las tecnologías de cifrado de Microsoft, vea [Encryption](encryption.md). El contenido cifrado por tecnologías de cifrado de terceros no es compatible. Por ejemplo, no se admite la vista previa o exportación de contenido cifrado con tecnologías que no son de Microsoft.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>Actividades de exhibición de documentos electrónicos que admiten elementos cifrados

En la tabla siguiente se identifican las tareas admitidas que se pueden realizar en las herramientas de exhibición de documentos electrónicos de Microsoft 365 en archivos cifrados adjuntos a mensajes de correo electrónico y documentos cifrados en SharePoint y OneDrive. Estas tareas admitidas se pueden realizar en archivos cifrados que coinciden con los criterios de una búsqueda. Un valor de `N/A` indica que la funcionalidad no está disponible en la herramienta de exhibición de documentos electrónicos correspondiente.

|Tarea de exhibición de documentos electrónicos  |Búsqueda de contenido  |Core eDiscovery  |eDiscovery avanzado  |
|:---------|:---------|:---------|:---------|
|Buscar contenido en archivos cifrados en correo electrónico y sitios<sup>1</sup>     |Sí      |Sí      |Sí      |
|Vista previa de archivos cifrados adjuntos al correo electrónico     |Sí      |Sí     |Sí       |
|Vista previa de documentos cifrados en SharePoint y OneDrive|No      |No    |Sí       |
|Revisar archivos cifrados en un conjunto de revisión    |N/D      |N/D        | Sí        |
|Exportar archivos cifrados adjuntos al correo electrónico    |Sí       |Sí  |Sí    |
|Exportar documentos cifrados en SharePoint y OneDrive    |No       |No  |Sí    |
|||||

> [!NOTE]
> <sup>1</sup> Los archivos cifrados que se encuentran en un equipo local (y que no están almacenados en un sitio SharePoint o OneDrive) no se indizan para la exhibición de documentos electrónicos. Esto significa que si un archivo local cifrado está adjunto a un mensaje de correo electrónico, una consulta de búsqueda de palabras clave no devolverá el archivo, incluso si el archivo contiene palabras clave que coinciden con la consulta de búsqueda. Sin embargo, una búsqueda de exhibición de documentos electrónicos puede devolver mensajes de correo electrónico con un archivo cifrado local si una propiedad de correo electrónico (como fecha de envío, remitente, destinatario o asunto) coincide con la consulta de búsqueda.

### <a name="decryption-limitations-with-sensitivity-labels"></a>Limitaciones de descifrado con etiquetas de confidencialidad

La exhibición de documentos electrónicos no admite archivos cifrados en SharePoint y OneDrive cuando una etiqueta de confidencialidad que aplicó el cifrado se configura con cualquiera de las siguientes opciones:

- Los usuarios pueden asignar permisos cuando aplican manualmente la etiqueta a un documento. Esto a veces se conoce como *permisos definidos por el usuario*.

- El acceso del usuario al documento tiene una configuración de expiración que se establece en un valor distinto de **Never**.

Para obtener más información acerca de estas opciones de configuración, vea la sección "Configurar la configuración de cifrado" en Restringir el acceso al contenido mediante etiquetas de confidencialidad [para aplicar cifrado.](encryption-sensitivity-labels.md#configure-encryption-settings)

Los documentos cifrados con la configuración anterior aún pueden devolverse mediante una búsqueda de exhibición de documentos electrónicos. Esto puede ocurrir cuando una propiedad de documento (como el título, el autor o la fecha de modificación) coincide con los criterios de búsqueda. Aunque estos documentos pueden incluirse en los resultados de búsqueda, no se pueden obtener una vista previa ni revisarse. Estos documentos también permanecerán cifrados cuando se exporten en Advanced eDiscovery.

## <a name="requirements-for-decryption-in-ediscovery"></a>Requisitos para el descifrado en eDiscovery

Debe tener asignado el rol Descifrar RMS para obtener una vista previa, revisar y exportar archivos cifrados con tecnologías de cifrado de Microsoft. También debe tener asignado este rol para revisar y consultar archivos cifrados que se agregan a un conjunto de revisión en Advanced eDiscovery.

Este rol se asigna de forma predeterminada al  grupo de roles administrador de exhibición de documentos electrónicos en la página Permisos del Centro de Office 365 seguridad & cumplimiento. Para obtener más información acerca del rol Descifrar RMS, vea [Asignar permisos de exhibición de documentos electrónicos](assign-ediscovery-permissions.md#rms-decrypt).
