---
title: Usar OneDrive Learning interoperabilidad de herramientas de OneDrive Learning
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Cree y cale las asignaciones, cree y cura el contenido del curso y colabore en archivos en tiempo real con la nueva OneDrive Learning Tools Interoperability App.
ms.openlocfilehash: 0e437ed4b05b9968ee1e853f668787eed5351fb5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2021
ms.locfileid: "53257049"
---
# <a name="use-microsoft-onedrive-lti-with-canvas"></a>Usar Microsoft OneDrive LTI con Canvas

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

## <a name="integrate-with-canvas"></a>Integrar con Canvas

La persona que realiza esta integración debe ser un administrador de Canvas y un administrador del Microsoft 365 inquilino.

1. Inicie sesión en el portal Microsoft Azure con la cuenta de administrador de inquilinos. El administrador de inquilinos de Azure también debe tener el rol de administrador de grupo.

    ![administrador de grupo resaltado](../media/lti-media/lti-group-admin.png)

2. Inicie sesión en el portal [OneDrive LTI de](https://odltiappnl.azurewebsites.net/admin)Microsoft.

3. Acepte los permisos para completar el inicio de sesión.

    ![aceptar permisos](../media/lti-media/lti-permissions.png)

4. Seleccione **Agregar inquilino LTI**.

     ![agregar inquilino de LTI](../media/lti-media/lti-add-tenant.png)

5. Selecciona **Plataforma de consumidor de LTI** como **Lienzo** en el desplegable.

6. Seleccione **Dirección URL base de Canvas** y, a continuación, seleccione **Siguiente**.

    ![seleccione Canvas y agregue la dirección URL base](../media/lti-media/lti-canvas-base-url.png)

   En la siguiente pantalla se muestran los campos que son confidenciales para usted.

7. Seleccione **Siguiente** de ?? página. ¿LOS REVISORES PUEDEN RELLENAR EL ESPACIO EN BLANCO AQUÍ?

8. Seleccione **Siguiente** en la pantalla que muestra información confidencial para usted.

   La pantalla final de Azure Portal muestra los pasos siguientes para agregar la instancia de Canvas.

9. Copia las claves de desarrollador de esta pantalla. Lo usarás al crear la instancia de Canvas.

## <a name="add-the-canvas-instance"></a>Agregar la instancia de Canvas

1. En la instancia de Canvas, anule la selección de **Claves de desarrollador** de  >  **administración**.

2. Elija **Clave LTI en** la lista desplegable en Clave de **desarrollador**.

   ![Obtener las claves de desarrollador de LTI](../media/lti-media/lti-developer-keys.png)

3. Pegue las claves de desarrollador aquí.

     ![Pegar las claves de desarrollador](../media/lti-media/lti-developer-keys.png)

   La clave se crea en **modo OFF**

   ![Las claves de desarrollador creadas en modo desactivado](../media/lti-media/lti-copy-developer-keys.png)

4. Copie el texto resaltado.
    Esto sirve como identificador de cliente en Microsoft OneDrive portal LTI.

5. Pegue el texto en el **campo Id.** de cliente en Microsoft OneDrive portal LTI y, a continuación, **seleccione Siguiente**.

6. Seleccione **Guardar**.

7. Para ver la configuración, seleccione **Ver inquilinos de LTI**.
