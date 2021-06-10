---
title: Plan de fin del soporte técnico de Exchange 2007
ms.author: dstrome
author: dstrome
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.assetid: c3024358-326b-404e-9fe6-b618e54d977d
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: Obtenga información sobre sus opciones después de Exchange Server de soporte técnico de 2007 e inicie la planeación de la migración a Microsoft 365, Office 365 o Exchange 2016.
ms.openlocfilehash: d7e8f50118dab6fcb618273f5c28497c80d4a549
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924205"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Plan de fin del soporte técnico de Exchange 2007

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Exchange Server 2007 llegó al final del soporte técnico en abril de 2017. Si no ha iniciado la migración de Exchange 2007 a Microsoft 365, Office 365 o Exchange 2016, ahora es el momento de empezar a planear.
  
## <a name="what-does-end-of-support-mean"></a>¿Qué *significa el fin de la compatibilidad?*

Exchange Server, como casi todos los productos de Microsoft, tiene un ciclo de vida de soporte técnico durante el cual proporcionamos nuevas características, correcciones de errores, correcciones de seguridad, y así sucesivamente. Este ciclo de vida suele durar 10 años desde la versión inicial del producto. El final de este ciclo de vida se conoce como el fin del soporte técnico del producto. Desde Exchange 2007 llegó a su fin de soporte técnico el 11 de abril de 2017, Microsoft ya no proporciona:
  
- Soporte técnico para los problemas que pueden producirse.
    
- Correcciones de errores para problemas que pueden afectar a la estabilidad y facilidad de uso del servidor.
    
- Correcciones de seguridad para vulnerabilidades que pueden hacer que el servidor sea vulnerable a infracciones de seguridad.
    
- Actualizaciones de zona horaria.
    
La instalación de Exchange 2007 seguirá en ejecución después de la fecha de finalización de la compatibilidad. Sin embargo, como no hay nuevas actualizaciones o compatibilidad, se recomienda encarecidamente migrar desde Exchange 2007 tan pronto como sea posible.
  
