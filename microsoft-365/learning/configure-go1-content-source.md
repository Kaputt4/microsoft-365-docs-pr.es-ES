---
title: Configurar Go1 como origen de contenido para Aprendizaje Microsoft Viva
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
description: Obtenga información sobre cómo configurar Go1 como un origen de contenido de aprendizaje para Aprendizaje Microsoft Viva.
ms.openlocfilehash: 1adef6275be2a8656eaad9a7f47805d13299e3c7
ms.sourcegitcommit: 8eca41cd21280ffcb1f50cafce7a934e5544f302
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2021
ms.locfileid: "60950538"
---
# <a name="configure-go1-as-a-content-source-for-microsoft-viva-learning"></a>Configurar Go1 como origen de contenido para Aprendizaje Microsoft Viva

En este artículo se muestra cómo configurar Go1 como origen de contenido de aprendizaje de terceros en Viva Learning.

>[!NOTE]
>El contenido accesible a través de Viva Learning está sujeto a términos distintos de los Términos del producto de Microsoft. El contenido de Go1 y los servicios asociados están sujetos a los términos de privacidad y servicio de Go1.

Go1 proporciona acceso a miles de cursos de los principales proveedores de contenido. [Obtenga más información sobre Go1](https://www.go1.com/go1-microsoft-viva). Siga estos pasos para agregar Go1 como origen de aprendizaje en Viva Learning.

## <a name="configure-in-your-go1-portal"></a>Configurar en el portal de Go1

>[!NOTE]
>Tendrás que tener permisos de administrador en Go1 para completar estos pasos.

En primer lugar, tendrás que seguir estos pasos para crear una aplicación en el Portal de Go1. Esta aplicación generará tus claves de API, que puedes usar para autenticar con Go1 y realizar solicitudes a la API.

1. Inicie sesión en el Portal de Go1 como administrador.

2. Seleccione **Integraciones en** las opciones del menú.

3. Seleccione **Desarrolladores**.
4. Selecciona el **botón Crear aplicación.**
5. Escriba un nombre para la aplicación, por ejemplo, "My-go1-viva-integration".
6. Escriba una dirección URL de llamada atrás, por ejemplo, "Mycompany.mygo1.com".
7. Guarde la información que ha especificado.
8. La información se mostrará con el secreto oculto. Seleccione los puntos suspensivos (**...**), luego seleccione **Ver secreto** para mostrar el secreto.
9. Copie los siguientes valores:

    - **Dirección URL de host del cliente:** Esta es la dirección URL del portal de Go1. Tendrá el aspecto de " https://mycompany.mygo1.com ".
    - **Id. de cliente:** Puedes encontrar tu id. en el Portal De Go1 en las **opciones del menú Integraciones/Programador.**
    - **Secreto:** Puedes encontrar el secreto en el Portal de Go1 en las **opciones del menú Integraciones/Programador.**

Obtenga más información [sobre cómo crear una aplicación de desarrollador privado para Go1](https://help.go1.com/en/articles/4642648-integrate-with-the-go1-api).

## <a name="configure-in-your-microsoft-365-admin-center"></a>Configurar en el Centro de administración de Microsoft 365

>[!NOTE]
>Tendrás que tener permisos de administrador en Microsoft 365 para completar estos pasos.

1. Inicie sesión en su [Centro de administración de Microsoft 365](https://admin.microsoft.com).
2. Vaya a **Configuración** y, a continuación, **configuración de la organización**. Seleccione Viva Learning y habilite Go1 en el panel.
3. Rellene los detalles de configuración que ha recuperado del portal de Go1.
4. Seleccione **Guardar** para activar el contenido de Go1 en Viva Learning. El contenido puede tardar hasta 24 horas en mostrarse en la aplicación Viva Learning web.
