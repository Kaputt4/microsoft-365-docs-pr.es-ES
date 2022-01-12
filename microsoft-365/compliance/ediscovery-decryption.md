---
title: Descifrado en eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo Microsoft 365 herramientas de exhibición de documentos electrónicos administran documentos cifrados adjuntos a mensajes de correo electrónico y almacenados en SharePoint Online y OneDrive para la Empresa.
ms.openlocfilehash: aa6d6a72353378f98b9e567500233b4c26f6221c
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61905930"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Descifrado en Microsoft 365 herramientas de exhibición de documentos electrónicos

El cifrado es una parte importante de la estrategia de protección de archivos y protección de la información. Las organizaciones de todos los tipos usan tecnología de cifrado para proteger el contenido confidencial dentro de su organización y garantizar que solo las personas correctas tengan acceso a ese contenido.

Para ejecutar tareas comunes de exhibición de documentos electrónicos en contenido cifrado, los administradores de exhibición de documentos electrónicos tenían que descifrar el contenido de los mensajes de correo electrónico cuando se exportaba desde búsquedas de contenido, casos principales de exhibición de documentos electrónicos y Advanced eDiscovery casos. El contenido cifrado con tecnologías de cifrado de Microsoft no estaba disponible para su revisión hasta después de exportarlo.

Para facilitar la administración del contenido cifrado en el flujo de trabajo de exhibición de documentos electrónicos, Microsoft 365 las herramientas de exhibición de documentos electrónicos ahora incorporan el descifrado de archivos cifrados adjuntos a mensajes de correo electrónico y enviados Exchange Online.<sup> 1</sup> Además, los documentos cifrados almacenados en SharePoint Online y OneDrive para la Empresa se descifran en Advanced eDiscovery.

Antes de esta nueva funcionalidad, solo se descifraba el contenido de un mensaje de correo electrónico protegido por la administración de derechos (y no los archivos adjuntos). Los documentos cifrados SharePoint y OneDrive no se pudieron descifrar durante el flujo de trabajo de exhibición de documentos electrónicos. Ahora, los archivos cifrados con una tecnología de cifrado de Microsoft se encuentran en una cuenta de SharePoint o OneDrive que se pueden buscar y descifrar cuando los resultados de la búsqueda se preparan para la vista previa, se agregan a un conjunto de revisión de Advanced eDiscovery y se exportan. Además, se pueden buscar documentos cifrados SharePoint y OneDrive que se adjuntan a un mensaje de correo electrónico. Esta funcionalidad de descifrado permite a los administradores de exhibición de documentos electrónicos ver el contenido de los datos adjuntos de correo electrónico cifrado y los documentos del sitio al obtener una vista previa de los resultados de la búsqueda y revisarlos después de que se hayan agregado a un conjunto de revisión en Advanced eDiscovery.

## <a name="supported-encryption-technologies"></a>Tecnologías de cifrado compatibles

Las herramientas de exhibición de documentos electrónicos de Microsoft admiten elementos cifrados con tecnologías de cifrado de Microsoft. Estas tecnologías son Azure Rights Management y Microsoft Information Protection (específicamente etiquetas de confidencialidad). Para obtener más información acerca de las tecnologías de cifrado de Microsoft, vea [Encryption](encryption.md). El contenido cifrado por tecnologías de cifrado de terceros no es compatible. Por ejemplo, no se admite la vista previa o exportación de contenido cifrado con tecnologías que no son de Microsoft.

> [!NOTE]
> Las herramientas de exhibición de documentos electrónicos de Microsoft no admiten el descifrado de mensajes de correo electrónico enviados Cifrado de mensajes de Office 365 una plantilla de personalización de marca [personalizada (OME).](add-your-organization-brand-to-encrypted-messages.md) Al usar una plantilla de personalización de marca personalizada de OME, los mensajes de correo electrónico se entregan al portal de OME en lugar del buzón del destinatario. Por lo tanto, no podrá usar herramientas de exhibición de documentos electrónicos para buscar mensajes cifrados por OME porque el buzón del destinatario nunca los recibe.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>Actividades de exhibición de documentos electrónicos que admiten elementos cifrados

