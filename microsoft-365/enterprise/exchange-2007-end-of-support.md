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
description: Obtenga información sobre sus opciones después de Exchange Server de soporte técnico de 2007 y empiece a planear la migración a Microsoft 365, Office 365 o Exchange 2016.
ms.openlocfilehash: 3f0a5c8ef9765a184358b932548eaa2ae7c59adc
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519850"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Plan de fin del soporte técnico de Exchange 2007

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Exchange Server 2007 alcanzó el fin del soporte técnico en abril de 2017. Si no ha iniciado la migración de Exchange 2007 a Microsoft 365, Office 365 o Exchange 2016, ahora es el momento de empezar a planear.
  
## <a name="what-does-end-of-support-mean"></a>¿Qué significa *el fin del* soporte técnico?

Exchange Server, al igual que casi todos los productos de Microsoft, tiene un ciclo de vida de soporte durante el cual proporcionamos nuevas características, correcciones de errores, correcciones de seguridad, entre otras. Este ciclo de vida suele durar 10 años desde la versión inicial del producto. El final de este ciclo de vida se conoce como el final del soporte técnico del producto. Desde que Exchange 2007 llegó a su fin de soporte técnico el 11 de abril de 2017, Microsoft ya no proporciona:
  
- Soporte técnico para los problemas que pueden producirse.
    
- Correcciones de errores para problemas que pueden afectar a la estabilidad y facilidad de uso del servidor.
    
- Correcciones de seguridad para vulnerabilidades que pueden hacer que el servidor sea vulnerable a infracciones de seguridad.
    
- Actualizaciones de zona horaria.
    
La instalación de Exchange 2007 seguirá funcionando después de la fecha de finalización del soporte técnico. Pero como no hay nuevas actualizaciones ni soporte técnico, se recomienda encarecidamente migrar desde Exchange 2007 lo antes posible.
  
Para obtener más información acerca de los servidores de Office 2007 que se acercan al final del soporte técnico, vea Planear la actualización de productos y servidores [de Office 2007.](upgrade-from-office-2007-servers-and-products.md)
  
## <a name="what-are-my-options"></a>¿Cuáles son mis opciones?

Puede:
  
- Migrar a Microsoft 365 mediante migración híbrida, por fases o por escala.
    
- Migre los servidores de Exchange 2007 a una versión más reciente de Exchange en los servidores locales.
    
En las secciones siguientes se explora cada opción con más detalle.
  
### <a name="migrate-to-microsoft-365"></a>Migrar a Microsoft 365

Migrar el correo electrónico a Microsoft 365 es la mejor y más sencilla opción para ayudar a retirar la implementación de Exchange 2007. Con una migración a Microsoft 365, puede hacer un único salto de la tecnología de 10 años a características de última generación, como:
  
- Capacidades de cumplimiento como directivas de retención, In-Place retención por juicio, exhibición de documentos electrónicos local y mucho más
    
- Grupos de Microsoft 365
    
- Bandeja de entrada Prioritarios
    
- MyAnalytics
    
- API de REST para el acceso mediante programación al correo electrónico, calendarios, contactos, entre otros
    
Microsoft 365 también obtiene primero nuevas características y experiencias, por lo que usted y sus usuarios normalmente pueden empezar a usarlos inmediatamente. Y no tendrá que preocuparse por:
  
- Comprar y mantener hardware.
    
- Pagar al frío y refrescar los servidores.
    
- Mantenerse al día de las correcciones de seguridad, producto y zona horaria.
    
- Mantener el almacenamiento y el software para cumplir los requisitos de cumplimiento.
    
- Actualización a una nueva versión de Exchange. Con Microsoft 365, siempre está en la versión más reciente de Exchange.
    
#### <a name="how-should-i-migrate-to-microsoft-365"></a>¿Cómo debería migrar a Microsoft 365?

Tiene algunas opciones de migración. Debe tener en cuenta algunas cosas, entre las que se incluyen:

