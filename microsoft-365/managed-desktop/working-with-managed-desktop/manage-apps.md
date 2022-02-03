---
title: Administrar aplicaciones en Microsoft Managed Desktop
description: Información sobre cómo actualizar aplicaciones de línea de negocio que se implementan en dispositivos de Escritorio administrado de Microsoft
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: a51be2521924164a8c90a51fcf99328ecf511877
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2022
ms.locfileid: "62322559"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>Administrar aplicaciones de línea de negocio en el Escritorio administrado de Microsoft

<!--Application management -->

Hay un par de maneras de administrar las actualizaciones de aplicaciones e implementarlas en los dispositivos de Escritorio administrado de Microsoft. Puede realizar actualizaciones de aplicaciones en el portal de Escritorio administrado de Microsoft o Intune.

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>Actualizar aplicaciones de línea de negocio en Microsoft Managed Desktop

**Para actualizar las aplicaciones de línea de negocio en el portal de Escritorio administrado de Microsoft:**

1. Inicie sesión en [el portal de administración de Escritorio administrado de Microsoft](https://aka.ms/mmdportal).
1. En **Inventario**, selecciona **Aplicaciones**.  
1. Selecciona la aplicación que quieres actualizar y, a continuación, selecciona **Editar**.
1. En **Administrar**, seleccione **Propiedades**.
1. Selecciona **Archivo de paquete de la** aplicación y, a continuación, busca para cargar un nuevo archivo de paquete de aplicación.
1. Seleccione **Archivo de paquete de la aplicación**.
1. Selecciona el icono de carpeta y busca la ubicación del archivo de la aplicación actualizado. Seleccione **Abrir**. La información de la aplicación se actualiza con la información del paquete.
1. Comprueba que **la versión de la aplicación** refleja el paquete de la aplicación actualizado.

La aplicación actualizada se implementará en los dispositivos del usuario.

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>Actualizar aplicaciones de línea de negocio en Intune

**Para actualizar las aplicaciones de línea de negocio en Intune:**

1. Inicie sesión en [Azure Portal](https://portal.azure.com).
2. Seleccione **Todos los** **serviciosIntune** > . Intune se encuentra en la **sección Supervisión y** administración.
3. Selecciona **Aplicaciones cliente > aplicaciones**.
4. Busca y selecciona la aplicación en la lista de aplicaciones.
5. En la **sección Información** general, seleccione **Propiedades**.
6. Seleccione **Archivo de paquete de la aplicación**.
7. Selecciona el icono de carpeta y busca la ubicación del archivo de la aplicación actualizado. Seleccione **Abrir**. La información de la aplicación se actualiza con la información del paquete.
8. Comprueba que **la versión de la aplicación** refleja el paquete de la aplicación actualizado.

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>Revertir una aplicación a una versión anterior

Cuando se implementa una nueva versión de una aplicación y se encuentra un error, puedes revertir a una versión anterior. El proceso Windows que se describe a continuación es para aplicaciones donde el tipo aparece como una aplicación de línea de negocio **msi** o una aplicación Windows **(Win 32) - versión preliminar**

**Para revertir una aplicación de línea de negocio a una versión anterior:**

1. Inicie sesión en [el portal de administración de Escritorio administrado de Microsoft](https://aka.ms/mmdportal).
2. En **Inventario**, selecciona **Aplicaciones**.  
3. Selecciona la aplicación que necesitas revertir y, a continuación, selecciona **Editar**.
4. En **Administrar**, seleccione **Propiedades**.
    - Para **Windows aplicaciones de la línea de negocio MSI**, selecciona Información de la aplicación **y, a** continuación, en **Ignorar** versión de la aplicación, selecciona **Sí**.
    - For **Windows app (Win 32): preview** apps, select **App information**, select **Detection rules**, and then select **Add**.
    Si hay una regla MSI, compruebe que la comprobación **de la** versión del producto MSI está establecida en **No**.
5. [Upload una versión anterior del archivo de origen de la aplicación](../get-started/deploy-apps.md) al portal de administración de escritorio administrado de Microsoft.  
