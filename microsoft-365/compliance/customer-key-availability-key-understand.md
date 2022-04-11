---
title: Obtener más información sobre la clave de disponibilidad de Clave de cliente
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
description: Obtenga información sobre la clave de disponibilidad que se usa para recuperar las claves de cliente perdidas.
ms.openlocfilehash: 1fd80d23980957402ae7d5e79a91e57d28df38f9
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2022
ms.locfileid: "64761845"
---
# <a name="learn-about-the-availability-key-for-customer-key"></a>Obtener más información sobre la clave de disponibilidad de Clave de cliente

La clave de disponibilidad es una clave raíz generada y aprovisionada automáticamente al crear una directiva de cifrado de datos. Microsoft 365 almacena y protege la clave de disponibilidad. La clave de disponibilidad es funcionalmente similar a las dos claves raíz que proporciona para el cifrado de servicio con clave de cliente. La clave de disponibilidad ajusta las claves un nivel inferior en la jerarquía de claves. A diferencia de las claves que proporciona y administra en Azure Key Vault, no puede acceder directamente a la clave de disponibilidad. Microsoft 365 servicios automatizados administran la clave de disponibilidad mediante programación. Estos servicios inician operaciones automatizadas que nunca implican acceso directo a la clave de disponibilidad.

El propósito principal de la clave de disponibilidad es proporcionar capacidad de recuperación a partir de la pérdida inesperada de claves raíz que administra. La pérdida podría ser el resultado de una mala administración o una acción malintencionada. Si pierde el control de las claves raíz, póngase en contacto con Soporte técnico de Microsoft y Microsoft le ayudará en el proceso de recuperación mediante la clave de disponibilidad. Usará la clave de disponibilidad para migrar a una nueva directiva de cifrado de datos con las nuevas claves raíz que aprovisione.

Storage y el control de la clave de disponibilidad son deliberadamente diferentes de las claves de Azure Key Vault por tres motivos:

- La clave de disponibilidad proporciona una funcionalidad "break-glass" de recuperación si se pierde el control sobre ambas claves de Azure Key Vault.
- La separación de controles lógicos y ubicaciones de almacenamiento seguras proporciona defensa en profundidad y protege contra la pérdida de todas las claves y los datos de un único ataque o punto de error.
- La clave de disponibilidad proporciona una funcionalidad de alta disponibilidad si Microsoft 365 servicios no pueden alcanzar las claves hospedadas en Azure Key Vault debido a errores transitorios. Esta regla solo se aplica a Exchange Online y Skype Empresarial cifrado de servicio. SharePoint archivos en línea, OneDrive para la Empresa y Teams nunca usan la clave de disponibilidad a menos que indique explícitamente a Microsoft que inicie el proceso de recuperación.

Compartir la responsabilidad de proteger los datos, utilizando diversas protecciones y procesos para la administración de claves, reduce en última instancia el riesgo de que todas las claves (y, por lo tanto, los datos) se pierdan o destruyan permanentemente. Microsoft le proporciona la única autoridad sobre la deshabilitación o destrucción de la clave de disponibilidad al salir del servicio. Por diseño, nadie de Microsoft tiene acceso a la clave de disponibilidad: solo es accesible mediante Microsoft 365 código de servicio.

Consulte el [Centro de confianza de Microsoft](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data) para obtener más información sobre cómo se protegen las claves.
  
## <a name="availability-key-uses"></a>Uso de la clave de disponibilidad

La clave de disponibilidad proporciona capacidad de recuperación para escenarios en los que un malfactor externo o un insider malintencionado roba el control del almacén de claves, o cuando una mala administración accidental produce la pérdida de claves raíz. Esta funcionalidad de recuperación se aplica a todos los servicios de Microsoft 365 compatibles con la clave de cliente. Los servicios individuales usan la clave de disponibilidad de forma diferente. Microsoft 365 solo usa la clave de disponibilidad de las formas que se describen a continuación.

### <a name="exchange-online-and-skype-for-business-uses"></a>usos de Exchange Online y Skype Empresarial

