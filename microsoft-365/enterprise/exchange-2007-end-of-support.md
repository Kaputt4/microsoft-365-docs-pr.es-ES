---
title: Plan de fin del soporte técnico de Exchange 2007
ms.author: dstrome
author: dstrome
manager: scotv
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
ms.assetid: c3024358-326b-404e-9fe6-b618e54d977d
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: Obtenga información sobre las opciones después de Exchange Server finalización del soporte técnico de 2007 y comience a planear la migración a Microsoft 365, Office 365 o Exchange 2016.
ms.openlocfilehash: 7b8cad31c04d5cd1cd9e618e8e38e872a1b32634
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65092677"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Plan de fin del soporte técnico de Exchange 2007

*Este artículo se aplica tanto a Microsoft 365 Enterprise como a Office 365 Enterprise.*

Exchange Server 2007 llegó a su fin en abril de 2017. Si no ha iniciado la migración de Exchange 2007 a Microsoft 365, Office 365 o Exchange 2016, ahora es el momento de empezar a planear.

## <a name="what-does-end-of-support-mean"></a>¿Qué significa *el fin del soporte* técnico?

Exchange Server, como casi todos los productos de Microsoft, tiene un ciclo de vida de soporte técnico durante el cual proporcionamos nuevas características, correcciones de errores, correcciones de seguridad, etc. Este ciclo de vida suele durar 10 años a partir de la versión inicial del producto. El final de este ciclo de vida se conoce como el fin del soporte técnico del producto. Desde Exchange 2007 llegó a su fin de soporte técnico el 11 de abril de 2017, Microsoft ya no proporciona:

- Soporte técnico para los problemas que pueden producirse.

- Correcciones de errores para problemas que pueden afectar a la estabilidad y facilidad de uso del servidor.

- Correcciones de seguridad para las vulnerabilidades que pueden hacer que el servidor sea vulnerable a infracciones de seguridad.

- Actualizaciones de zona horaria.

La instalación de Exchange 2007 continuará ejecutándose después de la fecha de finalización del soporte técnico. Pero como no hay actualizaciones ni soporte técnico nuevos, se recomienda encarecidamente migrar desde Exchange 2007 lo antes posible.

Para obtener más información sobre Office servidores de 2007 que están a punto de finalizar el soporte técnico, consulte [Planeamiento de la actualización desde Office productos y servidores de 2007](upgrade-from-office-2007-servers-and-products.md).

## <a name="what-are-my-options"></a>¿Cuáles son mis opciones?

Puede:

- Migre a Microsoft 365 mediante la migración temporal, preconfigurada o híbrida.

- Migre los servidores Exchange 2007 a una versión más reciente de Exchange en los servidores locales.

En las secciones siguientes se explora cada opción con más detalle.

### <a name="migrate-to-microsoft-365"></a>Migrar a Microsoft 365

Migrar el correo electrónico a Microsoft 365 es la mejor y más sencilla opción para ayudar a retirar la implementación de Exchange 2007. Con una migración a Microsoft 365, puede realizar un salto único desde la tecnología de 10 años hasta las características de última generación, entre las que se incluyen:

- Funcionalidades de cumplimiento, como directivas de retención, In-Place y suspensión por juicio, exhibición de documentos electrónicos en contexto, etc.

- Grupos de Microsoft 365

- Bandeja de entrada Prioritarios

- MyAnalytics

- API REST para el acceso mediante programación al correo electrónico, calendarios, contactos, etc.

Microsoft 365 también obtiene nuevas características y experiencias en primer lugar, por lo que usted y los usuarios pueden empezar a usarlos de inmediato. Y no tendrá que preocuparse por:

- Compra y mantenimiento de hardware.

- Pagar por calentar y enfriar los servidores.

- Mantenerse al día sobre las correcciones de seguridad, productos y zonas horarias.

- Mantener el almacenamiento y el software para admitir los requisitos de cumplimiento.

- Actualización a una nueva versión de Exchange. Con Microsoft 365, siempre está en la versión más reciente de Exchange.

#### <a name="how-should-i-migrate-to-microsoft-365"></a>¿Cómo debo migrar a Microsoft 365?

Tiene algunas opciones de migración. Debe tener en cuenta algunas cosas, entre las que se incluyen:

- El número de puestos o buzones que necesita mover.
- Cuánto tiempo desea que dure la migración.
- Si necesita una integración perfecta entre la instalación local y Microsoft 365 durante la migración.

En esta tabla se muestran las opciones de migración y los factores más importantes que determinan qué método usar:

