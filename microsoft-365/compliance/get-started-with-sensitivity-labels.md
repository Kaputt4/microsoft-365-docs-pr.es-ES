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
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: ¿Se ha decidido a implementar etiquetas de confidencialidad para proteger los datos de su organización, pero no sabe por dónde empezar? Lea algunas instrucciones prácticas que le ayudarán a ponerse en marcha.
ms.openlocfilehash: e07279a2de421985b0ba6f97d2b6ad843d2ba9fa
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61874033"
---
# <a name="get-started-with-sensitivity-labels"></a>Empiece a usar las etiquetas de confidencialidad

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Para obtener información sobre qué son las etiquetas de confidencialidad y cómo pueden ayudarle a proteger los datos de su organización, vea [Información sobre las etiquetas de confidencialidad](sensitivity-labels.md).

Si tiene [Azure Information Protection](/azure/information-protection/what-is-information-protection) y sigue usando etiquetas de Azure Information Protection administradas desde Azure Portal, deberá migrar estas etiquetas a la [plataforma de etiquetas unificada](/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform). En equipos con Windows, puede [elegir qué cliente de etiquetas desea usar](/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) para sus etiquetas de confidencialidad publicadas.

Cuando esté listo para empezar a proteger los datos de la organización mediante etiquetas de confidencialidad:

