---
title: Exchange hoja de ruta de fin de soporte técnico de 2013
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
description: Exchange 2013 llegará a su fin en abril de 2023. Use este plan de planificación para preparar la actualización a Exchange Online o a una versión posterior de Exchange Server local.
ms.openlocfilehash: 0d0cf068ad018e710c6d8e861ac04acfd261def9
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2022
ms.locfileid: "65468512"
---
# <a name="exchange-2013-end-of-support-roadmap"></a>Exchange hoja de ruta de fin de soporte técnico de 2013

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Exchange Server 2013 llegará a su fin el **11 de abril de 2023**. Si aún no ha iniciado la migración de Exchange 2013 a Microsoft 365, Office 365 o Exchange 2019, ahora es el momento de empezar a planear.

## <a name="what-does-end-of-support-mean"></a>¿Qué significa *el fin del soporte* técnico?

La mayoría de los productos de Microsoft tienen un ciclo de vida de soporte técnico durante el cual obtienen nuevas características, correcciones de errores, correcciones de seguridad, etc. Este ciclo de vida suele durar 10 años a partir de la versión inicial del producto. El final de este ciclo de vida se conoce como el fin del soporte técnico del producto. Dado que Exchange 2013 llega a su fin de soporte técnico el 11 de abril de 2023, Microsoft ya no proporcionará lo siguiente después de esta fecha:

- Soporte técnico para los problemas que pueden producirse.
- Correcciones de errores para problemas que pueden afectar a la estabilidad y facilidad de uso del servidor.
- Correcciones de seguridad para las vulnerabilidades que pueden hacer que el servidor sea vulnerable a infracciones de seguridad.
- Actualizaciones de zona horaria.

La instalación de Exchange 2013 continuará ejecutándose después de esta fecha. Pero debido a los cambios enumerados anteriormente, se recomienda encarecidamente migrar de Exchange 2013 a Exchange 2019 lo antes posible.


## <a name="what-are-my-options"></a>¿Cuáles son mis opciones?

Es un buen momento para explorar las opciones y preparar un plan de migración. Puede:

- Migre a Microsoft 365. Migre buzones de correo, carpetas públicas y otros datos mediante la migración híbrida, híbrida mínima o completa. A continuación, quite los servidores de Exchange locales y Active Directory.
- Actualice Exchange 2013. Vaya a Exchange 2019 para los servidores locales.

> [!IMPORTANT]
> Si su organización decide migrar buzones a Microsoft 365, pero planea seguir usando Azure AD Conectar para administrar cuentas de usuario en Active Directory, debe mantener al menos un servidor de Microsoft Exchange local. Si quita todos los servidores de Exchange, no podrá realizar cambios en Exchange destinatarios en Exchange Online porque el origen de la autoridad es el Active Directory local. En este escenario, tiene las siguientes opciones:
>
>- *Recomienda:* Migre los buzones a Microsoft 365 y actualice el entorno a Exchange 2019 antes del 11 de abril de 2023. Use Exchange 2013 para conectarse a Microsoft 365 y migrar buzones. A continuación, actualice de Exchange 2013 a Exchange 2019 y retire los servidores que ejecutan Exchange 2013.
>- Si no puede completar una migración a Exchange Online y actualizar los servidores locales antes del 11 de abril de 2023, actualice primero de Exchange 2013 a Exchange 2019 y, a continuación, use Exchange 2019 para migrar buzones a Microsoft 365.

Estas son las tres rutas de acceso que puede tomar para evitar el final de la compatibilidad con Exchange Server 2013.

## <a name="migrate-to-microsoft-365"></a>Migrar a Microsoft 365

La migración a Microsoft 365 es la mejor y más sencilla opción para ayudarle a retirar la implementación de Exchange 2013. Con una migración a Microsoft 365, puede realizar un único salto de la tecnología antigua a las características actuales, entre las que se incluyen:

- Buzones más grandes con mayor resistencia a los datos;
- Funcionalidades de seguridad como la protección contra correo no deseado y antimalware, 
- Funcionalidades de cumplimiento, como prevención de pérdida de datos, directivas de retención, In-Place y retención de litigios, exhibición de documentos electrónicos local y mucho más;
- Integración con SharePoint Online, OneDrive, Teams, Power BI y otros servicios de Microsoft 365;
- Bandeja de entrada centrada; Y
- Análisis avanzado y Ideas Viva.

Microsoft 365 también obtiene nuevas características y experiencias en primer lugar, de modo que su organización pueda empezar a usarlas de inmediato. Además, no tendrá que preocuparse por lo siguiente:

