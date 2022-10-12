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
- purview-compliance
- tier1
- highpri
- SPO_Content
- m365solution-mip
- m365initiative-compliance
- highpri
search.appverid:
- MOE150
- MET150
description: Pasos prescriptivos para administradores, requisitos de licencia y escenarios comunes que usan etiquetas de confidencialidad para ayudar a proteger los datos de la organización.
ms.openlocfilehash: cb956c413d975c6d0199cb9b8f2d620b35b69fdc
ms.sourcegitcommit: ca082da1c51a3f643f152492579eef5679d52bd0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "68548002"
---
# <a name="get-started-with-sensitivity-labels"></a>Empiece a usar las etiquetas de confidencialidad

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Para obtener información sobre qué son las etiquetas de confidencialidad y cómo pueden ayudarle a proteger los datos de su organización, vea [Información sobre las etiquetas de confidencialidad](sensitivity-labels.md).

Si tiene [Azure Information Protection](/azure/information-protection/what-is-information-protection) y sigue usando etiquetas de Azure Information Protection administradas desde Azure Portal, deberá migrar estas etiquetas a la [plataforma de etiquetas unificada](/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform). A continuación, se recomienda deshabilitar el complemento AIP para aplicaciones de Office para beneficiarse de la experiencia de etiquetado integrada más reciente. Para obtener más información, consulte [Migración del complemento de Azure Information Protection (AIP) al etiquetado integrado para aplicaciones de Office](sensitivity-labels-aip.md).

Cuando esté listo para empezar a proteger los datos de la organización mediante etiquetas de confidencialidad:

