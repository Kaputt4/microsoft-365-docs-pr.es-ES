---
title: Plan de final del soporte técnico de Exchange 2010
ms.author: dstrome
author: dstrome
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.assetid: e150e7b9-c432-4c8d-a0ae-c11847129a7d
f1.keywords:
- NOCSH
description: Exchange 2010 ha alcanzado el final del soporte técnico. Use este mapa de ruta de planeación para preparar la actualización a Exchange online o a una versión más reciente de Exchange Server local.
ms.openlocfilehash: 23384d93c4e65fb25a66ca6f2f0bcbe46b34ee18
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519696"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Plan de final del soporte técnico de Exchange 2010

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Exchange Server 2010 ha llegado al final del soporte técnico el **13 de octubre de 2020**. Si todavía no ha iniciado la migración de Exchange 2010 a Microsoft 365, Office 365 o Exchange 2016, ahora es el momento de empezar a planear.

## <a name="what-does-end-of-support-mean"></a>¿Qué significa el *fin de soporte* ?

La mayoría de los productos de Microsoft tienen un ciclo de vida de soporte técnico en el que obtienen nuevas características, correcciones de errores, correcciones de seguridad, etc. Este ciclo de vida suele durar diez años a partir de la versión inicial del producto. El final de este ciclo de vida se conoce como el final del soporte técnico del producto. Como Exchange 2010 ha alcanzado su fin de soporte el 13 de octubre de 2020, Microsoft ya no ofrece:

- Soporte técnico para los problemas que pueden surgir.
- Correcciones de errores para problemas que pueden afectar a la estabilidad y la usabilidad del servidor.
- Revisiones de seguridad para las vulnerabilidades que pueden hacer que el servidor sea vulnerable a las infracciones de seguridad.
- Las actualizaciones de zona horaria.

La instalación de Exchange 2010 seguirá ejecutándose después de esta fecha. Pero debido a los cambios mencionados anteriormente, se recomienda encarecidamente que migre de Exchange 2010 lo antes posible.

Para obtener más información acerca de la finalización del soporte técnico, vea [recursos que le ayudarán a actualizar desde los servidores y clientes de Office 2010](upgrade-from-office-2010-servers-and-products.md).

## <a name="what-are-my-options"></a>¿Qué opciones tengo?

Es un buen momento para explorar las opciones y preparar un plan de migración. Puede:

- Migre completamente a Microsoft 365. Migrar buzones de correo mediante la migración de transferencia, mínima híbrida o híbrida completa. A continuación, quite los servidores de Exchange locales y Active Directory.
- Migre los servidores de Exchange 2010 a Exchange 2016 en los servidores locales.

> [!IMPORTANT]
> Si su organización decide migrar buzones a Microsoft 365, pero planea mantener la sincronización de directorios o Azure AD Connect en su lugar para continuar administrando cuentas de usuario desde Active Directory local, debe tener al menos un servidor de Microsoft Exchange local. Si quita todos los servidores de Exchange, no podrá realizar cambios en los destinatarios de Exchange en Exchange Online porque el origen de la autoridad permanece en su Active Directory local. Deben realizarse los cambios. En este escenario, tiene las siguientes opciones:
>
>- Se *recomienda:* Si migró los buzones a Microsoft 365 y actualizó los servidores para el 13 de octubre de 2020, use Exchange 2010 para conectarse a Microsoft 365 y migrar los buzones de correo. A continuación, migre Exchange 2010 a Exchange 2016 y retire los servidores de Exchange 2010 restantes.
>- Si no ha completado la migración de buzones y la actualización del servidor local antes del 13 de octubre de 2020, actualice primero los servidores locales de Exchange 2010 a Exchange 2016 primero. A continuación, utilice Exchange 2016 para conectarse a Microsoft 365 y migrar los buzones de correo.

> [!NOTE]
> Es algo más complicado, pero también se pueden migrar buzones a Microsoft 365 mientras se migran los servidores locales de Exchange 2010 a Exchange 2016.

Estas son las tres rutas que puede realizar para evitar el fin de soporte para Exchange Server 2010.

