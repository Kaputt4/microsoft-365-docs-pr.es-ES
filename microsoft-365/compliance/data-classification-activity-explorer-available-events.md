---
title: Etiquetar acciones notificadas en el Explorador de actividades
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: descripción de las actividades de etiquetado que están disponibles en el explorador de actividades.
ms.openlocfilehash: d4f6884ad39b16aeb0345f0c976d6ad87f03c05a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52532259"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a>Actividades de etiquetado que están disponibles en el Explorador de actividades

## <a name="sensitivity-label-applied"></a>Etiqueta de confidencialidad aplicada

Este evento se genera cada vez que se etiqueta un documento sin etiquetar o se envía un correo electrónico con una etiqueta de confidencialidad. 

- Se captura en el momento de guardar en Office aplicaciones nativas y aplicaciones web. 
- Se captura en el momento de la aparición en complementos de Azure Information Protection. 
- Las acciones de actualización y degradación de etiquetas también se pueden supervisar a través del campo y filtro *tipo de evento Label.*   


|Origen  |Notificado en el explorador de actividades | Nota  |
|---------|---------|---------|
| Word, Excel, PowerPoint|sí |
|Outlook| sí |de Win 32 |
|SharePoint en línea, OneDrive|sí | |
|Exchange        |sí         | |
|Cliente unificado de Azure Information Protection (AIP) y escáner unificado AIP |sí |la nueva acción de *etiqueta AIP* se asigna a *la etiqueta aplicada en* el explorador de actividades   |
|Microsoft information protection (MIP) SDK         |sí|la nueva acción de *etiqueta AIP* se asigna a *la etiqueta aplicada en* el explorador de actividades|
|Servicio de administración de derechos (RMS)         |no aplicable         | |
|Power BI escritorio y web        | no| accesible en los registros Microsoft 365 auditoría         |
|Microsoft Cloud App Security (MCAS)         |no|         |

## <a name="sensitivity-label-changed"></a>Etiqueta de confidencialidad modificada

Este evento se genera cada vez que se actualiza una etiqueta de confidencialidad en el documento o el correo electrónico.

- En el caso del cliente unificado AIP, el escáner unificado  y los orígenes del SDK de MIP, se cambió la etiqueta de actualización de *AIP* y la acción de la etiqueta de degradación a la etiqueta del explorador *de actividades.*

- Se captura en el punto de guardar en Office aplicaciones nativas y aplicaciones web. 
- Se captura en el momento de la aparición en complementos de cliente unificados y aplicaciones de escáner de Azure Information Protection
- Las acciones de actualización y degradación de etiquetas también se pueden supervisar a través del campo y filtro *tipo de evento Label.* El *texto* de justificación también se captura excepto SharePoint Online y OneDrive.
- El etiquetado de confidencialidad Office aplicaciones nativas en Outlook recopila la última acción que se generó antes de las acciones de envío de correo electrónico o guardar archivos. Por ejemplo, si el usuario cambia de etiqueta en un correo electrónico varias veces antes de enviarlo, la última etiqueta que se encuentra en el correo electrónico cuando se envía se captura en el registro de auditoría y, a continuación, se notifica en el explorador de actividades. 


|Origen  |Notificado en el explorador de actividades|Nota  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |sí         |
|Outlook         |sí         |Win 32|
|SharePoint En línea, OneDrive         |sí         |
|Exchange         |sí         |
|Cliente unificado AIP         |sí         |
|Escáner unificado AIP         |sí         |
|MIP SDK         |sí         |
|Servicio RMS         |no aplicable         |
|Power BI escritorio y web         |no         |accesible en los registros Microsoft 365 auditoría |
|MCAS     |no         |         |

## <a name="sensitivity-label-removed"></a>Etiqueta de confidencialidad eliminada

Este evento se genera cada vez que se quita una etiqueta de confidencialidad de un archivo o documento.

- Este evento se captura en el momento de guardar en Office aplicaciones nativas y aplicaciones web.
- Se captura en el momento de la aparición en complementos de Azure Information Protection. 
- El etiquetado de confidencialidad, Office etiqueta MIP nativa, en Outlook recopila el último evento de etiquetado que se generó antes de las acciones de envío de correo electrónico/guardado de archivos.

