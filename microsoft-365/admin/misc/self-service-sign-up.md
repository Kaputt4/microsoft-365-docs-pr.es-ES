---
title: Uso del registro de autoservicio en su organización
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 4f8712ff-9346-4c6c-bb63-a21ad7a62cbd
description: Obtenga información sobre los programas de inscripción y autoservicio disponibles de Microsoft 365, como Microsoft Power Apps, Microsoft Flow y Dynamics 365 para operaciones financieras.
ms.custom: okr_SMB
ms.openlocfilehash: 02d318fbafb6e062f9c3d1592cd6adc7f764fd56
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44045278"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>Uso del registro de autoservicio en su organización

Estamos escuchando sus comentarios y hemos facilitado a los usuarios de su organización que se registren en los servicios en línea de Microsoft. Llamamos a este nuevo proceso de suscripción "registro de autoservicio" porque los usuarios pueden suscribirse a los servicios pagados por la suscripción o usar los servicios gratuitos, sin pedirle que realice ninguna acción en su nombre.
  
## <a name="how-self-service-sign-up-works"></a>Funcionamiento del registro de autoservicio

En el siguiente ejemplo, se describe cómo se realiza la inscripción automática en un centro educativo. El mismo proceso funciona en todas las organizaciones que tienen programas de autoservicio habilitados en su espacio empresarial.
  
1. Los alumnos y los miembros de la Facultad tienen direcciones de correo electrónico de la escuela que indican que están asociadas a su institución. Por ejemplo, la dirección de correo electrónico jakob@uw.edu puede indicar a un estudiante de la Universidad de Washington.

