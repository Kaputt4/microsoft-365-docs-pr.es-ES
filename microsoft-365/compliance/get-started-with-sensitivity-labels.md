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
ms.openlocfilehash: 9ffe0f52adf108ba03a41b2dba7261d21171bbba
ms.sourcegitcommit: 7dc36305721a92e19a6e397f906e19dcafa0073b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2020
ms.locfileid: "42101260"
---
# <a name="get-started-with-sensitivity-labels"></a>Empiece a usar las etiquetas de confidencialidad

Para obtener información sobre qué son las etiquetas de confidencialidad y cómo pueden ayudarle a proteger los datos de su organización, vea [Información sobre las etiquetas de confidencialidad](sensitivity-labels.md).

Si tiene [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection), determine si necesita migrar etiquetas a la plataforma de etiquetado unificado y qué cliente de etiquetado usar:
- [¿Cómo puedo saber si mi espacio empresarial está en la plataforma de etiquetado unificado?](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)
- [Elegir el cliente de etiquetas que se usará para equipos Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)

Cuando esté listo para empezar a proteger los datos de la organización mediante etiquetas de confidencialidad:

1. **Creación de las etiquetas.** Cree y asigne un nombre a las etiquetas de confidencialidad en función de la taxonomía de clasificación de su organización para distintos niveles de confidencialidad de contenido. Utilice nombres o términos comunes que tengan sentido para sus usuarios. Si aún no tiene una taxonomía establecida, considere la posibilidad de empezar por nombres de etiqueta como personal, público, general, confidencial y muy confidencial. Puede utilizar subetiquetas para agrupar etiquetas similares por categoría. Cuando se crea una etiqueta, use el texto de información sobre herramientas para ayudar a los usuarios a seleccionar la etiqueta apropiada.

2. **Defina la función de cada etiqueta.** Configure los ajustes de protección que desea asociar a cada etiqueta. Por ejemplo, tal vez desee que el contenido de menor confidencialidad (como una etiqueta "General") pueda simplemente tener un encabezado o pie de página aplicado, mientras que el contenido de mayor confidencialidad (como una etiqueta "Confidencial") debiera tener una marca de agua, encriptación y protección de los puntos de conexión.

3. **Publique las etiquetas.** Una vez configuradas las etiquetas de sensibilidad, publíquelas mediante una directiva de etiqueta. Decida qué usuarios y grupos deben tener las etiquetas y qué configuración de directiva usar. Una sola etiqueta es reutilizable: se define una vez y, después, se puede incluir en varias directivas de etiquetas asignadas a diferentes usuarios. Por ejemplo, puede crear una prueba de las etiquetas de confidencialidad asignando una directiva de etiqueta a solo algunos usuarios. Cuando esté listo para implementar las etiquetas en la organización, puede crear una nueva directiva para sus etiquetas y, esta vez, especificar todos los usuarios.

Flujo básico para la implementación y aplicación de etiquetas de confidencialidad:

![Diagrama que muestra el flujo de trabajo de las etiquetas de confidencialidad](../media/Sensitivity-label-flow.png)

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a>Permisos necesarios para crear y administrar etiquetas de confidencialidad

Los miembros de su equipo de cumplimiento que vayan a crear etiquetas de confidencialidad en el Centro de cumplimiento de Microsoft 365, Centro de seguridad de Microsoft 365 o el Centro de seguridad y cumplimiento de Office 365. 

De forma predeterminada, los administradores globales de su espacio empresarial tienen acceso a estos centros de administración y pueden dar acceso a los oficiales de cumplimiento y a otras personas, sin darles todos los permisos de un administrador de espacio empresarial. Para este acceso administrativo limitado y delegado, vaya a la página de **Permisos** de uno de estos centros de administración y luego agregue miembros al grupo de roles **Administrador de datos de cumplimiento**, **Administrador de cumplimiento** o **Administrador de seguridad**.

Como alternativa, puede crear un nuevo grupo de roles y agregar los roles de **administrador de etiquetas de confidencialidad** o **configuración de la organización** a este grupo. Para instrucciones, consulte [Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).

Estos permisos son necesarios solo para crear y configurar etiquetas de confidencialidad y sus directivas de etiquetado. No son necesarios para aplicar las etiquetas en aplicaciones o servicios.

## <a name="common-scenarios-for-sensitivity-labels"></a>Escenarios comunes de etiquetas de confidencialidad

Use la siguiente documentación para ayudarle con su implementación de etiquetado de confidencialidad:

|Quiero...|Documentación|
|----------------|---------------|
|Crear y publicar etiquetas de confidencialidad que ayudarán a proteger los datos de mi organización|[Crear y configurar etiquetas de confidencialidad y sus directivas](create-sensitivity-labels.md)|
|Cifre documentos y mensajes de correo electrónico con etiquetas de confidencialidad y restrinja quién puede tener acceso a ellos y cómo puede usar el contenido. |[Restringir el acceso al contenido mediante el uso de etiquetas de confidencialidad para aplicar el cifrado](encryption-sensitivity-labels.md)|
|Habilite las características de colaboración en SharePoint (y OneDrive) para los documentos que se etiquetan con el cifrado | [Habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive (vista previa)](sensitivity-labels-sharepoint-onedrive-files.md)
|Administre etiquetas de confidencialidad para las aplicaciones de Office para que el contenido se etiquete a medida que se crea |[Usar etiquetas de confidencialidad en las aplicaciones de Office](sensitivity-labels-office-apps.md)|
|Aplique etiquetas de confidencialidad automáticamente o recomiende etiquetas a los usuarios al crear contenido | [Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md)|
|Use etiquetas de confidencialidad para proteger el contenido de Teams y SharePoint |[Usar etiquetas de confidencialidad con Microsoft Teams, grupos de Office 365 y sitios de SharePoint (versión preliminar pública)](sensitivity-labels-teams-groups-sites.md)|
|Detecte, etiquete y proteja los archivos almacenados en almacenes de datos locales |[Implementación del escáner de Azure Information Protection para clasificar y proteger los archivos automáticamente](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)|
|Detecte, etiquete y proteja los archivos almacenados en almacenes de datos que están en la nube|[Descubrir, clasificar, etiquetar y proteger la información regulada y confidencialidad almacenada en la nube](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|Visualizar cómo se usan las etiquetas de confidencialidad para informar del estado de implementación y ajustar la configuración de etiquetas|[Ver el uso de etiquetas con el análisis de etiquetas](label-analytics.md)|


## <a name="end-user-documentation-for-sensitivity-labels"></a>Documentación de usuario final para las etiquetas de confidencialidad

La documentación más eficaz para los usuarios finales serán la guía y las instrucciones que proporcione para los nombres de etiquetas y configuraciones que elija. Sin embargo, puede usar los siguientes recursos para obtener instrucciones básicas:   

- [Aplicar etiquetas de confidencialidad a los archivos y mensajes en Office](https://support.office.com/article/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Problemas conocidos con las etiquetas de confidencialidad en Office](https://support.office.com/en-us/article/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Aplicar o recomendar automáticamente etiquetas de confidencialidad para sus archivos y correos electrónicos en Office](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [Problemas conocidos al aplicar o recomendar automáticamente etiquetas de confidencialidad](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)

- [Guía del usuario de etiquetado unificado de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-user-guide)


