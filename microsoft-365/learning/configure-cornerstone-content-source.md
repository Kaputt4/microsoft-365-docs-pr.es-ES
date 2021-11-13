---
title: Configurar Cornerstone OnDemand como origen de contenido para Aprendizaje Microsoft Viva
ms.author: daisyfeller
author: daisyfell
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 10/27/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: Obtenga información sobre cómo configurar Cornerstone OnDemand como un origen de contenido de aprendizaje para Aprendizaje Microsoft Viva.
ms.openlocfilehash: 4a4b49b4dbe2dd0c946438f103ccb668c01645e5
ms.sourcegitcommit: 8eca41cd21280ffcb1f50cafce7a934e5544f302
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2021
ms.locfileid: "60950610"
---
# <a name="configure-cornerstone-ondemand-as-a-content-source-for-microsoft-viva-learning"></a>Configurar Cornerstone OnDemand como origen de contenido para Aprendizaje Microsoft Viva

En este artículo se muestra cómo configurar Cornerstone OnDemand como origen de contenido de aprendizaje de terceros en Viva Learning. En primer lugar, deberá habilitar Viva Learning y obtener los detalles de su Portal de cornerstone. A continuación, tendrás que completar la configuración en tu Centro de administración de Microsoft 365.

>[!NOTE]
>El contenido accesible a través de Viva Learning está sujeto a términos distintos de los Términos del producto de Microsoft. El contenido de Cornerstone OnDemand y los servicios asociados están sujetos a los términos de privacidad y servicio de Cornerstone OnDemand.

## <a name="configure-in-your-cornerstone-portal"></a>Configurar en el Portal de Cornerstone

1. Inicie sesión en el Portal de Cornerstone como administrador.

    ![Imagen del Portal cornerstone.](../media/learning/csod-1.png)

2. Elija **Edge**.

    ![Imagen del panel perimetral.](../media/learning/csod-2.png)

3. Vaya a **Marketplace** y busque Viva.

    ![Imagen del Marketplace.](../media/learning/csod-3.png)

4. Seleccione el icono Learning Viva.

    ![Imagen del cursor que se mueve sobre el icono Learning Viva en marketplace.](../media/learning/csod-4.png)

5. Elija **Instalar**.

    ![Imagen del cursor que se mueve sobre el botón Instalar después de seleccionar el icono Learning Viva.](../media/learning/csod-5.png)

6. Active la casilla para confirmar que está de acuerdo con los Términos y condiciones y elija **Instalar**.

    ![Imagen de la pantalla Instalar con la casilla Términos y condiciones activada.](../media/learning/csod-6.png)

7. Seleccione **Configurar ahora**.

    ![Imagen del elemento emergente de instalación con un botón que indica Configurar ahora a la derecha y otro que dice Más adelante a la izquierda.](../media/learning/csod-7.png)

8. Copie el identificador de cliente, el secreto, el nombre del portal y la dirección URL base. A continuación, vuelva atrás y busque Viva.

    ![Imagen de la pantalla de configuración donde puede encontrar el identificador de cliente, el secreto de cliente, el nombre del portal y la dirección URL base.](../media/learning/csod-8.png)

9. Deslice el botón de alternancia para habilitar la integración Learning Viva.

    ![Imagen del botón de Learning integración de Viva en la posición activa.](../media/learning/csod-10.png)

## <a name="configure-in-your-microsoft-365-admin-center"></a>Configurar en el Centro de administración de Microsoft 365

1. Inicie sesión en su [Centro de administración de Microsoft 365](https://admin.microsoft.com).
2. Vaya a **Configuración** y, a continuación, **configuración de la organización**. Seleccione Viva Learning y habilite Cornerstone OnDemand en el panel.
3. Rellene los detalles de configuración que ha recuperado de su Portal de cornerstone.

    >[!NOTE]
    >El nombre para mostrar es el nombre del carrusel bajo el cual aparecerá contenido de aprendizaje de Cornerstone para su organización en Viva Learning. Si no escribe un nombre, mostrará el nombre predeterminado "Cornerstone OnDemand".

4. Seleccione **Guardar para** activar el contenido de Cornerstone en Viva Learning. El contenido puede tardar hasta 24 horas en mostrarse en la aplicación Viva Learning web.

>[!NOTE]
>Actualmente, todos los usuarios de una organización pueden descubrir todos los cursos específicos del inquilino, pero solo podrán consumir los cursos a los que tienen acceso. La detección de contenido específica del usuario basada en roles y permisos está planeada para futuras versiones.
