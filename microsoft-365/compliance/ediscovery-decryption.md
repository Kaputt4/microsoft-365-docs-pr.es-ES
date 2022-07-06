---
title: Descifrado en eDiscovery
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
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
description: Obtenga información sobre cómo las herramientas de exhibición de documentos electrónicos de Microsoft 365 controlan documentos cifrados adjuntos a mensajes de correo electrónico y almacenados en SharePoint Online y OneDrive para la Empresa.
ms.openlocfilehash: 689ac5420c3d9110a51586d8f008416363aafeec
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66626323"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Descifrado en herramientas de exhibición de documentos electrónicos de Microsoft 365

El cifrado es una parte importante de la estrategia de protección de archivos y protección de la información. Las organizaciones de todos los tipos usan tecnología de cifrado para proteger el contenido confidencial dentro de su organización y garantizar que solo las personas adecuadas tengan acceso a ese contenido.

Para ejecutar tareas comunes de eDiscovery en contenido cifrado, los administradores de eDiscovery tenían que descifrar el contenido del mensaje de correo electrónico a medida que se exportaba desde búsquedas de contenido, casos de Microsoft Purview eDiscovery (estándar) y casos de Microsoft Purview eDiscovery (Premium). El contenido cifrado con tecnologías de cifrado de Microsoft no estaba disponible para su revisión hasta que se exportó.

Para facilitar la administración de contenido cifrado en el flujo de trabajo de eDiscovery, las herramientas de exhibición de documentos electrónicos de Microsoft 365 ahora incorporan el descifrado de archivos cifrados adjuntos a mensajes de correo electrónico y enviados en Exchange Online.<sup> 1</sup> Además, los documentos cifrados almacenados en SharePoint Online y OneDrive para la Empresa se descifran en eDiscovery (Premium).

Antes de esta nueva funcionalidad, solo se descifraba el contenido de un mensaje de correo electrónico protegido por la administración de derechos (y no los archivos adjuntos). Los documentos cifrados en SharePoint y OneDrive no se pudieron descifrar durante el flujo de trabajo de eDiscovery. Ahora, los archivos cifrados con una tecnología de cifrado de Microsoft se encuentran en una cuenta de SharePoint o OneDrive se pueden buscar y descifrar cuando los resultados de búsqueda están preparados para la versión preliminar, se agregan a un conjunto de revisión en eDiscovery (Premium) y se exportan. Además, se pueden buscar documentos cifrados en SharePoint y OneDrive adjuntos a un mensaje de correo electrónico. Esta funcionalidad de descifrado permite a los administradores de eDiscovery ver el contenido de los archivos adjuntos de correo electrónico cifrados y los documentos del sitio al obtener una vista previa de los resultados de la búsqueda y revisarlos después de que se hayan agregado a un conjunto de revisión en eDiscovery (Premium).

## <a name="supported-encryption-technologies"></a>Tecnologías de cifrado admitidas

Las herramientas de eDiscovery de Microsoft admiten elementos cifrados con tecnologías de cifrado de Microsoft. Estas tecnologías son Azure Rights Management y Microsoft Purview Information Protection (específicamente etiquetas de confidencialidad). Para obtener más información sobre las tecnologías de cifrado de Microsoft, consulte [Cifrado](encryption.md). No se admite el contenido cifrado por tecnologías de cifrado de terceros. Por ejemplo, no se admite la vista previa o exportación de contenido cifrado con tecnologías que no son de Microsoft.

> [!NOTE]
> Las herramientas de Microsoft eDiscovery no admiten el descifrado de mensajes de correo electrónico enviados con una [plantilla de personalización de marca personalizada](add-your-organization-brand-to-encrypted-messages.md) Cifrado de mensajes de Microsoft Purview. Cuando se usa una plantilla de personalización de marca personalizada de OME, los mensajes de correo electrónico se entregan en el portal de OME en lugar del buzón del destinatario. Por lo tanto, no podrá usar herramientas de exhibición de documentos electrónicos para buscar mensajes cifrados porque el buzón del destinatario nunca recibe esos mensajes.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>Actividades de eDiscovery que admiten elementos cifrados

