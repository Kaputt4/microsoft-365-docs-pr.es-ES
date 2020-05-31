---
title: Empiece a usar las etiquetas de confidencialidad
f1.keywords:
- CSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: ¿Está listo para iniciar la implementación de etiquetas de confidencialidad para ayudar a proteger los datos de su organización, pero no está seguro de por dónde empezar? Lea algunas instrucciones prácticas que le ayudarán a ponerse en marcha.
ms.openlocfilehash: a69b71ec364eae4258960c3b33876f0df9530611
ms.sourcegitcommit: 21977f5cb6b01aee5cae54979717530b2a31a46a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "44411027"
---
# <a name="get-started-with-sensitivity-labels"></a>Empiece a usar las etiquetas de confidencialidad

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Para obtener información sobre qué son las etiquetas de confidencialidad y cómo pueden ayudarle a proteger los datos de su organización, vea [Información sobre las etiquetas de confidencialidad](sensitivity-labels.md).

Si tiene [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection), determine si necesita migrar etiquetas a la plataforma de etiquetado unificado y qué cliente de etiquetado usar:
- [¿Cómo puedo saber si mi espacio empresarial está en la plataforma de etiquetado unificado?](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)
- [Elegir el cliente de etiquetas que se usará para equipos Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)

Cuando esté listo para empezar a proteger los datos de la organización mediante etiquetas de confidencialidad:

