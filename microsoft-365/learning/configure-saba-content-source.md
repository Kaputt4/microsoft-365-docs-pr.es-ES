---
title: Configurar Saba como origen de contenido para Aprendizaje Microsoft Viva
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
description: Obtenga información sobre cómo configurar Saba como un origen de contenido de aprendizaje para Aprendizaje Microsoft Viva.
ms.openlocfilehash: cb13822e2f4a0a2eccf31e2c03f2ac5e109dd843
ms.sourcegitcommit: 8eca41cd21280ffcb1f50cafce7a934e5544f302
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2021
ms.locfileid: "60950502"
---
# <a name="configure-saba-as-a-content-source-for-microsoft-viva-learning"></a>Configurar Saba como origen de contenido para Aprendizaje Microsoft Viva

En este artículo se muestra cómo configurar Saba como un origen de contenido de aprendizaje de terceros para Aprendizaje Microsoft Viva. Debe ser administrador del sistema Saba o superusuador para realizar estos pasos.

>[!NOTE]
>El contenido accesible a través de Viva Learning está sujeto a términos distintos de los Términos del producto de Microsoft. El contenido de Saba y los servicios asociados están sujetos a los términos de privacidad y servicio de Saba.

>[!NOTE]
>Viva Learning integración con Saba usará las API de su cubo de llamadas API al mes y contará para su límite de limitación.

## <a name="configure-in-your-saba-portal"></a>Configurar en el portal de Saba

>[!NOTE]
>Tendrás que tener permisos de administrador en Saba para completar estos pasos.

### <a name="clients-host-url"></a>Dirección URL de host del cliente

1. Identifique la dirección URL principal de Saba Cloud (por ejemplo, "org".sabacloud.com). Si la dirección URL del panel de api org-api.sabacloud.com, la dirección URL de host se mostrará org.sabacloud.com.
2. Identifique la dirección URL del panel de api yendo a **Saba Cloud**  >  **Admin**  >  **System Admin Manage**  >  **Integrations** API  >  **Dashboard**. Busque la dirección URL del panel de api y, a continuación, quite "https://" y "-api" para obtener la dirección URL del host.

    ![Imagen del panel de api.](../media/learning/saba-a.png)

### <a name="client-id-and-client-secret"></a>Id. de cliente y secreto de cliente

1. En la misma pantalla donde obtuvo la dirección URL del host, copie el id. de cliente y el secreto de cliente si ya se han generado.

2. Si el secreto de cliente aún no está, seleccione el **botón GENERAR** para generarlo.

    ![Imagen del panel de api con el cursor sobre el botón Generar.](../media/learning/saba-b.png)

## <a name="configure-in-your-microsoft-365-admin-center"></a>Configurar en el Centro de administración de Microsoft 365

Tendrás que completar la configuración en tu Centro de administración de Microsoft 365.

>[!NOTE]
>Tendrás que tener permisos de administrador en Microsoft 365 para completar estos pasos.

1. Inicie sesión en su [Centro de administración de Microsoft 365](https://admin.microsoft.com).
2. Vaya a **Configuración** y, a continuación, **configuración de la organización**. Seleccione Viva Learning y habilite Saba Cloud en el panel.
3. Rellene los detalles que obtuvo del portal de Saba.
    >[!NOTE]
    >Nombre para mostrar es el nombre del carrusel en el que aparecerá contenido de aprendizaje de Saba para los usuarios de su organización en Viva Learning. Si no escribe un nombre nuevo, mostrará el nombre predeterminado "Nube de Saba".
4. Seleccione **Guardar** para activar el contenido de Saba Cloud en Aprendizaje Microsoft Viva. El contenido puede tardar hasta 24 horas en mostrarse en Viva Learning.

> [!Note]
> Para la integración de Saba Cloud, debe tener un dominio sabacloud.com en la dirección URL de host. Si tienes un nombre de dominio diferente, tendrás que generar un vale de soporte técnico para permitir tu nombre de dominio.

>[!NOTE]
>Actualmente, todos los usuarios de una organización pueden descubrir todos los cursos específicos del inquilino, pero solo podrán consumir los cursos a los que tienen acceso. La detección de contenido específica del usuario basada en roles y permisos está planeada para futuras versiones.
