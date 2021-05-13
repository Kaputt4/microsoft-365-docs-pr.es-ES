---
title: Obtener más información sobre la clave de disponibilidad de Clave de cliente
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Obtenga información sobre la clave de disponibilidad usada para recuperar las claves de cliente perdidas.
ms.openlocfilehash: 4f4dfdff0aa1c7ebe6dd1266c82c6fd290913a3e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345099"
---
# <a name="learn-about-the-availability-key-for-customer-key"></a>Obtener más información sobre la clave de disponibilidad de Clave de cliente

La clave de disponibilidad es una clave raíz generada y aprovisionada automáticamente al crear una directiva de cifrado de datos. Microsoft 365 almacena y protege la clave de disponibilidad. La clave de disponibilidad es funcionalmente como las dos claves raíz que proporciona para el cifrado de servicio con clave de cliente. La clave de disponibilidad ajusta las claves un nivel inferior en la jerarquía de claves. A diferencia de las claves que proporciona y administra en Azure Key Vault, no puede acceder directamente a la clave de disponibilidad. Microsoft 365 los servicios automatizados administran la clave de disponibilidad de forma programatica. Estos servicios inician operaciones automatizadas que nunca implican el acceso directo a la clave de disponibilidad.

El objetivo principal de la clave de disponibilidad es proporcionar capacidad de recuperación ante la pérdida inesperada de claves raíz que administra. La pérdida puede deberse a una mala administración o a una acción malintencionada. Si pierde el control de las claves raíz, póngase en contacto con el Soporte técnico de Microsoft y Microsoft le ayudará en el proceso de recuperación mediante la clave de disponibilidad. Usará la clave de disponibilidad para migrar a una nueva directiva de cifrado de datos con las nuevas claves raíz que aprovisione.

Storage y el control de la clave de disponibilidad son deliberadamente diferentes de las claves de Azure Key Vault por tres motivos:

- La clave de disponibilidad proporciona una capacidad de recuperación y "break-glass" si se pierde el control sobre ambas claves de Azure Key Vault.
- La separación de controles lógicos y ubicaciones de almacenamiento seguras proporciona defensa en profundidad y protege contra la pérdida de todas las claves y los datos de un solo ataque o punto de error.
- La clave de disponibilidad proporciona una funcionalidad de alta disponibilidad si Microsoft 365 servicios no pueden alcanzar las claves hospedadas en Azure Key Vault debido a errores transitorios. Esta regla solo se aplica al Exchange Online y Skype Empresarial de servicio. SharePoint Los archivos OneDrive para la Empresa, Teams y en línea nunca usan la clave de disponibilidad a menos que indique explícitamente a Microsoft que inicie el proceso de recuperación.

Compartir la responsabilidad de proteger los datos, usando una variedad de protecciones y procesos para la administración de claves, reduce en última instancia el riesgo de que todas las claves (y, por lo tanto, los datos) se pierdan o destruyan permanentemente. Microsoft le proporciona la autoridad única sobre la deshabilitación o destrucción de la clave de disponibilidad al salir del servicio. Por diseño, nadie en Microsoft tiene acceso a la clave de disponibilidad: solo es accesible mediante Microsoft 365 de servicio.

Consulta el [Centro de confianza de Microsoft](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data) para obtener más información sobre cómo protegemos las claves.
  
## <a name="availability-key-uses"></a>Usos de clave de disponibilidad

La clave de disponibilidad proporciona capacidad de recuperación para escenarios en los que un malhechor externo o un insider malintencionado roba el control del almacén de claves, o cuando una mala administración involuntaria da como resultado la pérdida de claves raíz. Esta funcionalidad de recuperación se aplica a todos los Microsoft 365 compatibles con la clave de cliente. Los servicios individuales usan la clave de disponibilidad de forma diferente. Microsoft 365 solo usa la clave de disponibilidad de las formas descritas a continuación.

### <a name="exchange-online-and-skype-for-business-uses"></a>Exchange Online y Skype Empresarial usos

