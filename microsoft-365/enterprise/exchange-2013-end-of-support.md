---
title: Exchange plan de fin de soporte técnico de 2013
ms.author: jhendr
author: JoanneHendrickson
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
ms.assetid: e150e7b9-c432-4c8d-a0ae-c11847129a7d
f1.keywords:
- NOCSH
description: Exchange 2013 llegará a su fin de soporte técnico en abril de 2023. Use este plan de planeación para prepararse para actualizar a Exchange Online o a una versión posterior de Exchange Server local.
ms.openlocfilehash: 2b949c113be16db97d68d92f2f1529245c287e48
ms.sourcegitcommit: aac7e002ec6e10a41baa2d0bd38614b0ed471a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2022
ms.locfileid: "62245140"
---
# <a name="exchange-2013-end-of-support-roadmap"></a>Exchange plan de fin de soporte técnico de 2013

*Este artículo se aplica tanto a Microsoft 365 Enterprise como a Office 365 Enterprise.*

Exchange Server 2013 llegará a su fin de soporte técnico el 11 de abril de **2023**. Si aún no ha iniciado la migración de Exchange 2013 a Microsoft 365, Office 365 o Exchange 2019, ahora es el momento de empezar a planear.

## <a name="what-does-end-of-support-mean"></a>¿Qué *significa el fin de la compatibilidad?*

La mayoría de los productos de Microsoft tienen un ciclo de vida de soporte técnico durante el cual obtienen nuevas características, correcciones de errores, correcciones de seguridad, y así sucesivamente. Este ciclo de vida suele durar 10 años desde la versión inicial del producto. El final de este ciclo de vida se conoce como el fin del soporte técnico del producto. Dado que Exchange 2013 llega a su fin de soporte técnico el 11 de abril de 2023, Microsoft ya proporcionará:

- Soporte técnico para los problemas que pueden producirse.
- Correcciones de errores para problemas que pueden afectar a la estabilidad y facilidad de uso del servidor.
- Correcciones de seguridad para vulnerabilidades que pueden hacer que el servidor sea vulnerable a infracciones de seguridad.
- Actualizaciones de zona horaria.

La instalación de Exchange 2013 seguirá en ejecución después de esta fecha. Pero debido a los cambios mencionados anteriormente, se recomienda encarecidamente migrar de Exchange 2013 a Exchange 2019 tan pronto como sea posible.


## <a name="what-are-my-options"></a>¿Cuáles son mis opciones?

Es un buen momento para explorar sus opciones y preparar un plan de migración. Puede:

- Migre a Microsoft 365. Migre buzones, carpetas públicas y otros datos mediante la migración total, híbrida mínima o híbrida completa. A continuación, quite los servidores Exchange locales y Active Directory.
- Actualización Exchange 2013. Pase a Exchange 2019 para los servidores locales.

> [!IMPORTANT]
> Si su organización decide migrar buzones a Microsoft 365 pero planea seguir usando Azure AD Conectar para administrar cuentas de usuario en Active Directory, debe mantener al menos un servidor de Microsoft Exchange local. Si quita todos los servidores Exchange, no podrá realizar cambios en los destinatarios Exchange en Exchange Online porque el origen de la autoridad es su Active Directory local. En este escenario, tiene las siguientes opciones:
>
>- *Se recomienda:* Migre los buzones Microsoft 365 y actualice su entorno a Exchange 2019 antes del 11 de abril de 2023. Use Exchange 2013 para conectarse a Microsoft 365 y migrar buzones. Después, actualice de Exchange 2013 a Exchange 2019 y desmantela los servidores que Exchange 2013.
>- Si no puede completar una migración a Exchange Online y actualizar los servidores locales antes del 11 de abril de 2023, actualice primero de Exchange 2013 Exchange Exchange 2019 y, a continuación, use Exchange 2019 para migrar buzones a Microsoft 365.

Estas son las tres rutas de acceso que puede tomar para evitar el fin de la compatibilidad con Exchange Server 2013.

## <a name="migrate-to-microsoft-365"></a>Migrar a Microsoft 365

Migrar a Microsoft 365 es la mejor y más sencilla opción para ayudarle a retirar su Exchange de 2013. Con una migración a Microsoft 365, puede realizar un solo salto de la tecnología antigua a las características actuales, incluidas:

- Buzones más grandes con mayor resistencia de datos;
- Capacidades de seguridad como la protección contra correo no deseado y antimalware, 
- Capacidades de cumplimiento como prevención de pérdida de datos, directivas de retención, In-Place y retención por juicio, exhibición de documentos electrónicos local y mucho más;
- Integración con SharePoint Online, OneDrive, Teams, Power BI y otros servicios Microsoft 365 web;
- Bandeja de entrada centrada; y
- Análisis avanzado y Viva Ideas.

