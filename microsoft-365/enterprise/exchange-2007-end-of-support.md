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
description: Obtenga información sobre las opciones una vez que se haya finalizado el soporte técnico de Exchange Server 2007 e inicie la planeación de la migración a Microsoft 365, Office 365 o Exchange 2016.
ms.openlocfilehash: 3f0a5c8ef9765a184358b932548eaa2ae7c59adc
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519850"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Plan de fin del soporte técnico de Exchange 2007

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Exchange Server 2007 ha alcanzado el final de soporte en el 2017 de abril. Si no ha iniciado la migración de Exchange 2007 a Microsoft 365, Office 365 o Exchange 2016, ahora es el momento de empezar a planear.
  
## <a name="what-does-end-of-support-mean"></a>¿Qué significa el *fin de soporte* ?

Exchange Server, como casi todos los productos de Microsoft, tiene un ciclo de vida de soporte técnico durante el cual ofrecemos nuevas características, correcciones de errores, correcciones de seguridad, etc. Este ciclo de vida suele durar diez años a partir de la versión inicial del producto. El final de este ciclo de vida se conoce como el final del soporte técnico del producto. Dado que Exchange 2007 ha alcanzado el final del soporte técnico el 11 de abril de 2017, Microsoft ya no ofrece:
  
- Soporte técnico para los problemas que pueden surgir.
    
- Correcciones de errores para problemas que pueden afectar a la estabilidad y la usabilidad del servidor.
    
- Revisiones de seguridad para las vulnerabilidades que pueden hacer que el servidor sea vulnerable a las infracciones de seguridad.
    
- Las actualizaciones de zona horaria.
    
La instalación de Exchange 2007 seguirá ejecutándose después de la fecha de finalización del soporte técnico. Pero, como no hay nuevas actualizaciones o soporte técnico, se recomienda encarecidamente migrar desde Exchange 2007 lo antes posible.
  