- Compra y mantenimiento de hardware;
- Pagar para ejecutar y enfriar los servidores;
- Mantener los servidores actualizados sobre las correcciones de seguridad, productos y zonas horarias;
- Mantener el almacenamiento y el software del servidor para admitir los requisitos de cumplimiento; O
- Actualizar a una nueva versión de Exchange; siempre está en la versión más reciente con Microsoft 365.

### <a name="how-should-i-migrate-to-microsoft-365"></a>¿Cómo debo migrar a Microsoft 365?

En función de su organización, tiene algunas opciones para llegar a Microsoft 365. En primer lugar, debe tener en cuenta algunas cosas, como:

- El número de buzones que necesita mover;
- Cuánto tiempo desea que dure la migración; Y
- Si necesita una integración sin problemas entre el entorno local y Microsoft 365 durante la migración.

En esta tabla se muestran las opciones de migración y los factores más importantes que determinan qué método usar.

<br>

****

|Opción de migración|Tamaño de la organización|Duración|
|---|---|---|
|Migración total|Menos de 150 buzones|Una semana o menos|
|Migración híbrida mínima|Menos de 150 buzones|Unas semanas o menos|
|Migración híbrida completa|Más de 150 buzones|Unas semanas o más|
|

En las secciones siguientes se proporciona información general sobre estos métodos. Para obtener más información, vea [Decidir una ruta de migración](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27).

### <a name="cutover-migration"></a>Migración total

En una migración de transición, se migran todos los buzones, grupos de distribución, contactos, etc., para Office 365 en una fecha y hora establecidas. Cuando haya terminado, apagará los servidores de Exchange locales y comenzará a usar Microsoft 365 exclusivamente.

La migración de transición es ideal para las organizaciones pequeñas que no tienen muchos buzones de correo, quieren llegar a Microsoft 365 rápidamente y no quieren lidiar con la complejidad de los otros métodos. Pero debe completarse en una semana o menos. Además, requiere que los usuarios vuelvan a configurar sus perfiles de Outlook. La migración de transición puede migrar hasta 2000 buzones, pero se recomienda usarla para un máximo de 150. Si intenta migrar más, podría quedar sin tiempo para transferir todos los buzones antes de la fecha límite, y el personal de soporte técnico de TI puede verse abrumado por las solicitudes para ayudar a los usuarios a volver a configurar Outlook.

Estas son las cosas que se deben tener en cuenta sobre la migración de transición:

