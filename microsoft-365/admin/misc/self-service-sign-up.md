---
title: Uso del registro de autoservicio en la organización
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_SMB
search.appverid:
- MET150
ms.assetid: 4f8712ff-9346-4c6c-bb63-a21ad7a62cbd
description: Obtenga información sobre el registro de autoservicio de Microsoft 365 y los programas de autoservicio disponibles, como Microsoft Power Apps, Microsoft Flow y Dynamics 365 for Finance.
ms.openlocfilehash: b81c445eca31d7a0deebcb6ff6dc392ec2be3606
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914671"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>Uso del registro de autoservicio en la organización

El registro de autoservicio facilita que los usuarios de su organización se inscriba en los servicios en línea de Microsoft. Llamamos a este proceso de registro "registro de autoservicio" porque los usuarios pueden registrarse para usar servicios pagados por su suscripción o usar servicios gratuitos, sin pedirle que tome medidas en su nombre.
  
## <a name="how-self-service-sign-up-works"></a>Cómo funciona el registro de autoservicio

En el ejemplo siguiente se describe cómo funciona el auto registro para una escuela. El mismo proceso funciona para cualquier organización que tenga programas de autoservicio habilitados en su inquilino.
  
1. Los alumnos y los miembros del profesorado tienen direcciones de correo electrónico de la escuela que indican que están asociados con su institución. Por ejemplo, la dirección de correo jakob@uw.edu puede indicar un estudiante en la Universidad de Washington.
2. Los alumnos y profesores van a nuestro [sitio web](https://go.microsoft.com/fwlink/p/?LinkId=536628)y usan su dirección de correo electrónico para registrarse en los servicios que su organización ofrece, como Aplicaciones de Microsoft 365 para empresas. También pueden registrarse para otros servicios gratuitos que ofrecemos.
3. Validamos su dirección de correo electrónico y, a continuación, pueden empezar a usar Microsoft 365, Power BI u otros servicios de inmediato.
4. Como administrador de negocios, puede ver quién se ha registrado para  una suscripción seleccionando la suscripción en la página Licencias del Centro de administración de Microsoft 365. De este modo, puede ver cuándo hay licencias nuevas o no reconocidas para los servicios en su inquilino. Para controlar si los usuarios pueden registrarse para suscripciones de autoservicio, use el cmdlet [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) PowerShell con el parámetro **AllowAdHocSubscriptions.** Para obtener más información, [vea How do I control self-service settings?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="available-self-service-programs"></a>Programas de autoservicio disponibles

A continuación se encuentran los programas de autoservicio disponibles actualmente. Esta lista se actualizará a medida que se agregan nuevos programas.
  
| Programa <br/> | Descripción <br/> | Información adicional <br/> | Sitio web para el registro de autoservicio <br/> |
|:-----|:-----|:-----|:-----|
|Office 365 A1**** <br/> |Cualquier alumno o profesor puede usar una dirección de correo electrónico educativa para registrarse en Office 365 gratuito y obtener aplicaciones de Office para la web, 1 TB de almacenamiento en la nube de OneDrive y SharePoint Online para sitios de clase, equipo y proyecto.  <br/> |[Preguntas frecuentes técnicas de Office 365 Education](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 Educación](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 A1 Plus** <br/> |Los alumnos y profesores elegibles pueden registrarse en Office 365 A1 Plus, que incluye todo lo mencionado anteriormente, además de Aplicaciones de Microsoft 365 para empresas. Aplicaciones de Microsoft 365 para empresas es un software de productividad, incluido Word, PowerPoint, Excel, Outlook, OneNote, Publisher, Access y Skype Empresarial, que se instala en el equipo de escritorio o portátil.  <br/> |[Preguntas frecuentes técnicas de Office 365 Education](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 Educación](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BI permite a los usuarios visualizar datos, compartir descubrimientos y colaborar de nuevas maneras intuitivas. <br/> Si su organización ya se suscribe, puede ver licencias de "Prueba de usuario individual de Power BI Pro", que ofrecen a los usuarios acceso limitado y gratuito a funcionalidades avanzadas.  <br/> |[Power BI en la organización](./power-bi-in-your-organization.md) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**Servicios de administración de derechos (RMS)** <br/> |RMS para personas es una suscripción de autoservicio gratuita para usuarios de una organización que han sido enviados archivos confidenciales que han sido protegidos por Azure Rights Management (Azure RMS), pero su departamento de TI no ha implementado Azure Rights Management (Azure RMS) ni Active Directory Rights Management Services (AD RMS).  <br/> |[RMS para personas y Azure Rights Management](/azure/information-protection/rms-for-individuals) <br/> |[Portal de Microsoft Rights Management](https://portal.azure.com/) para que pueda comprobar si puede abrir un documento protegido por derechos determinado.  <br/> |
|**Microsoft Power Apps** <br/> |En PowerApps, puedes administrar los datos de la organización ejecutando una aplicación que creaste o que otra persona creó y compartió contigo. Las aplicaciones se ejecutan en dispositivos móviles, como teléfonos, o puede ejecutarlas en un explorador abriendo Dynamics 365. Puedes crear una variedad infinita de aplicaciones, todas sin aprender un lenguaje de programación como C#.  <br/> |[Registro de autoservicio para PowerApps](/powerapps/maker/signup-for-powerapps) <br/> |[Microsoft Power Apps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 for Financials** <br/> |Obtenga una solución completa de administración financiera y empresarial para pequeñas y medianas empresas. Dynamics 365 for Financials facilita el pedido, la venta, la facturación y los informes, a partir del primer día.  <br/> |[Microsoft Dynamics 365 para finanzas](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 para finanzas](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 for Operations** <br/> |Aumente la velocidad de hacer negocios. Las herramientas erp completas de Dynamics 365 for Operations proporcionan escalabilidad global e inteligencia digital para ayudarle a crecer a su ritmo.  <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource es un destino para aplicaciones empresariales de software como servicio integradas en la plataforma en la nube de Microsoft. AppSource incluye cientos de aplicaciones, complementos y paquetes de contenido que amplían la funcionalidad de productos de Microsoft como Azure, Dynamics 365, Office 365 y Power BI.  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Incentivos para partners de Microsoft** <br/> |Microsoft Partner Network proporciona tres tipos de pertenencias. Cada tipo proporciona un conjunto de ventajas para ayudar a su empresa a crecer. A medida que logre sus objetivos, participe en el programa en el nivel que se adapte a sus necesidades únicas para obtener más beneficios y desarrollar su relación con nosotros y otros socios de la red.  <br/> |[Incentivos para partners de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Incentivos para partners de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Centro de negocios de Microsoft** <br/> |El Centro de negocios de Microsoft es el portal para clientes que han realizado compras a través del Contrato de productos y servicios de Microsoft (MPSA). <br/> |[Inicio rápido: registrarse en el Centro de negocios de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Centro de negocios de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Centro de servicio de licencias por volumen de Microsoft** <br/> |El Centro de servicio de licencias por volumen de Microsoft muestra las licencias compradas en Contratos enterprise, Select, Education (Campus o School), Open Value, Open License y ISV Royalty.  <br/> |[Recursos y formación de VLSC](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[Centro de servicio de licencias por volumen](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Education Edition** <br/> |Al usar Minecraft como una plataforma de aprendizaje, los profesores pueden motivar e inspirar a todos los alumnos a lograr más y a encender la pasión por el aprendizaje. Únase a una comunidad de formadores que aprendan a usar Minecraft para desbloquear el potencial de los alumnos.  <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |Cargue y comparta vídeos en toda la organización para mejorar la comunicación, la participación y el aprendizaje.  <br/> |[Experiencia del &amp; día 0 de registro](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Power Automate** <br/> |Power Automate es un producto que te ayuda a configurar flujos de trabajo automatizados entre tus aplicaciones y servicios favoritos para sincronizar archivos, recibir notificaciones, recopilar datos y mucho más.  <br/> |[Registrarse e iniciar sesión en Power Automate](/power-automate/sign-up-sign-in) <br/> |[Power Automate](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Power Virtual Agents** <br/> |Power Virtual Agents permite a los equipos crear bots eficaces con una interfaz gráfica guiada sin código sin necesidad de desarrolladores o científicos de datos. Power Virtual Agents aborda muchos de los principales problemas relacionados con la creación de bots en el sector en la actualidad. Elimina la diferencia entre los expertos en la materia y los equipos de desarrollo que construyen los bots, y la larga latencia entre los equipos que reconocen un problema y actualizan el bot para solucionarlo.  <br/> |[Detalles de licencias y acceso](/power-virtual-agents/requirements-licensing) <br/> |[Registrarse en Power Virtual Agents](https://aka.ms/TryPVA) <br/> |
|**Azure AD B2B** <br/> |La colaboración entre empresas (B2B) de Azure Active Directory (Azure AD) le permite invitar a usuarios externos (o "usuarios invitados") a usar los servicios de Azure AD de pago. Algunas características son gratuitas, pero para las características de Azure AD de pago, puede invitar hasta cinco usuarios invitados por cada licencia de edición de Azure AD que sea de su propiedad para un empleado o un usuario que no sea invitado en su inquilino. <br/> |[Registro de colaboración B2B de Autoservicio para Azure AD](/azure/active-directory/b2b/self-service-portal) <br/> |[Guía de licencias de colaboración B2B de Azure Active Directory](/azure/active-directory/b2b/licensing-guidance) <br/> |