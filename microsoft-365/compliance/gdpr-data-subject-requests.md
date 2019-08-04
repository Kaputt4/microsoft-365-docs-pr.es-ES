---
title: Solicitudes de interesados para el RGPD
description: ''
keywords: Microsoft 365, Microsoft 365 Education, documentación de Microsoft 365, RGPD
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: dc4352ac14f42a227f1572b0c7f1442aa4dec838
ms.sourcegitcommit: c201f5cc13d501e5207ebad166e42f90260af0c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2019
ms.locfileid: "35078910"
---
# <a name="data-subject-requests-and-the-gdpr"></a>Solicitudes de interesados para el RGPD

El reglamento general de protección de datos (RGPD), añade nuevas normas organizaciones que ofrecen bienes y servicios a los ciudadanos de la Unión Europea (UE), o que recopilen y analicen datos de los residentes de la UE, sin importar donde estén ubicados usted o su empresa. Puede encontrar más información en el [tema de resumen del RGPD](gdpr.md). <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWs1SI] 

Este documento le informa sobre la finalización de solicitudes de interesados en virtud del RGPD al usar productos y servicios de Microsoft.

- [Office 365](gdpr-dsr-Office365.md)
- [Azure](gdpr-dsr-Azure.md)
- [Intune](gdpr-dsr-Intune.md)
- [Dynamics 365](gdpr-dsr-Dynamics365.md)
- [Familia de Visual Studio](gdpr-dsr-visual-studio-family.md)
- [Azure DevOps Services](gdpr-dsr-vsts.md)
- [Soporte técnico y servicios profesionales de Microsoft](gdpr-dsr-prof-services.md)

## <a name="terminology"></a>Terminología

Definiciones útiles para el reglamento general de protección de datos, términos utilizados en este documento:

- *Controlador de datos (controlador)*: una persona jurídica, autoridad pública, agencia u otro organismo, que por sí solos o conjuntamente con otras personas, determine el propósito y el medio del procesamiento de datos personales.  
- *Datos personales * e *interesado*: cualquier información relacionada con una persona física identificada o una persona natural identificable (asunto de datos), una persona física identificable es la que puede identificarse, directa o indirectamente.  
- *Procesador:* persona física o jurídica, entidad pública, agencia u otro organismo que procese datos personales en nombre del controlador.  
- *Datos de clientes*: datos producidos y almacenados en las operaciones diarias de su empresa.

## <a name="what-is-a-dsr"></a>¿Qué es un DSR?

El Reglamento General de Protección de Datos (RGPD) otorga derechos a las personas (denominadas "interesados" en el reglamento) para administrar los datos personales recopilados por un empresario u otro tipo de agencia u organización (denominado "responsable del tratamiento de los datos" o simplemente "responsable"). El RGPD ofrece a los interesados derechos específicos sobre sus datos personales, como la obtención de copias de ellos, la solicitud de modificaciones, la restricción de procesamiento, la eliminación o la recepción en un formato electrónico que permita su transferencia a otro responsable del tratamiento.

Como controlador, tendrá que valorar cada DSR y dar una respuesta suficiente, ya sea llevando a cabo la acción solicitada o explicando los motivos por los que el controlador no puede satisfacer el DSR. Un controlador debe consultar con sus propios consejeros jurídicos o asesores de cumplimiento sobre la disposición adecuada de un DSR.

Es posible se requieran varios procesos para completar un DSR, según las reglas de cumplimiento del RGPD de su organización.
  
- **Descubrimiento** El proceso de determinar qué datos son necesarios para completar un DSR.
- **Acceso** La extracción y transmisión potencial al interesado de la información descubierta.
- **Rectificado** La implementación de modificaciones u otros cambios solicitados respecto a los datos personales.
- **Restricción** Limitar el acceso o el procesamiento de los datos, restringiendo el acceso o quitando los datos de la nube de Microsoft.
- **Exportar** Ofrecer los datos en un «formato de datos personales estructurado, de uso común y legible por máquina», como se indica en el «Derecho de portabilidad de datos» del RGPD.
- **Eliminar** Eliminar permanente los datos personales de la nube de Microsoft.

## <a name="specific-dsr-considerations"></a>Consideraciones específicas de DSR

### <a name="insights-generated-by-microsoft-products-or-services"></a>Información generada por los productos o servicios de Microsoft

[La información](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365) pueden ser generada por servicios (como MyAnalytics, etc.). Office 365 también incluye servicios en línea con información a los usuarios y a las organizaciones que los usan. Los datos generados por estos servicios pueden producir datos personales pertinentes para un DSR. Siga el vínculo en la lista siguiente para obtener más información sobre los procesos de DSR específicos de servicios.  

### <a name="dsrs-for-system-generated-logs"></a>DSR para registros generados por el sistema

Los registros y datos relacionados generados por Microsoft pueden considerarse, según la definición de "datos personales" de RGPD, datos personales. No se permite restringir o rectificar los datos de los registros generados por el sistema. Los registros generados por el sistema constituyen acciones realizadas en la nube de Microsoft y datos de diagnóstico, y modificar este tipo de datos podría afectar a los registros históricos de acciones, lo que aumentaría el fraude y los riesgos de seguridad. Microsoft permite acceder, exportar y eliminar los registros generados por el sistema que puedan ser necesarios para completar un DSR. Entre los ejemplos de estos datos se pueden incluir:  

- Datos de uso del servicio de productos, como registros de actividad de usuario.
- Solicitudes de búsqueda de usuarios y datos de consultas.
- Los datos generados por productos y servicios como resultado del funcionamiento del sistema y la interacción por los usuarios u otros sistemas.  

### <a name="yammer-and-kaizala"></a>Yammer y Kaizala

La eliminación de una cuenta de usuario no quitará los registros generados por los sistemas de Yammer y Kaizala. Para quitar los datos de estas aplicaciones, vea uno de los siguientes:

- [Gestión de solicitudes del interesado de RGPD en Yammer Enterprise](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)
- [Exportar o eliminar datos de la organización de un usuario en Kaizala](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)

### <a name="national-clouds"></a>Nubes nacionales

En algunas nubes nacionales, un administrador de TI global necesita eliminar los registros generados por el sistema.

### <a name="microsoft-services"></a>Servicios de Microsoft

Si su organización o sus usuarios se relacionan con Microsoft para recibir soporte técnico de nuestros productos y servicios, es posible que algunos de estos datos contengan datos personales. Para más información, vea [Solicitudes de interesados del soporte técnico y los servicios profesionales de Microsoft para el RGPD](gdpr-dsr-prof-services.md)

### <a name="microsoft-controller-products"></a>Productos para los que Microsoft es el controlador

En algunas circunstancias, los usuarios de su organización pueden acceder a los productos o servicios de Microsoft, para los que Microsoft es el controlador de datos. En estos casos, los usuarios tienen que iniciar su propio DSR directamente con Microsoft y Microsoft satisface las solicitudes directamente con el usuario.

### <a name="third-party-products"></a>Productos de terceros

Para los productos y servicios de terceros a los que se accede a través de la autenticación de cuentas de Microsoft, cualquier solicitud del interesado debe dirigirse al tercero correspondiente.

## <a name="learn-more"></a>Más información

- [Centro de confianza de Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
