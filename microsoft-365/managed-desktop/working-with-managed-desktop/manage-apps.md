---
title: Administrar aplicaciones en el escritorio administrado por Microsoft
description: Información sobre cómo actualizar las aplicaciones de línea de negocio que se implementan en dispositivos de escritorio administrados por Microsoft
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 87968e1238ee5b3dce6e569846e253dada72dd6d
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390737"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>Administrar aplicaciones de línea de negocio en el escritorio administrado por Microsoft

<!--Application management -->

Hay un par de maneras de administrar las actualizaciones de aplicaciones para las aplicaciones que haya incorporado en el escritorio administrado de Microsoft y que se hayan implementado en sus dispositivos de escritorio administrados por Microsoft. Puede realizar actualizaciones de aplicaciones en el portal de escritorio administrado de Microsoft o Intune. 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>Actualizar las aplicaciones de línea de negocio en el escritorio administrado por Microsoft

**Para actualizar las aplicaciones de línea de negocio en el portal de escritorio administrado de Microsoft**
1. Inicie sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mmdportal).
2. En **inventario**, seleccione **aplicaciones**.  
3. Seleccione la aplicación que desea actualizar y, a continuación, seleccione **Editar**.
4. En **administrar**, seleccione **propiedades**. 
5. Haga clic en **archivo de paquete de aplicaciones**y, a continuación, busque cargar un nuevo archivo de paquete de aplicaciones.
6. Seleccione **archivo de paquete de aplicaciones**.
7. Seleccione el icono de carpeta y vaya a la ubicación del archivo de aplicación actualizado. Seleccione **Abrir**. La información de la aplicación se actualiza con la información del paquete.
8. Compruebe que la versión de la **aplicación** refleja el paquete de la aplicación actualizado. 

La aplicación actualizada se implementará en los dispositivos del usuario.

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>Actualizar las aplicaciones de línea de negocio en Intune

**Para actualizar las aplicaciones de línea de negocio en Intune**
1. Inicie sesión en [Azure portal](https://azure.portal.com).
2. Seleccione **todos los servicios** > **** de Intune. Intune se encuentra en la sección **Monitoring + Management** .
3. Seleccione aplicaciones **cliente > aplicaciones**.
4. Busque y seleccione su aplicación en la lista de aplicaciones.
5. En la hoja **información general** , seleccione **propiedades**.
6. Seleccione **archivo de paquete de aplicaciones**.
7. Seleccione el icono de carpeta y vaya a la ubicación del archivo de aplicación actualizado. Seleccione **Abrir**. La información de la aplicación se actualiza con la información del paquete.
8. Compruebe que la versión de la **aplicación** refleja el paquete de la aplicación actualizado.

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>Revertir una aplicación a una versión anterior

Si se produce un error cuando se implementa una nueva versión de una aplicación, puede volver a una versión anterior. El proceso descrito aquí es para las aplicaciones donde tipo aparece como **aplicación MSI de línea de negocio de Windows** o aplicación de **windows (Win 32)-vista previa**

**Para volver a una versión anterior de una aplicación de línea de negocio**

1. Inicie sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mmdportal).
2. En **inventario**, seleccione **aplicaciones**.  
3. Seleccione la aplicación que necesita volver y, después, seleccione **Editar**.
4. En **administrar**, seleccione **propiedades**. 
    - Para las aplicaciones MSI de la **aplicación de línea de negocio de Windows** , seleccione información de la **aplicación**y, a continuación, en **omitir versión**de la aplicación, seleccione **sí**.
    - Para **Windows App (Win 32): vista previa** de aplicaciones, seleccione información de la **aplicación**, seleccione **reglas de detección**y, después, seleccione **Agregar**. 
    Si hay una regla MSI, compruebe que la **comprobación de la versión del producto MSI** esté establecida en **no**.
5. [Cargue una versión anterior del archivo de origen de la aplicación en el](../get-started/deploy-apps.md) portal de administración de escritorio administrada de Microsoft.  

