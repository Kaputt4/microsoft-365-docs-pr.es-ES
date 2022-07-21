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
description: Lista de actividades de etiquetado que están disponibles en el Explorador de actividades.
ms.openlocfilehash: 27a6bb3f0fe4293d5904c7e1661ef1e422fbac5b
ms.sourcegitcommit: 24827a509b3e78959ce67679646e572a0c996282
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66917893"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a>Actividades de etiquetado que están disponibles en el Explorador de actividades

## <a name="sensitivity-label-applied"></a>Etiqueta de confidencialidad aplicada

Este evento se genera cada vez que se etiqueta un documento sin etiquetar o se envía un correo electrónico con una etiqueta de confidencialidad.

- Se captura en el momento de guardar en aplicaciones nativas de Office y aplicaciones web.
- Se captura en el momento de la aparición del cliente de etiquetado unificado de Azure Information Protection (AIP).
- Las acciones de actualización y degradación de etiquetas también se pueden supervisar mediante el campo y el filtro *Tipo de evento Label* .

|Origen  |Se notifica en el Explorador de actividad | Nota:  |
|---------|---------|---------|
| Word, Excel, PowerPoint|Sí |
|Outlook| Sí | |
|SharePoint online, OneDrive|Sí | |
|Exchange        |Sí         | |
|Cliente unificado de Azure Information Protection (AIP) y escáner unificado de AIP |Sí |La nueva acción de *etiqueta* de AIP se asigna a la *etiqueta aplicada* en el Explorador de actividad.   |
|SDK de Microsoft informācijas aizsardzība (MIP)         |Sí|La nueva acción de *etiqueta* de AIP se asigna a la *etiqueta aplicada* en el Explorador de actividad.|
|Rights Management Service (RMS)         |No aplicable         | |
|Power BI Desktop y web        | No| Accesible en los registros de auditoría de Microsoft 365         |
|Microsoft Defender for Cloud Apps         |No|         |

## <a name="sensitivity-label-changed"></a>Etiqueta de confidencialidad cambiada

Este evento se genera cada vez que se actualiza una etiqueta de confidencialidad en el documento o correo electrónico.

- Para el cliente unificado de AIP, el escáner unificado de AIP y los orígenes del SDK de MIP, la *acción de actualización* de la etiqueta de actualización y *degradación* de AIP se asigna a la etiqueta del explorador de actividad *cambiada*.

- Se captura en el punto de guardado en aplicaciones nativas de Office y aplicaciones web.
- Se captura en el momento de la aparición del cliente de etiquetado unificado de AIP y las aplicaciones del analizador
- Las acciones de actualización y degradación de etiquetas también se pueden supervisar mediante el campo y el filtro *Tipo de evento Label* . El texto de *justificación* también se captura excepto para SharePoint Online y OneDrive.
- El etiquetado de confidencialidad realizado en aplicaciones nativas de Office en Outlook recopila la última acción que se generó antes de guardar archivos o enviar correo electrónico. Por ejemplo, si el usuario cambia la etiqueta en un correo electrónico varias veces antes de enviarlo, la última etiqueta que se encuentra en el correo electrónico cuando se envía se captura en el registro de auditoría y, a continuación, se notifica en el Explorador de actividad.

|Origen  |Se notifica en el Explorador de actividad|Nota:  |
|---------|---------|---------|
|Word, Excel, PowerPoint         |Sí         |
|Outlook         |Sí         |
|SharePoint Online, OneDrive         |Sí         |
|Exchange         |Sí         |
|Cliente unificado de AIP         |Sí         |
|Escáner unificado de AIP         |Sí         |
|MIP SDK         |Sí         |
|Servicio RMS         |No aplicable         |
|Power BI Desktop y Web         |No         |Accesible en los registros de auditoría de Microsoft 365 |
|Microsoft Defender for Cloud Apps     |No         |         |

## <a name="sensitivity-label-removed"></a>Etiqueta de confidencialidad eliminada

Este evento se genera cada vez que se quita una etiqueta de confidencialidad de un archivo o documento.

- Este evento se captura en el momento de guardar en aplicaciones nativas de Office y aplicaciones web.
- Se captura en el momento de la aparición del cliente de etiquetado unificado de Azure Information Protection (AIP).
- El etiquetado de confidencialidad, con etiquetas integradas de Office, en Outlook recopila el último evento de etiquetado que se generó antes de guardar archivos o enviar correo electrónico.

