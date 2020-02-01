---
title: Información general sobre el archivado ilimitado en Office 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: Obtenga información sobre el archivado de expansión automática en Office 365, que proporciona almacenamiento ilimitado de archivos para buzones de Exchange Online.
ms.openlocfilehash: e7d004c7ef92fbcb331191432a70114f36dabc07
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601376"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a>Información general sobre el archivado ilimitado en Office 365

En Office 365, los buzones de archivo proporcionan a los usuarios espacio de almacenamiento adicional en el buzón de correo. Después de habilitar el buzón de archivo de un usuario, hay disponible hasta 100 GB de almacenamiento adicional. En el pasado, cuando se alcanzaba la cuota de almacenamiento de 100-GB, las organizaciones tenían que ponerse en contacto con Microsoft para solicitar espacio de almacenamiento adicional para un buzón de archivo. Esto ya no es así.

La característica de archivado ilimitado de Office 365 (denominada *archivado de expansión automática*) proporciona almacenamiento adicional en los buzones de archivo. Cuando se alcanza la cuota de almacenamiento en el buzón de archivo, Office 365 aumenta automáticamente el tamaño del archivo, lo que significa que los usuarios no se quedarán sin espacio de almacenamiento en el buzón y los administradores no tendrán que solicitar almacenamiento adicional para los buzones de archivo.

Para obtener instrucciones paso a paso para activar el archivado de expansión automática, vea [Habilitar el archivado ilimitado en Office 365](enable-unlimited-archiving.md).

> [!NOTE]
> El archivado de expansión automática también es compatible con los buzones compartidos. Para habilitar el archivo para un buzón compartido, se necesita una licencia de Exchange Online (plan 2) o una licencia de Exchange Online (plan 1) con una licencia de archivado de Exchange Online.

## <a name="how-auto-expanding-archiving-works"></a>Funcionamiento del archivado de expansión automática

Como se ha explicado anteriormente, el espacio de almacenamiento de buzones de correo adicional se crea cuando se habilita el buzón de archivo de un usuario. Cuando el archivado de expansión automática está habilitado, Office 365 comprueba periódicamente el tamaño del buzón de archivo. Cuando un buzón de archivo se acerca al límite de almacenamiento, Office 365 crea automáticamente espacio de almacenamiento adicional para el archivo. Si el usuario se queda sin este espacio de almacenamiento adicional, Office 365 agrega más espacio de almacenamiento al archivo del usuario. Este proceso se produce de forma automática, lo que significa que los administradores no tienen que solicitar el almacenamiento de archivos adicional o administrar el archivado de expansión automática.

A continuación se muestra una introducción rápida del proceso.