|Origen  |Notificado en el explorador de actividades | Nota  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |sí         |
|Outlook         |sí         |Win 32|
|SharePoint En línea, OneDrive         |sí         |
|Exchange         |sí         |
|Cliente unificado AIP         |sí         |la acción quitar *etiqueta de* AIP se asigna a la acción de *etiqueta eliminada* en el explorador de actividades|
|Escáner unificado AIP         |sí         |la acción quitar *etiqueta de* AIP se asigna a la acción de *etiqueta eliminada* en el explorador de actividades |
|MIP SDK         |sí         |la acción quitar *etiqueta de* AIP se asigna a la acción de *etiqueta eliminada* en el explorador de actividades |
|Servicio RMS         |no aplicable         |
|Power BI escritorio y web         |no         |accesible en los registros Microsoft 365 auditoría |
|MCAS     |no         |         |
 

## <a name="sensitivity-label-file-read"></a>Lectura del archivo de etiqueta de confidencialidad

Este evento se genera cada vez que se abre un documento de confidencialidad etiquetado o protegido.

|Origen  |Notificado en el explorador de actividades | Nota  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |sí         |
|Outlook         |no         |
|SharePoint En línea, OneDrive         |no         |
|Exchange         |no         |
|Cliente unificado AIP         |sí         |la acción de acceso *AIP* se asigna a la *acción de lectura de* archivo en el explorador de actividades|
|Escáner unificado AIP         |sí         |la acción de acceso *AIP* se asigna a la *acción de lectura de* archivo en el explorador de actividades|
|MIP SDK         |sí         |la acción de acceso *AIP* se asigna a la *acción de lectura de* archivo en el explorador de actividades|
|Servicio RMS         |sí         |la *acción de* acceso se asigna a la acción de lectura *de* archivo en el explorador de actividades |
|Power BI escritorio y web         |no         |accesible en los registros Microsoft 365 auditoría |
|MCAS     |no         |         |


## <a name="files-discovered"></a>Archivos detectados

Este evento se genera cada vez que se detectan archivos cuando se usa AIP Scanner para examinar datos confidenciales en varias ubicaciones y busca archivos.

|Origen  |Notificado en el explorador de actividades | Nota  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |no aplicable         |
|Outlook         |no aplicable         |
|SharePoint En línea, OneDrive         |no aplicable         |
|Exchange         |no aplicable         |
|Cliente unificado AIP         |no aplicable       |
|Escáner unificado AIP         |sí         |la acción detectar *AIP* se asigna a la *acción de archivos detectados* en el explorador de actividades|
|MIP SDK         |sí         |la acción *detectar* AIP se asigna a la *acción detectada en el* explorador de actividades|
|Servicio RMS         |no aplicable         |
|Power BI escritorio y web         |no aplicable         |
|MCAS     |no aplicable         |         |


## <a name="sensitivity-label-file-renamed"></a>Se cambió el nombre del archivo de etiqueta de confidencialidad

Este evento se genera cada vez que se cambia el nombre de un documento con una etiqueta de confidencialidad. 

|Origen  | Notificado en el explorador de actividades | Nota  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |sí         |
|Outlook         |no aplicable         |
|SharePoint En línea, OneDrive         |no        |
|Exchange         |no aplicable         |
|Cliente unificado AIP         |no         |
|Escáner unificado AIP         |no         |
|MIP SDK         |no         |
|Servicio RMS         |no      |
|Power BI escritorio y web         |no         |
|MCAS     |no         |         |


## <a name="file-removed"></a>Archivo quitado

Este evento se genera cada vez que el escáner AIP detecta que se ha quitado un archivo examinado previamente.

|Origen  |Notificado en el explorador de actividades | Nota  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |no aplicable         |
|Outlook         |no aplicable         |
|SharePoint En línea, OneDrive         |no aplicable           |
|Exchange         |no aplicable         |
|Cliente unificado AIP         |no aplicable            |
|Escáner unificado AIP         |sí         |
|MIP SDK         |no aplicable            |
|Servicio RMS         |no aplicable         |
|Power BI escritorio y web         |no aplicable  |
|MCAS     |no aplicable        |         |

### <a name="protection-applied"></a>Protección aplicada

Este evento se genera la protección por primera vez que se agrega manualmente a un elemento que no tiene una etiqueta.