2. Los estudiantes y los profesores van a [nuestro sitio web](https://go.microsoft.com/fwlink/p/?LinkId=536628)y usan su dirección de correo electrónico para registrarse en los servicios que ofrece su organización, como las aplicaciones de Microsoft 365 para empresas. También pueden registrarse para obtener otros servicios gratuitos que ofrecemos.

3. Validamos su dirección de correo electrónico y, a continuación, pueden empezar a usar Microsoft 365, Power BI u otros servicios de inmediato.

4. Como administrador de la empresa, puede ver quién se ha registrado para obtener una suscripción viendo la página **sus productos** en el centro de administración. De esta forma puede ver cuándo hay licencias nuevas o no reconocidas para los servicios de su espacio empresarial. Para controlar si los usuarios pueden suscribirse a las suscripciones de autoservicio, use el cmdlet [set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) de PowerShell con el parámetro **AllowAdHocSubscriptions** . Para obtener más información, vea [¿cómo se controla la configuración de Self-Service?](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/self-service-purchase-faq?view=o365-worldwide)

## <a name="available-self-service-programs"></a>Programas de autoservicio disponibles

A continuación se muestran los programas de autoservicio actualmente disponibles. Esta lista se actualizará a medida que se agreguen nuevos programas.
  
|||||
|:-----|:-----|:-----|:-----|
|**Programa** <br/> |**Descripción** <br/> |**Información adicional** <br/> |Sitio web para registro de Self-Service * * * * <br/> |
|Office 365 a1 * * * * <br/> |Cualquier estudiante o profesor puede usar una dirección de correo electrónico escolar para registrarse gratuitamente para Office 365 y obtener aplicaciones de Office para la web, 1 TB de almacenamiento en la nube de OneDrive y SharePoint Online para los sitios de clase, equipo y proyecto.  <br/> |[Preguntas técnicas más frecuentes sobre Office 365 Education](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Educación](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 a1 más** <br/> |Los estudiantes y profesores elegibles pueden registrarse para Office 365 a1 Plus, que incluye todo lo mencionado anteriormente más Microsoft 365 apps for Enterprise. Microsoft 365 apps for Enterprise es software de productividad, incluidos Word, PowerPoint, Excel, Outlook, OneNote, Publisher, Access y Skype empresarial, que está instalado en el equipo de escritorio o portátil.  <br/> |[Preguntas técnicas más frecuentes sobre Office 365 Education](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Educación](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BI permite a los usuarios visualizar datos, compartir descubrimientos y colaborar en nuevas formas intuitivas. <br/> Si su organización ya está suscrita, también puede ver las licencias de "prueba de usuario individual de Power BI Pro", que ofrece a los usuarios un acceso limitado y gratuito a las capacidades avanzadas.  <br/> |[Power BI en su organización](https://go.microsoft.com/fwlink/p/?LinkId=536626) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**Servicios de administración de derechos (RMS)** <br/> |RMS para personas es una suscripción gratuita de autoservicio para los usuarios de una organización que han enviado archivos confidenciales que han sido protegidos por Azure Rights Management (Azure RMS), pero el Departamento de ti no ha implementado Azure Rights Management (Azure RMS) o Active Directory Rights Management Services (AD RMS).  <br/> |[RMS para usuarios individuales y Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=536627) <br/> |[Portal de Microsoft Rights Management](https://portal.azure.com/) para que pueda comprobar si puede abrir un documento protegido por derechos determinado.  <br/> |
|**Microsoft Power apps** <br/> |En PowerApps, puede administrar los datos organizativos mediante la ejecución de una aplicación que haya creado o que haya creado otro usuario y que se haya compartido con usted. Las aplicaciones se ejecutan en dispositivos móviles como teléfonos, o bien puede ejecutarlas en un explorador al abrir Dynamics 365. Puede crear una variedad infinita de aplicaciones sin tener que aprender un lenguaje de programación como C#.  <br/> |[Registro de autoservicio para PowerApps](https://go.microsoft.com/fwlink/p/?linkid=841461) <br/> |[Microsoft Power apps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 para operaciones financieras** <br/> |Obtenga una solución completa de administración empresarial y financiera para pequeñas y medianas empresas. Dynamics 365 for Financials facilita el pedido, la venta, la facturación y la creación de informes, comenzando el primer día.  <br/> |[Microsoft Dynamics 365 para operaciones financieras](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 para operaciones financieras](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 para operaciones** <br/> |Aumente la velocidad de hacer negocios. Las herramientas ERP completas en Dynamics 365 for Operations proporcionan escalabilidad global e inteligencia digital para ayudarle a crecer a su ritmo.  <br/> |[Microsoft Dynamics 365 para operaciones](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 para operaciones](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource es un destino para las aplicaciones empresariales de software como un solo servicio integradas en la plataforma en la nube de Microsoft. AppSource incluye cientos de aplicaciones, complementos y paquetes de contenido que amplían la funcionalidad de los productos de Microsoft, como Azure, Dynamics 365, Office 365 y Power BI.  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Incentivos para asociados de Microsoft** <br/> |La red de socios de Microsoft proporciona tres tipos de pertenencia. Cada tipo proporciona un conjunto de ventajas para ayudar a su negocio a crecer. A medida que alcanza sus objetivos, participe en el programa en el nivel que mejor se adapte a sus necesidades únicas de acceso a más ventajas y desarrolle su relación con nosotros y con otros socios de la red.  <br/> |[Incentivos para asociados de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Incentivos para asociados de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft Business Center** <br/> |Microsoft Business Center es el portal para los clientes que han realizado compras a través del contrato de productos y servicios de Microsoft (MPSA). <br/> |[Inicio rápido: registrarse en Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Centro de servicios de licencias por volumen de Microsoft** <br/> |El centro de servicios de licencias por volumen de Microsoft muestra licencias adquiridas en Enterprise, Select, Education (campus o School), Open Value, Open License y acuerdos de regalías (ISV).  <br/> |[Recursos y formación de VLSC](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[Centro de servicios de licencias por volumen](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Education Edition** <br/> |Mediante el uso de Minecraft como plataforma de aprendizaje, los educadores pueden motivar y inspirar a todos los alumnos para lograr más y inflaman pasión por aprender. Únase a una comunidad de educadores aprendiendo a usar Minecraft para desbloquear el potencial de los alumnos.  <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |Cargue y Comparta vídeos en su organización para mejorar la comunicación, la participación y el aprendizaje.  <br/> |[Experiencia del &amp; día 0 de suscripción](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Power Automate** <br/> |La automatización de energía es un producto que le ayuda a configurar flujos de trabajo automatizados entre sus aplicaciones y servicios favoritos para sincronizar archivos, obtener notificaciones, recopilar datos, etc.  <br/> |[Registrarse e iniciar sesión para la automatización de la alimentación](https://docs.microsoft.com/power-automate/sign-up-sign-in) <br/> |[Power Automate](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Agentes de Power virtual** <br/> |Power virtual Agents permite a los equipos crear de forma sencilla bots potentes mediante una interfaz gráfica guiada sin código sin la necesidad de científicos o desarrolladores de datos. Power virtual Agents enfrenta muchos de los principales problemas con la creación de robots en la industria de hoy. Elimina el vacío entre los expertos en la materia y los equipos de desarrollo que crean los bots y la larga latencia entre los equipos para reconocer un problema y actualizar el bot para solucionarlo.  <br/> |[Detalles de licencias y acceso](https://go.microsoft.com/fwlink/?linkid=2113708) <br/> |[Registrarse para obtener agentes virtuales de potencia](https://aka.ms/TryPVA) <br/> |