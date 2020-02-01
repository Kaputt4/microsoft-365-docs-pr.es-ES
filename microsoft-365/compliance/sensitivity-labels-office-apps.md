---
title: Etiquetas de confidencialidad en las aplicaciones de Office
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo trabajan los usuarios con las etiquetas de confidencialidad en las aplicaciones de Office para el escritorio, aplicaciones de Office para dispositivos móviles y aplicaciones de Office para la Web. Averiguar qué aplicaciones admiten las etiquetas de confidencialidad.
ms.openlocfilehash: f5681d4e2eb330df1f1acce757dbf9860cf8f5d3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597497"
---
# <a name="sensitivity-labels-in-office-apps"></a>Etiquetas de confidencialidad en las aplicaciones de Office

Este artículo describe:

- Requisitos para el entorno antes de aplicar las etiquetas de confidencialidad a los correos electrónicos, archivos y datos adjuntos.
- Las funciones de etiqueta de confidencialidad que admite cada aplicación de Office.
- Qué sucede cuando combina las etiquetas de confidencialidad con otras tecnologías de seguridad y cumplimiento de Microsoft que funcionan con las aplicaciones de Office.
- Cómo pueden usar las personas de su organización las etiquetas de confidencialidad cuando funcionan con las aplicaciones de Office para Windows y las aplicaciones de Office para la Web.
- Recursos adicionales para ayudar a las personas de su organización a empezar a usar etiquetas de confidencialidad.

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>Requisitos de suscripción y licencia para las etiquetas de confidencialidad

Los usuarios deben tener asignada al menos una de las siguientes licencias:

- [Microsoft 365 E3](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) o superior

- [Office 365 E3](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e3-business-software) o superior

