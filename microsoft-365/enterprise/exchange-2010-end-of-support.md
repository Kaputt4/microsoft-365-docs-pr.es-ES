---
title: Plan de final del soporte técnico de Exchange 2010
ms.author: dstrome
author: dstrome
manager: scotv
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- Ent_O365
ms.assetid: e150e7b9-c432-4c8d-a0ae-c11847129a7d
f1.keywords:
- NOCSH
description: Exchange 2010 ha llegado al final del soporte técnico. Use este plan de planificación para prepararse para actualizar a Exchange Online o a una versión más reciente de Exchange Server local.
ms.openlocfilehash: 02472f5d1ed1a4008e43bd89d227753465dcc409
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68171243"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Plan de final del soporte técnico de Exchange 2010

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Exchange Server 2010 llegó a su fin el **13 de octubre de 2020**. Si aún no ha iniciado la migración de Exchange 2010 a Microsoft 365, Office 365 o Exchange 2016, ahora es el momento de empezar a planear.

## <a name="what-does-end-of-support-mean"></a>¿Qué significa *el fin del soporte* técnico?

La mayoría de los productos de Microsoft tienen un ciclo de vida de soporte técnico durante el cual obtienen nuevas características, correcciones de errores, correcciones de seguridad, etc. Este ciclo de vida suele durar 10 años a partir de la versión inicial del producto. El final de este ciclo de vida se conoce como el fin del soporte técnico del producto. Dado que Exchange 2010 llegó a su fin de soporte técnico el 13 de octubre de 2020, Microsoft ya no proporciona:

- Soporte técnico para los problemas que pueden producirse.
- Correcciones de errores para problemas que pueden afectar a la estabilidad y facilidad de uso del servidor.
- Correcciones de seguridad para las vulnerabilidades que pueden hacer que el servidor sea vulnerable a infracciones de seguridad.
- Actualizaciones de zona horaria.

Tu instalación de Exchange 2010 seguirá ejecutándose después de esta fecha. Pero debido a los cambios enumerados anteriormente, se recomienda encarecidamente migrar desde Exchange 2010 lo antes posible.

Para obtener más información sobre cómo acercar el final del soporte técnico, vea [Recursos para ayudarle a actualizar desde clientes y servidores de Office 2010](upgrade-from-office-2010-servers-and-products.md).

## <a name="what-are-my-options"></a>¿Cuáles son mis opciones?

Es un buen momento para explorar las opciones y preparar un plan de migración. Puede:

- Migre completamente a Microsoft 365. Migración de buzones mediante migración híbrida, híbrida mínima o completa. A continuación, quite los servidores de Exchange locales y Active Directory.
- Migre los servidores de Exchange 2010 a Exchange 2016 en los servidores locales.

> [!IMPORTANT]
> Si su organización decide migrar buzones a Microsoft 365, pero planea mantener DirSync o Azure AD Connect en su lugar para seguir administrando cuentas de usuario desde Active Directory local, debe mantener al menos un servidor de Microsoft Exchange local. Si quita todos los servidores de Exchange, no podrá realizar cambios en los destinatarios de Exchange en Exchange Online porque el origen de autoridad permanece en el Active Directory local. Los cambios deben realizarse allí. En este escenario, tiene las siguientes opciones:
>
> - *Recomienda:* Si migró los buzones a Microsoft 365 y actualizó los servidores antes del 13 de octubre de 2020, use Exchange 2010 para conectarse a Microsoft 365 y migrar buzones. A continuación, migre Exchange 2010 a Exchange 2016 y retire los servidores de Exchange 2010 restantes.
> - Si no completó la migración de buzones y la actualización del servidor local antes del 13 de octubre de 2020, actualice primero los servidores locales de Exchange 2010 a Exchange 2016. A continuación, use Exchange 2016 para conectarse a Microsoft 365 y migrar buzones.

> [!NOTE]
> Es poco más complicado, pero también puede migrar buzones a Microsoft 365 al migrar los servidores locales de Exchange 2010 a Exchange 2016.

Estas son las tres rutas de acceso que puede tomar para evitar el final de la compatibilidad con Exchange Server 2010.