Microsoft 365 obtiene primero nuevas características y experiencias, para que su organización pueda empezar a usarlos de inmediato. Además, no tendrá que preocuparse de:

- Comprar y mantener hardware;
- Pagar para ejecutar y refrescar los servidores;
- Mantener los servidores actualizados en las correcciones de seguridad, producto y zona horaria;
- Mantener el almacenamiento del servidor y el software para admitir los requisitos de cumplimiento; o
- Actualizar a una nueva versión de Exchange; siempre estás en la última versión con Microsoft 365.

### <a name="how-should-i-migrate-to-microsoft-365"></a>¿Cómo debo migrar a Microsoft 365?

Según la organización, tiene algunas opciones para llegar a Microsoft 365. En primer lugar, debe tener en cuenta algunas cosas, como:

- El número de buzones que necesita mover;
- Cuánto tiempo desea que dure la migración; y
- Tanto si necesita una integración perfecta entre el entorno local y Microsoft 365 durante la migración.

En esta tabla se muestran las opciones de migración y los factores más importantes que determinan qué método usar.

<br>

****

|Opción de migración|Tamaño de la organización|Duración|
|---|---|---|
|Migración total|Menos de 150 buzones|Una semana o menos|
|Migración híbrida mínima|Menos de 150 buzones|Unas semanas o menos|
|Migración híbrida completa|Más de 150 buzones|Unas semanas o más|
|

En las secciones siguientes se ofrece información general sobre estos métodos. Para obtener más información, vea [Decide on a migration path](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27).

### <a name="cutover-migration"></a>Migración total

En una migración total, se migran todos los buzones, grupos de distribución, contactos, entre otros, a Office 365 una fecha y hora establecidas. Cuando haya terminado, cierre los servidores de Exchange locales y comience a usar Microsoft 365 exclusivamente.

La migración de recortes es ideal para organizaciones pequeñas que no tienen muchos buzones, que desean llegar Microsoft 365 la migración rápida y no quieren ocuparse de la complejidad de los otros métodos. Pero debe completarse en una semana o menos. Y requiere que los usuarios vuelvan a configurar sus Outlook perfiles. La migración de recorte puede migrar hasta 2.000 buzones, pero se recomienda usarlo para un máximo de 150. Si intenta migrar más, puede que se le agote el tiempo para transferir todos los buzones antes de la fecha límite, y el personal de soporte técnico de TI puede agobiarse con las solicitudes para ayudar a los usuarios a volver a configurar Outlook.

Estas son las cosas que debe tener en cuenta acerca de la migración de recortes:

