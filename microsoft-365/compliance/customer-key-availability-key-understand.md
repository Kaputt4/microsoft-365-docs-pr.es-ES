---
title: Obtener más información sobre la clave de disponibilidad de Clave de cliente
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Obtenga información sobre la clave de disponibilidad que se usa para recuperar claves de cliente perdidas.
ms.openlocfilehash: 8e9903294d5fc25e51ef25c0ae6237c943dec6ab
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632029"
---
# <a name="learn-about-the-availability-key-for-customer-key"></a>Obtener más información sobre la clave de disponibilidad de Clave de cliente

La clave de disponibilidad es una clave raíz generada y aprovisionada automáticamente al crear una directiva de cifrado de datos. Microsoft 365 almacena y protege la clave de disponibilidad. La clave de disponibilidad es funcionalmente como las dos claves raíz que se suministran para el cifrado de servicio con clave de cliente. La clave de disponibilidad ajusta las claves un nivel inferior en la jerarquía de claves. A diferencia de las claves que proporciona y administra en Azure Key Vault, no puede acceder directamente a la clave de disponibilidad. Los servicios automatizados de Microsoft 365 administran la clave de disponibilidad mediante programación. Estos servicios inician operaciones automatizadas que nunca implican el acceso directo a la clave de disponibilidad.

El propósito principal de la clave de disponibilidad es proporcionar capacidad de recuperación de la pérdida inesperada de claves raíz que administra. La pérdida podría deberse a una mala administración o a una acción malintencionada. Si pierde el control de las claves raíz, póngase en contacto con el soporte técnico de Microsoft y Microsoft le ayudará a través del proceso de recuperación con la clave de disponibilidad. Usará la clave de disponibilidad para migrar a una nueva directiva de cifrado de datos con las nuevas claves raíz que aprovisione.

El almacenamiento y el control de la clave de disponibilidad son deliberadamente diferentes de las claves de Azure Key Vault por tres motivos:

- La clave de disponibilidad proporciona una capacidad de recuperación "break-glass" si se pierde el control sobre ambas claves de Azure Key Vault.
- La separación de los controles lógicos y las ubicaciones de almacenamiento seguras proporciona una defensa en profundidad y protege contra la pérdida de todas las claves y los datos de un único ataque o punto de error.
- La clave de disponibilidad proporciona una capacidad de alta disponibilidad si los servicios de Microsoft 365 no pueden acceder a las claves hospedadas en Azure Key Vault debido a errores transitorios. Esta regla solo se aplica al cifrado de servicios de Exchange Online y Skype Empresarial. Los archivos de SharePoint Online, OneDrive para la Empresa y Teams nunca usan la clave de disponibilidad a menos que indique explícitamente a Microsoft que inicie el proceso de recuperación.

Compartir la responsabilidad de proteger los datos, mediante una variedad de protecciones y procesos para la administración de claves, reduce en última instancia el riesgo de que todas las claves (y, por lo tanto, los datos) se pierdan o destruyan permanentemente. Microsoft le proporciona la única autoridad sobre la deshabilitación o destrucción de la clave de disponibilidad cuando deja el servicio. Por diseño, nadie de Microsoft tiene acceso a la clave de disponibilidad: solo es accesible mediante el código de servicio de Microsoft 365.

Consulte el [Centro de confianza de Microsoft](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data) para obtener más información sobre cómo protegemos las claves.
  
## <a name="availability-key-uses"></a>Usos de la clave de disponibilidad

La clave de disponibilidad proporciona capacidad de recuperación para escenarios en los que un malhechor externo o un insider malintencionado roba el control del almacén de claves, o cuando una mala administración involuntaria da como resultado la pérdida de claves raíz. Esta funcionalidad de recuperación se aplica a todos los servicios de Microsoft 365 compatibles con la clave de cliente. Los servicios individuales usan la clave de disponibilidad de forma diferente. Microsoft 365 solo usa la clave de disponibilidad de las maneras que se describen a continuación.

### <a name="exchange-online-and-skype-for-business-uses"></a>Usos de Exchange Online y Skype Empresarial