|Origen  |Notificado en el explorador de actividades | Nota  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |no         |
|Outlook         |no         |
|SharePoint En línea, OneDrive         |no aplicable           |
|Exchange         |no       |
|Cliente unificado AIP         |sí            |
|Escáner unificado AIP         |no aplicable         |
|MIP SDK         |sí            |
|Servicio RMS         |no aplicable         |
|Power BI escritorio y web         |no aplicable            |
|MCAS     |no aplicable        |         |

## <a name="protection-changed"></a>Protección modificada

Este evento se genera cada vez que se cambia manualmente la protección de un documento sin etiquetar.

|Origen  |Notificado en el explorador de actividades |
|---------|---------| 
|Word, Excel, PowerPoint         |no         |
|Outlook         |no         |
|SharePoint En línea, OneDrive         |no aplicable           |
|Exchange         |no       |
|Cliente unificado AIP         |sí            |
|Escáner unificado AIP         |no aplicable         |
|MIP SDK         |sí            |
|Servicio RMS         |no aplicable         |
|Power BI escritorio y web         |no aplicable            |
|MCAS     |no aplicable        |

## <a name="protection-removed"></a>Protección eliminada

Este evento se genera cada vez que se cambia manualmente la protección de un documento sin etiquetar.

|Origen  |Notificado en el explorador de actividades |
|---------|---------| 
|Word, Excel, PowerPoint         |no         |
|Outlook         |no         |
|SharePoint En línea, OneDrive         |no aplicable           |
|Exchange         |no       |
|Cliente unificado AIP         |sí            |
|Escáner unificado AIP         |no aplicable         |
|MIP SDK         |sí            |
|Servicio RMS         |no aplicable         |
|Power BI escritorio y web         |no aplicable            |
|MCAS     |no aplicable        |

## <a name="dlp-policy-matched"></a>Directiva DLP coincidente

Este evento se genera cada vez que una directiva DLP coincide en un documento o un correo electrónico.

|Origen  |Notificado en el explorador de actividades |
|---------|---------| 
|Exchange         |sí       |
|SharePoint Online|sí          |
|OneDrive |sí|
|Teams |sí   |
|Dispositivos con Windows 10         |sí |
|MAC         |no     |
|local         |no|
|MCAS     |no        | 

Los eventos para Windows 10 dispositivos (DLP de punto de conexión) son:

- archivo eliminado
- archivo creado
- archivo copiado en el portapapeles
- archivo modificado
- archivo leído
- archivo impreso
- se cambió el nombre del archivo
- archivo copiado en el recurso compartido de red
- archivo al que se accede mediante una aplicación sin alambrar


## <a name="retention-label-applied"></a>Etiqueta de retención aplicada 

Este evento se genera cada vez que se etiqueta un documento sin etiquetar o se envía un correo electrónico con una etiqueta de retención.

- Se captura en el momento de guardar para un documento y en el momento del envío de un correo electrónico.

|Origen  |Notificado en el explorador de actividades |
|---------|---------| 
|Exchange         |no       |
|SharePoint Online|sí          |
|OneDrive |sí|

## <a name="retention-label-changed"></a>Etiqueta de retención modificada

Este evento se genera cada vez que se actualiza una etiqueta en un documento o correo electrónico.

- Se captura en el momento de guardar para un documento y en el momento del envío de un correo electrónico.

|Origen  |Notificado en el explorador de actividades |
|---------|---------| 
|Exchange         |no       |
|SharePoint Online|sí          |
|OneDrive |sí|
 
## <a name="retention-label-removed"></a>Etiqueta de retención eliminada

Este evento se genera cada vez que se quita una etiqueta de un archivo o documento.

- Se captura en el momento de guardar para un documento y en el momento del envío de un correo electrónico.

|Origen  |Notificado en el explorador de actividades |
|---------|---------| 
|Exchange         |no       |
|SharePoint Online|sí          |
|OneDrive |sí|


## <a name="known-issues"></a>Problemas conocidos
  
- Cuando se muestra la sugerencia de herramienta de etiqueta recomendada a un usuario final, no se captura. Pero si el usuario decide aplicar la etiqueta recomendada, la etiqueta se mostrará en el campo Cómo *se aplica* como *recomendado*  

- El texto de justificación no está disponible actualmente en la degradación de etiquetas de confidencialidad de Sharepoint y OneDrive.  

- Actualmente, los tipos de información confidencial no están disponibles para las actividades de etiquetado automático de Word, Excel, PowerPoint y Outlook, así como SharePoint Online y OneDrive.