Para obtener más información acerca de los servidores de Office 2007 cerca de la finalización del soporte técnico, vea [plan Your upgrade from office 2007 Servers and Products](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-are-my-options"></a>¿Qué opciones tengo?

Puede:
  
- Migrar a Microsoft 365 mediante transferencias, preconfiguradas o con migración híbrida.
    
- Migre los servidores de Exchange 2007 a una versión más reciente de Exchange en los servidores locales.
    
En las siguientes secciones se examina cada opción con más detalle.
  
### <a name="migrate-to-microsoft-365"></a>Migrar a Microsoft 365

Migrar el correo electrónico a Microsoft 365 es la mejor y sencilla opción para ayudarle a retirar su implementación de Exchange 2007. Con una migración a Microsoft 365, puede realizar un solo salto de tecnología de 10 años para las características de vanguardia, entre los que se incluyen:
  
- Capacidades de cumplimiento, como directivas de retención, In-Place y retención por juicio, exhibición de documentos electrónicos local y mucho más
    
- Grupos de Microsoft 365
    
- Bandeja de entrada Prioritarios
    
- MyAnalytics
    
- API de REST para el acceso mediante programación al correo electrónico, calendarios, contactos, etc.
    
Microsoft 365 también recibe nuevas características y experiencias en primer lugar, por lo que usted y sus usuarios normalmente pueden empezar a usarlas de inmediato. Y no tendrá que preocuparse por:
  
- Comprar y mantener hardware.
    
- Pagar al calor y enfriar los servidores.
    
- Mantenerse al día en las correcciones de zona horaria, del producto y la seguridad.
    
- Mantener el almacenamiento y el software para admitir los requisitos de cumplimiento.
    
- Actualización a una nueva versión de Exchange. Con Microsoft 365, siempre está en la última versión de Exchange.
    
#### <a name="how-should-i-migrate-to-microsoft-365"></a>¿Cómo debo migrar a Microsoft 365?

Tiene algunas opciones de migración. Debe tener en cuenta algunas cosas, entre las que se incluyen:

- El número de puestos o buzones que necesita mover.
- El tiempo que desea que dure la migración.
- Si necesita una integración sin problemas entre su instalación local y Microsoft 365 durante la migración.

En esta tabla se muestran las opciones de migración y los factores más importantes que determinan el método que se debe usar:
  

|**Opción de migración**|**Tamaño de la organización**|**Duración**|
|:-----|:-----|:-----|
|Migración total  <br/> |Menos de 150 puestos  <br/> |Una semana o menos  <br/> |
|Migración preconfigurada  <br/> |Más de 150 puestos  <br/> |Unas semanas  <br/> |
|Migración híbrida completa  <br/> |Varios cientos o miles de puestos  <br/> |Unos meses o más  <br/> |
   
En las secciones siguientes se proporciona información general sobre estos métodos. Para obtener más información, consulte [decidir una ruta de migración](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27). 
  
#### <a name="cutover-migration"></a>Migración total

En una migración total, se migran todos los buzones de correo, grupos de distribución, contactos, etc., a Microsoft 365 en una fecha y hora preseleccionadas. Una vez completada la migración, apague los servidores de Exchange locales y empiece a usar Microsoft 365 exclusivamente.
  
La migración total es ideal para las organizaciones pequeñas que no tienen muchos buzones de correo, por lo que quieren llegar a Microsoft 365 rápidamente y no quieren tratar con algunas de las complejidades de los otros métodos. Pero debe completarse en una semana o menos y requiere que los usuarios vuelvan a configurar sus perfiles de Outlook. La migración total puede administrar hasta 2.000 buzones de correo, pero se recomienda encarecidamente usarlo para migrar un máximo de 150 buzones. Si intenta migrar más, puede quedarse sin tiempo para transferir todos los buzones de correo antes de la fecha límite y el personal de soporte técnico de ti puede quedar abrumado con solicitudes para ayudar a los usuarios a volver a configurar Outlook.
  
Si está pensando en realizar una migración total, tenga en cuenta lo siguiente:
  
- Microsoft 365 tendrá que conectarse a los servidores de Exchange 2007 mediante Outlook Anywhere a través del puerto TCP 443.
    
- Todos los buzones locales se moverán a Microsoft 365.
    
- Necesitará una cuenta de administrador local que tenga acceso de lectura a los buzones de los usuarios.
    
- Los dominios aceptados de Exchange 2007 que desea usar en Microsoft 365 deben agregarse como dominios comprobados en el servicio.
    
- Entre el momento en que inicia la migración y la fase de finalización, Microsoft 365 sincronizará periódicamente los buzones de correo de Microsoft 365 y locales. Esto le permite completar la migración sin preocuparse por el correo electrónico que queda en sus buzones locales.
    
- Los usuarios recibirán nuevas contraseñas temporales para sus cuentas de Microsoft 365. Necesitarán cambiar su contraseña cuando inicien sesión en su buzón por primera vez.
    
- Necesitará una licencia de 365 de Microsoft que incluya Exchange Online para cada buzón de usuario que migre.
    
- Los usuarios tendrán que configurar un nuevo perfil de Outlook en cada uno de sus dispositivos y descargar de nuevo el correo electrónico. La cantidad de correo electrónico que Outlook va a descargar puede variar. Para obtener más información, vea [cambiar la cantidad de correo que se va a mantener sin conexión](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
    
Para obtener más información acerca de la migración total, consulte:
  
- [Lo que debe saber sobre una migración total de correo electrónico](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
    
- [Realizar una migración total de correo electrónico](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)
    
#### <a name="staged-migration"></a>Migración preconfigurada

En una migración preconfigurada, tiene unos cientos o miles de buzones de correo que desea migrar a Microsoft 365, necesitará una semana o más para completar la migración y no necesitará ninguna de las características avanzadas de migración híbrida, como información de calendario de disponibilidad compartida.
  
La migración preconfigurada es ideal para las organizaciones que necesitan más tiempo para migrar sus buzones de correo a Microsoft 365, pero que aún tienen previsto completar la migración en unas pocas semanas. Puede migrar buzones en lotes. Puede controlar cuántos y qué buzones se migran en un momento dado. Es posible que tenga que realizar buzones de correo por lotes de usuarios en el mismo departamento, por ejemplo, para asegurarse de que todos se mueven al mismo tiempo. O bien, puede dejar buzones ejecutivos hasta el último lote. Al igual que con las migraciones de traslado, los usuarios tendrán que volver a crear sus perfiles de Outlook.
  
Si está pensando en realizar una migración preconfigurada, tenga en cuenta lo siguiente:
  
- Microsoft 365 tendrá que conectarse a los servidores de Exchange 2007 mediante Outlook Anywhere a través del puerto TCP 443.
    
- Necesitará una cuenta de administrador local que tenga acceso de lectura a los buzones de los usuarios.
    
- Los dominios aceptados de Exchange 2007 que tiene previsto usar en Microsoft 365 deben agregarse como dominios comprobados en el servicio.
    
- Deberá crear un archivo CSV con el nombre completo y la dirección de correo electrónico de cada buzón que tenga previsto migrar en un lote. También tendrá que incluir una nueva contraseña para cada buzón de correo que esté migrando y enviar la contraseña a cada usuario. Se le pedirá al usuario que cambie la contraseña la primera vez que inicie sesión en el nuevo buzón de correo de Microsoft 365.
    
- Entre el momento en que inicia el lote de migración y la fase de finalización, Microsoft 365 sincronizará periódicamente los buzones de correo de Microsoft 365 y locales que se incluyen en el lote. Esto le permite completar la migración sin preocuparse por el correo electrónico que queda en sus buzones locales.
    
- Necesitará una licencia de 365 de Microsoft que incluya Exchange Online para cada buzón de usuario que migre.
    
- Los usuarios tendrán que configurar un nuevo perfil de Outlook en cada uno de sus dispositivos y descargar de nuevo el correo electrónico. La cantidad de correo electrónico que Outlook va a descargar puede variar. Para obtener más información, vea [cambiar la cantidad de correo que se va a mantener sin conexión](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
    
Para obtener más información acerca de la migración preconfigurada, consulte:
  
- [Lo que debe saber sobre una migración preconfigurada de correo electrónico](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)
    
- [Realizar una migración preconfigurada de correo electrónico](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)
    
#### <a name="full-hybrid"></a>Híbrida completa

En una migración híbrida completa, la organización tiene muchos cientos, hasta decenas de miles de buzones de correo, y desea mover algunos o todos ellos a Microsoft 365. Debido a que estas migraciones suelen ser más duraderas, las migraciones híbridas hacen que sea posible:
  
- Mostrar a los usuarios locales la información del calendario de disponibilidad de los usuarios de Microsoft 365, y viceversa.
    
- Vea una lista global de direcciones unificada que contiene destinatarios en el sistema local y en Microsoft 365.
    
- Ver las propiedades completas de los destinatarios de Outlook para todos los usuarios, independientemente de si son locales o en Microsoft 365.
    
- Proteger la comunicación del correo electrónico entre los servidores de Exchange locales y Microsoft 365 mediante TLS y certificados.
    
- Tratar los mensajes enviados entre servidores de Exchange locales y Microsoft 365 como internos, lo que les permite:
    
  - Ser evaluados y procesados correctamente por los agentes de transporte y cumplimiento que apuntan a los mensajes internos.
    
  - Omitir los filtros contra correo no deseado.
    
La migración híbrida completa es la mejor para las organizaciones que esperan permanecer en una configuración híbrida durante muchos meses o más. Obtendrá las características enumeradas anteriormente en esta sección, además de la sincronización de directorios, mejores características de cumplimiento integradas y la capacidad de mover buzones de correo a y desde Microsoft 365 mediante movimientos de buzón en línea. Microsoft 365 se convierte en una extensión de la organización local.
  
Si está pensando en realizar una migración híbrida completa, tenga en cuenta lo siguiente:
  
- La migración híbrida completa no es adecuada para todos los tipos de organizaciones. Debido a la complejidad de las migraciones híbridas completas, las organizaciones con menos de unos pocos cientos de buzones de correo no suelen ver las ventajas que justifican el esfuerzo y el costo necesario para configurarlos. Si esto suena como su organización, le recomendamos que considere una migración total o preconfigurada en su lugar.
    
- Deberá implementar al menos un servidor de Exchange 2013 en la organización de Exchange 2007 para que actúe como un "servidor híbrido". Este servidor se comunicará con Microsoft 365 en nombre de los servidores de Exchange 2007.
    
- Microsoft 365 deberá conectarse al "servidor híbrido" mediante Outlook Anywhere a través del puerto TCP 443.
    
- Deberá configurar la sincronización de directorios con Azure Active Directory (Azure AD) conectado entre los servidores locales de Active Directory y Microsoft 365.
    
- Los usuarios podrán iniciar sesión en el buzón de correo de Microsoft 365 usando el mismo nombre de usuario y la misma contraseña que cuando inicien sesión en la red local. (Esta funcionalidad requiere Azure AD Connect con la sincronización de contraseñas y/o los servicios de Federación de Active Directory).
    
- Necesitará una licencia de 365 de Microsoft que incluya Exchange Online para cada buzón de usuario que migre.
    
- Los usuarios no necesitan configurar un nuevo perfil de Outlook en la mayoría de sus dispositivos, aunque es posible que algunos de los teléfonos Android más antiguos necesiten un nuevo perfil. Los usuarios no tendrán que redescargar su correo electrónico.
    
Si los sonidos de la migración híbrida completa son adecuados para usted, vea los siguientes recursos para ayudarle con la migración:
  
- [Asistente para la implementación de Exchange](https://aka.ms/exdeploy)
    
- [Implementaciones híbridas de Exchange Server](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx)
    
- [Asistente de configuración híbrida](https://technet.microsoft.com/library/hh529921%28v=exchg.150%29.aspx)
    
- [Preguntas más frecuentes acerca del asistente de configuración híbrida](https://technet.microsoft.com/library/mt488940%28v=exchg.150%29.aspx)
    
- [Requisitos previos para la implementación híbrida](https://technet.microsoft.com/library/hh534377%28v=exchg.150%29.aspx)
    
### <a name="migrate-to-a-newer-version-of-exchange-server"></a>Migrar a una versión más reciente de Exchange Server

Creemos que puede lograr el mejor valor y la experiencia del usuario mediante la migración a Microsoft 365. Pero también sabemos que algunas organizaciones necesitan mantener su correo electrónico local. Esto puede deberse a los requisitos normativos, para garantizar que los datos no se almacenan en un centro de datos ubicado en otro país o similar. Si opta por mantener el correo electrónico local, puede migrar el entorno de Exchange 2007 a Exchange 2010, Exchange 2013 o Exchange 2016.
  
Si no puede migrar a Microsoft 365, le recomendamos que migre a Exchange 2016. Exchange 2016 incluye todas las características de versiones anteriores de Exchange. También se ajusta mejor a la experiencia disponible en Microsoft 365, aunque algunas características solo están disponibles en Microsoft 365. Consulte sólo algunas de las cosas que ha estado perdiendo:
  
|**Versión de Exchange**|**Funciones**|
|:-----|:-----|
|Exchange 2010  <br/> | Control de acceso de Role-Based (permisos sin ACL)  <br/>  Directivas de buzones de Outlook Web App  <br/>  Capacidad para compartir calendarios de disponibilidad y de delegado entre organizaciones  <br/> |
|Exchange 2013  <br/> | *Características de Exchange 2010 y...*  <br/>  Arquitectura simplificada que ha reducido el número de roles de servidor a tres (buzón de correo, acceso de cliente y transporte perimetral)  <br/>  Directivas de prevención de pérdida de datos (DLP) que evitan la pérdida de información confidencial  <br/>  Experiencia mejorada de Outlook Web App  <br/> |
|Exchange 2016  <br/> | *Características de Exchange 2013 y...*  <br/>  Funciones de servidor más sencillas para solo buzones de correo y de transporte perimetral  <br/>  DLP mejorado junto con la integración con SharePoint  <br/>  Resistencia de base de datos mejorada  <br/>  Colaboración en documentos en línea |
   
#### <a name="which-version-should-i-migrate-to"></a>¿A qué versión debo migrar?

Le recomendamos que primero asuma que migrará a Exchange 2016. A continuación, use la siguiente información para confirmar su hipótesis o para descartar Exchange 2016. Si no puede migrar a Exchange 2016 por algún motivo, realice el mismo proceso con Exchange 2013 y así sucesivamente.
  
|**Consideración**|**Más información**|
|:-----|:-----|
|Fecha de finalización del soporte técnico  <br/> | Al igual que Exchange 2007, cada versión de Exchange tiene su propia fecha de finalización de soporte:  <br/> *Exchange 2010* -enero 2020  <br/> *Exchange 2013* -abril 2023  <br/> *Exchange 2016* -octubre 2025  <br/>  Al final del soporte, lo antes que necesitará realizar otra migración.<br/> |
|Ruta de migración a Exchange 2010 y 2013.  <br/> |Estas son las fases generales para migrar a Exchange 2010 o Exchange 2013:  <br/> -Instale Exchange 2010 o 2013 en su organización de Exchange 2007 existente. <br/>-Mueva los servicios y otra infraestructura a Exchange 2010 o 2013.<br/>-Mueva los buzones de correo y las carpetas públicas a Exchange 2010 o 2013.<br/>-Retirar los servidores de Exchange 2007 restantes. |
|Ruta de migración a Exchange 2016  <br/> |Estas son las fases generales para la migración a Exchange 2016:  <br/> -Instale Exchange 2013 en su organización de Exchange 2007 existente.<br/>-Mueva los servicios y otra infraestructura a Exchange 2013.<br/>-Mueva los buzones de correo y las carpetas públicas a Exchange 2013.<br/>-Retirar los servidores de Exchange 2007 restantes.<br/>-Instale Exchange 2016 en su organización de Exchange 2013 existente.<br/>-Mueva los buzones de correo, las carpetas públicas, los servicios y otras infraestructuras a Exchange 2016 (no importa el orden). Retirar los servidores Exchange 2013 restantes.<br/><br/> **Nota:** La migración de Exchange 2013 a Exchange 2016 es sencilla. Las dos versiones tienen casi los mismos requisitos de hardware y estas versiones son muy compatibles. Por lo tanto, puede reconstruir un servidor que compró para Exchange 2013 e instalar Exchange 2016 en él. Para los movimientos de buzones en línea, la mayoría de los usuarios incluso no observarán que su buzón de correo se movió al servidor y después lo rehizo después de haberlo reconstruido con Exchange 2016.           |
|Coexistencia de versiones  <br/> | Al migrar a...  <br/> **Exchange 2016:** Exchange 2016 no se puede instalar en una organización que incluya un servidor de Exchange 2007. Primero tendrá que migrar a Exchange 2010 o 2013 (se recomienda encarecidamente usar Exchange 2013), quitar todos los servidores de Exchange 2007 y, a continuación, migrar a Exchange 2016.  <br/> **Exchange 2010 o exchange 2013:** Puede instalar Exchange 2010 o Exchange 2013 en una organización de Exchange 2007 existente. Esto le permite instalar uno o varios servidores Exchange 2010 o 2013 y realizar la migración.  <br/> |
|Hardware de servidor  <br/> | Los requisitos de hardware del servidor han cambiado de Exchange 2007. Asegúrese de que el hardware es compatible. Para más información, vea:  <br/> [Requisitos del sistema de Exchange 2016](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx) <br/> [Requisitos del sistema de Exchange 2013](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx) <br/> [Requisitos del sistema de Exchange 2010](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx) <br/>  Descubrirá que las mejoras significativas en el rendimiento de Exchange y la potencia de procesamiento y capacidad de almacenamiento aumentadas en los servidores más modernos significan que probablemente necesitará menos servidores para admitir el mismo número de buzones.  <br/> |
|Versión del sistema operativo  <br/> | Las versiones de sistema operativo mínimas admitidas para cada versión son:  <br/> **Exchange 2016** -Windows Server 2012  <br/> **Exchange 2013** -Windows Server 2008 R2 SP1  <br/> **Exchange 2010** -Windows Server 2008 SP2  <br/>  Obtenga más información acerca del soporte del sistema operativo en la [matriz de compatibilidad de Exchange](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
|Nivel funcional del bosque de Active Directory  <br/> | Los niveles de funcionalidad de bosque de Active Directory mínimos admitidos para cada versión son:  <br/> **Exchange 2016** Windows Server 2008 R2 SP1  <br/> **Exchange 2013** Windows Server 2003  <br/> **Exchange 2010** Windows Server 2003  <br/>  Obtenga más información acerca de la compatibilidad con el nivel funcional de bosque en la [matriz de compatibilidad de Exchange](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
|Versiones de cliente de Office  <br/> | Las versiones de cliente de Office mínimas admitidas para cada versión son:  <br/> **Exchange 2016** -Office 2010 (con las actualizaciones más recientes)  <br/> **Exchange 2013** -Office 2007 SP3  <br/> **Exchange 2010** -Office 2003  <br/>  Obtenga más información sobre Office Client Support en la [matriz de compatibilidad de Exchange](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
   
#### <a name="how-do-i-migrate"></a>¿Cómo se realiza la migración?

Si decidió mantener su correo local, use los siguientes recursos para ayudarle con la migración:
  
- [Asistente para la implementación de Exchange](https://aka.ms/exdeploy)
    
- Cambios en el esquema de Active Directory para Exchange [2016](https://technet.microsoft.com/library/bb738144%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/bb738144%28v=exchg.150%29.aspx), [2010](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)
    
- Requisitos del sistema para Exchange [2016](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx), [2010](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx)
    
- Requisitos previos para Exchange [2016](https://technet.microsoft.com/library/bb691354%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/bb691354%28v=exchg.150%29.aspx), [2010](https://technet.microsoft.com/library/bb691354%28v=exchg.141%29.aspx)
    
## <a name="get-help"></a>Obtener ayuda

Si va a migrar a Microsoft 365, puede ser elegible para usar nuestro servicio Microsoft FastTrack. FastTrack proporciona los procedimientos recomendados, las herramientas y los recursos para que la migración a Microsoft 365 sea lo más fluida posible. Y lo mejor de todo es que un ingeniero de soporte técnico le guiará a través de la migración, desde la planeación y el diseño hasta la migración del último buzón. Para obtener más información acerca de FastTrack, consulte [Microsoft FastTrack](https://fasttrack.microsoft.com/).
  
Si tiene problemas durante la migración a Microsoft 365 y no usa FastTrack o migrar a una versión más reciente de Exchange Server, estamos aquí para ayudarle. Estos son algunos de los recursos que puede usar:
  
- [Comunidad de soporte técnico](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
    
- [Soporte al cliente](https://support.microsoft.com/gp/support-options-for-business)
    
## <a name="related-topics"></a>Temas relacionados

[Recursos para ayudarle a actualizar sus clientes y servidores de Office 2007](upgrade-from-office-2007-servers-and-products.md)