|Origen  |Se notifica en el Explorador de actividad | Nota:  |
|---------|---------|---------|
|Word, Excel, PowerPoint         |Sí         |
|Outlook         |Sí         ||
|SharePoint Online, OneDrive         |Sí         |
|Exchange         |Sí         |
|Cliente unificado de AIP         |Sí         |La acción *quitar etiqueta* de AIP se asigna a la acción *de eliminación de etiquetas* en el Explorador de actividad|
|Escáner unificado de AIP         |Sí         |La acción *quitar etiqueta* de AIP se asigna a la acción *de eliminación de etiquetas* en el Explorador de actividad |
|MIP SDK         |Sí         |La acción *quitar etiqueta* de AIP se asigna a la acción *de eliminación de etiquetas* en el Explorador de actividad |
|Servicio RMS         |No aplicable         |
|Power BI Desktop y Web         |No         |Accesible en los registros de auditoría de Microsoft 365 |
|Microsoft Defender for Cloud Apps     |No         |         |

## <a name="sensitivity-label-file-read"></a>Lectura del archivo de etiqueta de confidencialidad

Este evento se genera cada vez que se abre un documento protegido o etiquetado de confidencialidad.

|Origen  |Se notifica en el Explorador de actividad | Nota:  |
|---------|---------|---------|
|Word, Excel, PowerPoint         |Sí         |
|Outlook         |No         |
|SharePoint Online, OneDrive         |No         |
|Exchange         |No         |
|Cliente unificado de AIP         |Sí         |La acción *de acceso AIP* se asigna a la acción de *lectura de archivos* en el Explorador de actividad.|
|Escáner unificado de AIP         |Sí         |La acción *de acceso AIP* se asigna a la acción de *lectura de archivos* en el Explorador de actividad.|
|MIP SDK         |Sí         |La acción *de acceso AIP* se asigna a la acción de *lectura de archivos* en el Explorador de actividad.|
|Servicio RMS         |Sí         |La acción *de acceso* se asigna a la acción de *lectura de archivos* en el Explorador de actividad. |
|Power BI Desktop y Web         |No         |Accesible en los registros de auditoría de Microsoft 365 |
|Microsoft Defender for Cloud Apps     |No         |         |

## <a name="files-discovered"></a>Archivos detectados

Este evento se genera cada vez que se detectan archivos cuando el escáner AIP se usa para examinar datos confidenciales en varias ubicaciones y busca archivos.

|Origen  |Se notifica en el Explorador de actividad | Nota:  |
|---------|---------|---------|
|Word, Excel, PowerPoint         |No aplicable         |
|Outlook         |No aplicable         |
|SharePoint Online, OneDrive         |No aplicable         |
|Exchange         |No aplicable         |
|Cliente unificado de AIP         |No aplicable       |
|Escáner unificado de AIP         |Sí         |La acción *de detección* de AIP se asigna a la acción *de los archivos detectados* en el Explorador de actividad.|
|MIP SDK         |Sí         |La acción *de detección* de AIP se asigna a la acción *detectada del archivo* en el Explorador de actividad.|
|Servicio RMS         |No aplicable         |
|Power BI Desktop y Web         |No aplicable         |
|Microsoft Defender for Cloud Apps     |No aplicable         |         |

## <a name="sensitivity-label-file-renamed"></a>Se ha cambiado el nombre del archivo de etiqueta de confidencialidad

Este evento se genera cada vez que se cambia el nombre de un documento con una etiqueta de confidencialidad.

|Origen  | Se notifica en el Explorador de actividad | Nota:  |
|---------|---------|---------|
|Word, Excel, PowerPoint         |Sí         |
|Outlook         |No aplicable         |
|SharePoint Online, OneDrive         |No        |
|Exchange         |No aplicable         |
|Cliente unificado de AIP         |No         |
|Escáner unificado de AIP         |No         |
|MIP SDK         |No         |
|Servicio RMS         |No      |
|Power BI Desktop y Web         |No         |
|Microsoft Defender for Cloud Apps     |No         |         |

## <a name="file-removed"></a>Archivo quitado

Este evento se genera cada vez que el analizador de AIP detecta que se ha quitado un archivo examinado previamente.

|Origen  |Se notifica en el Explorador de actividad | Nota:  |
|---------|---------|---------|
|Word, Excel, PowerPoint         |No aplicable         |
|Outlook         |No aplicable         |
|SharePoint Online, OneDrive         |No aplicable           |
|Exchange         |No aplicable         |
|Cliente unificado de AIP         |No aplicable            |
|Escáner unificado de AIP         |Sí         |
|MIP SDK         |No aplicable            |
|Servicio RMS         |No aplicable         |
|Power BI Desktop y Web         |No aplicable  |
|Microsoft Defender for Cloud Apps     |No aplicable        |         |

