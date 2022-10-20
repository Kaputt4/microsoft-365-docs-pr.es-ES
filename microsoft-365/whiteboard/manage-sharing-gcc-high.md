---
title: Administración del uso compartido para Microsoft Whiteboard en entornos de GCC High
ms.author: v-jdeweese
author: johnddeweese
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.service: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: Obtenga información sobre cómo administrar el uso compartido para Microsoft Whiteboard en entornos de GCC High.
ms.openlocfilehash: 45372ae960651493fc06f33168e94c6c613bace3
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68626739"
---
# <a name="manage-sharing-for-microsoft-whiteboard-in-gcc-high-environments"></a>Administración del uso compartido para Microsoft Whiteboard en entornos de GCC High

> [!NOTE]
> Esta guía se aplica a los entornos altos de la nube de la comunidad del gobierno de EE. UU. (GCC). La experiencia de uso compartido difiere en función del dispositivo y el cliente que se usan.

## <a name="share-in-teams-meetings"></a>Compartir en reuniones de Teams

Al compartir una pizarra en una reunión de Teams, Whiteboard crea un vínculo de uso compartido. Cualquier persona de la organización puede acceder a este vínculo. La pizarra también se comparte con cualquier usuario en el inquilino de la reunión. Las pizarras se comparten mediante vínculos que se pueden compartir con la empresa, independientemente de la configuración predeterminada. Se planea la compatibilidad con el tipo de vínculo de uso compartido predeterminado.

Durante una reunión de Teams, las cuentas de dispositivos externos y compartidos (normalmente usadas en Surface Hubs y Salas de Teams dispositivos) tienen más capacidad para la colaboración temporal. Los usuarios pueden ver y colaborar temporalmente en pizarras compartidas en una reunión, de forma similar a PowerPoint Live uso compartido.

En este caso, Whiteboard proporciona visualización y colaboración temporales en la pizarra solo durante la reunión de Teams. No se crea un vínculo de recurso compartido y Whiteboard no concede acceso al archivo.

Para habilitar este comportamiento, siga estos pasos:

1. Asegúrese de que Whiteboard está habilitado para su organización. Para obtener más información, vea [Administrar el acceso a Whiteboard](manage-whiteboard-access-gcc-high.md).

2. Con PowerShell, conéctese al inquilino y asegúrese de que el módulo de SharePoint Online se actualiza mediante la ejecución del siguiente comando:

   ```powershell
   Update-Module -Name Microsoft.Online.SharePoint.PowerShell
   ```

3. A continuación, ejecute el siguiente comando **Set-SPOTenant** :

   ```powershell
   Set-SPOTenant -AllowAnonymousMeetingParticipantsToAccessWhiteboards On
   ```

Esta configuración solo se aplica a las pizarras y reemplaza la configuración compartida anteriormente: **OneDriveLoopSharingCapability** y **CoreLoopSharingCapability**. Esa configuración ya no es aplicable y se puede omitir.

> [!NOTE]
> Esto solo se aplica a invitados y usuarios federados. No se aplica a los usuarios de reuniones anónimos en este momento.

> [!NOTE]
> Si desea que las cuentas de dispositivo compartido tengan acceso a Whiteboard en reuniones de Teams pero no a usuarios anónimos, puede deshabilitar **usuarios anónimos para que interactúen con las aplicaciones de las reuniones** mientras tienen **habilitado AllowAnonymousMeetingParticipantsToAccessWhiteboards** .

Estos cambios deben tardar aproximadamente 60 minutos en aplicarse en todo el inquilino.

|Escenario|Almacenamiento y propiedad|Configuración de uso compartido|Experiencia de uso compartido|
|---|---|---|---|
|Iniciar la pizarra desde un dispositivo móvil o de escritorio|Almacenamiento: OneDrive para la Empresa<br><br>Propietario: usuario que crea la pizarra|Habilitado|Usuarios en el inquilino: pueden crear, ver y colaborar<br><br>Usuarios externos: solo pueden ver y colaborar durante la reunión (el botón para compartir una pizarra no aparecerá para los usuarios externos)<br><br>Cuentas de dispositivo compartido: solo puede ver y colaborar durante la reunión.|
|Inicie la pizarra desde surface hub o Salas de Microsoft Teams|Aún no disponible|||

## <a name="add-as-a-tab-in-teams-channels-and-chats"></a>Agregar como pestaña en canales y chats de Teams

Al agregar una pizarra como una pestaña en un canal o chat de Teams, Whiteboard creará un vínculo de uso compartido al que pueda acceder cualquier persona de la organización.

|Escenario|Almacenamiento y propiedad|Configuración de uso compartido|Experiencia de uso compartido|
|---|---|---|---|
|Agregar la pizarra a un canal o chat desde un dispositivo móvil o de escritorio|Almacenamiento: OneDrive para la Empresa<br><br>Propietario: usuario que crea la pizarra|No aplicable|Usuarios en el inquilino: pueden iniciar, ver y colaborar<br><br>Usuarios externos: no admitidos|

## <a name="create-and-share-in-whiteboard-native-clients"></a>Creación y uso compartido en clientes nativos de Whiteboard

Al compartir una pizarra desde clientes web, de escritorio o móviles, puede elegir personas específicas. También puede crear un vínculo de uso compartido al que pueda acceder cualquier persona de la organización.

|Escenario|Almacenamiento y propiedad|Configuración de uso compartido|Experiencia de uso compartido|
|---|---|---|---|
|Creación de la pizarra desde un dispositivo móvil o de escritorio|Almacenamiento: OneDrive para la Empresa<br><br>Propietario: usuario que crea la pizarra|No aplicable|Usuarios en el inquilino: pueden compartir dentro de su organización<br><br>Usuarios externos: no se admite el uso compartido con usuarios externos en este momento|
|Crear la pizarra a partir de un Surface Hub|Almacenamiento: Local<br><br>Propietario: Ninguno|No aplicable|Usuarios en el inquilino (próximamente): el usuario podrá iniciar sesión para guardar y compartir el panel.<br><br>Usuarios externos: no se admite el uso compartido con usuarios externos en este momento|
|Creación de la pizarra a partir de Salas de Microsoft Teams|Aún no disponible|||

## <a name="see-also"></a>Vea también

[Administración del acceso a Whiteboard- GCC High](manage-whiteboard-access-gcc-high.md)

[Administración de datos para Pizarra: GCC High](manage-data-gcc-high.md)

[Administración de clientes para Whiteboard: GCC High](manage-clients-gcc-high.md)