1. **Creación de las etiquetas.** Cree y asigne un nombre a las etiquetas de confidencialidad en función de la taxonomía de clasificación de su organización para distintos niveles de confidencialidad de contenido. Utilice nombres o términos comunes que tengan sentido para sus usuarios. Si aún no tiene una taxonomía establecida, considere la posibilidad de empezar por nombres de etiqueta como personal, público, general, confidencial y muy confidencial. Puede utilizar subetiquetas para agrupar etiquetas similares por categoría. Cuando se crea una etiqueta, use el texto de información sobre herramientas para ayudar a los usuarios a seleccionar la etiqueta apropiada.
    
    Para una guía más extensa para definir una taxonomía de clasificación, descargue el documento técnico "Clasificación de datos y taxonomía de etiquetas de confidencialidad" del [Portal de confianza de servicios](https://aka.ms/DataClassificationWhitepaper).

2. **Defina la función de cada etiqueta.** Configure los ajustes de protección que desea asociar a cada etiqueta. Por ejemplo, tal vez quiera que el contenido de menor confidencialidad (como una etiqueta "General") pueda simplemente tener un encabezado o pie de página aplicado, mientras que el contenido de mayor confidencialidad (como una etiqueta "Confidencial") debiera tener una marca de agua y encriptación.

3. **Publique las etiquetas.** Una vez configuradas las etiquetas de sensibilidad, publíquelas mediante una directiva de etiqueta. Decida qué usuarios y grupos deben tener las etiquetas y qué configuración de directiva usar. Una sola etiqueta es reutilizable: se define una vez y, después, se puede incluir en varias directivas de etiquetas asignadas a diferentes usuarios. Por ejemplo, puede crear una prueba de las etiquetas de confidencialidad asignando una directiva de etiqueta a solo algunos usuarios. Cuando esté listo para implementar las etiquetas en la organización, puede crear una nueva directiva para sus etiquetas y, esta vez, especificar todos los usuarios.

Flujo básico para la implementación y aplicación de etiquetas de confidencialidad:

![Diagrama que muestra el flujo de trabajo de las etiquetas de confidencialidad](../media/Sensitivity-label-flow.png)

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>Requisitos de suscripción y licencias para las etiquetas de confidencialidad

Distintas suscripciones admiten diferentes etiquetas de confidencialidad y los requisitos de licencias para los usuarios dependen de las características que use.

Para ver las opciones para que los usuarios puedan beneficiarse de las características de cumplimiento de Microsoft 365 a partir del 1 de abril de 2020, vea la [Guía de licencias de Microsoft 365 para seguridad y cumplimiento normativo](https://aka.ms/ComplianceSD). Para las etiquetas de confidencialidad, vea la sección [Protección de la información](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection) y la descarga relacionada de archivos PDF o Excel.

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a>Permisos necesarios para crear y administrar etiquetas de confidencialidad

Los miembros de su equipo de cumplimiento que vayan a crear etiquetas de confidencialidad en el Centro de cumplimiento de Microsoft 365, Centro de seguridad de Microsoft 365 o el Centro de seguridad y cumplimiento. 

De forma predeterminada, los administradores globales de su espacio empresarial tienen acceso a estos centros de administración y pueden dar acceso a los oficiales de cumplimiento y a otras personas, sin darles todos los permisos de un administrador de espacio empresarial. Para este acceso administrativo limitado y delegado, vaya a la página de **Permisos** de uno de estos centros de administración y luego agregue miembros al grupo de roles **Administrador de datos de cumplimiento**, **Administrador de cumplimiento** o **Administrador de seguridad**.

Como alternativa, puede crear un nuevo grupo de roles y agregar los roles de **administrador de etiquetas de confidencialidad** o **configuración de la organización** a este grupo. Para un rol de solo lectura, utilice el **Lector de etiquetas de confidencialidad**. Para instrucciones, consulte [Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).

Estos permisos son necesarios solo para crear y configurar etiquetas de confidencialidad y sus directivas de etiquetado. No son necesarios para aplicar las etiquetas en aplicaciones o servicios. Si se necesitan permisos adicionales para configuraciones específicas relacionadas con las etiquetas de confidencialidad, estos permisos se especificarán en las instrucciones de la documentación correspondientes.

## <a name="common-scenarios-for-sensitivity-labels"></a>Escenarios comunes de etiquetas de confidencialidad

Use la siguiente documentación para ayudarle con su implementación de etiquetado de confidencialidad:

|Quiero...|Documentación|
|----------------|---------------|
|Crear y publicar etiquetas de confidencialidad que ayudarán a proteger los datos de mi organización|[Crear y configurar etiquetas de confidencialidad y sus directivas](create-sensitivity-labels.md)|
|Cifre documentos y mensajes de correo electrónico con etiquetas de confidencialidad y restrinja quién puede tener acceso a ellos y cómo puede usar el contenido |[Restringir el acceso al contenido mediante el uso de etiquetas de confidencialidad para aplicar el cifrado](encryption-sensitivity-labels.md)|
|Habilite las etiquetas de confidencialidad para Office en la web, con soporte para coautoría, eDiscovery, prevención de pérdida de datos y búsqueda, incluso cuando los documentos estén encriptados. | [Habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md)
|Administre etiquetas de confidencialidad para las aplicaciones de Office para que el contenido se etiquete a medida que se crea |[Usar etiquetas de confidencialidad en las aplicaciones de Office](sensitivity-labels-office-apps.md)|
|Aplicar automáticamente etiquetas de confidencialidad a documentos y mensajes de correo electrónico | [Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md)|
|Use etiquetas de confidencialidad para proteger el contenido de Teams y SharePoint |[Usar etiquetas de confidencialidad con Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint (versión preliminar pública)](sensitivity-labels-teams-groups-sites.md)|
|Detecte, etiquete y proteja los archivos almacenados en almacenes de datos locales |[Implementación del escáner de Azure Information Protection para clasificar y proteger los archivos automáticamente](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)|
|Detecte, etiquete y proteja los archivos almacenados en almacenes de datos que están en la nube|[Descubrir, clasificar, etiquetar y proteger la información regulada y confidencialidad almacenada en la nube](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|Aplicar y ver las etiquetas de confidencialidad en Power BI y proteger los informes que se descargan|[Protección de datos en Power BI (versión preliminar)](https://docs.microsoft.com/power-bi/admin/service-security-data-protection-overview)|
|Supervisar y comprender cómo se usan las etiquetas de confidencialidad en la organización|[Información general sobre la clasificación de datos](data-classification-overview.md) <br /><br /> [Ver el uso de etiquetas con el análisis de etiquetas](label-analytics.md)|


## <a name="end-user-documentation-for-sensitivity-labels"></a>Documentación de usuario final para las etiquetas de confidencialidad

La documentación más eficaz para los usuarios finales serán la guía y las instrucciones que proporcione para los nombres de etiquetas y configuraciones que elija. Sin embargo, puede usar los siguientes recursos para obtener instrucciones básicas:   

- [Aplicar etiquetas de confidencialidad a los archivos y mensajes en Office](https://support.microsoft.com/es-ES/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Problemas conocidos con las etiquetas de confidencialidad en Office](https://support.microsoft.com/es-ES/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Aplicar o recomendar automáticamente etiquetas de confidencialidad para sus archivos y correos electrónicos en Office](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [Problemas conocidos al aplicar o recomendar automáticamente etiquetas de confidencialidad](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)

- [Guía del usuario de etiquetado unificado de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-user-guide)


