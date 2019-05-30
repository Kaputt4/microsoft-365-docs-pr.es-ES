---
title: Solicitudes de servicio de datos de Office 365 con el RGPD
description: Comprenda los derechos de usuario según el RGPD y cómo Office 365 ayuda a las empresas a buscar y actuar en datos como respuesta a solicitudes del interesado.
keywords: Office 365, solicitud del interesado, Microsoft 365, Microsoft 365 Education, documentación de Microsoft 365, RGPD
author: herviicban
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: heicba
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: 8fa5cdfb9ad6d1360eddf11b02fb0619db26a17b
ms.sourcegitcommit: 10b818629fb99c0e88cc877fb256a37ffae3b35f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835454"
---
# <a name="office-365-data-subject-requests-for-the-gdpr"></a>Solicitudes del interesado de Office 365 para el RGPD

## <a name="introduction-to-dsrs"></a>Introducción a las solicitudes del interesado

El Reglamento general de protección de datos (RGPD) otorga derechos a las personas (que se denominan *interesados* en el reglamento) para administrar los datos personales recopilados por una empresa u otro tipo de agencia u organización (es decir, el *responsable de los datos* o, para abreviar, el *responsable*). Los datos personales se definen de forma muy amplia según el RGPD como cualquier dato relacionado con una persona física, ya sea identificada o identificable. El RGPD otorga a los interesados derechos específicos sobre sus datos personales, como la obtención de copias de los datos, la solicitud de cambios, la restricción de su tratamiento o su eliminación, o su recepción en formato electrónico para transferirlos a otro responsable. Las solicitudes formales realizadas por un interesado a un responsable de los datos para que realice una acción en sus datos personales se denominan *solicitudes del interesado* (DSR por sus siglas en inglés). El responsable de los datos está obligado a atender de inmediato cualquier DSR y ofrecer una respuesta adecuada, ya sea realizando la acción solicitada u ofreciendo una explicación de por qué no puede llevarla a cabo. Los responsables de los datos tienen que consultar a sus propios asesores legales o de cumplimiento normativo sobre cómo ofrecer una respuesta adecuada a una DSR concreta.

En esta guía se explica cómo usar productos, servicios y herramientas administrativas de Office 365 con el fin de encontrar y actuar sobre datos personales para responder a solicitudes del interesado. En concreto, incluye cómo encontrar, tener acceso y actuar sobre datos personales hospedados en la nube de Microsoft. Este es un breve resumen de los procedimientos descritos en esta guía:

1.  ***Detectar***: use herramientas de búsqueda y detección, como las que ofrece el Centro de seguridad y cumplimiento (SCC) de Microsoft, para encontrar con facilidad contenido de clientes que pueda ser objeto de una DSR. Después de recopilar documentos potencialmente relevantes, puede realizar una o varias de las acciones de DSR descritas en los pasos siguientes para responder a la solicitud de DSR. Como alternativa, puede determinar que esta última no cumple las directrices de respuesta a las solicitudes del interesado.

2.  ***Obtener acceso***: recupere datos personales hospedados en la nube de Microsoft y, si se le pide, ponga una copia a disposición del interesado.

3.  ***Rectificar***: realice cambios o implemente otras acciones solicitadas en los datos personales, si corresponde.

4.  ***Restringir***: restrinja el tratamiento de datos personales, ya sea quitando las licencias para distintos servicios de Office 365 o desactivando los servicios o las características que desee, siempre que sea posible. También puede quitar los datos de la nube de Microsoft y conservarlos localmente o en otra ubicación.

5.  ***Eliminar***: elimine de forma permanente los datos personales que residen en la nube de Microsoft.

6.  ***Exportar***: envíe una copia electrónica de datos personales al interesado. El "derecho de portabilidad de datos" del RGPD permite a un interesado solicitar una copia electrónica de datos personales en un formato común y de lectura mecánica.

### <a name="terminology"></a>Terminología

A continuación se ofrecen definiciones de términos relacionados con el RGPD.

- *Responsable*: la persona física o legal, autoridad pública, agencia u organismo que solo o junto a otras personas, determina los fines y medios del tratamiento de datos personales; donde los fines y los medios de dicho tratamiento están determinados por la ley de la unión o de un estado miembro, el responsable o los criterios específicos para su nominación pueden ser proporcionados por la ley de un estado miembro o de la unión.

-   *Datos personales* e *interesado*: cualquier información sobre una persona física identificada o identificable (“interesado”); una persona identificable natural es una que puede identificarse, directa o indirectamente, especialmente con referencia a un identificador, con un nombre, un número de identificación, datos de ubicación, un identificador en línea o uno o más elementos específicos físicos, fisiológicos, genéticos, mentales, económicos, culturales o de identidad social de esa persona natural;

-   *Encargado*: persona física o legal, autoridad pública, agencia u otro organismo que trata datos personales en nombre del responsable.

### <a name="how-to-use-this-guide"></a>Cómo utilizar esta guía

Para ayudarle a buscar información relevante a su caso de uso, esta guía está dividida en cuatro partes.

