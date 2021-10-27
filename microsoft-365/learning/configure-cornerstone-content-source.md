---
title: Configurar Cornerstone OnDemand como origen de contenido para Aprendizaje Microsoft Viva
ms.author: daisyfeller
author: daisyfell
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 10/07/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: Obtenga información sobre cómo configurar Cornerstone OnDemand como un origen de contenido de aprendizaje para Aprendizaje Microsoft Viva.
ROBOTS: NOINDEX
ms.openlocfilehash: 6cc77ec25f7297fa2492b5a22d70e60350b8eccc
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2021
ms.locfileid: "60586130"
---
# <a name="configure-cornerstone-ondemand-as-a-content-source-for-microsoft-viva-learning"></a>Configurar Cornerstone OnDemand como origen de contenido para Aprendizaje Microsoft Viva

>[!NOTE]
>Esta característica no se admite en la vista previa.

En este artículo se muestra cómo configurar Cornerstone OnDemand como origen de contenido de aprendizaje de terceros en Viva Learning. En primer lugar, deberá habilitar Viva Learning y obtener los detalles de su Portal de cornerstone. A continuación, tendrás que completar la configuración en tu Centro de administración de Microsoft 365.

>[!NOTE]
>El contenido accesible a través de Viva Learning está sujeto a términos distintos de los Términos del producto de Microsoft. El contenido de Cornerstone OnDemand y los servicios asociados están sujetos a los términos de privacidad y servicio de Cornerstone OnDemand.

## <a name="configure-in-your-cornerstone-portal"></a>Configurar en el Portal de Cornerstone

1. Inicie sesión en el Portal de Cornerstone como administrador.
2. Elija **Edge**.
3. Vaya a **Marketplace** y busque Viva.
4. Seleccione el icono Learning Viva.
5. Elija **Instalar**.
6. Active la casilla para confirmar que está de acuerdo con los Términos y condiciones y elija **Instalar**.
7. Seleccione **Configurar ahora**.
8. Copie el identificador de cliente, el secreto, el nombre del portal y la dirección URL base. A continuación, vuelva atrás y busque Viva.
9. Deslice el botón de alternancia para habilitar la integración Learning Viva.

## <a name="configure-in-microsoft-365-admin-center"></a>Configurar en Centro de administración de Microsoft 365

1. Inicie sesión en su [Centro de administración de Microsoft 365](https://admin.microsoft.com).
2. Vaya a **Configuración** y, a continuación, **configuración de la organización**. Seleccione Viva Learning y habilite Cornerstone OnDemand en el panel.
3. Rellene los detalles de configuración que ha recuperado de su Portal de cornerstone.

    >[!NOTE]
    >El nombre para mostrar es el nombre del carrusel bajo el cual aparecerá contenido de aprendizaje de Cornerstone para su organización en Viva Learning. Si no escribe un nombre, mostrará el nombre predeterminado "Cornerstone OnDemand".

4. Seleccione **Guardar para** activar el contenido de Cornerstone en Viva Learning. El contenido puede tardar hasta 24 horas en mostrarse en la aplicación Viva Learning web.

## <a name="data-residency"></a>Residencia de datos

Los metadatos del espacio empresarial se almacenan de forma centralizada en nuestros almacenes de datos y no se almacenan en almacenes de datos específicos geográficamente.

## <a name="roles-and-permissions"></a>Roles y permisos

Actualmente, todos los usuarios de una organización pueden descubrir todos los cursos específicos del inquilino, pero solo podrán usar los cursos a los que tienen acceso. La detección de contenido específica del usuario basada en roles y permisos está planeada para futuras versiones.
