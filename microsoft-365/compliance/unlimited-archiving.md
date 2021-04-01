---
title: Información general sobre el archivado ilimitado
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
description: Obtenga información sobre el archivado de expansión automática, que proporciona almacenamiento de archivo ilimitado para buzones de Exchange Online.
ms.openlocfilehash: d61d3649ed65a93298928cced21180bbeca6aa95
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476271"
---
# <a name="overview-of-unlimited-archiving"></a>Información general sobre el archivado ilimitado

En Office 365, los buzones de archivo proporcionan a los usuarios espacio de almacenamiento de buzones adicional. Una vez habilitado el buzón de archivo de un usuario, hay disponible hasta 100 GB de almacenamiento adicional. En el pasado, cuando se alcanzó la cuota de almacenamiento de 100 GB, las organizaciones tuvieron que ponerse en contacto con Microsoft para solicitar espacio de almacenamiento adicional para un buzón de archivo. Ese ya no es el caso.

La característica de archivado ilimitado en Microsoft 365 (denominado *archivado* de expansión automática) proporciona almacenamiento adicional en buzones de archivo. Cuando se alcanza la cuota de almacenamiento en el buzón de archivo, Microsoft 365 aumenta automáticamente el tamaño del archivo, lo que significa que los usuarios no se quedas sin espacio de almacenamiento del buzón y los administradores no tendrán que solicitar almacenamiento adicional para los buzones de archivo.

Para obtener instrucciones paso a paso para activar el archivado de expansión automática, vea [Enable unlimited archiving](enable-unlimited-archiving.md).

> [!NOTE]
> El archivado de expansión automática también es compatible con los buzones compartidos. Para habilitar el archivo de un buzón compartido, se requiere una licencia de Exchange Online Plan 2 o una licencia de Exchange Online Plan 1 con una Archivado de Exchange Online de correo.

## <a name="how-auto-expanding-archiving-works"></a>Cómo funciona el archivado de expansión automática

Como se explicó anteriormente, se crea espacio de almacenamiento de buzones de correo adicional cuando se habilita el buzón de archivo de un usuario. Cuando se habilita el archivado de expansión automática, Microsoft 365 comprueba periódicamente el tamaño del buzón de archivo. Cuando un buzón de archivo se acerca a su límite de almacenamiento, Microsoft 365 crea automáticamente espacio de almacenamiento adicional para el archivo. Si el usuario se queda sin este espacio de almacenamiento adicional, Microsoft 365 agrega más espacio de almacenamiento al archivo del usuario. Este proceso se realiza automáticamente, lo que significa que los administradores no tienen que solicitar almacenamiento de archivo adicional ni administrar el archivado de expansión automática.

Este es un resumen rápido del proceso.

