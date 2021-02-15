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
description: Exchange 2010 ha alcanzado el final del soporte técnico. Use esta guía básica de planeación para preparar la actualización a Exchange Online o a una versión más reciente de Exchange Server local.
ms.openlocfilehash: 23384d93c4e65fb25a66ca6f2f0bcbe46b34ee18
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519696"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Plan de final del soporte técnico de Exchange 2010

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Exchange Server 2010 llegó a su fin de soporte el **13 de octubre de 2020.** Si aún no ha iniciado la migración de Exchange 2010 a Microsoft 365, Office 365 o Exchange 2016, ahora es el momento de empezar a planear.

## <a name="what-does-end-of-support-mean"></a>¿Qué significa *el fin del* soporte técnico?

La mayoría de los productos de Microsoft tienen un ciclo de vida de soporte durante el cual obtienen nuevas características, correcciones de errores, correcciones de seguridad, entre otros. Este ciclo de vida suele durar 10 años desde la versión inicial del producto. El final de este ciclo de vida se conoce como el final del soporte técnico del producto. Dado que Exchange 2010 llegó a su fin de soporte el 13 de octubre de 2020, Microsoft ya no proporciona:

- Soporte técnico para los problemas que pueden producirse.
- Correcciones de errores para problemas que pueden afectar a la estabilidad y facilidad de uso del servidor.
- Correcciones de seguridad para vulnerabilidades que pueden hacer que el servidor sea vulnerable a las infracciones de seguridad.
- Actualizaciones de zona horaria.

La instalación de Exchange 2010 seguirá funcionando después de esta fecha. Pero debido a los cambios enumerados anteriormente, se recomienda encarecidamente migrar desde Exchange 2010 lo antes posible.

Para obtener más información sobre cómo acercarse al final del soporte técnico, vea Recursos para ayudarle a actualizar desde clientes y servidores [de Office 2010.](upgrade-from-office-2010-servers-and-products.md)

## <a name="what-are-my-options"></a>¿Cuáles son mis opciones?

Es un buen momento para explorar las opciones y preparar un plan de migración. Puede:

- Migrar completamente a Microsoft 365. Migrar buzones mediante una migración total, híbrida mínima o completa. A continuación, quite los servidores de Exchange locales y Active Directory.
- Migre los servidores de Exchange 2010 a Exchange 2016 en los servidores locales.

> [!IMPORTANT]
> Si su organización decide migrar buzones a Microsoft 365, pero tiene previsto mantener DirSync o Azure AD Connect en su lugar para seguir administrando cuentas de usuario desde Active Directory local, debe mantener al menos un servidor de Microsoft Exchange local. Si quita todos los servidores de Exchange, no podrá realizar cambios en los destinatarios de Exchange en Exchange Online porque el origen de la autoridad permanece en su Active Directory local. Los cambios deben realizarse allí. En este escenario, tiene las siguientes opciones:
>
>- *Recomendado:* Si migró sus buzones a Microsoft 365 y actualizó los servidores el 13 de octubre de 2020, use Exchange 2010 para conectarse a Microsoft 365 y migrar buzones. A continuación, migre Exchange 2010 a Exchange 2016 y decomise los servidores de Exchange 2010 restantes.
>- Si no ha completado la migración de buzones y la actualización del servidor local antes del 13 de octubre de 2020, actualice primero los servidores de Exchange 2010 locales a Exchange 2016. A continuación, use Exchange 2016 para conectarse a Microsoft 365 y migrar buzones.

> [!NOTE]
> Es un poco más complicado, pero también puede migrar buzones a Microsoft 365 mientras migra los servidores locales de Exchange 2010 a Exchange 2016.

Estas son las tres rutas que puede seguir para evitar el fin del soporte técnico Exchange Server 2010.