[Parte 1: Responder a solicitudes del interesado sobre datos del cliente](#part-1-responding-to-dsrs-for-customer-data) - : los *datos del cliente* son datos que se producen y almacenan en Office 365 durante las operaciones cotidianas de su negocio. Algunos ejemplos de las aplicaciones de Office 365 más usadas que le permiten crear y editar datos son Word, Excel, PowerPoint, Outlook y OneNote. Office 365 también consta de aplicaciones como SharePoint Online, Teams y Forms que le permiten colaborar con otros usuarios. En la parte 1 de esta guía se explica cómo detectar, tener acceso a, rectificar, restringir, eliminar y exportar datos desde las aplicaciones de Office 365 que se han utilizado para crearlos y almacenarlos en servicios online de Office 365. Aborda productos y servicios en los que Microsoft actúa como encargado de los datos de la organización y, por tanto, se pone la funcionalidad de solicitudes del interesado a disposición del administrador del espacio empresarial.

[Parte 2: Responder a solicitudes del interesado con respecto a la información generada por Office 365](#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365): Office 365 proporciona cierta información a través de servicios como Delve, MyAnalytics y Workplace Analytics. En la parte 2 de esta guía se explica cómo se genera esta información y cómo responder a las solicitudes del interesado relacionadas con ella.

[Parte 3: Responder a solicitudes de interesado sobre registros generados por el sistema](#part-3-responding-to-dsrs-for-system-generated-logs): cuando usa servicios de Office 365 Enterprise, Microsoft genera información como registros de servicio que registran el uso o el rendimiento de las características de los servicios en línea. La mayoría de los datos de servicio generados contienen identificadores anónimos generados por Microsoft y por ello a esta categoría se la denomina *registros generado por el sistema* en este documento. Aunque estos datos no pueden atribuirse a un interesado específico sin el uso de información adicional, algunos pueden ser considerados personales dentro de la definición del RGPD de "datos personales". La parte 3 de esta guía trata acerca de cómo acceder a, eliminar y exportar registros generados por el sistema.

[Parte 4: Recursos adicionales para ayudarle con las solicitudes del interesado](#part-4-additional-resources-to-assist-you-with-dsrs): en la parte 4 de esta guía aparecen escenarios limitados en los que Microsoft es el responsable de los datos cuando se usan determinados servicios y productos de Office 365.

> [!NOTE]
> En la mayoría de casos, cuando los usuarios de la organización usan servicios y productos de Microsoft Office 365, usted es el responsable de los datos y Microsoft el encargado de los datos. Como responsable de los datos, es responsable de responder directamente ante el interesado. Para ayudarle con esto, en las tres primeras partes de esta guía se detallan las funcionalidades técnicas disponibles para la organización a fin de responder a una solicitud DSR. Aunque en algunos escenarios limitados, Microsoft será el responsable de los datos cuando las personas usen determinados servicios y productos de Office 365. En estos casos, la información proporcionada en la parte 4 contiene instrucciones sobre cómo los interesados pueden enviar sus solicitudes DSR a Microsoft.


### <a name="office-365-national-clouds"></a>Nubes nacionales de Office 365

Los servicios de Microsoft Office 365 también están disponibles en los siguientes entornos de nube nacional: [Office 365 Germany](https://support.office.com/article/learn-about-office-365-germany-8a5a4bbc-667a-4cac-8769-d8ac9015db4c), [Office 365 ofrecido por 21Vianet (China)](https://support.office.com/article/Learn-about-Office-365-operated-by-21Vianet-A8AB5061-3346-4DA0-BB7C-5260822B53AE) y [Office 365 Administración pública de EE. UU.](https://technet.microsoft.com/library/mt774581.aspx) La mayoría de las instrucciones para administrar las solicitudes del interesado descritas en este documento se aplican a estos entornos de nube nacional. Aunque, debido a la naturaleza aislada de estos entornos, hay algunas excepciones. Cuando son relevantes para una subsección determinada, estas excepciones se mencionan en una nota correspondiente.

### <a name="hybrid-deployments"></a>Implementaciones híbridas

Puede que la organización de Office 365 se componga de ofertas de Microsoft que son una combinación de productos de servidor local y servicios basados en la nube. En general, una implementación híbrida suele consistir en el uso compartido de cuentas de usuario (administración de identidades) y recursos (como buzones, sitios web y datos) que existen en la nube y en la instalación local. Entre los escenarios híbridos comunes se incluyen:
- Implementaciones híbridas de Exchange, en la que algunos usuarios tienen buzones locales y otros tienen buzones de Exchange Online.
- Implementaciones híbridas de SharePoint, en las que los servidores de archivos y del sitio son locales y las cuentas de OneDrive para la Empresa están en Office 365.
- El sistema de administración de identidades local (Active Directory) que se sincroniza con Azure Activity Directory, que es el servicio de directorio subyacente en Office 365.

Al responder a una solicitud de DSR, es posible que tenga que determinar si los datos relevantes para una solicitud de este tipo se encuentran en la organización local o en la nube de Microsoft y, luego, seguir los pasos adecuados para responder a la solicitud. La guía de solicitudes del interesado de Office 365 (esta guía) ofrece instrucciones para responder a los datos basados en la nube. Para obtener instrucciones sobre los datos de la organización local, vea [RGPD para servidores locales de Office](https://docs.microsoft.com/Office365/Enterprise/gdpr-for-office-servers). 


## <a name="part-1-responding-to-dsrs-for-customer-data"></a>Parte 1: Responder a solicitudes del interesado sobre datos del cliente

Las instrucciones para responder a las solicitudes de interesado de los datos de clientes se dividen en las cuatro secciones siguientes.

- [Usar la herramienta Búsqueda de contenido eDiscovery para responder a las solicitudes de interesado](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs)

- [Usar una función integrada en la aplicación para responder a las solicitudes de interesado](#using-in-app-functionality-to-respond-to-dsrs)

- [Responder a solicitudes de interesado de corrección](#responding-to-dsr-rectification-requests)

- [Responder a solicitudes  de DSR](#responding-to-dsr-restriction-requests)

### <a name="how-to-determine-the-office-365-applications-that-may-be-in-scope-for-a-dsr-for-customer-data"></a>Cómo determinar las aplicaciones de Office 365 que pueden estar en el ámbito de una solicitud de datos de interesado de datos de clientes

Para ayudarle a determinar dónde buscar datos personales o qué buscar, resulta útil identificar las aplicaciones de Office 365 que los usuarios de su organización pueden usar para crear y almacenar los datos en Office 365. Conocer esto limita las aplicaciones de Office 365 que están en el ámbito de una solicitud de interesado y le ayuda a determinar cómo buscar y acceder a los datos personales relacionados con una solicitud de interesado. En concreto, esto significa si puede usar la herramienta de búsqueda de contenido o si ha de volver a usar la función integrada de la aplicación en la que se crearon los datos.

Una forma rápida de identificar las aplicaciones de Office 365 que los usuarios de su organización usan para crear datos de clientes consiste en determinar qué aplicaciones están incluidas en la suscripción a Office 365 de su organización. Para ello, puede acceder a las cuentas de usuario en el portal de administrador de Office 365 y la información de licencia del producto. Vea [Asignar licencias a usuarios en Office 365 para empresas.](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users)

## <a name="using-the-content-search-ediscovery-tool-to-respond-to-dsrs"></a>Usar la herramienta Búsqueda de contenido eDiscovery para responder a solicitudes del interesado

Al buscar datos personales en el conjunto más amplio de datos que su organización crea y almacena en Office 365, debería considerar qué aplicaciones es más probable que se hayan usado para crear los datos que busca. Microsoft calcula que más del 90 % de los datos de una organización que se almacenan en Office 365 se han creado en Word, Excel, PowerPoint, OneNote y Outlook. Es muy probable que los documentos creados en estas aplicaciones de Office, aunque se hayan adquirido mediante Office 365 ProPlus o una licencia perpetua de Office, estén almacenados en un sitio de SharePoint Online, en la cuenta de OneDrive para la Empresa de un usuario o en el buzón de Exchange Online de un usuario. Esto significa que puede usar la herramienta Búsqueda de contenido eDiscovery para buscar (y realizar otras acciones relacionadas con solicitudes del interesado) en sitios de SharePoint Online, cuentas de OneDrive para la Empresa y buzones de Exchange Online (incluidos los sitios y buzones asociados a Grupos de Office 365, Microsoft Teams, EDU Assignments y StaffHub) para encontrar documentos y elementos del buzón que puedan ser relevantes para la DSR que investiga. También puede usar la herramienta Búsqueda de contenido para descubrir datos del cliente creados en otras aplicaciones de Office 365.

En la siguiente tabla se enumeran las aplicaciones de Office 365 que los usuarios utilizan para crear contenido de cliente y que pueden detectarse con la Búsqueda de contenido. Esta sección de la guía de DSR ofrece instrucciones sobre cómo detectar, tener acceso a, exportar y eliminar datos creados con estas aplicaciones de Office 365.

***Tabla 1: Aplicaciones en las que se puede usar la Búsqueda de contenido para buscar datos de clientes***

| | |
| :---: | :---:|
<img src="media/O365-DSR-Doc-Final_image3.png" /><br/>Calendario | <img src="media/O365-DSR-Doc-Final_image4.png" /><br />SharePoint Online |
| <img src="media/O365-DSR-Doc-Final_image5.png" /><br/>Excel |<img src="media/O365-DSR-Doc-Final_image6.png" /><br /> Skype Empresarial|
| <img src="media/O365-DSR-Doc-Final_image7.png" /><br/>Office Lens |<img src="media/O365-DSR-Doc-Final_image8.png" /><br/> Tareas |
|<img src="media/O365-DSR-Doc-Final_image9.png" /><br/>OneDrive para la Empresa|<img src="media/O365-DSR-Doc-Final_image10.png" /><br />Teams|
| <img src="media/O365-DSR-Doc-Final_image11.png" /><br />OneNote| <img src="media/O365-DSR-Doc-Final_image12.png" />To-Do |
| <img src="media/O365-DSR-Doc-Final_image13.png" /><br />Outlook/Exchange Online | <img src="media/O365-DSR-Doc-Final_image14.png" /><br />Vídeo |
| <img src="media/O365-DSR-Doc-Final_image15.png" /><br />Contactos|<img src="media/O365-DSR-Doc-Final_image16.png" /><br />Visio |
| <img src="media/O365-DSR-Doc-Final_image17.png" /><br />PowerPoint | ![WordIcon.png](media/WordIcon.png) <br/> Word
||

<!-- end of table -->

> [!NOTE]
> La herramienta de Búsqueda de contenido eDiscovery no está disponible en [Office 365 ofrecido por 21Vianet (China)](https://support.office.com/article/Learn-about-Office-365-operated-by-21Vianet-A8AB5061-3346-4DA0-BB7C-5260822B53AE). Esto significa que no puede usar esta herramienta para buscar y exportar datos del cliente en las aplicaciones de Office 365 que se muestran en la tabla 1. Sin embargo, puede usar la herramienta eDiscovery local en Exchange Online para buscar contenido en buzones de usuario. También puede usar el Centro de eDiscovery en SharePoint Online para buscar contenido en cuentas de OneDrive y sitios de SharePoint. Como alternativa, puede pedirle a un propietario del documento que le ayude a buscar y realizar cambios en el contenido, eliminarlo o exportarlo si es necesario. Para obtener más información, vea:</br></br>&nbsp;&nbsp;• [Crear una búsqueda de eDiscovery local](https://technet.microsoft.com/library/dd353189(v=exchg.150).aspx)</br>&nbsp;&nbsp;• [Configurar un centro de eDiscovery en SharePoint Online](https://support.office.com/article/Set-up-an-eDiscovery-Center-in-SharePoint-Online-A18F8975-AA7F-43B4-A7D6-001D14744D8E)

### <a name="using-content-search-to-find-personal-data"></a>Usar la Búsqueda de contenido para buscar datos personales

El primer paso para responder a una solicitud de interesado es encontrar los datos personales requeridos en la misma. Para esto, debe usar las herramientas eDiscovery de Office 365 para buscar datos personales (entre todos los datos de su organización en Office 365), o puede dirigirse directamente a la aplicación nativa en la que se crearon los datos. Este primer paso (encontrar y revisar los datos personales en cuestión) le ayudará a determinar si una solicitud de interesado cumple los requisitos de su organización para respetarla o rechazarla. Por ejemplo, después de encontrar y revisar los datos personales en cuestión, puede determinar que la solicitud no cumple los requisitos de su organización porque puede afectar a los derechos y libertades de terceros, o porque los datos personales forman parte de un registro de negocios que su organización tiene interés en retener.

Como se indicó anteriormente, Microsoft estima que las aplicaciones de Microsoft Office, como Word y Excel, se usan para crear más del 90 % de los datos de una organización. Esto significa que puede usar la Búsqueda de contenido en el Centro de seguridad y cumplimiento para buscar la mayoría de los datos relacionados con las DSR.

En esta guía se presupone que usted o la persona que busca datos personales que puedan ser relevantes para una solicitud DSR ya están familiarizados, o al menos tienen cierta experiencia, con la herramienta de Búsqueda de contenido del Centro de seguridad y cumplimiento. Para obtener instrucciones generales sobre el uso de la Búsqueda de contenido, vea [Búsqueda de contenido en Office 365](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4). Asegúrese de que la persona responsable de las búsquedas tenga asignados los permisos necesarios en el Centro de seguridad y cumplimiento. Esta persona debe agregarse como miembro del grupo de roles de Supervisor de eDiscovery en el Centro de seguridad y cumplimiento; vea [Asignar permisos de eDiscovery en el Centro de seguridad y cumplimiento de Office 365](https://support.office.com/article/Assign-eDiscovery-permissions-in-the-Office-365-Security-Compliance-Center-5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7). Considere la posibilidad de agregar al grupo de roles de Supervisor de eDiscovery otros usuarios de la organización implicados en la investigación de solicitudes DSR para que puedan llevar a cabo las acciones necesarias en la herramienta de Búsqueda de contenido tales como previsualizar y exportar resultados de la búsqueda. Pero, a menos que configure los límites de cumplimiento normativo (tal y como se describe [aquí](#set-up-compliance-boundaries-to-limit-the-scope-of-content-searches)), tenga en cuenta que un Supervisor de eDiscovery puede buscar en todas las ubicaciones de contenido de la organización, incluidas aquellas que puedan estar o no relacionadas con una investigación de DSR.

Después de encontrar los datos, puede realizar la acción específica para satisfacer la solicitud del interesado.

> [!NOTE]
> En Office 365 Alemania, el Centro de seguridad y cumplimiento se encuentra en https://protection.office.de.


#### <a name="searching-content-locations"></a>Buscar ubicaciones de contenido

Puede buscar los siguientes tipos de ubicaciones de contenido con la herramienta de búsqueda de contenido.

-   Buzones de Exchange Online; incluyendo aquellos asociados con Grupos de Office 365 y Microsoft Teams

-   Carpetas públicas de Exchange Online

-   Sitios de SharePoint Online; incluyendo aquellos asociados con Grupos de Office 365 y Microsoft Teams

-   Cuentas de OneDrive para la Empresa

> [!NOTE]
> En esta guía se asume que todos los datos que puedan ser relevantes para una investigación de DSR se almacenan en Office 365; en otras palabras, se almacenan en la nube de Microsoft. Los datos almacenados en el equipo local de un usuario o en las instalaciones de los servidores de archivos de la organización quedan fuera del ámbito de una investigación de DSR en datos almacenados en Office 365. Para más información sobre cómo responder a las solicitudes de datos de DSR en organizaciones locales, vea [RGPD para servidores locales de Office](https://docs.microsoft.com/Office365/Enterprise/gdpr-for-office-servers).


#### <a name="tips-for-searching-content-locations"></a>Sugerencias para la búsqueda de ubicaciones de contenido

-   Empiece por buscar todas las ubicaciones de contenido de la organización (lo que puede hacerse en una sola búsqueda) para determinar con rapidez qué ubicaciones de contenido contienen elementos que coinciden con la consulta. A continuación, puede volver a ejecutar la búsqueda y restringir el ámbito a las ubicaciones específicas que contienen artículos relevantes.

-   Use las estadísticas de búsqueda para identificar las ubicaciones principales que contienen los elementos que coinciden con la consulta de búsqueda. Consulte [Ver las estadísticas de palabras clave de resultados de búsqueda de contenido](https://support.office.com/article/View-keyword-statistics-for-Content-Search-results-9701a024-c52e-43f0-b545-9a53478aec04).

-   Busque en el registro de auditoría de Office 365 actividades recientes de archivos y carpetas realizadas por el usuario sometido a la solicitud de interesado. Buscar en el registro de auditoría devolverá una lista con el nombre y la ubicación de los recursos que ha utilizado el usuario recientemente. Puede usar esta información para crear una consulta de búsqueda de contenido. Vea [Buscar en el registro de auditoría en el Centro de seguridad y cumplimiento de Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).

#### <a name="building-search-queries-to-find-personal-data"></a>Generar consultas de búsqueda para encontrar datos personales

Es muy probable que la DSR que investigue contenga identificadores que puede utilizar como palabras clave para buscar los datos personales. A continuación, se muestran algunos de los identificadores más comunes cuando se buscan datos personales:

-   Dirección de correo electrónico o el alias

-   Número de teléfono

-   Dirección de correo

-   Número de id. de empleado

-   Número de identificación nacional o versión de miembro de la UE del número de la Seguridad Social.

Es probable que la DSR que está investigando tenga un identificador y otros detalles sobre los datos personales solicitados que puede usar en una consulta de búsqueda.

Buscar solo una dirección de correo electrónico o la id. de un empleado probablemente devolverá una gran cantidad de resultados. Para limitar el ámbito de la búsqueda y que devuelva contenido más relevante en relación con la solicitud de interesado, puede agregar condiciones a la consulta de búsqueda. Al agregar una condición, la palabra clave y la condición de búsqueda se conectan de forma lógica por el operador booleano **AND**. Esto significa que solo los elementos que coincidan *tanto* con la palabra clave como con la condición aparecerán en los resultados de la búsqueda.

La tabla siguiente incluye algunas condiciones que puede usar para restringir el ámbito de búsqueda. También se muestran los valores que puede usar para cada condición para buscar tipos de documento específicos y elementos del buzón.

***Tabla 2: Limitar el ámbito de búsqueda mediante el uso de condiciones***
<!-- table starts here -->

||||
| :--- | :--- |:--- |
|**Condición**|**Descripción** |**Ejemplo de valores de condición**|
| Tipo de archivo | La extensión de un documento o archivo. Use esta condición para buscar documentos de Office y archivos creados en aplicaciones de Office 365. Use esta condición al buscar documentos ubicados en sitios de SharePoint Online y cuentas de OneDrive para la Empresa.<br/>Tenga en cuenta que la propiedad correspondiente del documento es el tipo de archivo. <br/>Para obtener una lista completa de extensiones de archivo que puede buscar, consulte [Extensiones de nombre de archivo y tipos de archivos analizados predeterminados en SharePoint](https://technet.microsoft.com/library/jj219530.aspx).|&nbsp;&bull;&nbsp;&nbsp;CSV: busca archivos con valores separados por coma (CSV); Los archivos de Excel se pueden guardar en formato CSV y un archivo CSV puede importarse fácilmente a Excel<br><br>&bull;&nbsp;&nbsp;docx: busca archivos de Word <br><br>&bull;&nbsp;&nbsp;mpp: busca archivos de Project <br/><br>&bull;&nbsp;&nbsp;one: busca archivos de OneNote <br><br>&bull;&nbsp;&nbsp;PDF: busca archivos guardados en formato PDF <br><br>&bull;&nbsp;&nbsp;pptx: busca archivos de PowerPoint <br><br>&bull;&nbsp;&nbsp;xlxs: busca archivos de Excel <br><br>&bull;&nbsp;&nbsp;vsd: busca archivos de Visio <br><br>&bull;&nbsp;&nbsp;wmv: busca archivos de vídeo de Windows Media <br>|
| Tipo de mensaje | El tipo de mensaje de correo electrónico que buscar. Use esta condición para buscar en los buzones de los contactos (Contactos), las tareas de reuniones (Calendario) o las conversaciones de Skype Empresarial. Tenga en cuenta que la propiedad de correo electrónico correspondiente es *tipo*.|&bull;&nbsp;&nbsp;*contactos*: busca en la lista de Mis contactos de un buzón <br><br>&bull;&nbsp;&nbsp;*correo electrónico*: busca mensajes de correo electrónico <br><br>&bull;&nbsp;&nbsp;*mensajería instantánea*: busca conversaciones de Skype Empresarial<br><br>&bull;&nbsp;&nbsp;*reuniones*: busca convocatorias de reunión y citas (Calendario) <br><br>&bull;&nbsp;&nbsp;*tareas*: busca en la lista de Mis tareas (Tareas); usar este valor también devolverá las tareas creadas en Microsoft To-Do.<br>|
| Etiqueta de cumplimiento |La etiqueta asignada a un mensaje de correo electrónico o un documento. Las etiquetas se usan para clasificar correos electrónicos y documentos para el gobierno de datos y para aplicar reglas de retención basadas en la clasificación definida por la etiqueta. Use esta condición para buscar elementos que tengan una etiqueta asignada automática o manualmente.<br/>Esta condición es útil para las investigaciones de DSR porque es posible que su organización utilice etiquetas para clasificar contenido relacionado con la privacidad de datos o que contenga datos personales o información confidencial. Consulte la sección "Usar la búsqueda de contenido para encontrar todo el contenido con una etiqueta específica" en [Información general sobre etiquetas en Office 365](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30).|compliancetag="datos personales"|
||||

  <!-- table ends here -->                                                                                           
Hay muchas más propiedades y condiciones de búsqueda de correo electrónico y documentos que puede usar para crear consultas de búsqueda más complejas. Vea las secciones siguientes en el tema de ayuda [Consultas de palabras clave y condiciones de búsqueda para buscar contenido](https://support.office.com/article/Keyword-queries-and-search-conditions-for-Content-Search-c4639c2e-7223-4302-8e0d-b6e10f1c3be3) para obtener más información.

- [Propiedades del correo electrónico que permiten búsquedas](https://support.office.com/article/Keyword-queries-and-search-conditions-for-Content-Search-c4639c2e-7223-4302-8e0d-b6e10f1c3be3)

- [Propiedades de sitio (documento ) que se pueden buscar](https://support.office.com/article/Keyword-queries-and-search-conditions-for-Content-Search-c4639c2e-7223-4302-8e0d-b6e10f1c3be3)

- [Condiciones de búsqueda](https://support.office.com/article/Keyword-queries-and-search-conditions-for-Content-Search-c4639c2e-7223-4302-8e0d-b6e10f1c3be3)

#### <a name="searching-for-personal-data-in-sharepoint-lists-discussions-and-forms"></a>Buscar datos personales en discusiones, formularios y listas de SharePoint

Además de buscar datos personales en los documentos, también puede usar la búsqueda de contenido para buscar otros tipos de datos creados con las aplicaciones nativas de SharePoint Online. Esto incluye aquellos creados con discusiones, formularios de datos y listas de SharePoint. Al ejecutar una búsqueda de contenido y buscar sitios de SharePoint Online (o OneDrive para Empresas) se devolverán datos de listas, discusiones y formularios que cumplan los criterios de búsqueda en los resultados.

##### <a name="examples-of-search-queries"></a>Ejemplo de consultas de búsqueda

A continuación se muestran algunos ejemplos de consultas de búsqueda que usan palabras clave y condiciones para buscar datos personales como respuesta a una solicitud de interesado. Los ejemplos muestran dos versiones de la consulta: uno de la sintaxis de palabras clave (donde la condición va incluida en el cuadro de palabras clave) y otro con la versión basada en GUI de la consulta con condiciones.

##### <a name="example-1"></a>Ejemplo 1

Este ejemplo devuelve archivos de Excel ubicados en sitios de SharePoint Online y cuentas de OneDrive para la Empresa que contienen la dirección de correo electrónico especificada. Tenga en cuenta que los archivos pueden aparecer si la dirección de correo se encuentra en los metadatos de los mismos.

***Sintaxis de palabras clave***

pilar@contoso.com AND filetype="xlxs"

***GUI***

![](media/O365-DSR-Doc_image18.png)

##### <a name="example-2"></a>Ejemplo 2

Este ejemplo devuelve archivos de Excel o Word ubicados en sitios de SharePoint Online y cuentas de OneDrive para la Empresa que contienen la id. o la fecha de nacimiento del empleado especificado.

(98765 OR "20-01-1990") AND (filetype="xlxs" OR filetype="docx")

***GUI***

![](media/O365-DSR-Doc_image19.png)

##### <a name="example-3"></a>Ejemplo 3

Este ejemplo devuelve mensajes de correo electrónico que contienen los números de identificación especificados, que en este caso es un número de la Seguridad Social de Francia (INSEE)

"1600330345678 97" AND kind="email"

***GUI***

![](media/O365-DSR-Doc_image20.png)

#### <a name="working-with-partially-indexed-items-in-content-search"></a>Trabajar con elementos parcialmente indizados en la búsqueda de contenido

Los elementos parcialmente indizados (también llamados *elementos no indizados*) son elementos del buzón de Exchange Online y documentos en los sitios de SharePoint Online y OneDrive para la Empresa que, por algún motivo no se han indizado por completo para su búsqueda, lo que significa que no es posible encontrarlos con una búsqueda de contenido. La mayoría de los mensajes de correo electrónico y documentos del sitio se indizan correctamente porque encuentran dentro de los [límites de indización de Office 365](https://support.office.com/article/limits-for-content-search-in-the-office-365-security-compliance-center-78fe3147-1979-4c41-83bb-aeccf244368d??). Los motivos por los que mensajes de correo electrónico y archivos no se indizan para su búsqueda incluyen:

-   El tipo de archivo [no se reconoce para su indización, o no es compatible](https://support.office.com/article/partially-indexed-items-in-content-search-in-office-365-d1691de4-ca0d-446f-a0d0-373a4fc8487b??), aunque a veces sí es compatible con la indización, pero se produjo un error en un archivo específico.

-   Los mensajes de correo electrónico tienen un archivo adjunto sin un identificador válido, como un archivo de imagen (esta es la causa más común de que un elemento de correo electrónico esté parcialmente indizado).

-   Los archivos adjuntos a los mensajes de correo electrónico son demasiado grandes o numerosos.

Le recomendamos que obtenga más información acerca de los elementos parcialmente indizados para poder trabajar con ellos al responder a solicitudes de interesados. Para obtener más información, consulte:

-   [Elementos parcialmente indizados en la búsqueda de contenido en Office 365](https://support.office.com/article/partially-indexed-items-in-content-search-in-office-365-d1691de4-ca0d-446f-a0d0-373a4fc8487b??)

-   [Investigar elementos indizados parcialmente en eDiscovery de Office 365](https://support.office.com/article/investigating-partially-indexed-items-in-office-365-ediscovery-4e8ff113-6361-41e2-915a-6338a7e2a1ed)

-   [Exportar elementos sin indexar](https://support.office.com/article/Export-Content-Search-results-from-the-Office-365-Security-Compliance-Center-ed48d448-3714-4c42-85f5-10f75f6a4278#unidexeditems)

#### <a name="tips-for-working-with-partially-indexed-items"></a>Sugerencias para trabajar con elementos indizados parcialmente

Es posible que los datos susceptibles a una investigación de solicitud de interesado se encuentren en un elemento parcialmente indizado. A continuación se muestran algunas sugerencias para trabajar con estos elementos:

-   Después de ejecutar una búsqueda, el número estimado de elementos parcialmente indexados se muestra en las estadísticas. Esta estimación no incluye elementos parcialmente indexados en SharePoint Online y OneDrive para la Empresa. Exporte los informes para realizar una búsqueda de contenido y así obtener información sobre elementos parcialmente indizados. El informe **elementos no indizados.csv** contiene información sobre elementos no indizados, incluida la ubicación del elemento, la dirección URL si el elemento está en SharePoint Online o OneDrive para la Empresa y la línea de asunto (para mensajes) o el nombre del documento. Para obtener más información, vea [Exportar un informe de búsqueda de contenido](https://support.office.com/article/Export-a-Content-Search-report-5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9).

-   Las estadísticas y la lista de elementos parcialmente indizados devueltos con los resultados de una búsqueda de contenido son todos los elementos parcialmente indizados de las ubicaciones de contenido que se buscan.

-   Para recuperar elementos parcialmente indizados que pueden estar relacionados con una investigación de solicitud de interesado, puede realizar una de las siguientes acciones.

##### <a name="export-all-partially-indexed-items"></a>Exportar todos los elementos parcialmente indexados

Puede exportar tanto los resultados de una búsqueda de contenido y los elementos parcialmente indexados de la ubicación de contenido en la que se ha realizado la búsqueda. También puede exportar solo los elementos parcialmente indizados y abrirlos en sus aplicaciones nativas para revisar el contenido. Deberá usar esta opción para exportar elementos de SharePoint Online y OneDrive para la Empresa. Consulte [Exportar resultados de búsqueda de contenidos del Centro de seguridad y cumplimiento de Office 365](https://support.office.com/article/Export-Content-Search-results-from-the-Office-365-Security-Compliance-Center-ed48d448-3714-4c42-85f5-10f75f6a4278).

##### <a name="export-a-specific-set-of-partially-indexed-items-from-mailboxes"></a>Exportar un conjunto específico de elementos parcialmente indexados de buzones

En lugar de exportar todos los elementos de buzones parcialmente indexados de una búsqueda, puede volver a ejecutar una búsqueda de contenido para buscar una lista específica de elementos parcialmente indizados y, a continuación, exportarlos. Tenga en cuenta que solo puede hacer esto con elementos de buzones. Consulte [Preparar un archivo CSV para una búsqueda de contenido en Office 365](https://support.office.com/article/prepare-a-csv-file-for-a-targeted-content-search-in-office-365-82c97bb4-2b64-4edc-804d-cedbda525d22).


### <a name="next-steps"></a>Pasos siguientes

Después de encontrar los datos personales relevantes para la solicitud de interesado, asegúrese de conservar la búsqueda de contenido específica que usó para hallarlos. Es probable que vuelva a usarla para completar otros pasos del proceso de respuesta a la solicitud de interesado, como [obtener una copia de los datos](#providing-a-copy-of-personal-data), [exportarlos](#exporting-personal-data) o [eliminarlos de forma permanente](#deleting-personal-data).

### <a name="additional-considerations-for-selected-applications"></a>Consideraciones adicionales para aplicaciones seleccionadas

Las siguientes secciones describen factores que debe tener en cuenta a la hora de buscar datos en las aplicaciones de Office 365 siguientes.

-   [Office Lens](#office-lens)

-   [Configuración de la experiencia de OneDrive para la Empresa y SharePoint](#onedrive-for-business-and-sharepoint-online-experience-settings)

-   [Microsoft Teams para educación](#microsoft-teams-for-education)

-   [Microsoft To-Do](#microsoft-to-do)

-   [Skype Empresarial](#skype-for-business)

#### <a name="office-lens"></a>Office Lens

Un usuario con Office Lens (una aplicación para la cámara compatible con dispositivos iOS, Android y Windows) puede tomar una fotografía de una pizarra, documentos físicos, tarjetas de presentación y otros elementos que contengan gran cantidad de texto. Office Lens utiliza tecnología de reconocimiento óptico de caracteres para extraer el texto de una imagen y guardarlo en un documento de Office como puede ser un archivo de Word, OneNote o PowerPoint, o a un archivo PDF. A continuación, los usuarios pueden cargar el archivo que contiene el texto de la imagen en sus cuentas de OneDrive para la Empresa en Office 365. Esto significa que puede utilizar la herramienta de búsqueda de contenido para buscar, eliminar y exportar datos y acceder a ellos en archivos creados a partir de una imagen de Office Lens. Para más información sobre Office Lens, consulte:

-   [Office Lens para iOS](https://support.office.com/article/Office-Lens-for-iOS-fbdca5f4-1b1b-4391-a931-dc1c2582397b)

-   [Office Lens para Android](https://support.office.com/article/Office-Lens-for-Android-ec124207-0049-4201-afaf-b5874a8e6f2b)

-   [Office Lens para Windows](https://support.office.com/article/Office-Lens-for-Windows-577ec09d-8da2-4029-8bb7-12f8114f472a)

#### <a name="onedrive-for-business-and-sharepoint-online-experience-settings"></a>Configuración de la experiencia de OneDrive para la Empresa y SharePoint Online

Además de los archivos creados por usuarios almacenados en las cuentas de OneDrive para la Empresa y los sitios de SharePoint Online, estos servicios almacenan información acerca del usuario que se utiliza para habilitar varias experiencias. Los usuarios que sigan en su organización pueden acceder a gran parte de esta información mediante funciones integradas. La información siguiente proporciona una guía para acceder a datos de aplicación de OneDrive para la Empresa y SharePoint Online, verlos y exportarlos.

##### <a name="sharepoint-user-profiles"></a>Perfiles de usuario de SharePoint

El perfil de usuario de Delve permite a los usuarios mantener propiedades almacenadas en el perfil de usuario de SharePoint Online, como, por ejemplo, la fecha de nacimiento, el número de teléfono móvil (y otra información de contacto), la información biográfica, los proyectos, las aptitudes y los conocimientos, la educación y los centros educativos, los intereses y las aficiones.

###### <a name="end-users"></a>Usuarios finales

Los usuarios finales pueden descubrir, tener acceso y corregir datos de perfil de usuario de SharePoint Online con la experiencia de perfil de Delve. Vea [Ver y actualizar el perfil en Office Delve](https://support.office.com/article/view-and-update-your-profile-in-office-delve-4e84343b-eedf-45a1-aeb9-8627ccca14ba) para obtener más información.

Otra forma de que los usuarios tengan acceso a sus datos de perfil de SharePoint consiste en navegar a la **página de edición de perfil** de su cuenta OneDrive para la Empresa, a la que se puede acceder dirigiéndose a la ruta de acceso **EditProfile.aspx** en la dirección URL de la cuenta de OneDrive para la Empresa. Por ejemplo, la cuenta de OneDrive para la Empresa de un usuario <strong>user1@contoso.com</strong> se encuentra en:
>`https://contoso-my.sharepoint.com/personal/user1\_contoso\_com/\_layouts/15/OneDrive.aspx`

La dirección URL de la página de edición de perfil sería:
>`https://contoso-my.sharepoint.com/personal/user1\_contoso\_com/\_layouts/15/EditProfile.aspx`

Tenga en cuenta que no podrá cambiar en SharePoint Online las propiedades originadas en Azure Active Directory. Sin embargo, los usuarios pueden ir a su página **Cuenta** si seleccionan su **foto** en la cabecera de Office 365 y, a continuación, hacen clic en **Mi cuenta**. Es posible que cambiar las propiedades aquí requiera que los usuarios trabajen con sus administradores para descubrir, acceder o rectificar una propiedad de perfil de usuario.

**Administradores**

Un administrador puede acceder a propiedades de perfil y rectificarlas en el Centro de administración de SharePoint. En el **Centro de administración de SharePoint**, haga clic en la pestaña **perfiles de usuario**. Haga clic en **Administrar perfiles de usuario**, escriba un nombre de usuario y haga clic en **Buscar**. El administrador puede hacer clic con el botón derecho en cualquier usuario y seleccionar **Editar mi perfil**. Tenga en cuenta que las propiedades originadas en Azure Active Directory no se pueden cambiar desde SharePoint Online.

Un administrador puede exportar todas las propiedades de perfil de usuario de un usuario mediante el cmdlet **Export-SPOUserProfile** de SharePoint Online PowerShell. Vea [Export-SPOUserProfile](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spouserprofile?view=sharepoint-ps).

Para más información sobre los perfiles de usuario, vea [Administrar perfiles de usuario en el Centro de administración de SharePoint](https://support.office.com/article/Manage-user-profiles-in-the-SharePoint-admin-center-494bec9c-6654-41f0-920f-f7f937ea9723).

##### <a name="user-information-list-on-sharepoint-online-sites"></a>Lista de información del usuario en sitios de SharePoint Online

Un subconjunto del perfil de usuario de SharePoint de un usuario se sincroniza con la lista de información del usuario de todos los sitios que visite o en los que tenga permisos de acceso. Se utilizan las experiencias de SharePoint Online, como las columnas Contactos en las bibliotecas de documentos, para mostrar información básica sobre el usuario, como el nombre del creador de un documento. Los datos de una lista de información del usuario coincidirán con la información almacenada en el perfil de usuario de SharePoint y se rectifican automáticamente si se cambia el origen. Para los usuarios eliminados, estos datos permanecen en los sitios con los que interactuaban para integridad referencial de los campos de columna de SharePoint. 

Los administradores pueden controlar qué propiedades son replicables en el Centro de administración de SharePoint. Para ello:

1. Vaya al **Centro de administración de SharePoint** y haga clic en la pestaña **Perfiles de usuario**. 

2. Haga clic en **Administrar propiedades de usuario** para ver una lista de propiedades. 

3. Haga clic con el botón derecho en una propiedad y seleccione **Editar** para ajustar diversos valores. 

4. En **Configuración de directiva**, la propiedad replicable controla si la propiedad se representará en la lista de información del usuario. Tenga en cuenta que no todas las propiedades permiten este ajuste.

Un administrador puede exportar todas las propiedades de información del usuario en un sitio determinado mediante el cmdlet **Export-SPOUserInfo** de SharePoint Online PowerShell. Vea [Export-SPOUserInfo](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spouserinfo?view=sharepoint-ps).

##### <a name="onedrive-for-business-experience-settings"></a>Configuración de la experiencia de OneDrive para la Empresa

En una experiencia de OneDrive para la Empresa del usuario, se almacena información para ayudar al usuario a encontrar y navegar por contenido que le interese. Los usuarios finales tienen acceso a la mayor parte de esta información con características integradas. Un administrador puede exportar la información con un [script de PowerShell](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6) o mediante comandos del [modelo de objetos del lado cliente (CSOM) de SharePoint](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-client-library-code).

Vea [Exportar la configuración de la experiencia de OneDrive para la Empresa](https://docs.microsoft.com/sharepoint/export-odfb-lists) para más información sobre la configuración, cómo se almacena y cómo se exporta.

##### <a name="onedrive-for-business-and-sharepoint-online-search"></a>Búsqueda de OneDrive para la Empresa y SharePoint Online

La experiencia de búsqueda integrada en la aplicación de OneDrive para la Empresa y SharePoint Online almacena las consultas de búsqueda de un usuario durante 30 días para aumentar la relevancia de los resultados de la búsqueda. Un administrador puede exportar las consultas de búsqueda de un usuario mediante el cmdlet **Export-SPOQueryLogs** de SharePoint Online PowerShell. Vea [Export-SPOQueryLogs](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spoquerylogs?view=sharepoint-ps).

#### <a name="microsoft-teams-for-education"></a>Microsoft Teams para educación

Microsoft Teams para Educación ofrece dos características de colaboración adicionales que pueden usar profesores y alumnos, y que crean y almacenan datos personales: Tareas y Blocs de notas de clase de OneNote. Puede usar la búsqueda de contenido para obtener información sobre los datos en ambas.

##### <a name="assignments"></a>Tareas

Los archivos de alumnos asociados con una tarea se almacenan en una biblioteca de documentos en el sitio correspondiente de Teams de SharePoint Online. Los administradores de TI pueden usar la herramienta de búsqueda de contenido para buscar archivos de alumno relacionados con las tareas. Por ejemplo, un administrador podría buscar todos los sitios de SharePoint Online de la organización y usar el nombre del alumno o de su clase en la consulta de búsqueda para encontrar datos relevantes a una solicitud de interesado.

Hay otros datos relacionados con tareas que no se almacenan en el sitio de SharePoint Online de la clase, lo que significa que no pueden detectarse con la búsqueda de contenido. Estos incluyen:

-   Archivos que el profesor asigna a los estudiantes como parte de la tarea.

-   Las calificaciones de los alumnos y los comentarios del profesor.

-   La lista de documentos enviados para una tarea por cada alumno.

-   Metadatos de tarea

Para este tipo de datos, un administrador de TI o propietario de los datos (como un profesor) puede que tenga que ir a la tarea en el equipo de clase para encontrar los datos relevantes a una solicitud de interesado.

##### <a name="onenote-class-notebook"></a>Bloc de notas de clase de OneNote

El Bloc de notas de clase de OneNote se almacena en el sitio de SharePoint Online del equipo de clase. Todos los alumnos de una clase tienen un bloc de notas privado que comparten con el profesor. También hay una biblioteca de contenido en la que un profesor puede compartir documentos con los alumnos y un espacio de colaboración para todos los alumnos de la clase. Los datos relacionados con estas funciones pueden detectarse en una búsqueda de contenido.

Aquí tiene las instrucciones específicas para buscar un bloc de notas de clase.

1. Ejecute una búsqueda de contenido con los criterios de búsqueda siguientes:

   - Buscar todos los sitios de SharePoint Online

   - Incluya el nombre del equipo de clase como palabra clave de búsqueda; por ejemplo, "Biología 9C".

2. Obtenga una vista previa de los resultados y busque el elemento correspondiente al Bloc de notas de clase.

3. Seleccione ese elemento y, a continuación, copie la ruta que se muestra en el panel de detalles. Esta es la carpeta raíz del Bloc de notas de clase.

4. Edite la búsqueda que creó en el paso 1, cambie el nombre de la clase en la consulta de palabras clave con la ruta de la carpeta del Bloc de notas de clase y ponga delante de la ruta de la carpeta la propiedad del sitio **ruta**; por ejemplo, **ruta:"<https://contosoedu.onmicrosoft.com/sites/9C> Biología/SiteAssets/bloc de notas de Biología 9C/"**. Asegúrese de incluir las comillas y la barra invertida final.

5. Agregue una condición de búsqueda, seleccione la condición Tipo de archivo y use "one" para como el valor del tipo de archivo. Esto devolverá todos los archivos de OneNote en los resultados de búsqueda. La sintaxis de la palabra clave resultante debería tener un aspecto similar al siguiente:[](#building-search-queries-to-find-personal-data)

    ```
   path:"<https://contosoedu.onmicrosoft.com/sites/9C> Biology/SiteAssets/9C Biology Notebook/" AND filetype="one"
   ```

6.  Vuelva a ejecutar la búsqueda de contenido. Los resultados de búsqueda deben incluir todos los archivos de OneNote del Bloc de notas de clase del equipo de clase.

#### <a name="microsoft-to-do"></a>Microsoft To-Do

Las tareas (llamadas *tareas* pendientes, que se guardan en *listas de tareas pendientes*) en Microsoft To-Do se guardan como tareas en un buzón de Exchange Online del usuario. Eso significa que se puede usar la herramienta Búsqueda de contenido para buscar, tener acceso, eliminar y exportar tareas. Para obtener más información, vea [Configurar Microsoft To-Do](https://support.office.com/article/Set-up-Microsoft-To-Do-490c1a8c-2333-4952-8125-841afadb9620).

#### <a name="skype-for-business"></a>Skype Empresarial

A continuación se muestra información adicional acerca de cómo acceder a datos personales, verlos y exportarlos en Skype Empresarial.

-   Los archivos adjuntados a una reunión se conservan en ella durante 180 días y después dejan de ser accesibles. Los participantes a la reunión pueden acceder a ellos tras unirse a la misma desde la convocatoria de reunión y, a continuación, revisarlos o descargarlos. Consulte la sección "Usar los datos adjuntos de la reunión" en [Precargar datos adjuntos para una reunión de Skype Empresarial](https://support.office.com/article/preload-attachments-for-a-skype-for-business-meeting-fd3d9f9d-b448-4754-b813-02e49393f251).

-   Las conversaciones de Skype Empresarial se conservan en la carpeta Historial de conversaciones en buzones de usuario. Puede usar la búsqueda de contenido para buscar datos en buzones en las conversaciones de Skype.

-   Un interesado puede exportar sus contactos de Skype Empresarial. Para ello, debe hacer clic en un grupo de contactos de Skype Empresarial y después hacer clic en **Copiar**. A continuación, puede pegar la lista de direcciones de correo electrónico en un texto o un documento de Word.

-   Si el buzón de Exchange Online de un participante de la reunión se coloca en retención por juicio o se asigna a una directiva de retención de Office 365, se conservan los archivos adjuntados a una reunión en el buzón de participantes. Puede usar la búsqueda de contenido para buscar los archivos en el buzón de participantes si no ha expirado el período de retención del archivo. Para obtener más información acerca de la retención de archivos, vea [Conservar archivos grandes adjuntados a una reunión de Skype Empresarial](https://docs.microsoft.com/skypeforbusiness/set-up-policies-in-your-organization/retaining-large-files-attached-to-a-meeting).

## <a name="providing-a-copy-of-personal-data"></a>Proporcionar una copia de los datos personales

Cuando haya encontrado datos personales que puedan responder a una solicitud de interesado, depende de usted y de su organización decidir qué datos proporcionar al interesado. Por ejemplo, puede proporcionarle una copia del documento, una versión redactada o una captura de pantalla con las porciones que considere adecuado compartir. Para cada una de estas respuestas a una petición de acceso, deberá recuperar una copia del documento u otro objeto que contenga los datos de respuesta.

Al proporcionar una copia al interesado, deberá quitar o censurar información personal sobre otros interesados, además de la información confidencial.


### <a name="using-content-search-to-get-a-copy-of-personal-data"></a>Usar la Búsqueda de contenido para obtener una copia de datos personales

Hay dos formas de usar la herramienta de búsqueda de contenido para obtener una copia de un documento o elemento de buzón que haya encontrado después de ejecutar una búsqueda.

-   Consulte una vista previa de los resultados de búsqueda y descargue una copia del documento o elemento. Se trata de un buen método para descargar algunos elementos o archivos.

-   Exporte los resultados de búsqueda y descargue una copia de todos sus elementos. Este método es más complejo, pero es recomendable para descargar una gran cantidad de elementos relacionados con una solicitud de interesado. También se incluyen informes útiles con la exportación de los resultados de búsqueda. Puede usar estos informes para obtener más información sobre cada elemento. El informe **Results.csv** es muy útil, ya que contiene una gran cantidad de información sobre los elementos exportados, como la ubicación exacta del elemento (por ejemplo, el buzón de mensajes de correo electrónico o la dirección URL de listas o documentos ubicados en sitios de SharePoint Online y OneDrive para la Empresa). Esta información le ayudará a identificar al propietario del elemento, por si necesita ponerse en contacto con él durante el proceso de investigación de la solicitud de interesado. Para obtener más información sobre los informes que se incluyen al exportar resultados de búsqueda, vea [Exportar un informe de búsqueda de contenido](https://support.office.com/article/Export-a-Content-Search-report-5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9).

#### <a name="preview-and-download-items"></a>Vista previa y descarga de elementos

Después de ejecutar una nueva búsqueda o abrir una existente, puede realizar una vista previa de cada elemento que coincida con la consulta de búsqueda para verificar que está relacionado con la solicitud de interesado que está investigando. Esto incluye listas y sitios web de SharePoint que aparecen en los resultados de búsqueda. También puede descargar el archivo original si necesita proporcionárselo al interesado. En ambos casos, puede realizar una captura de pantalla para satisfacer la petición de información del interesado.

Tenga en cuenta que no es posible obtener una vista previa de algunos tipos de elementos. Si la vista previa no es compatible con un tipo de archivo o elemento, tiene la opción de descargar dicho elemento de forma individual en un equipo local o una unidad de red u otra ubicación de red. Solo puede ver [tipos de archivo compatibles](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4).

Para obtener una vista previa y descargar elementos:

1.  Abra la búsqueda de contenido en el Centro de seguridad y cumplimiento.

2.  Si no se muestran los resultados, haga clic en **Vista previa de los resultados**.

3.  Haga clic en un elemento para verlo.

4.  Haga clic en **Descargar archivo original** para descargar el elemento en su equipo local. También podrá descargar aquellos elementos que no sean compatibles con una vista previa.

Para obtener más información sobre cómo obtener una vista previa de resultados de búsqueda, vea [Vista previa de los resultados de búsqueda](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4).

#### <a name="export-and-download-items"></a>Exportar y descargar elementos

También puede exportar los resultados de una búsqueda de contenido para obtener una copia de mensajes de correo electrónico, documentos, listas y páginas web que contengan datos personales, aunque este método es más complicado que obtener una vista previa de elementos. Vea la sección siguiente para obtener más información sobre [cómo exportar los resultados de una búsqueda de contenido](#export-and-download-content-using-content-search).

## <a name="exporting-personal-data"></a>Exportar datos personales

El "derecho de portabilidad de datos" permite a los interesados solicitar una copia electrónica de sus datos personales en un "formato estructurado, común y legible", y solicitar que su organización transmita estos archivos electrónicos a otro responsable de datos. Microsoft apoya este derecho de dos maneras:
- Ofreciendo aplicaciones de Office 365 que guardan datos en formatos electrónicos nativos, legibles y de uso común. Para obtener más información acerca de los formatos de archivo de Office, vea [Documentos técnicos de formatos de archivo de Office](https://msdn.microsoft.com/library/office/cc313105(v=office.12).aspx).
- Permitiendo a su organización exportar datos en el formato de archivo nativo o en un formato (como CSV, TXT y JSON) que puede importarse con facilidad a otra aplicación.

Para cumplir una solicitud de interesado de exportación, puede exportar documentos de Office en su formato de archivo nativo y exportar datos de otras aplicaciones de Office 365.

### <a name="export-and-download-content-using-content-search"></a>Exportar y descargar contenido mediante la búsqueda de contenido

Al exportar los resultados de una búsqueda de contenido, es posible descargar los elementos de correo electrónico como archivos PST o mensajes individuales (archivos .msg). Al exportar documentos y listas de SharePoint Online y OneDrive para la Empresa, se exportan copias en los formatos de archivo nativo. Por ejemplo, las listas de SharePoint se exportan como archivos CSV y las páginas web se exportan como archivos .aspx o html.

> [!NOTE]
> Exportar elementos de buzón de un buzón de usuario mediante la búsqueda de contenido requiere que el usuario (de cuyo buzón va a exportar elementos) tenga asignada una licencia de Exchange Online Plan 2. 

Para exportar y descargar elementos:

1.  Abra la búsqueda de contenido en el Centro de seguridad y cumplimiento.

2.  En la página de búsqueda, haga clic en ![](media/o365-dsr_image21.png) **Más** y, a continuación, haga clic en **Exportar resultados**. Tenga en cuenta que también puede exportar un informe.

3.  Rellene las secciones en la página **Exportar resultados**. Asegúrese de usar la barra de desplazamiento para ver todas las opciones de exportación.

4.  Vuelva a la página de búsqueda de contenido en el centro de cumplimiento y seguridad y haga clic en la pestaña **Exportar**.

5.  Haga clic en **Actualizar** para actualizar la página.

6.  En la columna **Nombre**, haga clic en el trabajo de exportación que acaba de crear. El nombre de la tarea de exportación es el nombre de la búsqueda de contenido anexado con **\_Exportar**.

7.  En la página de exportación, en **Clave de exportación**, haga clic en **Copiar al Portapapeles**. Esta clave se usará para descargar los resultados de la búsqueda en el paso 10.

8.  En la parte superior de la página, haga clic en ![](media/o365-dsr_image21.png) **Descargar resultados**.

9.  Si se le pide que instale la **Herramienta de exportación de eDiscovery de Microsoft Office 365**, haga clic en **Instalar**.

10. En la **Herramienta de exportación de eDiscovery **, pegue la clave de exportación que ha copiado en el paso 7 en el cuadro correspondiente.

11. Haga clic en **Examinar** para especificar la ubicación en la que desea descargar los archivos de los resultados de la búsqueda.

12. Haga clic en **Iniciar** para descargar los resultados de la búsqueda en el equipo.

Cuando se complete el proceso de exportación, tendrá acceso a los archivos en la ubicación del equipo local donde se descargaron. Los resultados de una búsqueda de contenido se descargan en una carpeta con el nombre de la búsqueda de contenido. Los documentos de los sitios se copian en una subcarpeta denominada **SharePoint**. Los elementos del buzón se copian en una subcarpeta denominada **Exchange**.

Consulte [Exportar resultados de búsqueda desde el Centro de seguridad y cumplimiento de Office 365](https://support.office.com/article/Export-Content-Search-results-from-the-Office-365-Security-Compliance-Center-ed48d448-3714-4c42-85f5-10f75f6a4278) para obtener instrucciones detalladas paso a paso.


### <a name="downloading-documents-and-lists-from-sharepoint-online-and-onedrive-for-business"></a>Descargar documentos y listas de SharePoint Online y OneDrive para la Empresa

Otra forma de exportar los datos de SharePoint Online y OneDrive para la Empresa consiste en descargar documentos y listas directamente desde un sitio de SharePoint Online o una cuenta de OneDrive para la Empresa. Tendrá que asignar los permisos para acceder a un sitio, ir al sitio y descargar el contenido. Vea:

-   [Descargar archivos y carpetas de OneDrive o SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)

-   [Exportar listas de SharePoint a Excel](https://support.office.com/article/export-to-excel-from-sharepoint-bfb2ea48-6118-4fa9-abb6-cced9424e5d9)

Para algunas solicitudes de interesado de exportación, le recomendamos permitir que los interesados puedan descargar contenido por su cuenta. Esto permite a los interesados ir a un sitio o carpeta compartida de SharePoint Online y hacer clic en **Sincronizar** para sincronizar todo el contenido o las carpetas seleccionadas de la biblioteca de documentos. Vea:

-   [Permitir a los usuarios sincronizar archivos de SharePoint con el nuevo cliente de sincronización de OneDrive](https://support.office.com/article/Enable-users-to-sync-SharePoint-files-with-the-new-OneDrive-sync-client-22e1f635-fb89-49e0-a176-edab26f69614)

-   [Sincronizar archivos de SharePoint con el nuevo cliente de sincronización de OneDrive](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-client-6de9ede8-5b6e-4503-80b2-6190f3354a88)

## <a name="deleting-personal-data"></a>Eliminar datos personales

El “derecho a la eliminación” de datos personales de cliente de una organización es una protección clave en el RGPD. Los datos personales que se eliminan son, entre otros, documentos o archivos, o bien datos específicos un documento o archivo (lo que sería una acción y proceso como aquellos descritos en la sección Rectificar de esta guía).

Cuando investiga o se prepara para eliminar datos personales en respuesta a una solicitud de derechos del interesado, es importante tener en cuenta varios factores para comprender cómo funciona la eliminación (y retención) de datos en Office 365.

-   **Eliminación temporal y eliminación definitiva**: en servicios de Office 365 como Exchange Online, SharePoint Online y OneDrive para la Empresa existe el concepto de *eliminación temporal* y *eliminación definitiva*, relacionado con la recuperación de un elemento eliminado (normalmente durante un tiempo limitado) antes de que se elimine permanentemente de la nube de Microsoft sin posibilidad de recuperación. En este contexto, se puede recuperar un elemento tras su eliminación temporal por parte de un usuario o administrador durante un período de tiempo antes de ser eliminado permanentemente. Cuando un elemento ha sido eliminado permanentemente, se marca para su eliminación permanente y se purga tan pronto como es procesado por el servicio de Office 365 correspondiente. Aquí se indica cómo se desarrolla la eliminación temporal y la eliminación definitiva para elementos en buzones de correo y sitios (independientemente de si el elemento es eliminado por el propietario de los datos o por un administrador):

    -   **Buzones de correo:** la eliminación temporal de un elemento se realiza cuando se elimina de la carpeta Elementos Eliminados o cuando un usuario elimina un elemento presionando **Mayús + Supr**. Tras la eliminación temporal de un elemento, este se mueve a la carpeta Elementos Recuperables del buzón de correo. En este momento, el elemento puede ser recuperado por el usuario antes de que expire el período de retención de elementos eliminados (en Office 365, el período de retención de elementos eliminados es de 14 días, pero un administrador puede extenderlo hasta 30 días). Cuando expira el período de retención, el elemento es eliminado permanentemente y se mueve a una carpeta oculta (denominada carpeta *Purgas*). El elemento se eliminará permanentemente (purgado) de Office 365 la próxima vez que se procese el buzón de correo (los buzones se procesan una vez cada 7 días).

    -   **Sitios de SharePoint Online y OneDrive para la Empresa**: cuando un archivo o documento se elimina, este se mueve a la Papelera de reciclaje del sitio (también denominada *Papelera de reciclaje de primer nivel*, que es similar a la Papelera de reciclaje de Windows). El elemento permanecerá en la Papelera de reciclaje durante 93 días (el período de retención de elementos eliminados para sitios en Office 365). Transcurrido ese período, el elemento se mueve automáticamente a la Papelera de reciclaje de la colección de sitios, que también se denomina la *Papelera de reciclaje de segundo nivel*. (Tenga en cuenta que los usuarios o administradores, con los permisos adecuados, pueden eliminar elementos de la Papelera de reciclaje de primer nivel). En este momento, el elemento se encuentra en eliminación blanda; aún puede ser recuperado por el usuario o administrador de SharePoint Online o por un administrador de colección de sitios de OneDrive para la Empresa). Cuando se elimina un elemento de la Papelera de reciclaje de segundo nivel (manual o automáticamente) queda eliminado permanentemente y no es accesible para el usuario o administrador. Tenga en cuenta que existe un período de retención de 93 días para las papeleras de reciclaje del primer nivel y del segundo nivel. Esto significa que la retención de la Papelera de reciclaje de segundo nivel se inicia cuando el elemento se elimina en primer lugar; por lo tanto, el tiempo de retención máximo total es de 93 días para ambas papeleras de reciclaje.

> [!NOTE]
> Comprender las acciones que dan lugar a la eliminación temporal o definitiva de este debate le ayudará a determinar cómo eliminar datos de forma que reúna los requisitos RGPD y responda a los requisitos de RGPD al responder a una solicitud de eliminación.

-   **Directivas de retención y suspensiones legales**: en Office 365, es posible colocar una "suspensión" en buzones y sitios; en resumen, esto supone que no se elimina nada de forma permanente si un buzón o sitio se encuentra retenido, hasta que expire el periodo de retención de un elemento o se levante la retención. Esto es importante a la hora de eliminar contenido de clientes como respuesta a una solicitud de interesado: si se elimina un elemento de forma permanente de una ubicación de contenido que está retenida, el objeto no se elimina permanentemente de Office 365. Esto significa que un administrador de TI podría recuperarlo. Si su organización tiene un requerimiento o directiva que obligue a eliminar permanentemente los datos y no permita recuperarlos en Office 365 como respuesta a una solicitud de interesado, entonces debería eliminar la retención de un buzón de correo o sitio para poder eliminar datos de forma permanente en Office 365. Es probable que las guías de su organización para responder a solicitudes de interesado de eliminación o a una suspensión legal sirvan de precedente. Si se elimina una retención para eliminar elementos, puede volver a implementarse más adelante.

### <a name="deleting-documents-in-sharepoint-online-and-onedrive-for-business"></a>Eliminar documentos en SharePoint Online y OneDrive para la Empresa

Cuando haya encontrado el documento ubicado en un sitio de SharePoint Online o en una cuenta de OneDrive para la Empresa (al seguir la guía en la sección Detectar) que debe eliminarse, un agente de privacidad de datos o un administrador de TI necesitaría tener asignados los diferentes permisos para acceder al sitio y eliminar el documento. En caso adecuado, se puede indicar al propietario del documento que debe eliminarlo.

Este es el proceso de alto nivel para eliminar documentos de sitios.

1.  Vaya al sitio y busque el documento.

2.  Elimine el documento. Al eliminar un documento de un sitio, se envía a la Papelera de reciclaje de primer nivel.

3.  Vaya a la Papelera de reciclaje de primer nivel (la Papelera de reciclaje del sitio) y elimine el mismo documento que eliminó en el paso anterior. El documento se envía a la Papelera de reciclaje de segundo nivel. **En este momento, el documento está eliminado de forma temporal**.

4.  Vaya a la Papelera de reciclaje de segundo nivel (la Papelera de reciclaje de la colección de sitios) y elimine el mismo documento que eliminó de la Papelera de reciclaje de primer nivel. **En este momento, el documento se ha eliminado de forma permanente**.

> [!IMPORTANT]
> No puede eliminar un documento que se encuentra en un sitio que está en suspensión (con una de las funciones de suspensión legal de Office 365). En caso de que una solicitud de eliminación de DSR tenga prioridad sobre una suspensión legal, tendrá que quitarse la retención del sitio para que un documento pueda eliminarse definitivamente.

Vea los temas siguientes para obtener procedimientos detallados.

- [Eliminar un archivo, carpeta o vínculo de una biblioteca de documentos de SharePoint](https://support.office.com/article/Delete-a-file-folder-or-link-from-a-SharePoint-document-library-71f3c90a-0d24-4d80-8b66-f88234b79a52#ID0EAADAAA=Online)

- [Eliminar elementos o vaciar la papelera de reciclaje de un sitio de SharePoint](https://support.office.com/article/delete-items-or-empty-the-recycle-bin-of-a-sharepoint-site-2e713599-d13e-40d6-96dc-66f0a366f74e#ID0EAADAAA=Online)

- [Eliminar elementos de la papelera de reciclaje de la colección de sitios](https://support.office.com/article/Delete-items-from-the-site-collection-Recycle-Bin-dd5c00c2-aef6-4458-9d04-80b185077653#ID0EAADAAA=Online)

- La sección "Obtener acceso a los documentos de OneDrive para la Empresa" en [Obtener acceso y realizar una copia de seguridad de los datos del usuario anterior](https://support.office.com/article/get-access-to-and-back-up-a-former-user-s-data-a6f7f9ad-e3f5-43de-ade5-e5a0d7531604).

- [Eliminar archivos o carpetas en OneDrive para la Empresa](https://support.office.com/article/Delete-files-or-folders-in-OneDrive-21fe345a-e488-4fa7-932b-f053c1bebe8a)

- [Eliminar una lista de SharePoint](https://support.office.com/article/delete-a-list-in-sharepoint-2a7bca5b-b8fd-4e5b-8f4b-2ac034f3070d#ID0EAADAAA=Online)

- [Eliminar elementos de lista en SharePoint Online](https://support.office.com/article/delete-list-items-in-sharepoint-online-db722233-4a38-4889-a6cf-4b33fe5c60c0)

### <a name="deleting-a-sharepoint-site"></a>Eliminar un sitio de SharePoint

Puede determinar que la mejor forma de responder a una solicitud de interesado de eliminación consiste en eliminar todo un sitio de SharePoint, lo que da pie a la eliminación de los datos personales del sitio. Puede hacerlo ejecutando cmdlets en SharePoint Online PowerShell.

-   Use el cmdlet [Remove-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-sposite?view=sharepoint-ps) para eliminar el sitio y enviarlo a la Papelera de reciclaje de SharePoint Online (eliminación temporal).

-   Use los cmdlet [Remove-SPODeletedsite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spodeletedsite?view=sharepoint-ps) para eliminar de forma permanente el sitio.

Tenga en cuenta que no puede eliminar un sitio que se encuentra retenido por eDiscovery o tiene asignada una empresa de retención. Los sitios deben eliminarse de una retención de eDiscovery o directiva de retención antes de eliminarlas.

### <a name="deleting-a-onedrive-for-business-site"></a>Eliminar un sitio de OneDrive para la Empresa.

De forma similar, puede determinar eliminar el sitio de OneDrive para la Empresa de un usuario en respuesta a una solicitud de interesado de eliminación. Si elimina la cuenta de usuario Office 365, su sitio de OneDrive para la Empresa se retiene (y se puede restaurar) durante 30 días. Después ese periodo, pasa a la Papelera de reciclaje (eliminación temporal) de SharePoint Online y, a continuación, tras 93 días, se elimina permanentemente. Para acelerar este proceso, puede usar el cmdlet [Remove-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-sposite?view=sharepoint-ps) para mover el sitio de OneDrive para empresa a la Papelera de reciclaje y, después, usar el cmdlet [Remove-SPODeletedSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spodeletedsite?view=sharepoint-ps) para eliminarlo de forma permanente. Al igual que con los sitios de SharePoint Online, no puede eliminar sitio de OneDrive para la Empresa de un usuario si se ha asignado una retención de eDiscovery o una directiva de retención, antes de eliminar la cuenta del usuario.

### <a name="deleting-onedrive-for-business-and-sharepoint-online-experience-settings"></a>Eliminar la configuración de la experiencia de OneDrive para la Empresa y SharePoint

Además de los archivos creados por usuarios almacenados en las cuentas de OneDrive para la Empresa y los sitios de SharePoint Online, estos servicios almacenan información acerca del usuario que se utiliza para habilitar varias experiencias. Se han documentado anteriormente en este documento. Consulte las [Consideraciones adicionales para aplicaciones seleccionadas](#additional-considerations-for-selected-applications) en la sección [Usar la herramienta de búsqueda de contenido eDiscovery para responder a solicitudes de interesado](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs) para obtener información sobre cómo acceder, ver y exportar datos de aplicación de OneDrive para la Empresa y SharePoint Online.

#### <a name="deleting-a-sharepoint-user-profile"></a>Eliminar un perfil de usuario de SharePoint

El perfil de usuario de SharePoint se eliminará definitivamente 30 días después de eliminar la cuenta de usuario en Azure Active Directory. Pero puede eliminar de forma permanente la cuenta de usuario, lo que eliminará el perfil de usuario de SharePoint. Para más información, vea la sección [Eliminar un usuario](#deleting-a-user) de esta guía.

Un administrador puede acelerar la eliminación del perfil de usuario de un usuario mediante el cmdlet **Remove-SPOUserProfile** de SharePoint Online PowerShell. Cea [Remove-SPOUserProfile](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spouserprofile?view=sharepoint-ps). Esto requiere que el usuario se elimine temporalmente al menos en Azure Active Directory.

#### <a name="deleting-user-information-lists-on-sharepoint-online-sites"></a>Eliminar listas de información del usuario en sitios de SharePoint Online

Para los usuarios que han abandonado la organización, estos datos permanecen en los sitios con los que interactuaban para integridad referencial de los campos de columna de SharePoint. Un administrador puede eliminar todas las propiedades de información del usuario de un usuario en un sitio determinado mediante el comando **Remove-SPOUserInfo** de SharePoint Online PowerShell. Vea [Remove-SPOUserInfo](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spouserinfo?view=sharepoint-ps) para obtener información sobre cómo ejecutar este cmdlet de PowerShell.

De forma predeterminada, este comando conservará el nombre para mostrar del usuario y eliminará propiedades tales como el número de teléfono, la dirección de correo electrónico, las aptitudes y los conocimientos u otras propiedades que se copiaron del perfil de usuario de SharePoint Online. Un administrador puede usar el parámetro **RedactUser** para especificar un nombre para mostrar alternativo del usuario en la lista de información del usuario. Esto afectará a varias partes de la experiencia del usuario y se traducirá en pérdida de información al consultar el historial de archivos del sitio.

Por último, la funcionalidad de censura no quitará todos los metadatos ni el contenido que hagan referencia a un usuario en los documentos. La forma de conseguir la censura de los metadatos y el contenido de archivos se describe en la sección [Realizar cambios al contenido en OneDrive para la Empresa y SharePoint Online](#making-changes-to-content-in-onedrive-for-business-and-sharepoint-online) de esta guía. Este método consiste en descargar, eliminar y volver a cargar una copia censurada del archivo.

#### <a name="deleting-onedrive-for-business-experience-settings"></a>Eliminar la configuración de la experiencia de OneDrive para la Empresa

La forma aconsejable de eliminar toda la información y configuración de la experiencia de OneDrive para la Empresa consiste en quitar el sitio de OneDrive para la Empresa del usuario, después de reasignar todos los archivos retenidos a otros usuarios. Un administrador puede eliminar estas listas mediante comandos de [Script de PowerShell](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6) y del [modelo de objetos del lado cliente de SharePoint (CSOM)](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-client-library-code). Vea [Eliminar la configuración de la experiencia de OneDrive para la Empresa](https://docs.microsoft.com/sharepoint/delete-odfb-lists) para obtener más información sobre la configuración, cómo se almacena y cómo se exporta.

#### <a name="onedrive-for-business-and-sharepoint-online-search-queries"></a>Consultas de búsqueda de OneDrive para la Empresa y SharePoint Online

Las consultas de búsqueda de un usuario creadas en la experiencia de búsqueda de OneDrive para la Empresa y SharePoint Online se eliminan automáticamente 30 días después de que el usuario haya creado la consulta.

### <a name="deleting-items-in-exchange-online-mailboxes"></a>Eliminar elementos en buzones de Exchange Online

Puede que tenga que eliminar elementos en los buzones de Exchange Online para satisfacer una solicitud de interesado de eliminación. Un administrador de TI puede eliminar elementos de un buzón de dos formas, dependiendo de si desea eliminarlos de forma temporal o permanente. Como los documentos en SharePoint Online los sitios en OneDrive para la Empresa, los elementos de un buzón que se encuentran retenidos no pueden eliminarse de forma permanente de Office 365. Es preciso retirar la retención antes de poder eliminarse. De nuevo, tendrá que determinar si la retención del buzón o la solicitud de interesado de eliminación tienen precedencia.

#### <a name="soft-delete-mailbox-items"></a>Eliminar temporalmente elementos del buzón

Puede usar la función de la acción de buscar contenido para eliminar temporalmente elementos devueltos por una búsqueda de contenido. Como se explicó anteriormente, los elementos eliminados temporalmente se envían a la carpeta de Elementos recuperables del buzón de correo.

Aquí presentamos una introducción rápida sobre este proceso:

1.  Cree y ejecute una búsqueda de contenido para encontrar los elementos que quiera eliminar del buzón del usuario. Puede que tenga que volver a ejecutar la búsqueda para restringir los resultados de modo que los elementos que quiere eliminar aparezcan en los resultados de búsqueda.

2.  Use el comando **New-ComplianceSearchAction** **-Purge** de PowerShell de Office 365 para eliminar el elemento de forma temporal que devuelve la búsqueda de contenido creada en el paso anterior.

Para obtener instrucciones detalladas, vea [Buscar y eliminar mensajes de correo electrónico en la organización de Office 365](https://support.office.com/article/Search-for-and-delete-email-messages-in-your-Office-365-organization-Admin-Help-3526fd06-b45f-445b-aed4-5ebd37b3762a).

#### <a name="hard-delete-mailbox-items"></a>Eliminar permanentemente elementos del buzón

Si tiene que eliminar de forma permanente elementos del buzón como respuesta a una solicitud de interesado de eliminación, puede usar el comando **Search-Mailbox-DeleteContent** en PowerShell de Exchange Online. Si usa este método, considere usar la búsqueda de contenido para desarrollar y refinar una consulta de búsqueda, de modo que aparezcan solo los elementos que se van a eliminar. A continuación puede usar la sintaxis de consulta al ejecutar el comando **Search-Mailbox-DeleteContent**.

Para obtener instrucciones detalladas, consulte [Buscar y eliminar mensajes](https://technet.microsoft.com/library/ff459253(v=exchg.150).aspx).

#### <a name="hard-delete-items-in-a-mailbox-on-hold"></a>Eliminar permanentemente elementos de un buzón retenidos

Como se ha explicado anteriormente, si elimina de forma permanente elementos de un buzón retenidos, los elementos no se quitan del buzón. Se mueven a una carpeta oculta en la carpeta elementos recuperables (la carpeta **Purgas**) donde permanecen hasta que expire la duración de retención del elemento o se retire la suspensión del buzón. Si no se producen ninguna de estas cosas, los elementos se eliminarán de Office 365 la próxima vez que se procese el buzón.

Su organización puede determinar qué elementos eliminar permanentemente al expirar la duración de retención cumplan los requisitos para una solicitud de interesado de eliminación. Sin embargo, si usted determina que deben eliminarse inmediatamente elementos del buzón de Office 365, tendrá que quitar la suspensión del buzón y luego eliminar permanentemente los elementos del buzón. Para obtener instrucciones detalladas, consulte [Eliminar elementos de la carpeta elementos recuperables de buzones en la nube en espera](https://support.office.com/article/Delete-items-in-the-Recoverable-Items-folder-of-cloud-based-mailboxes-on-hold-Admin-Help-a85e1c87-a48e-4715-bfa9-d5275cde67b0).

> [!NOTE]
> Para eliminar definitivamente elementos del buzón de correo para satisfacer la solicitud de interesado siguiendo el procedimiento del tema anterior, puede que tenga que eliminar temporalmente dichos elementos mientras el buzón de correo sigue retenido para poder moverlos a la carpeta Elementos recuperables.

## <a name="deleting-a-user"></a>Eliminar un usuario

Además de eliminar los datos personales en respuesta a una solicitud de interesado de eliminación, el "derecho al olvido" del interesado también puede cumplirse eliminando su cuenta de usuario de Office 365. A continuación se muestran algunos motivos por los que cambiar de usuario.

-   El interesado ha dejado (o está dejando) su organización.

-   El interesado ha solicitado eliminar registros generados por el sistema que se hayan recopilado sobre él. Ejemplos de datos generados por registros del sistema incluyen el uso de datos de la aplicación y servicio de Office 365. información sobre solicitudes de búsqueda realizadas por el interesado y datos generados por productos y servicios como producto de función e interacción del sistema por parte de usuarios de otros sistemas. Para más información, consulte [Parte 3: Responder a las solicitudes de interesado para registros generados por el sistema](#part-3-responding-to-dsrs-for-system-generated-logs) en esta guía.

-   Evite de forma permanente que el interesado obtenga acceso a los datos o los trate en Office 365 (en lugar de una restricción temporal por el métodos descrito en la sección [Responder a solicitudes de restricción de DSR](#responding-to-dsr-restriction-requests).

Después de eliminar una cuenta de usuario de Office 365:

-   El usuario no podrán iniciar sesión en Office 365 ni obtener acceso a cualquiera de los recursos de Office 365 de su organización, como su cuenta de OneDrive para la Empresa, sitios de SharePoint Online y su buzón de Exchange Online.

-   Se eliminan los datos personales, como la dirección de correo electrónico, el alias, el número de teléfono y la dirección postal asociados con la cuenta del usuario.

-   Algunas aplicaciones de Office 365 quitarán la información sobre el usuario. Por ejemplo, en Microsoft Flow, el usuario eliminado se quitará de la lista de propietarios de un flujo compartido.

-   Los registros generados por el sistema sobre el interesado se eliminarán 30 días después de eliminar la cuenta de usuario. Para más información, vea la sección [Eliminar registros generados por el sistema](#deleting-system-generated-logs).

> [!IMPORTANT] 
> Después de eliminar una cuenta de usuario, ese usuario ya no podrá iniciar sesión en Office 365 ni en los productos o servicios de los que disponía anteriormente en su cuenta profesional o educativa. Ese usuario tampoco podrá iniciar ninguna solicitud DSR directamente a través de Microsoft en instancias en las que Microsoft es el responsable de los datos. Para obtener más información, vea la sección [Productos y servicios autenticados con el identificador de organización por los que Microsoft es responsable de datos](#product-and-services-authenticated-with-an-org-id-for-which-microsoft-is-a-data-controller) de la parte 4 de esta guía.

> [!NOTE]
> Si es un cliente que actualmente realiza migraciones de FastTrack, la eliminación de la cuenta de usuario de Office 365 no eliminará la copia de datos que el equipo de Microsoft FastTrack conserva, cosa que se hace con el único propósito de completar la migración. Si quiere que el equipo de Microsoft FastTrack elimine también esa copia de datos durante la migración, puede [enviar una solicitud](https://go.microsoft.com/fwlink/?linkid=874544). En el transcurso habitual de las actividades, Microsoft FastTrack eliminará todas las copias de datos cuando la migración finalice.

Al igual que la eliminación temporal y la eliminación permanente de datos descritas en la sección anterior sobre el borrado de datos personales, también existe un estado de eliminación temporal y de eliminación permanente cuando se elimina una cuenta de usuario.

-   Al eliminar una cuenta de usuario (eliminando al usuario en el centro de administrador de Office 365 y en Azure Portal), esta queda eliminada temporalmente y pasa a la Papelera de reciclaje en Azure durante un máximo de 30 días. Hasta ese momento, será posible restaurar la cuenta de usuario.

-   Si ha eliminado permanentemente la cuenta de usuario, esta se quita de la Papelera de reciclaje en Azure. En este momento, ya no se podrán restaurar la cuenta de usuario y los datos asociados a ella se quitará permanentemente de la nube de Microsoft. Los registros generados por el sistema sobre el interesado se eliminarán tras eliminar la cuenta de usuario de forma permanente.

Este es el proceso de alto nivel para eliminar usuarios de su organización de Office 365.

1.  Vaya al Centro de administración de Office 365 o a Azure Portal y encuentre al usuario.

2.  Elimine al usuario. Al eliminar al usuario al principio, la cuenta del usuario se envía a la Papelera de reciclaje. En este momento, el usuario se encuentra eliminado temporalmente. La cuenta conservará a los eliminados temporalmente durante 30 días, lo que le permite restaurar la cuenta. Después de 30 días, la cuenta se elimina sola automáticamente. Para obtener instrucciones específicas, vea [Eliminar usuarios de Azure AD](https://docs.microsoft.com/azure/active-directory/add-users-azure-active-directory).<p>Puede también eliminar temporalmente una cuenta de usuario en el Centro de administración de Office 365. Vea [Eliminar un usuario de su organización](https://support.office.com/article/Delete-a-user-from-your-organization-D5155593-3BAC-4D8D-9D8B-F4513A81479E).</p>

3.  Si no quiere esperar 30 días para que la cuenta de usuario se elimine de forma permanente, puede hacerlo de forma manual. Para hacer esto en Azure Portal, vaya a la lista de usuarios eliminados recientemente y elimine definitivamente al usuario. En este momento, el usuario se elimina de forma permanente. Para obtener instrucciones, vea [Cómo eliminar permanentemente un usuario recién eliminado](https://docs.microsoft.com/azure/active-directory/active-directory-users-restore).

No puede eliminar de forma permanente un usuario del Portal de administración de Office 365.

> [!NOTE]
> En Office 365 ofrecido por 21Vianet (China), no puede eliminar permanentemente un usuario tal y como se ha descrito anteriormente. Para eliminar un usuario permanentemente, puede enviar una solicitud a través del Portal de administración de Office 365 en esta dirección [URL](https://portal.partner.microsoftonline.cn/AdminPortal/Home#/homepage). Vaya a **Comercio**, seleccione **Suscripción** -> **Privacidad** ->  **RGPD** y escriba la información necesaria.

### <a name="removing-exchange-online-data"></a>Quitar datos de Exchange Online

Una cosa que debe entender al eliminar un usuario es lo que ocurre en el buzón de usuario Exchange Online. Después de eliminar la cuenta de usuario (en el paso 3 del proceso anterior), el buzón de usuario eliminado no se purga automáticamente de Office 365. Pasarán un máximo de 60 días hasta que la cuenta de usuario se elimine definitivamente de Office 365. Este es el ciclo de vida del buzón después de eliminar la cuenta de usuario y una descripción del estado de los datos del buzón durante ese tiempo:

-   **Día 1 a día 30**: el buzón puede recuperarse completamente si se restaura la cuenta de usuario eliminada.

-   **Día 31 a día 60**: 30 días después de que se haya eliminado permanentemente la cuenta de usuario, un administrador de su organización puede recuperar datos en el buzón de correo e importarlos a otros. Esto proporciona a las organizaciones de Office 365 la posibilidad de recuperar los datos del buzón si es necesario.

-   **Día 61 a día 90**: un administrador ya no podrá recuperar los datos del buzón. Los datos del buzón se marcarán para su eliminación permanente y llevará 30 días más purgar los datos de Office 365.

Si decide que el ciclo de vida de este buzón no cumple los requisitos de su organización para responder a una solicitud de interesado de eliminación, también puede [ponerse en contacto con el Soporte técnico de Microsoft](https://support.microsoft.com/) *después* de haber eliminado definitivamente la cuenta de usuario y solicite a Microsoft que inicie el proceso manual de eliminar los datos de buzón de forma permanente. Tenga en cuenta que este proceso para eliminar los datos del buzón de forma permanente se inicia automáticamente al final del día 61 del ciclo de vida, por lo que no hay motivos para contactar con Microsoft.

## <a name="using-in-app-functionality-to-respond-to-dsrs"></a>Usar una función integrada en la aplicación para responder a las solicitudes de interesado

Aunque la gran mayoría de datos del cliente se crean y producen con las aplicaciones descritas en la sección anterior, Office 365 también ofrece muchas otras aplicaciones que los clientes pueden usar para generar y almacenar datos del cliente. Pero, Búsqueda de contenido actualmente no tiene la posibilidad de buscar datos creados en estas otras aplicaciones de Office 365. Para buscar datos generados por estas aplicaciones, el propietario de datos o usted deben usar funcionalidad o características del producto para encontrar datos que puedan ser relevantes para una DSR. En la tabla siguiente se muestran estas aplicaciones de Office 365. Haga clic en el icono de la aplicación para ir a su sección correspondiente en esta guía que describe cómo responder a las solicitudes DSR en el caso de datos creados en la aplicación.

***Tabla 3: Aplicaciones con funcionalidad integrada en la aplicación que puede usarse para buscar datos del cliente***

<!--start table here NO HEADER -->

||||
|:-----:|:-----:|:-----:|:-----:|
|[<img src="media/O365-DSR-Doc_image35.png"/>](#access)<br/>Access|[]()[<img src="media/O365-DSR-Doc_image22.png" />](#business-apps-for-office-365)<br/>Aplicaciones empresariales <br/>para Office 365 |[<img src="media/O365-DSR-Doc_image22.png"/>](#education)<br/>Education|
|[<img src="media/O365-DSR-Doc_image24.png" />](#flow)<br/>Flow|[<img src="media/formslogo-32px.png" />](#forms)<br/>Forms|[<img src="media/O365-DSR-Doc_image28.png" />](#kaizala)<br/>Kaizala|
|[<img src="media/O365-DSR-Doc_image30.png" />](#planner)<br/>Planner|[<img src="media/O365-DSR-Doc_image23.png"/>](#powerapps)<br/>PowerApps|[<img src="media/O365-DSR-Doc_image32.png" />](#power-bi)<br/>Power BI|
|[<img src="media/O365-DSR-Doc_image25.png" />](#project-online)<br/> Project Online|[<img src="media/publisher-32px.png"/>](#publisher)<br/>Publisher|[<img src="media/O365-DSR-Doc_image27.png" />](#staffhub)<br/>StaffHub|
|[<img src="media/O365-DSR-Doc_image29.png" />](#stream)<br/>Stream|[![Sway](media/sway-32px.png)](#sway)<br/>Sway|[<img src="media/O365-DSR-Doc_image36.png"/>](#whiteboard)<br/>Whiteboard|
||[![Yammer](media/yammer-32px.png)](#yammer)<br/>Yammer|
|||

<!-- end of table -->

### <a name="access"></a>Access

En las secciones siguientes se explica cómo usar la funcionalidad integrada en la aplicación en Microsoft Access para acceder a datos personales, buscarlos, exportarlos y eliminarlos.

##### <a name="discover"></a>Detectar

Existen varias formas de buscar registros en una base de datos de Access que puedan ser relevantes para una solicitud DSR. Para una investigación de DSR, puede buscar registros relacionados con el interesado o registros que contengan datos específicos. Por ejemplo, puede buscar o ir a un registro que corresponda al interesado. O buscar registros que contengan datos específicos, tales como datos personales sobre el interesado. Para más información, vea:

- [Buscar registros en una base de datos de Access](https://support.office.com/article/find-records-in-an-access-database-705220b7-0255-4ef9-9349-6bd7442d1b7e) 

- [Crear una consulta de selección simple](https://support.office.com/article/create-a-simple-select-query-de8b1c8d-14e9-4b25-8e22-70888d54de59)

##### <a name="access"></a>Access

Cuando haya encontrado los registros o campos relacionados con la solicitud DSR, puede realizar una captura de pantalla de los datos o exportarlos a un archivo de Excel, un archivo de Word o un archivo de texto. También puede crear e imprimir un informe basado en un origen de registros o una consulta de selección que haya creado para encontrar los datos. Vea:

- [Introducción a los informes en Access](https://support.office.com/article/introduction-to-reports-in-access-e0869f59-7536-4d19-8e05-7158dcd3681c)

- [Exportar datos a Excel](https://support.office.com/article/export-data-to-excel-64e974e6-ae43-4301-a53e-20463655b1a9)

- [Exportar datos a un documento de Word](https://support.office.com/article/export-access-data-to-a-word-document-6e954c8e-2243-4cb9-8544-607e5b7bfc12)

- [Exportar datos a un archivo de texto](https://support.office.com/article/export-data-to-a-text-file-f72dfc38-a8a0-4c5b-8c2c-bf2950814140)

##### <a name="export"></a>Exportar

Como se ha explicado anteriormente, puede exportar datos de una base de datos de Access en distintos formatos de archivo. Puede que el formato de archivo en el que elija exportar esté determinado por la solicitud de exportación DSR específica de un interesado. Vea [Importar y exportar](https://support.office.com/article/import-and-export-c060505b-d8ac-4499-8879-733e56c6106f) para obtener una lista de temas que describen cómo exportar datos de Access en diferentes formatos de archivo.

##### <a name="delete"></a>Eliminar

Puede eliminar un registro completo o solo un campo de una base de datos de Access. La forma más rápida de eliminar un registro de una base de datos de Access es abrir la tabla en la vista Hoja de datos, seleccionar el registro (fila) o solo los datos de un campo que quiere eliminar y presione Supr. También puede usar una consulta de selección que haya creado para buscar datos y luego convertirla en una consulta de eliminación. Vea:

- [Eliminar uno o varios registros de una base de datos](https://support.office.com/article/delete-one-or-more-records-from-a-database-002b850d-1efa-473d-9297-0994ce46c66a)

- [Crear y ejecutar una consulta de eliminación](https://support.office.com/article/create-and-run-a-delete-query-6da65fe1-0fc7-4a64-8ef0-c052cd4c3ec5)

### <a name="business-apps-for-office-365"></a>Aplicaciones empresariales para Office 365

En esta sección se explica cómo usar la funcionalidad integrada en la aplicación en cada una de las siguientes aplicaciones empresariales para Office 365 para responder a solicitudes DSR.
- [Bookings](#bookings)

- [Listings](#listings)

- [Connections](#connections)

- [Outlook Customer Manager](#outlook-customer-manager)

- [Invoicing](#invoicing)

#### <a name="bookings"></a>Bookings
En las secciones siguientes se explica cómo usar la funcionalidad integrada en la aplicación en Microsoft Bookings para acceder a datos personales, buscarlos, exportarlos y eliminarlos. Esto se aplica tanto a la aplicación Bookings independiente como a Bookings al obtener acceso a Business Center.

Microsoft Bookings permite a los administradores y usuarios o al personal, con licencia de Bookings en la organización, configurar páginas de reserva para que los clientes pueden programar y realizar cambios en las citas, recibir correos electrónicos de confirmación, actualizaciones, cancelaciones y correos electrónicos de aviso. Los propietarios de empresa y su personal también pueden reservar eventos en nombre de sus clientes con Bookings. 

Los clientes, los administradores o el personal crean los siguientes tipos de datos: 

- **Información de contacto de clientes, asociados y amigos**: estos datos contienen el nombre, el número de teléfono, la dirección de correo electrónico, la dirección y notas.
    
    - Se pueden crear contactos manualmente para cualquier persona mediante los clientes de la web de Bookings, de iOS y de Android.
    
    - Se pueden importar contactos para cualquier persona desde un dispositivo móvil de C1 en Bookings con los clientes de Bookings, iOS y Android.
    
    - Los contactos también se crean automáticamente en el momento de la creación de la reserva a través del flujo de trabajo de reservas para cualquier persona con reserva, ya sea que la reserva la cree un usuario en nombre de un cliente o la cree el cliente a través de la página de reservas del propietario.

- **Eventos de reserva**: se trata de reuniones entre el propietario de empresa o su personal designado y un cliente, creadas por el propietario de empresa o el cliente a través de la página pública de reservas del propietario de empresa. Los datos de estos eventos incluyen el nombre, la dirección, la dirección de correo electrónico, el número de teléfono y cualquier otra información que el propietario de empresa recopile del cliente en el momento de la reserva.

- **Confirmaciones, cancelaciones y actualizaciones por correo electrónico**: se trata de mensajes de correo electrónico generados y enviados por el sistema en asociación con determinados eventos de reserva. Contienen datos personales sobre el personal que está previsto que preste el servicio correspondiente y contienen datos personales sobre el cliente especificados por el propietario de empresa o el cliente en el momento de la reserva.

Todo el contenido de cliente se almacena en el buzón de Exchange Online que hospeda la instancia de Bookings de la organización. Este contenido se conserva mientras el propietario de empresa y el cliente están activos en el servicio, a menos que soliciten explícitamente que se eliminen los datos o dejen el servicio. Este contenido puede eliminarse de la interfaz de usuario integrada, con un cmdlet o mediante la eliminación del buzón de reserva correspondiente. Una vez iniciada la acción de eliminación, los datos se eliminarán en el período de tiempo establecido por el propietario de empresa. 

Si un cliente decide dejar el servicio, su contenido de cliente se elimina después de 90 días. Para más información sobre cuándo se elimina el contenido del buzón después de eliminar una cuenta de usuario, vea [Quitar datos de Exchange Online](#removing-exchange-online-data).

#### <a name="end-user-identifiable-information"></a>Información de identificación personal del usuario final

La información de identificación personal del usuario final (EUII) incluye información personal y de contacto sobre el personal que se programa en Bookings. Se agrega a las páginas detalles del personal cuando el propietario de empresa configura Bookings y realiza actualizaciones tras la instalación. Contiene el nombre del miembro del personal, las iniciales, la dirección de correo electrónico y el número de teléfono. Estos datos se almacenan en el buzón de Exchange Online que hospeda Bookings.

Estos datos se conservan mientras el miembro del personal esté activo en el servicio, a menos que los elimine explícitamente el propietario de empresa o un administrador mediante la interfaz de usuario integrada en la aplicación o mediante la eliminación del buzón de reserva correspondiente. Cuando el administrador inicia la eliminación de detalles del personal, o si el miembro del personal deja el servicio, sus detalles se eliminarán conforme a las directivas de retención de contenido del buzón de Exchange Online establecidas por el propietario de empresa o el administrador.

##### <a name="discoveraccess"></a>Detectar y tener acceso
Bookings recopila y almacena los siguientes tipos de datos:

- **Información de perfil de empresa**: el contenido del cliente sobre la empresa que utiliza Bookings se recopila a través del formulario información de la empresa de Bookings y, si el cliente utiliza Bookings junto con el Business Center, se sincroniza con el perfil de la empresa de Business Center. La única EUII asociada a estos datos es una dirección de correo electrónico de C1. Esta dirección es donde se envían las nuevas notificaciones de reserva y los correos electrónicos de actualización.

- **Contactos del cliente**: se pueden crear contactos manualmente mediante los clientes de la web de Bookings, de iOS y de Android o pueden importarse de un dispositivo móvil.  Los contactos se crean también automáticamente durante el uso de la página de reserva de autoservicio. Contienen EUII y se almacenan en el buzón de Bookings.

- **Detalles del personal**: el contenido del cliente incluye datos sobre el personal que es apto para prestar los servicios creados en clientes de la web de Bookings, de iOS y de Android. Los detalles del personal pueden contener el nombre, la dirección de correo electrónico y el número de teléfono.

- **Eventos de reserva**: se trata de reuniones con clientes y contenido de clientes relacionado que crea la empresa mediante un cliente web o una aplicación Android/iOS o que crea el cliente mediante una página pública de reservas (o una página de Facebook). Estos eventos pueden incluir el nombre, la dirección, la dirección de correo electrónico, el número de teléfono y detalles de la cita.

- **Cancelaciones y actualizaciones por correo electrónico y correos electrónicos de aviso**: se trata de mensajes de correo electrónico enviados por el sistema en asociación con las reservas. Contienen los datos del personal y los datos del cliente especificados en el momento de hacer la reserva.

##### <a name="export"></a>Exportar

Para exportar datos correspondientes al propietario de empresa, el personal y los clientes, puede usar el portal de privacidad de Business Center. Vea [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8) (Exportar o eliminar datos de usuario mediante el portal de privacidad de Business Center).

##### <a name="delete"></a>Eliminar
Puede eliminar los siguientes tipos de datos de Bookings en respuesta a una solicitud de eliminación de DSR:

- **Información de perfil de empresa y contactos**: puede eliminar el buzón de Bookings en el Centro de administración de Office 365. Después de eliminar el buzón, durante 30 días tiene la posibilidad de restaurarlo. Después de 30 días, la cuenta y el buzón correspondiente se eliminan permanentemente. Para obtener información detallada sobre cómo eliminar una cuenta de usuario, vea la sección [Eliminar un usuario](#deleting-a-user).

- **Detalles del personal**: puede eliminar personal desde el panel Bookings. Para eliminarlo definitivamente, puede eliminar su cuenta de Office 365.

- **Eventos de Bookings**: puede eliminar eventos de reserva del calendario de Bookings, lo que quitará la información del cliente.

- **Convocatorias de reuniones, confirmaciones, cancelaciones y actualizaciones por correo electrónico y correos electrónicos de aviso**: puede eliminar estos elementos del calendario de Bookings, lo que quitará la información del cliente.

Los propietarios de empresa y los administradores también pueden eliminar los datos de sus clientes mediante el portal de privacidad de Business Center. Vea [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8) (Exportar o eliminar datos de usuario mediante el portal de privacidad de Business Center).

Se pueden eliminar los datos del propietario de empresa y del personal, así como la cuenta de usuario de Office 365 correspondiente. Vea la sección [Borrar un usuario](#deleting-a-user).

#### <a name="listings"></a>Listings

En las secciones siguientes se explica cómo usar la funcionalidad integrada en la aplicación en Microsoft Listings para acceder a datos personales, buscarlos, exportarlos y eliminarlos.

##### <a name="discover"></a>Detectar
El propietario de Listings puede conectar su empresa con Google, Bing, Yelp y Facebook para ver una vista agregada de valoraciones y opiniones. Listings recopila y almacena los siguientes tipos de datos:

- Valoraciones y opiniones de Google

- Valoraciones y opiniones de Bing

- Valoraciones y opiniones de Yelp

- Valoraciones y opiniones de Facebook

##### <a name="access"></a>Acceso
Los propietarios de Listings pueden iniciar sesión en el panel Listings para ver las opiniones y valoraciones que han recibido.

##### <a name="export"></a>Exportar
Para exportar datos del propietario, el personal y los clientes de la empresa, use el portal de privacidad de Business Center. Vea [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8) (Exportar o eliminar datos de usuario mediante el portal de privacidad de Business Center).

##### <a name="delete"></a>Eliminar
Si un propietario de Listings quiere eliminar su información de Listings, puede desconectarse del proveedor en la página de Listings. Después de desconectarse, su información se eliminará de Listings.

#### <a name="connections"></a>Connections
En las secciones siguientes se explica cómo usar la funcionalidad integrada en la aplicación en Microsoft Connections para acceder a datos personales, buscarlos, exportarlos y eliminarlos.

##### <a name="discover"></a>Detectar
Connections recopila y almacena los siguientes tipos de datos: 

- Los clientes o contactos se crean en la empresa con el cliente web o la aplicación móvil (iOS, Android) o mediante la aplicación cuando se envía una campaña de marketing por correo electrónico a un contacto profesional. Los datos del cliente pueden incluir el nombre, la dirección, la dirección de correo electrónico y números de identificación fiscal. Tenga en cuenta que los contactos se comparten en todas las aplicaciones de Business Center.

- Los clientes pueden registrarse en la página de registro de Connections y guardar su información personal.

- Vínculos de campañas por correo electrónico

##### <a name="access"></a>Acceso
Los propietarios de Connections pueden iniciar sesión en el panel Connections y ver las campañas por correo electrónico que han enviado.

##### <a name="export"></a>Exportar
Para exportar datos del propietario, el personal y los clientes de la empresa, use el portal de privacidad de Business Center. Vea [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8) (Exportar o eliminar datos de usuario mediante el portal de privacidad de Business Center).

##### <a name="delete"></a>Eliminar
Después de enviar una campaña por correo electrónico, un propietario de Connections no puede eliminar la campaña. Si hay algún borrador de campaña que quiera eliminar, podrá iniciar sesión en el panel Connections y eliminar los borradores de campaña.

#### <a name="outlook-customer-manager"></a>Outlook Customer Manager
En las secciones siguientes se explica cómo usar la funcionalidad integrada en la aplicación en Outlook Customer Manager para buscar, tener acceso, exportar y eliminar datos personales.

##### <a name="discover"></a>Detectar
Outlook Customer Manager recopila y almacena información de usuario para el propietario de Outlook Customer Manager y sus clientes y contactos profesionales.

- Datos del propietario. Incluyen el nombre, la dirección y la dirección de correo electrónico. Los documentos y archivos que un propietario comparte con un cliente se almacenan en OneDrive para la Empresa, SharePoint Online y como tareas de Outlook.

- Datos de contacto profesionales y del cliente. Los datos del cliente pueden incluir el nombre, la dirección y la dirección de correo electrónico. Los datos de contacto y del cliente se crean en la empresa en Outlook o en Outlook Web App. Los contactos se comparten en todo Business Center. Los documentos y archivos que un cliente comparte con una empresa se almacenan en OneDrive para la Empresa, SharePoint Online y como tareas de Outlook.

Outlook Customer Manager también almacena actividades e información sobre los clientes de Exchange.

##### <a name="access"></a>Acceso
Los propietarios de Outlook Customer Manager pueden iniciar sesión en Outlook o en Outlook Web App y luego ir al panel Outlook Customer Manager para ver las interacciones que han tenido con sus clientes.
##### <a name="export"></a>Exportar
Para exportar datos del propietario de empresa y del cliente, utilice el portal de privacidad de Outlook Customer Manager. Para más información, vea [Export or delete user data using the Outlook Customer Manager privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8) (Exportar o eliminar datos de usuario mediante el portal de privacidad de Outlook Customer Manager).
##### <a name="delete"></a>Eliminar
Para eliminar datos del cliente, utilice el portal de privacidad de Outlook Customer Manager. Vea [Export or delete user data using the Outlook Customer Manager privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8) (Exportar o eliminar datos de usuario mediante el portal de privacidad de Outlook Customer Manager).

#### <a name="invoicing"></a>Invoicing
En las secciones siguientes se explica cómo usar la funcionalidad integrada en la aplicación en Microsoft Invoicing para buscar, tener acceso, exportar y eliminar datos personales.

##### <a name="discover"></a>Detectar
Invoicing recopila y almacena los siguientes tipos de datos:

- **Contactos**: los crea la empresa al crear una factura o un presupuesto para un cliente o contacto profesional. Los contactos se comparten en todo Business Center. Los datos del cliente incluyen el nombre, la dirección, la dirección de correo electrónico y los números de identificación fiscal.

- **Facturas**: se crean y envían a los clientes y representan tanto una deuda como una obligación tributaria.

- **Presupuestos**: la empresa puede enviar presupuestos a los clientes. Si un cliente acepta un presupuesto, este se convierte en factura. Un presupuesto se convierte en factura después de que el cliente lo acepte. Los registros de presupuestos no se conservan cuando se convierten en factura.

##### <a name="access"></a>Access
Los usuarios pueden ir al panel Invoicing en su Business Center para ver los borradores de las facturas que han creado y las facturas que se han enviado a los clientes.

##### <a name="export"></a>Exportar
Para exportar datos de facturación de clientes, use el portal de privacidad de Business Center. Vea [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8) (Exportar o eliminar datos de usuario mediante el portal de privacidad de Business Center).

##### <a name="delete"></a>Eliminar
Después de crear y enviar una factura, no se pueden eliminar debido a las leyes de contabilidad. Puede solicitar el propietario de facturación que Microsoft elimine algunos o toda su información de Office 365.

Como alternativa, puede eliminar la cuenta de usuario del titular de la factura en Office 365. Vea la sección [Eliminar un usuario](#deleting-a-user).

### <a name="education"></a>Education
En esta sección se explica cómo usar la funcionalidad integrada en la aplicación de las siguientes aplicaciones de Microsoft Education para responder a solicitudes DSR.

- Tareas

- Bloc de notas de clase

#### <a name="assignments"></a>Tareas
En las secciones siguientes se explica cómo usar la funcionalidad integrada en la aplicación en Microsoft Forms para acceder a datos personales, buscarlos, exportarlos y eliminarlos.

##### <a name="discoveraccess"></a>Detectar y tener acceso
Las tareas almacenan la información que generan los profesores y los alumnos. Parte de esta información se almacena en SharePoint y otra parte se almacena en una ubicación que no es de SharePoint.

##### <a name="finding-assignments-data-stored-in-sharepoint"></a>Buscar datos de tareas almacenados en SharePoint 

Los archivos de alumnos asociados a un envío de tarea se almacenan en una biblioteca de documentos (denominada **Trabajo del alumno**) y los archivos asociados a tareas creadas por los profesores (y accesibles para los alumnos) se almacenan en otra biblioteca de documentos (denominada **Archivos de clase**). Las bibliotecas de documentos están en el sitio de SharePoint del equipo de clase correspondiente.

Un administrador puede usar la herramienta de Búsqueda de contenido en el Centro de seguridad y cumplimiento de Office 365 para buscar archivos de alumnos (en las bibliotecas de trabajos de alumnos y de archivos de clase) relacionados con envíos de tareas, así como archivos relacionados con las tareas. Por ejemplo, un administrador puede buscar todos los sitios de SharePoint de la organización y usar el nombre del alumno y el nombre de la clase o tarea en la consulta de búsqueda para encontrar datos relevantes para una solicitud DSR. 

De forma similar, un administrador puede buscar archivos de profesor relacionados con las tareas en los archivos que un profesor ha distribuido a los alumnos. Por ejemplo, un administrador puede buscar todos los sitios de SharePoint de la organización y usar el nombre del profesor y el nombre de la clase o tarea en la consulta de búsqueda para encontrar datos relevantes para una solicitud DSR.

Vea la sección [Usar la herramienta Búsqueda de contenido eDiscovery para responder a solicitudes del interesado](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs) de esta guía.

##### <a name="finding-assignments-data-not-stored-in-sharepoint"></a>Buscar datos de tareas no almacenados en SharePoint
Los siguientes tipos de datos de tareas no se almacenan en el sitio de SharePoint del equipo de clase y, por lo tanto, no se pueden detectar mediante la Búsqueda de contenido. Estos datos incluyen lo siguiente:

- Las calificaciones de los alumnos y los comentarios del profesor.

- La lista de documentos enviados para una tarea por cada alumno.

- Detalles de la tarea, como la fecha en que vence.

Para buscar datos, un administrador o un profesor tendrá que ir a la tarea en el sitio del equipo de clase para encontrar datos que pueden ser relevantes para una solicitud DSR. Un administrador puede agregarse a sí mismo como propietario en la clase y ver todas las tareas del equipo de clase.

Tenga en cuenta que aunque un alumno ya no forme parte de una clase, puede que sus datos estén todavía presentes en la clase y marcados como "no inscrito ya". En este caso, un alumno que envíe una solicitud de DSR tendrá que proporcionar al administrador la lista de clases en las que se inscribió formalmente.

##### <a name="export"></a>Exportar
Puede exportar los datos de tareas de un alumno concreto correspondientes a todas las clases en las que el alumno está inscrito actualmente mediante un script PowerShell. Vea:

- [Using scripts to export and delete user data from Assignments](https://support.office.com/article/04473375-6c00-4dda-bfe5-b55a772958fe) (Usar scripts para exportar y eliminar datos de usuario de tareas).

- [Export student and teacher data from Assignments](https://support.office.com/article/e8c36e0e-fb6e-42c5-97fd-66f90f92a13a) (Exportar datos de alumnos y profesores de tareas).

Si el alumno se ha eliminado del sitio de clase del equipo, el administrador puede agregarlo al sitio antes de ejecutar el script de exportación. También puede usar el archivo de entrada del script para identificar cada clase en la que alguna vez el alumno haya estado inscrito. O bien, usar el script de exportación de tareas para exportar los datos de envío de todas las tareas a las que un profesor tenga acceso.

##### <a name="delete"></a>Eliminar
Puede eliminar datos de tareas de un alumno concreto correspondientes a todas las clases en las que el alumno está inscrito actualmente mediante un script PowerShell. Debe hacerlo antes de quitar al alumno de la clase. Vea:

- [Using scripts to export and delete user data from Assignments](https://support.office.com/article/04473375-6c00-4dda-bfe5-b55a772958fe) (Usar scripts para exportar y eliminar datos de usuario de tareas).

- [Eliminar datos de alumnos de tareas](https://support.office.com/article/a368853a-9565-4320-8e86-2f9423e932a4).

Si el alumno se ha eliminado del sitio de clase del equipo, el administrador puede agregarlo de nuevo al sitio antes de ejecutar el script de exportación. También puede usar el archivo de entrada del script para identificar todas las clases en la que el alumno ha estado inscrito alguna vez. No se puede usar el script de eliminación de tareas para eliminar datos de profesores porque todas las tareas se comparten en todo el sitio del equipo de clase. Como alternativa, el administrador tendrá que agregarse a sí mismo en el sitio del equipo de clase y luego eliminar una tarea concreta.

La búsqueda de contenido en el bloc de notas de clase se describe anteriormente en esta guía. Vea la sección [Bloc de notas de clase de OneNote](#onenote-class-notebook). También puede usar la herramienta Búsqueda de contenido para exportar datos de un bloc de notas de clase. Como alternativa, un administrador o el interesado puede exportar datos de un bloc de notas de clase. Vea [Guardar una copia de un bloc de notas de clase](https://support.office.com/article/44733e18-0ef1-4d4b-be51-fc2ac5bfe9ec).

### <a name="flow"></a>Flow

Las secciones siguientes explican cómo usar la función integrada en la aplicación en Microsoft Flow para acceder a datos personales, buscarlos, exportarlos y eliminarlos.

#### <a name="discover"></a>Detectar

Los usuarios pueden usar Flow para realizar tareas relacionadas con los datos como sincronizar archivos entre aplicaciones, copiar archivos desde un servicio de Office 365 a otro y recopilar datos de una aplicación de Office 365 y almacenarlos en otro. Por ejemplo, un usuario puede configurar Flow para guardar datos adjuntos de correo electrónico de Outlook para su cuenta de OneDrive para la Empresa. En este ejemplo, podría usar la herramienta de búsqueda de contenido para buscar en el buzón del usuario el mensaje de correo electrónico que contiene el archivo adjunto o buscar el archivo en su cuenta de OneDrive para la Empresa. Esto es un ejemplo en el que los datos manejados con Flow pueden detectarse en servicios de Office 365 conectados a un flujo de trabajo de Flow.

Además, los usuarios pueden usar Flow para copiar o cargar archivos de Office 365 a un servicio externo, como Dropbox. En estos casos, debería enviarse una solicitud de interesado relacionada con los datos de un servicio externo, que trata los datos en este tipo de escenario.

Si el administrador recibe una solicitud de interesado, puede agregarse a sí mismo como propietario de los flujos de un usuario. Esto permite que un administrador realice funciones como exportar definiciones de flujo, ejecutar historiales y realizar tareas de permisos de Flow. Vea [Administrar Flow en el Centro de administración](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/).

La capacidad de un administrador de añadirse a sí mismo como propietario de un Flow requiere una cuenta con los siguientes permisos:

- Licencia del Plan 2 de PowerApps/Flow (de pago o de prueba)

- [Administrador global de Office 365\](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504)

    o

- [Administrador mundial Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)

Estos privilegios permiten al administrador usar el centro de administración de Flow para acceder a todos los flujos de la organización.

Para agregarse como propietario de un flujo.

1.  Vaya a <https://admin.flow.microsoft.com>

2.  Inicie sesión con sus credenciales de Office 365.

3.  En la página **Entornos**, haga clic en el entorno cuyos flujos quiere ver. Tenga en cuenta que las organizaciones de Office 365 tienen ya un entorno predeterminado.

4.  En la página del entorno que ha seleccionado, haga clic en **Recursos** y luego en **Flujos**. Se muestra una lista de todos los flujos del entorno.

5.  Haga clic en **Ver detalles** del flujo al que quiere agregarse como miembro.

6.  En **Propietarios**, haga clic en **Administrar el uso compartido**.

7.  En la ventana **Compartir**, agréguese como miembro y, a continuación, guarde los cambios.

Después de hacerse usted mismo propietario, vaya a **Flujo** \> **Mis flujos** \> **Flujos de equipo** para acceder al flujo. Puede descargar el historial de ejecución o exportar el flujo desde allí. Vea:

-   [Descargar y ejecutar el historial de flujo](https://flow.microsoft.com/blog/download-history-recurrence/)

-   [Exportar e importar los flujos en entornos con empaquetado](https://flow.microsoft.com/blog/import-export-bap-packages/)

#### <a name="access"></a>Acceder

Un usuario puede tener acceso a las definiciones y ejecutar historiales de sus flujos.

-   **Definiciones de flujo:** Un usuario puede exportar la definición de un flujo (que se exporta como paquete de Flow, con formato JSON en un archivo zip). Vea [Exportar e importar sus flujos entre entornos con empaquetado](https://flow.microsoft.com/blog/import-export-bap-packages/).

-   **Historiales ejecutados por Flow:** Un usuario puede descargar el historial de ejecución de cada uno de los flujos. Un historial ejecutado por Flow se descarga como CSV, que se puede abrir en Excel para filtrar o buscar. Puede descargar el historial de ejecución de flujos de varios usuarios. Vea [ejecutar el historial del flujo de descargar](https://flow.microsoft.com/blog/download-history-recurrence/).

#### <a name="delete"></a>Eliminar

Un administrador puede agregarse a sí mismo como propietario de los flujos de un usuario en el centro de administración de Flow. <span id="_Hlk511117287" class="anchor"> </span>Si un usuario deja la organización y se elimina su cuenta de Office 365, se conservarán los flujos que posea. Esto sirve para ayudar a su organización a transicionar los flujos a los propietarios nuevos y evitar las interrupciones a su empresa con respecto a los flujos que pueden usarse para procesos empresariales compartidos. Un administrador deberá determinar si va a eliminar los flujos que pertenecen al usuario o simplemente volverá a asignar a los propietarios de nuevos y realizar la acción.

Para los flujos compartidos, cuando un usuario queda eliminado de su organización, su nombre se quita de la lista de propietarios.

#### <a name="export"></a>Exportar

Un administrador puede exportar la definición y ejecutar un historial de flujos de usuario. Para esto, un administrador debe agregarse como propietario del flujo del usuario en el centro de administración de Flow.

-   **Definiciones de flujo:** Después de que un administrador se agregue a sí mismo como propietario de un flujo, puede ir a **Flow** \> **Mis flujos** \> **Flujos de equipo** para exportar la definición de un flujo (que se exporta como paquete de Flow, con formato JSON en un archivo zip). Vea [Exportar e importar sus flujos entre entornos con empaquetado](https://flow.microsoft.com/blog/import-export-bap-packages/).

-   **Historiales de Flow**: De forma similar, un administrador debe añadirse como propietario de un Flow para exportar el historial de sus flujos. El historial de Flow se descarga como archivo CSV, lo que significa que puede usar Excel para filtrarlo o realizar búsquedas. También puede descargar el historial de varios Flow mientras sea el propietario. Vea [Descargar historiales de Flow](https://flow.microsoft.com/blog/download-history-recurrence/).

#### <a name="connections-and-custom-connectors-in-flow"></a>Conexiones y conectores personalizados en Flow

Las conexiones requieren que los usuarios proporciones credenciales para conectar a las API, aplicaciones SaaS y sistemas personalizados. Estas conexiones son propiedad del usuario que estableció la conexión y pueden [administrarse](https://docs.microsoft.com/flow/add-manage-connections) en el propio producto. Tras la reasignación de Flow, un administrador puede utilizar cmdlets de PowerShell para listar y eliminar estas conexiones como parte de la eliminación de datos de usuario.

Los conectores personalizados permiten a las organizaciones ampliar las capacidades de Flow al conectarse a los sistemas donde no hay disponible un conector de fábrica. El autor de un conector personalizado puede [compartirlo](https://docs.microsoft.com/flow/register-custom-api) con otros usuarios de la organización. Después de recibir una solicitud de interesado de eliminación, un administrador debe considerar volver a asignar la propiedad de estos conectores para evitar interrupciones de la empresa. Para acelerar este proceso, un administrador puede usar cmdlets de PowerShell para listar, volver a asignar o eliminar conectores personalizados.

### <a name="forms"></a>Formularios
Las secciones siguientes explican cómo usar la función integrada en la aplicación en Microsoft Forms acceder a datos personales, buscarlos, exportarlos y eliminarlos.

#### <a name="discover"></a>Detectar

Los usuarios de Forms pueden ir a <https://forms.office.com> y seleccionar **Mis formularios** para ver los formularios que han creado. También pueden seleccionar **Compartidos conmigo** para ver Forms compartidos por otros usuarios con un vínculo. Si hay muchos Forms por los que pasar, los usuarios pueden usar la barra de búsqueda integrada para buscar en Forms por título o autor. Para determinar si Microsoft Forms contiene datos personales susceptibles a su investigación de solicitud de interesado, puede pedirle al interesado que busque en su lista de **Compartidos conmigo** para determinar qué usuarios ("Propietarios de formulario") le han enviado Forms. A continuación, puede solicitar a los propietarios que seleccionen **Compartir** en la barra de navegación superior y que le envíen un vínculo a un formulario específico para que pueda consultarlo y determinar si es relevante para su solicitud.

#### <a name="access"></a>Acceder

Después de encontrar los formularios pertinentes, puede acceder a sus respuestas haciendo clic en la pestaña **Respuestas**. Obtenga más información sobre cómo [comprobar los resultados del cuestionario](https://support.office.com/article/c4a9b45c-d62f-4eb7-b5db-ad81892c7c07) o [resultados de formularios](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af). Para revisar los resultados en Excel, seleccione la pestaña **Respuestas** y, a continuación, haga clic en **Abrir en Excel**. Si desea enviar una copia del formulario al interesado, puede realizar capturas de pantalla de las preguntas y respuestas importantes que se muestran en formato de texto enriquecido o enviar una copia de Excel con los resultados del interesado. Si está usando Excel y le gustaría compartir con el interesado el resultado encuesta, puede eliminar algunas filas o columnas o censurar el resto de las secciones antes de compartir los resultados. Como alternativa, puede ir a **compartir \> obtener un vínculo para duplicar** (en Compartir como plantilla) para proporcionarle al interesado una réplica de todo el formulario.

#### <a name="delete"></a>Eliminar

El propietario de una encuesta, un cuestionario o un sondeo puede eliminarlos de forma permanente. Si quiere satisfacer la solicitud de un interesado sobre el derecho al olvido y eliminar completamente un formulario, búsquelo en la lista, seleccione los puntos (elipsis) en la esquina superior derecha de la vista previa del formulario y haga clic en **Eliminar**. Tras eliminar un formulario, no puede recuperarse. Para más información, consulte [Eliminar un formulario](https://support.office.com/article/delete-a-form-2207e468-ce1b-4c4a-a256-caf631d87af0).

#### <a name="export"></a>Exportar

Para exportar las preguntas y respuestas de un formulario a un archivo de Excel, abra el formulario, seleccione la pestaña **Respuestas** y a continuación, seleccione **Abrir en Excel**.

### <a name="kaizala"></a>Kaizala

En las secciones siguientes se explica cómo usar la funcionalidad integrada en la aplicación en Microsoft Kaizala para acceder a datos personales, buscarlos, exportarlos y eliminarlos.

#### <a name="discover"></a>Detectar
Un administrador tiene acceso a los datos de la organización de un usuario, que son datos que se comparten entre grupos de la organización, desde el portal de administración de Kaizala. Los datos de la organización se conservan durante un período de tiempo determinado por las directivas de retención de la organización. Además de los datos de usuario, los servidores de Kaizala también almacenan los siguientes tipos de datos de la organización:

- La lista de los miembros que forman parte de los grupos de la organización

- Los datos de mensajes de grupos de la organización, que son mensajes y respuestas que se comparten entre grupos de la organización

- Una lista de los usuarios de las organizaciones

- Los datos de uso de productos y servicios capturados para todos los usuarios de la organización

- Las acciones de Kaizala creadas por la organización

- Los datos de conectores de Kaizala

El interesado puede tener acceso a los datos del cliente de un usuario con la aplicación móvil de Kaizala de datos del consumidor. Los datos del consumidor incluyen los siguientes tipos de datos:

- Los datos que pertenecen a grupos privados en Kaizala (almacenados en servidores de Kaizala durante 90 días)

- La información de perfil de un usuario, además de los contactos del usuario

- La lista de los miembros que forman parte de los mismos grupos que el usuario

- Los mensajes y respuestas compartidos entre grupos

- La lista de contactos del usuario (almacenada en el servicio de Kaizala)

- Las transacciones efectuadas por el usuario en Kaizala (se aplica Kaizala únicamente a los usuarios de la República de la India)

- Los datos de uso de productos y servicios del usuario

#### <a name="access"></a>Acceso
Los usuarios de Kaizala pueden ir a su dispositivo móvil para ver contenido de Kaizala que han creado en su dispositivo. Para determinar si las aplicaciones móviles de Kaizala son un lugar en el que es probable que residan datos personales relevantes para una DSR, puede pedir al interesado que busque en su aplicación de Kaizala la información solicitada.

#### <a name="export"></a>Exportar
Cuando los usuarios de la organización usan Kaizala, se generan datos del consumidor y puede que se generen datos de la organización si el usuario forma parte de un grupo de la organización. Los administradores pueden exportar los datos de la organización de un usuario desde el portal de administración de Kaizala. Los usuarios consumidores de Kaizala pueden exportar sus datos privados desde la aplicación móvil de Kaizala. En ambos casos, tenga en cuenta que los datos de uso de productos y servicios también se exportan cuando un administrador o usuario exporta datos de Kaizala. Para más información, vea:

- [Exportar o eliminar datos de la organización de un usuario en Kaizala](https://support.office.com/article/export-or-delete-a-user-s-organizational-data-in-kaizala-150ec214-a070-4e8a-8509-82f46d84bbb6)

- [Exportar o eliminar los datos en la aplicación móvil de Kaizala](https://support.office.com/article/export-or-delete-your-data-in-the-kaizala-mobile-app-65f83dbc-4f10-4644-9b2d-9945c967684e)

#### <a name="delete"></a>Eliminar
Un administrador de Kaizala puede quitar la cuenta de un usuario de Kaizala en el portal de administración de Kaizala. Después de eliminar una cuenta de usuario, el usuario se quita de todos los grupos que pertenecen a la organización y los datos de la organización se eliminan de su dispositivo. 

Para eliminar todos los datos privados del dispositivo móvil del usuario, el usuario de Kaizala puede eliminar su cuenta de Kaizala. Después de eliminar la cuenta, todo el contenido relacionado con Kaizala, incluidos los chats, las fotos y otros datos, se eliminará del dispositivo.

Para más información, vea:

- [Exportar o eliminar datos de la organización de un usuario en Kaizala](https://support.office.com/article/export-or-delete-a-user-s-organizational-data-in-kaizala-150ec214-a070-4e8a-8509-82f46d84bbb6)

- [Exportar o eliminar los datos en la aplicación móvil de Kaizala](https://support.office.com/article/export-or-delete-your-data-in-the-kaizala-mobile-app-65f83dbc-4f10-4644-9b2d-9945c967684e)

### <a name="planner"></a>Planner

Las secciones siguientes explican cómo usar la función integrada en la aplicación en Microsoft Planner para acceder a datos personales, buscarlos, exportarlos y eliminarlos.

#### <a name="discover"></a>Detectar

Los planes de Planner están asociados a un grupo de Office 365 y los archivos de Grupos de Office 365 se almacenan en un sitio de SharePoint Online asociado con el grupo. Eso significa que puede usar la búsqueda de contenido para buscar archivos de Planner en el sitio del grupo de Office 365. Para ello, debe tener la dirección URL del grupo de Office 365. Vea [Buscar en Microsoft Teams y Grupos de Office 365](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4) en el tema de ayuda "Búsqueda de contenido en Office 365" para obtener sugerencias sobre cómo conseguir información sobre Grupos de Office 365 para ayudarle a buscar archivos de Planner en los sitios correspondientes de SharePoint Online.

#### <a name="access"></a>Access

Como se ha explicado anteriormente, puede buscar el sitio subordinado de SharePoint Online y el buzón que están asociados con un plan. A continuación, puede obtener una vista previa o descargar los resultados de búsqueda relacionados para obtener acceso a los datos.

#### <a name="delete"></a>Eliminar

Puede eliminar de forma manual la información personal de un usuario tanto otorgándose a sí mismo permisos de acceso a los planes de los que forma parte el usuario, o iniciar sesión como el usuario para realizar los cambios. Vea [Eliminar datos de usuario en Microsoft Planner](https://support.office.com/article/delete-user-data-in-microsoft-planner-4349ded2-1891-4896-8e27-05fd40f3929f).

#### <a name="export"></a>Exportar

Puede usar un script de PowerShell para exportar datos de un usuario desde Planner. Al exportar los datos, se exporta un archivo independiente de JSON por cada plan del que forme parte el usuario. Vea [Exportar datos de usuario desde Microsoft Planner](https://support.office.com/article/export-user-data-from-microsoft-planner-91258c96-b353-4da1-b6d9-d78e4809cf08).

### <a name="power-bi"></a>Power BI

Las siguientes secciones explican cómo usar la función integrada en la aplicación de Microsoft Power BI para acceder a datos personales, buscarlos, exportarlos y eliminarlos.

#### <a name="discover"></a>Detectar
Puede buscar contenido en las distintas áreas de trabajo de Power BI, tales como paneles, informes, libros y conjuntos de datos. Cada tipo de área de trabajo contiene un campo de búsqueda que permite buscar en esa área de trabajo. Vea [Navegación: búsqueda, detección y ordenación de contenido en el servicio Power BI](https://docs.microsoft.com/power-bi/service-navigation-search-filter-sort).

#### <a name="access"></a>Acceso

Puede imprimir paneles, informes y elementos visuales a partir de informes en Power BI para producir una copia física. Tenga en cuenta que no puede imprimir informes completos, solo una página cada vez. Para esto, vaya a un informe, use el campo de búsqueda para encontrar datos específicos y, a continuación, imprima esa página. Vea [Imprimir desde el servicio Power BI](https://docs.microsoft.com/power-bi/service-print).

#### <a name="delete"></a>Eliminar

Para eliminar libros, informes y paneles, consulte [Eliminar casi cualquier cosa en el servicio Power BI](https://docs.microsoft.com/power-bi/service-delete).

Eliminar un libro, informe o panel no elimina el conjunto de datos subyacente. Como Power BI depende de una conexión dinámica a los datos de origen subyacentes para ser completo y preciso, la eliminación de datos personales debe realizarse desde ahí (por ejemplo, si crea un informe de Power BI conectado a Dynamics 365 for Sales como origen de datos dinámico, tendrá que realizar cualquier corrección de datos en Dynamics 365 for Sales).

Después de eliminar los datos, puede usar la capacidad de [actualización de datos programada](https://docs.microsoft.com/power-bi/refresh-scheduled-refresh) de Power BI para actualizar el conjunto de datos que se almacena en Power BI, tras lo cual, los datos eliminados no se reflejarán en los informes o paneles de Power BI que usaban esos datos. Para ayudar a cumplir los requisitos del RGPD, debe tener directivas para garantizar que va a actualizar los datos al ritmo adecuado.

#### <a name="export"></a>Exportar

Para facilitar una solicitud de portabilidad de datos, puede exportar paneles e informes de Power BI:

-   Puede exportar los datos subyacentes para paneles e informes a un archivo de Excel estático. Vea el vídeo en [Imprimir desde el servicio de Power BI](https://docs.microsoft.com/power-bi/service-print). Con Excel, puede, a continuación, editar los datos personales que desea incluir en la solicitud de portabilidad y guardarlo en un formato legible, y común como .csv o .xml.

-   Puede exportar (descargar) un informe del servicio Power BI servicio en Office 365 a un archivo .pbix si se publicó con Power BI Desktop. A continuación, puede importar el archivo a Power BI Desktop y publicarlo (exportar) en el servicio Power BI de otra organización. Vea [Exportar un informe de servicio de Power BI Desktop](https://docs.microsoft.com/power-bi/service-export-to-pbix).

### <a name="powerapps"></a>PowerApps

Las siguientes secciones explican cómo usar la funcionalidad integrada en Microsoft PowerApps para acceder a datos personales, buscarlos, exportarlos y eliminarlos. Estos pasos describen cómo un administrador puede cambiar las aplicaciones y sus recursos dependientes a nuevos propietarios para limitar la interrupción de la empresa.

#### <a name="discover"></a>Detectar

PowerApps es un servicio para crear aplicaciones que se pueden compartir y usar en su organización. Como parte del proceso de creación o ejecución de una aplicación, un usuario acabará almacenando varios tipos de datos y recursos en el servicio de PowerApps, como aplicaciones, entornos, conexiones, conectores personalizados y permisos.

Para facilitar una solicitud de interesado relacionada con PowerApps, puede aprovechar las operaciones de administración expuestas en el [centro de administración de PowerApps](https://admin.powerapps.com/) y [cmdlets de PowerShell de administración de PowerApps](https://go.microsoft.com/fwlink/?linkid=871804). El acceso a estas herramientas requiere una cuenta con los permisos siguientes:

- Una licencia de PowerApps Plan 2 pagada o de prueba. Puede suscribirse a una licencia de prueba de 30 días [aquí](http://web.powerapps.com/trial).

- [Administrador global de Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504)

    o
- [Administrador mundial Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)

Para obtener más información sobre cómo encontrar datos personales, consulte [Detectar datos personales de PowerApps](https://go.microsoft.com/fwlink/?linkid=871880).

El servicio de PowerApps también incluye el servicio de datos comunes para aplicaciones, que permite a los usuarios almacenar datos en entidades estándar o personalizadas en una base de datos de servicio de datos común. Puede ver los datos almacenados en estas entidades desde el [portal PowerApps Maker](https://web.powerapps.com) y usar las funciones de búsqueda de producto de [búsqueda avanzada](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search) para buscar datos específicos de la entidad. Para más información sobre detectar datos personales en el servicio de datos comunes, consulte [Detectar datos personales en el servicio de datos comunes](https://go.microsoft.com/fwlink/?linkid=871881).

#### <a name="access"></a>Acceder

Los administradores tienen la capacidad de asignarse privilegios para acceder a las aplicaciones y a los recursos asociados y ejecutarlos (incluidos flujos, conexiones y conectores personalizados) con el [Centro de administración de PowerApps](https://admin.powerapps.com/) o [cmdlets de PowerShell de administrador de PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

Una vez tiene acceso a la aplicación de usuario, puede usar un navegador web para abrir la aplicación. A continuación, puede tomar una captura de pantalla de los datos. Vea [Usar PowerApps en un navegador web](https://docs.microsoft.com/powerapps/run-app-browser).

#### <a name="delete"></a>Eliminar

Como PowerApps permite a los usuarios crear aplicaciones de línea de negocios que pueden ser una parte crítica de las operaciones diarias de su organización, cuando un usuario se marcha y se elimina su cuenta de Office 365, el administrador necesitará determinar si elimina las aplicaciones del usuario o las reasigna a un nuevo propietario. Esto sirve para ayudar a su organización a pasar las aplicaciones a nuevos propietarios y evitar interrupciones en su negocio debido a aplicaciones que pueden usarse en procesos de negocios compartidos.

Para los datos compartidos, como aplicaciones, los administradores deben decidir si quieren eliminar permanentemente los datos compartidos de ese usuario o conservarlos y asignárselos a sí mismos o a alguien de la organización. Vea [datos personales de PowerApps eliminar](https://go.microsoft.com/fwlink/?linkid=871883).

Eliminan los datos que se almacenan un usuario de una entidad de servicio de datos común para la base de datos de aplicaciones también necesitará revisar y (si lo desea) por un administrador mediante las capacidades del producto. Vea [datos personales de servicio de datos común eliminar usuario](https://go.microsoft.com/fwlink/?linkid=871886).

#### <a name="export"></a>Exportar

Los administradores tienen la capacidad de exportar los datos personales almacenados de un usuario en el servicio de PowerApps mediante el [centro de administración de PowerApps](https://admin.powerapps.com/) y los [cmdlets de PowerShell de administración de PowerApps](https://go.microsoft.com/fwlink/?linkid=871804). Vea [Exportar datos personales de PowerApps](https://go.microsoft.com/fwlink/?linkid=871883).

También puede usar las capacidades de búsqueda integradas de [Búsqueda avanzada](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search) para buscar los datos personales de un usuario en cualquier entidad. Para más información acerca de la exportación de datos personales en servicios de datos comunes, vea [Exportar datos personales en servicios de datos comunes](https://go.microsoft.com/fwlink/?linkid=871889).

#### <a name="connections-and-custom-connectors-in-powerapps"></a>Conexiones y conectores personalizados en PowerApps

Las conexiones requieren que los usuarios proporcionen credenciales para conectarse a las API, aplicaciones SaaS y sistemas personalizados. Estas conexiones son propiedad del usuario que estableció la conexión y pueden [administrarse](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection) en el propio producto. Tras la reasignación de PowerApps, un administrador puede utilizar cmdlets de PowerShell para listar y eliminar estas conexiones como parte de la eliminación de datos de usuario.

Los conectores personalizados permiten a las organizaciones ampliar las capacidades de PowerApps al conectarse a los sistemas donde no hay disponible un conector de fábrica. El autor de un conector personalizado puede [compartirlo](https://docs.microsoft.com/connectors/custom-connectors/use-custom-connector-powerapps) con otros usuarios de la organización. Después de recibir una solicitud de interesado de eliminación, un administrador debe considerar volver a asignar la propiedad de estos conectores para evitar interrupciones de la empresa. Para acelerar este proceso, un administrador puede usar cmdlets de PowerShell para listar, volver a asignar o eliminar conectores personalizados.

### <a name="project-online"></a>Project Online

Las siguientes secciones explican cómo usar la función integrada en la aplicación de Microsoft Project Online para acceder a datos personales, buscarlos, exportarlos y eliminarlos.

#### <a name="discover-and-access"></a>Detectar y acceder

Puede usar la búsqueda de contenido para buscar el sitio de SharePoint Online que está asociado a un proyecto (cuando se crea un proyecto, hay una opción para crear un sitio de SharePoint Online asociado); la búsqueda de contenido no busca los datos en un proyecto en Project Online, solo en el sitio que tenga asociado. Aunque la búsqueda de contenido buscará metadatos sobre proyectos, como personas mencionan en el asunto). Sin embargo, esto puede ayudarle a encontrar el proyecto que contiene los datos relacionados con la DSR (y acceder a él).

> [!TIP]
> La dirección URL de la colección de sitios de la organización donde se encuentran los sitios asociados a Projects es **https://\<su organización\>.sharepoint.com/sites/pwa**; por ejemplo, **https://contoso.sharepoint.com/pwa**. Puede usar esta colección de sitios específica como ubicación de la búsqueda de contenido y luego escribir el nombre en la consulta de búsqueda. Además, un administrador de TI puede usar la página de colecciones de sitios en el Centro de administración de SharePoint para obtener una lista de colecciones de sitios de PWA de la organización.

#### <a name="delete"></a>Eliminar

Puede eliminar información de un usuario de su entorno de Project Online. Vea [Eliminar datos de usuario de Project Online](https://support.office.com/article/delete-user-data-from-project-online-252fa593-9c25-47ed-b861-643fe8bf1cb7).

#### <a name="export"></a>Exportar

Puede exportar el contenido de un usuario específico de su entorno de Project Online. Estos datos se exportan a varios archivos en el formato JSON. Para ver instrucciones paso a paso, consulte [Exportar datos de usuario de Project Online](https://support.office.com/article/export-user-data-from-project-online-27f3838d-3dbe-4b98-80dc-df55f851154d). Para obtener información detallada sobre los archivos que se exportan, vea [Definiciones de objeto JSON exportadas de Project Online](https://support.office.com/article/project-online-export-json-object-definitions-ce5faeae-9af4-4696-b847-a1f4f20327c7).

### <a name="publisher"></a>Publisher

Las secciones siguientes explican cómo usar la función integrada en la aplicación en Microsoft Publisher para acceder a datos personales, buscarlos, exportarlos y eliminarlos.

#### <a name="discover"></a>Detectar

Puede usar la característica de búsqueda en la aplicación para buscar texto en un archivo de Publisher del mismo modo que puede hacer en la mayoría de aplicaciones de Office. Vea [Buscar y reemplazar texto](https://support.office.com/article/find-and-replace-text-bfe54275-b7c7-4d0f-904d-a2f38d322268).

#### <a name="access"></a>Access

Después de encontrar los datos, puede tomar una captura de pantalla o copiarlos y pegarlos en un archivo de Word o de texto y proporcionarlos al interesado. También puede guardar una publicación como un archivo PDF, XPS o Word. Vea:

  - [Guardar una publicación como un documento de Word](https://support.office.com/article/save-a-publication-as-a-word-document-b5eaaae5-6f1b-48c1-bebc-44460376b693)

  - [Guardar como o convertir una publicación a .pdf o .xps utilizando Publisher](https://support.office.com/article/657332d0-d2c2-464a-9870-e9b3d22e6469)

#### <a name="export"></a>Exportar

Puede proporcionar un interesado con el archivo de Publisher real o, como se explicó anteriormente, puede guardar una publicación como archivo de Word, PDF o XPS. Vea:

  - [Guardar una publicación como un documento de Word](https://support.office.com/article/save-a-publication-as-a-word-document-b5eaaae5-6f1b-48c1-bebc-44460376b693)

  - [Guardar como o convertir una publicación a .pdf o .xps utilizando Publisher](https://support.office.com/article/657332d0-d2c2-464a-9870-e9b3d22e6469)

#### <a name="delete"></a>Eliminar

Puede eliminar el contenido de una publicación, eliminar páginas completas o eliminar un archivo completo de Publisher. Vea [Agregar o eliminar páginas](https://support.office.com/article/add-or-delete-pages-daf71e39-86e0-4bbc-a186-d5ec70450b08)

### <a name="staffhub"></a>StaffHub

Las siguientes secciones explican cómo usar la función integrada en la aplicación de Microsoft StaffHub para acceder a datos personales, buscarlos, exportarlos y eliminarlos.

#### <a name="discover"></a>Detectar

La mayoría de los datos de StaffHub está disponible para todos los miembros del equipo de StaffHub y administradores. Para revisar los datos de StaffHub, haga que un miembro del grupo o el administrador vaya a <https://staffhub.office.com> para buscar datos potencialmente relevantes respecto a la solicitud de interesado o haga que le agreguen como miembro de su equipo para que puede revisar la información en StaffHub en busca de información relevante.

#### <a name="access"></a>Acceder

Cuando encuentre contenido de StaffHub relevante, puede verlo y tomar capturas de pantalla de los datos que le gustaría proporcionar al interesado desde la aplicación o descargarlos.

-   **Información de programación**: la pestaña **Programación** de StaffHub ofrece una **vista Personas** y una **vista Turnos** que le permiten ver la programación diaria, semanal y mensual de los miembros del equipo o los turnos de trabajo. Estas vistas se pueden descargar en Excel, seleccione los puntos suspensivos (elipsis) en la esquina superior izquierda de la aplicación web StaffHub y haga clic en **Exportar programación**.

-   **Archivos compartidos**: todos los archivos de StaffHub se almacenan en SharePoint Online y por tanto es posible descubrirlos, acceder a ellos y exportarlos mediante la búsqueda de contenido tal como se describió anteriormente. También pueden verse desde StaffHub en la pestaña **Archivos**.

-   **Mensajería**: actualmente, se puede acceder a los mensajes siguiendo estos pasos para acceder a datos específicos de usuarios en el siguiente elemento. En el futuro, todos los mensajes de StaffHub se almacenarán en Microsoft Teams, lo que supondrá que podrá usar la herramienta de búsqueda de contenido para acceder a ellos.

-   **Datos específicos de usuarios**: los datos específicos de usuarios se componen de la configuración de usuario, la fuente de actividades de usuario y la solicitud de historial del usuario. Los administradores y los miembros del equipo no pueden ver ninguno de estos datos. Para obtener acceso o exportar los datos específicos del usuario, haga que el interesado inicie sesión con su cuenta de StaffHub. De forma alternativa, si el interesado ha dejado la organización, puede obtener sus datos haciendo que el administrador reinicie la cuenta.

-   **Kronos**: StaffHub admite conexiones a [Kronos](http://www.kronos.com/), que es una herramienta de administración de recursos de terceros. StaffHub y Kronos son encargados del tratamiento independientes y tratan los datos de su organización en los términos individuales que haya aceptado con cada parte. Si su DSR está relacionada con los datos mantenidos por Kronos, debe ponerse en contacto con Kronos para obtener asistencia con la DSR y viceversa.

#### <a name="delete"></a>Eliminar

-   Un administrador de grupo puede eliminar la mayoría del patrón de contenido de datos de la aplicación en StaffHub. Como se mencionó anteriormente en la sección Descubrir de StaffHub, puede agregarse a un equipo como administrador de grupo y eliminar los datos.

-   Cuando una cuenta de usuario se elimina permanentemente, StaffHub registra durante 30 días el nombre, el número de teléfono, la dirección de correo electrónico y la imagen de perfil del usuario días de la cuenta que se está eliminando.

#### <a name="export"></a>Exportar
Consulte la sección [Acceder](#access-12) de StaffHub.

### <a name="stream"></a>Stream

En las secciones siguientes se explica cómo usar la funcionalidad integrada en la aplicación en Microsoft Stream para acceder a datos personales, buscarlos, exportarlos y eliminarlos.

#### <a name="discover"></a>Detectar

Para detectar contenido generado o cargado en Stream que pueda ser relevante para una solicitud del interesado, un administrador de Stream puede ejecutar un informe de usuario para determinar los vídeos, las descripciones de vídeos, los grupos, los canales o los comentarios que un usuario de Stream pueda haber cargado, creado o publicado. Para obtener instrucciones sobre cómo generar un informe, vea [Administración de datos de usuario en Microsoft Stream](https://docs.microsoft.com/stream/managing-user-data). El resultado del informe está en formato HTML y contiene hipervínculos que pueden usarse para navegar a vídeos de posible interés. Si quiere ver un vídeo que tiene un conjunto de permisos personalizados y usted no forma parte de los usuarios originales a los que se dirigía el vídeo, puede verlo en modo de administrador. Vea [Funcionalidad de administración de Microsoft Stream](https://docs.microsoft.com/stream/manage-content-permissions).  

#### <a name="access"></a>Acceso

Según la naturaleza de la solicitud del interesado, puede usar una copia del informe descrito anteriormente ayudar a satisfacer una solicitud del interesado. El informe de usuario incluye el nombre y el identificador único del usuario de Stream, una lista de los vídeos cargados por el usuario, una lista de los vídeos a los que el usuario tiene acceso, una lista de los canales que el usuario ha creado, una lista de todos los grupos de los que el usuario es miembro y una lista de todos los comentarios que el usuario ha dejado en los vídeos. El informe muestra además si el usuario ha visto cada vídeo que aparece en el informe de usuario. Si quiere proporcionar al interesado acceso a un vídeo que satisface una solicitud DSR, puede compartir el vídeo.

#### <a name="export"></a>Exportar

Vea la sección Obtener acceso de Stream. 

#### <a name="delete"></a>Eliminar

Para eliminar o editar vídeos o cualquier otro contenido de Stream, un administrador de Stream puede seleccionar la vista en modo de administrador para realizar la función necesaria. Vea [Funcionalidad de administración de Microsoft Stream](https://docs.microsoft.com/stream/manage-content-permissions). Si un usuario deja la organización y no quiere que su nombre aparezca junto a los vídeos que ha cargado, puede quitar el nombre o reemplazarlo por otro. Vea [Administración de usuarios eliminados en Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users).

### <a name="sway"></a>Sway
Las secciones siguientes explican cómo usar la función integrada en la aplicación en Microsoft Sway para buscar, acceder, exportar y eliminar datos personales.

#### <a name="discover"></a>Detectar
El contenido creado con Sway (en [www.sway.com](http://www.sway.com)) sólo puede ser visto por el propietario y aquellos a los que el autor ha otorgado permiso. Vea [Configuración de privacidad en Sway](https://support.office.com/article/privacy-settings-in-sway-394b551c-be6f-4bd7-a70a-f318d72bf217). Para determinar si Sway es un lugar con datos personales que puedan responder a la solicitud de interesado, puede pedir al interesado y a los usuarios de la organización que probablemente hayan generado el contenido que busquen en sus Sways y compartan con usted cualquiera que pueda contener datos personales susceptibles de formar parte de la solicitud del interesado. Para obtener información sobre cómo compartir un Sway, consulte "Compartir un Sway desde su cuenta de organización" en el artículo [Compartir su Sway](https://support.office.com/article/share-your-sway-1cf853b8-ef7e-46b0-b704-003e58d28998).

#### <a name="access"></a>Acceder

Si ha encontrado datos personales en un Sway que desea compartir con el interesado, puede proporcionarle acceso a los datos a través de varias formas. Puede proporcionar al interesado una copia de la versión en línea de Sway (como se describió anteriormente), puede compartir capturas de pantalla de la porción relevante; también puede imprimir o descargar el Sway en Word o convertirlo en un archivo PDF. Cómo descargar un Sway se describe en la sección siguiente, "Exportar".

#### <a name="delete"></a>Eliminar

Para obtener información sobre cómo eliminar un Sway, vaya a la sección "¿Cómo elimino mi Sway?" en [Configuración de privacidad en Sway](https://support.office.com/article/privacy-settings-in-sway-394b551c-be6f-4bd7-a70a-f318d72bf217).

#### <a name="export"></a>Exportar

Para exportar un Sway, abra el Sway que quiere descargar, seleccione los puntos suspensivos de la esquina superior derecha, seleccione **Exportar** y luego elija **Word** o **PDF**.

### <a name="whiteboard"></a>Whiteboard

Las secciones siguientes explican cómo usar la función integrada en la aplicación en Microsoft Whiteboard para acceder a datos personales, buscarlos, exportarlos y eliminarlos.

- [Whiteboard 2016 en Surface Hub](#whiteboard-2016-on-surface-hub)

- [Whiteboard en todas las demás plataformas.](#whiteboard-for-pc-surface-hub-and-other-platforms)

#### <a name="whiteboard-2016-on-surface-hub"></a>Whiteboard 2016 en Surface Hub

En esta sección se describe cómo responder a las solicitudes DSR creadas con la aplicación de Whiteboard 2016 en Surface Hub.


##### <a name="discover"></a>Detectar

Los archivos de Whiteboard (.wbx) se almacenan en la cuenta de OneDrive para la Empresa de los usuarios. Se puede preguntar al interesado o a otros usuarios si las pizarras que han creado pueden contener datos personales relevantes para una solicitud DSR. Ellos pueden compartir una pizarra con usted o usted puede obtener una copia de la pizarra para dársela al interesado.

Para tener acceso a pizarras y transferirlas: 

1. Concédase acceso a la cuenta de OneDrive for Business del usuario. Vea la sección "Obtener acceso a los documentos de OneDrive para la Empresa" en [Obtener acceso y realizar una copia de seguridad de los datos del usuario anterior](https://support.office.com/article/get-access-to-and-back-up-a-former-user-s-data-a6f7f9ad-e3f5-43de-ade5-e5a0d7531604).

2. Vaya a la carpeta Datos de la aplicación Pizarra de la cuenta de OneDrive para la Empresa del usuario y copie los archivos .wbx de las pizarras que quiere transferir.

3. Concédase acceso a la cuenta de OneDrive para la Empresa del interesado y vaya a la carpeta Datos de la aplicación Pizarra.

4. Pegue los archivos .wbx que copió en el paso anterior.

##### <a name="access"></a>Acceso

Si encuentra datos personales en una pizarra que sean relevantes para una solicitud de acceso DSR, puede proporcionar al interesado acceso a una pizarra de varias formas:

- Realizar capturas de pantalla de las partes importantes de una pizarra.

- Cargue una copia del archivo .wbx en la cuenta de OneDrive para la Empresa del interesado. Vea la sección anterior para conocer los pasos sobre el acceso y la transferencia de archivos .wbx.

- Exportar una copia de pizarra como archivo .png.

##### <a name="export"></a>Exportar

Si ha obtenido una copia de una pizarra, puede exportarla. 

1. Inicie Whiteboard en Surface Hub.

2. Pulse el botón Compartir y luego seleccione Exportar una copia. Puede exportar una pizarra en un archivo de OneNote (.one) o un archivo de imagen (.png).

##### <a name="delete"></a>Eliminar

Puede concederse acceso a la cuenta de OneDrive para la Empresa del usuario y luego eliminar las pizarras.

1. Concédase acceso a la cuenta de OneDrive for Business del interesado. Vea la sección "Obtener acceso a los documentos de OneDrive para la Empresa" en [Obtener acceso y realizar una copia de seguridad de los datos del usuario anterior](https://support.office.com/article/get-access-to-and-back-up-a-former-user-s-data-a6f7f9ad-e3f5-43de-ade5-e5a0d7531604).

2. Vaya a la carpeta Datos de la aplicación Pizarra y elimine el contenido de la carpeta.

####  <a name="whiteboard-for-pc-surface-hub-and-other-platforms"></a>Whiteboard para PC, Surface Hub y otras plataformas

Si un administrador recibe una solicitud DSR de datos en la nueva aplicación Whiteboard, puede utilizar PowerShell de Whiteboard para agregarse a sí mismo (o a otros usuarios) como propietario de las pizarras de un usuario. Esto permite a un administrador realizar acciones tales como tener acceso, exportar y eliminar pizarras. Utilice el cmdlet **Set-WhiteboardOwner** para agregarse a sí mismo o a otro usuario como propietario de una pizarra o utilice el cmdlet **Invoke-TransferAllWhiteboards** para transferir la propiedad de todas las pizarras de un usuario concreto a otro propietario. Para más información sobre el uso de estos cmdlets y la instalación del módulo PowerShell de Whiteboard, veaMicrosoft Whiteboard cmdlet reference- Una vez que usted u ora persona tengan en propiedad una pizarra, vea [Microsoft Whiteboard cmdlet reference](https://docs.microsoft.com/powershell/module/whiteboard/?view=whiteboard-ps) (Referencia de cmdlets de Microsoft Whiteboard).

Una vez que usted u ora persona tengan en propiedad una pizarra, vea el [artículo de soporte técnico de Whiteboard](https://go.microsoft.com/fwlink/?linkid=872780) para obtener instrucciones detalladas sobre el acceso, exportación y eliminación de pizarras.

### <a name="yammer"></a>Yammer

Las secciones siguientes explican cómo usar la función integrada en la aplicación en Microsoft Yammer para acceder a datos personales, buscarlos, exportarlos y eliminarlos.

#### <a name="discover"></a>Detectar

En el centro de administración de Yammer, un administrador superior de Yammer (administrador global de Office 365 o un administrador superior de Yammer) puede exportar los datos que pertenezcan a un usuario determinado. La exportación incluye los mensajes y archivos registrados y modificados por el usuario, así como información sobre los temas y los grupos creados por el usuario. Cuando se ejecuta una exportación de datos específicos del usuario, el administrador también recibirá un mensaje de la Bandeja de entrada con datos de actividad de cuenta del usuario que pueden proporcionar al usuario si así lo desean. Para obtener instrucciones detalladas, consulte [Yammer Enterprise: privacidad](https://support.office.com/article/enterprise-privacy-yammer-eae49f12-4661-4ba5-aa72-01248f0709bf).

Las exportaciones específicas de usuarios son para una sola red, por lo que si el usuario se encuentra en una red de Yammer externa, el administrador debe exportar los datos para esa red externa, además de para la red doméstica.

Para acceder a los datos no incluidos en la exportación, pueden tomarse capturas de pantalla del perfil del usuario, configuración, grupos a los que pertenece, mensajes marcados, usuarios seguidos y temas seguidos. Los usuarios o administradores pueden recoger esta información. Para obtener más información, consulte [Yammer Enterprise: Privacidad](https://support.office.com/article/enterprise-privacy-yammer-eae49f12-4661-4ba5-aa72-01248f0709bf).

#### <a name="access"></a>Acceder

Puede ver los datos de los archivos exportados, incluyendo el texto completo de los mensajes y el contenido de los archivos. También puede hacer clic en vínculos de los archivos exportados para ir directamente a los mensajes registrados y archivos de Yammer, grupos y temas creados por el usuario, mensajes que le gustaron al usuario, mensajes que mencionan al usuario, sondeos en los que ha participado el usuario y vínculos que el usuario ha agregado.

La exportación de datos del usuario no incluye:

- El perfil del usuario:
    - Si el usuario tiene una identidad de Yammer, tiene control total de su perfil. Para obtener información sobre cómo ver y modificar el perfil, vea [Cambiar la configuración de perfiles de Yammer](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851).
    
    - Si el usuario tiene una identidad de Office 365, el perfil de usuario de Yammer se extrae automáticamente de Office 365, que obtiene la información de perfil de Azure Active Directory (AAD). Los usuarios de Yammer pueden cambiar temporalmente sus perfiles de Yammer, pero estos cambios se sobrescriben cuando se produzca un cambio en AAD, por lo que debe ver y cambiar los datos en AAD. Vea [Administrar usuarios de Yammer en su ciclo de vida de Office 365](https://support.office.com/article/Manage-Yammer-users-across-their-life-cycle-from-Office-365-6c4c8fff-6444-404a-bffc-f9da0bcc3039) y [Agregar o cambiar la información de perfil de un usuario en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-users-profile-azure-portal).

-   Configuración del usuario:

- El usuario puede ver y cambiar su propia configuración. Para obtener información sobre cómo ver y modificar la configuración de usuario, vea [Cambiar la configuración de perfiles de Yammer](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851). Un administrador puede ver esta información y hacer capturas, pero no puede cambiarla. Vaya a configuración de Yammer \> **Usuarios**y, a continuación, haga clic en el nombre del usuario.<br/>
    - La pertenencia a grupos del usuario, mensajes marcados, usuarios seguidos y temas seguidos.
    
    - El usuario puede ver esta información. Para obtener información sobre cómo hacerlo, vea [Consejos para estar organizado en Yammer](https://support.office.com/article/tips-for-staying-organized-in-yammer-40ae9666-75c0-4254-a84c-d87a9542f380). Un administrador puede ver esta información y hacer capturas, pero no puede cambiarla. Vaya a configuración de Yammer \> **Usuarios**y, a continuación, haga clic en el nombre del usuario.

#### <a name="export"></a>Exportar
Consulte instrucciones sobre cómo exportar datos en [Administrar solicitudes de interesados RGPD en Yammer Enterprise](https://support.office.com/article/enterprise-privacy-yammer-eae49f12-4661-4ba5-aa72-01248f0709bf). Ejecute una exportación por usuario por cada red de Yammer a la que pertenezca el usuario.

Tenga en cuenta que Yammer tiene configuración de retención de datos que elimina temporalmente o definitivamente los datos cuando un usuario elimina un mensaje o archivo. Si está configurada la eliminación temporal, los datos eliminados por el usuario se incluirán en la exportación. Si la retención de datos de Yammer está configurada para la eliminación permanente, los datos eliminados ya no están almacenados en Yammer y no se incluirán en la exportación.

#### <a name="delete"></a>Eliminar
Yammer permite a los administradores superiores ejecutar una eliminación que cumpla con el RGPD a través del centro de administración de Yammer si reciben una solicitud de interesado. Esta opción se denomina Borrar usuario y suspende al usuario durante 14 días para, a continuación, eliminar todos sus datos personales, a excepción de sus archivos y mensajes. Si el usuario es un invitado, esto debe hacerse en cada red externa de la que sea miembro.

> [!NOTE]
> Si un administrador desea quitar los archivos y mensajes de los usuarios durante el intervalo de 14 días, tendrá que realizar una exportación de nivel de usuario para identificar los archivos y mensajes y, después, decidir cuáles va a eliminar mediante la eliminación integrada o un script de PowerShell. Después del plazo de 14 días, el administrador no puede asociar al usuario con sus archivos o mensajes.

Cuando se elimina un usuario con la opción Borrar usuario, se envía una notificación a la bandeja de entrada de Yammer de todos los administradores de red y administradores superiores.La opción Borrar usuario elimina el perfil de Yammer del usuario, pero no elimina su perfil de Office 365 o Azure Active Directory.

Para obtener pasos detallados para quitar un usuario, consulte [Administrar solicitudes de interesados sobre RGPD en Yammer Enterprise](https://support.office.com/article/enterprise-privacy-yammer-eae49f12-4661-4ba5-aa72-01248f0709bf).

## <a name="responding-to-dsr-rectification-requests"></a>Responder a solicitudes de interesado de corrección

Si un interesado solicita corregir los datos personales almacenados por su organización en Office 365, usted y su organización tendrán que determinar si es adecuado aceptar la solicitud. En caso afirmativo, rectificar los datos puede incluir realizar acciones como censurar, editar o quitar datos personales de un documento y otro tipo o elemento. Pedir al propietario del documento o de los datos que use la aplicación de Office 365 adecuada para realizar el cambio solicitado es la manera más conveniente. Una alternativa es que un administrador de TI de su organización realice los cambios. Esto probablemente requiere que el administrador de TI (u otra persona de su organización con los privilegios adecuados, como un administrador de colección de sitios SharePoint Online) se asigne a sí mismo o a otro usuario los permisos necesarios para obtener acceso al documento o a la ubicación del documento para realizar los cambios directamente en el mismo.

### <a name="requesting-that-the-data-owner-to-make-the-approved-change"></a>Solicitar que el propietario de datos realice el cambio aprobado
Pedir al propietario de los datos que realice el cambio es la forma más directa de rectificar datos personales. Después de encontrar los datos relevantes de la solicitud del interesado, puede proporcionar la siguiente información para que este pueda realizar el cambio.

-   La ubicación y el nombre de archivo (para documentos y otros archivos) del elemento que debe cambiarse; ubicar los datos en cuestión es parte del [proceso de detección](#using-content-search-to-find-personal-data) explicado anteriormente.

-   El cambio aprobado que debe realizar el propietario de los datos

Le recomendamos que implemente un proceso de confirmación en el que usted u otro individuo implicado en la investigación de la solicitud de interesado verifique que se ha realizado el cambio solicitado.

### <a name="gaining-access-to-a-sharepoint-online-site-or-onedrive-for-business-account-to-make-changes"></a>Obtener acceso a un sitio de SharePoint Online o cuenta de OneDrive para la Empresa para realizar cambios
Si no es posible para el propietario de los datos implementar la solicitud de rectificación del interesado, un administrador de TI o de SharePoint de su organización puede acceder a la ubicación del contenido y realizar los cambios requeridos. O puede asignarle a usted o a otro responsable de privacidad de datos los permisos necesarios.

#### <a name="sharepoint-online"></a>SharePoint Online

Para asignar permisos de administrador o de propietario a un sitio de SharePoint Online de modo que usted u otro individuo pueda acceder al documento y editarlo, vea

-   [Administrar los administradores de una colección de sitios](https://support.office.com/article/Manage-administrators-for-a-site-collection-9A7E46F9-3FC4-4297-955A-82CB292A5BE0)

-   [Editar y administrar los permisos para una lista o una biblioteca de SharePoint](https://support.office.com/article/Edit-and-manage-permissions-for-a-SharePoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782)

#### <a name="onedrive-for-business"></a>OneDrive para la Empresa

Un administrador global de Office 365 puede acceder a la cuenta de OneDrive para la Empresa de un usuario con el Centro de administración de Office 365.

1.  Inicie sesión con sus credenciales de administrador global en Office 365.

2.  Vaya al Centro de administración de Office 365.

3.  Vaya a **Usuarios activos** y seleccione el usuario.

4.  Expanda **Configuración de OneDrive para la Empresa** en el panel de detalles y, después, haga clic en **Acceder a archivos**.

5.  Haga clic en la dirección URL para ir a la cuenta de OneDrive para la Empresa del usuario.

### <a name="gaining-access-to-an-exchange-online-mailbox-to-make-changes-to-data"></a>Obtener acceso a un buzón de Exchange Online para realizar cambios en los datos

Un administrador global de Office 365 puede asignarse los permisos necesarios para abrir y modificar (o eliminar) elementos de buzón de otro usuario, como si fuera el propietario del buzón. También puede asignar permisos a otro usuario. En concreto, el administrador global debe agregar el permiso **Leer y administrar**, que es el permiso de acceso completo en Exchange Online. Para obtener más información, vea:

-   [Conceder permisos de buzón a otro usuario en Office 365](https://support.office.com/article/Give-mailbox-permissions-to-another-user-in-Office-365-Admin-Help-1DBCF12F-A9DE-4D1D-B0B3-A227F8A736D8)

-   [Obtener acceso al buzón de otra persona](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081)

Tenga en cuenta que, si el buzón del usuario se coloca en suspensión legal o se ha asignado a una directiva de retención, todas las versiones de un buzón se conservan hasta que expire el período de retención o de suspensión. Eso significa que, si los elementos del buzón se cambian en respuesta a la solicitud de interesado de corrección, una copia del elemento original (antes del cambio) se conserva y se almacena en una carpeta oculta en la carpeta Elementos recuperables del buzón del usuario.

### <a name="making-changes-to-content-in-onedrive-for-business-and-sharepoint-online"></a>Realizar cambios en el contenido en OneDrive para la Empresa y SharePoint Online

Los propietarios de datos o administradores de pueden realizar cambios en las páginas, listas y documentos de SharePoint Online. Tenga en cuenta lo siguiente a la hora de realizar cambios en contenido de SharePoint:

-   Actualizar un documento guardará una nueva versión del mismo que contendrá la revisión. Las versiones anteriores del documento no se actualizarán. Eso significa que es posible que los datos que sean el asunto de una solicitud de interesado de corrección pueden conservarse en las versiones anteriores del tema. Tenga en cuenta que las versiones anteriores de un tema pueden eliminarse y, a continuación, se quitan permanentemente de Office 365. Consulte la sección de esta guía [Eliminar documentos en SharePoint Online y OneDrive para la Empresa](#deleting-documents-in-sharepoint-online-and-onedrive-for-business).

-   Para censurar completamente un archivo de SharePoint de forma que quite todo rastro de los datos de un interesado del archivo, incluyendo todas las versiones del archivo y toda la actividad registrada realizada por el interesado, tendrá que hacer lo siguiente:

    1.  Descargue una copia del archivo en su equipo local.

    2.  Elimine permanentemente el archivo de SharePoint Online, eliminando el archivo y vaciando la Papelera de reciclaje de primer y segundo nivel. Consulte la sección de esta guía [Eliminar documentos en SharePoint Online y OneDrive para la Empresa](#deleting-documents-in-sharepoint-online-and-onedrive-for-business).

    3.  Haga las revisiones en la copia del documento en el equipo local.

    4.  Cargue el archivo revisado en la ubicación original de SharePoint Online.

-   Se pueden editar los datos en listas de SharePoint. Vea [Agregar, editar o eliminar elementos de lista](https://support.office.com/article/add-edit-or-delete-list-items-a4b31f53-f044-470e-9823-4526594bacde).

Los administradores de TI también pueden corregir algunas propiedades personales asociadas con un documento:

La información de usuario del perfil de usuario de SharePoint u Office 365 se asocia a menudo con documentos de OneDrive para la Empresa y SharePoint Online para representar a esa persona. Por ejemplo, un nombre de usuario creado por o modificado por la columna Contactos para un elemento de lista o documento. Esta información de usuario puede rectificarse de varias formas, según su origen:

-   Rectificar las propiedades de usuario en su propio Active Directory local. Los clientes que sincronicen las propiedades de usuario como nombre de usuario, Nombre de pila, etcétera... desde su AD local, deben modificar dichas propiedades ahí. Las propiedades asignadas correctamente se propagarán a Office 365 y de ahí a OneDrive para la Empresa y SharePoint Online.

-   Rectificar las propiedades de usuario en el Centro de administración de Office 365. Los cambios realizados a la información de la cuenta se reflejarán automáticamente en OneDrive para la Empresa y SharePoint Online. Para obtener más información, vea [Agregar o cambiar información de perfil de un usuario en Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=864809). Tenga en cuenta que las propiedades cuyo origen sea Office 365 no pueden cambiarse desde SharePoint.

-   Rectificar las propiedades de usuario en el perfil de usuario de SharePoint del Centro de administración de SharePoint. En la pestaña perfiles de usuario del Centro de administración de SharePoint, los administradores pueden hacer clic en **Administrar perfiles de usuario** y buscar las propiedades de un usuario para editarlas.

-   Rectificar las propiedades de usuario en un origen personalizado. Las propiedades de perfil de SharePoint personalizadas pueden sincronizarse desde un origen personalizado a través de Microsoft Identity Manager (MIM) u otro método.

Tenga en cuenta que esto no afectará a todas las experiencias, que pueden conservar la información anterior. Por ejemplo, el nombre del usuario como texto en el documento.

### <a name="making-changes-to-content-in-power-bi"></a>Realizar cambios en el contenido de Power BI
Power BI depende de datos de origen subyacentes usados en sus paneles e informes para ser completos y precisos, por lo que corregir las imprecisiones de los datos de origen debe hacerse aquí. Por ejemplo, si crea un informe de Power BI conectado a Dynamics 365 for Sales como origen de datos dinámico, tendrá que realizar cualquier corrección de datos en Dynamics 365 for Sales.

Después de realizar esos cambios, puede aprovechar la capacidad de [actualización de datos programada](https://docs.microsoft.com/power-bi/refresh-scheduled-refresh) para actualizar el conjunto de datos que se almacena en Power BI, de modo que los datos revisados se reflejen en los recursos dependientes de Power BI. Para ayudar a cumplir los requisitos del RGPD, debe tener directivas para garantizar que va a actualizar los datos al ritmo adecuado.

### <a name="making-changes-to-content-in-yammer"></a>Realizar cambios en el contenido de Yammer

Para los mensajes, un usuario puede modificar un mensaje para rectificar cualquier inexactitud. Puede solicitar una lista de todos sus mensajes a un administrador superior de Yammer y, a continuación, hacer clic en un vínculo en el archivo para revisar cada mensaje.

Para los archivos, un usuario puede modificar un archivo concreto para rectificar cualquier imprecisión. Puede solicitar una lista de todos los archivos registrados a un administrador superior de Yammer y acceder a ellos. Los archivos que se exportan a la carpeta de archivos pueden verse, solo hay que buscar el archivo por número. Por ejemplo, para un archivo denominado 12345678.ppx en la exportación, use el cuadro de búsqueda en Yammer para buscar 1235678.ppx. O bien, vaya a <strong>https://www.yammer.com/\<network\_name\>/\#/files/\<file\_number\></strong>; por ejemplo, <strong>https://www.yammer.com/contosomkt.onmicrosoft.com/\#/files/12345678</strong>.

Para los datos a los que el usuario puede acceder a través de su perfil y configuración, es posible realizar todos los cambios necesarios.

-   El perfil del usuario:

    - Si el usuario tiene una identidad de Yammer, tiene control total de su perfil. Para obtener información sobre cómo ver y modificar el perfil, vea [Cambiar la configuración de perfiles de Yammer](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851).

    - Si el usuario tiene una identidad de Office 365, el perfil de usuario de Yammer se extrae automáticamente de Office 365, que obtiene la información de perfil de Azure Active Directory (AAD). Los usuarios de Yammer pueden cambiar temporalmente sus perfiles de Yammer, pero estos cambios se sobrescriben cuando se produzca un cambio en AAD, por lo que el mejor sitio para ver y cambiar los datos es AAD. El usuario necesitará solicitar la actualización de AAD. Vea [Administrar usuarios de Yammer en su ciclo de vida de Office 365](https://support.office.com/article/Manage-Yammer-users-across-their-life-cycle-from-Office-365-6c4c8fff-6444-404a-bffc-f9da0bcc3039) y [Agregar o cambiar la información de perfil de un usuario en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-users-profile-azure-portal).

-   Configuración del usuario:
    
    - El usuario puede cambiar su propia configuración. Para obtener información sobre cómo ver y modificar la configuración de usuario, vea [Cambiar la configuración de perfiles de Yammer](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851).

    - La pertenencia a grupos del usuario, mensajes marcados, usuarios seguidos y temas seguidos. El usuario puede cambiar esta información; vea [Sugerencias para organizarse en Yammer](https://support.office.com/article/tips-for-staying-organized-in-yammer-40ae9666-75c0-4254-a84c-d87a9542f380).

## <a name="responding-to-dsr-restriction-requests"></a>Responder a solicitudes de restricción de DSR

Estas son las formas de restringir el tratamiento de datos en Office 365:

- Quitar una licencia de aplicación para evitar que los usuarios tengan acceso a los datos a través de una aplicación de Office 365

- Impedir que los usuarios tengan acceso a su cuenta de OneDrive para la Empresa

- Desactivar el tratamiento de datos de un servicio de Office 365

- Quitar los datos de SharePoint Online y OneDrive para la Empresa temporalmente y conservarlos locales

- Impedir temporalmente el acceso a un sitio de SharePoint Online

- Impedir que un usuario inicie sesión en Office 365

Si su organización más adelante determina que ya no se aplica una restricción, puede terminar la restricción invirtiendo los pasos que realizó para realizarla. Por ejemplo, volver a asignar licencias, volver a activar un servicio o permitir al usuario iniciar sesión en Office 365.

### <a name="removing-the-license-for-an-office-365-application"></a>Quitar la licencia para una aplicación de Office 365

Como se ha explicado anteriormente, las licencias para todas las aplicaciones de Office 365 que se incluyen en la suscripción de Office 365 de su organización están asignadas a todos los usuarios de forma predeterminada. Si es necesario restringir el acceso a los datos sujetos a una solicitud de interesado, un administrador de TI puede usar el Portal de administración de Office 365 para desactivar temporalmente la licencia de un usuario en una aplicación. Si un usuario, a continuación, intenta usar esa aplicación, recibirá una notificación de producto sin licencia o un mensaje que indica que no tiene acceso. Para obtener más información, vea [Quitar licencias de usuarios en Office 365 para empresas](https://support.office.com/article/Remove-licenses-from-users-in-Office-365-for-business-9B497C85-D0A4-4735-80FA-D3565BC05BD1).

**Notas**:

- Para impedir que un usuario acceda a Yammer, primero debe [obligar a Office 365 a identificar a un usuario de Yammer](https://support.office.com/article/Enforce-office-365-identity-for-Yammer-users-008f940b-6bec-47fc-bcc6-9c6133467562) y, después, quitar la licencia del usuario Yammer.

- En los escenarios que aprovechan Power BI, puede restringir el acceso a la aplicación de proveedor (ISV) de software independientes incrustado en el contenido.

### <a name="preventing-users-from-accessing-their-onedrive-for-business-account"></a>Impedir que los usuarios tengan acceso a su cuenta de OneDrive para la Empresa

Quitar una licencia de usuario SharePoint Online no evitar que tengan acceso a su cuenta de OneDrive para la Empresa si esta ya existe. Debe quitar los permisos de usuario a su cuenta de OneDrive para la Empresa. Puede hacer esto quitando el usuario como propietario de una colección de sitios de su cuenta de OneDrive para la Empresa. En concreto, tendrá que quitar el usuario de los grupos Administrador de colección de sitios primaria y Administrador de colección de sitios en su perfil de usuario. Consulte la sección "Agregar y quitar administradores en una cuenta de OneDrive para empresa" en [Administrar perfiles de usuario en el Centro de administración de SharePoint](https://support.office.com/article/Manage-user-profiles-in-the-SharePoint-admin-center-494bec9c-6654-41f0-920f-f7f937ea9723).

### <a name="turning-off-an-office-365-service"></a>Desactivar un servicio de Office 365

Otra forma de lidiar con una solicitud de interesado para restringir el tratamiento de datos es apagar un servicio de Office 365. Por supuesto, esto afectará a todos los usuarios de su organización y evitará que todos usen el servicio o accedan a sus datos.

La manera más conveniente de desactivar un servicio es usar PowerShell de Office 365 y eliminar la licencia de usuario correspondiente de todos los usuarios de la organización. Esto restringirá el acceso a los datos de cualquiera que use ese servicio. Para obtener instrucciones detalladas, vea [Desactivar el acceso a servicios con PowerShell de Office 365](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) y siga los procedimientos para desactivar servicios de Office 365 para usuarios con un plan de licencia única.

> [!NOTE]
> Para Yammer, además de quitar la licencia de Yammer de las cuentas de usuario, también debe deshabilitar la capacidad de los usuarios de iniciar sesión con sus credenciales de Yammer (obligándoles a usar sus credenciales de Office 365 para iniciar sesión). Para obtener instrucciones detalladas, vea [Desactivar el acceso de Yammer para usuarios de Office 365](https://support.office.com/article/Turn-off-Yammer-access-for-Office-365-users-1f79bfad-f713-4143-aa5d-5584985ce53a).

### <a name="temporarily-removing-data-from-sharepoint-online-or-onedrive-for-business-sites"></a>Eliminar temporalmente los datos de SharePoint Online o de OneDrive para la Empresa

Otra forma de restringir el tratamiento de datos personales es quitarlos temporalmente de Office 365 en respuesta a una solicitud de interesado. Cuando su organización determine que ya no se aplica la restricción, puede volver a importar los datos a Office 365.

Como la mayoría de los documentos de Office se encuentra en los sitios de SharePoint Online o OneDrive para la Empresa, eliminar documentos y luego volver a importarlos es un proceso de alto nivel.

1.  Obtenga una copia del documento sujeto a la petición de restricción. Tendrá que solicitar el acceso al sitio, preguntar al administrador global de Office 365 o a un administrador de colección de sitios para conseguirla.

2.  Almacene el documento en una ubicación local (por ejemplo, un servidor de archivos o un recurso compartido de archivos) o en otra ubicación que distinta al inquilino de Office 365 en la nube de Microsoft.

3.  Elimine permanentemente el documento original (Purgar) de Office 365. Esto es un proceso de tres pasos:

    a. Elimine la copia original del documento. Al eliminar un documento de un sitio, se envía a la Papelera de reciclaje del sitio (también denominada *Papelera de reciclaje de primer nivel*).

    b. Vaya a la Papelera de reciclaje y elimine la copia del documento. Al eliminar un documento de la Papelera de reciclaje, se envía a la Papelera de reciclaje de la colección de sitios (también denominada *Papelera de reciclaje de segundo nivel*). Vea [Eliminar un archivo, carpeta o vínculo de una biblioteca de documentos de SharePoint](https://support.office.com/article/Delete-a-file-folder-or-link-from-a-SharePoint-document-library-71f3c90a-0d24-4d80-8b66-f88234b79a52).

    c. Vaya a la Papelera de reciclaje de la colección de sitios y elimine la copia del documento permanentemente de Office 365. Vea [Eliminar elementos de la Papelera de reciclaje de la colección de sitios](https://support.office.com/article/Delete-items-from-the-site-collection-Recycle-Bin-dd5c00c2-aef6-4458-9d04-80b185077653).

4.  Cuando ya no se aplique la restricción, la copia del documento que se almacenó localmente puede volver a cargarse en el sitio de Office 365.

> [!IMPORTANT] 
> El procedimiento anterior no funcionará si el documento se encuentra en un sitio que está suspendido (con una de las características de suspensión legal o de retención de Office 365). En caso de que una solicitud de restricción para una DSR tenga prioridad sobre una suspensión legal, tendrá que quitarse la suspensión del sitio antes de que un documento pueda eliminarse definitivamente. Además, el historial de los documentos eliminados se elimina definitivamente.

### <a name="temporarily-restricting-access-to-sharepoint-online-sites"></a>Restringir temporalmente el acceso a sitios de SharePoint Online

Un administrador de SharePoint Online puede impedir temporalmente que todos los usuarios tengan acceso a una colección de sitios de SharePoint Online mediante el bloqueo de la misma (con el comando de PowerShell de SharePoint Online **Set-SPOSite - LockState**). Esto evitará que los usuarios tengan acceso a la colección de sitios y cualquier contenido o datos que se encuentren en ella. Si después decide permitir el acceso al sitio a los usuarios, el administrador puede desbloquear el sitio. Vea [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) para obtener información sobre cómo ejecutar este cmdlet de PowerShell.

### <a name="preventing-a-user-from-signing-in-to-office-365"></a>Impedir que un usuario inicie sesión en Office 365

Un administrador de TI también puede impedir que un usuario inicie sesión en Office 365, lo que debería impedir que obtenga acceso a los servicios online de Office 365 o que procese los datos almacenados en Office 365. Vea [Bloquear el acceso de un antiguo empleado a los datos de Office 365](https://support.office.com/article/Remove-a-former-employee-from-Office-365-44d96212-4d90-4027-9aa9-a95eddb367d1).

## <a name="part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365"></a>Parte 2: Responder a solicitudes del interesado con respecto a la información generada por Office 365

El conjunto de aplicaciones de Microsoft incluye servicios online de Office 365 que ofrecen información a los usuarios y a las organizaciones que los usan.
- Delve y MyAnalytics ofrecen información a usuarios individuales

- Workplace Analytics proporciona información a las organizaciones.

Estos servicios se describen en las secciones siguientes.

### <a name="delve"></a>Delve

En Delve, los usuarios pueden administrar su perfil de Office 365 y encontrar contactos y documentos que pueden resultarles relevantes. Los usuarios solo pueden ver los documentos a los que tienen acceso. Para una serie de artículos útiles sobre Delve, consulte [Office Delve](https://support.office.com/article/What-is-Office-Delve-1315665a-c6af-4409-a28d-49f8916878ca).

#### <a name="access-and-export"></a>Acceder y exportar

Los administradores no pueden exportar o acceder a los datos de los usuarios Delve. Esto significa que los usuarios deben acceder a los datos de Delve y exportarlos ellos mismos. Pueden acceder a la mayoría de tipos de datos y exportarlos directamente desde Delve, pero algunos solo están disponibles a través de otros servicios.

##### <a name="data-available-in-the-delve-user-interface"></a>Datos disponibles en la interfaz de usuario de Delve

-   **Datos de perfil**: esta es la información de perfil de la lista global de direcciones de su organización en Azure Active Directory, así como la información opcional que los usuarios han decidido agregar sobre sí mismos. Para obtener acceso o exportar los datos de perfil en Delve, un usuario puede hacer clic en **Yo** \> **Actualizar perfil**. Se puede copiar el contenido directamente desde la página o realizar una captura de pantalla.

-   **Datos de blog**: se trata de entradas de blog publicadas por un usuario. Para acceder a datos de blog o exportarlos, un usuario puede hacer clic en **Yo** \> **Todas las entradas**. Se puede copiar el contenido directamente desde la página o realizar una captura de pantalla.

-   **Datos de contactos recientes**: estos son los usuarios de la organización que Delve considera relevantes para el usuario en un momento determinado. Cuando un usuario hace clic en **Yo** \> **Ver todo** en el panel "Haga clic en una persona para ver en qué está trabajando", Delve muestra las personas más relevantes para un usuario en un momento determinado.

##### <a name="data-available-through-an-export-link-in-delve"></a>Datos disponibles a través de un vínculo de exportación de Delve

- **Datos de lista de usuarios**: Estas son las personas que el usuario ha visto en Delve. La lista de **Usuarios** se muestra en el panel izquierdo de la página principal. Los usuarios pueden exportar la lista de los contactos que han visto recientemente en Delve.

- **Datos de favoritos**: estos son los paneles y los documentos que el usuario ha marcado como sus favoritos. La página **Favoritos** muestra los paneles y los documentos que el usuario ha agregado a sus favoritos. Los usuarios pueden exportar una lista de sus paneles favoritos actuales y los documentos.

- **Datos de configuración de la característica**: estas son las configuraciones o acciones de Delve resultantes de la utilización de Delve por parte de un usuario. Los usuarios pueden exportar una lista completa de esta configuración. 

Para acceder a los datos anteriores o exportarlos, el usuario puede hacer clic en el icono de engranaje de la esquina superior derecha de Delve y luego hacer clic en **Configuración de la característica** > **Exportar datos**. La información se exporta en formato JSON.

##### <a name="data-thats-available-through-other-services"></a>Datos disponibles a través de otros servicios

-   **Datos de documentos populares**: estos son documentos y datos adjuntos de correo electrónico que pueden ser relevantes para el usuario. Delve organiza de forma dinámica estos documentos y mensajes de correo electrónico en función de las actividades y los contactos del usuario en Office 365. Cuando un usuario abre Delve o hace clic en **Inicio**, Delve muestra los documentos o datos adjuntos más relevantes para el usuario en un momento determinado. Para acceder a los documentos y los datos adjuntos o exportarlos, el usuario puede ir al servicio de Office 365 a través del cual se publican los documentos o los datos adjuntos (como Office.com, SharePoint Online, OneDrive para la Empresa y Exchange Online).

-   **Datos de documentos recientes y datos adjuntos de correo**: estos son los documentos y datos adjuntos de correo electrónico que el usuario ha modificado más recientemente. Cuando un usuario hace clic en **Yo** \> **Ver todo** en el panel "Volver a los documentos y datos adjuntos de correo electrónico más recientes", Delve muestra los últimos documentos y datos adjuntos de correo electrónico modificados por el usuario.  Para acceder a los documentos y los datos adjuntos o exportarlos, el usuario puede ir al servicio de Office 365 a través del cual se publican los documentos o los datos adjuntos como, por ejemplo, Office.com, SharePoint Online, OneDrive para la Empresa y Exchange Online.

-   **Datos de documentos de usuarios de su entorno**: estos son los documentos que Delve considera que son más relevantes para el usuario en un momento determinado. Cuando un usuario hace clic en **Yo** \> **Ver todo** en el panel "Descubrir documentos de usuarios de su entorno", Delve muestra los documentos más relevantes para un usuario en un momento determinado. Para acceder a los documentos o exportarlos, el usuario puede ir al servicio de Office 365 a través del cual se publican los documentos o los datos adjuntos (como Office.com, SharePoint Online, OneDrive para la Empresa y Exchange Online).

#### <a name="rectify"></a>Rectificar

Los usuarios pueden modificar la siguiente información en Delve:

-   **Información de perfil**: un usuario puede hacer clic en **Yo** \> **Actualizar perfil** para actualizar su información. Dependiendo la configuración de su organización en la lista global de direcciones, los usuarios no podrán modificar toda su información de perfil, como el nombre o el puesto de trabajo.

-   **Configuración de características**: un usuario puede hacer clic en el icono de engranaje en la esquina superior derecha de Delve y después hacer clic en **Configuración de características**\> para cambiar la configuración que desee.

#### <a name="restrict"></a>Restringir

Para restringir el tratamiento de Delve en su organización, puede desactivar Office Graph. Más [aquí](https://support.office.com/article/office-delve-for-office-365-admins-54f87a42-15a4-44b4-9df0-d36287d9531b#bkmk_delveonoff).

#### <a name="delete"></a>Eliminar

Los usuarios pueden eliminar la siguiente información en Delve:

-   **Información de perfil**: para eliminar la información de perfil, un usuario puede hacer clic en **Yo** \> **Actualizar perfil** y eliminar el texto que desee. Dependiendo de la configuración de su organización en la lista global de direcciones, los usuarios no podrán eliminar toda su información de perfil, como el nombre o el puesto de trabajo.

-   **Documentos y datos adjuntos de correo electrónico**: para eliminar un documento o datos adjuntos, los usuarios deben ir al servicio donde estén almacenados el documento o los datos adjuntos (por ejemplo, SharePoint Online, OneDrive para la Empresa o Exchange Online) y eliminar allí el documento o los datos adjuntos.

### <a name="myanalytics"></a>MyAnalytics

MyAnalytics proporciona estadísticas a los usuarios para ayudarles a comprender cómo invierten su tiempo en el trabajo. Para ayudar a los usuarios a comprender mejor los datos que se muestran en el panel personal y cómo se calculan estos, recomiende a los usuarios el tema de ayuda [Panel personal de MyAnalytics](https://docs.microsoft.com/workplace-analytics/myanalytics/use/dashboard).

#### <a name="access-and-export"></a>Obtener acceso y exportar
Si la organización usa MyAnalytics, Microsoft genera información de todos los usuarios (tengan o no una licencia de usuario de MyAnalytics) para ofrecer resultados significativos a los usuarios con licencia. Toda la información de MyAnalytics se deriva de los encabezados de reunión y correo electrónico del buzón del usuario. Microsoft le ofrece la posibilidad de exportar los datos que MyAnalytics usa para generar esta información mediante la herramienta de casos de DSR del Centro de seguridad y cumplimiento. Para obtener instrucciones detalladas, vea [Exportar datos de MyAnalytics y el servicio de Roaming de Office](https://docs.microsoft.com/office365/securitycompliance/manage-gdpr-data-subject-requests-with-the-dsr-case-tool#exporting-data-from-myanalytics-and-the-office-roaming-service).

Además de la información que puede exportarse mediante el Centro de seguridad y cumplimiento, los usuarios con licencia de MyAnalytics pueden ir al [panel MyAnalytics](https://delve.office.com) cuando hayan iniciado sesión en su cuenta de Office 365 para ver la información que se genera sobre la forma en que invierten el tiempo en el trabajo. Pueden realizar capturas de pantalla de la información de MyAnalytics si quieren tener copias permanentes de sus datos.


#### <a name="rectify"></a>Rectificar

Todas las conclusiones generadas por MyAnalytics proceden de los elementos de calendario y el correo del usuario. Por lo tanto, no hay nada para rectificar excepto los elementos de calendario o correo electrónico de origen.

#### <a name="restrict"></a>Restringir

Para restringir el tratamiento de un usuario específico, puede expulsarlo de MyAnalytics. Para ver cómo hacerlo, consulte [Configurar ajustes de usuario de MyAnalytics](https://docs.microsoft.com/workplace-analytics/myanalytics/setup/configure-mya-user-settings).

#### <a name="delete"></a>Eliminar

Todo el contenido del buzón, incluidos los datos de MyAnalytics, se purga cuando una cuenta de usuario se "elimina de forma permanente" de Active Directory. Para más información, vea la sección [Eliminar un usuario](#deleting-a-user) de esta guía.

### <a name="workplace-analytics"></a>Workplace Analytics

Workplace Analytics permite a las organizaciones aumentar los datos de Office 365 con sus propios datos empresariales para obtener información sobre el compromiso de los empleados, patrones de colaboración y productividad de la organización. [Este artículo](https://docs.microsoft.com/workplace-analytics/overview/privacy-and-data-access) explica el control que su organización tiene los datos que trata Workplace Analytics y quién tiene acceso a ellos.

Para ayudarle con las solicitudes del interesado en Workplace Analytics: 

1. Determine si la organización usa Workplace Analytics. Para más información, vea [Asignar licencias a usuarios en Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users). Si la organización no usa Workplace Analytics, no hay ninguna otra acción.

2. Si la organización usa Workplace Analytics, compruebe a qué usuario de la organización se le ha asignado el rol de administrador de Workplace Analytics. También debe determinar si el buzón del interesado tiene licencia de Workplace Analytics. Si es necesario, pida al administrador de Workplace Analytics que se ponga en contacto con el Soporte técnico de Microsoft para administrar las siguientes solicitudes del interesado. 

#### <a name="access-and-export"></a>Obtener acceso y exportar

Puede que la información de los informes de Workplace Analytics creados por usted contengan o no datos personales de usuarios de la organización con licencia de Workplace Analytics, según la información que haya usado la organización para complementar los datos de Office 365. El administrador de Workplace Analytics deberá revisar esos informes para determinar si contienen datos personales del usuario. Si un informe contiene datos personales de un usuario, usted tendrá que decidir si quiere proporcionarle una copia del informe. Workplace Analytics permite exportar el informe. 

#### <a name="rectify"></a>Rectificar

Como se ha explicado anteriormente, Workplace Analytics usa datos de Office 365 junto con otros proporcionados por la organización para generar informes que le interesen. Los datos de Office 365 no se pueden corregir, se basan en las actividades del calendario y el correo electrónico de los usuarios. Pero los datos de la organización que haya cargado en Workplace Analytics se pueden corregir para generar el informe. Para ello, tiene que corregir los datos de origen, cargarlos y volver a ejecutar el informe para generar un nuevo informe de Workplace Analytics.

#### <a name="restrict"></a>Restringir
Para restringir el tratamiento de un usuario específico, puede quitar su licencia de Workplace Analytics.

#### <a name="delete"></a>Eliminar
Si un interesado quiere que se le quite de un informe o conjunto de informes de Workplace Analytics, puede eliminar el informe. Es su responsabilidad eliminar los usuarios de los datos de la organización que use para generar el informe y volver a cargar los datos. Todos los datos sobre el usuario se quitan cuando se "elimina de forma permanente" una cuenta de usuario de Azure Active Directory. 

Para quitar los datos personales de un interesado, un administrador global de Office 365 puede realizar lo siguiente: 

1. Eliminar la licencia de Workplace Analytics del interesado.

2. Eliminar la entrada de Azure Active Directory (AAD) para el interesado. (Para obtener más información, vea [Eliminar un usuario](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory#delete-a-user).)

3. Póngase en contacto con el soporte técnico y haga que el soporte abra un vale de una solicitud de eliminación de usuario de Derechos del interesado (DSR). En este vale, identifique al interesado mediante su nombre principal de usuario (UPN).

4. Exporte una copia de los datos de recursos humanos del sistema de recursos humanos de la empresa (vea [Exportar datos](https://docs.microsoft.com/workplace-analytics/setup/prepare-organizational-data#step-three--export-data)), quite la información del interesado de ese archivo de datos de recursos humanos y después cargue el archivo de datos de recursos humanos editado en formato .csv en Workplace Analytics (vea [Cargar datos de la organización](https://docs.microsoft.com/workplace-analytics/setup/upload-organizational-data)).

## <a name="part-3-responding-to-dsrs-for-system-generated-logs"></a>Parte 3: Responder a solicitudes de derechos del interesado sobre registros generados por el sistema

Microsoft también le permite acceder a registros generados por el sistema, exportarlos y eliminarlos, que pueden considerarse como datos personales según la definición amplia del RGPD de “datos personales”. Estos son algunos ejemplos de registros generados por el sistema que pueden considerarse como datos personales según el RGPD:

-   Datos de uso del servicio de productos, como registros de actividad de usuario.

-   Solicitudes de búsqueda de usuarios y datos de consultas.

-   Los datos generados por productos y servicios como resultado del funcionamiento del sistema y la interacción por los usuarios u otros sistemas.

No se admite la capacidad de restringir o rectificar datos en los registros generados por el sistema. Los registros generados por el sistema constituyen acciones realizadas en la nube de Microsoft y datos de diagnóstico, y modificar este tipo de datos podría afectar a los registros históricos de acciones, lo que aumentaría el fraude y los riesgos de seguridad.

### <a name="accessing-and-exporting-system-generated-logs"></a>Acceder a registros generados por el sistema y exportarlos

Los administradores pueden obtener acceso a registros generados por el sistema asociados con el uso de un usuario específico de las aplicaciones y servicios de Office 365. Para obtener acceso y exportar los registros generados por el sistema:

1.  Vaya al [Portal de confianza de servicios de Microsoft](https://servicetrust.microsoft.com/) e inicie sesión con las credenciales de un administrador global de Office 365.

2.  En la lista desplegable **Privacidad** de la parte superior de la página, haga clic en **Solicitud del interesado**.

3.  En la página **Solicitud del interesado**, en **Registros generados por el sistema**, haga clic en **Exportación de registros de datos**.

    Se mostrará la pantalla **Exportación de registros de datos**. Se mostrará una lista de las solicitudes de datos de exportación enviadas por su organización.

4.  Para crear una solicitud para usuario, haga clic en **Crear solicitud de exportación de datos**.

Después de crear una solicitud, se mostrará en la página **Exportación de registros de datos**, donde puede realizar un seguimiento de su estado. Después de completar una solicitud, puede hacer clic en un vínculo para obtener acceso a los registros generados por el sistema, que se exportarán a la ubicación de Azure Storage de su organización en un plazo de 30 días después de crear la solicitud. Los datos se guardarán en formatos de archivo de lectura mecánica comunes, como JSON o XML. Si no tiene una cuenta de Azure ni una ubicación de Azure Storage, tendrá que crear una cuenta de Azure o una ubicación de Azure Storage para su organización para que la herramienta Exportación de registros de datos pueda exportar los registros generados por el sistema. Para más información, vea [Introducción a Azure Storage](https://docs.microsoft.com/azure/storage/common/storage-introduction).

> [!NOTE]
> Al crear una solicitud de exportación de datos, los datos generados por el sistema para algunas aplicaciones no se exportarán mediante la herramienta Exportación de registros de datos. Para exportar datos de estas aplicaciones, vea [Pasos adicionales para exportar datos de registros generados por el sistema](https://docs.microsoft.com/microsoft-365/compliance/gdpr-system-generated-log-data).

Este es un resumen de las acciones de acceso y exportación de registros generados por el sistema con la herramienta Exportación de registros de datos:

  - **¿Cuánto tarda la herramienta Exportación de registros de datos de Microsoft en completar una solicitud? ** Esto depende de varios factores. En la mayoría de los casos debe completarse en uno o dos días, pero puede tardar hasta 30 días.

  - **¿Qué formato tendrá el resultado?** El resultado serán archivos con formato de lectura mecánica estructurados, como XML, CSV o JSON.

- **¿Quién tiene acceso a la herramienta Exportación de registros de datos para enviar solicitudes de acceso de registros generados por el sistema?** Los administradores globales de Office 365 tendrán acceso a la utilidad Administrador de registros del RGPD.

- **¿Qué datos devuelve la herramienta Exportación de registros de datos?** La herramienta Exportación de registros de datos devuelve registros generados por el sistema que Microsoft almacena. Los datos exportados abarcan varios servicios Microsoft, como Office 365, Azure y Dynamics.

- **¿Cómo se devuelven los datos al usuario?** Los datos se exportarán a la ubicación de Azure Storage de su organización; los administradores de la organización tendrán que determinar cómo mostrarán o enviarán estos datos a los usuarios.

- **¿Cuál será la apariencia de los datos en los registros generados por el sistema?** Ejemplo de una entrada de registro generado por el sistema en formato JSON:


   ```
   [{
            "DateTime": "2017-04-28T12:09:29-07:00",

             "AppName": "SharePoint",

             "Action": "OpenFile",

             "IP": "154.192.13.131",

             "DevicePlatform": "Windows 1.0.1607"
   }]
   ```

> [!NOTE]
> Algunas características no permiten exportar ni eliminar los registros generados por el sistema con información personal para mantener la integridad de dicha información con fines de seguridad y auditoría.

También se pueden recuperar datos de uso de productos y servicios de algunos de los servicios de Microsoft utilizados con más frecuencia, como Exchange Online, SharePoint Online, Skype Empresarial, Yammer y Grupos de Office 365, buscando en el registro de auditoría de Office 365 del Centro de seguridad y cumplimiento. Para más información, vea [Use the Office 365 audit log search tool in DSR investigations](#use-the-office-365-audit-log-search-tool-in-dsr-investigations) (Usar la herramienta de búsqueda de registro de auditoría de Office 365 en investigaciones de DSR) en el Apéndice A. El uso del registro de auditoría puede ser de interés para usted, puesto que es posible asignar permisos a otras personas de la organización (como, por ejemplo, el responsable de cumplimiento normativo) para buscar en el registro de auditoría a fin de tener acceso a estos datos.

#### <a name="national-clouds"></a>Nubes nacionales
En las siguientes nubes nacionales, un administrador de TI global tendrá que realizar este procedimiento para exportar registros de datos generados por el sistema:

- Office 365 Alemania: [Visite el Portal de confianza del servicio Microsoft de Alemania](https://aka.ms/MicrosoftSTPGermany) y siga los pasos descritos anteriormente.

- Office 365 Administración pública de EE. UU.: [vaya al Portal de administración de Office 365](https://portal.office365.us) y envíe una solicitud al Soporte técnico de Microsoft.

- Office 365 ofrecido por 21Vianet (China): [vaya al Portal de administración de Office 365 operado por 21Vianet](https://portal.partner.microsoftonline.cn/AdminPortal/Home#/homepage) y después a **Comercio** > **Suscripción** > **Privacidad** > **RGPD** y escriba la información necesaria.

### <a name="deleting-system-generated-logs"></a>Eliminar registros generados por el sistema
Para eliminar los registros generados por el sistema recuperados con una solicitud de acceso, tiene que quitar el usuario del servicio y eliminar permanentemente su cuenta de Azure Active Directory. Para obtener instrucciones sobre cómo eliminar un usuario de forma permanente, vea la sección [Eliminar un usuario](#deleting-a-user) en esta guía. Es importante tener en cuenta que la eliminación permanente de una cuenta de usuario es irreversible una vez iniciada.

La eliminación permanente de una cuenta de usuario quitará los datos del usuario de los registros generados por el sistema de casi todos los servicios de Office 365 en menos de 30 días. Una excepción a esto es la eliminación permanente de la cuenta de usuario de Exchange Online, que tarda más de 30 días. Debido a la naturaleza crítica del contenido de Exchange Online y para evitar la pérdida accidental de datos, este sistema se ha diseñado para colocar intencionadamente los datos en un estado de suspensión hasta 60 días después de la eliminación permanente de una cuenta de usuario. Para eliminar definitivamente los datos de Exchange Online de un usuario en un plazo de 30 días, elimine definitivamente la cuenta de usuario en Azure Active Directory y luego contacte con el [soporte técnico de Microsoft](https://support.microsoft.com/) y pida que los datos de Exchange Online del usuario se quiten manualmente del proceso de eliminación programado. Para más información, vea [Quitar datos de Exchange Online](#removing-exchange-online-data), que ya se explicó anteriormente en esta guía.

La eliminación de una cuenta de usuario no quitará los registros generados por los sistemas de Yammer y Kaizala. Para quitar los datos de estas aplicaciones, vea uno de los siguientes:

- Yammer: [administrar las solicitudes del interesado sobre RGDP en Yammer Enterprise](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)
- Kaizala:[exportar o eliminar datos de la organización de un usuario en Kaizala](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)

#### <a name="national-clouds"></a>Nubes nacionales

En las siguientes nubes nacionales, un administrador de TI global tendrá que realizar este procedimiento para eliminar registros generados por el sistema:

- Office 365 Alemania: cuando la cuenta de usuario se elimina definitivamente, también se eliminarán los registros generados por el sistema. 

- Office 365 Administración pública de EE. UU.: envíe una solicitud al Soporte técnico de Microsoft a través del [Portal de administración de Office 365](http://portal.office365.us).

- Office 365 ofrecido por 21Vianet (China): envíe una solicitud al Soporte técnico de Microsoft a través del Portal de administración de Office 365 en esta dirección [URL](https://portal.partner.microsoftonline.cn/AdminPortal/Home#/homepage). Vaya a **Comercio** y seleccione **Suscripción** -> **Privacidad** -> **RGPD** y escriba la información necesaria.

## <a name="part-4-additional-resources-to-assist-you-with-dsrs"></a>Parte 4: Recursos adicionales para ayudarle con las solicitudes del interesado

### <a name="dsr-guides-for-other-microsoft-enterprise-services"></a>Guías de solicitudes de interesados para otros servicios empresariales de Microsoft

Esta guía está dedicada al tema sobre cómo buscar y actuar sobre datos personales para responder a una solicitud de interesado al usar productos, servicios y herramientas administrativas de Office 365. Vaya al [Portal de confianza del servicio de Microsoft](https://servicetrust.microsoft.com/) para tener acceso a guías similares de otros servicios empresariales de Microsoft.

### <a name="microsoft-support"></a>Soporte técnico de Microsoft
Los "datos de soporte" son aquellos que sus usuarios y usted envían a Microsoft cuando interactúan con Microsoft para recibir soporte técnico relacionado con Office 365 u otros productos y servicios de Microsoft (por ejemplo, para solucionar problemas de comportamiento inesperado del producto). Algunos de estos datos pueden contener datos personales. Para más información, vea [Solicitudes del interesado de soporte técnico y los servicios profesionales de Microsoft para el RGPD](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-prof-services).

### <a name="product-and-services-authenticated-with-an-org-id-for-which-microsoft-is-a-data-controller"></a>Productos y servicios autenticados con el identificador de una organización en la que Microsoft es responsable de los datos

En las tres primeras partes de esta guía se describen productos y servicios en los que Microsoft es encargado del tratamiento de los datos de la organización y, por tanto, se pone la funcionalidad de solicitudes del interesado a disposición del administrador de inquilinos. Hay diversas circunstancias en las que los usuarios de la organización puedan usar su cuenta profesional o educativa (también denominadas "identificador de Azure Active Directory" o "AAD") para iniciar sesión en los productos y servicios de Microsoft en los que Microsoft es el responsable de los datos. En dichos productos y servicios, los usuarios tendrán que iniciar sus propias solicitudes del interesado directamente en Microsoft y Microsoft tratará las solicitudes directamente con el usuario. Tenga en cuenta que los productos y servicios relacionados con el almacenamiento de contenido creado por los usuarios permiten a los usuarios tener acceso, exportar, corregir y eliminar este contenido como parte de su funcionalidad intrínseca. Los escenarios en lo que esto se aplica incluyen los siguientes:

- **Servicios en línea conectados opcionales**: Office 365 ProPlus ofrece al usuario varios servicios en línea conectados opcionales. La lista de estos servicios y los controles de usuario relacionados se muestran [aquí](https://support.office.com/article/microsoft-s-other-connected-services-92c234f1-dc91-4dc1-925d-6c90fc3816d8). Puede decidir si quiere permitir que sus usuarios finales usen estos servicios. Para obtener más información, vea [Formas en que los administradores pueden administrar servicios de los responsables de los datos en Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/manage-controller-services-office-365-proplus). En la medida en que estos servicios opcionales realicen un tratamiento de datos personales, Microsoft es el responsable de los datos para estos servicios.

- **Comentarios de los usuarios**: si los usuarios envían comentarios sobre productos y servicios de Microsoft, Microsoft es el responsable de los datos de esos comentarios en la medida en que contengan datos personales. Microsoft cumplirá las solicitudes de derechos del interesado en relación con los comentarios recopilados por Microsoft (incluidos los comentarios administrados por los encargados del tratamiento secundarios de Microsoft), excepto en aquellos casos en los que Microsoft indique a los usuarios que no incluyan datos personales durante el proceso de recopilación de comentarios. Excepciones: si Microsoft indica a los usuarios que no incluyan datos personales durante el proceso de recopilación de comentarios, Microsoft se basará en esa instrucción y supondrá que no se ha proporcionado ningún dato personal. Los usuarios que hayan creado una cuenta independiente con proveedores de servicios de comentarios de terceros tendrán que realizar su solicitud de derechos del interesado directamente con esos proveedores.

- **Cuenta profesional o educativa de Windows autenticada**: si su organización ha comprado licencias de Windows y los usuarios las autentican en su cuenta profesional o educativa de Microsoft, este actúa como responsable de los datos. Para más información, vea [Solicitudes del interesado de Windows para el RGPD](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-windows).

- **Productos y servicios adquiridos por el usuario**: si permite que los usuarios, actuando a título individual, adquieran productos o servicios de Microsoft que usan AAD para la autenticación (como complementos de Office o aplicaciones disponibles en Microsoft Store), es posible que Microsoft sea el responsable de los datos. Para estos productos o servicios de Microsoft, los usuarios tendrán que ponerse en contacto con Microsoft directamente para iniciar una DSR.

> [!IMPORTANT]
> Si elimina un usuario habilitado mediante Azure Active Directory, el (antiguo) usuario ya no podrá iniciar sesión en los productos o servicios que usaba anteriormente con una cuenta profesional o educativa. Además, Microsoft ya no podrá autenticar al usuario en relación con una solicitud de derechos del interesado correspondiente para productos o servicios en los que Microsoft sea el responsable de los datos. Si quiere que un usuario pueda iniciar solicitudes de derechos del interesado en estos servicios, es importante que le indique que lo haga antes de eliminar la cuenta de AAD del usuario.

### <a name="personal-accounts"></a>Cuentas personales
Si los usuarios han utilizado cuentas de Microsoft (es decir, cuentas personales) para adquirir productos y servicios de Microsoft para su propio uso y en los que Microsoft sea responsable de los datos, pueden iniciar solicitudes de DSR mediante el [Panel de privacidad de Microsoft](https://account.microsoft.com/account/privacy).

### <a name="third-party-products"></a>Productos de terceros

Si su organización o los usuarios que actúan en su capacidad individual, han adquirido productos o servicios de terceros y usar su cuenta profesional o educativa de Microsoft para la autenticación, las solicitudes de interesados deben dirigirse a la entidad correspondiente.

## <a name="appendix-a-preparing-for-dsr-investigations"></a>Apéndice A: Preparar investigaciones de solicitudes de interesados

Para ayudar a su organización a preparar investigaciones de solicitudes de terceros con servicios de Office 365, considere las siguientes recomendaciones:

- Usar la herramienta de casos eDiscovery de solicitudes de interesado en el Centro de seguridad y cumplimiento de Office 365 para administrar investigaciones de solicitudes de interesado

- Configurar los límites de cumplimiento para limitar el ámbito de las búsquedas de contenido

- Usar la herramienta de búsqueda de registro de auditoría de Office 365 en investigaciones de solicitudes de interesado

### <a name="use-the-dsr-case-tool-to-manage-dsr-investigations"></a>Usar la herramienta de caso de solicitudes de interesado para administrar investigaciones de solicitudes de interesado

Le recomendamos que use la herramienta de solicitudes de interesado en el centro de cumplimiento y seguridad para administrar las investigaciones. Al usar la herramienta, puede:

- Crear un caso independiente para cada investigación de DSR.

- Use la búsqueda integrada para buscar todo el contenido relacionado con un interesado concreto. Al crear un caso e iniciar la búsqueda, se buscan estas ubicaciones de contenido:
    
   - Todos los buzones de la organización (incluidos los buzones asociados a Microsoft Teams y Grupos de Office 365)
    
    - Todos los sitios de SharePoint Online y OneDrive para la Empresa de la organización
    
    - Todos los sitios de Microsoft Teams y sitios de grupo de Office 365 de su organización
    
    - Todas las carpetas públicas de Exchange Online

- Revise la consulta de búsqueda predeterminada y vuelva a ejecutar la búsqueda para restringir los resultados de búsqueda.

- Controle quién tiene acceso al caso agregando usuarios como miembros, solo los miembros pueden acceder al caso y podrán ver solo sus casos en la lista de casos de la página de solicitudes de interesados en el Centro de seguridad y cumplimiento. Además, puede asignar distintos permisos a distintos miembros del mismo caso. Por ejemplo, puede permitir a algunos miembros ver solo el caso y los resultados de una búsqueda de contenido y permitir a otros crear búsquedas y exportar resultados.

- Cree trabajos de exportación para exportar los resultados de la búsqueda en respuesta a una solicitud de exportación de DSR. Puede exportar todo el contenido devuelto por la Búsqueda de contenido. También se exportarán otros datos de Office 365 relacionados con un interesado.

- Cree trabajos de exportación para exportar los resultados de la búsqueda en respuesta a una solicitud de exportación de DSR. Puede exportar todo el contenido devuelto por la Búsqueda de contenido. Además, puede exportar registros generados por el sistema para My Analytics y el Servicio de roaming de Office.

- Elimine los casos cuando se complete el proceso de investigación de solicitudes de derechos del interesado. Se quitarán todas las búsquedas de contenido y trabajos de exportación asociados al caso.

Para empezar a usar casos de DSR, vea [Administrar solicitudes de los interesados sobre RGPD con la herramienta de casos de DSR en el Centro de seguridad y cumplimiento de Office 365](https://support.office.com/article/manage-dsr-cases-in-the-office-365-security-compliance-center-ce9eb942-3589-42cb-88fd-1576ecb09c5c).

> [!IMPORTANT]
> Un administrador de eDiscovery puede ver y administrar todos los casos de DSR de la organización. Para obtener más información sobre los distintos roles relacionados con eDiscovery, vea [Asignar permisos de eDiscovery a posibles miembros](https://docs.microsoft.com/Office365/SecurityCompliance/assign-ediscovery-permissions).

### <a name="set-up-compliance-boundaries-to-limit-the-scope-of-content-searches"></a>Configurar los límites de cumplimiento normativo para limitar el ámbito de las búsquedas de contenido

Los límites de cumplimiento se implementan con la función de filtrado de permisos de búsqueda en el Centro de seguridad y cumplimiento. Los límites de cumplimiento crean límites de búsqueda lógicos dentro de una organización que controlan o limitan en qué ubicaciones de contenido (por ejemplo, buzones de Exchange Online y sitios de SharePoint Online) puede buscar un administrador de TI o responsable de cumplimiento. Los límites de cumplimiento son útiles para organizaciones multinacionales que necesitan respetar los límites geográficos, las organizaciones gubernamentales que necesiten para separar diferentes agencias y las organizaciones de empresa que se segregan en unidades de negocio o departamentos. En todos estos escenarios, los límites de cumplimiento pueden usarse en investigaciones de solicitudes de interesado para limitar los buzones y sitios en los que se puedan buscar personas implicadas en la investigación.

Puede usar los límites de cumplimiento con casos de eDiscovery para limitar las ubicaciones del contenido que se pueden buscar en una investigación en esas ubicaciones dentro de la agencia o unidad de negocio.

Una descripción general de alto nivel acerca de cómo implementar límites de cumplimiento (junto a casos de eDiscovery) en investigaciones de solicitudes de interesado.

1. Determine las agencias de su organización que se designarán como límite de cumplimiento.

2. Determine el atributo de objeto de usuario de Azure Active Directory que se va a usar para definir los límites de cumplimiento normativo. Por ejemplo, puede elegir el atributo Country, CountryCode o Department, para que los miembros del grupo de roles de administrador que cree el siguiente paso solo puedan buscar las ubicaciones de contenido de los usuarios con un valor específico para ese atributo. Así es como se limita quién puede buscar contenido en un organismo específico.

> [!NOTE]
> Actualmente, debe realizar un paso adicional para OneDrive para la Empresa y presentar una solicitud del Soporte técnico de Microsoft para que el atributo se sincronice con las cuentas de OneDrive para la Empresa.

4. Cree un grupo de roles de administrador en el Centro de seguridad y cumplimiento de Office 365 para cada límite de cumplimiento. Para crear estos grupos de roles, se recomienda copiar el grupo de roles de Supervisor de eDiscovery y luego quitar roles según sea necesario.

5. Agregue miembros a cada uno de los grupos de roles específicos, como administradores de eDiscovery. Los miembros son los responsables de investigar y responder a las solicitudes de interesado y normalmente serán administradores de TI, responsables de privacidad de datos, administradores de cumplimiento y representantes de recursos humanos.

6. Cree un filtro de permisos de búsqueda para cada límite de cumplimiento para que los miembros del grupo de roles de administración correspondiente solo pueden buscar usuarios en buzones y sitios dentro de ese límite de cumplimiento. El filtro de permisos de búsqueda permitirá a miembros del grupo de roles correspondiente buscar solo en las ubicaciones de contenido con el valor de atributo de objeto de usuario que se corresponde con el límite de cumplimiento.

Para obtener instrucciones detalladas, consulte [Configurar los límites de cumplimiento para investigaciones de eDiscovery en Office 365](https://support.office.com/article/1b45c82f-26c8-44fb-9f3b-b45436fe2271).

### <a name="use-the-office-365-audit-log-search-tool-in-dsr-investigations"></a>Usar la herramienta de búsqueda de registro de auditoría de Office 365 en investigaciones de solicitudes de interesado

Los administradores de TI pueden usar la herramienta de búsqueda de registro de auditoría en el centro de cumplimiento y seguridad para los documentos de identidad, archivos y otros recursos de Office 365 que los usuarios han creado, cambiado, eliminado, o a los que estos han accedido. Una búsqueda de actividad de este tipo puede ser útil en investigaciones de solicitud de interesado. Por ejemplo, en SharePoint Online y OneDrive para la Empresa, los eventos de auditoría se registran cuando los usuarios realizan estas actividades:

- Acceso a un archivo
- Modificación de un archivo
- Movimiento de un archivo
- Carga o descarga de un archivo

En el registro de auditoría puede buscar actividades específicas, tipos de actividades, actividades realizadas por un usuario concreto y otros criterios de búsqueda. Además de actividades de SharePoint Online y OneDrive para la Empresa, también puede buscar actividades de Flow, Power BI y Microsoft Teams. Tenga en cuenta que los registros de auditoría se conservan durante 90 días. Por lo tanto, no podrá buscar actividades de usuario que hayan ocurrido más de 90 días antes. Para obtener una lista completa de actividades auditadas y cómo buscar en el registro de auditoría, vea [Buscar en el registro de auditoría del Centro de seguridad y cumplimiento de Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).

> [!TIP]
> Para evitar la limitación de 90 días descrita anteriormente y mantener un historial acumulado de los registros de auditoría de la organización, puede exportar todas las actividades periódicamente (por ejemplo, cada 30 días) para tener un registro continuo de los registros de auditoría de la organización.

## <a name="appendix-b-change-log"></a>Apéndice B: registro de cambios

La siguiente tabla enumeran los cambios realizados en la Guía de solicitudes del interesado de Office 365 desde su publicación inicial en el 25 de mayo de 2018.

|Fecha  |Sección / aplicación. |Cambio  |
|:---------|:---------|:---------|
|18/09/2018     |   [Whiteboard](#whiteboard)      |La vista previa de Whiteboard ya no está en vista previa y se ha publicado para disponibilidad general. Por lo tanto, se ha cambiado el nombre de la sección de vista previa de Whiteboard a "Whiteboard para PC, Surface Hub y otras plataformas"; los procedimientos para el acceso, la exportación y la eliminación de datos se han eliminado de esta sección y han sido reemplazados con un vínculo al artículo de soporte técnico de Whiteboard.|
|08/11/2018     |    [Workplace Analytics](#workplace-analytics)     |Se han agregado instrucciones paso a paso a la sección Eliminar acerca de cómo quitar a un interesado de Workplace Analytics y quitar la información sobre un interesado de un informe de Workplace Analytics.|
|12/11/2018| Todo| Se han arreglado los marcadores y los vínculos a temas externos que no funcionaban.|
|9/1/2019|[StaffHub](#staffhub)|En la sección Eliminar se ha actualizado la descripción de lo que ocurre cuando una cuenta de usuario se elimina permanentemente.|
|8/5/2019| [Publisher](#publisher)|Contenido agregado sobre cómo responder a solicitudes del interesado sobre Publisher.|
||||