![Rutas de actualización de Exchange Server 2010](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

En las siguientes secciones se examina cada opción con más detalle.

## <a name="migrate-to-microsoft-365"></a>Migrar a Microsoft 365

Migrar el correo electrónico a Microsoft 365 es la mejor y sencilla opción para ayudarle a retirar la implementación de Exchange 2010. Con una migración a Microsoft 365, puede realizar un solo salto de tecnología antigua a las características actuales, entre los que se incluyen:

- Capacidades de cumplimiento, como directivas de retención, In-Place y retención por juicio, exhibición de documentos electrónicos local y mucho más.
- Microsoft Teams.
- Power BI.
- Bandeja de entrada prioritarios.
- MyAnalytics.

Microsoft 365 también obtiene primero características y experiencias nuevas, por lo que su organización puede empezar a usarlas inmediatamente. Además, no tendrá que preocuparse por:

- Comprar y mantener hardware.
- Pagar al calor y enfriar los servidores.
- Mantenerse al día en las correcciones de zona horaria, del producto y la seguridad.
- Mantener el almacenamiento y el software para admitir los requisitos de cumplimiento.
- Actualización a una nueva versión de Exchange. Siempre está en la última versión de Exchange en Microsoft 365.

### <a name="how-should-i-migrate-to-microsoft-365"></a>¿Cómo debo migrar a Microsoft 365?

En función de su organización, tiene algunas opciones para obtener acceso a Microsoft 365. En primer lugar, debe tener en cuenta algunas cosas, como:
- El número de puestos o buzones que necesita mover.
- El tiempo que desea que dure la migración.
- Si necesita una integración sin problemas entre la instalación local y Microsoft 365 durante la migración.
 
En esta tabla se muestran las opciones de migración y los factores más importantes que determinan el método que se debe usar.

|Opción de migración|Tamaño de la organización|Duración|
|---|---|---|
|Migración total|Menos de 150 puestos|Una semana o menos|
|Migración híbrida mínima|Menos de 150 puestos|Unas semanas o menos|
|Migración híbrida completa|Más de 150 puestos|Unas semanas o más|

En las siguientes secciones se proporciona información general sobre estos métodos. Para obtener más información, consulte [decidir una ruta de migración](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27).

### <a name="cutover-migration"></a>Migración total

En una migración total, migrar todos los buzones de correo, grupos de distribución, contactos, etc. a Office 365 en una fecha y hora establecidas. Cuando haya terminado, cierre los servidores de Exchange locales y empiece a usar Microsoft 365 exclusivamente.

La migración total es ideal para las organizaciones pequeñas que no tienen muchos buzones de correo, por lo que quieren llegar a Microsoft 365 rápidamente y no quieren ocuparse de la complejidad de los otros métodos. Pero debe completarse en una semana o menos. Y requiere que los usuarios vuelvan a configurar sus perfiles de Outlook. La migración total puede migrar hasta 2.000 buzones de correo, pero le recomendamos que lo use para un máximo de 150. Si intenta migrar más, puede quedarse sin tiempo para transferir todos los buzones de correo antes de la fecha límite y el personal de soporte técnico de ti puede quedar abrumado con solicitudes para ayudar a los usuarios a volver a configurar Outlook.

Estos son algunos aspectos que se deben tener en cuenta sobre la migración total:

- Microsoft 365 tendrá que conectarse a los servidores de Exchange 2010 mediante Outlook Anywhere a través del puerto TCP 443.
- Todos los buzones locales se moverán a Microsoft 365.
- Necesitará una cuenta de administrador local que tenga acceso de lectura a los buzones de los usuarios.
- Los dominios aceptados de Exchange 2010 que desea usar en Microsoft 365 deben agregarse como dominios comprobados en el servicio.
- Entre el momento en que se inicia la migración y el momento en que se inicia la fase de finalización, Microsoft 365 sincronizará periódicamente los buzones de correo de Microsoft 365 y locales. Esto le permite completar la migración sin preocuparse por el correo electrónico que queda en sus buzones locales.
- Los usuarios recibirán nuevas contraseñas temporales para su cuenta de Microsoft 365. Necesitarán cambiarlos cuando inicien sesión en sus buzones por primera vez.
- Necesitará una licencia de 365 de Microsoft que incluya Exchange Online para cada buzón de usuario que migre.
- Los usuarios tendrán que configurar un nuevo perfil de Outlook en cada uno de sus dispositivos y descargar de nuevo el correo electrónico. La cantidad de correo electrónico que Outlook va a descargar puede variar. Para obtener más información, vea [trabajar sin conexión en Outlook](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

Para obtener más información sobre la migración total, consulte:

- [Lo que debe saber sobre una migración total de correo electrónico](https://docs.microsoft.com/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [Realizar una migración total de correo electrónico a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>Migración híbrida mínima

En una migración híbrida o Express mínima, se mueven unos pocos cientos de buzones a Microsoft 365 en unas pocas semanas. Este método no es compatible con las características de migración híbrida avanzada, como la información de disponibilidad de un calendario compartido.

La migración híbrida mínima es ideal para las organizaciones que necesitan más tiempo para migrar sus buzones de correo a Microsoft 365, pero que aún planean completar la migración en unas pocas semanas. Se obtienen algunas de las ventajas de la *migración completa* más avanzada sin mucha complejidad. Puede controlar cuántos y qué buzones de correo migrar en un momento dado. Los buzones de correo de Microsoft 365 se crearán con los nombres de usuario y las contraseñas de las cuentas locales. Y, a diferencia de las migraciones de traslado, los usuarios no tienen que volver a crear sus perfiles de Outlook.

Estos son algunos aspectos que se deben tener en cuenta sobre la migración híbrida mínima:

- Deberá realizar una sincronización de directorios única entre los servidores locales de Active Directory y Microsoft 365.
- Los usuarios podrán iniciar sesión en el buzón de correo de Microsoft 365 con el mismo nombre de usuario y la misma contraseña que antes de su buzón.
- Necesitará una licencia de 365 de Microsoft que incluya Exchange Online para cada buzón de usuario que migre.
- Los usuarios no necesitan configurar un nuevo perfil de Outlook en la mayoría de sus dispositivos, aunque es posible que algunos teléfonos Android más antiguos necesiten un nuevo perfil. Los usuarios no tendrán que volver a descargar el correo electrónico.

Para obtener más información, vea [usar minimal Hybrid para migrar rápidamente buzones de Exchange a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate).

### <a name="full-hybrid"></a>Híbrida completa

En una migración híbrida completa, tiene muchos cientos, hasta decenas de miles de buzones de correo, y se mueven algunos o todos a Microsoft 365. Debido a que estas migraciones suelen ser más duraderas, las migraciones híbridas hacen que sea posible:

- Mostrar a los usuarios locales la información del calendario de disponibilidad de los usuarios de Microsoft 365, y viceversa.
- Vea una lista global de direcciones unificada que contiene destinatarios en el sistema local y en Microsoft 365.
- Ver las propiedades completas de los destinatarios de Outlook para todos los usuarios, independientemente de si son locales o en Microsoft 365.
- Proteger la comunicación del correo electrónico entre los servidores de Exchange locales y Office 365 mediante TLS y certificados.
- Tratar los mensajes enviados entre servidores de Exchange locales y Microsoft 365 como internos, lo que les permite:
  - Ser evaluados y procesados correctamente por los agentes de transporte y cumplimiento que apuntan a los mensajes internos.
  - Omitir los filtros contra correo no deseado.

Las migraciones híbridas completas son las más adecuadas para las organizaciones que esperan permanecer en una configuración híbrida durante muchos meses o más. Se obtienen las características enumeradas anteriormente en esta sección, además de la sincronización de directorios, mejores características de cumplimiento integradas y la capacidad de mover buzones de correo a y desde Microsoft 365 mediante movimientos de buzón en línea. Microsoft 365 se convierte en una extensión de la organización local.

Aspectos que deben tenerse en cuenta sobre la migración híbrida completa:

- No son adecuados para todas las organizaciones. Debido a la complejidad de las migraciones híbridas completas, las organizaciones con menos de unos pocos cientos de buzones de correo no suelen ver los beneficios que justifican el esfuerzo y el costo que implican. En estos casos, se recomienda que considere la posibilidad de realizar una migración híbrida total o mínima en su lugar.
- Debe configurar la sincronización de directorios con Azure Active Directory (Azure AD) Connect entre los servidores locales de Active Directory y Microsoft 365.
- Los usuarios podrán iniciar sesión en el buzón de correo de Microsoft 365 con el mismo nombre de usuario y contraseña que usan cuando inicien sesión en la red local. (Esta funcionalidad requiere Azure AD Connect con la sincronización de contraseñas y/o los servicios de Federación de Active Directory).
- Necesita una licencia de 365 de Microsoft que incluya Exchange Online para cada buzón de usuario que migre.
- Los usuarios no necesitan configurar un nuevo perfil de Outlook en la mayoría de sus dispositivos, aunque es posible que algunos de los teléfonos Android más antiguos necesiten un nuevo perfil. Los usuarios no tendrán que volver a descargar el correo electrónico.

> [!IMPORTANT]
> Si su organización decide migrar buzones a Microsoft 365, pero planea mantener la sincronización de directorios o Azure AD Connect en su lugar para seguir administrando cuentas de usuario desde Active Directory local, debe tener al menos un servidor de Exchange local. Si se quitan todos los servidores de Exchange, no podrá realizar cambios en los destinatarios de Exchange en Exchange Online. Esto se debe a que el origen de la autoridad permanece en su Active Directory local y los cambios deben realizarse allí.

Si el sonido de la migración híbrida completa le resulta adecuado, consulte los siguientes recursos:

- [Asistente para la implementación de Exchange](https://aka.ms/exdeploy)
- [Implementaciones híbridas de Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid)
- [Asistente de configuración híbrida](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)
- [Preguntas más frecuentes acerca del asistente de configuración híbrida](https://docs.microsoft.com/exchange/hybrid-configuration-wizard-faqs)
- [Requisitos previos para la implementación híbrida](https://docs.microsoft.com/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>Actualizar a una versión más reciente de Exchange Server local

Creemos que se obtiene el mejor valor y la mejor experiencia del usuario mediante la migración completa a Microsoft 365. Pero somos conscientes de que algunas organizaciones necesitan mantener algunos servidores de Exchange locales. Esto puede deberse a los requisitos normativos, para garantizar que los datos no se almacenan en un centro de datos externo porque tiene una configuración o requisitos únicos que no se pueden cumplir en la nube, o porque necesita Exchange para administrar los buzones en la nube porque todavía usa Active Directory local. En cualquier caso, si mantiene Exchange local, debe asegurarse de que su entorno de Exchange 2010 se actualiza al menos Exchange 2013 o Exchange 2016.

Para que la experiencia sea óptima, le recomendamos que actualice el entorno local restante a Exchange 2016. No es necesario instalar Exchange Server 2013 si desea ir directamente de Exchange Server 2010 a Exchange Server 2016.

Exchange 2016 incluye todas las características de versiones anteriores de Exchange. Se asemeja más a la experiencia disponible en Microsoft 365, aunque algunas características solo están disponibles en Microsoft 365. Consulte sólo algunas de las cosas que ha estado perdiendo:

|Versión de Exchange|Características|
|---|---|
|**Exchange 2013**|La arquitectura simplificada reduce el número de roles de servidor a tres (buzón de correo, acceso de cliente y transporte perimetral)|
||Directivas de prevención de pérdida de datos (DLP) que evitan la pérdida de información confidencial|
||Experiencia mejorada de Outlook Web App|
|**Exchange 2016**|*Características de Exchange 2013 y...*|
||Funciones de servidor más sencillas para solo buzones de correo y de transporte perimetral|
||DLP mejorado junto con la integración con SharePoint|
||Resistencia de base de datos mejorada|
||Colaboración en documentos en línea|

|Consideración|Más información|
|---|---|
|Fecha de finalización del soporte técnico|Al igual que Exchange 2010, cada versión de Exchange tiene su propia fecha de finalización de soporte:<br/><br/>Exchange 2013-abril 2023<br/>Exchange 2016-octubre 2025<br/><br/>Al principio de la fecha de finalización del soporte, lo antes que necesitará realizar otra migración. Abril de 2023 es mucho más cercana a lo que cree.|
|Ruta de migración a Exchange 2013 o 2016|La ruta de migración de Exchange 2010 a una versión más reciente es la misma si elige Exchange 2013 o Exchange 2016:<br/><br/>Instale Exchange 2013 o 2016 en su organización de Exchange 2010 existente.<br/>Mueva los servicios y otra infraestructura a Exchange 2013 o 2016.<br/>Mueva los buzones de correo y las carpetas públicas a Exchange 2013 o 2016 Retire los servidores de Exchange 2010 restantes.|
|Coexistencia de versiones|Al migrar a Exchange 2013 o Exchange 2016, puede instalar cualquier versión en una organización existente de Exchange 2010. Esto le permite instalar uno o varios servidores de Exchange 2013 o Exchange 2016 y realizar la migración.|
|Hardware de servidor|Los requisitos de hardware del servidor han cambiado de Exchange 2010. Asegúrese de que el hardware es compatible. Obtenga más información sobre los requisitos de hardware para cada versión:<br/><br/>[Requisitos del sistema para Exchange 2016](https://docs.microsoft.com/Exchange/plan-and-deploy/system-requirements?view=exchserver-2016)<br/>[Requisitos del sistema para Exchange 2013](https://docs.microsoft.com/Exchange/exchange-2013-system-requirements-exchange-2013-help)<br/><br/>Con las mejoras significativas en el rendimiento de Exchange y la mayor capacidad de procesamiento y capacidad de almacenamiento de los nuevos servidores, es probable que necesite menos servidores para admitir el mismo número de buzones de correo.|
|Versión del sistema operativo|Las versiones de sistema operativo mínimas admitidas para cada versión son:<br/><br/>Exchange 2016-Windows Server 2012<br/>Exchange 2013-Windows Server 2008 R2 SP1<br/><br/>Puede encontrar más información acerca del soporte del sistema operativo en la [matriz de compatibilidad de Exchange](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).|
|Nivel funcional del bosque de Active Directory|Los niveles de funcionalidad de bosque de Active Directory mínimos admitidos para cada versión son:<br/><br/>Exchange 2016-Windows Server 2008 R2 SP1<br/>Exchange 2013-Windows Server 2003<br/><br/>Puede encontrar más información acerca de la compatibilidad del nivel funcional del bosque en la [matriz de compatibilidad de Exchange](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).|
|Versiones de cliente de Office|Las versiones de cliente de Office mínimas admitidas para cada versión son:<br/><br/>Exchange 2016-Office 2010 (con las actualizaciones más recientes)<br/>Exchange 2013-Office 2007 SP3<br/><br/>Obtenga más información sobre Office Client Support en la [matriz de compatibilidad de Exchange](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).||| 


Use los siguientes recursos para ayudarle con la migración:

- [Asistente para la implementación de Exchange](https://aka.ms/exdeploy)
- Cambios en el esquema de Active Directory para Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)
- Requisitos del sistema para Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/system-requirements?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-system-requirements-exchange-2013-help)
- Requisitos previos para Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/prerequisites?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-prerequisites-exchange-2013-help)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Resumen de opciones para el cliente y los servidores de Office 2010 y Windows 7

Para obtener un resumen visual de las opciones de actualización y migración a la nube para clientes de Office 2010 y servidores de Windows 7, consulte el [póster de final del soporte técnico.](../downloads/Office2010Windows7EndOfSupport.pdf)

[![Fin del soporte técnico para clientes y servidores de Office 2010 y póster de Windows 7](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

En este póster de una página se ilustran las distintas rutas que puede realizar para responder a los productos de cliente y servidor de Office 2010 y el fin de soporte de Windows 7, con las rutas de usuario preferidas y la compatibilidad con opciones de Microsoft 365 Enterprise resaltado.

También puede [Descargar](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) este póster e imprimirlo en formato carta, legal o tabloide (11 x 17).

## <a name="what-if-i-need-help"></a>¿Qué debo hacer si necesito ayuda?

Si va a migrar a Microsoft 365, puede ser elegible para usar nuestro servicio Microsoft FastTrack. FastTrack proporciona los procedimientos recomendados, las herramientas y los recursos para que la migración a Microsoft 365 sea lo más fluida posible. Lo mejor de todo es que tendrá un ingeniero de soporte técnico para guiarle desde la planeación y el diseño hasta la migración del último buzón de correo. Para obtener más información acerca de FastTrack, consulte [Microsoft FastTrack](https://fasttrack.microsoft.com/).

Si tiene problemas durante la migración a Microsoft 365 y no está usando FastTrack o está migrando a una versión más reciente de Exchange Server, estos son algunos recursos que puede usar:

- [Comunidad de soporte técnico](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [Soporte al cliente](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-articles"></a>Artículos relacionados

[Recursos para ayudarle a actualizar desde servidores y clientes de Office 2010](upgrade-from-office-2010-servers-and-products.md)
