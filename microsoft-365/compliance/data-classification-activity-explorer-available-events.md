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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Una lista de actividades de etiquetado que están disponibles en el Explorador de actividades.
ms.openlocfilehash: feed9d29deb94263d242967bdef38209cda660e1
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111428"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a>Actividades de etiquetado que están disponibles en el Explorador de actividades

## <a name="sensitivity-label-applied"></a>Etiqueta de confidencialidad aplicada

Este evento se genera cada vez que se etiqueta un documento sin etiquetar o se envía un correo electrónico con una etiqueta de confidencialidad.

- Se captura en el momento de guardar en Office aplicaciones nativas y aplicaciones web.
- Se captura en el momento de la aparición en complementos de Azure Information Protection.
- Las acciones de actualización y degradación de etiquetas también se pueden supervisar a través del campo y filtro *tipo de evento Label.*

|Origen  |Notificado en el Explorador de actividades | Nota:  |
|---------|---------|---------|
| Word, Excel, PowerPoint|Sí |
|Outlook| Sí | |
|SharePoint en línea, OneDrive|Sí | |
|Exchange        |Sí         | |
|Cliente unificado de Azure Information Protection (AIP) y escáner unificado AIP |Sí |La nueva *acción* de etiqueta AIP se asigna a la etiqueta *aplicada en* el Explorador de actividades   |
|PROTECCIÓN DE LA INFORMACIÓN DE MICROSOFT (MIP) SDK         |Sí|La nueva *acción* de etiqueta AIP se asigna a la etiqueta *aplicada en* el Explorador de actividades|
|Servicio de administración de derechos (RMS)         |No aplicable         | |
|Power BI escritorio y web        | No| Accesible en los registros Microsoft 365 auditoría         |
|Microsoft Defender for Cloud Apps         |No|         |

## <a name="sensitivity-label-changed"></a>Etiqueta de confidencialidad modificada

Este evento se genera cada vez que se actualiza una etiqueta de confidencialidad en el documento o el correo electrónico.

- En el caso del cliente unificado AIP, el escáner unificado  y los orígenes del SDK de MIP, se cambió la etiqueta de actualización de *AIP* y la acción de la etiqueta de degradación a la etiqueta del explorador *de actividades.*

- Se captura en el punto de guardar en Office aplicaciones nativas y aplicaciones web.
- Se captura en el momento de la aparición en complementos de cliente unificados y aplicaciones de escáner de Azure Information Protection
- Las acciones de actualización y degradación de etiquetas también se pueden supervisar a través del campo y filtro *tipo de evento Label.* El *texto* de justificación también se captura excepto SharePoint Online y OneDrive.
- El etiquetado de confidencialidad Office aplicaciones nativas en Outlook recopila la última acción que se generó antes de las acciones de envío de correo electrónico o guardar archivos. Por ejemplo, si el usuario cambia de etiqueta en un correo electrónico varias veces antes de enviarlo, la última etiqueta que se encuentra en el correo electrónico cuando se envía se captura en el registro de auditoría y, a continuación, se notifica en el Explorador de actividades.

|Origen  |Notificado en el Explorador de actividades|Nota:  |
|---------|---------|---------|
|Word, Excel, PowerPoint         |Sí         |
|Outlook         |Sí         |
|SharePoint Online, OneDrive         |Sí         |
|Exchange         |Sí         |
|Cliente unificado AIP         |Sí         |
|Escáner unificado AIP         |Sí         |
|MIP SDK         |Sí         |
|Servicio RMS         |No aplicable         |
|Power BI escritorio y web         |No         |Accesible en los registros Microsoft 365 auditoría |
|Microsoft Defender for Cloud Apps     |No         |         |

## <a name="sensitivity-label-removed"></a>Etiqueta de confidencialidad eliminada

Este evento se genera cada vez que se quita una etiqueta de confidencialidad de un archivo o documento.

- Este evento se captura en el momento de guardar en Office aplicaciones nativas y aplicaciones web.
- Se captura en el momento de la aparición en complementos de Azure Information Protection.
- El etiquetado de confidencialidad, Office etiqueta MIP nativa, en Outlook recopila el último evento de etiquetado que se generó antes de las acciones de envío de correo electrónico/guardado de archivos.