Para obtener más información acerca Office servidores de 2007 que se acercan al final de la compatibilidad, vea [Plan your upgrade from Office 2007 servers and products](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-are-my-options"></a>¿Cuáles son mis opciones?

Puede:
  
- Migre a Microsoft 365 mediante la migración híbrida, por fases o por fases.
    
- Migre Exchange servidores de 2007 a una versión más reciente de Exchange en los servidores locales.
    
Las secciones siguientes exploran cada opción con más detalle.
  
### <a name="migrate-to-microsoft-365"></a>Migrar a Microsoft 365

Migrar el correo electrónico a Microsoft 365 es la mejor y más sencilla opción para ayudar a retirar Exchange implementación de 2007. Con una migración a Microsoft 365, puede hacer un solo salto de una tecnología de 10 años a características de última generación, como:
  
- Funcionalidades de cumplimiento como directivas de retención, In-Place y retención por juicio, exhibición de documentos electrónicos local y mucho más
    
- Grupos de Microsoft 365
    
- Bandeja de entrada Prioritarios
    
- MyAnalytics
    
- API de REST para el acceso mediante programación al correo electrónico, calendarios, contactos, y así sucesivamente
    
Microsoft 365 obtiene primero nuevas características y experiencias, por lo que los usuarios y tú pueden empezar a usarlos de inmediato. Y no tendrás que preocuparte de:
  
- Comprar y mantener hardware.
    
- Pagar para que los servidores se calienten y se enfríen.
    
- Mantenerse al día en las correcciones de seguridad, producto y zona horaria.
    
- Mantener el almacenamiento y el software para admitir los requisitos de cumplimiento.
    
- Actualización a una nueva versión de Exchange. Con Microsoft 365, siempre estás en la versión más reciente de Exchange.
    
#### <a name="how-should-i-migrate-to-microsoft-365"></a>¿Cómo debo migrar a Microsoft 365?

Tiene algunas opciones de migración. Debe tener en cuenta algunas cosas, como:

- Número de puestos o buzones que necesita mover.
- Cuánto tiempo desea que dure la migración.
- Si necesita una integración perfecta entre la instalación local y Microsoft 365 durante la migración.

En esta tabla se muestran las opciones de migración y los factores más importantes que determinan qué método usar:
  

|**Opción de migración**|**Tamaño de la organización**|**Duración**|
|:-----|:-----|:-----|
|Migración total  <br/> |Menos de 150 puestos  <br/> |Una semana o menos  <br/> |
|Migración preconfigurada  <br/> |Más de 150 puestos  <br/> |Unas semanas  <br/> |
|Migración híbrida completa  <br/> |Entre cientos y miles de puestos  <br/> |Unos meses o más  <br/> |
   
En las secciones siguientes se proporciona información general sobre estos métodos. Para obtener más información, vea [Decide on a migration path](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27). 
  
#### <a name="cutover-migration"></a>Migración total

En una migración total, se migran todos los buzones, grupos de distribución, contactos, entre otros, para Microsoft 365 en una fecha y hora preseleccionados. Una vez completada la migración, se cierran los servidores Exchange locales y se empieza a usar Microsoft 365 exclusivamente.
  
La migración de extensiones es ideal para organizaciones pequeñas que no tienen muchos buzones de correo, que desean llegar Microsoft 365 Microsoft 365 rápidamente y no quieren tratar algunas de las complejidades de los otros métodos. Pero debe completarse en una semana o menos y requiere que los usuarios vuelvan a configurar sus Outlook perfiles. La migración de recortes puede controlar hasta 2.000 buzones, pero se recomienda encarecidamente usarlo para migrar un máximo de 150 buzones. Si intenta migrar más, puede que se le agote el tiempo para transferir todos los buzones antes de la fecha límite, y el personal de soporte técnico de TI puede agobiarse con las solicitudes para ayudar a los usuarios a volver a configurar Outlook.
  
Si está pensando en realizar una migración de recortes, estos son los aspectos que debe tener en cuenta:
  
- Microsoft 365 tendrá que conectarse a los servidores de Exchange 2007 mediante Outlook en cualquier lugar a través del puerto TCP 443.
    
- Todos los buzones locales se mueven a Microsoft 365.
    
- Necesitará una cuenta de administrador local que tenga acceso de lectura a los buzones de los usuarios.
    
- Los Exchange 2007 aceptados que desea usar en Microsoft 365 deben agregarse como dominios comprobados en el servicio.
    
- Entre el momento en que inicie la migración y cuando comience la fase de finalización, Microsoft 365 sincronizará periódicamente los buzones de correo Microsoft 365 y locales. Esto le permite completar la migración sin preocuparse de que el correo electrónico se deje en sus buzones locales.
    
- Los usuarios recibirán nuevas contraseñas temporales para sus Microsoft 365 cuentas. Necesitarán cambiar su contraseña cuando inicien sesión en su buzón por primera vez.
    
- Necesitará una licencia de Microsoft 365 que incluya Exchange Online para cada buzón de usuario que migre.
    
- Los usuarios tendrán que configurar un nuevo perfil Outlook en cada uno de sus dispositivos y volver a descargar su correo electrónico. La cantidad de correo electrónico que Outlook descargará puede variar. Para obtener más información, [vea Cambiar la cantidad de correo que se debe mantener sin conexión.](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)
    
Para obtener más información acerca de la migración de los recortes, vea:
  
- [Lo que necesita saber sobre una migración de correo electrónico sin escalas](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
    
- [Realizar una migración de correo electrónico](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)
    
#### <a name="staged-migration"></a>Migración preconfigurada

En una migración por fases, tiene unos cientos o varios miles de buzones que desea migrar a Microsoft 365, necesita tardar una semana o más en completar la migración y no necesita ninguna de las características avanzadas de migración híbrida, como la información de calendario de disponibilidad compartida.
  
La migración por fases es ideal para las organizaciones que necesitan tardar más tiempo en migrar sus buzones a Microsoft 365 pero aún planean completar la migración en unas pocas semanas. Puede migrar buzones en lotes. Puede controlar cuántos y qué buzones se migran en un momento determinado. Puede procesar por lotes los buzones de los usuarios del mismo departamento, por ejemplo, para asegurarse de que se mueven todos al mismo tiempo. O bien, puede dejar buzones ejecutivos hasta el último lote. Al igual que con las migraciones de recorte, los usuarios tendrán que volver a crear sus Outlook de usuario.
  
Si está pensando en realizar una migración por fases, estos son los aspectos que debe tener en cuenta:
  
- Microsoft 365 tendrá que conectarse a los servidores de Exchange 2007 mediante Outlook en cualquier lugar a través del puerto TCP 443.
    
- Necesitará una cuenta de administrador local que tenga acceso de lectura a los buzones de los usuarios.
    
- Los Exchange 2007 aceptados que planea usar en Microsoft 365 deben agregarse como dominios comprobados en el servicio.
    
- Deberá crear un archivo CSV con el nombre completo y la dirección de correo electrónico de cada buzón que tiene previsto migrar en un lote. También tendrá que incluir una nueva contraseña para cada buzón que va a migrar y enviar esa contraseña a cada usuario. Se pedirá al usuario que cambie la contraseña la primera vez que inicie sesión en su nuevo buzón Microsoft 365 correo.
    
- Entre el momento en que inicie el lote de migración y cuando comience la fase de finalización, Microsoft 365 sincronizará periódicamente los buzones de correo Microsoft 365 y locales incluidos en el lote. Esto le permite completar la migración sin preocuparse de que el correo electrónico se deje en sus buzones locales.
    
- Necesitará una licencia de Microsoft 365 que incluya Exchange Online para cada buzón de usuario que migre.
    
- Los usuarios tendrán que configurar un nuevo perfil Outlook en cada uno de sus dispositivos y volver a descargar su correo electrónico. La cantidad de correo electrónico que Outlook descargará puede variar. Para obtener más información, [vea Cambiar la cantidad de correo que se debe mantener sin conexión.](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)
    
Para obtener más información acerca de la migración por fases, vea:
  
- [Lo que necesita saber sobre una migración de correo electrónico por fases](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)
    
- [Realizar una migración por fases del correo electrónico](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)
    
#### <a name="full-hybrid"></a>Híbrido completo

En una migración híbrida completa, su organización tiene muchos cientos, hasta decenas de miles, de buzones y desea mover algunos o todos a Microsoft 365. Dado que estas migraciones suelen ser a largo plazo, las migraciones híbridas hacen posible lo siguiente:
  
- Mostrar a los usuarios locales la información del calendario de disponibilidad para los usuarios Microsoft 365 y viceversa.
    
- Vea una lista global unificada de direcciones que contiene destinatarios tanto locales como Microsoft 365.
    
- Ver todas Outlook de destinatarios para todos los usuarios, independientemente de si son locales o en Microsoft 365.
    
- Comunicación de correo electrónico segura entre servidores Exchange locales y Microsoft 365 mediante TLS y certificados.
    
- Trate los mensajes enviados entre servidores Exchange locales y Microsoft 365 como internos, lo que les permite:
    
  - Los agentes de transporte y cumplimiento deben evaluar y procesar correctamente los mensajes internos.
    
  - Omitir filtros contra correo no deseado.
    
La migración híbrida completa es la mejor para las organizaciones que esperan permanecer en una configuración híbrida durante varios meses o más. Verá las características enumeradas anteriormente en esta sección, además de la sincronización de directorios, las características de cumplimiento mejor integradas y la capacidad de mover buzones de correo a y desde Microsoft 365 mediante movimientos de buzones en línea. Microsoft 365 se convierte en una extensión de la organización local.
  
Si está pensando en realizar una migración híbrida completa, estos son los aspectos que debe tener en cuenta:
  
- La migración híbrida completa no es adecuada para todos los tipos de organizaciones. Debido a la complejidad de las migraciones híbridas completa, las organizaciones con menos de unos pocos cientos de buzones no suelen ver ventajas que justifiquen el esfuerzo y el costo necesarios para configurar uno. Si esto suena como su organización, le recomendamos que considere la posibilidad de realizar una migración por fases o de recorte en su lugar.
    
- Deberá implementar al menos un servidor Exchange 2013 en su organización de Exchange 2007 para actuar como un "servidor híbrido". Este servidor se comunicará con Microsoft 365 en nombre de los servidores Exchange 2007.
    
- Microsoft 365 tendrá que conectarse al "servidor híbrido" mediante Outlook en cualquier lugar a través del puerto TCP 443.
    
- Deberá configurar la sincronización de directorios mediante Azure Active Directory (Azure AD) Conectar entre los servidores locales de Active Directory y Microsoft 365.
    
- Los usuarios podrán iniciar sesión en su buzón de Microsoft 365 con el mismo nombre de usuario y contraseña que cuando inicien sesión en la red local. (Esta funcionalidad requiere que Azure AD Conectar sincronización de contraseñas o servicios de federación de Active Directory).
    
- Necesitará una licencia de Microsoft 365 que incluya Exchange Online para cada buzón de usuario que migre.
    
- Los usuarios no necesitan configurar un nuevo perfil de Outlook en la mayoría de sus dispositivos, aunque es posible que algunos teléfonos Android más antiguos necesiten un perfil nuevo. Los usuarios no tendrán que volver a descargar su correo electrónico.
    
Si la migración híbrida completa suena correctamente, consulte los siguientes recursos para ayudarle con la migración:
  
- [Exchange Asistente para implementación](/exchange/exchange-deployment-assistant)
    
- [Implementaciones híbridas de Exchange Server](/exchange/exchange-hybrid)
    
- [Asistente de configuración híbrida](/exchange/hybrid-configuration-wizard)
    
- [Preguntas más frecuentes acerca del asistente de configuración híbrida](/exchange/hybrid-configuration-wizard-faqs)
    
- [Requisitos previos para la implementación híbrida](/exchange/hybrid-deployment-prerequisites)
    
### <a name="migrate-to-a-newer-version-of-exchange-server"></a>Migrar a una versión más reciente de Exchange Server

Creemos firmemente que puede lograr el mejor valor y experiencia de usuario mediante la migración a Microsoft 365. Pero también entendemos que algunas organizaciones necesitan mantener su correo electrónico local. Esto podría deberse a requisitos normativos, para garantizar que los datos no se almacenan en un centro de datos ubicado en otro país o similar. Si decide mantener el correo electrónico local, puede migrar el entorno de Exchange 2007 Exchange 2010, Exchange 2013 o Exchange 2016.
  
Si no puede migrar a Microsoft 365, se recomienda migrar a Exchange 2016. Exchange 2016 incluye todas las características de versiones anteriores de Exchange. También coincide más estrechamente con la experiencia disponible con Microsoft 365, aunque algunas características solo están disponibles en Microsoft 365. Echa un vistazo a algunas de las cosas que te han faltado:
  
|**Exchange versión**|**Funciones**|
|:-----|:-----|
|Exchange 2010  <br/> | Role-Based control de acceso (permisos sin ACL)  <br/>  Directivas de buzones de Outlook Web App  <br/>  Capacidad para compartir calendarios de disponibilidad y delegados entre organizaciones  <br/> |
|Exchange 2013  <br/> | *Características de Exchange 2010 y ...*  <br/>  Arquitectura simplificada que redujo el número de roles de servidor a tres (buzón, acceso de cliente, transporte perimetral)  <br/>  Directivas de prevención de pérdida de datos (DLP) que ayudan a evitar que se filtre información confidencial  <br/>  Experiencia de Outlook Web App mejorada  <br/> |
|Exchange 2016  <br/> | *Características de Exchange 2013 y ...*  <br/>  Roles de servidor simplificados para solo buzón y transporte perimetral  <br/>  DLP mejorado junto con la integración con SharePoint  <br/>  Resistencia mejorada de la base de datos  <br/>  Colaboración de documentos en línea |
   
#### <a name="which-version-should-i-migrate-to"></a>¿A qué versión debo migrar?

Le recomendamos que inicialmente suponga que migrará a Exchange 2016. A continuación, use la siguiente información para confirmar su suposición o para descartar Exchange 2016. Si no puede migrar a Exchange 2016 por algún motivo, haga el mismo proceso con Exchange 2013, y así sucesivamente.
  
|**Consideración**|**Más información**|
|:-----|:-----|
|Fechas de finalización del soporte técnico  <br/> | Al Exchange 2007, cada versión de Exchange tiene su propia fecha de fin de soporte técnico:  <br/> *Exchange 2010* - Enero de 2020  <br/> *Exchange 2013* - Abril de 2023  <br/> *Exchange 2016* - Octubre de 2025  <br/>  Cuanto antes finalice la compatibilidad, más pronto tendrá que realizar otra migración.<br/> |
|Ruta de migración a Exchange 2010 y 2013.  <br/> |Estas son las fases generales para migrar a Exchange 2010 o Exchange 2013:  <br/> - Instalar Exchange 2010 o 2013 en la organización Exchange 2007. <br/>- Mover servicios y otra infraestructura a Exchange 2010 o 2013.<br/>- Mover buzones y carpetas públicas a Exchange 2010 o 2013.<br/>- Retirar los servidores Exchange 2007. |
|Ruta de migración a Exchange 2016  <br/> |Estas son las fases generales para migrar a Exchange 2016:  <br/> - Instalar Exchange 2013 en la organización Exchange 2007.<br/>- Mover servicios y otra infraestructura a Exchange 2013.<br/>- Mover buzones y carpetas públicas a Exchange 2013.<br/>- Retirar los servidores Exchange 2007.<br/>- Instalar Exchange 2016 en la organización Exchange 2013.<br/>- Mover buzones, carpetas públicas, servicios y otra infraestructura a Exchange 2016 (el orden no importa). Retirar los servidores Exchange 2013.<br/><br/> **Nota:** Migrar de Exchange 2013 a Exchange 2016 es sencillo. Las dos versiones tienen casi los mismos requisitos de hardware y estas versiones son muy compatibles. Por lo tanto, puede volver a crear un servidor que compró para Exchange 2013 e instalar Exchange 2016 en él. Para los movimientos de buzones en línea, la mayoría de los usuarios ni siquiera notará que su buzón se movió del servidor y, a continuación, de nuevo después de volver a crearlo con Exchange 2016.           |
|Coexistencia de versiones  <br/> | Al migrar a ...  <br/> **Exchange 2016:** Exchange 2016 no se puede instalar en una organización que incluya un servidor Exchange 2007. Primero deberá migrar Exchange Exchange 2010 o 2013 (se recomienda encarecidamente Exchange 2013), quitar todos los servidores de Exchange 2007 y, a continuación, migrar a Exchange 2016.  <br/> **Exchange 2010 o Exchange 2013:** Puede instalar Exchange 2010 o Exchange 2013 en una organización Exchange 2007. Esto le permite instalar uno o más servidores Exchange 2010 o 2013 y realizar la migración.  <br/> |
|Hardware de servidor  <br/> | Los requisitos de hardware del servidor han cambiado Exchange 2007. Asegúrese de que el hardware es compatible. Para más información, vea:  <br/> [Exchange del sistema de 2016](/Exchange/plan-and-deploy/system-requirements) <br/> [Exchange del sistema de 2013](/exchange/exchange-2013-system-requirements-exchange-2013-help) <br/> [Exchange 2010 System Requirements](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141)) <br/>  Encontrará que las mejoras significativas en el rendimiento de Exchange y la mayor capacidad de almacenamiento y potencia informática en servidores más recientes significan que probablemente necesitará menos servidores para admitir el mismo número de buzones.  <br/> |
|Versión del sistema operativo  <br/> | Las versiones mínimas admitidas del sistema operativo para cada versión son:  <br/> **Exchange 2016:** Windows Server 2012  <br/> **Exchange 2013:** Windows Server 2008 R2 SP1  <br/> **Exchange 2010:** Windows Server 2008 SP2  <br/>  Encontrará más información sobre la compatibilidad del sistema operativo [en Exchange Matriz de compatibilidad](/Exchange/plan-and-deploy/supportability-matrix).  <br/> |
|Nivel funcional del bosque de Active Directory  <br/> | Los niveles funcionales mínimos admitidos de bosque de Active Directory para cada versión son:  <br/> **Exchange 2016** Windows Server 2008 R2 SP1  <br/> **Exchange 2013** Windows Server 2003  <br/> **Exchange 2010** Windows Server 2003  <br/>  Encontrará más información sobre la compatibilidad de nivel funcional del bosque [en Exchange Matriz de compatibilidad](/Exchange/plan-and-deploy/supportability-matrix).  <br/> |
|Office cliente  <br/> | Las versiones mínimas Office cliente admitidas para cada versión son:  <br/> **Exchange 2016:** Office 2010 (con las actualizaciones más recientes)  <br/> **Exchange 2013:** Office 2007 SP3  <br/> **Exchange 2010** - Office 2003  <br/>  Encontrará más información sobre el Office cliente en [Exchange Matriz de compatibilidad](/Exchange/plan-and-deploy/supportability-matrix).  <br/> |
   
#### <a name="how-do-i-migrate"></a>¿Cómo puedo migrar?

Si decidió mantener el correo electrónico local, use los siguientes recursos para ayudar con la migración:
  
- [Exchange Asistente para implementación](/exchange/exchange-deployment-assistant)
    
- Cambios de esquema de Active Directory para Exchange [2016](/Exchange/plan-and-deploy/active-directory/ad-schema-changes), [2013](/exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help), [2010](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)
    
- Requisitos del sistema Exchange [2016](/Exchange/plan-and-deploy/system-requirements), [2013](/exchange/exchange-2013-system-requirements-exchange-2013-help), [2010](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141))
    
