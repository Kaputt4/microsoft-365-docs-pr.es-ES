---
title: Implementación de La pizarra de Microsoft en dispositivos Windows 10
ms.author: v-jdeweese
author: johnddeweese
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: Obtenga información sobre cómo implementar Microsoft Whiteboard en dispositivos que ejecutan Windows 10 o versiones posteriores.
ms.openlocfilehash: bdea83d61a22ecfa3b26feecf7d7711549ace463
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367717"
---
# <a name="deploy-microsoft-whiteboard-on-windows-10-devices"></a>Implementación de La pizarra de Microsoft en dispositivos Windows 10

La pizarra se puede implementar en dispositivos que ejecutan Windows 10 o versiones posteriores mediante Microsoft Intune o Microsoft Configuration Manager (anteriormente System Center Configuration Manager). La pizarra no se admite en Windows Server.

Para implementar Whiteboard, primero debe asegurarse de que Whiteboard está habilitado para su organización. Para obtener más información, vea [Administrar el acceso a Whiteboard](manage-whiteboard-access-organizations.md).

- **Microsoft Intune mediante un modo de licencia en línea**: este proceso le permite especificar grupos de usuarios que recibirán acceso a la aplicación Whiteboard.

- **Microsoft Configuration Manager mediante la instalación y las actualizaciones manuales sin conexión**: este proceso le permite instalar Whiteboard y, a continuación, actualizarla manualmente cada 2-4 semanas.

>[!NOTE]
> Se recomienda usar Microsoft Intune. El uso de Microsoft Configuration Manager requiere que ti vuelva a empaquetar e instalar actualizaciones continuamente para garantizar que los usuarios ejecutan una versión actualizada.

## <a name="install-whiteboard-using-microsoft-intune"></a>Instalación de Whiteboard con Microsoft Intune

1. Agregue Whiteboard como una aplicación disponible mediante los pasos de este artículo: [Agregar aplicaciones de Microsoft Store a Microsoft Intune](/mem/intune/apps/store-apps-windows).

2. Asigne la aplicación a un grupo siguiendo los pasos de este artículo: [Asignar aplicaciones a grupos con Microsoft Intune](/mem/intune/apps/apps-deploy).

## <a name="install-whiteboard-using-microsoft-configuration-manager"></a>Instalación de Whiteboard con Microsoft Configuration Manager

1. Con una cuenta de administrador global, inicie sesión en el [Microsoft Store para Empresas](https://businessstore.microsoft.com).

2. En el encabezado, seleccione **Administrar**.

3. En el panel de navegación derecho, seleccione **Configuración** y, a continuación, active **Mostrar aplicaciones sin conexión**.

4. Espere entre 10 y 15 minutos para la propagación.

5. A continuación, vaya a la [aplicación Pizarra](https://businessstore.microsoft.com/store/details/microsoft-whiteboard/9mspc6mp8fm4).

6. Seleccione **Obtener la aplicación** y acepte los términos de licencia.

7. Volver a la página de la aplicación.

8. En el menú desplegable **Tipo de licencia** , seleccione **Sin conexión**.

9. Haga clic en **Administrar**.

10. Esta acción le lleva a la página de administración de inventario, que ahora ofrecerá la opción **Descargar paquete para su uso sin conexión**.

11. Elija la versión de la arquitectura y, a continuación, descárguela.

12. Tan pronto como haya descargado la aplicación, puede implementarla a través de Configuration Manager. Para crear un paquete de actualización, siga los pasos del 7 al 10 para descargar una versión más reciente y empaquetarla para Configuration Manager.

13. Para obtener más información, consulte [Instalación de aplicaciones para un dispositivo](/mem/configmgr/apps/deploy-use/install-app-for-device).

## <a name="see-also"></a>Vea también

[Administración del acceso a Whiteboard](manage-whiteboard-access-organizations.md)

[Administración de datos para Whiteboard](manage-data-organizations.md)

[Administración del uso compartido para Whiteboard](manage-sharing-organizations.md)