Además de la funcionalidad de recuperación, Exchange Online y Skype Empresarial usar la clave de disponibilidad para garantizar la disponibilidad de los datos durante problemas operativos transitorios o intermitentes relacionados con el servicio que accede a las claves raíz. Cuando el servicio no puede acceder a ninguna de las claves de cliente de Azure Key Vault debido a errores transitorios, el servicio usa automáticamente la clave de disponibilidad. El servicio NUNCA va directamente a la clave de disponibilidad.

Los sistemas automatizados de Exchange Online y Skype Empresarial pueden usar la clave de disponibilidad durante errores transitorios para admitir servicios back-end automatizados, como antivirus, detección electrónica, prevención de pérdida de datos, movimientos de buzones e indexación de datos.

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-uses"></a>SharePoint los archivos en línea, OneDrive para la Empresa y Teams usa

Para SharePoint archivos en línea, OneDrive para la Empresa y Teams, la clave de disponibilidad NUNCA se usa fuera de la funcionalidad de recuperación y los clientes deben indicar explícitamente a Microsoft que inicie el uso de la clave de disponibilidad durante un escenario de recuperación. Las operaciones de servicio automatizadas solo se basan en las claves de cliente en Azure Key Vault. Para obtener información detallada sobre cómo funciona la jerarquía de claves para estos servicios, vea [How SharePoint Online, OneDrive para la Empresa y Teams files use la clave de disponibilidad](#how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key).

## <a name="availability-key-security"></a>Seguridad de clave de disponibilidad

Microsoft comparte la responsabilidad de la protección de datos con usted mediante la creación de instancias de la clave de disponibilidad y la adopción de amplias medidas para protegerla. Microsoft no expone el control directo de la clave de disponibilidad a los clientes. Por ejemplo, solo puede revertir (girar) las claves que posee en Azure Key Vault. Para obtener más información, consulte [Roll or rotate a customer key or an availability key (Roll or rotate a customer key or an availability key](customer-key-availability-key-roll.md)).

### <a name="availability-key-secret-stores"></a>Almacenes de secretos de clave de disponibilidad

Microsoft protege las claves de disponibilidad en almacenes de secretos internos controlados por acceso, como la Key Vault de Azure orientada al cliente. Implementamos controles de acceso para impedir que los administradores de Microsoft accedan directamente a los secretos contenidos en. Las operaciones del Almacén de secretos, incluida la rotación y eliminación de claves, se producen a través de comandos automatizados que nunca implican acceso directo a la clave de disponibilidad. Las operaciones de administración de almacenes secretos se limitan a ingenieros específicos y requieren escalación de privilegios a través de una herramienta interna, Caja de seguridad. La escalación de privilegios requiere la aprobación y la justificación del administrador antes de que se le conceda. La caja de seguridad garantiza que el acceso esté limitado por el tiempo con revocación automática de acceso tras la expiración del tiempo o que el ingeniero cierre la sesión.

las claves de disponibilidad **Exchange Online y Skype Empresarial** se almacenan en un almacén secreto de Active Directory Exchange Online. Las claves de disponibilidad se almacenan de forma segura dentro de contenedores específicos del inquilino dentro del controlador de Dominio de Active Directory. Esta ubicación de almacenamiento seguro es independiente y aislada del almacén secreto de archivos SharePoint Online, OneDrive para la Empresa y Teams.

**SharePoint claves de disponibilidad de archivos en línea, OneDrive para la Empresa y Teams** se almacenan en un almacén secreto interno administrado por el equipo de servicio. Este servicio de almacenamiento de secretos protegido tiene servidores front-end con puntos de conexión de aplicación y un SQL Database como back-end. Las claves de disponibilidad se almacenan en el SQL Database y se encapsulan (cifran) mediante claves de cifrado del almacén de secretos que usan una combinación de AES-256 y HMAC para cifrar la clave de disponibilidad en reposo. Las claves de cifrado del almacén de secretos se almacenan en un componente aislado lógicamente de la misma SQL Database y se cifran aún más con claves RSA-2048 contenidas en certificados administrados por la entidad de certificación (CA) de Microsoft. Estos certificados se almacenan en los servidores front-end del almacén secreto que realizan operaciones en la base de datos.

### <a name="defense-in-depth"></a>Defensa en profundidad

Microsoft emplea una estrategia de defensa en profundidad para evitar que actores malintencionados afecten a la confidencialidad, integridad o disponibilidad de los datos de los clientes almacenados en la nube de Microsoft. Se implementan controles preventivos y de detectives específicos para proteger el almacén secreto y la clave de disponibilidad como parte de la estrategia de seguridad global.

Microsoft 365 se ha creado para evitar el uso indebido de la clave de disponibilidad. La capa de aplicación es el único método a través del cual se pueden usar claves, incluida la clave de disponibilidad, para cifrar y descifrar datos. Solo Microsoft 365 código de servicio tiene la capacidad de interpretar y recorrer la jerarquía de claves para las actividades de cifrado y descifrado. El aislamiento lógico existe entre las ubicaciones de almacenamiento de claves de cliente, claves de disponibilidad, otras claves jerárquicas y datos de cliente. Este aislamiento mitiga el riesgo de exposición de datos en caso de que una o varias ubicaciones estén en peligro. Cada capa de la jerarquía ha creado funcionalidades de detección de intrusiones 24x7 para proteger los datos y los secretos almacenados.

Los controles de acceso se implementan para evitar el acceso no autorizado a los sistemas internos, incluidos los almacenes de secretos de clave de disponibilidad. Los ingenieros de Microsoft no tienen acceso directo a los almacenes de secretos de clave de disponibilidad. Para obtener más detalles sobre los controles de acceso, revise [Controles de acceso administrativo en Microsoft 365](/compliance/assurance/assurance-administrative-access-controls-overview).

Los controles técnicos impiden que el personal de Microsoft inicie sesión en cuentas de servicio con privilegios elevados, que de lo contrario podrían usar los atacantes para suplantar servicios Microsoft. Por ejemplo, estos controles impiden el inicio de sesión interactivo.

El registro de seguridad y los controles de supervisión son otra medida de seguridad en profundidad implementada que mitiga el riesgo para servicios Microsoft y los datos. Los equipos de servicio de Microsoft han implementado soluciones de supervisión activas que generan alertas y registros de auditoría. Todos los equipos de servicio cargan sus registros en un repositorio central donde los registros se agregan y procesan. Las herramientas internas examinan automáticamente los registros para confirmar que los servicios funcionan en un estado óptimo, resistente y seguro. La actividad inusual se marca para una revisión adicional.

Cualquier evento de registro que indique una posible infracción de la directiva de seguridad de Microsoft se llama inmediatamente a la atención de los equipos de seguridad de Microsoft. Microsoft 365 seguridad ha configurado alertas para detectar intentos de acceso a almacenes de secretos de clave de disponibilidad. También se generan alertas si el personal de Microsoft intenta iniciar sesión interactivo en las cuentas de servicio, lo que está prohibido y protegido por los controles de acceso. Microsoft 365 seguridad también detecta y alerta sobre las desviaciones del servicio de Microsoft 365 de las operaciones normales de línea base. Los malhechores que intentan usar mal Microsoft 365 servicios desencadenarían alertas que provocarían el desalojo del delincuente del entorno de nube de Microsoft.

## <a name="use-the-availability-key-to-recover-from-key-loss"></a>Uso de la clave de disponibilidad para recuperarse de la pérdida de claves

Si pierde el control de las claves de cliente, la clave de disponibilidad le proporciona la capacidad de recuperar y volver a cifrar los datos.

### <a name="recovery-procedure-for-exchange-online-and-skype-for-business"></a>Procedimiento de recuperación para Exchange Online y Skype Empresarial

Si pierde el control de las claves de cliente, la clave de disponibilidad le ofrece la capacidad de recuperar los datos y poner los recursos de Microsoft 365 afectados de nuevo en línea. La clave de disponibilidad sigue protegiendo los datos mientras se recupera. En un nivel alto, para recuperarse completamente de la pérdida de claves, deberá crear un nuevo DEP y mover los recursos afectados a la nueva directiva.

Para cifrar los datos con nuevas claves de cliente, cree nuevas claves en Azure Key Vault, cree un nuevo DEP con las nuevas claves de cliente y, a continuación, asigne el nuevo DEP a los buzones cifrados actualmente con el DEP anterior para el que las claves se perdieron o se vieron comprometidas.

Este proceso de re-cifrado puede tardar hasta 72 horas. Esta es la duración estándar al cambiar un DEP.
  
### <a name="recovery-procedure-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Procedimiento de recuperación para SharePoint archivos en línea, OneDrive para la Empresa y Teams

Para SharePoint archivos en línea, OneDrive para la Empresa y Teams, la clave de disponibilidad nunca se usa fuera de la funcionalidad de recuperación. Debe indicar explícitamente a Microsoft que inicie el uso de la clave de disponibilidad durante un escenario de recuperación. Para iniciar el proceso de recuperación, póngase en contacto con Microsoft para activar la clave de disponibilidad. Una vez activada, la clave de disponibilidad se usa automáticamente para descifrar los datos, lo que le permite cifrar los datos con un DEP recién creado asociado a las nuevas claves de cliente.  

Esta operación es proporcional al número de sitios de la organización. Una vez que llame a Microsoft para usar la clave de disponibilidad, debe estar totalmente en línea en un plazo de aproximadamente cuatro horas.

## <a name="how-exchange-online-and-skype-for-business-use-the-availability-key"></a>Cómo Exchange Online y Skype Empresarial usar la clave de disponibilidad

Al crear un DEP con clave de cliente, Microsoft 365 genera una clave de directiva de cifrado de datos (clave DEP) asociada a ese DEP. El servicio cifra la clave DEP tres veces: una con cada una de las claves de cliente y una con la clave de disponibilidad. Solo se almacenan las versiones cifradas de la clave DEP y una clave DEP solo se puede descifrar con las claves de cliente o la clave de disponibilidad. A continuación, la clave DEP se usa para cifrar las claves de buzón, que cifran buzones individuales.
  
Microsoft 365 sigue este proceso para descifrar y proporcionar datos cuando los clientes usan el servicio:
  
1. Descifra la clave DEP mediante la clave de cliente.

2. Use la clave DEP descifrada para descifrar una clave de buzón.

3. Use la clave de buzón de correo descifrada para descifrar el buzón en sí, lo que le permite acceder a los datos del buzón.

## <a name="how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key"></a>Cómo SharePoint archivos en línea, OneDrive para la Empresa y Teams usan la clave de disponibilidad

La arquitectura y la implementación de SharePoint Online y OneDrive para la Empresa para la clave de cliente y la clave de disponibilidad son diferentes de Exchange Online y Skype Empresarial.
  
Cuando una organización pasa a claves administradas por el cliente, Microsoft 365 crea una clave intermedia específica de la organización (TIK). Microsoft 365 cifra el TIK dos veces, una vez con cada una de las claves de cliente, y almacena las dos versiones cifradas del TIK. Solo se almacenan las versiones cifradas de TIK y solo se puede descifrar una TIK con las claves de cliente. A continuación, la TIK se usa para cifrar las claves de sitio, que luego se usan para cifrar las claves de blob (también denominadas claves de fragmento de archivo). En función del tamaño del archivo, el servicio puede dividir un archivo en varios fragmentos de archivo cada uno con una clave única. Los blobs (fragmentos de archivo) se cifran con las claves de blob y se almacenan en el servicio Microsoft Azure Blob Storage.
  
Microsoft 365 sigue este proceso para descifrar y proporcionar archivos de cliente cuando los clientes usan el servicio:

1. Descifra el TIK mediante la clave de cliente.

2. Use la TIK descifrada para descifrar una clave de sitio.

3. Use la clave de sitio descifrada para descifrar una clave de blob.

4. Use la clave de blob descifrada para descifrar el blob.

Microsoft 365 descifra una TIK mediante la emisión de dos solicitudes de descifrado a Azure Key Vault con un ligero desplazamiento. El primero en finalizar proporciona el resultado, cancelando la otra solicitud.
  
En caso de que pierda el acceso a las claves de cliente, Microsoft 365 también cifra la TIK con una clave de disponibilidad y la almacena junto con los TIK cifrados con cada clave de cliente. La TIK cifrada con la clave de disponibilidad solo se usa cuando el cliente llama a Microsoft para dar de alta la ruta de recuperación cuando ha perdido el acceso a sus claves, de forma malintencionada o accidental.
  
Por motivos de disponibilidad y escalado, los TIK descifrados se almacenan en caché en una caché de memoria con un tiempo limitado. Dos horas antes de que una caché de TIK expire, Microsoft 365 intenta descifrar cada TIK. Descifrar los TIK amplía la duración de la memoria caché. Si se produce un error en el descifrado de TIK durante un período de tiempo significativo, Microsoft 365 genera una alerta para notificar a la ingeniería antes de la expiración de la memoria caché. Solo si el cliente llama a Microsoft Microsoft 365 iniciará la operación de recuperación, lo que implica descifrar la TIK con la clave de disponibilidad almacenada en el almacén secreto de Microsoft e incorporar el inquilino de nuevo mediante la TIK descifrada y un nuevo conjunto de claves de Azure Key Vault proporcionadas por el cliente.
  
A partir de hoy, la clave de cliente está implicada en la cadena de cifrado y descifrado de SharePoint datos de archivos en línea almacenados en el almacén de blobs de Azure, pero no SharePoint elementos de lista en línea o metadatos almacenados en el SQL Database. Microsoft 365 no usa la clave de disponibilidad para los archivos de Exchange Online, Skype Empresarial, SharePoint Online, OneDrive para la Empresa y Teams que no sean los descritos anteriormente, que es iniciado por el cliente. El acceso humano a los datos del cliente está protegido por la caja de seguridad del cliente.

## <a name="availability-key-triggers"></a>Desencadenadores de clave de disponibilidad

Microsoft 365 desencadena la clave de disponibilidad solo en circunstancias específicas. Estas circunstancias difieren según el servicio.

### <a name="triggers-for-exchange-online-and-skype-for-business"></a>Desencadenadores para Exchange Online y Skype Empresarial
  
1. Microsoft 365 lee el DEP al que se asigna el buzón para determinar la ubicación de las dos claves de cliente en Azure Key Vault.

2. Microsoft 365 elige aleatoriamente una de las dos claves de cliente del DEP y envía una solicitud a Azure Key Vault para desencapsular la clave DEP mediante la clave de cliente.

3. Si se produce un error en la solicitud para desencapsular la clave DEP mediante la clave de cliente, Microsoft 365 envía una segunda solicitud a Azure Key Vault, esta vez instruyéndola a usar la clave de cliente alternativa (segunda).

4. Si se produce un error en la segunda solicitud para desencapsular la clave DEP mediante la clave de cliente, Microsoft 365 examina los resultados de ambas solicitudes.

    - Si el examen determina que las solicitudes no devolvió un error del sistema:

       - Microsoft 365 desencadena la clave de disponibilidad para descifrar la clave DEP.

       - Microsoft 365, a continuación, usa la clave DEP para descifrar la clave de buzón y completar la solicitud del usuario. 

       - En este caso, Azure Key Vault no puede responder o no es accesible debido a un error transitorio.

    - Si el examen determina que las solicitudes no pudieron devolver ACCESS DENIED:

       - Esto significa que se ha realizado una acción deliberada, involuntaria o malintencionada para que las claves de cliente no estén disponibles (por ejemplo, durante el proceso de purga de datos como parte de la salida del servicio).

       - En este caso, la clave de disponibilidad solo se usará para las acciones del sistema y no para las acciones del usuario, se produce un error en la solicitud del usuario y el usuario recibe un mensaje de error.

> [!IMPORTANT]
> Microsoft 365 código de servicio siempre tiene un token de inicio de sesión válido para razonar sobre los datos del cliente a fin de proporcionar servicios en la nube que agregan valor. Por lo tanto, hasta que se elimine la clave de disponibilidad, se puede usar como reserva para las acciones iniciadas por, o internamente, Exchange Online y Skype Empresarial como la creación de índices de búsqueda o el traslado de buzones. Esto se aplica tanto a las solicitudes errors transitorias como a las solicitudes ACCESS DENIED a Azure Key Vault.

### <a name="triggers-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Desencadenadores para SharePoint archivos en línea, OneDrive para la Empresa y Teams

Para SharePoint archivos en línea, OneDrive para la Empresa y Teams, la clave de disponibilidad NUNCA se usa fuera de la funcionalidad de recuperación y los clientes deben indicar explícitamente a Microsoft que inicie el uso de la clave de disponibilidad durante un escenario de recuperación.

## <a name="audit-logs-and-the-availability-key"></a>Registros de auditoría y la clave de disponibilidad

Los sistemas automatizados de Microsoft 365 procesan todos los datos a medida que fluyen a través del sistema para proporcionar servicios en la nube, por ejemplo, antivirus, detección electrónica, prevención de pérdida de datos e indexación de datos. Microsoft 365 no genera registros visibles para el cliente para esta actividad. Además, el personal de Microsoft no tiene acceso a los datos como parte de estas operaciones normales del sistema.

### <a name="exchange-online-and-skype-for-business-availability-key-logging"></a>registro de claves de disponibilidad Exchange Online y Skype Empresarial

Cuando Exchange Online y Skype Empresarial accede a la clave de disponibilidad para proporcionar servicio, Microsoft 365 publica registros visibles para el cliente accesibles desde el Centro de seguridad y cumplimiento. Cada vez que el servicio usa la clave de disponibilidad, se genera un registro de auditoría para la operación de clave de disponibilidad. Un nuevo tipo de registro denominado "Cifrado del servicio de claves del cliente" con el tipo de actividad "Reserva a clave de disponibilidad" permite a los administradores filtrar los resultados de búsqueda de [registros de auditoría unificada](./search-the-audit-log-in-security-and-compliance.md) para ver los registros de clave de disponibilidad.

Los registros incluyen atributos como fecha, hora, actividad, identificador de organización e identificador de directiva de cifrado de datos. El registro está disponible como parte de los registros de auditoría unificados y es accesible desde la pestaña Búsqueda de registros de auditoría del Centro de cumplimiento de seguridad &.

![Búsqueda de registros de auditoría para eventos clave de disponibilidad](../media/customerkeyauditlogsearchavailabilitykeyloggingimage.png)

los registros de clave de disponibilidad Exchange Online y Skype Empresarial usan el [esquema común](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) de actividad de administración de Office 365 con parámetros personalizados agregados: Id. de directiva, Identificador de versión de clave de ámbito e Id. de solicitud.

![Parámetros personalizados de clave de disponibilidad](../media/customerkeyauditlogsearchavailabilitykeyloggingcustomparam.png)

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-availability-key-logging"></a>SharePoint registro de claves de disponibilidad de archivos en línea, OneDrive para la Empresa y Teams

El registro de claves de disponibilidad aún no está disponible para estos servicios. Para SharePoint archivos en línea, OneDrive para la Empresa y Teams, Microsoft solo activa la clave de disponibilidad, cuando así lo indique, con fines de recuperación. Como resultado, ya conoce todos los eventos en los que se usa la clave de disponibilidad para estos servicios.

## <a name="availability-key-in-the-customer-key-hierarchy"></a>Clave de disponibilidad en la jerarquía clave de cliente
  
Microsoft 365 usa la clave de disponibilidad para ajustar el nivel de claves más bajo en la jerarquía de claves establecida para el cifrado del servicio de claves de cliente. Existen jerarquías clave diferentes entre los servicios. Los algoritmos de clave también difieren entre las claves de disponibilidad y otras claves de la jerarquía de cada servicio aplicable. Los algoritmos de clave de disponibilidad utilizados por los distintos servicios son los siguientes:

- Las claves de disponibilidad Exchange Online y Skype Empresarial usan AES-256.

- Las claves de disponibilidad de archivos SharePoint Online, OneDrive para la Empresa y Teams usan RSA-2048.

### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Cifrado de cifrado que se usa para cifrar claves para Exchange Online y Skype Empresarial

![Cifrado de cifrado para Exchange Online clave de cliente](../media/customerkeyencryptionhierarchiesexchangeskype.png)

### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-and-onedrive-for-business"></a>Cifrado de cifrado que se usa para cifrar las claves de SharePoint Online y OneDrive para la Empresa

![Cifrado de cifrado para SharePoint clave de cliente en línea](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Artículos relacionados

- [Cifrado de servicio con clave de cliente](customer-key-overview.md)

- [Configuración de la clave de cliente](customer-key-set-up.md)

- [Administrar clave de cliente](customer-key-manage.md)

- [Rotar o alternar una Clave de cliente o una clave de disponibilidad](customer-key-availability-key-roll.md)
