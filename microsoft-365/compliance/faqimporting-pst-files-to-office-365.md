---
title: Preguntas más frecuentes sobre la importación de archivos PST a Office 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
description: 'Preguntas más frecuentes para los administradores sobre el uso del servicio de importación de Office 365 para importar los archivos PST de su organización a los buzones de Office 365. '
ms.openlocfilehash: 31df33ffe2c69478f0304bd27b49254995d8b89c
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634438"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a>Preguntas más frecuentes sobre la importación de archivos PST a Office 365

**Este artículo está destinado a los administradores. ¿Desea importar los archivos PST a su propio buzón? Consulte [importar el correo electrónico, los contactos y el calendario desde un archivo. pst de Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|
   
Estas son algunas de las preguntas más frecuentes sobre el uso del servicio de importación de Office 365 para importar archivos PST en masa a los buzones de Office 365. Para obtener más información acerca de cómo importar archivos PST, vea [información general sobre la importación de archivos PST a Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84).
  
## <a name="using-network-upload-to-import-pst-files"></a>Uso de la carga en la red para importar archivos PST

Para obtener instrucciones paso a paso, consulte [usar la carga de red para importar archivos PST a Office 365](use-network-upload-to-import-pst-files.md).
  
 **¿Qué permisos son necesarios para crear trabajos de importación en el servicio de importación de Office 365?**
  
Debe tener asignado el rol importación y exportación de buzón de Exchange Online para importar archivos PST a los buzones de Office 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol Mailbox Import Export al grupo de roles Administración de la organización. O puede crear un nuevo grupo de rol, asignar el rol de exportación e importación de buzón y, después, agregarse o agregar a otros usuarios como miembro. Para obtener más información, vea las secciones "Agregar un rol a un grupo de roles" o "Crear un grupo de roles" en [Administrar grupos de roles en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Además, para crear trabajos de importación en el Centro de seguridad y cumplimiento, debe cumplirse uno de estos requisitos:
  
- Debe tener asignado el rol de los destinatarios de correo en Exchange Online. De forma predeterminada, este rol se asigna a los grupos de roles de administración de la organización y administración de destinatarios.
    
    O bien
    
- Debe ser administrador global en su organización de Office 365. 
    
> [!TIP]
> Puede crear un nuevo grupo de roles en Exchange Online que está pensado específicamente para la importación de archivos PST a Office 365. Para obtener el nivel mínimo de privilegios necesarios para importar archivos PST, asigne los roles de importación y exportación de buzón y de destinatarios de correo al nuevo grupo de roles y, a continuación, agregue a los miembros. 
  
 **¿Dónde está disponible la carga en la red?**
  
La carga de red está disponible actualmente en estas regiones: Estados Unidos, Canadá, Brasil, Reino Unido, Francia, Europa, India, este asiático, sudeste asiático, Japón, República de Corea y Australia. Network upload will be available in more regions soon.

> [!NOTE]
> En este momento, la carga de red de los archivos PST no está disponible en Alemania y Suiza. Estas preguntas más frecuentes se actualizarán cuando se disponga de carga en la red en estos países.
  
 **¿Cuál es el precio de importar archivos PST con la carga en la red?**
  
Using network upload to import PST files is free.
  
Esto también significa que después de que los archivos PST se eliminen del área de Azure Storage, ya no se mostrarán en la lista de archivos para un trabajo de importación completado en el Centro de administración de Microsoft 365. Aunque todavía puede aparecer un trabajo de importación en la página **Importar datos a Office 365**, la lista de archivos PST puede estar vacía cuando vea los detalles de los trabajos de importación más antiguos. 
  
 **¿Qué versión del formato de archivo PST se admite para importarse en Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. Recomendamos la importación de archivos que usen el formato Unicode de archivo PST. En cambio, los archivos que usan el formato ANSI de archivo PST, como pueden ser los de los idiomas que usan un conjunto de caracteres de doble byte (DBCS), también pueden importarse a Office 365. Para obtener más información acerca de la importación de archivos PST ANSI, consulte el paso 4 en [usar la carga en la red para importar los archivos PST de su organización a Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).
  
Además, los archivos PST de Outlook 2007 y versiones posteriores se pueden importar a Office 365.
  
 **Después de cargar mis archivos PST en el área de Azure Storage, ¿cuánto tiempo se mantienen en Azure antes de eliminarse?**
  
Cuando use el método de carga en la red para importar archivos PST, cárguelos en un contenedor de blobs de Azure denominado **ingestiondata**. Si no hay ningún trabajo de importación en curso en la página **Importar archivos PST** en el Centro de seguridad y cumplimiento, entonces todos los archivos PST del contenedor **ingestiondata** en Azure se eliminarán en un plazo de 30 días después de que se haya creado el trabajo de importación más reciente en el Centro de seguridad y cumplimiento. Eso significa también tendrá que crear una nueva tarea de importación en el Centro de seguridad y cumplimiento (se describe en el paso 5 de las instrucciones de carga de red) en un plazo de 30 días posteriores a la carga de archivos PST en Azure. 
  
Esto también significa que después de que los archivos PST se eliminen del área de Azure Storage, ya no se mostrarán en la lista de archivos para un trabajo de importación completado en el Centro de seguridad y cumplimiento. Aunque todavía puede aparecer un trabajo de importación en la página **Importar archivos PST** en el Centro de seguridad y cumplimiento, la lista de archivos PST puede estar vacía cuando vea los detalles de los trabajos de importación más antiguos. 
  
 **¿Cuánto tiempo se tarda en importar un archivo PST en un buzón?**
  
Depende de la capacidad de su red, pero normalmente se necesitan varias horas para que cada terabyte (TB) de datos se cargue en el área de Azure Storage para su organización. Después de que los archivos PST se copien en el área de Azure Storage, un archivo PST se importa a un buzón de Office 365 a una velocidad mínima de 24 GB al día. Si esta tasa no satisface sus necesidades, puede considerar otros métodos para migrar datos de correo electrónico a Office 365. Para obtener más información, vea [Formas de migrar varias cuentas de correo electrónico a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
Si se importan distintos archivos PST a diferentes buzones de destino, el proceso de importación se producirá en paralelo; en otras palabras, cada par de PST y buzón se importará de forma simultánea. Si se importan varios archivos PST al mismo buzón, se hará de manera simultánea.
  
 **¿Existe un límite de tamaño del mensaje al importar archivos PST?**
  
Sí. Si un archivo PST contiene un elemento de buzón de más de 150 MB, el elemento se ignorará durante el proceso de importación.
  
 **¿Las propiedades de los mensajes, como cuando el mensaje se envía o se recibe, la lista de destinatarios y otras propiedades, se conservan cuando se importan los archivos PST en un buzón de Office 365?**
  
Sí. Ninguno de los metadatos de los mensajes originales cambiará durante el proceso de importación.
  
 **¿Existe algún límite en el número de niveles de una jerarquía de carpetas para un archivo PST que quiero importar a un buzón?**
  
Sí. No puede importar archivos PST que tengan 300 o más niveles de carpetas anidadas.
  
 **¿Puedo usar la carga en la red para importar archivos PST en un buzón inactivo en Office 365?**
  
Yes, this capability is now available. 
  
 **¿Puedo usar la carga en la red para importar archivos PST en un buzón de archivo en línea en una implementación híbrida de Exchange?**
  
Sí, esta función está disponible ahora.
  
 **¿Puedo usar la carga de red para importar archivos PST en carpetas públicas de Exchange Online?**
  
No, no puede importar archivos PST en carpetas públicas.
  
## <a name="using-drive-shipping-to-import-pst-files"></a>Uso del envío de unidades para importar los archivos PST

Para obtener instrucciones paso a paso, consulte [usar el envío de unidades para importar archivos PST a Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).
  
 **¿Qué permisos son necesarios para crear trabajos de importación en el servicio de importación de Office 365?**
  
Debe tener asignado el rol Importación o exportación de buzón para poder importar archivos PST a los buzones de Office 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol Mailbox Import Export al grupo de roles Administración de la organización. O puede crear un nuevo grupo de rol, asignar el rol de exportación e importación de buzón y, después, agregarse o agregar a otros usuarios como miembro. Para obtener más información, vea las secciones "Agregar un rol a un grupo de roles" o "Crear un grupo de roles" en [Administrar grupos de roles en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Además, para crear trabajos de importación en el Centro de seguridad y cumplimiento, debe cumplirse uno de estos requisitos:
  
- Debe tener asignado el rol de los destinatarios de correo en Exchange Online. De forma predeterminada, este rol se asigna a los grupos de roles de administración de la organización y administración de destinatarios.
    
    O bien
    
- Debe ser administrador global en su organización de Office 365. 
    
> [!TIP]
> Puede crear un nuevo grupo de roles en Exchange Online que está pensado específicamente para la importación de archivos PST a Office 365. Para obtener el nivel mínimo de privilegios necesarios para importar archivos PST, asigne los roles de importación y exportación de buzón y de destinatarios de correo al nuevo grupo de roles y, a continuación, agregue a los miembros. 
  
 **¿Dónde está disponible el envío de unidades?**
  
El envío de unidades está disponible actualmente en Estados Unidos, Canadá, Brasil, Reino Unido, Europa, India, Asia Oriental, Sudeste asiático, Japón, República de Corea y Australia. Próximamente, el envío de unidades estará disponible en más regiones.

> [!NOTE]
> En este momento, el envío de unidades para importar archivos PST no está disponible en Alemania y Suiza. Estas preguntas más frecuentes se actualizarán cuando se disponga de envío de unidades en estos países.
  
 **¿Qué contratos de licencias comerciales admiten el envío de unidades?**
  
El envío de unidades para importar archivos PST en Office 365 está disponible mediante el Contrato Microsoft Enterprise (EA). El envío de unidades no está disponible mediante un Contrato de productos y servicios de Microsoft (MPSA).
  
 **¿Cuál es el precio de usar el envío de unidades para importar archivos PST en Office 365?**
  
El costo de usar el envío de unidades para importar archivos PST en buzones de Office 365 es de 2 USD por GB de datos. Por ejemplo, si envía una unidad de disco duro que contiene 1000 GB (1 TB) de archivos PST, el costo es 2000 USD. Puede colaborar con un asociado para abonar la cuota de importación. Para obtener información sobre cómo buscar un asociado, consulte [Buscar un asociado o distribuidor de Office 365](https://go.microsoft.com/fwlink/p/?LinkId=785197).
  
 **¿Qué tipo de unidades de disco duro se admiten para el envío de unidades?**
  
El servicio de importación de Office 365 solo se puede usar con unidades de estado sólido de 2,5 pulgadas (SSD) o discos duros internos SATA II/III de 2,5 o 3,5 pulgadas. Puede usar discos duros de hasta 10 TB. Para los trabajos de importación, se procesará solo el primer volumen de datos del disco duro. El volumen de datos debe tener el formato NTFS. Al copiar datos a un disco duro, puede adjuntarlos directamente mediante un conector SSD de 2,5 pulgadas o un conector SATA II o SATA III de 2,5 o 3,5 pulgadas. También puede adjuntarlos de forma externa usando un adaptador USB externo SSD de 2,5 pulgadas o uno SATA II o SATA III de 2,5 o 3,5 pulgadas.
  
> [!IMPORTANT]
> El Servicio de importación de Office 365 no admite los discos duros externos con un adaptador USB integrado. Además, no se puede usar un disco que esté dentro de la carcasa de un disco duro externo. No envíe discos duros externos. 
  
 **¿Cuántas unidades de disco duro puedo enviar para un trabajo de importación único?**
  
Puede enviar un máximo de 10 unidades de disco duro para un único trabajo de importación.
  
 **Después de enviar mi unidad de disco duro, ¿cuánto tiempo tarda en llegar al centro de datos de Microsoft?**
  
Eso depende de varias cosas, como su proximidad al centro de datos de Microsoft y qué tipo de opción de envío ha usado para enviar la unidad de disco duro (es decir, envío en un día, en dos días o entrega mediante red terrestre). Con la mayoría de los transportistas, puede usar el número de seguimiento para realizar un seguimiento del estado de su envío.
  
 **Tras la recepción de mi disco duro en el centro de datos de Microsoft, ¿cuánto tiempo se tarda en cargar los archivos PST en Azure?**
  
Una vez que se recibe el disco duro en el centro de datos de Microsoft, se tardará entre 7 y 10 días laborables para cargar los archivos PST en el área de almacenamiento de Azure de su organización. Los archivos PST se cargarán en un contenedor de blobs de Azure denominado **ingestiondata**. 
  
 **¿Cuánto tiempo se tarda en importar un archivo PST en un buzón?**
  
Una vez que los archivos PST se han cargado al área de Azure Storage, Office 365 analiza los datos de los archivos PST (de forma segura) para identificar la antigüedad de los elementos y los diferentes tipos de mensajes incluidos en los archivos PST. Cuando se haya completado este análisis, podrá importar todos los datos de los archivos PST o establecer filtros para determinar qué datos importa. Durante el trabajo de importación, un archivo PST se importa a un buzón de correo de Office 365 a una velocidad de 24 GB al día como mínimo. Si esta tasa no satisface sus necesidades, puede considerar otros métodos para importar datos de correo electrónico a Office 365. Para obtener más información, vea [Formas de migrar varias cuentas de correo electrónico a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
Si se importan distintos archivos PST a diferentes buzones de destino, el proceso de importación se producirá en paralelo; en otras palabras, cada par de PST y buzón se importará de forma simultánea. Si se importan varios archivos PST al mismo buzón, se hará de manera simultánea.
  
 **Después de que Microsoft cargue mis archivos PST a Azure, ¿cuánto tiempo se conservarán en Azure antes de su eliminación?**
  
Todos los archivos PST de la ubicación de almacenamiento de Azure de su organización (en el contenedor de blobs denominado **ingestiondata**), se eliminarán 30 días después de que se haya creado el trabajo de importación más reciente en la página **importar archivos PST** del centro de seguridad & cumplimiento. 
  
Esto también significa que después de que los archivos PST se eliminen del área de Azure Storage, ya no se mostrarán en la lista de archivos para un trabajo de importación completado en el Centro de seguridad y cumplimiento. Aunque todavía puede aparecer un trabajo de importación en la página **Importar archivos PST** en el Centro de seguridad y cumplimiento, la lista de archivos PST puede estar vacía cuando vea los detalles de los trabajos de importación más antiguos. 
  
 **¿Qué versión del formato de archivo PST se admite para importarse en Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. Recomendamos la importación de archivos que usen el formato Unicode de archivo PST. En cambio, los archivos que usan el formato ANSI de archivo PST, como pueden ser los de los idiomas que usan un conjunto de caracteres de doble byte (DBCS), también pueden importarse a Office 365. Para obtener más información acerca de la importación de archivos PST ANSI, consulte el paso 3 de [usar el envío de unidades para importar archivos PST a Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
Además, los archivos PST de Outlook 2007 y versiones posteriores se pueden importar a Office 365.
  
 **¿Existe un límite de tamaño del mensaje al importar archivos PST?**
  
Sí. Si un archivo PST contiene un elemento de buzón de más de 150 MB, el elemento se ignorará durante el proceso de importación.
  
 **¿Las propiedades de los mensajes, como cuando el mensaje se envía o se recibe, la lista de destinatarios y otras propiedades, se conservan cuando se importan los archivos PST en un buzón de Office 365?**
  
Sí. Los metadatos de los mensajes originales no se modifican durante el proceso de importación.
  
 **¿Existe algún límite en el número de niveles de una jerarquía de carpetas para un archivo PST que quiero importar a un buzón?**
  
Sí. No puede importar archivos PST que tengan 300 o más niveles de carpetas anidadas.
  
 **¿Puedo usar el envío de unidades para importar archivos PST en un buzón inactivo en Office 365?**
  
Yes, this capability is now available.
  
 **¿Puedo usar el envío de unidades para importar archivos PST en un buzón de archivo en línea en una implementación híbrida de Exchange?**
  
Sí, esta función está disponible ahora.
  
 **¿Puedo usar el envío de unidades para importar archivos PST en carpetas públicas de Exchange Online?**
  
No, no puede importar archivos PST en carpetas públicas.
  
 **¿Puede Microsoft borrar los datos de mi unidad de disco duro antes de que me la envíen de nuevo?**
  
No, Microsoft no puede borrar los datos de las unidades de disco duro antes de enviarlas de nuevo a los clientes. Las unidades de disco duro se le devuelven en el mismo estado en el que se encontraban cuando las recibió Microsoft.
  
 **¿Puede Microsoft destruir mi unidad de disco duro en lugar de enviármela de nuevo?**
  
No, Microsoft no puede destruir la unidad de disco duro. Las unidades de disco duro se le devuelven en el mismo estado que estaban cuando las recibió Microsoft.
  
 **¿Qué servicios de mensajería admiten la devolución?**
  
Si es un cliente de Estados Unidos o Europa, Microsoft usa FedEx para devolver la unidad de disco duro. Para las demás regiones, Microsoft usa DHL.
  
 **¿Cuáles son los costos de la devolución?**
  
Los costos de la devolución varían dependiendo de la proximidad al centro de datos de Microsoft al que ha enviado la unidad. Microsoft facturará la cuenta de DHL o FedEx para devolver su unidad de disco duro. El costo de la devolución es su responsabilidad.
  
 **¿Puedo usar un servicio de envío personalizado, como el envío personalizado de FedEx, para enviar mi unidad de disco duro a Microsoft?**
  
Sí.
  
 **Si tengo que enviar mi unidad a otro país, ¿necesito hacer algo?**
  
La unidad de disco duro que envíe a Microsoft puede tener que atravesar fronteras internacionales. Si este es el caso, es responsable de garantizar que la unidad y los datos que contiene se importen o exporten según las leyes aplicables. Antes de enviar una unidad de disco duro, compruebe con sus asesores que la unidad y los datos pueden enviarse legalmente al centro de datos de Microsoft especificado. Esto ayudará a garantizar que llegan a Microsoft de manera puntual.
