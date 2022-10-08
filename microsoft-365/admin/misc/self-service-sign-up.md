---
title: Uso del registro de autoservicio en su organización
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: seemg, pablom
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_signup
- AdminSurgePortfolio
- okr_SMB
search.appverid: MET150
description: Obtenga información sobre el registro de autoservicio de Microsoft 365 y los programas de autoservicio disponibles, como Microsoft Power Apps, Microsoft Power Automate y Dynamics 365 for Finance.
ms.date: 03/17/2021
ms.openlocfilehash: e12e3b75be80a78640fb57cceb7aeca1cbd85a45
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68204879"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>Uso del registro de autoservicio en su organización

El registro de autoservicio facilita que los usuarios de su organización se registren para servicios en línea desde Microsoft. Llamamos a este proceso de registro "registro de autoservicio" porque los usuarios pueden registrarse para usar los servicios pagados por su suscripción o usar servicios gratuitos, sin pedirle que tome medidas en su nombre.

## <a name="how-self-service-sign-up-works"></a>Funcionamiento del registro de autoservicio

En el ejemplo siguiente se describe cómo funciona el registro automático para una escuela. El mismo proceso funciona para cualquier organización que tenga programas de autoservicio habilitados en su inquilino.

1. Los alumnos y profesores tienen direcciones de correo electrónico de la escuela que indican que están asociadas con su institución. Por ejemplo, la dirección de correo electrónico jakob@uw.edu puede indicar un estudiante en la Universidad de Washington.
2. Los alumnos y profesores van a [nuestro sitio web](https://go.microsoft.com/fwlink/p/?LinkId=536628) y usan su dirección de correo electrónico para registrarse en los servicios que ofrece su organización, Aplicaciones Microsoft 365 para empresas. También pueden registrarse para obtener otros servicios gratuitos que ofrecemos.
3. Validamos su dirección de correo electrónico y, a continuación, pueden empezar a usar Microsoft 365, Power BI u otros servicios de inmediato.
4. Como administrador de empresa, puede ver quién se ha registrado para una suscripción seleccionando la suscripción en la página **Licencias** de la Centro de administración de Microsoft 365. De este modo, puede ver cuándo hay licencias nuevas o no reconocidas para los servicios del inquilino. Para controlar si los usuarios pueden registrarse para suscripciones de autoservicio, use el cmdlet de PowerShell [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings) con el parámetro **AllowAdHocSubscriptions** . Para obtener más información, consulte [Cómo controlar la configuración de autoservicio?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="available-self-service-programs"></a>Programas de autoservicio disponibles

A continuación se muestran los programas de autoservicio disponibles actualmente. Esta lista se actualizará a medida que se agreguen nuevos programas.

| Programa <br/> | Descripción <br/> | Información adicional <br/> | Sitio web para el registro de autoservicio <br/> |
|:-----|:-----|:-----|:-----|
|Office 365 A1**** <br/> |Cualquier alumno o profesor puede usar una dirección de correo electrónico de la escuela para registrarse de forma gratuita Office 365 y obtener aplicaciones de Office para la web, 1 TB de almacenamiento en la nube de OneDrive y SharePoint Online para sitios de clase, equipo y proyecto.  <br/> |[Office 365 Educación Preguntas más frecuentes técnicas](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 Educación](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 A1 Plus** <br/> |Los alumnos y profesores aptos pueden registrarse para Office 365 A1 Plus, que incluye todo lo mencionado anteriormente más Aplicaciones Microsoft 365 para empresas. Aplicaciones Microsoft 365 para empresas es el software de productividad, incluidos Word, PowerPoint, Excel, Outlook, OneNote, Publisher, Access y Skype Empresarial, que se instala en el equipo de escritorio o portátil.  <br/> |[Office 365 Educación Preguntas más frecuentes técnicas](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 Educación](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BI permite a los usuarios visualizar datos, compartir detecciones y colaborar de nuevas maneras intuitivas. <br/> Si su organización ya se suscribe, también puede ver licencias para "Power BI Pro prueba de usuario individual", que ofrecen a los usuarios acceso gratuito y limitado a funcionalidades avanzadas.  <br/> |[Power BI en su organización](/power-bi/enterprise/service-admin-org-subscription) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**Servicios de administración de derechos (RMS)** <br/> |RMS para individuos es una suscripción de autoservicio gratuita para los usuarios de una organización a los que se les han enviado archivos confidenciales protegidos por Azure Rights Management (Azure RMS), pero su departamento de TI no ha implementado Azure Rights Management (Azure RMS) ni Active Directory Rights Management Services (AD RMS).  <br/> |[RMS para individuos y Azure Rights Management](/azure/information-protection/rms-for-individuals) <br/> |[Portal de Microsoft Rights Management](https://portal.azure.com/) para que pueda comprobar si puede abrir un documento con derechos protegidos determinado.  <br/> |
|**Microsoft Power Apps** <br/> |En Power Apps, puede administrar los datos de la organización ejecutando una aplicación que creó o que otra persona creó y compartió con usted. Las aplicaciones se ejecutan en dispositivos móviles, como teléfonos, o bien puede ejecutarlas en un explorador abriendo Dynamics 365. Puede crear una variedad infinita de aplicaciones, todo ello sin aprender un lenguaje de programación como C#.  <br/> |[Registro de autoservicio para Power Apps](/powerapps/maker/signup-for-powerapps) <br/> |[Microsoft Power Apps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 for Financials** <br/> |Obtenga una solución completa de gestión empresarial y financiera para pequeñas y medianas empresas. Dynamics 365 for Financials facilita el orden, la venta, la facturación y los informes, a partir del primer día.  <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 for Operations** <br/> |Aumente su velocidad de hacer negocios. Las herramientas de ERP completas de Dynamics 365 for Operations proporcionan escalabilidad global e inteligencia digital para ayudarle a crecer a su ritmo.  <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource es un destino para aplicaciones empresariales de software como servicio basadas en la plataforma en la nube de Microsoft. AppSource incluye cientos de aplicaciones, complementos y paquetes de contenido que amplían la funcionalidad de productos de Microsoft como Azure, Dynamics 365, Office 365 y Power BI.  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Incentivos para asociados de Microsoft** <br/> |Microsoft Partner Network proporciona tres tipos de pertenencias. Cada tipo proporciona un conjunto de ventajas para ayudar a su negocio a crecer. A medida que alcance sus objetivos, participe en el programa en el nivel que se adapte a sus necesidades únicas para acceder a más beneficios y desarrollar su relación con nosotros y otros asociados de la red.  <br/> |[Incentivos para asociados de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Incentivos para asociados de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Centro de negocios de Microsoft** <br/> |El Centro de negocios de Microsoft es el portal para los clientes que han realizado compras a través del Contrato de productos y servicios de Microsoft (MPSA). <br/> |[Inicio rápido: Registro en el Centro de negocios de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Centro de negocios de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Centro de servicios de licencias por volumen de Microsoft** <br/> |El Centro de servicios de licencias por volumen de Microsoft muestra las licencias adquiridas en contratos Enterprise, Select, Education (Campus o School), Open Value, Open License y ISV Royalty.  <br/> |[Entrenamiento y recursos de VLSC](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[Centro de servicios de licencias por volumen](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Education Edition** <br/> |Mediante el uso de Minecraft como plataforma de aprendizaje, los educadores pueden motivar e inspirar a cada estudiante para lograr más, e encender una pasión por el aprendizaje. Únase a una comunidad de educadores que aprendan a usar Minecraft para desbloquear el potencial de los estudiantes.  <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |Cargue y comparta vídeos en toda la organización para mejorar la comunicación, la participación y el aprendizaje.  <br/> |[Experiencia del &amp; día 0 de registro](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Power Automate** <br/> |Power Automate es un producto que le ayuda a configurar flujos de trabajo automatizados entre sus aplicaciones y servicios favoritos para sincronizar archivos, obtener notificaciones, recopilar datos y mucho más.  <br/> |[Registro e inicio de sesión en Power Automate](/power-automate/sign-up-sign-in) <br/> |[Power Automate](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Power Virtual Agents** <br/> |Power Virtual Agents permite a los equipos crear fácilmente bots eficaces mediante una interfaz gráfica guiada sin código sin necesidad de científicos de datos o desarrolladores. Power Virtual Agents aborda muchos de los principales problemas relacionados con la creación de bots en el sector en la actualidad. Elimina la brecha entre los expertos en la materia y los equipos de desarrollo que crean los bots, y la latencia larga entre los equipos que reconocen un problema y actualizan el bot para solucionarlo.  <br/> |[Detalles de licencias y acceso](/power-virtual-agents/requirements-licensing) <br/> |[Registrarse en Power Virtual Agents](https://aka.ms/TryPVA) <br/> |
|**Azure AD B2B** <br/> |La colaboración de negocio a negocio (B2B) de Azure Active Directory (Azure AD) le permite invitar a usuarios externos (o "usuarios invitados") a usar los servicios de Azure AD de pago. Algunas características son gratuitas, pero para todas las características de Azure AD de pago, puede invitar hasta cinco usuarios invitados para cada licencia de edición de Azure AD que posea para un empleado o un usuario no invitado en el inquilino. <br/> |[Registro de colaboración B2B de autoservicio para Azure AD](/azure/active-directory/b2b/self-service-portal) <br/> |[Guía de licencias de colaboración B2B de Azure Active Directory](/azure/active-directory/b2b/licensing-guidance) <br/> |