|Opción de migración|Tamaño de la organización|Duración|
|---|---|---|
|Migración total|Menos de 150 puestos|Una semana o menos|
|Migración preconfigurada|Más de 150 puestos|Unas semanas|
|Migración híbrida completa|Varios cientos o miles de asientos|Unos meses o más|

En las secciones siguientes se proporciona información general sobre estos métodos. Para obtener más detalles, consulte [Decidir una ruta de migración](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27).

#### <a name="cutover-migration"></a>Migración total

En una migración de transición, se migran todos los buzones, grupos de distribución, contactos, etc., a Microsoft 365 en una fecha y hora preseleccionadas. Una vez completada la migración, apagará los servidores de Exchange locales y comenzará a usar Microsoft 365 exclusivamente.

La migración de transición es ideal para organizaciones pequeñas que no tienen muchos buzones de correo, quieren llegar a Microsoft 365 rápidamente y no quieren tratar con algunas de las complejidades de los otros métodos. Pero debe completarse en una semana o menos y requiere que los usuarios vuelvan a configurar sus perfiles de Outlook. La migración de transición puede controlar hasta 2000 buzones, pero se recomienda encarecidamente usarla para migrar un máximo de 150 buzones. Si intenta migrar más, podría quedar sin tiempo para transferir todos los buzones antes de la fecha límite, y el personal de soporte técnico de TI puede verse abrumado por las solicitudes para ayudar a los usuarios a volver a configurar Outlook.

Si está pensando en realizar una migración de transición, estas son las cosas que debe tener en cuenta:

- Microsoft 365 tendrá que conectarse a los servidores Exchange 2007 mediante Outlook Anywhere a través del puerto TCP 443.

- Todos los buzones locales se moverán a Microsoft 365.

- Necesitará una cuenta de administrador local que tenga acceso de lectura a los buzones de los usuarios.

- Los dominios aceptados de Exchange 2007 que desea usar en Microsoft 365 deben agregarse como dominios comprobados en el servicio.

- Entre el momento en que se inicia la migración y la fase de finalización, Microsoft 365 sincronizará periódicamente los buzones de Microsoft 365 y locales. Esto le permite completar la migración sin preocuparse de que el correo electrónico se quede atrás en los buzones locales.

- Los usuarios recibirán nuevas contraseñas temporales para sus cuentas de Microsoft 365. Tendrán que cambiar su contraseña cuando inicien sesión en su buzón por primera vez.

- Necesitará una licencia de Microsoft 365 que incluya Exchange Online para cada buzón de usuario que migre.

- Los usuarios tendrán que configurar un nuevo perfil de Outlook en cada uno de sus dispositivos y volver a descargar su correo electrónico. La cantidad de correo electrónico que Outlook descargará puede variar. Para obtener más información, vea [Cambiar la cantidad de correo que se debe mantener sin conexión](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).

Para obtener más información sobre la migración de transición, consulte:

- [Lo que necesita saber sobre una migración de correo electrónico de transición](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)

- [Realizar una migración total del correo electrónico](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)

#### <a name="staged-migration"></a>Migración preconfigurada

En una migración preconfigurada, tiene unos cientos o varios miles de buzones que desea migrar a Microsoft 365, necesita tardar una semana o más para completar la migración y no necesita ninguna de las características de migración híbrida avanzadas, como la información de calendario de disponibilidad compartida.

La migración por fases es excelente para las organizaciones que necesitan más tiempo para migrar sus buzones a Microsoft 365, pero que aún planean completar la migración en unas semanas. Puede migrar buzones en lotes. Puede controlar cuántos y qué buzones se migran en un momento determinado. Puede procesar por lotes buzones de los usuarios del mismo departamento, por ejemplo, para asegurarse de que se mueven todos al mismo tiempo. O bien, puede dejar buzones ejecutivos hasta el último lote. Al igual que con las migraciones de transición, los usuarios tendrán que volver a crear sus perfiles de Outlook.

Si está pensando en realizar una migración por fases, estas son las cosas que debe tener en cuenta:

- Microsoft 365 tendrá que conectarse a los servidores Exchange 2007 mediante Outlook Anywhere a través del puerto TCP 443.

- Necesitará una cuenta de administrador local que tenga acceso de lectura a los buzones de los usuarios.

- Los dominios aceptados de Exchange 2007 que tiene previsto usar en Microsoft 365 deben agregarse como dominios comprobados en el servicio.

- Tendrá que crear un archivo CSV con el nombre completo y la dirección de correo electrónico de cada buzón que planee migrar en un lote. También deberá incluir una nueva contraseña para cada buzón de correo que va a migrar y enviar esa contraseña a cada usuario. Se pedirá al usuario que cambie la contraseña la primera vez que inicie sesión en su nuevo buzón de Microsoft 365.

