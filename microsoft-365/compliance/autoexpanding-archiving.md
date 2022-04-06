---
title: Información sobre el archivado de expansión automática
f1.keywords:
  - NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
  - Strat_O365_IP
  - M365-security-compliance
search.appverid:
  - MOE150
  - MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: 'Obtenga información sobre el archivado de expansión automática, que proporciona almacenamiento de archivo adicional para buzones de Exchange Online.'
---

# <a name="learn-about-auto-expanding-archiving"></a>Información sobre el archivado de expansión automática

En Office 365, los buzones de archivo proporcionan a los usuarios espacio de almacenamiento de buzones de correo adicional. Una vez habilitado el buzón de archivo de un usuario, hay disponible hasta 100 GB de almacenamiento adicional. En el pasado, cuando se alcanzó la cuota de almacenamiento de 100 GB, las organizaciones tuvieron que ponerse en contacto con Microsoft para solicitar espacio de almacenamiento adicional para un buzón de archivo. Ya no es así.

La característica de archivado de Microsoft 365 (denominada *archivado de expansión automática*) proporciona hasta 1,5 TB de almacenamiento adicional en buzones de archivo. Cuando se alcanza la cuota de almacenamiento en el buzón de archivo, Microsoft 365 aumenta automáticamente (e incrementalmente) el tamaño del archivo hasta que el buzón de archivo alcanza los 1,5 TB.

Para obtener instrucciones paso a paso para activar el archivado de expansión automática, consulte [Habilitar el archivado de expansión automática](enable-autoexpanding-archiving.md).

> [!NOTE]
> El archivado de expansión automática también es compatible con los buzones compartidos. Para habilitar el archivo para un buzón compartido, se requiere una licencia de ExchangeOnline (plan 2) o de ExchangeOnline (plan 1) con una licencia de Archivado de ExchangeOnline.

## <a name="how-auto-expanding-archiving-works"></a>Cómo funciona el archivado de expansión automática

Como se explicó anteriormente, se crea espacio de almacenamiento de buzones de correo adicional cuando se habilita el buzón de archivo de un usuario. Cuando se habilita el archivado de expansión automática, Microsoft 365 comprueba periódicamente el tamaño del buzón de archivo. Cuando un buzón de archivo se acerca a su límite de almacenamiento, Microsoft 365 automáticamente crea espacio de almacenamiento adicional para el archivo. Si el usuario se queda sin este espacio de almacenamiento adicional, Microsoft 365 agrega más espacio de almacenamiento al archivo del usuario. Este proceso continúa hasta que el archivo del usuario alcanza un tamaño de 1,5 TB. Este proceso se realiza automáticamente, lo que significa que los administradores no tienen que solicitar almacenamiento de archivo adicional ni administrar el archivado de expansión automática.

Esta es una introducción rápida del proceso.

