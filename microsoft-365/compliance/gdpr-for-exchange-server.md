---
title: RGPD para Exchange Server
description: Aprenda a cumplir con los requisitos de la GDPR para un servidor de intercambio local, como la retención de artículos eliminados y la recopilación automática de datos.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 7d2f482ad06f9ed44467795f310aecb2c44eea0d
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547326"
---
# <a name="gdpr-for-exchange-server"></a>RGPD para Exchange Server

Como parte de la protección de información personal, le recomendamos lo siguiente:

-   Use [Etiquetas de retención y directivas de retención](https://technet.microsoft.com/library/dd297955(v=exchg.160).aspx) en Exchange Server para implementar una directiva de ciclo de vida del correo electrónico.

-   Implemente [Information Rights Management](https://technet.microsoft.com/library/dd638140(v=exchg.160).aspx) para limitar quién tiene acceso a la información almacenada en Exchange Server.

-   Habilite [el cifrado de BitLocker](https://blogs.technet.microsoft.com/exchange/2015/10/20/enabling-bitlocker-on-exchange-servers/) en sus servidores.

## <a name="identifying-in-scope-content"></a>Identificar el contenido en el ámbito

Exchange utiliza dos depósitos de almacenamiento primarios para el contenido generado por el usuario final: buzones y carpetas públicas. El contenido almacenado en el buzón de un usuario individual está asociado de forma exclusiva a ese usuario y representa su repositorio predeterminado dentro de Exchange. Los datos almacenados en el buzón de un usuario incluyen contenido creado con Outlook, Outlook en la Web (antes conocido como Outlook Web App), Exchange ActiveSync, clientes de Skype para Empresas y otras herramientas de terceros que se conectan a los servidores de Exchange mediante POP, IMAP o Exchange Web Services (EWS). Algunos ejemplos de estos elementos son: mensajes, elementos de calendario (reuniones y citas), contactos, notas y tareas. Al eliminar el buzón de un usuario individual se elimina el contenido generado por el usuario o enviado directamente a él en el contexto de su buzón. Puede eliminar los buzones de correo de los usuarios utilizando el centro de administración de Exchange (EAC) o el cmdlet [Remove-Mailbox](https://docs.microsoft.com/powershell/module/exchange/remove-mailbox) en el Shell de administración de Exchange.
Nota: El parámetro Permanente en el cmdlet Remove-Mailbox debe usarse con cuidado ya que los datos no se pueden recuperar si se usa esta opción.

Exchange también proporciona buzones compartidos que permiten a uno o más usuarios acceder para enviar y recibir contenido que está almacenado en un buzón común. El buzón compartido es una entidad única que no está asociada a una sola cuenta. En su lugar, se concede acceso a varios usuarios para enviar, recibir y revisar el contenido de correo electrónico del buzón compartido. Los buzones compartidos se administran utilizando el centro de administración de Exchange y los mismos cmdlets que se utilizan para administrar los buzones de los usuarios habituales. Si necesita eliminar mensajes individuales de un buzón, hay diferentes opciones disponibles dependiendo de la versión de Exchange. En Exchange Server 2010 y 2013, puede usar el cmdlet de[Buscar en el buzón](https://docs.microsoft.com/powershell/module/exchange/search-mailbox) con el parámetro DeleteContent para identificar y quitar mensajes de un buzón. En Exchange Server 2016 y posteriores, es necesario utilizar la funcionalidad [New-ComplianceSearch](https://technet.microsoft.com/library/ff459253(v=exchg.160).aspx).

Las carpetas públicas son una implementación de almacenamiento compartido que no está asociada a un usuario específico. En cambio, se concede a los usuarios acceso a las carpetas públicas para generar contenido. La implementación real de las carpetas públicas varía en función de la versión de Exchange (Exchange Server 2010 utiliza una implementación diferente a la de Exchange Server 2013 y posteriores). Existen herramientas limitadas para administrar el contenido de las carpetas públicas. Las herramientas de cliente (por ejemplo, Outlook) son el mecanismo principal para administrar el contenido de las carpetas públicas. Existen cmdlets para administrar los objetos de las carpetas públicas, pero no para administrar elementos de contenido individuales dentro de la carpeta pública. Es probable que se necesite un script personalizado que aproveche los servicios web de intercambio (EWS) u otras herramientas de terceros para gestionar elementos individuales de la carpeta pública.

El requisito principal es probable que sea administrar el contenido del buzón de usuarios individuales. Este requisito se enviará fácilmente a través de las herramientas gráficas o basada en cmdlet que usa regularmente para administrar buzones. Si necesita procesar el contenido en varios buzones o tipos de recursos, [eDiscovery](https://technet.microsoft.com/library/dd298021(v=exchg.160).aspx) es el mecanismo preferido en Exchange para identificar contenido en el ámbito.

## <a name="deleted-item-retention"></a>Retención de elementos eliminados

Al eliminar mensajes individuales o elementos de un buzón de correo (no todo el buzón o el recurso de la carpeta pública en sí) se retiene el contenido en un formulario que se puede recuperar en función del valor del parámetro DeletedItemRetention de la base de datos del buzón o la base de datos de la carpeta pública. El valor predeterminado es de 14 días, pero un administrador de Exchange puede configurar este valor.

## <a name="removing-soft-deleted-and-disconnected-mailboxes"></a>Quitar buzones eliminados temporalmente y desconectados

Cuando un buzón de Exchange se desactiva, elimina o se mueve entre bases de datos (por ejemplo, como parte del balanceo de carga), el buzón se coloca en un estado de desactivación, eliminación temporal o desconexión, dependiendo de la operación. Mientras el buzón se encuentra en cualquiera de estos estados, Exchange mantiene el buzón (que incluye su contenido) basándose en el valor actual del parámetro MailboxRetention que se especifica en la base de datos de buzones. El valor predeterminado es 30 días, pero este valor se puede configurar por un administrador de Exchange. Puede utilizar el cmdlet[Remove-StoreMailbox](https://docs.microsoft.com/powershell/module/exchange/remove-storemailbox) para obligar a Exchange a eliminar (purgar) permanentemente todos los datos asociados a un buzón antes de que el periodo de retención expire de forma natural.

> [!IMPORTANT]
> Use el cmdlet Remove-StoreMailbox con cuidado, ya que llevará a una pérdida irrecuperable de datos del buzón de correo de destino. 

## <a name="on-prem-to-cloud-migrations"></a>Migración de un entorno local a la nube

Mientras se migran los datos de Exchange Server a Exchange Online, los datos migrados pueden seguir residiendo en el Exchange Server local de origen en un formato recuperable por un administrador de Exchange. De manera predeterminada, estos datos se eliminarán automáticamente de la base de datos en un plazo de 30 días (consulte la sección anterior sobre la eliminación de buzones de correo electrónico borrados y desconectados).

## <a name="automatic-data-collection-reported-to-microsoft-by-exchange-server"></a>Recolección de datos automática notificada a Microsoft por Exchange Server

Los servidores de Exchange implementados en entornos locales no proporcionan ningún tipo de captura automática de datos de usuarios finales o informes a Microsoft. Los servidores de Exchange que tienen los informes de volcado de memoria de Watson habilitados en el sistema operativo Windows pueden recibir contenidos de memoria limitados en el momento en que se crea el informe de bloqueo.