![Exchange Server rutas de actualización de 2010.](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

En las secciones siguientes se explora cada opción con más detalle.

## <a name="migrate-to-microsoft-365"></a>Migrar a Microsoft 365

Migrar el correo electrónico a Microsoft 365 es la mejor y más sencilla opción para ayudarle a retirar la implementación de Exchange 2010. Con una migración a Microsoft 365, puede realizar un único salto de la tecnología antigua a las características actuales, entre las que se incluyen:

- Funcionalidades de cumplimiento, como directivas de retención, In-Place y suspensión por juicio, exhibición de documentos electrónicos en contexto, etc.
- Microsoft Teams.
- Power BI.
- Bandeja de entrada centrada.
- MyAnalytics.

Microsoft 365 también obtiene primero nuevas características y experiencias, por lo que su organización puede empezar a usarlas de inmediato. Además, no tendrá que preocuparse por lo siguiente:

- Compra y mantenimiento de hardware.
- Pagar por calentar y enfriar los servidores.
- Mantenerse al día sobre las correcciones de seguridad, productos y zonas horarias.
- Mantener el almacenamiento y el software para admitir los requisitos de cumplimiento.
- Actualización a una nueva versión de Exchange. Siempre está en la versión más reciente de Exchange en Microsoft 365.

### <a name="how-should-i-migrate-to-microsoft-365"></a>¿Cómo debo migrar a Microsoft 365?

En función de su organización, tiene algunas opciones para llegar a Microsoft 365. En primer lugar, debe tener en cuenta algunas cosas, como:

- El número de puestos o buzones que necesita mover.
- Cuánto tiempo desea que dure la migración.
- Si necesita una integración sin problemas entre la instalación local y Microsoft 365 durante la migración.

En esta tabla se muestran las opciones de migración y los factores más importantes que determinan qué método usar.

|Opción de migración|Tamaño de la organización|Duración|
|---|---|---|
|Migración total|Menos de 150 puestos|Una semana o menos|
|Migración híbrida mínima|Menos de 150 puestos|Unas semanas o menos|
|Migración híbrida completa|Más de 150 puestos|Unas semanas o más|

En las secciones siguientes se proporciona información general sobre estos métodos. Para obtener más información, vea [Decidir una ruta de migración](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27).

### <a name="cutover-migration"></a>Migración total

En una migración de transición, se migran todos los buzones, grupos de distribución, contactos, etc., para Office 365 en una fecha y hora establecidas. Cuando haya terminado, apagará los servidores de Exchange locales y comenzará a usar Microsoft 365 exclusivamente.

La migración de transición es ideal para organizaciones pequeñas que no tienen muchos buzones de correo, quieren llegar a Microsoft 365 rápidamente y no quieren lidiar con la complejidad de los otros métodos. Pero debe completarse en una semana o menos. Y requiere que los usuarios vuelvan a configurar sus perfiles de Outlook. La migración de transición puede migrar hasta 2000 buzones, pero se recomienda usarla para un máximo de 150. Si intenta migrar más, podría quedar sin tiempo para transferir todos los buzones antes de la fecha límite, y el personal de soporte técnico de TI puede verse abrumado por las solicitudes para ayudar a los usuarios a volver a configurar Outlook.

Estas son las cosas que se deben tener en cuenta sobre la migración de transición:

- Microsoft 365 tendrá que conectarse a los servidores de Exchange 2010 mediante Outlook En cualquier lugar a través del puerto TCP 443.
- Todos los buzones locales se moverán a Microsoft 365.
- Necesitará una cuenta de administrador local que tenga acceso de lectura a los buzones de los usuarios.
- Los dominios aceptados de Exchange 2010 que desea usar en Microsoft 365 deben agregarse como dominios comprobados en el servicio.
- Entre el inicio de la migración y la fase de finalización, Microsoft 365 sincronizará periódicamente los buzones de Microsoft 365 y locales. Esto le permite completar la migración sin preocuparse de que el correo electrónico se quede atrás en los buzones locales.
- Los usuarios recibirán nuevas contraseñas temporales para su cuenta de Microsoft 365. Tendrán que cambiarlos cuando inicien sesión en sus buzones por primera vez.
- Necesitará una licencia de Microsoft 365 que incluya Exchange Online para cada buzón de usuario que migre.
- Los usuarios tendrán que configurar un nuevo perfil de Outlook en cada uno de sus dispositivos y volver a descargar su correo electrónico. La cantidad de correo electrónico que Outlook descargará puede variar. Para obtener más información, vea [Trabajar sin conexión en Outlook](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

Para obtener más información sobre la migración de transición, consulte:

- [Lo que necesita saber sobre una migración de correo electrónico de transición](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [Realizar una migración total del correo electrónico a Office 365](/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>Migración híbrida mínima

En una migración híbrida o rápida mínima, mueve unos cientos de buzones a Microsoft 365 en pocas semanas. Este método no admite características avanzadas de migración híbrida, como la información de calendario de disponibilidad compartida.

La migración híbrida mínima es ideal para las organizaciones que necesitan más tiempo para migrar sus buzones de correo a Microsoft 365, pero aún así planean completar la migración en unas semanas. Obtendrá algunas de las ventajas de la *migración híbrida completa* más avanzada sin gran parte de la complejidad. Puede controlar cuántos y qué buzones se van a migrar en un momento determinado. Los buzones de Microsoft 365 se crearán con los nombres de usuario y contraseñas de las cuentas locales. Y, a diferencia de las migraciones de transición, los usuarios no tienen que volver a crear sus perfiles de Outlook.

Estas son las cosas que se deben tener en cuenta sobre la migración híbrida mínima:

- Tendrá que realizar una sincronización de directorios única entre los servidores de Active Directory local y Microsoft 365.
- Los usuarios podrán iniciar sesión en su buzón de Microsoft 365 con el mismo nombre de usuario y contraseña que antes de su buzón.
- Necesitará una licencia de Microsoft 365 que incluya Exchange Online para cada buzón de usuario que migre.
- Los usuarios no tendrán que configurar un nuevo perfil de Outlook en la mayoría de sus dispositivos, aunque algunos teléfonos Android anteriores podrían necesitar un nuevo perfil. Los usuarios no tendrán que volver a descargar su correo electrónico.

Para obtener más información, vea [Usar híbrido mínimo para migrar rápidamente buzones de Exchange a Office 365](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate).

### <a name="full-hybrid"></a>Híbrido completo

En una migración híbrida completa, tiene muchos cientos, hasta decenas de miles, de buzones de correo y mueve algunos o todos a Microsoft 365. Como estas migraciones suelen ser a largo plazo, las migraciones híbridas permiten:

- Muestre a los usuarios locales la información del calendario de disponibilidad para los usuarios de Microsoft 365 y viceversa.
- Vea una lista global unificada de direcciones que contiene destinatarios tanto en el entorno local como en Microsoft 365.
- Vea las propiedades completas del destinatario de Outlook para todos los usuarios, independientemente de si son locales o en Microsoft 365.
- Proteja la comunicación por correo electrónico entre servidores de Exchange locales y Office 365 mediante TLS y certificados.
- Trate los mensajes enviados entre servidores de Exchange locales y Microsoft 365 como internos, lo que les permite:
  - Los agentes de transporte y cumplimiento deben evaluar y procesar correctamente los mensajes internos.
  - Omita los filtros antispam.

Las migraciones híbridas completas son las mejores para las organizaciones que esperan permanecer en una configuración híbrida durante muchos meses o más. Obtendrá las características enumeradas anteriormente en esta sección, además de la sincronización de directorios, las mejores características de cumplimiento integrado y la capacidad de mover buzones hacia y desde Microsoft 365 mediante movimientos de buzones en línea. Microsoft 365 se convierte en una extensión de la organización local.

Aspectos a tener en cuenta sobre la migración híbrida completa:

- No son adecuadas para todas las organizaciones. Debido a la complejidad de las migraciones híbridas completas, las organizaciones con menos de unos cientos de buzones no suelen ver ventajas que justifiquen el esfuerzo y el costo implicados. En tales casos, se recomienda considerar la migración híbrida de transición o mínima en su lugar.
- Debe configurar la sincronización de directorios mediante Azure Active Directory (Azure AD) Connect entre los servidores de Active Directory local y Microsoft 365.
- Los usuarios podrán iniciar sesión en su buzón de Microsoft 365 con el mismo nombre de usuario y contraseña que usan al iniciar sesión en la red local. (Esta funcionalidad requiere Azure AD Connect con sincronización de contraseñas o Servicios de federación de Active Directory (AD FS)).
- Necesita una licencia de Microsoft 365 que incluya Exchange Online para cada buzón de usuario que migre.
- Los usuarios no necesitan configurar un nuevo perfil de Outlook en la mayoría de sus dispositivos, aunque algunos teléfonos Android anteriores podrían necesitar un nuevo perfil. Los usuarios no tendrán que volver a descargar su correo electrónico.

> [!IMPORTANT]
> Si su organización decide migrar buzones a Microsoft 365, pero planea mantener DirSync o Azure AD Connect en su lugar para seguir administrando cuentas de usuario desde Active Directory local, debe mantener al menos un servidor exchange local. Si se quitan todos los servidores de Exchange, no podrá realizar cambios en los destinatarios de Exchange en Exchange Online. Esto se debe a que el origen de la autoridad permanece en el Active Directory local y es necesario realizar cambios allí.

Si una migración híbrida completa le parece adecuada, consulte los siguientes recursos útiles:

- [Asistente para la implementación de Exchange](/exchange/exchange-deployment-assistant)
- [Implementaciones híbridas de Exchange Server](/exchange/exchange-hybrid)
- [Asistente de configuración híbrida](/exchange/hybrid-configuration-wizard)
- [Preguntas más frecuentes acerca del asistente de configuración híbrida](/exchange/hybrid-configuration-wizard-faqs)
- [Requisitos previos para la implementación híbrida](/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>Actualización a una versión más reciente de Exchange Server local

Creemos firmemente que obtiene el mejor valor y experiencia de usuario mediante la migración completa a Microsoft 365. Pero entendemos que algunas organizaciones necesitan mantener algunos servidores de Exchange en el entorno local. Esto puede deberse a requisitos normativos, para garantizar que los datos no se almacenan en un centro de datos externo, porque tiene una configuración o requisitos únicos que no se pueden cumplir en la nube, o porque necesita Exchange para administrar buzones de correo en la nube porque todavía usa Active Directory local. En cualquier caso, si mantiene Exchange local, debe asegurarse de que el entorno de Exchange 2010 se actualice al menos a Exchange 2013 o Exchange 2016.

Para obtener la mejor experiencia, se recomienda actualizar el entorno local restante a Exchange 2016. No es necesario instalar Exchange Server 2013 si desea pasar directamente de Exchange Server 2010 a Exchange Server 2016.

Exchange 2016 incluye todas las características de las versiones anteriores de Exchange. Coincide con la experiencia disponible con Microsoft 365, aunque algunas características solo están disponibles en Microsoft 365. Echa un vistazo a algunas de las cosas que te han faltado:

|Versión de Exchange|Características|
|---|---|
|**Exchange 2013**|La arquitectura simplificada reduce el número de roles de servidor a tres (buzón, acceso de cliente, transporte perimetral)|
||Directivas de prevención de pérdida de datos (DLP) que ayudan a evitar que se filtre información confidencial|
||Experiencia de Outlook Web App mejorada|
|**Exchange 2016**|*Características de Exchange 2013 y ...*|
||Roles de servidor más simplificados para solo buzón y transporte perimetral|
||DLP mejorado junto con la integración con SharePoint|
||Resistencia mejorada de la base de datos|
||Colaboración de documentos en línea|


|Consideración|Más información|
|---|---|
|Fechas de finalización del soporte técnico|Al igual que Exchange 2010, cada versión de Exchange tiene su propia fecha de finalización de soporte técnico: <br/><br/> Exchange 2013 : abril de 2023 <br/><br/> Exchange 2016 - Octubre de 2025 <br/><br/> Cuanto antes finalice la fecha de finalización del soporte técnico, antes tendrá que realizar otra migración. ¡Abril de 2023 está mucho más cerca de lo que crees!|
|Ruta de migración a Exchange 2013 o 2016|La ruta de migración de Exchange 2010 a una versión más reciente es la misma si elige Exchange 2013 o Exchange 2016: <br/><br/> Instale Exchange 2013 o 2016 en la organización de Exchange 2010 existente. <br/><br/> Mueva servicios y otra infraestructura a Exchange 2013 o 2016. <br/><br/> Mueva buzones de correo y carpetas públicas a Exchange 2013 o 2016 Retirar los servidores restantes de Exchange 2010.|
|Coexistencia de versiones|Al migrar a Exchange 2013 o Exchange 2016, puede instalar cualquiera de las versiones en una organización existente de Exchange 2010. Esto le permite instalar uno o varios servidores de Exchange 2013 o Exchange 2016 y realizar la migración.|
|Hardware de servidor|Los requisitos de hardware del servidor han cambiado desde Exchange 2010. Asegúrese de que el hardware es compatible. Obtenga más información sobre los requisitos de hardware para cada versión aquí: <br/><br/> [Requisitos del sistema para Exchange 2016](/Exchange/plan-and-deploy/system-requirements?view=exchserver-2016&preserve-view=true) <br/><br/> [Requisitos del sistema para Exchange 2013](/Exchange/exchange-2013-system-requirements-exchange-2013-help) <br/><br/> Con las mejoras significativas en el rendimiento de Exchange y el aumento de la potencia informática y la capacidad de almacenamiento en servidores más recientes, es probable que necesite menos servidores para admitir el mismo número de buzones.|
|Versión del sistema operativo|Las versiones mínimas del sistema operativo admitidas para cada versión son: <br/><br/> Exchange 2016: Windows Server 2012 <br/><br/> Exchange 2013: Windows Server 2008 R2 SP1 <br/><br/> Puede encontrar más información sobre la compatibilidad del sistema operativo en [Matriz de compatibilidad de Exchange](/exchange/plan-and-deploy/supportability-matrix).|
|Nivel funcional del bosque de Active Directory|Los niveles funcionales mínimos admitidos del bosque de Active Directory para cada versión son: <br/><br/> Exchange 2016: Windows Server 2008 R2 SP1 <br/><br/> Exchange 2013: Windows Server 2003 <br/><br/> Puede encontrar más información sobre la compatibilidad de nivel funcional de bosque en [Matriz de compatibilidad de Exchange](/exchange/plan-and-deploy/supportability-matrix).|
|Versiones de cliente de Office|Las versiones mínimas de cliente de Office admitidas para cada versión son: <br/><br/> Exchange 2016: Office 2010 (con las actualizaciones más recientes) <br/><br/> Exchange 2013: Office 2007 SP3 <br/><br/> Obtenga más información sobre la compatibilidad con clientes de Office en [Matriz de compatibilidad de Exchange](/exchange/plan-and-deploy/supportability-matrix).|

Use los siguientes recursos para ayudar con la migración:

- [Asistente para la implementación de Exchange](/exchange/exchange-deployment-assistant)
- Cambios en el esquema de Active Directory para Exchange [2016](/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2016&preserve-view=true), [2013](/Exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)
- Requisitos del sistema para Exchange [2016](/exchange/plan-and-deploy/system-requirements?view=exchserver-2016&preserve-view=true), [2013](/Exchange/exchange-2013-system-requirements-exchange-2013-help)
- Requisitos previos para Exchange [2016](/exchange/plan-and-deploy/prerequisites?view=exchserver-2016&preserve-view=true), [2013](/Exchange/exchange-2013-prerequisites-exchange-2013-help)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Resumen de las opciones para el cliente y los servidores de Office 2010 y Windows 7

Para obtener un resumen visual de las opciones de actualización y migración a la nube para clientes de Office 2010 y servidores de Windows 7, consulte el [póster de final del soporte técnico.](../downloads/Office2010Windows7EndOfSupport.pdf)

[![Fin del soporte técnico para clientes y servidores de Office 2010 y póster de Windows 7.](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Este póster de una página muestra las distintas rutas de acceso que puede tomar para responder a los productos de cliente y servidor de Office 2010 y Windows 7 llegando al final del soporte técnico, con rutas de acceso preferidas y compatibilidad con opciones en Microsoft 365 Enterprise resaltadas.

También puede [descargar](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) este póster e imprimirlo en formato de letra, legal o tabloide (11 x 17).

## <a name="what-if-i-need-help"></a>¿Y si necesito ayuda?

Si va a migrar a Microsoft 365, es posible que pueda usar nuestro servicio de Microsoft FastTrack. FastTrack proporciona procedimientos recomendados, herramientas y recursos para que la migración a Microsoft 365 sea lo más fluida posible. Lo mejor de todo es que un ingeniero de soporte técnico le guiará desde el planeamiento y el diseño hasta la migración del último buzón. Para obtener más información sobre FastTrack, consulte [Microsoft FastTrack](https://fasttrack.microsoft.com/).

Si tiene problemas durante la migración a Microsoft 365 y no usa FastTrack o va a migrar a una versión más reciente de Exchange Server, estos son algunos recursos que puede usar:

- [Comunidad de soporte técnico](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [Soporte al cliente](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-articles"></a>Artículos relacionados

[Recursos para ayudarle a actualizar desde servidores y clientes de Office 2010](upgrade-from-office-2010-servers-and-products.md)