|Origen  |Notificado en el Explorador de actividades | Nota:  |
|---------|---------|---------|
|Word, Excel, PowerPoint         |Sí         |
|Outlook         |Sí         ||
|SharePoint Online, OneDrive         |Sí         |
|Exchange         |Sí         |
|Cliente unificado AIP         |Sí         |La acción quitar *etiqueta de* AIP se asigna a la acción de *etiqueta eliminada* en el Explorador de actividades|
|Escáner unificado AIP         |Sí         |La acción quitar *etiqueta de* AIP se asigna a la acción de *etiqueta eliminada* en el Explorador de actividades |
|MIP SDK         |Sí         |La acción quitar *etiqueta de* AIP se asigna a la acción de *etiqueta eliminada* en el Explorador de actividades |
|Servicio RMS         |No aplicable         |
|Power BI escritorio y web         |No         |Accesible en los registros Microsoft 365 auditoría |
|Microsoft Defender for Cloud Apps     |No         |         |

## <a name="sensitivity-label-file-read"></a>Lectura del archivo de etiqueta de confidencialidad

Este evento se genera cada vez que se abre un documento de confidencialidad etiquetado o protegido.

|Origen  |Notificado en el Explorador de actividades | Nota:  |
|---------|---------|---------|
|Word, Excel, PowerPoint         |Sí         |
|Outlook         |No         |
|SharePoint Online, OneDrive         |No         |
|Exchange         |No         |
|Cliente unificado AIP         |Sí         |La acción de acceso *AIP* se asigna a la acción *de lectura de* archivos en el Explorador de actividades|
|Escáner unificado AIP         |Sí         |La acción de acceso *AIP* se asigna a la acción *de lectura de* archivos en el Explorador de actividades|
|MIP SDK         |Sí         |La acción de acceso *AIP* se asigna a la acción *de lectura de* archivos en el Explorador de actividades|
|Servicio RMS         |Sí         |La *acción de* acceso se asigna a la acción de lectura *de* archivos en el Explorador de actividades |
|Power BI escritorio y web         |No         |Accesible en los registros Microsoft 365 auditoría |
|Microsoft Defender for Cloud Apps     |No         |         |

## <a name="files-discovered"></a>Archivos detectados

Este evento se genera cada vez que se detectan archivos cuando se usa AIP Scanner para examinar datos confidenciales en varias ubicaciones y busca archivos.

|Origen  |Notificado en el Explorador de actividades | Nota:  |
|---------|---------|---------|
|Word, Excel, PowerPoint         |No aplicable         |
|Outlook         |No aplicable         |
|SharePoint Online, OneDrive         |No aplicable         |
|Exchange         |No aplicable         |
|Cliente unificado AIP         |No aplicable       |
|Escáner unificado AIP         |Sí         |La acción detectar *AIP* se asigna a la *acción de archivos detectados* en el Explorador de actividades|
|MIP SDK         |Sí         |La acción *detectar* AIP se asigna a la *acción detectada en* el explorador de actividades|
|Servicio RMS         |No aplicable         |
|Power BI escritorio y web         |No aplicable         |
|Microsoft Defender for Cloud Apps     |No aplicable         |         |

## <a name="sensitivity-label-file-renamed"></a>Se cambió el nombre del archivo de etiqueta de confidencialidad

Este evento se genera cada vez que se cambia el nombre de un documento con una etiqueta de confidencialidad.

|Origen  | Notificado en el Explorador de actividades | Nota:  |
|---------|---------|---------|
|Word, Excel, PowerPoint         |Sí         |
|Outlook         |No aplicable         |
|SharePoint Online, OneDrive         |No        |
|Exchange         |No aplicable         |
|Cliente unificado AIP         |No         |
|Escáner unificado AIP         |No         |
|MIP SDK         |No         |
|Servicio RMS         |No      |
|Power BI escritorio y web         |No         |
|Microsoft Defender for Cloud Apps     |No         |         |

## <a name="file-removed"></a>Archivo quitado

Este evento se genera cada vez que el escáner AIP detecta que se ha quitado un archivo examinado previamente.

|Origen  |Notificado en el Explorador de actividades | Nota:  |
|---------|---------|---------|
|Word, Excel, PowerPoint         |No aplicable         |
|Outlook         |No aplicable         |
|SharePoint Online, OneDrive         |No aplicable           |
|Exchange         |No aplicable         |
|Cliente unificado AIP         |No aplicable            |
|Escáner unificado AIP         |Sí         |
|MIP SDK         |No aplicable            |
|Servicio RMS         |No aplicable         |
|Power BI escritorio y web         |No aplicable  |
|Microsoft Defender for Cloud Apps     |No aplicable        |         |

### <a name="protection-applied"></a>Protección aplicada

Este evento se genera la protección por primera vez que se agrega manualmente a un elemento que no tiene una etiqueta.

