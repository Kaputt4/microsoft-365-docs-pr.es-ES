---
title: 'Migrar archivos de Google a Microsoft 365 para empresas '
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Aprende a migrar archivos de Google a Microsoft 365 para empresas mediante Mover.
ms.openlocfilehash: 6feabff7e36e84f7dba56e74333648325cf43920
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913579"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>Migrar archivos de Google a Microsoft 365 para empresas 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

Cuando pases a Microsoft 365 para empresas, querrás migrar los archivos desde Google Drive. Puedes usar la aplicación Mover para mover archivos de unidades personales y compartidas. Para obtener más información, vea [Mover Cloud Migration](/sharepointmigration/mover-plan-migration).

> [!NOTE]
> Mover realizará una copia de los archivos y moverá las copias a Microsoft 365 para empresas. Los archivos originales también permanecerán en Google Drives.

## <a name="before-you-start"></a>Antes de comenzar

Todos los usuarios deben haber iniciado sesión en Microsoft 365 para empresas y configurar sus OneDrive para la Empresa. Para ello, vaya a [office.com](https://office.com), inicie sesión con su Microsoft 365 para empresas y, a continuación, elija OneDrive.

## <a name="try-it"></a>¿Se atreve?

### <a name="install-mover"></a>Instalar Mover

1. Inicie sesión en la consola de administración de Google Workspace [en admin.google.com](https://admin.google.com).

1. Elija **Aplicaciones**  >  **Google Workspace Marketplace aplicaciones** Agregar aplicación a la lista de instalación de  >  **dominio**.

1. Busque Mover y selecciónelo.

1. Elija **Instalación de dominio** y, a **continuación, Continuar**.

1. Revise los permisos, active la casilla para aceptar los términos y, a continuación, **seleccione Permitir**, elija **Siguiente** y, a continuación, **Listo**.

### <a name="create-connectors-and-run-the-migration"></a>Crear conectores y ejecutar la migración

1. Volver a las **aplicaciones de Google Workspace Marketplace**.
1. Actualiza el explorador y selecciona la **aplicación Mover.**
1. Desplácese hacia abajo y elija el vínculo de navegación universal.
1. Seleccione **Autorizar nuevo conector,** busque **G Suite (administrador)** y elija **Autorizar**.
1. Cambie el **nombre para** mostrar , si lo desea, seleccione **Autorizar**.
1. Elija una cuenta de administrador de Google, revise los permisos y, a continuación, **seleccione Permitir**.

    Mover muestra el número de unidades de equipo y unidades de usuario detectadas. 

1. En **Seleccionar destino,** elija **Autorizar nuevo** **conector, busque Office 365** y seleccione **Autorizar**.
1. Para conceder permisos a la aplicación Mover en tu Azure Active Directory, ve a [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).
1. Seleccione **Office 365 Mover,** **Permisos,** **Conceder consentimiento de administrador para su empresa**.
1. Elija su cuenta, revise los permisos y seleccione **Aceptar**.
1. Elija **Propiedades** y compruebe que **la asignación de usuario necesaria está** activada.
1. Vuelva a la aplicación Mover, cambie **el** nombre para mostrar , si lo desea, elija **Autorizar** y, a continuación, seleccione una cuenta de administrador de Microsoft.

    Mover le informará sobre el número de sitios SharePoint Online (o SPO) y los usuarios que ha detectado.
1. Elija **Continuar configuración de migración,** agregar **usuarios** y, a continuación, detectar automáticamente y **agregar usuarios**.

    La aplicación Mover intentará asignar unidades de la ruta de origen en Google, a la ruta de destino en Microsoft 365. 

    Si una unidad no se asigna automáticamente, agregue su ruta de destino a un archivo CSV, que usaremos más adelante para migrar la unidad compartida a una biblioteca SharePoint documentos. 

1. En este caso, hemos agregado un sitio SharePoint llamado Archivos migrados y hemos tomado nota de la dirección URL de la página de documentos. 
1. A continuación, creamos un archivo CSV con el formato de Ruta de origen, Ruta de destino y Etiquetas. 

    Para obtener más [información, vea aka.ms/movercsv](/sharepointmigration/mover-create-migration-csv).

    Al agregar la dirección URL de ruta de destino, quite todo después de Documentos compartidos. Por ejemplo, esta dirección URL completa no funciona: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    Cambie el valor a `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`.

1. Una vez que el archivo CSV esté listo, seleccione **Acciones de migración**, **Agregar** a migración , Elija un archivo **para cargar**.
1. Navegue hasta el archivo CSV, selecciónelo y, a continuación, elija **Abrir**.
1. Seleccione las unidades de usuario cuyos archivos desea migrar y, a continuación, **elija Iniciar la migración de usuarios**.
1. Revise la información de migración, elija cuándo iniciar la migración, acepte los Términos **y condiciones** y, a continuación, **seleccione Continuar**.

La aplicación Mover te informará cuando se complete el proceso de migración.