- Entre el momento en que inicie el lote de migración y cuando comience la fase de finalización, Microsoft 365 sincronizará periódicamente los buzones de Microsoft 365 y locales incluidos en el lote. Esto le permite completar la migración sin preocuparse de que el correo electrónico se quede atrás en los buzones locales.

- Necesitará una licencia de Microsoft 365 que incluya Exchange Online para cada buzón de usuario que migre.

- Los usuarios tendrán que configurar un nuevo perfil de Outlook en cada uno de sus dispositivos y volver a descargar su correo electrónico. La cantidad de correo electrónico que Outlook descargará puede variar. Para obtener más información, vea [Cambiar la cantidad de correo que se debe mantener sin conexión](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).

Para obtener más información sobre la migración preconfigurada, consulte:

- [Lo que necesita saber sobre una migración de correo electrónico preconfigurada](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)

- [Realizar una migración provisional del correo electrónico](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)

#### <a name="full-hybrid"></a>Híbrido completo

En una migración híbrida completa, su organización tiene muchos cientos, hasta decenas de miles, de buzones de correo y quiere mover algunos o todos ellos a Microsoft 365. Como estas migraciones suelen ser a largo plazo, las migraciones híbridas permiten:

- Muestre a los usuarios locales la información del calendario de disponibilidad para los usuarios de Microsoft 365 y viceversa.

- Vea una lista de direcciones global unificada que contenga destinatarios tanto en el entorno local como en Microsoft 365.

- Vea las propiedades completas de Outlook destinatario para todos los usuarios, independientemente de si son locales o en Microsoft 365.

- Proteja la comunicación por correo electrónico entre servidores de Exchange locales y Microsoft 365 mediante TLS y certificados.

- Trate los mensajes enviados entre servidores de Exchange locales y Microsoft 365 como internos, lo que les permite:

  - Los agentes de transporte y cumplimiento deben evaluar y procesar correctamente los mensajes internos.

  - Omita los filtros antispam.

La migración híbrida completa es mejor para las organizaciones que esperan permanecer en una configuración híbrida durante muchos meses o más. Obtendrá las características enumeradas anteriormente en esta sección, además de la sincronización de directorios, las características de cumplimiento mejor integradas y la capacidad de mover buzones de correo hacia y desde Microsoft 365 mediante movimientos de buzones en línea. Microsoft 365 se convierte en una extensión de la organización local.

Si está pensando en realizar una migración híbrida completa, estas son las cosas que debe tener en cuenta:

- La migración híbrida completa no es adecuada para todos los tipos de organizaciones. Debido a la complejidad de las migraciones híbridas completas, las organizaciones con menos de unos cientos de buzones no suelen ver ventajas que justifiquen el esfuerzo y el costo necesario para configurar uno. Si esto suena a su organización, le recomendamos que considere una migración por fases o de transición en su lugar.

- Tendrá que implementar al menos un servidor de Exchange 2013 en la organización de Exchange 2007 para que actúe como un "servidor híbrido". Este servidor se comunicará con Microsoft 365 en nombre de los servidores Exchange 2007.

- Microsoft 365 tendrá que conectarse al "servidor híbrido" mediante Outlook Anywhere a través del puerto TCP 443.

- Tendrá que configurar la sincronización de directorios mediante Conectar de Azure Active Directory (Azure AD) entre los servidores de Active Directory local y Microsoft 365.

- Los usuarios podrán iniciar sesión en su buzón de Microsoft 365 con el mismo nombre de usuario y contraseña que cuando inician sesión en la red local. (Esta funcionalidad requiere Azure AD Conectar con sincronización de contraseñas o Servicios de federación de Active Directory (AD FS)).

- Necesitará una licencia de Microsoft 365 que incluya Exchange Online para cada buzón de usuario que migre.

- Los usuarios no necesitan configurar un nuevo perfil de Outlook en la mayoría de sus dispositivos, aunque algunos teléfonos Android más antiguos podrían necesitar un nuevo perfil. Los usuarios no tendrán que volver a descargar su correo electrónico.

Si la migración híbrida completa le parece adecuada, consulte los siguientes recursos para ayudarle con la migración:

- [Asistente para la implementación de Exchange](/exchange/exchange-deployment-assistant)

- [Implementaciones híbridas de Exchange Server](/exchange/exchange-hybrid)

- [Asistente de configuración híbrida](/exchange/hybrid-configuration-wizard)

