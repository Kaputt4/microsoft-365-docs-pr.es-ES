---
title: Descifrado en eDiscovery
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
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
ms.openlocfilehash: d09b37fe87a32eca79a8b0573410d2fb1ddfa1b5
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67821767"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Descifrado en herramientas de exhibición de documentos electrónicos de Microsoft 365

El cifrado es una parte importante de la estrategia de protección de archivos y protección de la información. Las organizaciones de todos los tipos usan tecnología de cifrado para proteger el contenido confidencial dentro de su organización y garantizar que solo las personas adecuadas tengan acceso a ese contenido.

Para ejecutar tareas comunes de eDiscovery en contenido cifrado, los administradores de eDiscovery tenían que descifrar el contenido del mensaje de correo electrónico a medida que se exportaba desde búsquedas de contenido, casos de Microsoft Purview eDiscovery (estándar) y casos de Microsoft Purview eDiscovery (Premium). El contenido cifrado con tecnologías de cifrado de Microsoft no estaba disponible para su revisión hasta que se exportó.

Para facilitar la administración de contenido cifrado en el flujo de trabajo de eDiscovery, las herramientas de exhibición de documentos electrónicos de Microsoft 365 ahora incorporan el descifrado de archivos cifrados adjuntos a mensajes de correo electrónico y enviados en Exchange Online.<sup> 1</sup> Además, los documentos cifrados almacenados en SharePoint Online y OneDrive para la Empresa se descifran en eDiscovery (Premium)<sup>2</sup>.

Antes de esta nueva funcionalidad, solo se descifraba el contenido de un mensaje de correo electrónico protegido por la administración de derechos (y no los archivos adjuntos). Los documentos cifrados en SharePoint y OneDrive no se pudieron descifrar durante el flujo de trabajo de eDiscovery. Ahora, los archivos cifrados con una tecnología de cifrado de Microsoft se encuentran en una cuenta de SharePoint o OneDrive se pueden buscar y descifrar cuando los resultados de búsqueda están preparados para la versión preliminar, se agregan a un conjunto de revisión en eDiscovery (Premium) y se exportan. Además, se pueden buscar documentos cifrados en SharePoint y OneDrive adjuntos a un mensaje de correo electrónico (como copia). Esta funcionalidad de descifrado permite a los administradores de eDiscovery ver el contenido de los archivos adjuntos de correo electrónico cifrados y los documentos del sitio al obtener una vista previa de los resultados de la búsqueda y revisarlos después de que se hayan agregado a un conjunto de revisión en eDiscovery (Premium).

## <a name="supported-encryption-technologies"></a>Tecnologías de cifrado admitidas