- El número de puestos o buzones que necesita mover.
- Cuánto tiempo desea que dure la migración.
- Si necesita una integración perfecta entre la instalación local y Microsoft 365 durante la migración.

En esta tabla se muestran las opciones de migración y los factores más importantes que determinan qué método usar:
  

|**Opción de migración**|**Tamaño de la organización**|**Duración**|
|:-----|:-----|:-----|
|Migración total  <br/> |Menos de 150 puestos  <br/> |Una semana o menos  <br/> |
|Migración preconfigurada  <br/> |Más de 150 puestos  <br/> |Unas pocas semanas  <br/> |
|Migración híbrida completa  <br/> |De cientos a miles de puestos  <br/> |Unos meses o más  <br/> |
   
En las secciones siguientes se proporciona información general sobre estos métodos. Para obtener más información, consulte [Decidir una ruta de migración.](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27) 
  
#### <a name="cutover-migration"></a>Migración total

En una migración total, se migran todos los buzones, grupos de distribución, contactos, entre otros, a Microsoft 365 en una fecha y hora preseleccionados. Una vez completada la migración, cierre los servidores de Exchange locales y empiece a usar Microsoft 365 exclusivamente.
  
La migración de escala es excelente para organizaciones pequeñas que no tienen muchos buzones, quieren acceder a Microsoft 365 rápidamente y no quieren tratar algunas de las complejidades de los otros métodos. Pero debe completarse en una semana o menos y requiere que los usuarios vuelvan a configurar sus perfiles de Outlook. La migración de todo puede controlar hasta 2.000 buzones, pero se recomienda encarecidamente que la use para migrar un máximo de 150 buzones. Si intenta migrar más, puede que se le agote el tiempo para transferir todos los buzones antes de la fecha límite, y el personal de soporte técnico de TI puede saturarse con solicitudes para ayudar a los usuarios a reconfigurar Outlook.
  
Si está pensando en realizar una migración de escala, tenga en cuenta lo siguiente:
  
- Microsoft 365 tendrá que conectarse a los servidores de Exchange 2007 mediante Outlook en cualquier lugar a través del puerto TCP 443.
    
- Todos los buzones locales se trasladarán a Microsoft 365.
    
- Necesitará una cuenta de administrador local que tenga acceso de lectura a los buzones de los usuarios.
    
- Los dominios aceptados de Exchange 2007 que desea usar en Microsoft 365 deben agregarse como dominios comprobados en el servicio.
    
- Entre el momento en que se inicia la migración y cuando se inicia la fase de finalización, Microsoft 365 sincronizará periódicamente los buzones de Microsoft 365 y los buzones locales. Esto le permite completar la migración sin preocuparse de que el correo electrónico se deje en sus buzones locales.
    
- Los usuarios recibirán nuevas contraseñas temporales para sus cuentas de Microsoft 365. Necesitarán cambiar su contraseña cuando inicien sesión en su buzón por primera vez.
    
- Necesitará una licencia de Microsoft 365 que incluya Exchange Online para cada buzón de usuario que migre.
    
- Los usuarios tendrán que configurar un nuevo perfil de Outlook en cada uno de sus dispositivos y volver a descargar su correo electrónico. La cantidad de correo electrónico que Outlook descargará puede variar. Para obtener más información, [vea Cambiar la cantidad de correo que se va a mantener sin conexión.](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)
    
Para obtener más información acerca de la migración de escala, vea:
  