- [Preguntas más frecuentes acerca del asistente de configuración híbrida](/exchange/hybrid-configuration-wizard-faqs)

- [Requisitos previos para la implementación híbrida](/exchange/hybrid-deployment-prerequisites)

### <a name="migrate-to-a-newer-version-of-exchange-server"></a>Migración a una versión más reciente de Exchange Server

Creemos firmemente que puede lograr el mejor valor y la experiencia del usuario mediante la migración a Microsoft 365. Pero también entendemos que algunas organizaciones necesitan mantener su correo electrónico local. Esto podría deberse a requisitos normativos, para garantizar que los datos no se almacenan en un centro de datos ubicado en otro país, o similar. Si decide mantener el correo electrónico local, puede migrar el entorno de Exchange 2007 a Exchange 2010, Exchange 2013 o Exchange 2016.

Si no puede migrar a Microsoft 365, se recomienda migrar a Exchange 2016. Exchange 2016 incluye todas las características de las versiones anteriores de Exchange. También coincide con la experiencia disponible con Microsoft 365, aunque algunas características solo están disponibles en Microsoft 365. Echa un vistazo a algunas de las cosas que te han faltado:

|Exchange versión|Características|
|---|---|
|Exchange 2010| Role-Based Access Control (permisos sin ACL) <br/> Directivas de buzones de Outlook Web App <br/> Capacidad de compartir calendarios de disponibilidad y delegados entre organizaciones|
|Exchange 2013| *Características de Exchange 2010 y ...* <br/> Arquitectura simplificada que redujo el número de roles de servidor a tres (buzón, acceso de cliente, transporte perimetral) <br/> Directivas de prevención de pérdida de datos (DLP) que ayudan a evitar que se filtre información confidencial <br/> Experiencia de Outlook Web App mejorada|
|Exchange 2016| *Características de Exchange 2013 y ...* <br/> Roles de servidor más simplificados para solo buzón y transporte perimetral <br/> DLP mejorado junto con la integración con SharePoint <br/> Resistencia mejorada de la base de datos <br/> Colaboración de documentos en línea|

#### <a name="which-version-should-i-migrate-to"></a>¿A qué versión debo migrar?

Se recomienda suponer inicialmente que migrará a Exchange 2016. A continuación, use la siguiente información para confirmar su suposición o para descartar Exchange 2016. Si no puede migrar a Exchange 2016 por algún motivo, realice el mismo proceso con Exchange 2013, etc.

