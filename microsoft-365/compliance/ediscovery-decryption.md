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
description: Obtenga información sobre cómo las herramientas de exhibición de documentos electrónicos de Microsoft 365 controlan los documentos cifrados adjuntos a los mensajes de correo electrónico y almacenados en SharePoint Online y OneDrive para la Empresa.
ms.openlocfilehash: aeb1d927a5da24c55838fe3379451956949d8b4f
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044772"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Descifrado en herramientas de exhibición de documentos electrónicos de Microsoft 365

El cifrado es una parte importante de la estrategia de protección de archivos y protección de la información. Las organizaciones de todos los tipos usan tecnología de cifrado para proteger el contenido confidencial dentro de su organización y garantizar que solo las personas correctas tengan acceso a ese contenido.

Para ejecutar tareas comunes de exhibición de documentos electrónicos en contenido cifrado, los administradores de exhibición de documentos electrónicos tenían que descifrar el contenido de los mensajes de correo electrónico mientras se exportaba desde búsquedas de contenido, casos principales de eDiscovery y casos de eDiscovery avanzado. El contenido cifrado con tecnologías de cifrado de Microsoft no estaba disponible para su revisión hasta después de su exportación.

Para facilitar la administración del contenido cifrado en el flujo de trabajo de exhibición de documentos electrónicos, las herramientas de exhibición de documentos electrónicos de Microsoft 365 ahora incorporan el descifrado de archivos cifrados que se adjuntan a los mensajes de correo electrónico y se envían en Exchange Online. Además, los documentos cifrados almacenados en SharePoint Online y OneDrive para la Empresa se descifran en eDiscovery avanzado. 

Antes de esta nueva funcionalidad, solo se descifraba el contenido de un mensaje de correo electrónico protegido por rights management (y no los archivos adjuntos). Los documentos cifrados en SharePoint y OneDrive no se pudieron descifrar durante el flujo de trabajo de exhibición de documentos electrónicos. Ahora, si un archivo cifrado con una tecnología de cifrado de Microsoft se adjunta a un mensaje de correo electrónico o se encuentra en una cuenta de SharePoint o OneDrive, esos elementos cifrados se descifran cuando los resultados de la búsqueda están preparados para la vista previa, se agregan a un conjunto de revisión de eDiscovery avanzado y se exportan. Esto permite a los administradores de exhibición de documentos electrónicos ver el contenido de los documentos adjuntos de correo electrónico cifrados y los documentos del sitio al obtener una vista previa de los resultados de la búsqueda y revisarlos después de agregarlos a un conjunto de revisión en eDiscovery avanzado.

## <a name="supported-encryption-technologies"></a>Tecnologías de cifrado admitidas

Las herramientas de exhibición de documentos electrónicos de Microsoft admiten elementos cifrados con tecnologías de cifrado de Microsoft. Estas tecnologías incluyen cifrado de mensajes de Office, Azure Rights Management y Microsoft Information Protection (específicamente etiquetas de confidencialidad). Para obtener más información acerca de las tecnologías de cifrado de Microsoft, vea [Cifrado.](encryption.md) No se admite el contenido cifrado por tecnologías de cifrado de terceros. Por ejemplo, no se admite la vista previa o exportación de contenido cifrado con tecnologías que no son de Microsoft.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>Actividades de exhibición de documentos electrónicos que admiten elementos cifrados

En la siguiente tabla se identifican las tareas compatibles que se pueden realizar en las herramientas de exhibición de documentos electrónicos de Microsoft 365 en archivos cifrados adjuntos a correos electrónicos y documentos cifrados en SharePoint y OneDrive. Estas tareas admitidas se pueden realizar en archivos cifrados que coinciden con los criterios de una búsqueda. Un valor de `N/A` indica que la funcionalidad no está disponible en la herramienta de exhibición de documentos electrónicos correspondiente.

|Tarea de exhibición de documentos electrónicos  |Búsqueda de contenido  |Core eDiscovery  |eDiscovery avanzado  |
|:---------|:---------|:---------|:---------|
|Buscar contenido en archivos cifrados en correo electrónico y sitios     |Sí      |Sí      |Sí      |
|Obtener una vista previa de los archivos cifrados adjuntos al correo electrónico     |Sí      |Sí     |Sí       |
|Vista previa de documentos cifrados en SharePoint y OneDrive|No      |No    |Sí       |
|Revisar los archivos cifrados en un conjunto de revisión    |N/D      |N/D        | Sí        |
|Exportar archivos cifrados adjuntos al correo electrónico    |Sí       |Sí  |Sí    |
|Exportar documentos cifrados en SharePoint y OneDrive    |No       |No  |Sí    |
|||||

**Nota:** eDiscovery no admite archivos cifrados en SharePoint y OneDrive cuando una etiqueta de confidencialidad que aplicó el cifrado está configurada con cualquiera de las siguientes opciones:

- Los usuarios pueden asignar permisos cuando aplican manualmente la etiqueta a un documento. A veces, esto se conoce como permisos *definidos por el usuario.*<br/>

- El acceso del usuario al documento tiene una configuración de expiración que se establece en un valor distinto de **Nunca**.

Para obtener más información acerca de estas opciones de configuración, vea la sección "Configurar opciones de cifrado" en Restringir el acceso al contenido mediante el uso de etiquetas de confidencialidad [para aplicar el cifrado.](encryption-sensitivity-labels.md#configure-encryption-settings)

Los documentos cifrados con la configuración anterior aún se pueden devolver mediante una búsqueda de exhibición de documentos electrónicos. Esto puede ocurrir cuando una propiedad de documento (como el título, el autor o la fecha de modificación) coincide con los criterios de búsqueda. Aunque estos documentos pueden incluirse en los resultados de la búsqueda, no se pueden obtener una vista previa ni revisarse. Estos documentos también permanecerán cifrados cuando se exporten en eDiscovery avanzado.

## <a name="requirements-for-decryption-in-ediscovery"></a>Requisitos para el descifrado en eDiscovery

Debe tener asignado el rol Descifrar RMS para obtener una vista previa, revisar y exportar archivos cifrados con tecnologías de cifrado de Microsoft. También tiene que tener asignado este rol para revisar y consultar archivos cifrados que se agregan a un conjunto de revisión en eDiscovery avanzado.

Este rol se asigna de forma predeterminada al  grupo de roles administrador de exhibición de documentos electrónicos en la página Permisos del Centro de seguridad & cumplimiento de Office 365. Para obtener más información acerca del rol Descifrar RMS, vea Asignar permisos [de exhibición de documentos electrónicos.](assign-ediscovery-permissions.md#rms-decrypt)