- [Lo que necesita saber sobre una migración de correo electrónico de escala](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
    
- [Realizar una migración de correo electrónico](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)
    
#### <a name="staged-migration"></a>Migración preconfigurada

En una migración por fases, tiene unos cientos o unos pocos miles de buzones que desea migrar a Microsoft 365, necesita tardar una semana o más en completar la migración y no necesita ninguna de las características avanzadas de la migración híbrida, como la información de calendario de disponibilidad compartida.
  
La migración por fases es excelente para las organizaciones que necesitan tardar más tiempo en migrar sus buzones a Microsoft 365, pero que aún planean completar la migración en unas pocas semanas. Puede migrar buzones en lotes. Puede controlar cuántos y qué buzones se migran en un momento determinado. Puede procesar por lotes buzones de correo de usuarios del mismo departamento, por ejemplo, para asegurarse de que se mueven todos al mismo tiempo. O bien, puede dejar buzones ejecutivos hasta el último lote. Al igual que con las migraciones de escala, los usuarios tendrán que volver a crear sus perfiles de Outlook.
  
Si está pensando en realizar una migración por fases, tenga en cuenta lo siguiente:
  
- Microsoft 365 tendrá que conectarse a los servidores de Exchange 2007 mediante Outlook en cualquier lugar a través del puerto TCP 443.
    
- Necesitará una cuenta de administrador local que tenga acceso de lectura a los buzones de los usuarios.
    
- Los dominios aceptados de Exchange 2007 que planea usar en Microsoft 365 deben agregarse como dominios comprobados en el servicio.
    
- Deberá crear un archivo CSV con el nombre completo y la dirección de correo electrónico de cada buzón que planee migrar en un lote. También deberá incluir una nueva contraseña para cada buzón que va a migrar y enviar esa contraseña a cada usuario. Se pedirá al usuario que cambie la contraseña la primera vez que inicie sesión en su nuevo buzón de Microsoft 365.
    
- Entre el momento en que se inicia el lote de migración y cuando se inicia la fase de finalización, Microsoft 365 sincronizará periódicamente los buzones locales y de Microsoft 365 incluidos en el lote. Esto le permite completar la migración sin preocuparse de que el correo electrónico se deje en sus buzones locales.
    
- Necesitará una licencia de Microsoft 365 que incluya Exchange Online para cada buzón de usuario que migre.
    
- Los usuarios tendrán que configurar un nuevo perfil de Outlook en cada uno de sus dispositivos y volver a descargar su correo electrónico. La cantidad de correo electrónico que Outlook descargará puede variar. Para obtener más información, [vea Cambiar la cantidad de correo que se va a mantener sin conexión.](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)
    
Para obtener más información acerca de la migración por fases, vea:
  
- [Lo que necesita saber sobre una migración de correo electrónico por fases](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)
    
- [Realizar una migración por fases de correo electrónico](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)
    
#### <a name="full-hybrid"></a>Híbrido completo

En una migración híbrida completa, su organización tiene muchos cientos, hasta decenas de miles, de buzones y desea mover algunos o todos a Microsoft 365. Dado que estas migraciones suelen ser a más largo plazo, las migraciones híbridas hacen posible lo siguiente:
  
- Mostrar a los usuarios locales la información de calendario de disponibilidad de los usuarios de Microsoft 365 y viceversa.
    
- Vea una lista global unificada de direcciones que contiene destinatarios tanto en local como en Microsoft 365.
    
- Ver las propiedades de destinatario de Outlook completa para todos los usuarios, independientemente de si son locales o de Microsoft 365.
    
- Proteger la comunicación por correo electrónico entre los servidores de Exchange locales y Microsoft 365 mediante TLS y certificados.
    
- Trate los mensajes enviados entre los servidores de Exchange locales y Microsoft 365 como internos, lo que les permite:
    
  - Sean evaluados y procesados correctamente por agentes de transporte y cumplimiento destinados a mensajes internos.
    
  - Omitir filtros contra correo no deseado.
    
La migración híbrida completa es la mejor para las organizaciones que esperan permanecer en una configuración híbrida durante varios meses o más. Verá las características enumeradas anteriormente en esta sección, además de la sincronización de directorios, las mejores características de cumplimiento integradas y la capacidad de mover buzones a y desde Microsoft 365 mediante movimientos de buzones en línea. Microsoft 365 se convierte en una extensión de su organización local.
  
Si está pensando en realizar una migración híbrida completa, tenga en cuenta lo siguiente:
  
- La migración híbrida completa no es adecuada para todos los tipos de organizaciones. Debido a la complejidad de las migraciones híbridas completa, las organizaciones con menos de unos pocos cientos de buzones no suelen ver ventajas que justifican el esfuerzo y el costo necesarios para configurar uno. Si esto se parece a su organización, le recomendamos que considere una migración por fases o por escala en su lugar.
    
- Deberá implementar al menos un servidor de Exchange 2013 en su organización de Exchange 2007 para actuar como un "servidor híbrido". Este servidor se comunicará con Microsoft 365 en nombre de sus servidores de Exchange 2007.
    
- Microsoft 365 tendrá que conectarse al "servidor híbrido" mediante Outlook en cualquier lugar a través del puerto TCP 443.
    
- Deberá configurar la sincronización de directorios con Azure Active Directory (Azure AD) Connect entre los servidores locales de Active Directory y Microsoft 365.
    
- Los usuarios podrán iniciar sesión en su buzón de Microsoft 365 con el mismo nombre de usuario y contraseña que cuando inicien sesión en la red local. (Esta funcionalidad requiere Azure AD Connect con sincronización de contraseñas o servicios de federación de Active Directory).
    
- Necesitará una licencia de Microsoft 365 que incluya Exchange Online para cada buzón de usuario que migre.
    
- Los usuarios no necesitan configurar un nuevo perfil de Outlook en la mayoría de sus dispositivos, aunque es posible que algunos teléfonos Android más antiguos necesiten un nuevo perfil. Los usuarios no tendrán que volver a descargar su correo electrónico.
    
Si la migración híbrida completa le parece adecuada, consulte los siguientes recursos para ayudarle con la migración:
  
- [Asistente para la implementación de Exchange](https://aka.ms/exdeploy)
    
- [Implementaciones híbridas de Exchange Server](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx)
    
- [Asistente de configuración híbrida](https://technet.microsoft.com/library/hh529921%28v=exchg.150%29.aspx)
    
- [Preguntas más frecuentes acerca del asistente de configuración híbrida](https://technet.microsoft.com/library/mt488940%28v=exchg.150%29.aspx)
    
- [Requisitos previos para la implementación híbrida](https://technet.microsoft.com/library/hh534377%28v=exchg.150%29.aspx)
    
### <a name="migrate-to-a-newer-version-of-exchange-server"></a>Migrar a una versión más reciente de Exchange Server

Creemos que puede lograr el mejor valor y experiencia de usuario migrando a Microsoft 365. Pero también sabemos que algunas organizaciones necesitan mantener su correo electrónico local. Esto puede deberse a requisitos normativos, para garantizar que los datos no se almacenan en un centro de datos ubicado en otro país o similar. Si decide mantener el correo electrónico local, puede migrar su entorno de Exchange 2007 a Exchange 2010, Exchange 2013 o Exchange 2016.
  
Si no puede migrar a Microsoft 365, le recomendamos que migre a Exchange 2016. Exchange 2016 incluye todas las características de versiones anteriores de Exchange. También coincide más estrechamente con la experiencia disponible con Microsoft 365, aunque algunas características solo están disponibles en Microsoft 365. Echa un vistazo a algunas de las cosas que te han faltado:
  
|**Versión de Exchange**|**Funciones**|
|:-----|:-----|
|Exchange 2010  <br/> | Role-Based control de acceso (permisos sin ACL)  <br/>  Directivas de buzones de Outlook Web App  <br/>  Capacidad de compartir calendarios de disponibilidad y delegados entre organizaciones  <br/> |
|Exchange 2013  <br/> | *Características de Exchange 2010 y ...*  <br/>  Arquitectura simplificada que redujo el número de roles de servidor a tres (buzón, acceso de cliente, transporte perimetral)  <br/>  Directivas de prevención de pérdida de datos (DLP) que ayudan a evitar la pérdida de información confidencial  <br/>  Experiencia mejorada de Outlook Web App  <br/> |
|Exchange 2016  <br/> | *Características de Exchange 2013 y ...*  <br/>  Roles de servidor simplificados adicionales solo para buzón de correo y transporte perimetral  <br/>  DLP mejorado junto con la integración con SharePoint  <br/>  Resistencia de base de datos mejorada  <br/>  Colaboración de documentos en línea |
   
#### <a name="which-version-should-i-migrate-to"></a>¿A qué versión debo migrar?

Le recomendamos que inicialmente suponga que migrará a Exchange 2016. A continuación, use la siguiente información para confirmar su suposición o para descartar Exchange 2016. Si no puede migrar a Exchange 2016 por algún motivo, realice el mismo proceso con Exchange 2013, y así sucesivamente.
  
|**Consideración**|**Más información**|
|:-----|:-----|
|Fechas de finalización del soporte técnico  <br/> | Al igual que Exchange 2007, cada versión de Exchange tiene su propia fecha de finalización de soporte técnico:  <br/> *Exchange 2010* - Enero de 2020  <br/> *Exchange 2013* - Abril de 2023  <br/> *Exchange 2016* - Octubre de 2025  <br/>  Cuanto antes finalice el soporte técnico, más pronto tendrá que realizar otra migración.<br/> |
|Ruta de migración a Exchange 2010 y 2013.  <br/> |Estas son las fases generales para migrar a Exchange 2010 o Exchange 2013:  <br/> - Instale Exchange 2010 o 2013 en su organización existente de Exchange 2007. <br/>- Mover servicios y otra infraestructura a Exchange 2010 o 2013.<br/>- Mover buzones y carpetas públicas a Exchange 2010 o 2013.<br/>- Retirar los servidores de Exchange 2007 restantes. |
|Ruta de migración a Exchange 2016  <br/> |Estas son las fases generales para migrar a Exchange 2016:  <br/> - Instale Exchange 2013 en su organización de Exchange 2007 existente.<br/>- Mover servicios y otra infraestructura a Exchange 2013.<br/>- Mover buzones y carpetas públicas a Exchange 2013.<br/>- Retirar los servidores de Exchange 2007 restantes.<br/>- Instale Exchange 2016 en su organización de Exchange 2013 existente.<br/>- Mover buzones de correo, carpetas públicas, servicios y otra infraestructura a Exchange 2016 (el orden no importa). Retirar los servidores de Exchange 2013 restantes.<br/><br/> **Nota:** Migrar de Exchange 2013 a Exchange 2016 es sencillo. Las dos versiones tienen casi los mismos requisitos de hardware, y estas versiones son muy compatibles. Por lo tanto, puede recompilar un servidor que compró para Exchange 2013 e instalar Exchange 2016 en él. Para los movimientos de buzones en línea, la mayoría de los usuarios ni siquiera se darán cuenta de que su buzón se movió del servidor y, a continuación, volverá después de volver a crearlo con Exchange 2016.           |
|Coexistencia de versiones  <br/> | Al migrar a...  <br/> **Exchange 2016:** Exchange 2016 no se puede instalar en una organización que incluya un servidor de Exchange 2007. Primero tendrá que migrar a Exchange 2010 o 2013 (se recomienda encarecidamente Exchange 2013), quitar todos los servidores de Exchange 2007 y, a continuación, migrar a Exchange 2016.  <br/> **Exchange 2010 o Exchange 2013:** Puede instalar Exchange 2010 o Exchange 2013 en una organización existente de Exchange 2007. Esto le permite instalar uno o más servidores de Exchange 2010 o 2013 y realizar la migración.  <br/> |
|Hardware de servidor  <br/> | Los requisitos de hardware del servidor han cambiado desde Exchange 2007. Asegúrese de que el hardware es compatible. Para más información, vea:  <br/> [Requisitos del sistema de Exchange 2016](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx) <br/> [Requisitos del sistema de Exchange 2013](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx) <br/> [Requisitos del sistema de Exchange 2010](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx) <br/>  Verá que las mejoras significativas en el rendimiento de Exchange y el aumento de la capacidad informática y de almacenamiento en servidores más recientes significan que probablemente necesitará menos servidores para admitir el mismo número de buzones.  <br/> |
|Versión del sistema operativo  <br/> | Las versiones mínimas admitidas del sistema operativo para cada versión son:  <br/> **Exchange 2016** - Windows Server 2012  <br/> **Exchange 2013** - Windows Server 2008 R2 SP1  <br/> **Exchange 2010** - Windows Server 2008 SP2  <br/>  Encontrará más información sobre la compatibilidad con el sistema operativo en [la matriz de compatibilidad de Exchange.](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx)  <br/> |
|Nivel funcional del bosque de Active Directory  <br/> | Los niveles funcionales mínimos admitidos del bosque de Active Directory para cada versión son:  <br/> **Exchange 2016** Windows Server 2008 R2 SP1  <br/> **Exchange 2013** Windows Server 2003  <br/> **Exchange 2010** Windows Server 2003  <br/>  Encontrará más información sobre la compatibilidad con el nivel funcional del bosque en [la matriz de compatibilidad de Exchange.](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx)  <br/> |
|Versiones de cliente de Office  <br/> | Las versiones mínimas de cliente de Office admitidas para cada versión son:  <br/> **Exchange 2016** - Office 2010 (con las últimas actualizaciones)  <br/> **Exchange 2013** - Office 2007 SP3  <br/> **Exchange 2010** - Office 2003  <br/>  Encontrará más información sobre la compatibilidad con clientes de Office en [la matriz de compatibilidad de Exchange.](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx)  <br/> |
   
#### <a name="how-do-i-migrate"></a>¿Cómo puedo migrar?

Si decide mantener el correo electrónico local, use los siguientes recursos para ayudarle con la migración:
  
- [Asistente para la implementación de Exchange](https://aka.ms/exdeploy)
    
- Cambios en el esquema de Active Directory para Exchange [2016](https://technet.microsoft.com/library/bb738144%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/bb738144%28v=exchg.150%29.aspx), [2010](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)
    
- Requisitos del sistema para Exchange [2016](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx), [2010](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx)
    
- Requisitos previos para Exchange [2016](https://technet.microsoft.com/library/bb691354%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/bb691354%28v=exchg.150%29.aspx), [2010](https://technet.microsoft.com/library/bb691354%28v=exchg.141%29.aspx)
    
## <a name="get-help"></a>Obtener ayuda

Si va a migrar a Microsoft 365, es posible que sea apto para usar nuestro servicio Microsoft FastTrack. FastTrack proporciona procedimientos recomendados, herramientas y recursos para que la migración a Microsoft 365 sea lo más sencilla posible. Lo mejor de todo es que un ingeniero de soporte técnico le ayudará a través de la migración, desde la planeación y el diseño hasta la migración del último buzón. Para obtener más información sobre FastTrack, vea [Microsoft FastTrack](https://fasttrack.microsoft.com/).
  
Si tiene problemas durante la migración a Microsoft 365 y no usa FastTrack o la migración a una versión más reciente de Exchange Server, estamos aquí para ayudarle. Estos son algunos recursos que puede usar:
  
- [Comunidad de soporte técnico](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
    
- [Soporte al cliente](https://support.microsoft.com/gp/support-options-for-business)
    
## <a name="related-topics"></a>Temas relacionados

[Recursos para ayudarle a actualizar los clientes y servidores de Office 2007](upgrade-from-office-2007-servers-and-products.md)
