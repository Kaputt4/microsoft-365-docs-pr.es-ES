---
title: Administración del uso compartido para La pizarra de Microsoft
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
description: Obtenga información sobre cómo administrar el uso compartido para La pizarra de Microsoft.
ms.openlocfilehash: aeb6da3d6bd66c02468ff19efa072af4d7084389
ms.sourcegitcommit: d0557f757cfa48330ed57e966033891d10f03688
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2022
ms.locfileid: "68492516"
---
# <a name="manage-sharing-for-microsoft-whiteboard"></a>Administración del uso compartido para La pizarra de Microsoft

La experiencia de uso compartido difiere en función de si se encuentra en una reunión de Teams, si usa un dispositivo compartido o si la configuración de uso compartido de nivel de inquilino está habilitada. Los siguientes escenarios solo se aplican a las nuevas pizarras creadas después de que Whiteboard cambie al uso de OneDrive para la Empresa almacenamiento. No hay ningún cambio en los paneles creados anteriormente todavía almacenados en Azure.

## <a name="share-in-teams-meetings"></a>Compartir en reuniones de Teams

Al compartir una pizarra en una reunión de Teams, Whiteboard crea un vínculo de uso compartido. Cualquier persona de la organización puede acceder a este vínculo. La pizarra también se comparte con cualquier usuario en el inquilino de la reunión. Las pizarras se comparten mediante vínculos que se pueden compartir con la empresa, independientemente de la configuración predeterminada. Se planea la compatibilidad con el tipo de vínculo de uso compartido predeterminado.

Hay más capacidad para la colaboración temporal por parte de cuentas de dispositivos externos y compartidos durante una reunión de Teams. Los usuarios pueden ver y colaborar temporalmente en pizarras compartidas en una reunión, de forma similar a PowerPoint Live uso compartido.

En este caso, Whiteboard proporciona visualización y colaboración temporales en la pizarra solo durante la reunión de Teams. No se crea un vínculo de recurso compartido y Whiteboard no concede acceso al archivo.

Para habilitar este comportamiento, siga estos pasos:

1. Asegúrese de que Whiteboard está habilitado para su organización. Para obtener más información, vea [Administrar el acceso a Whiteboard](manage-whiteboard-access-organizations.md).

2. Con PowerShell, conéctese al inquilino y asegúrese de que el módulo de SharePoint Online se actualiza mediante la ejecución del siguiente comando:

   ```powershell
   Update-Module -Name Microsoft.Online.SharePoint.PowerShell
   ```

3. A continuación, ejecute el siguiente comando **Set-SPOTenant** :

   ```powershell
   Set-SPOTenant -AllowAnonymousMeetingParticipantsToAccessWhiteboards On
   ```

4. Asegúrese de que la configuración de reunión de Teams **Usuarios anónimos pueden interactuar con aplicaciones en reuniones** está habilitada. Si la ha deshabilitado, los usuarios anónimos (en lugar de invitados o usuarios federados) no tendrán acceso a la pizarra durante la reunión.

Esta configuración solo se aplica a las pizarras y reemplaza la configuración compartida anteriormente: **OneDriveLoopSharingCapability** y **CoreLoopSharingCapability**. Esa configuración ya no es aplicable y se puede omitir.

> [!NOTE]
> De forma predeterminada, la configuración de reunión de Teams **Usuarios anónimos pueden interactuar con aplicaciones en reuniones** está habilitada. Si la ha deshabilitado, los usuarios anónimos (en lugar de invitados o usuarios federados) no tendrán acceso a la pizarra durante la reunión.

Estos cambios deben tardar aproximadamente 60 minutos en aplicarse en todo el inquilino.