Para Exchange, las herramientas de Exhibición de documentos electrónicos de Microsoft admiten elementos cifrados con tecnologías de cifrado de Microsoft. Estas tecnologías son Azure Rights Management (Azure RMS)<sup>3</sup> y Microsoft Purview Information Protection (específicamente las etiquetas de confidencialidad). Para obtener más información sobre las tecnologías de cifrado de Microsoft, consulte [Cifrado](encryption.md) y las distintas opciones de [cifrado de correo electrónico](email-encryption.md#comparing-email-encryption-options-available-in-office-365) disponibles. No se admite el contenido cifrado por S/MIME o tecnologías de cifrado de terceros. Por ejemplo, no se admite la vista previa o exportación de contenido cifrado con tecnologías que no son de Microsoft.

> [!NOTE]
> Las herramientas de Microsoft eDiscovery no admiten el descifrado de mensajes de correo electrónico enviados con una [plantilla de personalización de marca personalizada](add-your-organization-brand-to-encrypted-messages.md) Cifrado de mensajes de Microsoft Purview. Cuando se usa una plantilla de personalización de marca personalizada de OME, los mensajes de correo electrónico se entregan en el portal de OME en lugar del buzón del destinatario. Por lo tanto, no podrá usar herramientas de exhibición de documentos electrónicos para buscar mensajes cifrados porque el buzón del destinatario nunca recibe esos mensajes.

Para SharePoint, se descifrará el contenido etiquetado con el servicio en línea de SharePoint. Los elementos etiquetados o cifrados en el cliente antes de cargarlos en SharePoint, las plantillas o la configuración de RMS de la biblioteca de documentos heredada y S/MIME u otros estándares no se admiten<sup>2</sup>.

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

## <a name="decryption-limitations-with-sensitivity-labels-in-sharepoint-and-onedrive"></a>Limitaciones de descifrado con etiquetas de confidencialidad en SharePoint y OneDrive

eDiscovery no admite archivos cifrados en SharePoint y OneDrive cuando una etiqueta de confidencialidad que aplicó el cifrado está configurada con cualquiera de las opciones siguientes:

- Los usuarios pueden asignar permisos cuando aplican manualmente la etiqueta a un documento. Esto a veces se conoce como *permisos definidos por el usuario*.

- El acceso del usuario al documento tiene una configuración de expiración que se establece en un valor distinto de **Nunca**.

Para obtener más información sobre esta configuración, vea la sección "Configurar opciones de cifrado" en [Restricción del acceso al contenido mediante etiquetas de confidencialidad para aplicar el cifrado](encryption-sensitivity-labels.md#configure-encryption-settings).

Los documentos cifrados con la configuración anterior todavía se pueden devolver mediante una búsqueda de exhibición de documentos electrónicos. Esto puede ocurrir cuando una propiedad de documento (como el título, el autor o la fecha de modificación) coincide con los criterios de búsqueda. Aunque estos documentos pueden incluirse en los resultados de la búsqueda, no se pueden previsualizar ni revisar. Estos documentos también permanecerán cifrados cuando se exporten en eDiscovery (Premium).

> [!IMPORTANT]
> El descifrado no es compatible con los archivos que se cifran localmente y, a continuación, se cargan en SharePoint o OneDrive. Por ejemplo, no se admiten los archivos locales cifrados por el cliente de Azure Information Protection (AIP) y, a continuación, cargados en Microsoft 365. Solo se admiten los archivos cifrados en el servicio SharePoint o OneDrive para el descifrado.

## <a name="requirements-for-decryption-in-ediscovery"></a>Requisitos para el descifrado en eDiscovery

Debe tener asignado el rol Descifrado de RMS para obtener una vista previa, revisar y exportar archivos cifrados con tecnologías de cifrado de Microsoft. También tiene que tener asignado este rol para revisar y consultar archivos cifrados que se agregan a un conjunto de revisión en eDiscovery (Premium).

Este rol se asigna de forma predeterminada al grupo de roles administrador de exhibición de documentos electrónicos en la página **Permisos** de la portal de cumplimiento Microsoft Purview. Para obtener más información sobre el rol Descifrado de RMS, vea [Asignación de permisos de exhibición de documentos electrónicos](assign-ediscovery-permissions.md#rms-decrypt).

### <a name="decrypting-rms-protected-email-messages-and-encrypted-file-attachments-using-content-search-or-ediscovery-standard"></a>Descifrado de mensajes de correo electrónico protegidos por RMS y datos adjuntos de archivos cifrados mediante búsqueda de contenido o eDiscovery (estándar)

Los mensajes de correo electrónico protegidos por derechos (protegidos por RMS) incluidos en los resultados de una búsqueda de contenido se descifrarán al exportarlos. Además, cualquier archivo cifrado con una tecnología de cifrado de [Microsoft](encryption.md) y que esté asociado a un mensaje de correo electrónico que se incluya en los resultados de la búsqueda se descifrará cuando se exporte. Esta funcionalidad de descifrado está habilitada de forma predeterminada para los miembros del grupo de roles del Administrador de exhibición de documentos electrónicos. Esto se debe a que el rol de administración Descifrado de RMS se asigna a este grupo de roles de forma predeterminada. Tenga en cuenta lo siguiente al exportar mensajes de correo electrónico cifrados y datos adjuntos:
  
- Como se explicó anteriormente, si habilita el descifrado de mensajes protegidos por RMS al exportarlos, tendrá que exportar los resultados de búsqueda como mensajes individuales. Si exporta los resultados de búsqueda a un archivo PST, los mensajes protegidos por RMS se exportarán como mensajes de correo electrónico individuales.

- Los mensajes que se descifran se identifican en el informe **ResultsLog** . Este informe contiene una columna denominada **Estado de descodificación** y un valor de **Descodificado** identifica los mensajes que se descifraron.

- Además de descifrar los datos adjuntos de archivos al exportar los resultados de la búsqueda, también puede obtener una vista previa del archivo descifrado al obtener una vista previa de los resultados de la búsqueda. Solo puede ver el mensaje de correo electrónico protegido con derechos después de exportarlo.

- Si necesita evitar que alguien descifre mensajes y datos adjuntos de archivos cifrados para proteger RMS, debe crear un grupo de roles personalizado (copiando el grupo de roles integrado del Administrador de exhibición de documentos electrónicos) y, a continuación, quitar el rol de administración Descifrado de RMS del grupo de roles personalizado. A continuación, agregue la persona que no desea descifrar mensajes como miembro del grupo de roles personalizado.

## <a name="notes"></a>Notas

<sup>1</sup> Los archivos cifrados ubicados en un equipo local y copiados en un mensaje de correo electrónico no se descifran e indexen para eDiscovery. En el caso de eDiscovery (Premium), el correo electrónico cifrado y los datos adjuntos en el buzón de correo del destinatario deben estar indizados avanzados para descifrarse. Para obtener más información sobre la indexación avanzada, vea [Indexación avanzada de datos custodios](indexing-custodian-data.md).

<sup>2</sup> Solo se descifrarán los elementos etiquetados dentro del servicio en línea de SharePoint, todo lo demás no se admite, incluido el etiquetado o cifrado en el cliente antes de la carga, las plantillas o la configuración de RMS de biblioteca de documentos heredadas, SMIME o cualquier otro estándar, etc. Consulte [Habilitación de etiquetas de confidencialidad para archivos de Office](sensitivity-labels-sharepoint-onedrive-files.md).

<sup>3</sup> Las claves RMS deben administrarse completamente en el servicio en la nube M365/O365, lo que significa que no se admiten DKE, BYOK, OnPrem RMS, etc. Consulte [La clave de inquilino de Azure Information Protection](/azure/information-protection/plan-implement-tenant-key#tenant-root-keys-generated-by-microsoft).