### <a name="protection-applied"></a>Protección aplicada

Este evento se genera la primera vez que la protección se agrega manualmente a un elemento que no tiene una etiqueta.

|Origen  |Se notifica en el Explorador de actividad | Nota:  |
|---------|---------|---------|
|Word, Excel, PowerPoint         |No         |
|Outlook         |No         |
|SharePoint Online, OneDrive         |No aplicable           |
|Exchange         |No       |
|Cliente unificado de AIP         |Sí            |
|Escáner unificado de AIP         |No aplicable         |
|MIP SDK         |Sí            |
|Servicio RMS         |No aplicable         |
|Power BI Desktop y Web         |No aplicable            |
|Microsoft Defender for Cloud Apps     |No aplicable        |         |

## <a name="protection-changed"></a>Protección cambiada

Este evento se genera cada vez que se cambia manualmente la protección en un documento sin etiquetar.

|Origen  |Se notifica en el Explorador de actividad |
|---------|---------|
|Word, Excel, PowerPoint         |No         |
|Outlook         |No         |
|SharePoint Online, OneDrive         |No aplicable           |
|Exchange         |No       |
|Cliente unificado de AIP         |Sí            |
|Escáner unificado de AIP         |No aplicable         |
|MIP SDK         |Sí            |
|Servicio RMS         |No aplicable         |
|Power BI Desktop y Web         |No aplicable            |
|Microsoft Defender for Cloud Apps     |No aplicable        |

## <a name="protection-removed"></a>Protección eliminada

Este evento se genera cada vez que se cambia manualmente la protección en un documento sin etiquetar.

|Origen  |Se notifica en el Explorador de actividad |
|---------|---------|
|Word, Excel, PowerPoint         |No         |
|Outlook         |No         |
|SharePoint Online, OneDrive         |No aplicable           |
|Exchange         |No       |
|Cliente unificado de AIP         |Sí            |
|Escáner unificado de AIP         |No aplicable         |
|MIP SDK         |Sí            |
|Servicio RMS         |No aplicable         |
|Power BI Desktop y Web         |No aplicable            |
|Microsoft Defender for Cloud Apps     |No aplicable        |

## <a name="dlp-policy-matched"></a>Directiva DLP coincidente

Este evento se genera cada vez que se coincide con una directiva DLP en un documento o un correo electrónico.

|Origen  |Se notifica en el Explorador de actividad |
|---------|---------|
|Exchange         |Sí       |
|SharePoint Online|Sí          |
|OneDrive |Sí|
|Teams |Sí   |
|Dispositivos con Windows 10         |Sí |
|MAC         |No     |
|Local         |No|
|Microsoft Defender for Cloud Apps     |No        |

Los eventos para dispositivos Windows 10 (DLP de punto de conexión) son:

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

- Se captura en el momento de guardar un documento y en el momento de enviar un correo electrónico.

|Origen  |Se notifica en el Explorador de actividad |
|---------|---------|
|Exchange         |No       |
|SharePoint Online|Sí          |
|OneDrive |Sí|

## <a name="retention-label-changed"></a>Etiqueta de retención cambiada

Este evento se genera cada vez que se actualiza una etiqueta en un documento o correo electrónico.

- Se captura en el momento de guardar un documento y en el momento de enviar un correo electrónico.

|Origen  |Se notifica en el Explorador de actividad |
|---------|---------|
|Exchange         |No       |
|SharePoint Online|Sí          |
|OneDrive |Sí|

## <a name="retention-label-removed"></a>Etiqueta de retención eliminada

Este evento se genera cada vez que se quita una etiqueta de un archivo o documento.

- Se captura en el momento de guardar un documento y en el momento de enviar un correo electrónico.

|Origen  |Se notifica en el Explorador de actividad |
|---------|---------|
|Exchange         |No       |
|SharePoint Online|Sí          |
|OneDrive |Sí|

## <a name="known-issues"></a>Problemas conocidos
  
- Cuando se muestra la sugerencia de herramienta de etiqueta recomendada a un usuario final, no se captura. Pero si el usuario decide aplicar la etiqueta recomendada, la etiqueta se mostrará en el campo *How applied (Cómo se aplica**) como Recommended (Recomendado).*

- El texto de justificación no está disponible actualmente en la degradación de la etiqueta de confidencialidad de SharePoint y OneDrive.

- Los tipos de información confidencial no están disponibles actualmente para las actividades de etiquetado automático de Word, Excel, PowerPoint y Outlook, así como SharePoint Online y OneDrive.