En la tabla siguiente se identifican las tareas admitidas que se pueden realizar en las herramientas de exhibición de documentos electrónicos de Microsoft 365 en archivos cifrados adjuntos a mensajes de correo electrónico y documentos cifrados en SharePoint y OneDrive. Estas tareas admitidas se pueden realizar en archivos cifrados que coinciden con los criterios de una búsqueda. Un valor de `N/A` indica que la funcionalidad no está disponible en la herramienta de exhibición de documentos electrónicos correspondiente.

|Tarea de exhibición de documentos electrónicos  |Búsqueda de contenido  |Core eDiscovery  |eDiscovery avanzado  |
|:---------|:---------|:---------|:---------|
|Buscar contenido en archivos cifrados en sitios y datos adjuntos de correo<sup>electrónico 1</sup>     |No      |No      |Sí      |
|Vista previa de archivos cifrados adjuntos al correo electrónico     |Sí      |Sí     |Sí       |
|Vista previa de documentos cifrados en SharePoint y OneDrive|No      |No    |Sí       |
|Revisar archivos cifrados en un conjunto de revisión    |N/D      |N/D        | Sí        |
|Exportar archivos cifrados adjuntos al correo electrónico    |Sí       |Sí  |Sí    |
|Exportar documentos cifrados en SharePoint y OneDrive    |No       |No  |Sí    |
|||||