- Requisitos previos Exchange [2016](/Exchange/plan-and-deploy/prerequisites), [2013](/exchange/exchange-2013-prerequisites-exchange-2013-help), [2010](/previous-versions/office/exchange-server-2010/bb691354(v=exchg.141))
    
## <a name="get-help"></a>Obtener ayuda

Si está migrando a Microsoft 365, puede ser elegible para usar nuestro servicio De FastTrack de Microsoft. FastTrack proporciona procedimientos recomendados, herramientas y recursos para que la migración a Microsoft 365 sea lo más sencilla posible. Lo mejor de todo es que un ingeniero de soporte técnico le ayudará a través de la migración, desde la planeación y el diseño hasta la migración del último buzón. Para obtener más información sobre FastTrack, vea [Microsoft FastTrack](https://fasttrack.microsoft.com/).
  
Si tiene problemas durante la migración a Microsoft 365 y no está usando FastTrack o la migración a una versión más reciente de Exchange Server, estamos aquí para ayudarle. Estos son algunos recursos que puede usar:
  
- [Comunidad de soporte técnico](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
    
- [Soporte al cliente](https://support.microsoft.com/gp/support-options-for-business)
    
## <a name="related-topics"></a>Temas relacionados

[Recursos que le ayudarán a actualizar Office servidores y clientes de 2007](upgrade-from-office-2007-servers-and-products.md)