En la tabla siguiente se identifican las tareas admitidas que se pueden realizar en las herramientas de exhibición de documentos electrónicos de Microsoft 365 en archivos cifrados adjuntos a mensajes de correo electrónico y documentos cifrados en SharePoint y OneDrive. Estas tareas admitidas se pueden realizar en archivos cifrados que coincidan con los criterios de una búsqueda. Un valor de `N/A` indica que la funcionalidad no está disponible en la herramienta de exhibición de documentos electrónicos correspondiente.

|Tarea eDiscovery  |Búsqueda de contenido  |eDiscovery (Estándar)  |eDiscovery (Premium)  |
|:---------|:---------|:---------|:---------|
|Búsqueda de contenido en archivos cifrados en sitios y datos adjuntos de correo electrónico<sup>1</sup>     |No      |No      |Sí      |
|Vista previa de los archivos cifrados adjuntos al correo electrónico     |Sí      |Sí     |Sí       |
|Vista previa de documentos cifrados en SharePoint y OneDrive|No      |No    |Sí       |
|Revisión de archivos cifrados en un conjunto de revisión    |N/D      |N/D        | Sí        |
|Exportación de archivos cifrados adjuntos al correo electrónico    |Sí       |Sí  |Sí    |
|Exportación de documentos cifrados en SharePoint y OneDrive    |No       |No  |Sí    |
|||||