- Microsoft 365 tendrá que conectarse a los servidores de Exchange 2013 mediante Outlook anywhere a través del puerto TCP 443.
- Todos los buzones locales se moverán a Microsoft 365.
- Necesitará una cuenta de administrador local que tenga acceso de lectura a los buzones de los usuarios.
- Los dominios aceptados de Exchange 2013 que desea usar en Microsoft 365 deben agregarse como dominios comprobados en el servicio.
- Entre el inicio de la migración y la fase de finalización, Microsoft 365 sincronizará periódicamente los buzones de Microsoft 365 y locales. Esto le permite completar la migración sin preocuparse de que el correo electrónico se quede atrás en los buzones locales.
- Los usuarios recibirán nuevas contraseñas temporales para su cuenta de Microsoft 365. Tendrán que cambiarlos cuando inicien sesión en sus buzones por primera vez.
- Necesitará una licencia de Microsoft 365 que incluya Exchange Online para cada buzón de usuario que migre.
- Los usuarios tendrán que configurar un nuevo perfil de Outlook en cada uno de sus dispositivos y volver a descargar su correo electrónico. La cantidad de correo electrónico que Outlook descargará puede variar. Para obtener más información, vea [Trabajar sin conexión en Outlook](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

Para obtener más información sobre la migración de transición, consulte:

- [Lo que necesita saber sobre una migración de correo electrónico de transición](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [Realizar una migración total del correo electrónico a Office 365](/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>Migración híbrida mínima

En una migración híbrida o rápida mínima, mueve unos cientos de buzones a Microsoft 365 en unas pocas semanas. Este método no admite características avanzadas de migración híbrida, como la información de calendario de disponibilidad compartida.

La migración híbrida mínima es ideal para las organizaciones que necesitan más tiempo para migrar sus buzones a Microsoft 365, pero que aún planean completar la migración en unas semanas. Obtendrá algunas de las ventajas de la *migración híbrida completa* más avanzada sin gran parte de la complejidad. Puede controlar cuántos y qué buzones se van a migrar en un momento determinado. Microsoft 365 buzones se crearán con los nombres de usuario y contraseñas de las cuentas locales. Además, a diferencia de las migraciones de transición, los usuarios no tienen que volver a crear sus perfiles de Outlook.

Estas son las cosas que se deben tener en cuenta sobre la migración híbrida mínima:

- Tendrá que realizar una sincronización de directorios única entre los servidores de Active Directory local y Microsoft 365.
- Los usuarios podrán iniciar sesión en su buzón de Microsoft 365 con el mismo nombre de usuario y contraseña que antes de su buzón.
- Necesitará una licencia de Microsoft 365 que incluya Exchange Online para cada buzón de usuario que migre.
- Los usuarios no tendrán que configurar un nuevo perfil de Outlook en la mayoría de sus dispositivos, aunque algunos teléfonos Android antiguos podrían necesitar un nuevo perfil. Los usuarios no tendrán que volver a descargar su correo electrónico.

Para obtener más información, vea [Usar híbrido mínimo para migrar rápidamente Exchange buzones de correo a Office 365](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate).

### <a name="full-hybrid"></a>Híbrido completo

En una migración híbrida completa, tiene muchos cientos, hasta decenas de miles, de buzones de correo y mueve algunos o todos a Microsoft 365. Como estas migraciones suelen ser a largo plazo, las migraciones híbridas permiten:

- Muestre a los usuarios locales la información del calendario de disponibilidad para los usuarios de Microsoft 365 y viceversa.
- Vea una lista de direcciones global unificada que contenga destinatarios tanto en el entorno local como en Microsoft 365.
- Vea las propiedades completas de Outlook destinatario para todos los usuarios, independientemente de si son locales o en Microsoft 365.
- Proteger la comunicación por correo electrónico entre servidores de Exchange locales y Office 365 mediante TLS y certificados.
- Trate los mensajes enviados entre servidores de Exchange locales y Microsoft 365 como internos, lo que les permite:
  - Los agentes de transporte y cumplimiento deben evaluar y procesar correctamente los mensajes internos.
  - Omita los filtros antispam.

Las migraciones híbridas completas son las mejores para las organizaciones que esperan permanecer en una configuración híbrida durante muchos meses o más. Obtendrá las características enumeradas anteriormente en esta sección, además de la sincronización de directorios, las características de cumplimiento integradas y la capacidad de mover buzones hacia y desde Microsoft 365 mediante movimientos de buzones en línea. Microsoft 365 se convierte en una extensión de la organización local.

Aspectos a tener en cuenta sobre la migración híbrida completa:

- No son adecuadas para todas las organizaciones. Debido a la complejidad de las migraciones híbridas completas, las organizaciones con menos de unos cientos de buzones no suelen ver ventajas que justifiquen el esfuerzo y el costo implicados. En tales casos, se recomienda considerar la migración híbrida de transición o mínima en su lugar.
- Debe configurar la sincronización de directorios mediante Azure Active Directory (Azure AD) Conectar entre los servidores de Active Directory local y Microsoft 365.
- Los usuarios podrán iniciar sesión en su buzón de Microsoft 365 con el mismo nombre de usuario y contraseña que usan al iniciar sesión en la red local. (Esta funcionalidad requiere Conectar de Azure AD con sincronización de contraseñas o Servicios de federación de Active Directory (AD FS)).
- Necesita una licencia de Microsoft 365 que incluya Exchange Online para cada buzón de usuario que migre.
- Los usuarios no necesitan configurar un nuevo perfil de Outlook en la mayoría de sus dispositivos, aunque algunos teléfonos Android anteriores podrían necesitar un nuevo perfil. Los usuarios no tendrán que volver a descargar su correo electrónico.

> [!IMPORTANT]
> Si su organización decide migrar buzones a Microsoft 365, pero planea mantener Azure AD Conectar para administrar cuentas de usuario en Active Directory, debe mantener al menos un servidor Exchange local. Si se quitan todos los servidores Exchange, no podrá realizar cambios en Exchange destinatarios. Esto se debe a que el origen de la autoridad es Active Directory y es necesario realizar cambios allí.

Si una migración híbrida completa le parece adecuada, consulte los siguientes recursos útiles:

- [Asistente para la implementación de Exchange](/exchange/exchange-deployment-assistant)
- [Implementaciones híbridas de Exchange Server](/exchange/exchange-hybrid)
- [Asistente de configuración híbrida](/exchange/hybrid-configuration-wizard)
- [Preguntas más frecuentes acerca del asistente de configuración híbrida](/exchange/hybrid-configuration-wizard-faqs)
- [Requisitos previos para la implementación híbrida](/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>Actualización a una versión más reciente de Exchange Server local

Creemos firmemente que obtiene el mejor valor y experiencia de usuario mediante la migración completa a Microsoft 365. Pero entendemos que algunas organizaciones necesitan mantener algunos servidores Exchange en el entorno local. Esto puede deberse a requisitos normativos, para garantizar que los datos no se almacenan en un centro de datos externo, porque tiene una configuración o requisitos únicos que no se pueden cumplir en la nube, o porque necesita Exchange para administrar buzones de correo en la nube porque todavía usa Active Directory local. En cualquier caso, si mantiene Exchange local, debe asegurarse de que se actualiza el entorno de Exchange 2013.

Para obtener la mejor experiencia, se recomienda actualizar el entorno local restante a Exchange 2019. No es necesario instalar Exchange Server 2016 porque puede pasar directamente de Exchange Server 2013 a Exchange Server 2019. Exchange 2019 coincide más estrechamente con la experiencia disponible con Microsoft 365, aunque algunas características solo están disponibles en Microsoft 365.



****
A continuación se muestran aspectos importantes que debe saber sobre la actualización de Exchange 2013:

|Elemento|Más información|
|---|---|
|Fechas de finalización del soporte técnico|Al igual que Exchange 2013, cada versión de Exchange tiene su propia fecha de finalización del soporte técnico: <p> Exchange 2013 - Abril de 2023 <p> ¡Abril de 2023 está mucho más cerca de lo que crees!|
|Ruta de migración a Exchange 2019|La ruta de migración de Exchange 2013 a una versión más reciente es sencilla: <p> Instale Exchange 2019 en la organización de Exchange 2013 existente. <p> Mover servicios y datos de Exchange 2013 a Exchange 2019 y retirar Exchange servidores de 2013.|
|Hardware de servidor|Los requisitos de hardware del servidor han cambiado a partir de Exchange 2013. Asegúrese de que el hardware es compatible. Obtenga más información sobre los requisitos de hardware aquí: <p> [requisitos del sistema de Exchange 2019](/exchange/plan-and-deploy/system-requirements?view=exchserver-2019) <p>Con las mejoras significativas en el rendimiento de Exchange y el aumento de la potencia informática y la capacidad de almacenamiento en servidores más recientes, es probable que necesite menos servidores para admitir el mismo número de buzones.|
|Versión del sistema operativo|La versión mínima del sistema operativo compatible para Exchange 2019 es Windows Server 2019. Windows compatibilidad con Server 2022 estará disponible próximamente <p> Puede encontrar más información sobre la compatibilidad del sistema operativo en [Exchange Matriz de compatibilidad](/exchange/plan-and-deploy/supportability-matrix).|
|Nivel funcional del bosque de Active Directory|El nivel funcional mínimo admitido del bosque de Active Directory es Windows Server 2012 R2. Puede encontrar más información sobre la compatibilidad de nivel funcional del bosque en [Exchange Matriz de compatibilidad](/exchange/plan-and-deploy/supportability-matrix).|
|Office versiones de cliente|La versión de cliente de Office mínima admitida también se documenta en la [matriz de compatibilidad de Exchange](/exchange/plan-and-deploy/supportability-matrix?view=exchserver-2019#clients).|
|

Use los siguientes recursos para ayudar con la migración:

- [Asistente para la implementación de Exchange](/exchange/exchange-deployment-assistant)
- Cambios en [el esquema de Active Directory para Exchange 2019](/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2019)
- Requisitos del sistema [para Exchange 2019](/exchange/plan-and-deploy/system-requirements?view=exchserver-2019)


## <a name="what-if-i-need-help"></a>¿Y si necesito ayuda?

Si va a migrar a Microsoft 365, es posible que pueda usar nuestro servicio de Microsoft FastTrack. FastTrack proporciona procedimientos recomendados, herramientas y recursos para que la migración a Microsoft 365 sea lo más fluida posible. Lo mejor de todo es que un ingeniero de soporte técnico le guiará desde el planeamiento y el diseño hasta la migración del último buzón. Para obtener más información sobre FastTrack, consulte [Microsoft FastTrack](https://fasttrack.microsoft.com/).

Si tiene problemas durante la migración a Microsoft 365 y no usa FastTrack o va a migrar a una versión más reciente de Exchange Server, estos son algunos recursos que puede usar:

- [Comunidad de soporte técnico](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [Soporte al cliente](https://support.microsoft.com/gp/support-options-for-business)


