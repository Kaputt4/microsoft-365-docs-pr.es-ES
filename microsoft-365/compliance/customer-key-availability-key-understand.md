---
title: Obtenga información sobre la clave de disponibilidad para Office 365 Customer Key
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
description: Obtenga información sobre la clave de disponibilidad que se usa para recuperar claves de cliente de Office 365 perdidas.
ms.openlocfilehash: 86f602a59f436a6ce42df583c88c0403eb17e5ae
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42076965"
---
# <a name="learn-about-the-availability-key-for-office-365-customer-key"></a>Obtenga información sobre la clave de disponibilidad para Office 365 Customer Key

La clave de disponibilidad es una clave raíz que se genera y aprovisiona automáticamente cuando se crea una directiva de cifrado de datos. Office 365 almacena y protege la clave de disponibilidad. La clave de disponibilidad es funcionalmente similar a las dos claves raíz que se proporcionan para el cifrado de servicio con la clave de cliente. La clave de disponibilidad ajusta las claves en un nivel inferior de la jerarquía de claves. A diferencia de las claves que se proporcionan y se administran en Azure Key Vault, no se puede tener acceso directamente a la clave Availability. Office 365 Automated Services administre la clave de disponibilidad con cmdlets de PowerShell. Estos cmdlets inician operaciones automatizadas que nunca implican acceso directo a la clave de disponibilidad.

El objetivo principal de la clave de disponibilidad es proporcionar la capacidad de recuperación de la pérdida imprevista de las claves raíz que se administran. La pérdida podría ser el resultado de una acción malintencionada o de una mala administración. Si pierde el control de las claves raíz, póngase en contacto con el soporte técnico de Microsoft y Microsoft le ayudará en el proceso de recuperación con la clave de disponibilidad. Usará la clave de disponibilidad para migrar a una nueva Directiva de cifrado de datos con las claves raíz nuevas que aprovisione.

El almacenamiento y el control de la clave de disponibilidad son deliberadamente diferentes de las claves de Azure Key Vault por tres motivos:

- La clave de disponibilidad proporciona una función de recuperación y "interrupción de la luna" si se pierde el control sobre ambas claves del almacén de claves de Azure.
- La separación de los controles lógicos y las ubicaciones de almacenamiento seguro proporciona una defensa en profundidad y protege contra la pérdida de todas las claves y de los datos, desde un único ataque o punto de error.
- La clave de disponibilidad proporciona una capacidad de alta disponibilidad si los servicios de Office 365 no pueden comunicarse con claves hospedadas en Azure Key Vault debido a errores transitorios. Esta regla solo se aplica a Exchange Online y al cifrado del servicio de Skype empresarial. Los archivos de SharePoint Online, OneDrive para la empresa y Microsoft Teams nunca usan la clave de disponibilidad a menos que indique explícitamente a Microsoft que inicie el proceso de recuperación.

Compartir la responsabilidad para proteger los datos, mediante el uso de una variedad de protecciones y procesos para la administración de claves, reduce en última instancia el riesgo de que se pierdan o destruyan permanentemente todas las claves (y, por lo tanto, los datos). Microsoft proporciona una única autoridad sobre la deshabilitación o la destrucción de la clave de disponibilidad cuando abandona el servicio. Por diseño, nadie en Microsoft tiene acceso a la clave de disponibilidad: solo es accesible para el código del servicio de Office 365.

Consulte el [centro de confianza de Microsoft](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data) para obtener más información sobre cómo se protegen las claves.
  
## <a name="availability-key-uses"></a>Uso de la clave de disponibilidad

La clave de disponibilidad proporciona capacidad de recuperación para escenarios en los que un malefactor externo o Insider roba el control de la bóveda clave, o cuando una administración no intencionada de forma inadvertida da como resultado la pérdida de claves raíz. Esta capacidad de recuperación se aplica a todos los servicios de Office 365 compatibles con la clave de cliente. Los servicios individuales usan la clave de disponibilidad de forma diferente. Office 365 solo usa la clave de disponibilidad de las maneras que se describen a continuación.

### <a name="exchange-online-and-skype-for-business-uses"></a>Exchange Online y Skype empresarial usan