Además de la funcionalidad de recuperación, Exchange Online y Skype Empresarial la clave de disponibilidad para garantizar la disponibilidad de datos durante problemas operativos transitorios o intermitentes relacionados con el acceso del servicio a las claves raíz. Cuando el servicio no puede llegar a ninguna de las claves de cliente en Azure Key Vault debido a errores transitorios, el servicio usa automáticamente la clave de disponibilidad. El servicio NUNCA va directamente a la clave de disponibilidad.

Los sistemas automatizados de Exchange Online y Skype Empresarial pueden usar la clave de disponibilidad durante errores transitorios para admitir servicios back-end automatizados como antivirus, detección electrónica, prevención de pérdida de datos, movimientos de buzones e indización de datos.

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-uses"></a>SharePoint Los archivos OneDrive para la Empresa, Teams y en línea

Para los archivos SharePoint Online, OneDrive para la Empresa y Teams, la clave de disponibilidad NUNCA se usa fuera de la capacidad de recuperación y los clientes deben indicar explícitamente a Microsoft que inicie el uso de la clave de disponibilidad durante un escenario de recuperación. Las operaciones de servicio automatizadas solo dependen de las claves de cliente en el almacén de claves de Azure. Para obtener información detallada sobre cómo funciona la jerarquía de claves para estos servicios, vea [How SharePoint Online, OneDrive para la Empresa y Teams files use the availability key](#how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key).

## <a name="availability-key-security"></a>Seguridad clave de disponibilidad

Microsoft comparte la responsabilidad de la protección de datos con usted al crear instancias de la clave de disponibilidad y tomar medidas exhaustivas para protegerla. Microsoft no expone el control directo de la clave de disponibilidad a los clientes. Por ejemplo, solo puede girar (girar) las claves que posee en Azure Key Vault. Para obtener más información, vea [Roll or rotate a customer key or an availability key](customer-key-availability-key-roll.md).

### <a name="availability-key-secret-stores"></a>Almacenes secretos clave de disponibilidad

Microsoft protege las claves de disponibilidad en almacenes secretos internos controlados por el acceso, como Azure Key Vault orientado al cliente. Implementamos controles de acceso para impedir que los administradores de Microsoft accedan directamente a los secretos contenidos en. Las operaciones del Almacén secreto, incluida la rotación y eliminación de claves, se producen a través de comandos automatizados que nunca implican acceso directo a la clave de disponibilidad. Las operaciones de administración de almacenes secretos están limitadas a ingenieros específicos y requieren una escalación de privilegios a través de una herramienta interna, Lockbox. La escalación de privilegios requiere la aprobación y justificación del administrador antes de concederse. Lockbox garantiza que el acceso esté limitado por el tiempo con la revocación automática de acceso al expirar el tiempo o al cerrar sesión el ingeniero.

**Exchange Online y Skype Empresarial** claves de disponibilidad se almacenan en un Exchange Online secreto de Active Directory. Las claves de disponibilidad se almacenan de forma segura dentro de contenedores específicos del espacio empresarial dentro del controlador de dominio de Active Directory. Esta ubicación de almacenamiento seguro es independiente y aislada del almacén secreto de archivos SharePoint online, OneDrive para la Empresa y Teams archivos.

**SharePoint Online, OneDrive para la Empresa y** Teams claves de disponibilidad de archivos se almacenan en un almacén secreto interno administrado por el equipo de servicio. Este servicio de almacenamiento secreto protegido tiene servidores front-end con extremos de aplicación y un SQL Database como back-end. Las claves de disponibilidad se almacenan en el SQL Database y se encapsulan (cifradas) mediante claves de cifrado de almacén secreto que usan una combinación de AES-256 y HMAC para cifrar la clave de disponibilidad en reposo. Las claves de cifrado del almacén secreto se almacenan en un componente aislado lógicamente del mismo SQL Database y se cifran con claves RSA-2048 contenidas en certificados administrados por la entidad de certificación (CA) de Microsoft. Estos certificados se almacenan en los servidores front-end del almacén secreto que realizan operaciones en la base de datos.

### <a name="defense-in-depth"></a>Defensa en profundidad

Microsoft emplea una estrategia de defensa en profundidad para evitar que actores malintencionados impacten en la confidencialidad, integridad o disponibilidad de los datos de clientes almacenados en Microsoft Cloud. Se implementan controles preventivos y de detective específicos para proteger el almacén secreto y la clave de disponibilidad como parte de la estrategia de seguridad general.

Microsoft 365 se ha creado para evitar el uso incorrecto de la clave de disponibilidad. La capa de aplicación es el único método a través del cual las claves, incluida la clave de disponibilidad, se pueden usar para cifrar y descifrar datos. Solo Microsoft 365 de servicio tiene la capacidad de interpretar y atravesar la jerarquía de claves para las actividades de cifrado y descifrado. Existe aislamiento lógico entre las ubicaciones de almacenamiento de claves de cliente, claves de disponibilidad, otras claves jerárquicas y datos de cliente. Este aislamiento mitiga el riesgo de exposición a datos en caso de que se vea comprometida una o más ubicaciones. Cada capa de la jerarquía ha integrado capacidades de detección de intrusiones 24 x 7 para proteger los datos y secretos almacenados.

Los controles de acceso se implementan para evitar el acceso no autorizado a sistemas internos, incluidos los almacenes secretos de clave de disponibilidad. Los ingenieros de Microsoft no tienen acceso directo a los almacenes secretos de clave de disponibilidad. Para obtener más información sobre los controles de acceso, revise [Administrative Access Controls en Microsoft 365](/Office365/securitycompliance/office-365-administrative-access-controls-overview).

Los controles técnicos impiden que el personal de Microsoft pueda iniciar sesión en cuentas de servicio con privilegios elevados, que de lo contrario podrían usar los atacantes para suplantar servicios Microsoft. Por ejemplo, estos controles impiden el inicio de sesión interactivo.

Los controles de seguimiento y registro de seguridad son otra protección de defensa en profundidad implementada que mitiga los riesgos para servicios Microsoft y los datos. Los equipos de servicio de Microsoft han implementado soluciones de supervisión activas que generan alertas y registros de auditoría. Todos los equipos de servicio cargan sus registros en un repositorio central donde se agregan y procesan los registros. Las herramientas internas examinan automáticamente los registros para confirmar que los servicios funcionan en un estado óptimo, resistente y seguro. La actividad inusual se marca para su revisión posterior.

Cualquier evento de registro que indique una posible infracción de la directiva de seguridad de Microsoft se llama inmediatamente a la atención de los equipos de seguridad de Microsoft. Microsoft 365 seguridad ha configurado alertas para detectar intentos de acceso a almacenes secretos de claves de disponibilidad. Las alertas también se generan si el personal de Microsoft intenta iniciar sesión interactiva en cuentas de servicio, lo que está prohibido y protegido por los controles de acceso. Microsoft 365 seguridad también detecta y alerta sobre las desviaciones del Microsoft 365 de operaciones de línea base normales. Los malhechores que intenten usar Microsoft 365 servicios activarían alertas que provocarían el desalojo del infractor del entorno en la nube de Microsoft.

## <a name="use-the-availability-key-to-recover-from-key-loss"></a>Usar la clave de disponibilidad para recuperarse de la pérdida de clave

Si pierde el control de las claves de cliente, la clave de disponibilidad le ofrece la capacidad de recuperar y volver a cifrar los datos.

### <a name="recovery-procedure-for-exchange-online-and-skype-for-business"></a>Procedimiento de recuperación Exchange Online y Skype Empresarial

Si pierde el control de las claves de cliente, la clave de disponibilidad le ofrece la capacidad de recuperar los datos y volver a poner en línea los recursos Microsoft 365 afectados. La clave de disponibilidad sigue protegiendo los datos mientras se recupera. En un nivel alto, para recuperarse completamente de la pérdida de claves, deberá crear un nuevo DEP y mover los recursos afectados a la nueva directiva.

Para cifrar los datos con nuevas claves de cliente, cree nuevas claves en Azure Key Vault, cree un nuevo DEP con las nuevas claves de cliente y, a continuación, asigne el nuevo DEP a los buzones cifrados actualmente con el DEP anterior para el que las claves se perdieron o se han visto comprometidas.

Este proceso de volver a cifrar puede tardar hasta 72 horas. Esta es la duración estándar al cambiar un DEP.
  
### <a name="recovery-procedure-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Procedimiento de recuperación para SharePoint en línea, OneDrive para la Empresa y Teams archivos

Para SharePoint online, OneDrive para la Empresa y Teams, la clave de disponibilidad NUNCA se usa fuera de la funcionalidad de recuperación. Debe indicar explícitamente a Microsoft que inicie el uso de la clave de disponibilidad durante un escenario de recuperación. Para iniciar el proceso de recuperación, póngase en contacto con Microsoft para activar la clave de disponibilidad. Una vez activada, la clave de disponibilidad se usa automáticamente para descifrar los datos, lo que permite cifrar los datos con un DEP recién creado asociado a nuevas claves de cliente.  

Esta operación es proporcional al número de sitios de la organización. Una vez que llame a Microsoft para que use la clave de disponibilidad, debe estar totalmente en línea en unas cuatro horas.

## <a name="how-exchange-online-and-skype-for-business-use-the-availability-key"></a>Cómo Exchange Online y Skype Empresarial la clave de disponibilidad

Al crear un DEP con clave de cliente, Microsoft 365 genera una clave de directiva de cifrado de datos (clave DEP) asociada a ese DEP. El servicio cifra la clave DEP tres veces: una con cada una de las claves de cliente y otra con la clave de disponibilidad. Solo se almacenan las versiones cifradas de la clave DEP y solo se puede descifrar una clave DEP con las claves de cliente o la clave de disponibilidad. A continuación, se usa la clave DEP para cifrar las claves de buzón, que cifran los buzones individuales.
  
Microsoft 365 sigue este proceso para descifrar y proporcionar datos cuando los clientes usan el servicio:
  
1. Descifrar la clave DEP con la clave de cliente.

2. Use la clave DEP descifrada para descifrar una clave de buzón.

3. Use la clave de buzón de correo descifrada para descifrar el propio buzón, lo que le permite tener acceso a los datos del buzón.

## <a name="how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key"></a>Cómo SharePoint online, OneDrive para la Empresa y Teams usan la clave de disponibilidad

La SharePoint online y la OneDrive para la Empresa e implementación de la clave de cliente y la clave de disponibilidad son diferentes de Exchange Online y Skype Empresarial.
  
Cuando una organización se mueve a claves administradas por el cliente, Microsoft 365 crea una clave intermedia (TIK) específica de la organización. Microsoft 365 cifra la TIK dos veces, una con cada una de las claves de cliente, y almacena las dos versiones cifradas de la TIK. Solo se almacenan las versiones cifradas de la TIK y solo se puede descifrar una TIK con las claves de cliente. A continuación, la TIK se usa para cifrar las claves de sitio, que luego se usan para cifrar claves de blob (también denominadas claves de fragmento de archivo). Según el tamaño del archivo, el servicio puede dividir un archivo en varios fragmentos de archivo cada uno con una clave única. Los blobs (fragmentos de archivo) se cifran con las claves de blob y se almacenan en el Microsoft Azure de almacenamiento de blobs.
  
Microsoft 365 sigue este proceso para descifrar y proporcionar archivos de cliente cuando los clientes usan el servicio:

1. Descifra el TIK con la clave de cliente.

2. Use la TIK descifrada para descifrar una clave de sitio.

3. Use la clave de sitio descifrada para descifrar una clave de blob.

4. Use la clave de blob descifrada para descifrar el blob.

Microsoft 365 descifra una TIK mediante la emisión de dos solicitudes de descifrado a Azure Key Vault con un ligero desplazamiento. El primero en finalizar presenta el resultado, cancelando la otra solicitud.
  
En caso de perder acceso a las claves de cliente, Microsoft 365 también cifra la TIK con una clave de disponibilidad y la almacena junto con los TIK cifrados con cada clave de cliente. La TIK cifrada con la clave de disponibilidad solo se usa cuando el cliente llama a Microsoft para obtener la ruta de recuperación cuando ha perdido el acceso a sus claves, de forma malintencionada o accidentalmente.
  
Por motivos de disponibilidad y escala, los TIK descifrados se almacenan en caché en una memoria caché de tiempo limitado. Dos horas antes de que una memoria caché de TIK expire, Microsoft 365 intentar descifrar cada TIK. Descifrar los TIK amplía la duración de la memoria caché. Si se produce un error de descifrado de TIK durante una cantidad significativa de tiempo, Microsoft 365 genera una alerta para notificar a los ingenieros antes de la expiración de la memoria caché. Solo si el cliente llama Microsoft 365 Microsoft iniciará la operación de recuperación, lo que implica descifrar la TIK con la clave de disponibilidad almacenada en el almacén secreto de Microsoft y volver a incorporar el espacio empresarial con la TIK descifrada y un nuevo conjunto de claves de Azure Key Vault suministradas por el cliente.
  
A partir de hoy, la clave de cliente está implicada en la cadena de cifrado y descifrado de datos de archivos de SharePoint Online almacenados en el almacén de blobs de Azure, pero no en los elementos de lista o metadatos de SharePoint Online almacenados en el SQL Database. Microsoft 365 no usa la clave de disponibilidad para los archivos Exchange Online, Skype Empresarial, SharePoint Online, OneDrive para la Empresa y Teams que no sea el caso descrito anteriormente, iniciado por el cliente. El acceso humano a los datos del cliente está protegido por la caja de seguridad del cliente.

## <a name="availability-key-triggers"></a>Desencadenadores de clave de disponibilidad

Microsoft 365 activa la clave de disponibilidad solo en circunstancias específicas. Estas circunstancias difieren según el servicio.

### <a name="triggers-for-exchange-online-and-skype-for-business"></a>Desencadenadores para Exchange Online y Skype Empresarial
  
1. Microsoft 365 lee el DEP al que está asignado el buzón para determinar la ubicación de las dos claves de cliente en Azure Key Vault.

2. Microsoft 365 elige aleatoriamente una de las dos claves de cliente del DEP y envía una solicitud a Azure Key Vault para desenvolver la clave DEP con la clave de cliente.

3. Si se produce un error en la solicitud para desenvolver la clave DEP mediante la clave de cliente, Microsoft 365 envía una segunda solicitud a Azure Key Vault, esta vez instruyéndole que use la (segunda) clave de cliente alternativa.

4. Si se produce un error en la segunda solicitud para desenvolver la clave DEP mediante la clave de cliente, Microsoft 365 los resultados de ambas solicitudes.

    - Si el examen determina que las solicitudes no pudieron devolver un error del sistema:

       - Microsoft 365 activa la clave de disponibilidad para descifrar la clave DEP.

       - Microsoft 365 la clave DEP para descifrar la clave de buzón y completar la solicitud de usuario. 

       - En este caso, Azure Key Vault no puede responder o es inaccesible debido a un ERROR transitorio.

    - Si el examen determina que las solicitudes no pudieron devolver ACCESS DENIED:

       - Esto significa que se han realizado acciones deliberadas, involuntarias o malintencionadas para que las claves de cliente no estén disponibles (por ejemplo, durante el proceso de purga de datos como parte de la salida del servicio).

       - En este caso, la clave de disponibilidad se usará solo para acciones del sistema y no para acciones de usuario, la solicitud de usuario falla y el usuario recibe un mensaje de error.

>[!IMPORTANT]
>Microsoft 365 código de servicio siempre tiene un token de inicio de sesión válido para razonar sobre los datos del cliente para proporcionar servicios en la nube de adición de valor. Por lo tanto, hasta que la clave de disponibilidad se haya eliminado, se puede usar como reserva para acciones iniciadas por, o internas a, Exchange Online y Skype Empresarial, como la creación de índices de búsqueda o el movimiento de buzones. Esto se aplica tanto a errores transitorios como a solicitudes DENEGADAS de ACCESO a Azure Key Vault.

### <a name="triggers-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Desencadenadores para SharePoint online, OneDrive para la Empresa y Teams archivos

Para los archivos SharePoint Online, OneDrive para la Empresa y Teams, la clave de disponibilidad NUNCA se usa fuera de la capacidad de recuperación y los clientes deben indicar explícitamente a Microsoft que inicie el uso de la clave de disponibilidad durante un escenario de recuperación.

## <a name="audit-logs-and-the-availability-key"></a>Registros de auditoría y la clave de disponibilidad

Los sistemas automatizados de Microsoft 365 procesan todos los datos a medida que fluyen por el sistema para proporcionar servicios en la nube, por ejemplo, antivirus, detección electrónica, prevención de pérdida de datos e indización de datos. Microsoft 365 genera registros visibles para el cliente para esta actividad. Además, el personal de Microsoft no tiene acceso a los datos como parte de estas operaciones normales del sistema.

### <a name="exchange-online-and-skype-for-business-availability-key-logging"></a>Exchange Online y Skype Empresarial de claves de disponibilidad

Cuando Exchange Online y Skype Empresarial acceso a la clave de disponibilidad para proporcionar el servicio, Microsoft 365 publica registros visibles para el cliente accesibles desde el Centro de seguridad y cumplimiento. Cada vez que el servicio usa la clave de disponibilidad, se genera un registro de registro de auditoría para la operación de clave de disponibilidad. Un nuevo tipo de registro denominado "Cifrado de servicio de clave de cliente" con el tipo de actividad "Reserva a la clave de disponibilidad" permite a los administradores filtrar los resultados de búsqueda del registro de auditoría unificado para ver los registros de claves de disponibilidad. [](./search-the-audit-log-in-security-and-compliance.md)

Los registros incluyen atributos como fecha, hora, actividad, id. de organización e id. de directiva de cifrado de datos. El registro está disponible como parte de registros de auditoría unificados y es accesible desde la pestaña Búsqueda de registros de auditoría del Centro de & cumplimiento.

![Búsqueda de registros de auditoría para eventos clave de disponibilidad](../media/customerkeyauditlogsearchavailabilitykeyloggingimage.png)

Exchange Online y Skype Empresarial clave de disponibilidad usan el esquema común [](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) de actividad de administración de Office 365 con parámetros personalizados agregados: Id. de directiva, Identificador de versión de clave de ámbito e Identificador de solicitud.

![Parámetros personalizados de clave de disponibilidad](../media/customerkeyauditlogsearchavailabilitykeyloggingcustomparam.png)

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-availability-key-logging"></a>SharePoint Registro de claves OneDrive para la Empresa, OneDrive para la Empresa y Teams de disponibilidad de archivos

El registro de claves de disponibilidad aún no está disponible para estos servicios. Para SharePoint Online, OneDrive para la Empresa y Teams, Microsoft solo activa la clave de disponibilidad cuando se le indique, con fines de recuperación. Como resultado, ya conoce todos los eventos en los que se usa la clave de disponibilidad para estos servicios.

## <a name="availability-key-in-the-customer-key-hierarchy"></a>Clave de disponibilidad en la jerarquía clave de cliente
  
Microsoft 365 la clave de disponibilidad para ajustar el nivel de claves inferior en la jerarquía de claves establecida para el cifrado de servicio de clave de cliente. Existen distintas jerarquías clave entre servicios. Los algoritmos de clave también difieren entre las claves de disponibilidad y otras claves en la jerarquía de cada servicio aplicable. Los algoritmos de clave de disponibilidad usados por los diferentes servicios son los siguientes:

- Las Exchange Online y Skype Empresarial de disponibilidad usan AES-256.

- Las SharePoint Online, OneDrive para la Empresa y Teams claves de disponibilidad de archivos usan RSA-2048.

### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Cifrados usados para cifrar claves para Exchange Online y Skype Empresarial

![Cifrado de cifrado para Exchange Online clave de cliente](../media/customerkeyencryptionhierarchiesexchangeskype.png)

### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-and-onedrive-for-business"></a>Cifrados usados para cifrar claves para SharePoint Online y OneDrive para la Empresa

![Cifrado de cifrado para SharePoint clave de cliente en línea](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Artículos relacionados

- [Cifrado de servicio con clave de cliente](customer-key-overview.md)

- [Configurar clave de cliente](customer-key-set-up.md)

- [Administrar clave de cliente](customer-key-manage.md)

- [Rotar o alternar una Clave de cliente o una clave de disponibilidad](customer-key-availability-key-roll.md)