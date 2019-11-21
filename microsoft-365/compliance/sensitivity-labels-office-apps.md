---
title: Etiquetas de confidencialidad en las aplicaciones de Office
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/20/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo trabajan los usuarios con las etiquetas de confidencialidad en las aplicaciones de Office para el escritorio, aplicaciones de Office para dispositivos móviles y aplicaciones de Office para la Web. Averiguar qué aplicaciones admiten las etiquetas de confidencialidad.
ms.openlocfilehash: 1b472185df2d45717cba6cfca30176768bf9cd4e
ms.sourcegitcommit: 5f96fa472cbdca30c2cfe24d66c9c6fcaedb1a6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2019
ms.locfileid: "38755598"
---
# <a name="sensitivity-labels-in-office-apps"></a>Etiquetas de confidencialidad en las aplicaciones de Office

Este artículo describe:

- Requisitos para el entorno antes de aplicar las etiquetas de confidencialidad a los correos electrónicos, archivos y datos adjuntos.
- Las funciones de etiqueta de confidencialidad que admite cada aplicación de Office.
- Qué sucede cuando combina las etiquetas de confidencialidad con otras tecnologías de seguridad y cumplimiento de Microsoft que funcionan con las aplicaciones de Office.
- Cómo pueden usar las personas de su organización las etiquetas de confidencialidad cuando funcionan con las aplicaciones de Office para Windows y las aplicaciones de Office para la Web.
- Dónde obtener acceso a las personas de su organización que se inician con etiquetas de confidencialidad.

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>Requisitos de suscripción y licencia para las etiquetas de confidencialidad

Los usuarios deben tener asignada al menos una de las siguientes licencias:

- [Microsoft 365 E3](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) o superior

- [Office 365 E3](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e3-business-software) o superior