![Información general sobre el proceso de archivado de expansión automática](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. El archivado está habilitado para un buzón de usuario o un buzón compartido. Se crea un buzón de archivo con 100 GB de espacio de almacenamiento y la cuota de advertencia para el buzón de archivo se establece en 90 GB.

2. Un administrador habilita el archivado de expansión automática para el buzón de correo. Cuando el buzón de archivo (incluida la carpeta elementos recuperables) alcanza los 90 GB, se convierte en un archivo de expansión automática y Office 365 agrega espacio de almacenamiento al archivo. El espacio de almacenamiento adicional puede tardar hasta 30 días en aprovisionarse.

   > [!NOTE]
   > Si un buzón se coloca en retención o se asigna a una directiva de retención de Office 365, la cuota de almacenamiento para el buzón de archivo aumenta a 110 GB cuando está habilitado el archivado de expansión automática. De forma similar, la cuota de advertencia de archivo aumenta a 100 GB.

3. Office 365 agrega automáticamente más espacio de almacenamiento cuando es necesario.

> [!IMPORTANT]
> El archivo de expansión automática solo se admite para los buzones de correo que se usan para usuarios individuales (o buzones compartidos) con una tasa de crecimiento que no supera 1 GB por día. El buzón de archivo de un usuario está diseñado exclusivamente para dicho usuario. El uso del registro en diario, las reglas de transporte o las reglas de reenvío automático para copiar mensajes en un buzón de archivo no está permitido. Microsoft se reserva el derecho a denegar el archivado ilimitado en los casos en que el buzón de archivo de un usuario se usa para almacenar datos de archivo para otros usuarios o en otros casos del uso inadecuado.

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>¿Qué se mueve al espacio de almacenamiento adicional del archivo?

Para hacer un uso eficaz del almacenamiento de archivos de expansión automática, las carpetas pueden moverse. Office 365 determina qué carpetas se mueven cuando se agrega almacenamiento adicional al archivo. A veces, cuando se mueve una carpeta, se crean automáticamente una o varias subcarpetas y los elementos de la carpeta original se distribuyen a estas carpetas para facilitar el proceso de movimiento. Al ver la parte de archivo de la lista de carpetas en Outlook, estas subcarpetas se muestran en la carpeta original.  La Convención de nomenclatura que Office 365 usa para nombrar estas subcarpetas es ** \<el\>nombre de carpeta _yyyy (creado en MMM DD, YYYY h_mm)**, donde:

- **yyyy** es el año en que se recibieron los mensajes de la carpeta.

- **DD de MMM de aaaa h_m** es la fecha y hora en que la subcarpeta se creó en Office 365, en formato UTC, en función de la zona horaria del usuario y la configuración regional en Outlook.

En las siguientes capturas de pantallas se muestra una lista de carpetas antes y después de que los mensajes se muevan a un archivo de expansión automática.

 **Antes de agregar almacenamiento adicional**

![Lista de carpetas de buzón de archivo antes de aprovisionar el archivo de expansión automática](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 **Una vez agregado el almacenamiento adicional**

![Lista de carpetas del buzón de archivo después de aprovisionar el archivo de expansión automática](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> Como se ha descrito anteriormente, Office 365 mueve los elementos a las subcarpetas (y los asigna a sus nombres usando la Convención de nomenclatura descrita anteriormente) para facilitar la distribución de contenido a un archivo auxiliar. Pero mover elementos a subcarpetas no siempre es así. A veces, se puede mover una carpeta completa a un archivo auxiliar. En este caso, la carpeta contendrá su nombre original.  No será visible en la lista de carpetas de Outlook que la carpeta se movió a un archivo auxiliar.

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>Requisitos de Outlook para obtener acceso a elementos en un archivo de expansión automática

Para obtener acceso a los mensajes que se almacenan en un archivo de expansión automática, los usuarios tienen que usar uno de los siguientes clientes de Outlook:

- Outlook 2016 o Outlook 2019 para Windows

- Outlook en la Web

- Outlook 2016 o Outlook 2019 para Mac

Estos son algunos aspectos que se deben tener en cuenta al usar Outlook o Outlook en la web para tener acceso a los mensajes almacenados en un archivo de expansión automática.

- Puede tener acceso a cualquier carpeta del buzón de archivo, incluidas las que se han movido al área de almacenamiento expandido automáticamente.

- Puede buscar elementos que se movieron a un área de almacenamiento adicional solo si busca en la propia carpeta. Esto significa que debe seleccionar la carpeta de archivo en la lista de carpetas para seleccionar la opción **carpeta actual** como ámbito de búsqueda. De forma similar, si una carpeta de un área de almacenamiento con expansión automática contiene subcarpetas, deberá buscar cada subcarpeta por separado.

- Los recuentos de elementos en Outlook y los recuentos de leídos o no leídos (en Outlook y Outlook en la web) en un archivo de expansión automática podrían no ser precisos.

- Puede eliminar los elementos de una subcarpeta que señale a un área de almacenamiento expandida automáticamente, pero no se puede eliminar la carpeta en sí.

- No puede usar la característica recuperar elementos eliminados para recuperar un elemento que se eliminó de un área de almacenamiento expandida automáticamente.

## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a>Archivado de expansión automática y otras características de cumplimiento de Office 365

En esta sección se explica la funcionalidad entre el archivado de expansión automática y otras características del gobierno de datos y cumplimiento de Office 365.

- **eDiscovery:** Cuando usa una herramienta de exhibición de documentos electrónicos de Office 365, como búsqueda de contenido o exhibición de documentos electrónicos local, también se busca en las áreas de almacenamiento adicionales de un archivo de expansión automática.

- **Retención:** Cuando coloca un buzón de correo en retención mediante el uso de herramientas como retención por juicio en Exchange online o eDiscovery Case retenciones y directivas de retención en el centro de seguridad y cumplimiento, el contenido ubicado en un archivo de expansión automática también se coloca en retención.

- **Administración de registros de mensajes (MRM):** Si usa directivas de eliminación de MRM en Exchange Online para eliminar de forma permanente los elementos de buzón de correo expirados, los elementos expirados que se encuentran en el archivo de expansión automática también se eliminarán.

- **Servicio de importación:** Puede usar el servicio de importación de Office 365 para importar archivos PST al archivo de expansión automática de un usuario. Puede importar hasta 100 GB de datos de archivos PST en el buzón de archivo del usuario.

## <a name="more-information"></a>Más información

Para obtener más información técnica sobre el archivado de expansión automática, consulte [Office 365: archivos de expansión automática de archivos de preguntas más frecuentes](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).