![Información general sobre el proceso de archivado de expansión automática.](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. El archivado está habilitado para un buzón de usuario o un buzón compartido. Se crea un buzón de archivo con 100 GB de espacio de almacenamiento y la cuota de advertencia para el buzón de archivo se establece en 90 GB.

2. Un administrador habilita el archivado de expansión automática para el buzón. Cuando el buzón de archivo (incluida la carpeta Elementos recuperables) alcanza los 90 GB, se convierte en un archivo de expansión automática y Microsoft 365 agrega espacio de almacenamiento al archivo hasta que alcanza un tamaño máximo de 1,5 TB. El espacio de almacenamiento adicional puede tardar hasta 30 días en aprovisionarse.

   > [!NOTE]
   > Si un buzón se coloca en espera o se asigna a una directiva de retención, la cuota de almacenamiento para el buzón de archivo se aumenta a 110 GB cuando se habilita el archivado de expansión automática. Del mismo modo, la cuota de advertencia de archivo se aumenta a 100 GB.

3. Microsoft 365 agrega automáticamente más espacio de almacenamiento cuando sea necesario.

> [!IMPORTANT]
> El archivado de expansión automática solo se admite para buzones usados por usuarios individuales (o buzones compartidos) con una tasa de crecimiento que no supere 1 GB al día. El buzón de archivo de un usuario está diseñado exclusivamente para dicho usuario. No se permite el uso de registro en diario, reglas de transporte ni reglas de reenvío automático para copiar mensajes en un buzón de archivo. Microsoft se reserva el derecho de denegar el archivado adicional en los casos en los que se usa el buzón de archivo de un usuario para almacenar datos de archivo para otros usuarios o en otros casos de uso inadecuado.

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>¿Qué se mueve al espacio de almacenamiento de archivo adicional?

Para hacer un uso eficaz del almacenamiento de archivo de expansión automática, las carpetas pueden moverse. Microsoft 365 determina qué carpetas se mueven cuando se agrega almacenamiento adicional al archivo. A veces, cuando se mueve una carpeta, se crean automáticamente una o varias subcarpetas y los elementos de la carpeta original se distribuyen a estas carpetas para facilitar el proceso de movimiento. Al ver la parte de archivo de la lista de carpetas en Outlook, estas subcarpetas se muestran en la carpeta original. La convención de nomenclatura que Microsoft 365 usa para asignar un nombre a estas subcarpetas es **\<folder name\>_yyyy (creado en mmm dd, yyyy h_mm)**, donde:

- **yyyy es el** año en que se recibieron los mensajes de la carpeta.

- **mmm dd, yyyy h_m** es la fecha y hora en que la subcarpeta fue creada por Office 365, en formato UTC, según la zona horaria y la configuración regional del usuario en Outlook.

Las capturas de pantalla siguientes muestran una lista de carpetas antes y después de que los mensajes se muevan a un archivo expandido automáticamente.

 **Antes de agregar almacenamiento adicional**

![Lista de carpetas del buzón de archivo antes de aprovisionar el archivo de expansión automática.](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 **Después de agregar almacenamiento adicional**

![Lista de carpetas del buzón de archivo después de aprovisionar el archivo de expansión automática.](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> Como se ha descrito anteriormente, Microsoft 365 mueve los elementos a subcarpetas (y los denomina mediante la convención de nomenclatura descrita anteriormente) para ayudar a distribuir contenido a un archivo auxiliar. Pero es posible que no siempre se muevan elementos a subcarpetas. A veces, se puede mover una carpeta completa a un archivo auxiliar. En este caso, la carpeta conservará su nombre original.  No se mostrará en la lista de carpetas de Outlook que la carpeta se movió a un archivo auxiliar.

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>Requisitos de Outlook para acceder a los elementos de un archivo expandido automáticamente

Para acceder a los mensajes que se almacenan en un archivo expandido automáticamente, los usuarios tienen que usar uno de los siguientes clientes de Outlook:

- Outlook como parte de Aplicaciones de Microsoft 365 para empresas (anteriormente denominado Office 365 ProPlus)

- Outlook como parte de Aplicaciones de Microsoft 365 para negocios (anteriormente denominado Office 365 Empresa)

- Outlook 2016 o Outlook 2019 para Windows

- Outlook en la Web

- Outlook 2016 o Outlook 2019 para Mac

Estos son algunos aspectos a tener en cuenta al usar Outlook o Outlook en la Web para obtener acceso a los mensajes almacenados en un archivo expandido automáticamente.

- Puede tener acceso a cualquier carpeta del buzón de archivo, incluidas las que se movieron al área de almacenamiento de expansión automática.

- Si un buzón de archivo tiene al menos un área de almacenamiento expandida automáticamente, no puede eliminar una carpeta del buzón de archivo ni del archivo auxiliar. En otras palabras, después de aprovisionar un área de almacenamiento expandida automáticamente, no puede eliminar ninguna carpeta del archivo.

- Puede eliminar elementos de un área de almacenamiento expandida automáticamente. Sin embargo, no puede usar la característica Recuperar elementos eliminados para recuperar un elemento después de habilitar el archivado de expansión automática para un buzón.

- La búsqueda de archivado expandido automáticamente está disponible en Outlook para la web (OWA). De forma similar a Archivo en línea, puede buscar elementos que se movieron a un área de almacenamiento adicional. Cuando se selecciona archivo como ámbito de búsqueda en OWA, se buscarán todos los archivos (incluidos los archivos expandidos automáticamente) y sus subcarpetas correspondientes. Tenga en cuenta que no se admite la búsqueda para la característica de archivos de expansión automática en una situación de archivo solo en la nube (el buzón principal sigue siendo local).

- La búsqueda de archivos de expansión automática está disponible en Outlook para Windows en el Canal empresarial mensual. Con esta actualización, el ámbito buzón actual está disponible, lo que le permite buscar en el archivo expandido automáticamente. Tenga en cuenta que no se admite la búsqueda para la característica de archivos de expansión automática en una situación de archivo solo en la nube (el buzón principal sigue siendo local). Para obtener más información sobre esta y otras características de soporte técnico de Microsoft Search, vea [Cómo Outlook para Windows conectado a Exchange Online utiliza Búsqueda de Microsoft](https://techcommunity.microsoft.com/t5/outlook-global-customer-service/how-outlook-for-windows-connected-to-exchange-online-utilizes/ba-p/1715045). 

- Es posible que los recuentos de elementos en Outlook y los recuentos leídos o no leídos (en Outlook y Outlook en la web) en un archivo expandido automáticamente no sean precisos.

## <a name="auto-expanding-archiving-and-other-compliance-features"></a>Archivado de expansión automática y otras características de cumplimiento

En esta sección se explica la funcionalidad entre el archivado de expansión automática y otras características de cumplimiento y gobierno de datos.

- **Exhibición de documentos electrónicos:** Cuando se usa una herramienta de exhibición de documentos electrónicos, como la búsqueda de contenido o la exhibición de documentos electrónicos In-Place, también se buscan las áreas de almacenamiento adicionales de un archivo expandido automáticamente.

- **Retención:** Al poner un buzón en espera mediante herramientas como Suspensión por litigio en Exchange Online o las directivas de retención y retención de casos de exhibición de documentos electrónicos en el centro de seguridad y cumplimiento, el contenido ubicado en un archivo expandido automáticamente también se pone en espera.

- **Administración de registros de mensajería (MRM):** Si usa directivas de eliminación de MRM en Exchange Online para eliminar permanentemente los elementos de buzón expirados, también se eliminarán los elementos expirados ubicados en el archivo expandido automáticamente.

- servicio de importación de **:** Puede usar el servicio de importación de Office 365 para importar archivos PST en el archivo expandido automáticamente de un usuario. Puede importar hasta 100 GB de datos de archivos PST al buzón de archivo del usuario.

## <a name="next-steps"></a>Pasos siguientes

Para obtener más detalles técnicos sobre el archivado de expansión automática, vea[ Microsoft 365: Preguntas más frecuentes sobre la expansión automática de archivos ](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784).

Si quiere habilitar el archivado de expansión automática, vea [Habilitar el archivado de expansión automática](enable-autoexpanding-archiving.md).
