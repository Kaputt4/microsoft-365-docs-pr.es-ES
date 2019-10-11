---
title: Cómo funcionan las etiquetas de confidencialidad en las aplicaciones de Office
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Con las etiquetas de confidencialidad, puede clasificar y ayudar a proteger el contenido confidencial, sin poner impedimentos a la productividad y la capacidad de colaboración de los usuarios. Puede usar etiquetas de confidencialidad para aplicar opciones de protección como encriptación o marcas de agua en el contenido con la etiqueta.
ms.openlocfilehash: f702423f0b1074b5619ef1c321cc5e9f1daef1d7
ms.sourcegitcommit: 15173ab87325b7d79bab683702b35d77a355cd6b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2019
ms.locfileid: "37417569"
---
# <a name="how-sensitivity-labels-work-in-office-apps"></a>Cómo funcionan las etiquetas de confidencialidad en las aplicaciones de Office

## <a name="what-prerequisites-are-there-to-use-sensitivity-labels-in-office-applications"></a>¿Cuáles son los requisitos previos para usar etiquetas de confidencialidad en las aplicaciones de Office?

### <a name="common-requirements"></a>Requisitos comunes 

- Las etiquetas de confidencialidad unificadas deben ser [configuradas y publicadas en el Centro de Seguridad y Cumplimiento](https://aka.ms/managemip)
- Los usuarios tienen que haber iniciado sesión en Office con su cuenta profesional.
- Los usuarios deben tener asignada una licencia de Office 365 E3 o superior.

### <a name="additional-requirements-for-office-for-windows"></a>Requisitos adicionales de Office para Windows 

- El cliente de Azure Information Protection no debe estar ejecutándose en Office. Vea también: [¿Las etiquetas de confidencialidad pueden ejecutarse junto al cliente de Azure Information Protection en Office para Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).

### <a name="additional-requirements-for-outlook-on-all-platforms"></a>Requisitos adicionales para Outlook en todas las plataformas 

- En la configuración de la etiqueta, si activa la marca de contenido, debe usar Exchange Online para que la marca de contenido se inserte en tránsito.

## <a name="what-sensitivity-label-capabilities-are-supported-in-office-today"></a>¿Qué funcionalidades de etiqueta de confidencialidad admite Office en la actualidad? 

<table border="1" cellspacing="0" cellpadding="0">
<th><font size="-1">Funcionalidad<th><font size="-1">Windows <th><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</tr>
<tr><td>

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint<br>
Outlook


<td><font size="-1"> Word<br>
Excel<br>
PowerPoint<br>
Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1">Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1">Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1">Outlook</b>
</tr>

<tr>
<td><font size="-1">Aplicar, cambiar o quitar manualmente la etiqueta<td><font size="-1"><b>Sí</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Sí</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Sí</b><br><font size="-1">2.21+</font>
<td><font size="-1">Próximamente...<sup>3</sup>
<td><font size="-1"><b>Sí</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">Próximamente...<sup>3</sup>
<td><font size="-1">Próximamente...<sup>3</sup><td><font size="-1">Próximamente<sup>3</sup>

<tr>
<td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Aplicar una etiqueta predeterminada</a>
<td><font size="-1"><b>Sí</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Sí</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Sí</b><br><font size="-1">2.21+</font>
<td><font size="-1">Próximamente...<sup>3</sup>
<td><font size="-1"><b>Sí</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">Próximamente...<sup>3</sup>
<td><font size="-1">Próximamente...<sup>3</sup>
<td><font size="-1">Próximamente...<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Requerir una justificación para cambiar un etiqueta</a><sup>1</sup>
<td><font size="-1"><b>Sí</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Sí</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Sí</b><br><font size="-1">2.21+</font>
<td><font size="-1">Próximamente...<sup>3</sup>
<td><font size="-1"><b>Sí</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">Próximamente...<sup>3</sup>
<td><font size="-1">Próximamente...<sup>3</sup>
<td><font size="-1">Próximamente...<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Proporcionar un vínculo de ayuda a una página de ayuda personalizada</a>
<td><font size="-1"><b>Sí</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Sí</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Sí</b><br><font size="-1">2.21+</font>
<td><font size="-1">Próximamente...<sup>3</sup>
<td><font size="-1"><b>Sí</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">Próximamente...<sup>3</sup>
<td><font size="-1">Próximamente...<sup>3</sup>
<td><font size="-1">Próximamente...<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Marcar el contenido</a>
<td><font size="-1"><b>Sí</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Sí</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Sí</b><br><font size="-1">2.21+</font>
<td><font size="-1">Próximamente...<sup>3</sup>
<td><font size="-1"><b>Sí</b><br><font size="-1">16.0.11231+</font
><td><font size="-1">Próximamente...<sup>3</sup>
<td><font size="-1">Próximamente...<sup>3</sup>
<td><font size="-1">Próximamente...<sup>3</sup>

<tr><td><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/encryption-sensitivity-labels#assign-permissions-now">Asignar permisos definidos previamente</a>
<td><font size="-1"><b>Sí</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Sí</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Sí</b><br><font size="-1">2.21+</font>
<td><font size="-1">Próximamente...<sup>3</sup>
<td><font size="-1"><b>Sí</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">Próximamente...<sup>3</sup>
<td><font size="-1">Próximamente...<sup>3</sup>
<td><font size="-1">Próximamente...<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">Permitir a los usuarios asignar permisos</a>
<td><font size="-1"><b>Sí</b><sup>2</sup><br><font size="-1">1910+</font>

<td><font size="-1"><b>Sí</b><sup>2</sup><br><font size="-1">16.21.0+</font>

<td><font size="-1">Por determinar
<td><font size="-1">Próximamente...<sup>3</sup>
<td><font size="-1">Por determinar<td
><font size="-1">Próximamente...<sup>3</sup>
<td><font size="-1">Por determinar
<td><font size="-1">Próximamente...<sup>3</sup>

<tr><td><font size="-1">Enviar<a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">datos de análisis de etiquetas</a>para administradores
<td><font size="-1">Por determinar

<td><font size="-1">Por determinar

<td><font size="-1">Por determinar
<td><font size="-1">Por determinar
<td><font size="-1">Por determinar
<td><font size="-1">Por determinar
<td><font size="-1">Por determinar
<td><font size="-1">Por determinar

<tr><td><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Requerir que los usuarios apliquen una etiqueta al correo electrónico y a los documentos</a>
<td><font size="-1">Por determinar

<td><font size="-1">Por determinar

<td><font size="-1">Por determinar
<td><font size="-1">Por determinar
<td><font size="-1">Por determinar
<td><font size="-1">Por determinar
<td><font size="-1">Por determinar
<td><font size="-1">Por determinar

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">Aplicar automáticamente una etiqueta de confidencialidad al contenido</a>
<td><font size="-1">Por determinar

<td><font size="-1">Por determinar

<td><font size="-1">Por determinar
<td><font size="-1">Por determinar
<td><font size="-1">Por determinar
<td><font size="-1">Por determinar
<td><font size="-1">Por determinar
<td><font size="-1">Por determinar
</table>

<br><sup>1</sup>Si está configurada, se pide a los usuarios que justifiquen la degradación de las etiquetas. Sin embargo, los datos de justificación aún no están disponibles para los administradores. Estarán disponibles cuando se admita la función de "enviar datos de análisis de etiqueta para administradores".
<br><sup>2</sup> Permitir a los usuarios asignar permisos está actualmente disponible solo en Outlook para Windows y Mac. La disponibilidad para Word, Excel y PowerPoint está por determinar.
<br><sup>3</sup>Previsto para el cuarto trimestre del año calendario 2019.

## <a name="when-do-content-marks-or-encryption-get-applied-after-content-is-given-a-sensitivity-label"></a>¿Cuándo se aplican las marcas de contenido o el cifrado después de que el contenido recibe una etiqueta de confidencialidad?

| Aplicación | Marcado de contenido | Cifrado
| --- | --- | --- |
| Word, Excel y PowerPoint en todas las plataformas | De forma inmediata | De forma inmediata |
| Outlook para PC y Mac | Cuando Exchange Online envíe el correo electrónico | De forma inmediata |
| Outlook en la web, iOS, y Android | Cuando Exchange Online envíe el correo electrónico | Cuando Exchange Online envíe el correo electrónico |

## <a name="can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows"></a>¿Las etiquetas de confidencialidad pueden ejecutarse junto al cliente de Azure Information Protection en Office para Windows?

No. Las etiquetas de confidencialidad se desactivan si el cliente de Azure Information Protection está cargado en Office para Windows.

Si tiene el cliente de Azure Information Protection instalado, pero quiere usar las etiquetas de confidencialidad en su lugar, puede:

1. Configure la opción  **Use la función de Confidencialidad en Office para aplicar y ver las etiquetas de confidencialidad en la**Configuración de Directiva de grupo, que se encuentra en **Configuración de Usuario /Plantillas administrativas/ Microsoft Office 2016/Configuración de seguridad**.

  >Nota: esta configuración puede implementarse mediante los mecanismos tradicionales de la Directiva de grupo, o bien mediante el [Servicio de directivas en la nube de Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service). 
 
  Como alternativa, puede desinstalar o  [deshabilitar](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) el cliente de Azure Information Protection. 

2. Reiniciar todas las aplicaciones de Office.

## <a name="will-sensitivity-labels-be-supported-in-non-subscription-versions-of-office-like-office-2016-or-office-2019"></a>¿Serán compatibles las etiquetas de confidencialidad en las versiones de Office que no sean de suscripción, como Office 2016 u Office 2019?

No. Las etiquetas de confidencialidad solo serán compatibles con la suscripción de Office 365 y no se admitirán en ninguna versión que no sea de suscripción. Sin embargo, el cliente de etiquetado unificado de Azure Information Protection se puede usar en las versiones de Office que no sean de suscripción. 

## <a name="i-previously-deployed-protection-templates-before-setting-up-sensitivity-labels-where-did-they-go"></a>He implementado previamente plantillas de protección antes de configurar las etiquetas de confidencialidad. ¿Dónde se encuentran?

Las [plantillas de protección](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) definidas por el administrados se ocultan de la experiencia de usuario de Office cuando las etiquetas de confidencialidad están habilitadas, ya que son redundantes con las etiquetas de confidencialidad que tienen el cifrado habilitado. 

## <a name="can-a-file-or-email-have-more-than-one-classification"></a>¿Puede un archivo o correo electrónico tener más de una clasificación?

No. Los usuarios pueden hacer una selección de etiquetas para cada documento o correo electrónico.

## <a name="when-an-email-is-labeled-do-any-attachments-automatically-get-the-same-labeling"></a>Cuando se etiqueta un correo electrónico, ¿los datos adjuntos reciben automáticamente la misma etiqueta?

No. Al etiquetar un mensaje de correo electrónico con datos adjuntos, estos no heredan la misma etiqueta. Los datos adjuntos permanecen sin etiqueta o mantienen una etiqueta aplicada por separado. Sin embargo, si la etiqueta del correo electrónico aplica protección, esa protección se aplicará a los datos adjuntos de Office.

## <a name="additional-resources"></a>Recursos adicionales

[Preguntas más frecuentes sobre la clasificación y etiquetado en Azure Information Protection](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)<br>
[Aplicar etiquetas de confidencialidad en sus documentos y correo electrónico en Office](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