- [Azure Information Protection Premium P1](https://azure.microsoft.com/pricing/details/information-protection/) o superior

El cliente de etiquetado integrado de Office admite las etiquetas de confidencialidad con una versión de suscripción de Office. El cliente no admite versiones independientes, por ejemplo, Office 2016 u Office 2019.

Para usar las etiquetas de confidencialidad automáticas o recomendadas, los usuarios deben disponer de una de las siguientes licencias:

- [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) o posterior

- [Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software) o posterior

- [Azure Information Protection Premium P2](https://azure.microsoft.com/pricing/details/information-protection/) o superior

## <a name="support-for-sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Compatibilidad con capacidades de etiqueta de confidencialidad en Word, Excel y PowerPoint

Para cada funcionalidad, en la tabla siguiente se muestra la versión mínima que necesita para esa aplicación. TBD significa que no puede usar esa funcionalidad en esa plataforma.

|Función                                                                                                        |Escritorio de Windows |Escritorio de Mac |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Aplicar, cambiar o quitar manualmente la etiqueta](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Versión preliminar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Aplicar una etiqueta predeterminada](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | Por determinar                                                        |
|[Requerir una justificación para cambiar una etiqueta](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Versión preliminar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Proporcionar un vínculo de ayuda a una página de ayuda personalizada](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Versión preliminar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Marcar el contenido](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Versión preliminar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Asignar permisos ahora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Versión preliminar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Permitir a los usuarios asignar permisos](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | Por determinar            | Por determinar        | Por determinar   | Por determinar         | Por determinar                                                        |
|[Ver el uso de etiquetas con análisis de etiqueta](label-analytics.md) y enviar datos para administradores                      | Por determinar            | Por determinar        | Por determinar   | Por determinar         | Por determinar                                                        |
|
  [Requerir que los usuarios apliquen una etiqueta al correo electrónico y a los documentos](sensitivity-labels.md#what-label-policies-can-do)   | Por determinar            | Por determinar        | Por determinar   | Por determinar         | Por determinar                                                        |
|[Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md)                    | Vista previa: en distribución a [Office Insider](https://office.com/insider)                                  | Por determinar | Por determinar | Por determinar | [Versión preliminar](sensitivity-labels-sharepoint-onedrive-files.md) |
|Compatibilidad con [autoguardado](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) y [coautoría](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) en documentos con y sin etiquetas | Por determinar | Por determinar | Por determinar | Por determinar | [Versión preliminar](sensitivity-labels-sharepoint-onedrive-files.md) |
|

## <a name="support-for-sensitivity-label-capabilities-in-outlook"></a>Compatibilidad con capacidades de etiqueta de confidencialidad en Outlook

Para cada funcionalidad, en la tabla siguiente se muestra la versión mínima que necesita para esa aplicación. TBD significa que no puede usar esa funcionalidad en esa plataforma.

|Función                                                                                                        |Outlook en el escritorio de Windows |Escritorio de Outlook en Mac  |Outlook en iOS |Outlook en Android |Outlook en la Web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Aplicar, cambiar o quitar manualmente la etiqueta](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Sí               |
|[Aplicar una etiqueta predeterminada](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Sí               |
|[Requerir una justificación para cambiar una etiqueta](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Sí               |
|[Proporcionar un vínculo de ayuda a una página de ayuda personalizada](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Sí               |
|[Marcar el contenido](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Sí               |
|[Asignar permisos ahora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Sí               |
|[Permitir a los usuarios asignar permisos](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Sí               |
|[Ver el uso de etiquetas con análisis de etiqueta](label-analytics.md) y enviar datos para administradores                      | Por determinar                       | Por determinar                    | Por determinar           | Por determinar               | Por determinar               |
|
  [Requerir que los usuarios apliquen una etiqueta al correo electrónico y a los documentos](sensitivity-labels.md#what-label-policies-can-do)   | Por determinar                       | Por determinar                    | Por determinar           | Por determinar               | Por determinar               |
|[Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md)                    | Por determinar                       | Por determinar                    | Por determinar           | Por determinar               | Vista previa: en distribución a la [versión dirigida](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide) |
|

## <a name="about-the-office-built-in-labeling-client"></a>Información sobre el cliente de etiquetado de Office integrado

El cliente de etiquetado integrado de Office descarga etiquetas y opciones de configuración de directivas desde los siguientes centros de administración:

- Centro de seguridad y cumplimiento de Office 365

- Centro de seguridad de Microsoft 365

- Centro de cumplimiento de Microsoft 365

El cliente de etiquetado integrado de Office se habilita automáticamente para los usuarios que tienen una o más [directivas de etiqueta publicadas](sensitivity-labels.md#what-label-policies-can-do) en ellos.

Para usar el cliente de etiquetado integrado en Office en Windows, no puede ejecutar el complemento de Azure Information Protection al mismo tiempo en Office. Puede desinstalar temporalmente o permanentemente el cliente de Azure Information Protection o puede dejarlo instalado y configurar Office para impedir que se ejecute.

1. Complete una de estas opciones:

    **Para varios equipos:** Configure la opción **usar la característica de confidencialidad en Office para aplicar y ver etiquetas de distinción** configuración de directiva de grupo. Busque esta opción de configuración en **configuración del usuario/Plantillas administrativas/Microsoft Office 2016/configuración de seguridad**. Implemente esta configuración mediante la Directiva de grupo o con el [servicio de directiva de nube de Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).

    **Para un solo equipo:** Vea "ver, administrar e instalar complementos en los programas de Office" y [deshabilitar o quitar permanentemente](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d) el complemento de Azure Information Protection en un único equipo.

2. Reiniciar todas las aplicaciones de Office.

Para obtener más información acerca de las aplicaciones cliente para la protección de la información, vea [el lado cliente de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/use-client).

## <a name="protection-templates-and-sensitivity-labels"></a>Plantillas de protección y etiquetas de confidencialidad

[Las plantillas de protección](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)definidas por el administrador, como las que se definen para el cifrado de mensajes de Office 365, están ocultas para la experiencia del usuario de Office cuando las etiquetas de confidencialidad están habilitadas porque son redundantes con las etiquetas de confidencialidad que tienen habilitado el cifrado.

## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Aplicar etiquetas de confidencialidad a archivos, mensajes de correo electrónico y datos adjuntos

Los usuarios pueden aplicar una sola etiqueta a la vez para cada documento o correo electrónico.

Al etiquetar un mensaje de correo electrónico que tiene datos adjuntos, los datos adjuntos no heredan la etiqueta. Si los datos adjuntos tenían una etiqueta que conservan esa etiqueta por separado. Si los datos adjuntos no tienen etiqueta, los datos adjuntos permanecen sin etiqueta. Sin embargo, si la etiqueta del correo electrónico aplica protección, esa protección se aplicará a los datos adjuntos de Office.

## <a name="sensitivity-label-compatibility"></a>Compatibilidad de las etiquetas de confidencialidad

**Con aplicaciones habilitadas para RMS**. Si abre un documento o correo electrónico con la etiqueta _y cifrada_ en una [aplicación habilitada para RMS](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) que no admite las etiquetas de confidencialidad, la aplicación sigue forzando el cifrado y la administración de derechos.

**Con el cliente de Azure Information Protection**. Puede ver y cambiar las etiquetas de confidencialidad que se aplican a los documentos y correos electrónicos con el cliente de etiquetación integrado de Office con el cliente de Azure Information Protection y la otra forma.

**Con otras versiones de Office**. Cualquier usuario autorizado puede abrir documentos con etiquetas y correos electrónicos en otras versiones de Office. Sin embargo, solo puede ver o cambiar la etiqueta en versiones de Office compatibles o en el cliente de Azure Information Protection. Las versiones de aplicaciones de Office admitidas se muestran en las tablas de este artículo.

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Compatibilidad con archivos de OneDrive y SharePoint protegidos por etiquetas de confidencialidad

Para usar el cliente de etiquetado integrado de Office en Office en la web, el documento debe estar ubicado en una instancia de OneDrive para la empresa o de SharePoint Online que haya optado [por la habilitación de las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="when-office-365-applies-marks-and-encryption-to-content"></a>Cuando Office 365 aplica marcas y cifrado al contenido

Office 365 aplica marcas de contenido o cifrado con una etiqueta de confidencialidad diferente según la aplicación que use.

| Aplicación | Marcado de contenido | Cifrado |
| --- | --- | --- |
| Word, Excel y PowerPoint en todas las plataformas | De forma inmediata | De forma inmediata |
| Outlook para PC y Mac | Después de que Exchange Online envíe el correo electrónico | De forma inmediata |
| Outlook en la web, iOS, y Android | Después de que Exchange Online envíe el correo electrónico | Después de que Exchange Online envíe el correo electrónico |
|

## <a name="more-resources"></a>Más recursos

[Preguntas más frecuentes sobre la clasificación y etiquetado en Azure Information Protection](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)

[Aplicar etiquetas de confidencialidad en sus documentos y correo electrónico en Office](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