|Consideración|Más información|
|---|---|
|Fechas de finalización del soporte técnico| Al igual que Exchange 2007, cada versión de Exchange tiene su propia fecha de finalización de soporte técnico: <br/> *Exchange 2010* - Enero de 2020 <br/> *Exchange 2013* - Abril de 2023 <br/> *Exchange 2016* - Octubre de 2025 <br/> Cuanto antes finalice el soporte técnico, antes tendrá que realizar otra migración.|
|Ruta de migración a Exchange 2010 y 2013.|Estas son las fases generales para migrar a Exchange 2010 o Exchange 2013: <br/> - Instale Exchange 2010 o 2013 en la organización de Exchange 2007 existente. <br/>- Traslado de servicios y otra infraestructura a Exchange 2010 o 2013.<br/>- Mover buzones y carpetas públicas a Exchange 2010 o 2013.<br/>- Retirar los servidores restantes Exchange 2007.|
|Ruta de migración a Exchange 2016|Estas son las fases generales para migrar a Exchange 2016: <br/> - Instale Exchange 2013 en la organización de Exchange 2007 existente.<br/>- Traslado de servicios y otras infraestructuras a Exchange 2013.<br/>- Mover buzones y carpetas públicas a Exchange 2013.<br/>- Retirar los servidores restantes Exchange 2007.<br/>- Instale Exchange 2016 en la organización de Exchange 2013 existente.<br/>- Mover buzones, carpetas públicas, servicios y otra infraestructura a Exchange 2016 (el orden no importa). Retirar los servidores restantes Exchange 2013.<br/><br/> **Nota:** Migrar de Exchange 2013 a Exchange 2016 es sencillo. Las dos versiones tienen casi los mismos requisitos de hardware, y estas versiones son muy compatibles. Por lo tanto, puede volver a generar un servidor que compró para Exchange 2013 e instalar Exchange 2016 en él. En el caso de los movimientos de buzón en línea, la mayoría de los usuarios ni siquiera notará que su buzón se ha movido del servidor y, después, lo ha vuelto a crear con Exchange 2016.|
|Coexistencia de versiones| Al migrar a ... <br/> **Exchange 2016:** Exchange 2016 no se puede instalar en una organización que incluya un servidor Exchange 2007. Primero tendrá que migrar a Exchange 2010 o 2013 (se recomienda encarecidamente Exchange 2013), quitar todos los servidores Exchange 2007 y, a continuación, migrar a Exchange 2016. <br/> **Exchange 2010 o Exchange 2013:** puede instalar Exchange 2010 o Exchange 2013 en una organización existente de Exchange 2007. Esto le permite instalar uno o varios servidores Exchange 2010 o 2013 y realizar la migración.|
|Hardware de servidor| Los requisitos de hardware del servidor han cambiado desde Exchange 2007. Asegúrese de que el hardware es compatible. Para más información, vea: <br/> [Requisitos del sistema de Exchange 2016](/Exchange/plan-and-deploy/system-requirements) <br/> [Requisitos del sistema de Exchange 2013](/exchange/exchange-2013-system-requirements-exchange-2013-help) <br/> [Requisitos del sistema de Exchange 2010](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141)) <br/> Verá que las mejoras significativas en el rendimiento de Exchange y el aumento de la capacidad de computación y almacenamiento en servidores más recientes significan que probablemente necesitará menos servidores para admitir el mismo número de buzones.|
|Versión del sistema operativo| Las versiones mínimas del sistema operativo admitidas para cada versión son: <br/> **Exchange 2016**: Windows Server 2012 <br/> **Exchange 2013**: Windows Server 2008 R2 SP1 <br/> **Exchange 2010**: Windows Server 2008 SP2 <br/> Obtenga más información sobre la compatibilidad con el sistema operativo en [Exchange Matriz de compatibilidad](/Exchange/plan-and-deploy/supportability-matrix).|
|Nivel funcional del bosque de Active Directory| Los niveles funcionales mínimos admitidos del bosque de Active Directory para cada versión son: <br/> **Exchange 2016** Windows Server 2008 R2 SP1 <br/> **Exchange 2013** Windows Server 2003 <br/> **Exchange 2010** Windows Server 2003 <br/> Obtenga más información sobre la compatibilidad con el nivel funcional del bosque en [Exchange Matriz de compatibilidad](/Exchange/plan-and-deploy/supportability-matrix).|
|Office versiones de cliente| Las versiones de cliente Office mínimas admitidas para cada versión son: <br/> **Exchange 2016**- Office 2010 (con las actualizaciones más recientes) <br/> **Exchange 2013**: Office 2007 SP3 <br/> **Exchange 2010** - Office 2003 <br/> Obtenga más información sobre Office compatibilidad con clientes en [Exchange Matriz de compatibilidad](/Exchange/plan-and-deploy/supportability-matrix).|

#### <a name="how-do-i-migrate"></a>Cómo migrar?

Si decide mantener el correo electrónico local, use los siguientes recursos para ayudar con la migración:

- [Asistente para la implementación de Exchange](/exchange/exchange-deployment-assistant)

- Cambios en el esquema de Active Directory para Exchange [2016](/Exchange/plan-and-deploy/active-directory/ad-schema-changes), [2013](/exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help), [2010](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)

- Requisitos del sistema para Exchange [2016](/Exchange/plan-and-deploy/system-requirements), [2013](/exchange/exchange-2013-system-requirements-exchange-2013-help), [2010](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141))

- Requisitos previos para Exchange [2016](/Exchange/plan-and-deploy/prerequisites), [2013](/exchange/exchange-2013-prerequisites-exchange-2013-help), [2010](/previous-versions/office/exchange-server-2010/bb691354(v=exchg.141))

## <a name="get-help"></a>Obtener ayuda

Si va a migrar a Microsoft 365, es posible que pueda usar nuestro servicio de Microsoft FastTrack. FastTrack proporciona procedimientos recomendados, herramientas y recursos para que la migración a Microsoft 365 sea lo más fluida posible. Lo mejor de todo es que un ingeniero de soporte técnico le guiará a través de la migración, desde el planeamiento y el diseño hasta la migración del último buzón. Para obtener más información sobre FastTrack, consulte [Microsoft FastTrack](https://fasttrack.microsoft.com/).

Si tiene problemas durante la migración a Microsoft 365 y no usa FastTrack o la migración a una versión más reciente de Exchange Server, estamos aquí para ayudarle. Estos son algunos recursos que puede usar:

- [Comunidad de soporte técnico](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)

- [Soporte al cliente](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-topics"></a>Temas relacionados

[Recursos para ayudarle a actualizar los servidores y clientes de Office 2007](upgrade-from-office-2007-servers-and-products.md)
