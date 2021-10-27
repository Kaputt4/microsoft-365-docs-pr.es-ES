---
title: Configurar Go1 como origen de contenido para Aprendizaje Microsoft Viva
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
description: Obtenga información sobre cómo configurar Go1 como un origen de contenido de aprendizaje para Aprendizaje Microsoft Viva.
ROBOTS: NOINDEX
ms.openlocfilehash: ade44c0cc7607ab1b7a247ee60bdd2ca3505e6e9
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2021
ms.locfileid: "60586166"
---
# <a name="configure-go1-as-a-content-source-for-microsoft-viva-learning"></a>Configurar Go1 como origen de contenido para Aprendizaje Microsoft Viva

>[!NOTE]
>Esta característica no se admite en la vista previa.

En este artículo se muestra cómo configurar Go1 como origen de contenido de aprendizaje de terceros en Viva Learning.

>[!NOTE]
>El contenido accesible a través de Viva Learning está sujeto a términos distintos de los Términos del producto de Microsoft. El contenido de Go1 y los servicios asociados están sujetos a los términos de privacidad y servicio de Go1.

Go1 proporciona acceso a miles de cursos de los principales proveedores de contenido. [Obtenga más información sobre Go1](https://www.go1.com/go1-microsoft-viva). Siga estos pasos para agregar Go1 como origen de aprendizaje en Viva Learning.

## <a name="create-a-developers-app-in-go1"></a>Crear una aplicación de desarrollador en Go1

En primer lugar, tendrás que seguir estos pasos para crear una aplicación en el Portal de Go1. Esta aplicación generará tus claves de API, que puedes usar para autenticar con Go1 y realizar solicitudes a la API.

1. Inicie sesión en el Portal de Go1 como administrador.

2. Seleccione **Integraciones en** las opciones del menú.

3. Seleccione **Desarrolladores**.

    <!--![Image of the Developers option in the Integrations menu.](../media/learning/go1-1.png)-->

4. Selecciona el **botón Crear aplicación.**

    <!--![Image of the Create App button.](../media/learning/go1-2.png)-->

5. Escriba un nombre para la aplicación, por ejemplo, "My-go1-viva-integration".

6. Escriba una dirección URL de llamada atrás, por ejemplo, "Mycompany.mygo1.com".

    <!--![Image of the field where you enter the name and callback URL.](../media/learning/go1-3.png)-->

7. Guarde la información que ha especificado.

8. La información se mostrará con el secreto oculto. Seleccione los puntos suspensivos (**...**), luego seleccione **Ver secreto** para mostrar el secreto.

9. Copie los siguientes valores:

    - **Dirección URL de host del cliente:** Esta es la dirección URL del portal de Go1. Tendrá el aspecto de " https://mycompany.mygo1.com ".
    - **Id. de cliente:** Puedes encontrar tu id. en el Portal De Go1 en las **opciones del menú Integraciones/Programador.**
    - **Secreto:** Puedes encontrar el secreto en el Portal de Go1 en las **opciones del menú Integraciones/Programador.**

## <a name="complete-configuration-in-the-microsoft-365-admin-center"></a>Configuración completa en el Centro de administración de Microsoft 365

Copie y pegue los valores que ha recuperado del Portal de Go1 en la pantalla de instalación de Go1 en el Centro de administración de Microsoft 365.

Obtenga más información [sobre cómo crear una aplicación de desarrollador privado para Go1](https://help.go1.com/en/articles/4642648-integrate-with-the-go1-api).