- Microsoft 365 tendrá que conectarse a los servidores de Exchange 2013 mediante Outlook cualquier lugar a través del puerto TCP 443.
- Todos los buzones locales se mueven a Microsoft 365.
- Necesitará una cuenta de administrador local que tenga acceso de lectura a los buzones de los usuarios.
- Los Exchange 2013 aceptados que desea usar en Microsoft 365 deben agregarse como dominios comprobados en el servicio.
- Entre cuando se inicia la migración y cuando se inicia la fase de finalización, Microsoft 365 sincronizará periódicamente los buzones de correo Microsoft 365 y locales. Esto le permite completar la migración sin preocuparse de que el correo electrónico se deje en sus buzones locales.
- Los usuarios recibirán nuevas contraseñas temporales para su Microsoft 365 cuenta. Necesitarán cambiar esas cuando inicien sesión en sus buzones por primera vez.
- Necesitará una licencia de Microsoft 365 que incluya Exchange Online para cada buzón de usuario que migre.
- Los usuarios tendrán que configurar un nuevo perfil Outlook en cada uno de sus dispositivos y volver a descargar su correo electrónico. La cantidad de correo electrónico que Outlook descargará puede variar. Para obtener más información, vea [Trabajar sin conexión en Outlook](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

Para obtener más información acerca de la migración de recortes, vea:

- [Lo que necesita saber sobre una migración de correo electrónico sin escalas](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [Realizar una migración de correo electrónico a Office 365](/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>Migración híbrida mínima

En una migración híbrida mínima, o express, se mueven unos cientos de buzones a Microsoft 365 en unas pocas semanas. Este método no admite características avanzadas de migración híbrida, como la información de calendario de disponibilidad compartida.

La migración híbrida mínima es ideal para las organizaciones que necesitan tardar más tiempo en migrar sus buzones a Microsoft 365, pero aún planean completar la migración en unas pocas semanas. Obtiene algunas de las ventajas de la migración híbrida completa más *avanzada* sin gran parte de la complejidad. Puede controlar cuántos y qué buzones migrar en un momento determinado. Microsoft 365 los buzones de correo se crearán con los nombres de usuario y las contraseñas de las cuentas locales. Y, a diferencia de las migraciones de recorte, los usuarios no tienen que volver a crear sus Outlook de usuario.

Estas son las cosas que debe tener en cuenta acerca de la migración híbrida mínima:

- Deberá realizar una sincronización de directorios única entre los servidores locales de Active Directory y Microsoft 365.
- Los usuarios podrán iniciar sesión en su buzón de Microsoft 365 con el mismo nombre de usuario y contraseña que antes de su buzón.
- Necesitará una licencia de Microsoft 365 que incluya Exchange Online para cada buzón de usuario que migre.
- Los usuarios no necesitarán configurar un nuevo perfil Outlook en la mayoría de sus dispositivos, aunque algunos teléfonos Android más antiguos podrían necesitar un perfil nuevo. Los usuarios no necesitarán volver a descargar su correo electrónico.

Para obtener más información, vea [Use Minimal Hybrid to quickly migrate Exchange mailboxes to Office 365](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate).

### <a name="full-hybrid"></a>Híbrido completo

En una migración híbrida completa, tiene muchos cientos, hasta decenas de miles, de buzones y mueve algunos o todos a Microsoft 365. Dado que estas migraciones suelen ser a largo plazo, las migraciones híbridas hacen posible lo siguiente:

- Mostrar a los usuarios locales la información del calendario de disponibilidad para los usuarios Microsoft 365 y viceversa.
- Vea una lista global unificada de direcciones que contiene destinatarios tanto locales como Microsoft 365.
- Ver todas Outlook de destinatarios para todos los usuarios, independientemente de si son locales o en Microsoft 365.
- Comunicación de correo electrónico segura entre servidores Exchange locales y Office 365 mediante TLS y certificados.
- Trate los mensajes enviados entre servidores Exchange locales y Microsoft 365 como internos, lo que les permite:
  - Los agentes de transporte y cumplimiento deben evaluar y procesar correctamente los mensajes internos.
  - Omitir filtros contra correo no deseado.

Las migraciones híbridas completa son las mejores para las organizaciones que esperan permanecer en una configuración híbrida durante varios meses o más. Obtiene las características enumeradas anteriormente en esta sección, además de la sincronización de directorios, las características de cumplimiento mejor integradas y la capacidad de mover buzones a y desde Microsoft 365 mediante movimientos de buzones en línea. Microsoft 365 se convierte en una extensión de la organización local.

Aspectos a tener en cuenta sobre la migración híbrida completa:

- No son adecuados para todas las organizaciones. Debido a la complejidad de las migraciones híbridas completa, las organizaciones con menos de unos pocos cientos de buzones no suelen ver ventajas que justifiquen el esfuerzo y el costo implicados. En estos casos, se recomienda considerar la migración híbrida mínima o de recorte.
- Debe configurar la sincronización de directorios mediante Azure Active Directory (Azure AD) Conectar entre los servidores locales de Active Directory y Microsoft 365.
- Los usuarios podrán iniciar sesión en su buzón de Microsoft 365 con el mismo nombre de usuario y contraseña que usan al iniciar sesión en la red local. (Esta funcionalidad requiere Azure AD Conectar sincronización de contraseñas o servicios de federación de Active Directory).
- Necesita una licencia Microsoft 365 que incluya Exchange Online para cada buzón de usuario que migre.
- Los usuarios no necesitan configurar un nuevo perfil de Outlook en la mayoría de sus dispositivos, aunque es posible que algunos teléfonos Android más antiguos necesiten un perfil nuevo. Los usuarios no necesitarán volver a descargar su correo electrónico.

> [!IMPORTANT]
> Si su organización decide migrar buzones a Microsoft 365 pero planea mantener Azure AD Conectar para administrar cuentas de usuario en Active Directory, debe mantener al menos un servidor Exchange local. Si se quitan Exchange servidores, no podrá realizar cambios en Exchange destinatarios. Esto se debe a que el origen de la autoridad es Active Directory y es necesario realizar cambios allí.

Si una migración híbrida completa suena adecuada para usted, vea los siguientes recursos útiles:

- [Exchange de implementación](/exchange/exchange-deployment-assistant)
- [Implementaciones híbridas de Exchange Server](/exchange/exchange-hybrid)
- [Asistente de configuración híbrida](/exchange/hybrid-configuration-wizard)
- [Preguntas más frecuentes acerca del asistente de configuración híbrida](/exchange/hybrid-configuration-wizard-faqs)
- [Requisitos previos para la implementación híbrida](/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>Actualizar a una versión más reciente de Exchange Server local

Creemos firmemente que obtiene el mejor valor y experiencia de usuario mediante la migración completa a Microsoft 365. Pero entendemos que algunas organizaciones necesitan mantener algunos servidores Exchange locales. Esto puede deberse a requisitos normativos, para garantizar que los datos no se almacenan en un centro de datos externo, porque tiene una configuración única o requisitos que no se pueden cumplir en la nube, o porque necesita Exchange para administrar buzones en la nube porque todavía usa Active Directory local. En cualquier caso, si mantiene Exchange local, debe asegurarse de que Exchange entorno de 2013 se actualice.

Para obtener la mejor experiencia, se recomienda actualizar el entorno local restante a Exchange 2019. No es necesario instalar Exchange Server 2016 porque puede ir directamente de Exchange Server 2013 a Exchange Server 2019. Exchange 2019 coincide más estrechamente con la experiencia disponible con Microsoft 365, aunque algunas características solo están disponibles en Microsoft 365.



****
A continuación se muestran aspectos importantes que debe saber sobre la actualización Exchange 2013:

|Elemento|Más información|
|---|---|
|Fechas de finalización del soporte técnico|Al Exchange 2013, cada versión de Exchange tiene su propia fecha de fin de soporte: <p> Exchange 2013 - Abril de 2023 <p> Abril de 2023 está mucho más cerca de lo que crees.|
|Ruta de migración a Exchange 2019|La ruta de migración de Exchange 2013 a una versión más reciente es sencilla: <p> Instale Exchange 2019 en su organización Exchange 2013. <p> Mover servicios y datos de Exchange 2013 a Exchange 2019 y retirar Exchange servidores de 2013.|
|Hardware de servidor|Los requisitos de hardware del servidor han cambiado Exchange 2013. Asegúrese de que el hardware es compatible. Encontrará más información sobre los requisitos de hardware aquí: <p> [Exchange del sistema de 2019](/exchange/plan-and-deploy/system-requirements?view=exchserver-2019) <p>Con las mejoras significativas en el rendimiento de Exchange y el aumento de la capacidad informática y de almacenamiento en servidores más recientes, es probable que necesite menos servidores para admitir el mismo número de buzones.|
|Versión del sistema operativo|La versión mínima del sistema operativo compatible para Exchange 2019 es Windows Server 2019. Windows compatibilidad con Server 2022 próximamente <p> Encontrará más información sobre la compatibilidad del sistema operativo [en Exchange Matriz de compatibilidad](/exchange/plan-and-deploy/supportability-matrix).|
|Nivel funcional del bosque de Active Directory|El nivel funcional mínimo compatible del bosque de Active Directory es Windows Server 2012 R2. Encontrará más información sobre la compatibilidad de nivel funcional del bosque [en Exchange Matriz de compatibilidad](/exchange/plan-and-deploy/supportability-matrix).|
|Office cliente|La versión de cliente Office mínima admitida también se documenta en la [Exchange de compatibilidad.](/exchange/plan-and-deploy/supportability-matrix?view=exchserver-2019#clients)|
|

Use los siguientes recursos para ayudar con la migración:

- [Exchange de implementación](/exchange/exchange-deployment-assistant)
- Cambios en el esquema de Active Directory [para Exchange 2019](/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2019)
- Requisitos [del sistema para Exchange 2019](/exchange/plan-and-deploy/system-requirements?view=exchserver-2019)


## <a name="what-if-i-need-help"></a>¿Qué ocurre si necesito ayuda?

Si está migrando a Microsoft 365, puede ser elegible para usar nuestro servicio de FastTrack Microsoft. FastTrack proporciona procedimientos recomendados, herramientas y recursos para que la migración a Microsoft 365 sea lo más sencilla posible. Lo mejor de todo es que un ingeniero de soporte técnico le ayudará desde la planeación y el diseño hasta la migración del último buzón. Para obtener más información FastTrack, vea [Microsoft FastTrack](https://fasttrack.microsoft.com/).

Si tiene problemas durante la migración a Microsoft 365 y no usa FastTrack o está migrando a una versión más reciente de Exchange Server, estos son algunos recursos que puede usar:

- [Comunidad de soporte técnico](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [Soporte al cliente](https://support.microsoft.com/gp/support-options-for-business)