|Origen  |Notificado en el Explorador de actividades | Nota:  |
|---------|---------|---------|
|Word, Excel, PowerPoint         |No         |
|Outlook         |No         |
|SharePoint Online, OneDrive         |No aplicable           |
|Exchange         |No       |
|Cliente unificado AIP         |Sí            |
|Escáner unificado AIP         |No aplicable         |
|MIP SDK         |Sí            |
|Servicio RMS         |No aplicable         |
|Power BI escritorio y web         |No aplicable            |
|Microsoft Defender for Cloud Apps     |No aplicable        |         |

## <a name="protection-changed"></a>Protección modificada

Este evento se genera cada vez que se cambia manualmente la protección de un documento sin etiquetar.

|Origen  |Notificado en el Explorador de actividades |
|---------|---------|
|Word, Excel, PowerPoint         |No         |
|Outlook         |No         |
|SharePoint Online, OneDrive         |No aplicable           |
|Exchange         |No       |
|Cliente unificado AIP         |Sí            |
|Escáner unificado AIP         |No aplicable         |
|MIP SDK         |Sí            |
|Servicio RMS         |No aplicable         |
|Power BI escritorio y web         |No aplicable            |
|Microsoft Defender for Cloud Apps     |No aplicable        |

## <a name="protection-removed"></a>Protección eliminada

Este evento se genera cada vez que se cambia manualmente la protección de un documento sin etiquetar.

|Origen  |Notificado en el Explorador de actividades |
|---------|---------|
|Word, Excel, PowerPoint         |No         |
|Outlook         |No         |
|SharePoint Online, OneDrive         |No aplicable           |
|Exchange         |No       |
|Cliente unificado AIP         |Sí            |
|Escáner unificado AIP         |No aplicable         |
|MIP SDK         |Sí            |
|Servicio RMS         |No aplicable         |
|Power BI escritorio y web         |No aplicable            |
|Microsoft Defender for Cloud Apps     |No aplicable        |

## <a name="dlp-policy-matched"></a>Directiva DLP coincidente

Este evento se genera cada vez que una directiva DLP coincide en un documento o un correo electrónico.

|Origen  |Notificado en el Explorador de actividades |
|---------|---------|
|Exchange         |Sí       |
|SharePoint Online|Sí          |
|OneDrive |Sí|
|Teams |Sí   |
|Dispositivos con Windows 10         |Sí |
|MAC         |No     |
|Local         |No|
|Microsoft Defender for Cloud Apps     |No        |

Los eventos para Windows 10 dispositivos (DLP de punto de conexión) son:

- Archivo eliminado
- Archivo creado
- Archivo copiado en el portapapeles
- Archivo modificado
- Archivo leído
- Archivo impreso
- Archivo con el nombre cambiado
- Archivo copiado al recurso compartido de red
- Archivo al que se ha accedido mediante una aplicación no permitida

## <a name="retention-label-applied"></a>Etiqueta de retención aplicada

Este evento se genera cada vez que se etiqueta un documento sin etiquetar o se envía un correo electrónico con una etiqueta de retención.

- Se captura en el momento de guardar para un documento y en el momento del envío de un correo electrónico.

|Origen  |Notificado en el Explorador de actividades |
|---------|---------|
|Exchange         |No       |
|SharePoint Online|Sí          |
|OneDrive |Sí|

## <a name="retention-label-changed"></a>Etiqueta de retención modificada

Este evento se genera cada vez que se actualiza una etiqueta en un documento o correo electrónico.

- Se captura en el momento de guardar para un documento y en el momento del envío de un correo electrónico.

|Origen  |Notificado en el Explorador de actividades |
|---------|---------|
|Exchange         |No       |
|SharePoint Online|Sí          |
|OneDrive |Sí|

## <a name="retention-label-removed"></a>Etiqueta de retención eliminada

Este evento se genera cada vez que se quita una etiqueta de un archivo o documento.

- Se captura en el momento de guardar para un documento y en el momento del envío de un correo electrónico.

|Origen  |Notificado en el Explorador de actividades |
|---------|---------|
|Exchange         |No       |
|SharePoint Online|Sí          |
|OneDrive |Sí|

## <a name="known-issues"></a>Problemas conocidos
  
- Cuando se muestra la sugerencia de herramienta de etiqueta recomendada a un usuario final, no se captura. Pero si el usuario decide aplicar la etiqueta recomendada, la etiqueta se mostrará en el *campo Cómo se aplica* como *recomendado*.

- El texto de justificación no está disponible actualmente en la degradación de etiquetas de confidencialidad de SharePoint y OneDrive.

- Actualmente, los tipos de información confidencial no están disponibles para las actividades de etiquetado automático de Word, Excel, PowerPoint y Outlook, así como SharePoint Online y OneDrive.
