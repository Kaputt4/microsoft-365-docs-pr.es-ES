---
title: Proteger los archivos de SharePoint Online con DLP y etiquetas de confidencialidad
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 'Resumen: aplique Azure Information Protection para proteger los archivos en un sitio de grupo de SharePoint Online altamente confidencial.'
ms.openlocfilehash: 8d802d8c2b5202e51089659264b2e2c14f14ad3d
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214634"
---
# <a name="protect-sharepoint-online-files-with-a-sensitivity-label"></a>Proteger los archivos de SharePoint Online con DLP y etiquetas de confidencialidad

Siga los pasos de este artículo para configurar una etiqueta de confidencialidad que proporcione cifrado y permisos para los archivos. Estos archivos se pueden agregar a una biblioteca de SharePoint configurada para una protección extremadamente confidencial. También puede abrir un archivo directamente desde el sitio y aplicar la etiqueta. La protección de cifrado y permisos viaja con un archivo aunque este se descargue del sitio. 

Estos pasos son parte de una solución más grande para la configuración de protección confidencial para sitios de SharePoint y los archivos de estos sitios. Para obtener más información, consulte [Protección de archivos y sitios de SharePoint Online](../security/office-365-security/secure-sharepoint-online-sites-and-files.md). 

Usar etiquetas de confidencialidad para los archivos de SharePoint Online no es recomendable para todos los clientes, pero es una opción para aquellos que necesitan este nivel de protección de un subconjunto de archivos.

Algunas notas importantes sobre esta solución:
- Si su organización no ha [habilitado las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive (versión preliminar pública)](/microsoft-365/compliance/sensitivity-labels-sharepoint-onedrive-files): cuando se aplica el cifrado a los archivos almacenados en Office 365, el servicio no puede procesar el contenido de estos archivos. No funcionan algunas características de colaboración, como la coautoría, eDiscovery, la búsqueda y Delve. Las directivas de prevención de pérdida de datos (DLP) solo pueden trabajar con los metadatos (incluidas las etiquetas), pero no con el contenido de estos archivos (por ejemplo, números de tarjeta de crédito incluidos en los archivos).

- Esta solución requiere que el usuario seleccione una etiqueta para aplicar la protección. Si necesita el cifrado automático y la capacidad de SharePoint para indizar y revisar los archivos, considere la posibilidad de usar Information Rights Management (IRM) en SharePoint Online. Al configurar una biblioteca de SharePoint para IRM, los archivos se cifran automáticamente al descargarse para su edición.  IRM de SharePoint presenta algunas limitaciones que pueden influir en su decisión. Para obtener más información, consulte [Configurar Information Rights Management (IRM) en el Centro de administración de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/set-up-irm-in-sp-admin-center).

## <a name="admin-setup"></a>Configuración de administración

Para lograr este nivel extra de seguridad en los archivos en un sitio de grupo específico de SharePoint, debe configurar una etiqueta de confidencialidad personalizada que sea su propia etiqueta o una subetiqueta de la etiqueta general para datos altamente regulados. Solo los miembros del grupo de Microsoft 365 para el sitio de grupo de SharePoint Online verán la etiqueta o subetiqueta personalizada en su lista de etiquetas.

- Usar una etiqueta de confidencialidad cuando necesite un número reducido de etiquetas tanto para los equipos de uso global como para los individuales privados.

- Use una subetiqueta de confidencialidad cuando tenga un gran número de etiquetas o quiera organizar etiquetas para equipos extremadamente confidenciales bajo la etiqueta de uso general para archivos extremadamente confidenciales.

Siga [estas instrucciones ](encryption-sensitivity-labels.md) para configurar una etiqueta o subetiqueta aparte con la siguiente configuración:

- El nombre de la etiqueta o de la subetiqueta contiene el nombre del sitio de grupo.
- El cifrado está habilitado
- El grupo de Microsoft 365 del sitio de grupo tiene permisos de coautoría.

Tras crear la nueva etiqueta o subetiqueta, publíquela para los usuarios, que podrán aplicarlas a los archivos, ya sea de forma local antes de cargarlas en el equipo o más tarde, cuando el archivo se almacene en el equipo.
 
Entonces, los usuarios podrán seleccionar la etiqueta de confidencialidad de la opción **Confidencialidad** de la cinta de opciones **Inicio** en Microsoft Word, Excel y PowerPoint.
  
> [!NOTE]
> Si tiene varios sitios de grupo de SharePoint Online extremadamente confidenciales, debe crear varias etiquetas de sensibilidad. 
  
## <a name="adding-permissions-for-external-users"></a>Agregar permisos a usuarios externos
Hay dos maneras de conceder a los usuarios externos el acceso a archivos protegidos con una etiqueta de confidencialidad. En ambos casos, los usuarios externos deben tener una cuenta de Azure AD. Si los usuarios externos no son miembros de una organización que usa Azure AD, pueden obtener una cuenta de Azure AD como usuario individual a través de esta página de suscripción: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).

 - Agregar usuarios externos al grupo de Microsoft 365 para el sitio de grupo. Primero debe agregar la cuenta como un usuario B2B en el directorio. Puede que el [almacenamiento en caché de pertenencia al grupo de Azure Rights Management](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection) tarde un par de horas.  
 - Agregar cuentas de usuario externas directamente a la configuración de la etiqueta. Puede agregar todos los usuarios de una organización (por ejemplo, Fabrikam.com), a un grupo de Microsoft 365 (por ejemplo, un grupo de finanzas dentro de una organización) o a un usuario. Por ejemplo, puede agregar un equipo externo de reguladores a los permisos de su etiqueta de confidencialidad.

## <a name="see-also"></a>Vea también

[Instrucciones de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles](/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[Adopción de la nube y soluciones híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