Además de la capacidad de recuperación, Exchange Online y Skype empresarial usan la clave de disponibilidad para garantizar la disponibilidad de los datos durante los problemas de funcionamiento transitorios, o intermitentes, relacionados con las claves raíz de acceso del servicio. Cuando el servicio no puede llegar a ninguna de las claves de cliente en Azure Key Vault debido a errores transitorios, el servicio usa automáticamente la clave de disponibilidad. El servicio nunca va directamente a la clave de disponibilidad.

Los sistemas automatizados de Exchange Online y Skype empresarial pueden usar la clave de disponibilidad durante los errores transitorios para admitir los servicios back-end automatizados como anti-virus, e-Discovery, prevención de pérdida de datos, movimientos de buzones de correo y indización de datos.

### <a name="sharepointonlineonedriveforbusinessandteamsfiles-uses"></a>Los archivos de SharePoint Online, OneDrive para la empresa y Microsoft Teams usan

Para los archivos de SharePoint Online, OneDrive para la empresa y Microsoft Teams, la clave de disponibilidad nunca se usa fuera de la capacidad de recuperación y los clientes deben indicar explícitamente a Microsoft que inicie el uso de la clave de disponibilidad durante un escenario de recuperación. Las operaciones de servicio automatizadas se basan exclusivamente en las claves de cliente en Azure Key Vault. Para obtener información detallada sobre cómo funciona la jerarquía clave para estos servicios, vea [Cómo SharePoint Online, OneDrive para la empresa y los archivos de Microsoft Teams usan la clave de disponibilidad](#how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key).

## <a name="availability-key-security"></a>Seguridad de clave de disponibilidad

Microsoft comparte la responsabilidad de la protección de datos con usted creando una instancia de la clave de disponibilidad y adoptando medidas extensivas para protegerla. Microsoft no expone el control directo de la clave de disponibilidad a los clientes. Por ejemplo, solo puede girar (girar) las claves que posee en el almacén de claves de Azure. Para obtener más información, consulte [Roll or Rotate a Customer Key o a Availability Key](customer-key-availability-key-roll.md).

### <a name="availability-key-secret-stores"></a>Almacenes principales del secreto de disponibilidad

Microsoft protege las claves de disponibilidad en almacenes de secreto interno controlados por acceso, como el almacén de claves de Azure accesible para el cliente. Implementamos controles de acceso para evitar que los administradores de Microsoft accedan directamente a los secretos contenidos en. Las operaciones del almacén secreto, incluida la rotación, la eliminación y la recuperación clave se producen a través de comandos automatizados que nunca implican acceso directo a la clave de disponibilidad. El acceso para ajustar estos comandos está limitado a ingenieros específicos y requiere el aumento de privilegios a través de una herramienta interna, Lockbox. La elevación de privilegios requiere la aprobación del administrador y la justificación antes de que se concedan. Lockbox asegura que el acceso esté enlazado a tiempo con la revocación de acceso automática cuando se agote el tiempo o se cierre la sesión del ingeniero.

Las claves de disponibilidad de **Skype empresarial y Exchange Online** se almacenan en un almacén secreto de Active Directory. Exchange Online Active Directory está compuesto por bosques de administración que enrutan el tráfico y los bosques de capacidad que contienen objetos, identidades y datos. Los bosques de capacidad constan de bosques de cuentas y bosques de recursos. Los bosques de cuentas tienen varios controladores de dominio de capacidad que se sincronizan entre sí. Las claves de disponibilidad se almacenan de forma segura dentro de estos controladores de dominio de capacidad. Esta ubicación de almacenamiento seguro es independiente y aislada del almacén secreto de SharePoint Online, OneDrive para la empresa y archivos de Microsoft Teams.

Las claves de disponibilidad de **los archivos de SharePoint Online, OneDrive para la empresa y Microsoft Teams** se almacenan en un almacén secreto interno administrado por el equipo de servicio. Este servicio de almacenamiento de secretos seguros tiene servidores front-end con extremos de la aplicación y una base de datos SQL como back-end. Las claves de disponibilidad se almacenan en la base de datos SQL y se empaquetan (cifradas) mediante claves de cifrado del almacén secreto que usan una combinación de AES-256 y HMAC para cifrar la clave de disponibilidad en reposo. Las claves de cifrado del almacén secreto se almacenan en un componente aislado lógicamente de la misma base de datos SQL y se cifran con claves RSA-2048 contenidas en certificados administrados por la entidad de certificación (CA) de Microsoft. Estos certificados se almacenan en los servidores front-end del almacén secreto que realizan operaciones en la base de datos.

### <a name="defense-in-depth"></a>Defensa en profundidad

Microsoft emplea una estrategia de defensa en profundidad para evitar que los actores malintencionados afecten a la confidencialidad, la integridad o la disponibilidad de los datos de clientes almacenados en la nube de Microsoft. Se implementan controles preventivos y de detectives específicos para proteger el almacén secreto y la clave de disponibilidad como parte de la estrategia de seguridad general.

Office 365 se ha creado para evitar el mal uso de la clave de disponibilidad. La capa de aplicación es el único método a través del cual se pueden usar claves, incluida la clave de disponibilidad, para cifrar y descifrar datos. Solo el código de servicio de Office 365 tiene la capacidad de interpretar y recorrer la jerarquía de claves para actividades de cifrado y descifrado. Si un administrador malintencionado de Microsoft omitió los controles para extraer una clave de disponibilidad del almacén secreto, la clave no puede usarse para obtener acceso a los datos del cliente. El aislamiento lógico se encuentra entre las ubicaciones de almacenamiento de las claves de cliente, las claves de disponibilidad, otras claves jerárquicas y los datos de clientes. Este aislamiento reduce el riesgo de exposición de los datos en caso de que una o más ubicaciones estén en peligro. Cada capa de la jerarquía ha incorporado capacidades de detección de intrusiones 24x7 para proteger los almacenes de datos y secretos.

Los controles de acceso se implementan para evitar el acceso no autorizado a sistemas internos, incluidos los almacenes de claves secretas de disponibilidad. Los ingenieros de Microsoft no tienen acceso directo a los almacenes de clave secretas de disponibilidad. Para obtener más información sobre los controles de acceso, revise [controles de acceso administrativo en Office 365](https://docs.microsoft.com/Office365/securitycompliance/office-365-administrative-access-controls-overview).

Los controles técnicos impiden que el personal de Microsoft inicie sesión en cuentas de servicio con privilegios elevados, que de otro modo podrían usar los atacantes para suplantar los servicios de Office 365. Por ejemplo, estos controles evitan el inicio de sesión interactivo.

Los controles de registro y supervisión de seguridad son otra protección defensiva implementada que mitiga el riesgo de los servicios de Microsoft y sus datos. Los equipos de servicios de Microsoft han implementado soluciones de supervisión activas que generan alertas y registros de auditoría. Todos los equipos de servicios cargan sus registros en un repositorio central donde se agregan y procesan los registros. Las herramientas internas examinan automáticamente los registros para confirmar que los servicios funcionan en un estado óptimo, resistente y seguro. La actividad inusual se marca para una revisión posterior.

Cualquier evento de registro que indique una posible infracción de la Directiva de seguridad de Microsoft se pone inmediatamente en conocimiento de los equipos de seguridad de Microsoft. Office 365 Security ha configurado las alertas para detectar el intento de acceso a los almacenes secretos clave de disponibilidad. También se generan alertas si el personal de Microsoft intenta iniciar sesión de forma interactiva para las cuentas de servicio, prohibidas y protegidas por los controles de acceso. Office 365 Security también detecta y alerta sobre desviaciones del servicio de Office 365 de las operaciones de línea de base normales. Malefactors de un intento de mal uso de los servicios de Office 365 activarían las alertas que generaban la expulsión del atacante desde el entorno de nube de Microsoft.

## <a name="use-the-availability-key-to-recover-from-key-loss"></a>Usar la clave de disponibilidad para recuperarse de la pérdida de claves

Si pierde el control de las claves de cliente, la clave de disponibilidad le proporciona la capacidad de recuperar y volver a cifrar los datos.

### <a name="recovery-procedure-for-exchange-online-and-skype-for-business"></a>Procedimiento de recuperación para Exchange Online y Skype empresarial

Si pierde el control de las claves de cliente, la clave de disponibilidad le ofrece la capacidad de recuperar los datos y de volver a poner en línea los recursos de Office 365 afectados. La clave de disponibilidad sigue protegiendo sus datos mientras se recupera. En un nivel alto, para una recuperación completa de la pérdida de clave, deberá crear un nuevo DEP y mover los recursos afectados a la nueva Directiva.

Para cifrar los datos con nuevas claves de cliente, cree nuevas claves en Azure Key Vault, cree un nuevo DEP con las nuevas claves de cliente y, a continuación, asigne el nuevo DEP a los buzones que están cifrados actualmente con el DEP anterior para el que las claves se han perdido o están en peligro.

Este proceso de nuevo cifrado puede tardar hasta 72 horas. Esta es la duración estándar cuando se cambia un DEP.
  
### <a name="recovery-procedure-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Procedimiento de recuperación para archivos de SharePoint Online, OneDrive para la empresa y Microsoft Teams

Para los archivos de SharePoint Online, OneDrive para la empresa y Microsoft Teams, la clave de disponibilidad nunca se usa fuera de la capacidad de recuperación. Debe indicar explícitamente a Microsoft que inicie el uso de la clave de disponibilidad durante un escenario de recuperación. Para iniciar el proceso de recuperación, póngase en contacto con Microsoft para activar la clave de disponibilidad. Una vez activada, la clave de disponibilidad se usa automáticamente para descifrar los datos, lo que le permite cifrar los datos con un DEP recién creado asociado a nuevas claves de clientes.  

Esta operación es proporcional al número de sitios de la organización. Una vez que llame a Microsoft para usar la clave de disponibilidad, debe estar completamente en línea en un plazo de cuatro horas.

## <a name="how-exchange-online-and-skype-for-business-use-the-availability-key"></a>Uso de la clave de disponibilidad en Exchange Online y Skype empresarial

Cuando se crea un DEP con una clave de cliente, Office 365 genera una clave de la Directiva de cifrado de datos (clave DEP) asociada a ese DEP. El servicio cifra la clave DEP tres veces: una con cada una de las claves de cliente y otra con la clave de disponibilidad. Solo se almacenan las versiones cifradas de la clave de DEP y una clave de DEP solo se puede descifrar con las claves de cliente o la clave de disponibilidad. A continuación, se usa la clave DEP para cifrar las claves de buzón, que cifran los buzones individuales.
  
Office 365 sigue este proceso para descifrar y proporcionar datos cuando los clientes usan el servicio:
  
1. Descifre la clave de DEP con la clave de cliente.

2. Use la clave DEP descifrada para descifrar una clave de buzón.

3. Use la clave de buzón descifrado para descifrar el buzón de correo mismo, lo que le permite tener acceso a los datos del buzón.

Office 365 descifra una clave DEP emitiendo dos solicitudes de descifrado a Azure Key Vault con un ligero desplazamiento. La primera para finalizar ofrece el resultado, cancelando la otra solicitud.

## <a name="how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key"></a>Cómo los archivos de SharePoint Online, OneDrive para la empresa y Teams usan la clave de disponibilidad

La arquitectura y la implementación de SharePoint Online y OneDrive para la empresa para la clave de cliente y la clave de disponibilidad son diferentes de Exchange Online y Skype empresarial.
  
Cuando una organización se mueve a claves administradas por el cliente, Office 365 crea una clave intermedia específica del espacio empresarial (TIK). Office 365 cifra el TIK dos veces, una vez con cada una de las claves de cliente y almacena las dos versiones cifradas de TIK. Solo se almacenan las versiones cifradas de TIK y un TIK solo se puede descifrar con las claves de cliente. A continuación, el TIK se usa para cifrar las claves del sitio, que se usan para cifrar claves BLOB (también denominadas claves de fragmentos de archivo). Según el tamaño del archivo, el servicio puede dividir un archivo en varios fragmentos de archivo con una clave única. Los BLOBs (fragmentos de archivo) se cifran con las claves BLOB y se almacenan en el servicio de almacenamiento de blobs de Microsoft Azure.
  
Office 365 sigue este proceso para descifrar y proporcionar los archivos de cliente cuando los clientes usan el servicio:

1. Descifre la TIK con la clave de cliente.

2. Use la TIK descifrada para descifrar una clave de sitio.

3. Use la clave de sitio descifrada para descifrar una clave BLOB.

4. Use la clave BLOB descifrada para descifrar el BLOB.

Office 365 descifra un TIK emitiendo dos solicitudes de descifrado a Azure Key Vault con un ligero desplazamiento. La primera para finalizar ofrece el resultado, cancelando la otra solicitud.
  
En caso de que pierda el acceso a las claves de cliente, Office 365 también cifra el TIK con una clave de disponibilidad y lo almacena junto con el TIKs cifrado con cada clave de cliente. La TIK cifrada con la clave de disponibilidad solo se usa cuando el cliente llama a Microsoft para dar de alta la ruta de recuperación cuando ha perdido el acceso a sus claves, de forma malintencionada o accidental.
  
Por motivos de disponibilidad y escala, los TIKs descifrados se almacenan en caché en una memoria caché de memoria de tiempo limitado. Dos horas antes de que se establezca la expiración de la memoria caché de TIK, Office 365 intenta descifrar cada TIK. El descifrado de TIKs amplía la duración de la memoria caché. Si se produce un error en el descifrado de TIK durante un período de tiempo significativo, Office 365 genera una alerta para notificar Ingeniería antes de la expiración de la caché. Solo si el cliente llama a Microsoft Office 365 iniciar la operación de recuperación, lo que implica descifrar TIK con la clave de disponibilidad almacenada en el almacén de secretos de Microsoft y volver a incorporar el inquilino mediante el TIK descifrado y un nuevo conjunto de claves de almacén de claves de Azure suministradas por el cliente.
  
A partir de hoy, la clave de cliente está involucrada en la cadena de cifrado y descifrado de los datos de archivo de SharePoint Online almacenados en el almacén de blobs de Azure, pero no en los elementos de lista o metadatos de SharePoint Online almacenados en la base de datos SQL. Office 365 no usa la clave de disponibilidad para los archivos de Exchange Online, Skype empresarial, SharePoint Online, OneDrive para la empresa y teams que no sean los que se describen anteriormente, que se inician por el cliente. El acceso humano a los datos de los clientes está protegido por las cajas de caja del cliente.

## <a name="availability-key-triggers"></a>Desencadenadores de clave de disponibilidad

Office 365 activa la clave de disponibilidad sólo en circunstancias específicas. Estas circunstancias difieren según el servicio.

### <a name="triggers-for-exchange-online-and-skype-for-business"></a>Desencadenadores para Exchange Online y Skype empresarial
  
1. Office 365 lee la DEP a la que está asignado el buzón para determinar la ubicación de las dos claves de cliente en Azure Key Vault.

2. Office 365 elige aleatoriamente una de las dos claves de cliente de la DEP y envía una solicitud a Azure Key Vault para desajustar la clave de DEP mediante la clave de cliente.

3. Si se produce un error en la solicitud para desencapsular la clave de DEP mediante la clave de cliente, Office 365 envía una segunda solicitud a Azure Key Vault, esta vez indicando que use la clave de cliente alternativa (segundo).

4. Si se produce un error en la segunda solicitud para desencapsular la clave de DEP mediante la clave de cliente, Office 365 examina los resultados de ambas solicitudes.

    - Si el examen determina que las solicitudes no se han vuelto a devolver un ERROR del sistema:

       - Office 365 activa la clave de disponibilidad para descifrar la clave DEP.

       - A continuación, Office 365 usa la clave DEP para descifrar la clave de buzón y completar la solicitud del usuario. 

       - En este caso, Azure Key Vault no puede responder o no ser accesible debido a un ERROR transitorio.

    - Si el examen determina que las solicitudes no se han vuelto a devolver acceso denegado:

       - Esto significa que se ha realizado una acción deliberada, involuntaria o malintencionada para representar las claves del cliente no disponibles (por ejemplo, durante el proceso de depuración de datos como parte del abandono del servicio).

       - En este caso, no se usará la clave de disponibilidad, se producirá un error en la solicitud del usuario y el usuario recibirá un mensaje de error.

>[!IMPORTANT]
>El código de servicio de Office 365 siempre tiene un token de inicio de sesión válido para la conformación de los datos de clientes para proporcionar servicios en la nube de valor agregado. Por lo tanto, hasta que se elimine la clave de disponibilidad, puede usarse como reserva para las acciones iniciadas por Exchange Online y Skype empresarial, como la creación de índice de búsqueda o el movimiento de buzones de correo. Esto se aplica tanto a los errores transitorios como a las solicitudes de acceso denegado a Azure Key Vault.

### <a name="triggers-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Desencadenadores para los archivos de SharePoint Online, OneDrive para la empresa y Microsoft Teams

Para los archivos de SharePoint Online, OneDrive para la empresa y Microsoft Teams, la clave de disponibilidad nunca se usa fuera de la capacidad de recuperación y los clientes deben indicar explícitamente a Microsoft que inicie el uso de la clave de disponibilidad durante un escenario de recuperación.

## <a name="audit-logs-and-the-availability-key"></a>Registros de auditoría y la clave de disponibilidad

Sistemas automatizados en Office 365 procesar todos los datos a medida que se transmiten a través del sistema para proporcionar servicios en la nube, por ejemplo, antivirus, e-Discovery, prevención de pérdida de datos e indización de datos. Office 365 no genera registros visibles para el cliente de esta actividad. Además, el personal de Microsoft no tiene acceso a los datos como parte de estas operaciones normales del sistema.

### <a name="exchange-online-and-skype-for-business-availability-key-logging"></a>Registro de claves de disponibilidad de Skype empresarial y Exchange Online

Exchange Online y Skype empresarial usan automáticamente la clave de disponibilidad durante los errores transitorios. Cuando se produce esta reserva, Office 365 publica registros visibles para el cliente accesibles desde el centro de seguridad y cumplimiento. Cada vez que estos servicios usan la clave de disponibilidad, se genera un registro de auditoría para la operación de clave de disponibilidad. Un nuevo tipo de registro denominado "cifrado del servicio de clave de cliente" con el tipo de actividad "fallback to Availability key" permite a los administradores filtrar los resultados de la búsqueda de registros de [Auditoría unificada](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) para ver los registros clave de disponibilidad. El registro de la clave de disponibilidad se genera solo cuando la clave Customer se usa para obtener acceso a los datos y no para las claves administradas por el servicio de Microsoft.

Los registros de registro incluyen atributos como la fecha, la hora, la actividad, el identificador de la organización y el identificador de la Directiva de cifrado de datos. El registro está disponible como parte de los registros de auditoría unificada de Office 365 y es accesible desde la ficha de búsqueda de registro de auditoría del centro de seguridad y cumplimiento de Office 365.

![Búsqueda de registros de auditoría para eventos de clave de disponibilidad](../media/customerkeyauditlogsearchavailabilitykeyloggingimage.png)

Los registros de claves de disponibilidad de Skype empresarial y Exchange Online usan el [esquema común](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) de actividad de administración de Office 365 con parámetros personalizados agregados: identificador de Directiva, identificador de versión de clave de ámbito y identificador de solicitud.

![Parámetros personalizados de clave de disponibilidad](../media/customerkeyauditlogsearchavailabilitykeyloggingcustomparam.png)

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-availability-key-logging"></a>Registro de clave de disponibilidad de archivos de SharePoint Online, OneDrive para la empresa y Teams

El registro de clave de disponibilidad todavía no está disponible para estos servicios. En el caso de los archivos de SharePoint Online, OneDrive para la empresa y Microsoft Teams, la clave de disponibilidad solo la activa Microsoft, cuando se le indique, para propósitos de recuperación. Como resultado, ya conoce cada evento en el que se usa la clave de disponibilidad para estos servicios.

## <a name="availability-key-in-the-customer-key-hierarchy"></a>Clave de disponibilidad en la jerarquía de clave de cliente
  
Office 365 usa la clave de disponibilidad para ajustar el nivel de las claves inferiores en la jerarquía clave establecida para el cifrado del servicio de clave de cliente. Existen distintas jerarquías de clave entre los servicios. Los algoritmos de clave también difieren entre las claves de disponibilidad y otras claves de la jerarquía de cada servicio aplicable. Los algoritmos de clave de disponibilidad usados por los diferentes servicios son los siguientes:

- Las claves de disponibilidad de Skype empresarial y Exchange Online usan AES-256.

- Las claves de disponibilidad de los archivos de SharePoint Online, OneDrive para la empresa y Microsoft Teams usan RSA-2048.

### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Cifrado de cifrado usado para cifrar claves para Exchange Online y Skype empresarial

![Cifrado de cifrado para la clave de cliente de Exchange Online](../media/customerkeyencryptionhierarchiesexchangeskype.png)

### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-and-onedrive-for-business"></a>Cifrado de cifrado usado para cifrar claves para SharePoint Online y OneDrive para la empresa

![Cifrado de cifrado para la clave de cliente de SharePoint Online](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Artículos relacionados

- [Cifrado de servicios con clave de cliente de Office 365](customer-key-overview.md)

- [Configurar la clave de cliente de Office 365](customer-key-set-up.md)

- [Administrar la clave de cliente de Office 365](customer-key-manage.md)

- [Rollo o rotación de una clave de cliente o una clave de disponibilidad](customer-key-availability-key-roll.md)