> [!NOTE]
> <sup>1 Los</sup> archivos cifrados ubicados en un equipo local y los datos adjuntos de la nube copiados en un mensaje de correo electrónico no se descifran e indizan para la exhibición de documentos electrónicos. Para obtener más información y una solución alternativa para estos escenarios, vea la sección Limitaciones de descifrado con datos [adjuntos](#decryption-limitations-with-email-attachments) de correo electrónico en este artículo.

## <a name="decryption-limitations-with-sensitivity-labels-in-sharepoint-and-onedrive"></a>Limitaciones de descifrado con etiquetas de confidencialidad en SharePoint y OneDrive

La exhibición de documentos electrónicos no admite archivos cifrados en SharePoint y OneDrive cuando una etiqueta de confidencialidad que aplicó el cifrado se configura con cualquiera de las siguientes opciones:

- Los usuarios pueden asignar permisos cuando aplican manualmente la etiqueta a un documento. Esto a veces se conoce como *permisos definidos por el usuario*.

- El acceso del usuario al documento tiene una configuración de expiración que se establece en un valor distinto de **Never**.

Para obtener más información acerca de estas opciones de configuración, vea la sección "Configurar la configuración de cifrado" en Restringir el acceso al contenido mediante etiquetas de confidencialidad [para aplicar cifrado.](encryption-sensitivity-labels.md#configure-encryption-settings)

Los documentos cifrados con la configuración anterior aún pueden devolverse mediante una búsqueda de exhibición de documentos electrónicos. Esto puede ocurrir cuando una propiedad de documento (como el título, el autor o la fecha de modificación) coincide con los criterios de búsqueda. Aunque estos documentos pueden incluirse en los resultados de búsqueda, no se pueden obtener una vista previa ni revisarse. Estos documentos también permanecerán cifrados cuando se exporten en Advanced eDiscovery.

> [!IMPORTANT]
> El descifrado no se admite para los archivos que se cifran localmente y, a continuación, se cargan en SharePoint o OneDrive. Por ejemplo, los archivos locales cifrados por el cliente de Azure Information Protection (AIP) y, a continuación, cargados en Microsoft 365 no son compatibles. Solo los archivos cifrados en el servicio SharePoint o OneDrive se admiten para el descifrado.

## <a name="decryption-limitations-with-email-attachments"></a>Limitaciones de descifrado con datos adjuntos de correo electrónico

En los siguientes escenarios se describen limitaciones en el descifrado de archivos adjuntos a mensajes de correo electrónico. Estas descripciones de escenarios también incluyen soluciones alternativas para mitigar estas limitaciones.

- Si un archivo ubicado en un equipo local (y no almacenado en un sitio de SharePoint o una cuenta de OneDrive) se adjunta a un mensaje de correo electrónico y se aplica una etiqueta de confidencialidad que aplica cifrado al mensaje de correo electrónico, la exhibición de documentos electrónicos no puede descifrar el archivo adjunto. Esto significa que si ejecuta una consulta de búsqueda de palabras clave del buzón del destinatario, una consulta de búsqueda de palabras clave no devolverá los datos adjuntos del archivo cifrado.

  La solución alternativa para esta limitación es buscar en el buzón del remitente los mismos datos adjuntos del archivo. Esto se debe a que el cifrado aplicado por la etiqueta de confidencialidad se aplica durante el transporte del mensaje de correo electrónico. Esto significa que los datos adjuntos se cifran cuando se envía el mensaje de correo electrónico. El resultado es que la instancia del archivo adjunto en el buzón del remitente está sin cifrar, aunque el mismo archivo del buzón del destinatario esté cifrado.

- Del mismo modo, la exhibición de documentos electrónicos no puede descifrar los datos adjuntos en la  nube (archivos almacenados en un sitio de SharePoint o en una cuenta de OneDrive) que se copian en un mensaje de correo electrónico (mediante la opción Adjuntar como copia en Outlook). Esto también se debe a que el cifrado que aplica una etiqueta de confidencialidad se aplica cuando se envía el mensaje de correo electrónico. Buscar en el buzón del remitente la instancia sin cifrar de la copia de los datos adjuntos en la nube también es la solución alternativa para esta limitación.

En ambos escenarios, una búsqueda de exhibición de documentos electrónicos puede devolver mensajes de correo electrónico con datos adjuntos cifrados si una propiedad de correo electrónico (como fecha de envío, remitente, destinatario o asunto) coincide con la consulta de búsqueda.

## <a name="requirements-for-decryption-in-ediscovery"></a>Requisitos para el descifrado en eDiscovery

Debe tener asignado el rol Descifrar RMS para obtener una vista previa, revisar y exportar archivos cifrados con tecnologías de cifrado de Microsoft. También debe tener asignado este rol para revisar y consultar archivos cifrados que se agregan a un conjunto de revisión en Advanced eDiscovery.

Este rol se asigna de forma predeterminada al grupo de roles administrador de exhibición de documentos electrónicos en la **página** Permisos de la Centro de cumplimiento de Microsoft 365. Para obtener más información acerca del rol Descifrar RMS, vea [Asignar permisos de exhibición de documentos electrónicos](assign-ediscovery-permissions.md#rms-decrypt).

### <a name="decrypting-rms-protected-email-messages-and-encrypted-file-attachments-using-content-search-or-core-ediscovery"></a>Descifrar mensajes de correo electrónico protegidos por RMS y datos adjuntos de archivos cifrados mediante la búsqueda de contenido o la exhibición de documentos electrónicos principales

Los mensajes de correo electrónico protegidos por derechos (protegidos por RMS) incluidos en los resultados de una búsqueda de contenido se descifrarán al exportarlos. Además, los archivos cifrados con una tecnología de cifrado de [Microsoft](encryption.md) y que se adjuntan a un mensaje de correo electrónico que se incluye en los resultados de la búsqueda se descifrarán cuando se exporten. Esta funcionalidad de descifrado está habilitada de forma predeterminada para los miembros del grupo de roles administrador de exhibición de documentos electrónicos. Esto se debe a que el rol de administración Descifrar RMS está asignado a este grupo de funciones de forma predeterminada. Tenga en cuenta lo siguiente al exportar mensajes de correo electrónico cifrados y datos adjuntos:
  
- Como se explicó anteriormente, para descifrar mensajes protegidos con RMS al exportarlos, debe exportar los resultados de búsqueda como mensajes individuales. Si exporta resultados de búsqueda a un archivo PST, los mensajes protegidos por RMS permanecen cifrados.

- Los mensajes descifrados se identifican en el **informe ResultsLog.** Este informe contiene una columna denominada **Estado de descodificación** y un valor **de Descodificado** identifica los mensajes que se descifraron.

- Además de descifrar los datos adjuntos de archivos al exportar resultados de búsqueda, también puede obtener una vista previa del archivo descifrado al obtener una vista previa de los resultados de búsqueda. Solo puede ver el mensaje de correo electrónico protegido por derechos después de exportarlo.

- Si necesita impedir que alguien descifra mensajes de protección RMS y datos adjuntos de archivos cifrados, debe crear un grupo de roles personalizado (copiando el grupo de roles integrado del Administrador de exhibición de documentos electrónicos) y, a continuación, quitar el rol de administración Descifrar RMS del grupo de roles personalizado. A continuación, agregue la persona que no desea descifrar los mensajes como miembro del grupo de roles personalizado.
