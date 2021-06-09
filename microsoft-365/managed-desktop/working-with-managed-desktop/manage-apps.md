---
title: Administrar aplicaciones en Escritorio administrado de Microsoft
description: Información sobre cómo actualizar aplicaciones de línea de negocio que se implementan en Escritorio administrado de Microsoft dispositivos
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1a6b91ab5b4523f4b980dab0c25af41a9d614189
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600687"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>Administrar aplicaciones de línea de negocio en el Escritorio administrado de Microsoft

<!--Application management -->

Hay un par de formas de administrar las actualizaciones de aplicaciones para las aplicaciones que has incorporado a Escritorio administrado de Microsoft e implementadas en tus dispositivos Escritorio administrado de Microsoft dispositivos. Puedes realizar actualizaciones de aplicaciones en Escritorio administrado de Microsoft portal o Intune. 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>Actualizar aplicaciones de línea de negocio en Escritorio administrado de Microsoft

**Para actualizar las aplicaciones de línea de negocio en Escritorio administrado de Microsoft portal**
1. Inicie sesión en [Escritorio administrado de Microsoft portal de administración](https://aka.ms/mmdportal).
2. En **Inventario,** seleccione **Aplicaciones**.  
3. Selecciona la aplicación que quieres actualizar y, a continuación, selecciona **Editar**.
4. En **Administrar**, seleccione **Propiedades**. 
5. Haz **clic en Archivo de paquete de** la aplicación y, a continuación, busca para cargar un nuevo archivo de paquete de la aplicación.
6. Seleccione **Archivo de paquete de aplicación**.
7. Selecciona el icono de carpeta y busca la ubicación del archivo de la aplicación actualizado. Seleccione **Abrir**. La información de la aplicación se actualiza con la información del paquete.
8. Comprueba que **la versión de la aplicación** refleja el paquete de la aplicación actualizado. 

La aplicación actualizada se implementará en los dispositivos del usuario.

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>Actualizar aplicaciones de línea de negocio en Intune

**Para actualizar las aplicaciones de línea de negocio en Intune**
1. Inicie sesión en [Azure Portal](https://portal.azure.com).
2. Seleccione **Todos los servicios**  >  **intune**. Intune se encuentra en la **sección Supervisión y** administración.
3. Seleccione **Aplicaciones cliente > aplicaciones**.
4. Busca y selecciona la aplicación en la lista de aplicaciones.
5. En la **hoja Información** general, seleccione **Propiedades**.
6. Seleccione **Archivo de paquete de aplicación**.
7. Selecciona el icono de carpeta y busca la ubicación del archivo de la aplicación actualizado. Seleccione **Abrir**. La información de la aplicación se actualiza con la información del paquete.
8. Comprueba que **la versión de la aplicación** refleja el paquete de la aplicación actualizado.

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>Revertir una aplicación a una versión anterior

Si se encuentra un error cuando se implementa una nueva versión de una aplicación, puedes revertir a una versión anterior. El proceso Windows descrito aquí es para aplicaciones donde el tipo aparece como una aplicación de línea de negocio **msi** o una aplicación Windows **(Win 32) - versión preliminar**

**Para revertir una aplicación de línea de negocio a una versión anterior**

1. Inicie sesión en [Escritorio administrado de Microsoft portal de administración](https://aka.ms/mmdportal).
2. En **Inventario,** seleccione **Aplicaciones**.  
3. Selecciona la aplicación que necesitas revertir y, a continuación, selecciona **Editar**.
4. En **Administrar**, seleccione **Propiedades**. 
    - Para Windows aplicaciones de línea de negocio **MSI,** seleccione Información de la aplicación **y,** a continuación, en **Omitir** versión de la aplicación, **seleccione Sí**.
    - Para **Windows aplicación (Win 32):** vista previa de aplicaciones, seleccione **Información** de la aplicación, seleccione Reglas de detección **y,** a continuación, **seleccione Agregar**. 
    Si hay una regla MSI, compruebe que la comprobación **de la** versión del producto MSI está establecida en **No**.
5. [Upload una versión anterior del archivo de origen de la aplicación](../get-started/deploy-apps.md) a Escritorio administrado de Microsoft portal de administración.  

