---
title: Más información sobre los buzones de archivo para Microsoft Purview
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Más información sobre los buzones de archivo para proporcionar almacenamiento adicional en el buzón de correo.
ms.openlocfilehash: 57de7c7791615e8587222de992588f1923348059
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66621257"
---
# <a name="learn-about-archive-mailboxes"></a>Más información sobre buzones de archivo

El archivado de buzones en Microsoft 365 (también denominado *archivado local*) proporciona a los usuarios espacio de almacenamiento adicional en el buzón de correo. Después de activar los buzones de archivo, el buzón actual de un usuario se convierte en su *buzón principal* y se crea un buzón adicional, denominado *buzón de archivo*. Ambos buzones se consideran el buzón de un usuario para las características de cumplimiento, como la búsqueda de contenido en el portal de cumplimiento de Microsoft Purview, la retención de Microsoft 365 y la suspensión legal.

Los usuarios pueden acceder y almacenar mensajes en sus buzones de archivo mediante Outlook y Outlook en la Web. Los usuarios también pueden mover o copiar mensajes entre su buzón de correo principal y el buzón de archivo. También pueden recuperar elementos eliminados de la carpeta de Elementos recuperables en su buzón de archivo mediante la herramienta Recuperar elementos eliminados.

## <a name="managing-archive-mailboxes-with-messaging-records-management-mrm"></a>Administración de buzones de archivo con administración de registros de mensajería (MRM)

Los mensajes también se pueden mover al buzón de archivo mediante la [directiva de retención predeterminada de Exchange](/exchange/security-and-compliance/messaging-records-management/default-retention-policy) desde la administración de registros de mensajería (MRM). Esta directiva predeterminada se asigna automáticamente a todos los buzones y hace lo siguiente:

  - Mueve los elementos que tienen dos años o más del buzón principal del usuario a su buzón de archivo.

  - Mueve los elementos que tienen 14 días o más de la carpeta Elementos recuperables del buzón de correo principal del usuario a la carpeta Elementos recuperables del buzón de archivo.

Puede personalizar la directiva de MRM de su organización con [etiquetas de retención](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies). Para obtener una configuración de ejemplo, consulte [Configurar una directiva de archivo y eliminación de buzones en su organización](set-up-an-archive-and-deletion-policy-for-mailboxes.md).

> [!NOTE]
> MRM, como las directivas y etiquetas de retención de Microsoft 365, también puede eliminar automáticamente los correos electrónicos después de un período especificado. Como tecnología anterior a la retención de Microsoft 365, MRM sigue trabajando en paralelo con las directivas y etiquetas de retención de Microsoft Purview. Para más información, consulte [Usar directivas y etiquetas de retención en lugar de características anteriores](retention.md#use-retention-policies-and-retention-labels-instead-of-older-features).

## <a name="auto-expanding-archiving"></a>Archivado de expansión automática 

Una vez habilitado el buzón de archivo de un usuario, hay disponible hasta 100 GB de almacenamiento adicional. Si los usuarios necesitan más espacio de almacenamiento, habilite el archivado de expansión automática para proporcionar hasta 1,5 TB de almacenamiento adicional en los buzones de archivo. Para más información, consulte [Más información sobre el archivado de expansión automática](autoexpanding-archiving.md).

## <a name="licensing"></a>Licencias

Para obtener una lista de licencias de Outlook que admiten buzones de archivo, consulte las referencias al archivado local en [Requisitos de licencia de Outlook para características de Exchange](https://support.microsoft.com/office/46b6b7c5-c3ca-43e5-8424-1e2807917c99).

## <a name="next-steps"></a>Pasos siguientes

Consulte [Habilitación de buzones de archivo en el portal de cumplimiento de Microsoft Purview](enable-archive-mailboxes.md)