1. **Creación de las etiquetas.** Cree y asigne un nombre a las etiquetas de confidencialidad en función de la taxonomía de clasificación de su organización para distintos niveles de confidencialidad de contenido. Utilice nombres o términos comunes que tengan sentido para sus usuarios. Si aún no tiene una taxonomía establecida, considere la posibilidad de empezar por nombres de etiqueta como personal, público, general, confidencial y muy confidencial. Puede utilizar subetiquetas para agrupar etiquetas similares por categoría. Cuando se crea una etiqueta, use el texto de información sobre herramientas para ayudar a los usuarios a seleccionar la etiqueta apropiada.
    
    Para una guía más extensa para definir una taxonomía de clasificación, descargue el documento técnico "Clasificación de datos y taxonomía de etiquetas de confidencialidad" del [Portal de confianza de servicios](https://aka.ms/DataClassificationWhitepaper).

2. **Defina la función de cada etiqueta.** Configure los ajustes de protección que desea asociar a cada etiqueta. Por ejemplo, tal vez quiera que el contenido de menor confidencialidad (como una etiqueta "General") pueda simplemente tener un encabezado o pie de página aplicado, mientras que el contenido de mayor confidencialidad (como una etiqueta "Confidencial") debiera tener una marca de agua y encriptación.

3. **Publique las etiquetas.** Una vez configuradas las etiquetas de sensibilidad, publíquelas mediante una directiva de etiqueta. Decida qué usuarios y grupos deben tener las etiquetas y qué configuración de directiva usar. Una sola etiqueta es reutilizable: se define una vez y, después, se puede incluir en varias directivas de etiquetas asignadas a diferentes usuarios. Por ejemplo, puede crear una prueba de las etiquetas de confidencialidad asignando una directiva de etiqueta a solo algunos usuarios. Cuando esté listo para implementar las etiquetas en la organización, puede crear una nueva directiva para sus etiquetas y, esta vez, especificar todos los usuarios.


> Es posible que sea apto para la creación automática de etiquetas predeterminadas y una directiva de etiquetas predeterminada que se encarga de los pasos 1 a 3. Para más información, vea [Etiquetas y directivas predeterminadas para Microsoft Information Protection](mip-easy-trials.md).

Flujo básico para la implementación y aplicación de etiquetas de confidencialidad:

![Diagrama que muestra el flujo de trabajo de las etiquetas de confidencialidad.](../media/Sensitivity-label-flow.png)

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>Requisitos de suscripción y licencias para las etiquetas de confidencialidad

Distintas suscripciones admiten diferentes etiquetas de confidencialidad y los requisitos de licencias para los usuarios dependen de las características que use.

Para ver las opciones para que los usuarios puedan beneficiarse de las características de cumplimiento de Microsoft 365, consulte la [Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance). Para obtener etiquetas de confidencialidad, consulte la [sección Protección de la información: etiquetado de confidencialidad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-sensitivity-labeling) y la descarga [de PDF](https://go.microsoft.com/fwlink/?linkid=2139145) relacionada para los requisitos de licencias de nivel de característica.

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a>Permisos necesarios para crear y administrar etiquetas de confidencialidad

Los miembros del equipo de cumplimiento que vayan a crear etiquetas de confidencialidad necesitarán permisos para el Centro de cumplimiento de Microsoft 365.

De forma predeterminada, los administradores globales de su espacio empresarial tienen acceso a este centro de administración y pueden dar acceso a los oficiales de cumplimiento y a otras personas, sin darles todos los permisos de un administrador de espacio empresarial. Para este acceso administrativo limitado y delegado, agregue usuarios al grupo de roles **Administrador de datos de cumplimiento**, **Administrador de cumplimiento** o **Administrador de seguridad**. 

Como alternativa al uso de los roles predeterminados, puede crear un nuevo grupo de roles y agregar **administrador de etiquetas de confidencialidad** o roles de **configuración de la organización** a este grupo. Para un rol de solo lectura, use **lector de etiquetas de confidencialidad**. 

> [!NOTE]
> Ahora, en la versión preliminar, puede usar los siguientes grupos de roles:
> - **Protección de información**
> - **Administradores de Information Protection**
> - **Analistas de Information Protection**
> - **Investigadores de Information Protection**
> - **Lectores de Information Protection**
>
> Para obtener una explicación de cada uno de ellos y de los nuevos roles que contienen, seleccione un grupo de roles en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Centro de cumplimiento de Microsoft 365</a> > **Permisos y roles** > **Centro de cumplimiento** > **Roles** y, a continuación, revise la descripción en el panel desplegable. O bien, consulte [Grupos de roles en el Centro de seguridad y cumplimiento](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#role-groups-in-the-security--compliance-center).

Para obtener instrucciones sobre cómo agregar usuarios al grupo de roles predeterminado, roles o crear sus propios grupos de roles, consulte [Permisos en el Centro de cumplimiento de Microsoft 365](microsoft-365-compliance-center-permissions.md).

Estos permisos son necesarios solo para crear y configurar etiquetas de confidencialidad y sus directivas de etiquetado. No son necesarios para aplicar las etiquetas en aplicaciones o servicios. Si se necesitan permisos adicionales para configuraciones específicas relacionadas con las etiquetas de confidencialidad, estos permisos se especificarán en las instrucciones de la documentación correspondientes.

## <a name="deployment-strategy-for-sensitivity-labels"></a>Estrategia de implementación para las etiquetas de sensibilidad
Una estrategia exitosa para implementar etiquetas de carácter para una organización consiste en crear un equipo virtual de trabajo en el que se identifiquen y administren los requisitos técnicos de la empresa, pruebas de concepto, controles internos y aprobaciones, y implementación final para el entorno de producción.

Con la tabla de la siguiente sección, le recomendamos que identifique uno o dos escenarios principales que se correspondan con los requisitos empresariales más impactantes. Después de implementar estos escenarios, vuelva a la lista para identificar la siguiente o las dos prioridades para la implementación.

Encontrará instrucciones generales de implementación adicionales y procedimientos recomendados en la [Guía de aceleración de implementación para la Protección de la información de Microsoft y prevención de pérdida de datos](https://microsoft.github.io/ComplianceCxE/dag/mip-dlp/), uno de los recursos del sitio [Customer Acceleration Team (CAT)](https://microsoft.github.io/ComplianceCxE/).

## <a name="common-scenarios-for-sensitivity-labels"></a>Escenarios comunes de etiquetas de confidencialidad

Todos los escenarios requieren que [Crear y configurar etiquetas de confidencialidad y sus directivas](create-sensitivity-labels.md).

|Quiero...|Documentación|
|----------------|---------------|
|Administrar etiquetas de confidencialidad para las aplicaciones de Office para que el contenido se etiquete a medida que se crea (incluye la compatibilidad con el etiquetado manual en todas las plataformas) |[Administrar etiquetas de confidencialidad en las aplicaciones de Office](sensitivity-labels-office-apps.md)|
|Permitir que los usuarios etiqueten y protejan archivos de equipos Windows con las aplicaciones de Office, el Explorador de archivos y PowerShell|[Cliente de etiquetado unificado de Azure Information Protection para Windows](/azure/information-protection/rms-client/aip-clientv2)|
|Cifre documentos y mensajes de correo electrónico con etiquetas de confidencialidad y restrinja quién puede tener acceso a ellos y cómo puede usar el contenido |[Restringir el acceso al contenido mediante el uso de etiquetas de confidencialidad para aplicar el cifrado](encryption-sensitivity-labels.md)|
|Habilite las etiquetas de confidencialidad para Office en la web, con soporte para coautoría, eDiscovery, la prevención de pérdida de datos y búsqueda, incluso cuando los documentos estén cifrados. | [Habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md)
|Usar la coautoría y guardar automáticamente en las aplicaciones de escritorio de Office cuando los documentos están cifrados | [Habilitar la coautoría para archivos cifrados con etiquetas de confidencialidad](sensitivity-labels-coauthoring.md)
|Aplicar automáticamente etiquetas de confidencialidad a documentos y mensajes de correo electrónico | [Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md)|
|Use etiquetas de confidencialidad para proteger el contenido de Teams y SharePoint |[Usar etiquetas de confidencialidad con Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](sensitivity-labels-teams-groups-sites.md)|
|Aplicar una etiqueta de confidencialidad a un modelo de comprensión de documentos, de modo que los documentos identificados en una biblioteca SharePoint se clasifiquen y se protejan automáticamente |[Aplicar una etiqueta de confidencialidad a un modelo en Microsoft SharePoint Syntex](/microsoft-365/contentunderstanding/apply-a-sensitivity-label-to-a-model)|
|Prevenir o advertir a los usuarios sobre el uso compartido de archivos o correos electrónicos con una etiqueta de confidencialidad específica |[Usar etiquetas de confidencialidad como condiciones en las directivas de DLP](dlp-sensitivity-label-as-condition.md) |
|Aplicar una etiqueta de retención para conservar o eliminar archivos o correos electrónicos que tengan una etiqueta de confidencialidad específica|[Aplicar una etiqueta de retención automáticamente para conservar o eliminar contenido](apply-retention-labels-automatically.md) |
|Detecte, etiquete y proteja los archivos almacenados en almacenes de datos locales |[Implementación del escáner de Azure Information Protection para clasificar y proteger los archivos automáticamente](/azure/information-protection/deploy-aip-scanner)|
|Detecte, etiquete y proteja los archivos almacenados en almacenes de datos que están en la nube|[Descubrir, clasificar, etiquetar y proteger la información regulada y confidencialidad almacenada en la nube](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|Aplicar y ver las etiquetas de confidencialidad en Power BI y proteger los datos cuando se guarden fuera del servicio.|[Etiquetas de confidencialidad en Power BI](/power-bi/admin/service-security-sensitivity-label-overview)|
|Supervisar y comprender cómo se usan las etiquetas de confidencialidad en la organización|[Obtenga información sobre la clasificación de datos](data-classification-overview.md)|
|Amplíe las etiquetas de confidencialidad a los servicios y aplicaciones de terceros.|[SDK de Microsoft Information Protection](/information-protection/develop/overview#microsoft-information-protection-sdk)|
|Extender las etiquetas de confidencialidad a través del contenido de mis recursos de Azure Purview, como Azure Blob Storage, Azure Files, Azure Data Lake Storage y orígenes de datos de varias nubes|[Etiquetado en Azure Purview](/azure/purview/create-sensitivity-label) |


## <a name="end-user-documentation-for-sensitivity-labels"></a>Documentación de usuario final para las etiquetas de confidencialidad

La documentación más eficaz para los usuarios finales serán la guía y las instrucciones que proporcione para los nombres de etiquetas y configuraciones que elija. Puede usar el valor de directiva de etiquetado **Proporcionar a los usuarios un vínculo a una página de ayuda personalizada** para especificar un vínculo interno para esta documentación. Así, los usuarios pueden acceder con facilidad desde el botón **Confidencialidad**:

- Para las etiquetas integradas: opción del menú **Más información**.
- Para el cliente de etiquetado unificado de Azure Information Protection: opción del menú **Ayuda y comentarios** > vínculo **Más información** en el cuadro de diálogo de Azure Information Protection.

Para ayudarle a ofrecer su documentación personalizada, consulte la siguiente página y descargas que puede usar para formar a los usuarios: [Aprendizaje para el usuario final para etiquetas de confidencialidad](https://microsoft.github.io/ComplianceCxE/enduser/sensitivity/). 

También puede usar los siguientes recursos para obtener instrucciones básicas:

- [Aplicar etiquetas de confidencialidad a sus archivos y correos electrónicos en Office](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Problemas conocidos con las etiquetas de confidencialidad en Office](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Aplicar o recomendar automáticamente etiquetas de confidencialidad para sus archivos y correos electrónicos en Office](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [Problemas conocidos al aplicar o recomendar automáticamente etiquetas de confidencialidad](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)

- [Guía del usuario de etiquetado unificado de Azure Information Protection](/azure/information-protection/rms-client/clientv2-user-guide)

Si las etiquetas de confidencialidad aplican el cifrado para documentos PDF, estos se pueden abrir con Microsoft Edge en Windows o Mac. Para obtener más información y para lectores alternativos, vea [¿Cuáles son los lectores de PDF compatibles para archivos PDF protegidos?](/azure/information-protection/rms-client/protected-pdf-readers#viewing-protected-pdfs-in-microsoft-edge-on-windows-or-mac)