![Información general sobre el proceso de archivado de expansión automática](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. El archivado está habilitado para un buzón de usuario o un buzón compartido. Se crea un buzón de archivo con 100 GB de espacio de almacenamiento y la cuota de advertencia para el buzón de archivo se establece en 90 GB.

2. Un administrador habilita el archivado de expansión automática para el buzón. Cuando el buzón de archivo (incluida la carpeta Elementos recuperables) alcanza los 90 GB, se convierte en un archivo de expansión automática y Microsoft 365 agrega espacio de almacenamiento al archivo. El espacio de almacenamiento adicional puede tardar hasta 30 días en aprovisionarse.

   > [!NOTE]
   > Si un buzón se coloca en espera o se asigna a una directiva de retención, la cuota de almacenamiento para el buzón de archivo aumenta a 110 GB cuando se habilita el archivado de expansión automática. Del mismo modo, la cuota de advertencia de archivo se aumenta a 100 GB.

3. Microsoft 365 agrega automáticamente más espacio de almacenamiento cuando sea necesario.

> [!IMPORTANT]
> El archivo de expansión automática solo se admite para buzones usados para usuarios individuales (o buzones compartidos) con una tasa de crecimiento que no supere 1 GB al día. El buzón de archivo de un usuario está diseñado exclusivamente para dicho usuario. No se permite usar el registro en diario, las reglas de transporte o las reglas de reenvío automático para copiar mensajes a un buzón de archivo. Microsoft se reserva el derecho de denegar el archivado ilimitado en los casos en los que el buzón de archivo de un usuario se usa para almacenar datos de archivo para otros usuarios o en otros casos de uso inadecuado.

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>¿Qué se mueve al espacio de almacenamiento de archivo adicional?

Para hacer un uso eficaz del almacenamiento de archivo de expansión automática, las carpetas pueden moverse. Microsoft 365 determina qué carpetas se mueven cuando se agrega almacenamiento adicional al archivo. A veces, cuando se mueve una carpeta, se crean automáticamente una o varias subcarpetas y los elementos de la carpeta original se distribuyen a estas carpetas para facilitar el proceso de movimiento. Al ver la parte de archivo de la lista de carpetas en Outlook, estas subcarpetas se muestran en la carpeta original.  La convención de nomenclatura que Microsoft 365 usa para asignar el nombre a estas subcarpetas es _yyyy (Creado en **\<folder name\> mmm dd, yyyy h_mm),** donde:

- **yyyy es el** año en que se recibieron los mensajes de la carpeta.

- **mmm dd, yyyy h_m** es la fecha y hora en que Office 365 creó la subcarpeta, en formato UTC, en función de la zona horaria y la configuración regional del usuario en Outlook.

Las capturas de pantalla siguientes muestran una lista de carpetas antes y después de que los mensajes se mueven a un archivo expandido automáticamente.

 **Antes de agregar almacenamiento adicional**

![Lista de carpetas del buzón de archivo antes de aprovisionar el archivo de expansión automática](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 **Después de agregar almacenamiento adicional**

![Lista de carpetas del buzón de archivo después de aprovisionar el archivo de expansión automática](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> Como se ha descrito anteriormente, Microsoft 365 mueve elementos a subcarpetas (y los nombra mediante la convención de nomenclatura descrita anteriormente) para ayudar a distribuir contenido a un archivo auxiliar. Pero es posible que no siempre se muevan elementos a subcarpetas. A veces, se puede mover una carpeta completa a un archivo auxiliar. En este caso, la carpeta conservará su nombre original.  No se mostrará en la lista de carpetas de Outlook que la carpeta se movió a un archivo auxiliar.

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>Requisitos de Outlook para obtener acceso a elementos en un archivo expandido automáticamente

Para obtener acceso a los mensajes almacenados en un archivo expandido automáticamente, los usuarios deben usar uno de los siguientes clientes de Outlook:

- Outlook 2016 o Outlook 2019 para Windows

- Outlook en la Web

- Outlook 2016 o Outlook 2019 para Mac

Estos son algunos aspectos a tener en cuenta al usar Outlook o Outlook en la web para obtener acceso a los mensajes almacenados en un archivo expandido automáticamente.

- Puede tener acceso a cualquier carpeta del buzón de archivo, incluidas las que se movieron al área de almacenamiento expandida automáticamente.

- La búsqueda de archivado expandido automáticamente está disponible en Outlook para la web (OWA). De forma similar a Archivo en línea, puede buscar elementos que se movieron a un área de almacenamiento adicional. Cuando se selecciona archivo como ámbito de búsqueda en OWA, se buscarán todos los archivos (incluidos los archivos expandido automáticamente) y sus subcarpetas correspondientes.

- La búsqueda de archivo expandida automáticamente está disponible en El escritorio de Outlook en canal actual (versión preliminar). Dentro de esta vista previa, el ámbito buzón actual está disponible, lo que le permite buscar en el archivo expandido automáticamente. Para obtener más información acerca de esta y otras características de soporte técnico de Microsoft [Search,](https://techcommunity.microsoft.com/t5/outlook-global-customer-service/how-outlook-for-windows-connected-to-exchange-online-utilizes/ba-p/1715045)vea How Outlook for Windows connected to Exchange Online use Microsoft Search . 

- Es posible que los recuentos de elementos en Outlook y recuentos de lectura y lectura (en Outlook y Outlook en la web) en un archivo expandido automáticamente no sean precisos.

- Puede eliminar elementos de una subcarpeta que apunta a un área de almacenamiento expandida automáticamente, pero la carpeta en sí no se puede eliminar.

- No puede usar la característica Recuperar elementos eliminados para recuperar un elemento que se eliminó de un área de almacenamiento expandida automáticamente.

## <a name="auto-expanding-archiving-and-other-compliance-features"></a>Ampliación automática del archivado y otras características de cumplimiento

En esta sección se explica la funcionalidad entre el archivado de expansión automática y otras características de cumplimiento y gobierno de datos.

- **Exhibición de documentos electrónicos:** Cuando se usa una herramienta de exhibición de documentos electrónicos, como la búsqueda de contenido o la exhibición de documentos electrónicos In-Place, también se buscan las áreas de almacenamiento adicionales de un archivo expandido automáticamente.

- **Retención:** Cuando se pone un buzón en espera mediante herramientas como retención por juicio en Exchange Online o retención de casos de exhibición de documentos electrónicos y directivas de retención en el centro de seguridad y cumplimiento, el contenido ubicado en un archivo expandido automáticamente también se pone en espera.

- **Administración de registros de mensajería (MRM):** Si usa directivas de eliminación de MRM en Exchange Online para eliminar permanentemente elementos de buzón expirados, también se eliminarán los elementos expirados ubicados en el archivo expandido automáticamente.

- **Servicio de importación:** Puede usar el servicio de importación de Office 365 para importar archivos PST al archivo expandido automáticamente de un usuario. Puede importar hasta 100 GB de datos de archivos PST al buzón de archivo del usuario.

## <a name="more-information"></a>Más información

Para obtener más detalles técnicos sobre el archivado de expansión automática, vea [Microsoft 365: Preguntas](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784)más frecuentes sobre la expansión automática de archivos .