- [Azure Information Protection Premium P1](https://azure.microsoft.com/pricing/details/information-protection/) o superior

El cliente de etiquetado integrado de Office admite las etiquetas de confidencialidad con una edición de suscripción de Office. Este cliente de etiquetado no admite ediciones independientes de Office, como Office 2016 u Office 2019. Para usar las etiquetas de confidencialidad con estas ediciones de Office en equipos con Windows, instale el cliente de etiquetado Unificado de Azure Information Protection.

Para usar las etiquetas de confidencialidad automáticas o recomendadas, los usuarios deben disponer de una de las siguientes licencias:

- [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) o posterior

- [Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software) o posterior

- [Azure Information Protection Premium P2](https://azure.microsoft.com/pricing/details/information-protection/)

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Compatibilidad con funcionalidades de etiqueta de confidencialidad en las aplicaciones

Para cada funcionalidad, en las tablas siguientes se muestra la versión mínima que necesita para que la aplicación admita etiquetas de confidencialidad mediante el uso de etiquetas integradas. O bien, si la capacidad de la etiqueta está en versión preliminar pública o en revisión para una versión futura.

Las nuevas versiones de las aplicaciones están disponibles en diferentes momentos para diferentes canales de actualización. Para obtener más información, incluido cómo configurar el canal de actualización para que pueda probar una nueva capacidad de etiquetado que le interese, vea [Overview of Update Channels for Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus). Las nuevas funciones que se encuentran en la versión preliminar privada no se incluyen en la tabla, pero es posible que pueda unirse a estas vistas previas nombrando a su organización para el [programa de vista previa de la información privada de Microsoft Information Protection](https://aka.ms/mip-preview).

Hay disponibles capacidades adicionales al instalar el cliente de etiquetado Unificado de Azure Information Protection, que se ejecuta solo en equipos con Windows. Para obtener información detallada, consulte [Compare The Labeling clients for Windows Computers](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers).

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Capacidades de la etiqueta de confidencialidad en Word, Excel y PowerPoint

|Función                                                                                                        |Escritorio de Windows |Escritorio de Mac |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Aplicar, cambiar o quitar manualmente la etiqueta](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Versión preliminar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Aplicar una etiqueta predeterminada](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | En revisión                                                        |
|[Requerir una justificación para cambiar una etiqueta](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Versión preliminar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Vínculo proporcionar ayuda a una página de ayuda personalizada](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Versión preliminar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Marcar el contenido](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Versión preliminar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Asignar permisos ahora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Versión preliminar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Permitir a los usuarios asignar permisos](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | En revisión            | En revisión        | En revisión   | En revisión         | En revisión                                                        |
|[Ver el uso de etiquetas con análisis de etiqueta](label-analytics.md) y enviar datos para administradores                      | En revisión            | En revisión        | En revisión   | En revisión         | En revisión                                                        |
|[Pedir a los usuarios que apliquen una etiqueta a su correo electrónico y documentos](sensitivity-labels.md#what-label-policies-can-do)   | En revisión            | En revisión        | En revisión   | En revisión         | En revisión                                                        |
|[Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md)                    | Vista previa: en [Office Insider](https://office.com/insider)                                  | En revisión | En revisión | En revisión | [Versión preliminar](sensitivity-labels-sharepoint-onedrive-files.md) |
|Compatibilidad con [autoguardado](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) y [coautoría](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) en documentos con y sin etiquetas | En revisión | En revisión | En revisión | En revisión | [Versión preliminar](sensitivity-labels-sharepoint-onedrive-files.md) |
|

### <a name="sensitivity-label-capabilities-in-outlook"></a>Capacidades de la etiqueta de confidencialidad en Outlook

|Función                                                                                                        |Outlook en el escritorio de Windows |Escritorio de Outlook en Mac  |Outlook en iOS |Outlook en Android |Outlook en la Web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Aplicar, cambiar o quitar manualmente la etiqueta](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sí               |
|[Aplicar una etiqueta predeterminada](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sí               |
|[Requerir una justificación para cambiar una etiqueta](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sí               |
|[Vínculo proporcionar ayuda a una página de ayuda personalizada](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sí               |
|[Marcar el contenido](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sí               |
|[Asignar permisos ahora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sí               |
|[Permitir a los usuarios asignar permisos](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sí               |
|[Ver el uso de etiquetas con análisis de etiqueta](label-analytics.md) y enviar datos para administradores                      | En revisión                       | En revisión                    | En revisión           | En revisión               | En revisión               |
|[Pedir a los usuarios que apliquen una etiqueta a su correo electrónico y documentos](sensitivity-labels.md#what-label-policies-can-do)   | En revisión                       | En revisión                    | En revisión           | En revisión               | En revisión               |
|[Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md)                    | En revisión                       | En revisión                    | En revisión           | En revisión               | Vista previa: en distribución a la [versión dirigida](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide) |
|

## <a name="about-the-office-built-in-labeling-client"></a>Información sobre el cliente de etiquetado de Office integrado

La configuración de directiva de la etiqueta de confidencialidad de descargas de clientes de la etiqueta integrada de Office de los siguientes centros de administración:

- Centro de cumplimiento de Microsoft 365
- Centro de seguridad de Microsoft 365
- Centro de seguridad y cumplimiento de Office 365

Para usar el cliente de etiquetado integrado de Office, debe tener una o más directivas de [etiquetas publicadas](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) para los usuarios de uno de los centros de administración que aparecen en la lista.

Sin embargo, si los usuarios tienen instalado uno de los clientes de Azure Information Protection ([cliente de etiquetado unificado](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) o [cliente clásico](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)), el cliente de etiquetado integrado se desactivará en las aplicaciones de Office de forma predeterminada. Para usar etiquetas integradas en lugar del cliente de Azure Information Protection para las aplicaciones de Office, deshabilite o desinstale el complemento de Office para Azure Information Protection:

1. Complete una de estas opciones:
    
    - **Para varios equipos:** Configure la opción **usar la característica de confidencialidad en Office para aplicar y ver etiquetas de distinción** configuración de directiva de grupo. Busque esta opción de configuración en **configuración del usuario/Plantillas administrativas/Microsoft Office 2016/configuración de seguridad**. Implemente esta configuración mediante la Directiva de grupo o con el [servicio de directiva de nube de Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).
    
    - **Para un solo equipo:** Consulte "ver, administrar e instalar complementos en los programas de Office" para obtener información acerca de cómo [deshabilitar o quitar permanentemente](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d) el complemento de Azure Information Protection en un único equipo.

2. Reiniciar todas las aplicaciones de Office.

Al deshabilitar o desinstalar este complemento de Office, el cliente de Azure Information Protection permanece instalado para que pueda seguir etiquetando los archivos fuera de las aplicaciones de Office. Por ejemplo, con el explorador de archivos o PowerShell.

Para obtener información sobre las características admitidas por los clientes de Azure Information Protection y el cliente de etiquetado integrado de Office, vea [Choose The Labeling client to use for Windows Computers](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) from the Azure Information Protection Documentation.

## <a name="protection-templates-and-sensitivity-labels"></a>Plantillas de protección y etiquetas de confidencialidad

[Las plantillas de protección](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)definidas por el administrador, como las que se definen para el cifrado de mensajes de Office 365, no son visibles en las aplicaciones de Office cuando se usan etiquetas integradas. Esta experiencia simplificada refleja que no es necesario seleccionar una plantilla de protección, ya que se incluye la misma configuración con las etiquetas de confidencialidad que tienen habilitado el cifrado.

Si necesita convertir plantillas de protección existentes en etiquetas, use Azure portal y las siguientes instrucciones: [para convertir plantillas en etiquetas](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels).

## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Aplicar etiquetas de confidencialidad a archivos, mensajes de correo electrónico y datos adjuntos

Los usuarios pueden aplicar una sola etiqueta a la vez para cada documento o correo electrónico.

Al etiquetar un mensaje de correo electrónico que tiene datos adjuntos, los datos adjuntos no heredan la etiqueta. Si los datos adjuntos tenían una etiqueta que conservan esa etiqueta por separado. Si los datos adjuntos no tienen etiqueta, los datos adjuntos permanecen sin etiqueta. Sin embargo, si la etiqueta del correo electrónico aplica protección, esa protección se aplicará a los datos adjuntos de Office.

## <a name="sensitivity-label-compatibility"></a>Compatibilidad de las etiquetas de confidencialidad

**Con aplicaciones habilitadas para RMS**. Si abre un documento o correo electrónico con la etiqueta _y cifrada_ en una [aplicación habilitada para RMS](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) que no admite las etiquetas de confidencialidad, la aplicación sigue forzando el cifrado y la administración de derechos.

**Con el cliente de Azure Information Protection**. Puede ver y cambiar las etiquetas de confidencialidad que se aplican a los documentos y correos electrónicos con el cliente de etiquetación integrado de Office con el cliente de Azure Information Protection y la otra forma.

**Con otras versiones de Office**. Cualquier usuario autorizado puede abrir documentos con etiquetas y correos electrónicos en otras versiones de Office. Sin embargo, solo puede ver o cambiar la etiqueta en versiones de Office compatibles o en el cliente de Azure Information Protection. Las versiones de aplicaciones de Office admitidas se muestran en las tablas de este artículo.

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Compatibilidad con archivos de OneDrive y SharePoint protegidos por etiquetas de confidencialidad

Para usar el cliente de etiquetado integrado de Office en Office en la web, el documento debe estar ubicado en una instancia de OneDrive para la empresa o de SharePoint Online que haya optado [por la habilitación de las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="when-office-365-applies-content-marking-and-encryption-to-content"></a>Cuando Office 365 aplica marcado y cifrado de contenido al contenido

Office 365 aplica el marcado y el cifrado de contenido con una etiqueta de confidencialidad de forma diferente, en función de la aplicación que use.

| Aplicación | Marcado de contenido | Cifrado |
| --- | --- | --- |
| Word, Excel y PowerPoint en todas las plataformas | De forma inmediata | De forma inmediata |
| Outlook para PC y Mac | Después de que Exchange Online envíe el correo electrónico | De forma inmediata |
| Outlook en la web, iOS, y Android | Después de que Exchange Online envíe el correo electrónico | Después de que Exchange Online envíe el correo electrónico |
|

## <a name="more-resources"></a>Más recursos

[Aplicar etiquetas de confidencialidad en sus documentos y correo electrónico en Office](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Problemas conocidos al aplicar etiquetas de confidencialidad en sus archivos de Office](https://support.office.com/article/known-issues-when-you-apply-sensitivity-labels-to-your-office-files-b169d687-2bbd-4e21-a440-7da1b2743edc)