![Exchange Server de actualización de 2010](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

En las secciones siguientes se explora cada opción con más detalle.

## <a name="migrate-to-microsoft-365"></a>Migrar a Microsoft 365

Migrar el correo electrónico a Microsoft 365 es la mejor y más sencilla opción para ayudarle a retirar la implementación de Exchange 2010. Con una migración a Microsoft 365, puede realizar un único salto de la tecnología antigua a las características actuales, entre las que se incluyen:

- Capacidades de cumplimiento como directivas de retención, In-Place retención por juicio, exhibición de documentos electrónicos local y mucho más.
- Microsoft Teams.
- Power BI.
- Bandeja de entrada con foco.
- MyAnalytics.

Microsoft 365 también obtiene primero nuevas características y experiencias, por lo que su organización puede empezar a usarlos inmediatamente. Además, no tendrá que preocuparse por:

- Comprar y mantener hardware.
- Pagar al frío y refrescar los servidores.
- Mantenerse al día de las correcciones de seguridad, producto y zona horaria.
- Mantener el almacenamiento y el software para cumplir los requisitos de cumplimiento.
- Actualización a una nueva versión de Exchange. Siempre está en la versión más reciente de Exchange en Microsoft 365.

### <a name="how-should-i-migrate-to-microsoft-365"></a>¿Cómo debería migrar a Microsoft 365?

Dependiendo de su organización, tiene algunas opciones para obtener acceso a Microsoft 365. En primer lugar, debe tener en cuenta algunas cosas, como:
- El número de puestos o buzones que necesita mover.
- Cuánto tiempo desea que dure la migración.
- Si necesita una integración perfecta entre la instalación local y Microsoft 365 durante la migración.
 
En esta tabla se muestran las opciones de migración y los factores más importantes que determinan el método que se va a usar.

|Opción de migración|Tamaño de la organización|Duración|
|---|---|---|
|Migración total|Menos de 150 puestos|Una semana o menos|
|Migración híbrida mínima|Menos de 150 puestos|Unas pocas semanas o menos|
|Migración híbrida completa|Más de 150 puestos|Unas pocas semanas o más|

En las secciones siguientes se proporciona información general sobre estos métodos. Para obtener más información, vea [Decide on a migration path](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27).

### <a name="cutover-migration"></a>Migración total

En una migración total, se migran todos los buzones, grupos de distribución, contactos, entre otros, a Office 365 en una fecha y hora establecidas. Cuando haya terminado, cierre los servidores de Exchange locales y empiece a usar Microsoft 365 exclusivamente.

La migración de escala es excelente para las organizaciones pequeñas que no tienen muchos buzones, quieren acceder a Microsoft 365 rápidamente y no quieren abordar la complejidad de los otros métodos. Pero debe completarse en una semana o menos. Y requiere que los usuarios vuelvan a configurar sus perfiles de Outlook. La migración de escala puede migrar hasta 2.000 buzones, pero se recomienda usarlo para un máximo de 150. Si intenta migrar más, puede que se le agote el tiempo para transferir todos los buzones antes de la fecha límite, y el personal de soporte técnico de TI puede saturarse con solicitudes para ayudar a los usuarios a reconfigurar Outlook.

Estos son los aspectos que se deben tener en cuenta sobre la migración de escala:

- Microsoft 365 tendrá que conectarse a los servidores de Exchange 2010 mediante Outlook en cualquier lugar a través del puerto TCP 443.
- Todos los buzones locales se trasladarán a Microsoft 365.
- Necesitará una cuenta de administrador local que tenga acceso de lectura a los buzones de los usuarios.
- Los dominios aceptados de Exchange 2010 que desea usar en Microsoft 365 deben agregarse como dominios comprobados en el servicio.
- Entre el momento en que se inicia la migración y cuando se inicia la fase de finalización, Microsoft 365 sincronizará periódicamente los buzones de Microsoft 365 y los buzones locales. Esto le permite completar la migración sin preocuparse de que el correo electrónico se deje en sus buzones locales.
- Los usuarios recibirán nuevas contraseñas temporales para su cuenta de Microsoft 365. Necesitarán cambiarla cuando inicien sesión en sus buzones por primera vez.
- Necesitará una licencia de Microsoft 365 que incluya Exchange Online para cada buzón de usuario que migre.
- Los usuarios tendrán que configurar un nuevo perfil de Outlook en cada uno de sus dispositivos y volver a descargar su correo electrónico. La cantidad de correo electrónico que Outlook descargará puede variar. Para obtener más información, vea [Trabajar sin conexión en Outlook.](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633)

Para obtener más información acerca de la migración de escala, vea:

- [Lo que necesita saber sobre una migración de correo electrónico de escala](https://docs.microsoft.com/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [Realizar una migración de correo electrónico a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>Migración híbrida mínima

En una migración híbrida o expresa mínima, se mueven unos cientos de buzones a Microsoft 365 en unas pocas semanas. Este método no admite características avanzadas de migración híbrida, como la información de calendario de disponibilidad compartida.

Una migración híbrida mínima es ideal para las organizaciones que necesitan tardar más tiempo en migrar sus buzones a Microsoft 365, pero aún así planean completar la migración en unas pocas semanas. Obtiene algunas de las ventajas de la migración híbrida completa más *avanzada* sin gran parte de la complejidad. Puede controlar cuántos buzones de correo se van a migrar en un momento determinado. Los buzones de Microsoft 365 se crearán con los nombres de usuario y contraseñas de las cuentas locales. Y, a diferencia de las migraciones de escala, los usuarios no tienen que volver a crear sus perfiles de Outlook.

Estos son los aspectos que se deben tener en cuenta sobre la migración híbrida mínima:

- Deberá realizar una sincronización de directorios única entre los servidores locales de Active Directory y Microsoft 365.
- Los usuarios podrán iniciar sesión en su buzón de Microsoft 365 con el mismo nombre de usuario y contraseña que antes de su buzón.
- Necesitará una licencia de Microsoft 365 que incluya Exchange Online para cada buzón de usuario que migre.
- Los usuarios no necesitarán configurar un nuevo perfil de Outlook en la mayoría de sus dispositivos, aunque es posible que algunos teléfonos Android más antiguos necesiten un nuevo perfil. Los usuarios no necesitarán volver a descargar su correo electrónico.

Para obtener más información, vea Usar un entorno híbrido mínimo para migrar rápidamente [buzones de Exchange a Office 365.](https://docs.microsoft.com/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate)

### <a name="full-hybrid"></a>Híbrido completo

En una migración híbrida completa, tiene muchos cientos, hasta decenas de miles, de buzones y mueve algunos o todos a Microsoft 365. Dado que estas migraciones suelen ser a más largo plazo, las migraciones híbridas hacen posible lo siguiente:

- Mostrar a los usuarios locales la información de calendario de disponibilidad de los usuarios de Microsoft 365 y viceversa.
- Vea una lista global unificada de direcciones que contiene destinatarios tanto en local como en Microsoft 365.
- Ver las propiedades de destinatario de Outlook completa para todos los usuarios, independientemente de si son locales o de Microsoft 365.
- Proteger la comunicación por correo electrónico entre los servidores de Exchange locales y Office 365 mediante TLS y certificados.
- Trate los mensajes enviados entre servidores de Exchange locales y Microsoft 365 como internos, lo que les permite:
  - Sean evaluados y procesados correctamente por agentes de transporte y cumplimiento destinados a mensajes internos.
  - Omitir filtros contra correo no deseado.

Las migraciones híbridas completa son las más recomendadas para las organizaciones que esperan permanecer en una configuración híbrida durante varios meses o más. Obtiene las características enumeradas anteriormente en esta sección, además de la sincronización de directorios, las mejores características de cumplimiento integradas y la capacidad de mover buzones a y desde Microsoft 365 mediante movimientos de buzones en línea. Microsoft 365 se convierte en una extensión de su organización local.

Aspectos que se deben tener en cuenta sobre la migración híbrida completa:

- No son adecuados para todas las organizaciones. Debido a la complejidad de las migraciones híbridas completa, las organizaciones con menos de unos pocos cientos de buzones no suelen ver ventajas que justifican el esfuerzo y el costo implicados. En estos casos, se recomienda considerar la migración híbrida mínima o de escala en su lugar.
- Debe configurar la sincronización de directorios con Azure Active Directory (Azure AD) Connect entre los servidores locales de Active Directory y Microsoft 365.
- Los usuarios podrán iniciar sesión en su buzón de Microsoft 365 con el mismo nombre de usuario y contraseña que usan al iniciar sesión en la red local. (Esta funcionalidad requiere Azure AD Connect con sincronización de contraseñas o servicios de federación de Active Directory).
- Necesita una licencia de Microsoft 365 que incluya Exchange Online para cada buzón de usuario que migre.
- Los usuarios no necesitan configurar un nuevo perfil de Outlook en la mayoría de sus dispositivos, aunque es posible que algunos teléfonos Android más antiguos necesiten un nuevo perfil. Los usuarios no necesitarán volver a descargar su correo electrónico.

> [!IMPORTANT]
> Si su organización decide migrar buzones a Microsoft 365, pero tiene previsto mantener DirSync o Azure AD Connect en su lugar para seguir administrando cuentas de usuario desde Active Directory local, debe mantener al menos un servidor de Exchange local. Si se quitan todos los servidores de Exchange, no podrá realizar cambios en los destinatarios de Exchange en Exchange Online. Esto se debe a que el origen de la autoridad permanece en su Active Directory local y es necesario realizar cambios allí.

Si una migración híbrida completa le parece adecuada, vea los siguientes recursos útiles:

- [Asistente para la implementación de Exchange](https://aka.ms/exdeploy)
- [Implementaciones híbridas de Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid)
- [Asistente de configuración híbrida](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)
- [Preguntas más frecuentes acerca del asistente de configuración híbrida](https://docs.microsoft.com/exchange/hybrid-configuration-wizard-faqs)
- [Requisitos previos para la implementación híbrida](https://docs.microsoft.com/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>Actualizar a una versión más reciente de Exchange Server local

Creemos que obtiene el mejor valor y experiencia de usuario migrando completamente a Microsoft 365. Pero sabemos que algunas organizaciones necesitan mantener algunos servidores de Exchange locales. Esto puede deberse a requisitos normativos, para garantizar que los datos no se almacenan en un centro de datos externo, porque tiene una configuración única o requisitos que no se pueden cumplir en la nube, o porque necesita que Exchange administre los buzones en la nube porque sigue utilizando Active Directory local. En cualquier caso, si mantiene Exchange local, debe asegurarse de que su entorno de Exchange 2010 esté actualizado al menos a Exchange 2013 o Exchange 2016.

Para obtener la mejor experiencia, le recomendamos que actualice el entorno local restante a Exchange 2016. You don't need to install Exchange Server 2013 if you want to go straight from Exchange Server 2010 to Exchange Server 2016.

Exchange 2016 incluye todas las características de versiones anteriores de Exchange. Coincide más estrechamente con la experiencia disponible con Microsoft 365, aunque algunas características solo están disponibles en Microsoft 365. Echa un vistazo a algunas de las cosas que te han faltado:

|Versión de Exchange|Características|
|---|---|
|**Exchange 2013**|La arquitectura simplificada reduce el número de roles de servidor a tres (buzón, acceso de cliente, transporte perimetral)|
||Directivas de prevención de pérdida de datos (DLP) que ayudan a evitar la pérdida de información confidencial|
||Experiencia mejorada de Outlook Web App|
|**Exchange 2016**|*Características de Exchange 2013 y ...*|
||Roles de servidor simplificados adicionales a solo buzón de correo y transporte perimetral|
||DLP mejorado junto con la integración con SharePoint|
||Resistencia de base de datos mejorada|
||Colaboración de documentos en línea|

|Consideración|Más información|
|---|---|
|Fechas de finalización del soporte técnico|Al igual que Exchange 2010, cada versión de Exchange tiene su propia fecha de fin de soporte técnico:<br/><br/>Exchange 2013 - Abril de 2023<br/>Exchange 2016 - Octubre de 2025<br/><br/>Cuanto antes sea la fecha de finalización del soporte técnico, más pronto tendrá que realizar otra migración. Abril de 2023 es mucho más cercano de lo que crees.|
|Ruta de migración a Exchange 2013 o 2016|La ruta de migración de Exchange 2010 a una versión más reciente es la misma si elige Exchange 2013 o Exchange 2016:<br/><br/>Instale Exchange 2013 o 2016 en su organización de Exchange 2010 existente.<br/>Mover servicios y otra infraestructura a Exchange 2013 o 2016.<br/>Mover buzones y carpetas públicas a Exchange 2013 o 2016 Retirar los servidores de Exchange 2010 restantes.|
|Coexistencia de versiones|Al migrar a Exchange 2013 o Exchange 2016, puede instalar cualquier versión en una organización existente de Exchange 2010. Esto le permite instalar uno o más servidores de Exchange 2013 o Exchange 2016 y realizar la migración.|
|Hardware de servidor|Los requisitos de hardware del servidor han cambiado desde Exchange 2010. Asegúrese de que el hardware es compatible. Aquí encontrará más información sobre los requisitos de hardware para cada versión:<br/><br/>[Requisitos del sistema para Exchange 2016](https://docs.microsoft.com/Exchange/plan-and-deploy/system-requirements?view=exchserver-2016)<br/>[Requisitos del sistema para Exchange 2013](https://docs.microsoft.com/Exchange/exchange-2013-system-requirements-exchange-2013-help)<br/><br/>Con las mejoras significativas en el rendimiento de Exchange y el aumento de la capacidad informática y de almacenamiento en servidores más recientes, es probable que necesite menos servidores para admitir el mismo número de buzones.|
|Versión del sistema operativo|Las versiones mínimas admitidas del sistema operativo para cada versión son:<br/><br/>Exchange 2016 - Windows Server 2012<br/>Exchange 2013 - Windows Server 2008 R2 SP1<br/><br/>Puede encontrar más información sobre la compatibilidad del sistema operativo en [la matriz de compatibilidad de Exchange.](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix)|
|Nivel funcional del bosque de Active Directory|Los niveles funcionales mínimos admitidos del bosque de Active Directory para cada versión son:<br/><br/>Exchange 2016 - Windows Server 2008 R2 SP1<br/>Exchange 2013 - Windows Server 2003<br/><br/>Puede encontrar más información sobre la compatibilidad con el nivel funcional del bosque en [la matriz de compatibilidad de Exchange.](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix)|
|Versiones de cliente de Office|Las versiones mínimas de cliente de Office admitidas para cada versión son:<br/><br/>Exchange 2016 - Office 2010 (con las últimas actualizaciones)<br/>Exchange 2013 - Office 2007 SP3<br/><br/>Encontrará más información sobre la compatibilidad con clientes de Office en [la matriz de compatibilidad de Exchange.](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix)||| 


Use los siguientes recursos para ayudarle con la migración:

- [Asistente para la implementación de Exchange](https://aka.ms/exdeploy)
- Cambios en el esquema de Active Directory para Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)
- Requisitos del sistema para Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/system-requirements?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-system-requirements-exchange-2013-help)
- Requisitos previos para Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/prerequisites?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-prerequisites-exchange-2013-help)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Resumen de las opciones para el cliente y los servidores de Office 2010 y Windows 7

Para obtener un resumen visual de las opciones de actualización y migración a la nube para clientes de Office 2010 y servidores de Windows 7, consulte el [póster de final del soporte técnico.](../downloads/Office2010Windows7EndOfSupport.pdf)

[![Fin del soporte técnico para clientes y servidores de Office 2010 y póster de Windows 7](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

En este póster de una página se ilustran las distintas rutas que puede seguir para responder a los productos de cliente y servidor de Office 2010 y windows 7 para llegar al final del soporte técnico, con las rutas de acceso preferidas y la compatibilidad con opciones en Microsoft 365 Enterprise resaltadas.

También puede descargar [este](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) póster e imprimirlo en formato carta, legal o tabloide (11 x 17).

## <a name="what-if-i-need-help"></a>¿Qué ocurre si necesito ayuda?

Si va a migrar a Microsoft 365, es posible que sea apto para usar nuestro servicio Microsoft FastTrack. FastTrack proporciona procedimientos recomendados, herramientas y recursos para que la migración a Microsoft 365 sea lo más sencilla posible. Lo mejor de todo es que un ingeniero de soporte técnico le ayudará desde la planeación y el diseño hasta la migración del último buzón. Para obtener más información sobre FastTrack, vea [Microsoft FastTrack](https://fasttrack.microsoft.com/).

Si tiene problemas durante la migración a Microsoft 365 y no usa FastTrack o está migrando a una versión más reciente de Exchange Server, estos son algunos recursos que puede usar:

- [Comunidad de soporte técnico](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [Soporte al cliente](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-articles"></a>Artículos relacionados

[Recursos para ayudarle a actualizar desde servidores y clientes de Office 2010](upgrade-from-office-2010-servers-and-products.md)