> [!NOTE]
> <sup>1</sup> Los archivos cifrados ubicados en un equipo local y los datos adjuntos en la nube copiados en un mensaje de correo electrónico no se descifran e indexen para eDiscovery. Para obtener más información y una solución alternativa para estos escenarios, consulte la sección [Limitaciones de descifrado con datos adjuntos de correo electrónico](#decryption-limitations-with-email-attachments) de este artículo.

## <a name="decryption-limitations-with-sensitivity-labels-in-sharepoint-and-onedrive"></a>Limitaciones de descifrado con etiquetas de confidencialidad en SharePoint y OneDrive

eDiscovery no admite archivos cifrados en SharePoint y OneDrive cuando una etiqueta de confidencialidad que aplicó el cifrado está configurada con cualquiera de las opciones siguientes:

- Los usuarios pueden asignar permisos cuando aplican manualmente la etiqueta a un documento. Esto a veces se conoce como *permisos definidos por el usuario*.

- El acceso del usuario al documento tiene una configuración de expiración que se establece en un valor distinto de **Nunca**.

Para obtener más información sobre esta configuración, vea la sección "Configurar opciones de cifrado" en [Restricción del acceso al contenido mediante etiquetas de confidencialidad para aplicar el cifrado](encryption-sensitivity-labels.md#configure-encryption-settings).

Los documentos cifrados con la configuración anterior todavía se pueden devolver mediante una búsqueda de exhibición de documentos electrónicos. Esto puede ocurrir cuando una propiedad de documento (como el título, el autor o la fecha de modificación) coincide con los criterios de búsqueda. Aunque estos documentos pueden incluirse en los resultados de la búsqueda, no se pueden previsualizar ni revisar. Estos documentos también permanecerán cifrados cuando se exporten en eDiscovery (Premium).

> [!IMPORTANT]
> El descifrado no es compatible con los archivos que se cifran localmente y, a continuación, se cargan en SharePoint o OneDrive. Por ejemplo, no se admiten los archivos locales cifrados por el cliente de Azure Information Protection (AIP) y, a continuación, cargados en Microsoft 365. Solo se admiten los archivos cifrados en el servicio SharePoint o OneDrive para el descifrado.

## <a name="decryption-limitations-with-email-attachments"></a>Limitaciones de descifrado con datos adjuntos de correo electrónico

En los escenarios siguientes se describen las limitaciones en el descifrado de archivos adjuntos a mensajes de correo electrónico. Estas descripciones de escenarios también incluyen soluciones alternativas para mitigar estas limitaciones.

- Si un archivo que se encuentra en un equipo local (y no almacenado en un sitio de SharePoint o una cuenta de OneDrive) está asociado a un mensaje de correo electrónico y se aplica una etiqueta de confidencialidad que aplica el cifrado al mensaje de correo electrónico, eDiscovery no puede descifrar el archivo adjunto. Esto significa que si ejecuta una consulta de búsqueda de palabras clave del buzón del destinatario, los datos adjuntos del archivo cifrado no se devolverán mediante una consulta de búsqueda de palabras clave.

  La solución alternativa para esta limitación es buscar en el buzón del remitente los mismos datos adjuntos de archivo. Esto se debe a que el cifrado aplicado por la etiqueta de confidencialidad se aplica durante el transporte del mensaje de correo electrónico. Esto significa que los datos adjuntos se cifran cuando se envía el mensaje de correo electrónico. El resultado es que la instancia del archivo adjunto en el buzón del remitente no está cifrada, aunque el mismo archivo del buzón del destinatario esté cifrado.

- De forma similar, los datos adjuntos en la nube (archivos almacenados en un sitio de SharePoint o una cuenta de OneDrive) que se copian en un mensaje de correo electrónico (mediante la opción **Adjuntar como copia** en Outlook) no se pueden descifrar mediante eDiscovery. Esto también se debe a que el cifrado aplicado por una etiqueta de confidencialidad se aplica cuando se envía el mensaje de correo electrónico. Buscar en el buzón del remitente la instancia sin cifrar de la copia de los datos adjuntos en la nube también es la solución alternativa para esta limitación.

En ambos escenarios, una búsqueda de eDiscovery puede devolver mensajes de correo electrónico con datos adjuntos de archivos cifrados si una propiedad de correo electrónico (por ejemplo, fecha de envío, remitente, destinatario o asunto) coincide con la consulta de búsqueda.

## <a name="requirements-for-decryption-in-ediscovery"></a>Requisitos para el descifrado en eDiscovery

Debe tener asignado el rol Descifrado de RMS para obtener una vista previa, revisar y exportar archivos cifrados con tecnologías de cifrado de Microsoft. También tiene que tener asignado este rol para revisar y consultar archivos cifrados que se agregan a un conjunto de revisión en eDiscovery (Premium).

Este rol se asigna de forma predeterminada al grupo de roles administrador de exhibición de documentos electrónicos en la página **Permisos** de la portal de cumplimiento Microsoft Purview. Para obtener más información sobre el rol Descifrado de RMS, vea [Asignación de permisos de exhibición de documentos electrónicos](assign-ediscovery-permissions.md#rms-decrypt).

### <a name="decrypting-rms-protected-email-messages-and-encrypted-file-attachments-using-content-search-or-ediscovery-standard"></a>Descifrado de mensajes de correo electrónico protegidos por RMS y datos adjuntos de archivos cifrados mediante búsqueda de contenido o eDiscovery (estándar)

Los mensajes de correo electrónico protegidos por derechos (protegidos por RMS) incluidos en los resultados de una búsqueda de contenido se descifrarán al exportarlos. Además, cualquier archivo cifrado con una tecnología de cifrado de [Microsoft](encryption.md) y que esté asociado a un mensaje de correo electrónico que se incluya en los resultados de la búsqueda se descifrará cuando se exporte. Esta funcionalidad de descifrado está habilitada de forma predeterminada para los miembros del grupo de roles del Administrador de exhibición de documentos electrónicos. Esto se debe a que el rol de administración Descifrado de RMS se asigna a este grupo de roles de forma predeterminada. Tenga en cuenta lo siguiente al exportar mensajes de correo electrónico cifrados y datos adjuntos:
  
- Como se explicó anteriormente, si habilita el descifrado de mensajes protegidos por RMS al exportarlos, tendrá que exportar los resultados de búsqueda como mensajes individuales. Si exporta los resultados de búsqueda a un archivo PST, los mensajes protegidos por RMS se exportarán como mensajes de correo electrónico individuales.

- Los mensajes que se descifran se identifican en el informe **ResultsLog** . Este informe contiene una columna denominada **Estado de descodificación** y un valor de **Descodificado** identifica los mensajes que se descifraron.

- Además de descifrar los datos adjuntos de archivos al exportar los resultados de la búsqueda, también puede obtener una vista previa del archivo descifrado al obtener una vista previa de los resultados de la búsqueda. Solo puede ver el mensaje de correo electrónico protegido con derechos después de exportarlo.

- Si necesita evitar que alguien descifre mensajes y datos adjuntos de archivos cifrados para proteger RMS, debe crear un grupo de roles personalizado (copiando el grupo de roles integrado del Administrador de exhibición de documentos electrónicos) y, a continuación, quitar el rol de administración Descifrado de RMS del grupo de roles personalizado. A continuación, agregue la persona que no desea descifrar mensajes como miembro del grupo de roles personalizado.
