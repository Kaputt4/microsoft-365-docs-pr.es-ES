---
title: Configurar Saba como origen de contenido para Aprendizaje Microsoft Viva
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
description: Obtenga información sobre cómo configurar Saba como un origen de contenido de aprendizaje para Aprendizaje Microsoft Viva.
ROBOTS: NOINDEX
ms.openlocfilehash: 26af97604b071e621794937d45882c98fdef0d31
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2021
ms.locfileid: "60557159"
---
# <a name="configure-saba-as-a-content-source-for-microsoft-viva-learning"></a>Configurar Saba como origen de contenido para Aprendizaje Microsoft Viva

En este artículo se muestra cómo configurar Saba como un origen de contenido de aprendizaje de terceros para Aprendizaje Microsoft Viva. Debe ser administrador del sistema Saba o superusuador para realizar estos pasos.

>[!NOTE]
>El contenido accesible a través de Viva Learning está sujeto a términos distintos de los Términos del producto de Microsoft. El contenido de Saba y los servicios asociados están sujetos a los términos de privacidad y servicio de Saba.

## <a name="clients-host-url"></a>Dirección URL de host del cliente

1. Identifique la dirección URL principal de Saba Cloud (por ejemplo, "org".sabacloud.com). Si la dirección URL del panel de api org-api.sabacloud.com, la dirección URL de host se mostrará org.sabacloud.com.

2. Identifique la dirección URL del panel de api yendo a **Saba Cloud**  >  **Admin**  >  **System Admin Manage**  >  **Integrations** API  >  **Dashboard**. Busque la dirección URL del panel de api y, a continuación, quite "https://" y "-api" para obtener la dirección URL del host.

<!--![Image of the API dashboard.](../media/learning/saba-1.png)-->

## <a name="client-id-and-client-secret"></a>Id. de cliente y secreto de cliente

1. En la misma pantalla donde obtuvo la dirección URL del host, copie el id. de cliente y el secreto de cliente si ya se han generado.

2. Si el secreto de cliente aún no está, seleccione el **botón GENERAR** para generarlo.

    <!--![Image of the button to generate the Client secret.](../media/learning/saba-2.png)-->

## <a name="username-and-password"></a>Nombre de usuario y contraseña

Proporcione el nombre de usuario y la contraseña de una cuenta administrativa Microsoft Viva usar para extraer cursos, finalización e información relacionada de la nube de Saba a través de la API de REST. Esta cuenta debería ser idealmente un superusuista. Si la cuenta no es un superusuaria, debe tener al menos roles de administrador **Learning:** generador de catálogos y administrador de **capital** humano (o roles de seguridad personalizados equivalentes) en Saba.

## <a name="last-steps"></a>Últimos pasos

Tendrás que completar la configuración en tu Centro de administración de Microsoft 365.

1. Inicie sesión en su [Centro de administración de Microsoft 365](https://admin.microsoft.com).
2. Vaya a **Configuración** y, a continuación, **configuración de la organización**. Seleccione Viva Learning y habilite Saba Cloud en el panel.
3. Rellene los detalles que obtuvo del portal de Saba.
    >[!NOTE]
    >Nombre para mostrar es el nombre del carrusel en el que aparecerá contenido de aprendizaje de Saba para los usuarios de su organización en Viva Learning. Si no escribe un nombre nuevo, mostrará el nombre predeterminado "Nube de Saba".

    <!--![Image of where you post configuration details in the admin center.](../media/learning/saba-3.png)-->

4. Seleccione **Guardar** para activar el contenido de Saba Cloud en Aprendizaje Microsoft Viva. El contenido puede tardar hasta 24 horas en mostrarse en Viva Learning.

> [!Note]
> Para la integración de Saba Cloud, debe tener un dominio sabacloud.com en la dirección URL de host. Si tienes un nombre de dominio diferente, tendrás que generar un vale de soporte técnico para permitir tu nombre de dominio.

## <a name="data-residency"></a>Residencia de datos

Los metadatos del espacio empresarial se almacenan de forma centralizada en nuestros almacenes de datos y no se almacenan en almacenes de datos específicos geográficamente.

## <a name="roles-and-permissions"></a>Roles y permisos

Actualmente, todos los usuarios de una organización podrán descubrir todos los cursos específicos del espacio empresarial. Sin embargo, solo podrán usar los cursos a los que tienen acceso. La detección de contenido específica del usuario (basada en roles y permisos) está planeada para su implantación en el futuro.