1. **Creación de las etiquetas.** Cree y asigne un nombre a las etiquetas de confidencialidad en función de la taxonomía de clasificación de su organización para distintos niveles de confidencialidad de contenido. Utilice nombres o términos comunes que tengan sentido para sus usuarios. Si aún no tiene una taxonomía establecida, considere la posibilidad de empezar por nombres de etiqueta como personal, público, general, confidencial y muy confidencial. Puede utilizar subetiquetas para agrupar etiquetas similares por categoría. Cuando se crea una etiqueta, use el texto de información sobre herramientas para ayudar a los usuarios a seleccionar la etiqueta apropiada.
    
    Para una guía más extensa para definir una taxonomía de clasificación, descargue el documento técnico "Clasificación de datos y taxonomía de etiquetas de confidencialidad" del [Portal de confianza de servicios](https://aka.ms/DataClassificationWhitepaper).

2. **Defina la función de cada etiqueta.** Configure los ajustes de protección que desea asociar a cada etiqueta. Por ejemplo, tal vez quiera que el contenido de menor confidencialidad (como una etiqueta "General") pueda simplemente tener un encabezado o pie de página aplicado, mientras que el contenido de mayor confidencialidad (como una etiqueta "Confidencial") debiera tener una marca de agua y encriptación.

3. **Publique las etiquetas.** Una vez configuradas las etiquetas de sensibilidad, publíquelas mediante una directiva de etiqueta. Decida qué usuarios y grupos deben tener las etiquetas y qué configuración de directiva usar. Una sola etiqueta es reutilizable: se define una vez y, después, se puede incluir en varias directivas de etiquetas asignadas a diferentes usuarios. Por ejemplo, puede crear una prueba de las etiquetas de confidencialidad asignando una directiva de etiqueta a solo algunos usuarios. Cuando esté listo para implementar las etiquetas en la organización, puede crear una nueva directiva para sus etiquetas y, esta vez, especificar todos los usuarios.

> [!TIP]
> Es posible que sea apto para la creación automática de etiquetas predeterminadas y una directiva de etiquetas predeterminada que se encarga de los pasos 1 a 3. Para obtener más información, consulte [Etiquetas y directivas predeterminadas para Microsoft Purview Information Protection](mip-easy-trials.md).

Flujo básico para la implementación y aplicación de etiquetas de confidencialidad:

![Diagrama que muestra el flujo de trabajo de las etiquetas de confidencialidad.](../media/Sensitivity-label-flow.png)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>Requisitos de suscripción y licencias para las etiquetas de confidencialidad

Distintas suscripciones admiten diferentes etiquetas de confidencialidad y los requisitos de licencias para los usuarios dependen de las características que use.

Para ver las opciones para que los usuarios puedan beneficiarse de las características de Microsoft Purview, consulte la [Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance). Para obtener etiquetas de confidencialidad, consulte la sección [Microsoft Purview Information Protection: etiquetado de confidencialidad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-information-protection-sensitivity-labeling) y la [descarga de PDF](https://go.microsoft.com/fwlink/?linkid=2139145) relacionada para los requisitos de licencias de nivel de características.

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a>Permisos necesarios para crear y administrar etiquetas de confidencialidad

Los miembros del equipo de cumplimiento que vayan a crear etiquetas de confidencialidad necesitarán permisos para el Portal de cumplimiento de Microsoft Purview.

De forma predeterminada, los administradores globales de su espacio empresarial tienen acceso a este centro de administración y pueden dar acceso a los oficiales de cumplimiento y a otras personas, sin darles todos los permisos de un administrador de espacio empresarial. Para este acceso administrativo limitado y delegado, agregue usuarios al grupo de roles **Administrador de datos de cumplimiento**, **Administrador de cumplimiento** o **Administrador de seguridad**. 

Alternatively to using the default roles, you can create a new role group and add either **Sensitivity Label Administrator** or **Organization Configuration** roles to this group. For a read-only role, use **Sensitivity Label Reader**. 

> [!NOTE]
> Ahora, en la versión preliminar, puede usar los siguientes grupos de roles:
> - **Protección de información**
> - **Administradores de Information Protection**
> - **Analistas de Information Protection**
> - **Investigadores de Information Protection**
> - **Lectores de Information Protection**
>
> For an explanation of each one, and the new roles that they contain, select a role group in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft Purview compliance portal</a> > **Permissions & roles** > **Compliance center** > **Roles**, and then review the description in the flyout pane. Or, see [Role groups in the Security & Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#role-groups-in-the-security--compliance-center).

Para obtener instrucciones sobre cómo agregar usuarios al grupo de roles predeterminado, roles o crear sus propios grupos de roles, consulte [Permisos en el Portal de cumplimiento de Purview](microsoft-365-compliance-center-permissions.md).

Estos permisos son necesarios solo para crear y configurar etiquetas de confidencialidad y sus directivas de etiquetado. No son necesarios para aplicar las etiquetas en aplicaciones o servicios. Si se necesitan permisos adicionales para configuraciones específicas relacionadas con las etiquetas de confidencialidad, estos permisos se especificarán en las instrucciones de la documentación correspondientes.

## <a name="deployment-strategy-for-sensitivity-labels"></a>Estrategia de implementación para las etiquetas de sensibilidad
Una estrategia exitosa para implementar etiquetas de carácter para una organización consiste en crear un equipo virtual de trabajo en el que se identifiquen y administren los requisitos técnicos de la empresa, pruebas de concepto, controles internos y aprobaciones, y implementación final para el entorno de producción.

Con la tabla de la siguiente sección, le recomendamos que identifique uno o dos escenarios principales que se correspondan con los requisitos empresariales más impactantes. Después de implementar estos escenarios, vuelva a la lista para identificar la siguiente o las dos prioridades para la implementación.

## <a name="common-scenarios-for-sensitivity-labels"></a>Escenarios comunes de etiquetas de confidencialidad

Todos los escenarios requieren que [Crear y configurar etiquetas de confidencialidad y sus directivas](create-sensitivity-labels.md).

|Quiero...|Documentación|
|----------------|---------------|
|Administrar etiquetas de confidencialidad para las aplicaciones de Office para que el contenido se etiquete a medida que se crea (incluye la compatibilidad con el etiquetado manual en todas las plataformas) |[Administrar etiquetas de confidencialidad en las aplicaciones de Office](sensitivity-labels-office-apps.md)|
|Ampliar el etiquetado a Explorador de archivos y PowerShell, con características adicionales para las aplicaciones de Office en Windows (si es necesario)|[Cliente de etiquetado unificado de Azure Information Protection para Windows](/azure/information-protection/rms-client/aip-clientv2)|
|Cifre documentos y mensajes de correo electrónico con etiquetas de confidencialidad y restrinja quién puede tener acceso a ellos y cómo puede usar el contenido |[Restringir el acceso al contenido mediante el uso de etiquetas de confidencialidad para aplicar el cifrado](encryption-sensitivity-labels.md)|
|Habilite las etiquetas de confidencialidad para Office en la web, con soporte para coautoría, eDiscovery, la prevención de pérdida de datos y búsqueda, incluso cuando los documentos estén cifrados. | [Habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md)
|Los archivos de SharePoint se etiquetarán automáticamente con una etiqueta de confidencialidad predeterminada | [Configurar una etiqueta de confidencialidad predeterminada para una biblioteca de documentos de SharePoint](sensitivity-labels-sharepoint-default-label.md)
|Usar la coautoría y guardar automáticamente en las aplicaciones de escritorio de Office cuando los documentos están cifrados | [Habilitar la coautoría para archivos cifrados con etiquetas de confidencialidad](sensitivity-labels-coauthoring.md)
|Aplicar automáticamente etiquetas de confidencialidad a documentos y mensajes de correo electrónico | [Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md)|
|Use etiquetas de confidencialidad para proteger el contenido de Teams y SharePoint |[Usar etiquetas de confidencialidad con Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](sensitivity-labels-teams-groups-sites.md)|
|Usar etiquetas de confidencialidad para configurar el tipo de vínculo de uso compartido predeterminado para los sitios y documentos individuales en SharePoint y OneDrive |[Usar etiquetas de confidencialidad para establecer el vínculo de uso compartido predeterminado para sitios y documentos en SharePoint y OneDrive](sensitivity-labels-default-sharing-link.md)|
|Aplicar una etiqueta de confidencialidad a un modelo de comprensión de documentos, de modo que los documentos identificados en una biblioteca SharePoint se clasifiquen y se protejan automáticamente |[Aplicar una etiqueta de confidencialidad a un modelo en Microsoft SharePoint Syntex](/microsoft-365/contentunderstanding/apply-a-sensitivity-label-to-a-model)|
|Prevenir o advertir a los usuarios sobre el uso compartido de archivos o correos electrónicos con una etiqueta de confidencialidad específica |[Usar etiquetas de confidencialidad como condiciones en las directivas de DLP](dlp-sensitivity-label-as-condition.md) |
|Aplicar una etiqueta de confidencialidad a un archivo cuando reciba una alerta que indica que hay contenido que contiene datos personales se comparte y necesita protección| [Investigación y corrección de alertas en la administración de riesgos de privacidad](/privacy/priva/risk-management-alerts)|
|Aplicar una etiqueta de retención para conservar o eliminar archivos o correos electrónicos que tengan una etiqueta de confidencialidad específica|[Aplicar una etiqueta de retención automáticamente para conservar o eliminar contenido](apply-retention-labels-automatically.md) |
|Detecte, etiquete y proteja los archivos almacenados en almacenes de datos locales |[Implementación del escáner de Azure Information Protection para clasificar y proteger los archivos automáticamente](/azure/information-protection/deploy-aip-scanner)|
|Detecte, etiquete y proteja los archivos almacenados en almacenes de datos que están en la nube|[Descubrir, clasificar, etiquetar y proteger la información regulada y confidencialidad almacenada en la nube](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|Etiquete columnas de bases de datos de SQL mediante las mismas etiquetas de confidencialidad que las usadas para archivos y correos electrónicos, de modo que la organización tenga una solución de etiquetado unificada que pueda seguir protegiendo estos datos estructurados cuando se exportan |[Clasificación y detección de datos para Azure SQL Database, Azure SQL Managed Instance y Azure Synapse Analytics](/azure/azure-sql/database/data-discovery-and-classification-overview) <br /><br /> [Detección y clasificación de datos de SQL para SQL Server local](/sql/relational-databases/security/sql-data-discovery-and-classification)|
|Aplicar y ver las etiquetas de confidencialidad en Power BI y proteger los datos cuando se guarden fuera del servicio.|[Etiquetas de confidencialidad en Power BI](/power-bi/admin/service-security-sensitivity-label-overview)|
|Supervisar y comprender cómo se usan las etiquetas de confidencialidad en la organización|[Obtenga información sobre la clasificación de datos](data-classification-overview.md)|
|Amplíe las etiquetas de confidencialidad a los servicios y aplicaciones de terceros.|[SDK de Microsoft Information Protection](/information-protection/develop/overview#microsoft-information-protection-sdk)|
|Extender las etiquetas de confidencialidad a través del contenido de mis recursos del Mapa de datos de Microsoft Purview, como Azure Blob Storage, Azure Files, Azure Data Lake Storage y orígenes de datos de varias nubes|[Etiquetado en el mapa de datos de Microsoft Purview](/azure/purview/create-sensitivity-label) |

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

- [Creación de archivos PDF protegidos a partir de archivos de Office](https://support.microsoft.com/topic/aba7e367-e482-49e7-b746-a385e48d01e4)

- [Guía del usuario de etiquetado unificado de Azure Information Protection](/azure/information-protection/rms-client/clientv2-user-guide)

Si las etiquetas de confidencialidad aplican el cifrado para documentos PDF, estos se pueden abrir con Microsoft Edge en Windows o Mac. Para obtener más información y para lectores alternativos, vea [¿Cuáles son los lectores de PDF compatibles para archivos PDF protegidos?](/azure/information-protection/rms-client/protected-pdf-readers#viewing-protected-pdfs-in-microsoft-edge-on-windows-or-mac)