Además de la capacidad de recuperación, Exchange Online y Skype Empresarial usan la clave de disponibilidad para garantizar la disponibilidad de los datos durante problemas operativos transitorios o intermitentes relacionados con el acceso del servicio a las claves raíz. Cuando el servicio no puede acceder a ninguna de las claves de cliente en Azure Key Vault debido a errores transitorios, el servicio usa automáticamente la clave de disponibilidad. El servicio NUNCA va directamente a la clave de disponibilidad.

Los sistemas automatizados de Exchange Online y Skype Empresarial pueden usar la clave de disponibilidad durante errores transitorios para admitir servicios back-end automatizados como antivirus, detección electrónica, prevención de pérdida de datos, movimientos de buzones e indización de datos.

### <a name="sharepointonlineonedriveforbusinessandteamsfiles-uses"></a>SharePoint Online, OneDrive para la Empresa y los archivos de Teams usan

Para los archivos de SharePoint Online, OneDrive para la Empresa y Teams, la clave de disponibilidad NUNCA se usa fuera de la capacidad de recuperación y los clientes deben indicar explícitamente a Microsoft que inicie el uso de la clave de disponibilidad durante un escenario de recuperación. Las operaciones de servicio automatizadas solo dependen de las claves de cliente en el almacén de claves de Azure. Para obtener información detallada sobre cómo funciona la jerarquía de claves para estos servicios, vea cómo los archivos de [SharePoint Online, OneDrive](#how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key)para la Empresa y Teams usan la clave de disponibilidad.

## <a name="availability-key-security"></a>Seguridad de clave de disponibilidad

Microsoft comparte la responsabilidad de la protección de datos con usted mediante la creación de instancias de la clave de disponibilidad y la toma de medidas exhaustivas para protegerla. Microsoft no expone el control directo de la clave de disponibilidad a los clientes. Por ejemplo, solo puede girar las claves que posee en Azure Key Vault. Para obtener más información, vea [Roll o rotate a customer key or an availability key](customer-key-availability-key-roll.md).

### <a name="availability-key-secret-stores"></a>Almacenes de secretos de clave de disponibilidad

Microsoft protege las claves de disponibilidad en almacenes secretos internos controlados por el acceso, como azure Key Vault orientado al cliente. Implementamos controles de acceso para impedir que los administradores de Microsoft accedan directamente a los secretos incluidos en. Las operaciones del almacén secreto, incluida la rotación y eliminación de claves, se producen a través de comandos automatizados que nunca implican el acceso directo a la clave de disponibilidad. Las operaciones de administración del almacén secreto están limitadas a ingenieros específicos y requieren la escalación de privilegios a través de una herramienta interna, Caja de seguridad. La escalación de privilegios requiere la aprobación y justificación del administrador antes de su concesión. La caja de seguridad garantiza que el acceso esté limitado por el tiempo de revocación automática de acceso al expirar el tiempo o de cerrar sesión del ingeniero.

**Las claves de disponibilidad de Exchange Online** y Skype Empresarial se almacenan en un almacén secreto de Active Directory de Exchange Online. Las claves de disponibilidad se almacenan de forma segura dentro de contenedores específicos del espacio empresarial dentro del controlador de dominio de Active Directory. Esta ubicación de almacenamiento seguro es independiente y aislada del almacén secreto de archivos de SharePoint Online, OneDrive para la Empresa y Teams.

Las claves de disponibilidad de archivos de **SharePoint Online, OneDrive** para la Empresa y Teams se almacenan en un almacén secreto interno administrado por el equipo de servicio. Este servicio de almacenamiento secreto protegido tiene servidores front-end con extremos de aplicación y una base de datos SQL como back-end. Las claves de disponibilidad se almacenan en la base de datos de SQL y se encapsulan (cifran) mediante claves de cifrado de almacén secreto que usan una combinación de AES-256 y HMAC para cifrar la clave de disponibilidad en reposo. Las claves de cifrado del almacén secreto se almacenan en un componente aislado lógicamente de la misma base de datos de SQL y se cifran aún más con claves RSA-2048 contenidas en certificados administrados por la entidad de certificación (CA) de Microsoft. Estos certificados se almacenan en los servidores front-end del almacén secreto que realizan operaciones con la base de datos.

### <a name="defense-in-depth"></a>Defensa en profundidad

Microsoft emplea una estrategia de defensa en profundidad para evitar que actores malintencionados repercutan en la confidencialidad, integridad o disponibilidad de los datos de los clientes almacenados en la nube de Microsoft. Se implementan controles específicos preventivos y de investigación para proteger el almacén secreto y la clave de disponibilidad como parte de la estrategia de seguridad general.

Microsoft 365 está diseñado para evitar el uso incorrecto de la clave de disponibilidad. La capa de aplicación es el único método a través del cual se pueden usar claves, incluida la clave de disponibilidad, para cifrar y descifrar datos. Solo el código de servicio de Microsoft 365 tiene la capacidad de interpretar y recorrer la jerarquía clave para las actividades de cifrado y descifrado. Existe aislamiento lógico entre las ubicaciones de almacenamiento de claves de cliente, claves de disponibilidad, otras claves jerárquicas y datos de clientes. Este aislamiento mitiga el riesgo de exposición de datos en caso de que se vea comprometida una o varias ubicaciones. Cada capa de la jerarquía ha integrado capacidades de detección de intrusiones 24 x 7 para proteger los datos y secretos almacenados.

Los controles de acceso se implementan para evitar el acceso no autorizado a los sistemas internos, incluidos los almacenes secretos de clave de disponibilidad. Los ingenieros de Microsoft no tienen acceso directo a los almacenes secretos de clave de disponibilidad. Para obtener más información sobre los controles de acceso, revise [Controles de acceso administrativo en Microsoft 365](https://docs.microsoft.com/Office365/securitycompliance/office-365-administrative-access-controls-overview).

Los controles técnicos impiden que el personal de Microsoft pueda iniciar sesión en cuentas de servicio con privilegios elevados, que de lo contrario podrían usar los atacantes para suplantar los servicios Microsoft. Por ejemplo, estos controles impiden el inicio de sesión interactivo.

Los controles de seguimiento y registro de seguridad son otra protección de defensa en profundidad implementada que mitiga los riesgos para los servicios Microsoft y sus datos. Los equipos de servicio de Microsoft han implementado soluciones de supervisión activas que generan alertas y registros de auditoría. Todos los equipos de servicio cargan sus registros en un repositorio central donde se agregan y procesan los registros. Las herramientas internas examinan automáticamente los registros para confirmar que los servicios funcionan en un estado óptimo, resistente y seguro. La actividad inusual se marca para una revisión posterior.

Cualquier evento de registro que indique una posible infracción de la directiva de seguridad de Microsoft se llama inmediatamente a la atención de los equipos de seguridad de Microsoft. La seguridad de Microsoft 365 ha configurado alertas para detectar intentos de acceso a los almacenes secretos de clave de disponibilidad. También se generan alertas si el personal de Microsoft intenta iniciar sesión interactiva en cuentas de servicio, lo que está prohibido y protegido por controles de acceso. La seguridad de Microsoft 365 también detecta y alerta sobre las desviaciones del servicio de Microsoft 365 de las operaciones de línea base normales. Los malhechores que intentan hacer un uso incorrecto de los servicios de Microsoft 365 desencadenarían alertas que provocarían el desalojo del entorno en la nube de Microsoft.

## <a name="use-the-availability-key-to-recover-from-key-loss"></a>Usar la clave de disponibilidad para recuperarse de la pérdida de claves

Si pierde el control de las claves de cliente, la clave de disponibilidad le ofrece la capacidad de recuperar y volver a cifrar los datos.

### <a name="recovery-procedure-for-exchange-online-and-skype-for-business"></a>Procedimiento de recuperación para Exchange Online y Skype Empresarial

Si pierde el control de las claves de cliente, la clave de disponibilidad le ofrece la capacidad de recuperar los datos y volver a poner en línea los recursos de Microsoft 365 afectados. La clave de disponibilidad sigue protegiendo los datos mientras se recupera. En un nivel alto, para recuperarse completamente de la pérdida de claves, deberá crear un nuevo DEP y mover los recursos afectados a la nueva directiva.

Para cifrar los datos con claves de cliente nuevas, cree nuevas claves en Azure Key Vault, cree un nuevo DEP con las nuevas claves de cliente y, a continuación, asigne el nuevo DEP a los buzones cifrados actualmente con el DEP anterior para los que se perdieron o se han comprometido las claves.

Este proceso de cifrado puede tardar hasta 72 horas. Esta es la duración estándar al cambiar un DEP.
  
### <a name="recovery-procedure-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Procedimiento de recuperación para archivos de SharePoint Online, OneDrive para la Empresa y Teams

Para los archivos de SharePoint Online, OneDrive para la Empresa y Teams, la clave de disponibilidad NUNCA se usa fuera de la capacidad de recuperación. Debe indicar explícitamente a Microsoft que inicie el uso de la clave de disponibilidad durante un escenario de recuperación. Para iniciar el proceso de recuperación, póngase en contacto con Microsoft para activar la clave de disponibilidad. Una vez activada, la clave de disponibilidad se usa automáticamente para descifrar los datos, lo que te permite cifrar los datos con un DEP recién creado asociado a las nuevas claves de cliente.  

Esta operación es proporcional al número de sitios de la organización. Una vez que llames a Microsoft para usar la clave de disponibilidad, debes estar completamente conectado en un plazo de unas cuatro horas.

## <a name="how-exchange-online-and-skype-for-business-use-the-availability-key"></a>Cómo Exchange Online y Skype Empresarial usan la clave de disponibilidad

Al crear un DEP con clave de cliente, Microsoft 365 genera una clave de directiva de cifrado de datos (clave DEP) asociada con ese DEP. El servicio cifra la clave DEP tres veces: una con cada una de las claves de cliente y otra con la clave de disponibilidad. Solo se almacenan las versiones cifradas de la clave DEP y una clave DEP solo se puede descifrar con las claves de cliente o la clave de disponibilidad. A continuación, la clave DEP se usa para cifrar claves de buzón, que cifran buzones individuales.
  
Microsoft 365 sigue este proceso para descifrar y proporcionar datos cuando los clientes usan el servicio:
  
1. Descifra la clave DEP con la clave de cliente.

2. Use la clave DEP descifrada para descifrar una clave de buzón.

3. Use la clave de buzón de correo descifrada para descifrar el propio buzón, lo que le permite tener acceso a los datos del buzón.

## <a name="how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key"></a>Cómo usan los archivos de SharePoint Online, OneDrive para la Empresa y Teams la clave de disponibilidad

La arquitectura y la implementación de la clave de cliente y la clave de disponibilidad de SharePoint Online y OneDrive para la Empresa son diferentes de Exchange Online y Skype Empresarial.
  
Cuando una organización pasa a claves administradas por el cliente, Microsoft 365 crea una clave intermedia (TIK) específica de la organización. Microsoft 365 cifra la TIK dos veces, una vez con cada una de las claves de cliente, y almacena las dos versiones cifradas de la TIK. Solo se almacenan las versiones cifradas de la TIK y solo se puede descifrar una TIK con las claves de cliente. A continuación, la TIK se usa para cifrar claves de sitio, que luego se usan para cifrar claves blobs (también denominadas claves de fragmento de archivo). Según el tamaño del archivo, el servicio puede dividir un archivo en varios fragmentos de archivo cada uno con una clave única. Los blobs (fragmentos de archivo) se cifran con las claves blob y se almacenan en el servicio de almacenamiento de blobs de Microsoft Azure.
  
Microsoft 365 sigue este proceso para descifrar y proporcionar archivos de cliente cuando los clientes usan el servicio:

1. Descifra la TIK con la clave de cliente.

2. Use la TIK descifrada para descifrar una clave de sitio.

3. Use la clave de sitio descifrada para descifrar una clave blob.

4. Use la clave de blob descifrada para descifrar el blob.

Microsoft 365 descifra una TIK mediante la emisión de dos solicitudes de descifrado a Azure Key Vault con un ligero desplazamiento. El primero en finalizar ofrece el resultado, cancelando la otra solicitud.
  
En caso de que pierda el acceso a las claves de cliente, Microsoft 365 también cifra el TIK con una clave de disponibilidad y lo almacena junto con los TIKs cifrados con cada clave de cliente. El TIK cifrado con la clave de disponibilidad solo se usa cuando el cliente llama a Microsoft para obtener la ruta de recuperación cuando ha perdido el acceso a sus claves de forma malintencionada o accidental.
  
Por motivos de disponibilidad y escala, las TIK descifradas se almacenan en caché en una memoria caché de tiempo limitado. Dos horas antes de que una memoria caché de TIK expire, Microsoft 365 intenta descifrar cada TIK. Descifrar los TIK amplía la duración de la memoria caché. Si se produce un error de descifrado TIK durante un período de tiempo significativo, Microsoft 365 genera una alerta para notificar a los ingenieros antes de la expiración de la memoria caché. Solo si el cliente llama a Microsoft, Microsoft 365 iniciará la operación de recuperación, lo que implica descifrar el TIK con la clave de disponibilidad almacenada en el almacén secreto de Microsoft y volver a incorporar el inquilino con la TIK descifrada y un nuevo conjunto de claves de Azure Key Vault proporcionadas por el cliente.
  
A partir de hoy, la clave de cliente está involucrada en la cadena de cifrado y descifrado de los datos de archivos de SharePoint Online almacenados en el almacén de blobs de Azure, pero no en los elementos de lista o metadatos de SharePoint Online almacenados en la base de datos de SQL. Microsoft 365 no usa la clave de disponibilidad para los archivos de Exchange Online, Skype Empresarial, SharePoint Online, OneDrive para la Empresa y Teams que no sea el caso descrito anteriormente, iniciado por el cliente. El acceso humano a los datos de los clientes está protegido por la Caja de seguridad del cliente.

## <a name="availability-key-triggers"></a>Desencadenadores de clave de disponibilidad

Microsoft 365 desencadena la clave de disponibilidad solo en circunstancias específicas. Estas circunstancias difieren según el servicio.

### <a name="triggers-for-exchange-online-and-skype-for-business"></a>Desencadenadores para Exchange Online y Skype Empresarial
  
1. Microsoft 365 lee el DEP al que está asignado el buzón para determinar la ubicación de las dos claves de cliente en Azure Key Vault.

2. Microsoft 365 elige aleatoriamente una de las dos claves de cliente del DEP y envía una solicitud a Azure Key Vault para desenvolver la clave DEP con la clave de cliente.

3. Si se produce un error en la solicitud para desenvolver la clave DEP con la clave de cliente, Microsoft 365 envía una segunda solicitud a Azure Key Vault, esta vez instruyéndole que use la (segunda) clave de cliente alternativa.

4. Si se produce un error en la segunda solicitud para desenvolver la clave DEP con la clave de cliente, Microsoft 365 examina los resultados de ambas solicitudes.

    - Si el examen determina que las solicitudes no han podido devolver un ERROR del sistema:

       - Microsoft 365 desencadena la clave de disponibilidad para descifrar la clave DEP.

       - A continuación, Microsoft 365 usa la clave DEP para descifrar la clave de buzón y completar la solicitud del usuario. 

       - En este caso, Azure Key Vault no puede responder o es inaccesible debido a un ERROR transitorio.

    - Si el examen determina que las solicitudes no pudieron devolver ACCESO DENEGADO:

       - Esto significa que se ha realizado una acción deliberada, involuntaria o malintencionada para que las claves de cliente no estén disponibles (por ejemplo, durante el proceso de depuración de datos como parte de la salida del servicio).

       - En este caso, la clave de disponibilidad se usará solo para las acciones del sistema y no para las acciones del usuario, se producirá un error en la solicitud del usuario y el usuario recibirá un mensaje de error.

>[!IMPORTANT]
>El código de servicio de Microsoft 365 siempre tiene un token de inicio de sesión válido para la razón de los datos de los clientes con el fin de proporcionar servicios en la nube de valor agregado. Por lo tanto, hasta que no se elimine la clave de disponibilidad, puede usarse como reserva para acciones iniciadas por Exchange Online y Skype Empresarial, o internamente, como la creación de índices de búsqueda o el movimiento de buzones. Esto se aplica a las solicitudes ERRORS transitorias y ACCESS DENIED a Azure Key Vault.

### <a name="triggers-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Desencadenadores para archivos de SharePoint Online, OneDrive para la Empresa y Teams

Para los archivos de SharePoint Online, OneDrive para la Empresa y Teams, la clave de disponibilidad NUNCA se usa fuera de la capacidad de recuperación y los clientes deben indicar explícitamente a Microsoft que inicie el uso de la clave de disponibilidad durante un escenario de recuperación.

## <a name="audit-logs-and-the-availability-key"></a>Registros de auditoría y clave de disponibilidad

Los sistemas automatizados de Microsoft 365 procesan todos los datos a medida que fluyen por el sistema para proporcionar servicios en la nube, por ejemplo, antivirus, detección electrónica, prevención de pérdida de datos e indización de datos. Microsoft 365 no genera registros visibles para el cliente para esta actividad. Además, el personal de Microsoft no tiene acceso a los datos como parte de estas operaciones normales del sistema.

### <a name="exchange-online-and-skype-for-business-availability-key-logging"></a>Registro de claves de disponibilidad de Exchange Online y Skype Empresarial

Cuando Exchange Online y Skype Empresarial acceden a la clave de disponibilidad para proporcionar el servicio, Microsoft 365 publica registros visibles para el cliente accesibles desde el Centro de seguridad y cumplimiento. Cada vez que el servicio usa la clave de disponibilidad, se genera un registro de registro de auditoría para la operación de clave de disponibilidad. Un nuevo tipo de registro denominado "Cifrado de servicio de clave de cliente" con tipo de actividad "Reserva a clave de disponibilidad" permite a los administradores filtrar los resultados de la búsqueda del registro de auditoría unificado para ver los registros de clave de disponibilidad. [](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

Los registros incluyen atributos como la fecha, la hora, la actividad, el id. de la organización y el identificador de directiva de cifrado de datos. El registro está disponible como parte de los registros de auditoría unificados y es accesible desde la pestaña Búsqueda de registros de auditoría del Centro de & cumplimiento.

![Búsqueda de registros de auditoría para eventos de clave de disponibilidad](../media/customerkeyauditlogsearchavailabilitykeyloggingimage.png)

Los registros de claves de disponibilidad de Exchange Online [](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) y Skype Empresarial usan el esquema común actividad de administración de Office 365 con parámetros personalizados agregados: identificador de directiva, identificador de versión de clave de ámbito e identificador de solicitud.

![Parámetros personalizados de clave de disponibilidad](../media/customerkeyauditlogsearchavailabilitykeyloggingcustomparam.png)

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-availability-key-logging"></a>Registro de claves de disponibilidad de archivos de SharePoint Online, OneDrive para la Empresa y Teams

El registro de claves de disponibilidad aún no está disponible para estos servicios. Para los archivos de SharePoint Online, OneDrive para la Empresa y Teams, Microsoft solo activa la clave de disponibilidad, cuando se lo indique, con fines de recuperación. Como resultado, ya conoce todos los eventos en los que se usa la clave de disponibilidad para estos servicios.

## <a name="availability-key-in-the-customer-key-hierarchy"></a>Clave de disponibilidad en la jerarquía de claves de cliente
  
Microsoft 365 usa la clave de disponibilidad para ajustar el nivel de claves inferior en la jerarquía de claves establecida para el cifrado de la clave de cliente. Existen diferentes jerarquías clave entre servicios. Los algoritmos de clave también difieren entre las claves de disponibilidad y otras claves en la jerarquía de cada servicio aplicable. Los algoritmos de clave de disponibilidad usados por los diferentes servicios son los siguientes:

- Las claves de disponibilidad de Exchange Online y Skype Empresarial usan AES-256.

- Las claves de disponibilidad de archivos de SharePoint Online, OneDrive para la Empresa y Teams usan RSA-2048.

### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Cifrados usados para cifrar claves para Exchange Online y Skype Empresarial

![Cifrado de cifrado para la clave de cliente de Exchange Online](../media/customerkeyencryptionhierarchiesexchangeskype.png)

### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-and-onedrive-for-business"></a>Cifrados usados para cifrar claves para SharePoint Online y OneDrive para la Empresa

![Cifrado de cifrado para la clave de cliente de SharePoint Online](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Artículos relacionados

- [Cifrado de servicio con clave de cliente](customer-key-overview.md)

- [Configurar la clave de cliente](customer-key-set-up.md)

- [Administrar clave de cliente](customer-key-manage.md)

- [Rotar o alternar una Clave de cliente o una clave de disponibilidad](customer-key-availability-key-roll.md)