|Escenario|Almacenamiento y propiedad|Configuración de uso compartido|Experiencia de uso compartido|
|---|---|---|---|
|Iniciar la pizarra desde un dispositivo móvil o de escritorio|Almacenamiento: OneDrive para la Empresa<br><br>Propietario: usuario que crea la pizarra|Habilitado|Usuarios en el inquilino: pueden crear, ver y colaborar<br><br>Usuarios externos: solo pueden ver y colaborar durante la reunión (el botón para compartir una pizarra no aparecerá para los usuarios externos)<br><br>Cuentas de dispositivo compartido: solo puede ver y colaborar durante la reunión.|
|Iniciar la pizarra desde un dispositivo móvil o de escritorio|Almacenamiento: OneDrive para la Empresa<br><br>Propietario: usuario que crea la pizarra|Deshabilitada|Usuarios en el inquilino: pueden iniciar, ver y colaborar<br><br>Usuarios externos: no se puede ver ni colaborar<br><br>Cuentas de dispositivo compartido: no se puede ver ni colaborar|
|Inicie la pizarra desde surface hub o Salas de Microsoft Teams|Almacenamiento: Azure (los archivos de pizarra se moverán a OneDrive para la Empresa en el futuro)<br><br>Propietario: Participante de la reunión|No aplicable|Usuarios en el inquilino: pueden iniciar, ver y colaborar<br><br>Usuarios externos: solo pueden ver y colaborar durante la reunión.<br><br> Cuentas de dispositivo compartido: solo puede ver y colaborar durante la reunión.|

> [!NOTE]
> Si una pizarra se almacena en OneDrive y ya está asociada a una reunión, no se puede iniciar en un dispositivo Surface Hub o Salas de Microsoft Teams. Un usuario autenticado en otro dispositivo tendrá que hacerlo. Tenemos previsto habilitar esta funcionalidad en una versión futura.

## <a name="add-as-a-tab-in-teams-channels-and-chats"></a>Agregar como pestaña en canales y chats de Teams

Al agregar una pizarra como una pestaña en un canal o chat de Teams, Whiteboard creará un vínculo de uso compartido al que pueda acceder cualquier persona de la organización.

|Escenario|Almacenamiento y propiedad|Configuración de uso compartido|Experiencia de uso compartido|
|---|---|---|---|
|Agregar la pizarra a un canal o chat desde un dispositivo móvil o de escritorio|Almacenamiento: OneDrive para la Empresa<br><br>Propietario: usuario que crea la pizarra|No aplicable (solo se aplica a reuniones)|Usuarios en el inquilino: pueden iniciar, ver y colaborar<br><br>Usuarios externos: no admitidos<br><br>Invitados de Teams: no compatible<br><br>Cuentas de dispositivo compartido: no aplicables|

## <a name="create-and-share-in-whiteboard-native-clients"></a>Creación y uso compartido en clientes nativos de Whiteboard

Al compartir pizarras desde clientes web, de escritorio o móviles, puede elegir personas específicas. También puede crear un vínculo de uso compartido al que pueda acceder cualquier persona de la organización.

> [!NOTE]
> El uso compartido externo durante una reunión de Teams aún no está disponible, pero se agregará en una versión futura.

|Escenario|Almacenamiento y propiedad|Configuración de uso compartido|Experiencia de uso compartido|
|---|---|---|---|
|Creación de la pizarra desde un dispositivo móvil o de escritorio|Almacenamiento: OneDrive para la Empresa<br><br>Propietario: usuario que crea la pizarra|No aplicable (solo se aplica a reuniones)|Usuarios en el inquilino: pueden compartir dentro de su organización<br><br>Usuarios externos: no se admite el uso compartido con usuarios externos en este momento|
|Crear la pizarra a partir de un Surface Hub|Almacenamiento: Local<br><br>Propietario: Ninguno (a menos que el usuario inicie sesión para guardar y compartir el panel, lo que se guarda en OneDrive para la Empresa. El uso compartido fácil se agregará de nuevo en el futuro.|No aplicable (solo se aplica a reuniones)|Usuarios en el inquilino: el usuario debe iniciar sesión para guardar y compartir el panel (el recurso compartido fácil se agregará en el futuro).<br><br>Usuarios externos: no se admite el uso compartido con usuarios externos en este momento fuera de una reunión de Teams|
|Creación de la pizarra a partir de Salas de Microsoft Teams|Todavía no se admite|No aplicable (solo se aplica a reuniones)|Todavía no se admite|

## <a name="see-also"></a>Vea también

[Administración del acceso a Whiteboard](manage-whiteboard-access-organizations.md)

[Administración de datos para Whiteboard](manage-data-organizations.md)

[Requisitos de red para Microsoft Defender de Cloud Apps](/defender-cloud-apps/network-requirements)

[Implementación de pizarra en Windows](deploy-on-windows-organizations.md)
