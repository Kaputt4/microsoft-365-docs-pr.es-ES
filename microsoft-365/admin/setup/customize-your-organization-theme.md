---
title: Personalizar el tema de la organización
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 8275da91-7a48-4591-94ab-3123a3f79530
description: 'Obtenga información sobre cómo cambiar el tema predeterminado de Microsoft 365 y personalizarlo para que se ajuste al logotipo o al logotipo de su compañía. '
ms.openlocfilehash: dba7003f6624a2635976ac689d608a83e62de5c0
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327211"
---
# <a name="customize-the-microsoft-365-theme-for-your-organization"></a>Personalizar el tema de 365 de Microsoft para su organización

Obtenga información sobre cómo personalizar el tema en el centro de administración de Microsoft 365. Como administrador de su suscripción de Microsoft 365 para empresas, puede cambiar el tema predeterminado que aparece en la barra de navegación superior para todos los usuarios de la organización. Puede Agregar el logotipo de su compañía y cambiar los colores para que se ajusten al resto de la marca. Incluso puede Agregar un vínculo de destino para que los usuarios naveguen a cuando seleccionen su logotipo. Puede ver aquí el tema predeterminado y el resultado del tema personalizado en Microsoft 365.
  
![Tema de Microsoft 365 predeterminado y tema de Microsoft 365 personalizado](../../media/e2cbc922-b424-4683-8c5c-fdbcbd0ce844.png)
  
## <a name="customize-your-theme-in-the-admin-center"></a>Personalizar el tema en el centro de administración

1. En el centro de administración, vaya a configuración de la organización de **configuración** \> **Org Settings**y, a continuación, elija la pestaña **perfil** de la organización.

2. En la pestaña Perfil de la **organización** , elija **temas personalizados**.

3. En el panel **temas de aduana** , cambie los elementos del tema que desee para su organización:
    
    - **Usar una imagen de logotipo personalizada**: elija si desea usar una imagen de una dirección URL o cargar una imagen. Si usa una dirección URL, asegúrese de que la dirección URL use HTTPS y de 200 x 30 píxeles de cualquier formato de cualquier tamaño. Puede cargar un logotipo de menos de 10 KB de 200 x 30 píxeles en formato JPG, PNG, GIF o SVG.

      > [!NOTE]
      > Para que el logotipo aparezca en la aplicación móvil de SharePoint, use solo imágenes SVG. Las imágenes que se cargan en cualquier otro formato no se muestran en la aplicación. No se pueden hacer clic en los logotipos en la aplicación móvil de SharePoint.

    - **Hacer que el logotipo haga clic**en: puede usar su logotipo en la barra de navegación como un vínculo a cualquier recurso de la empresa. Puede escribir la dirección URL del logotipo aquí, comenzando con http://o https://. Esto es opcional.

    - **Seleccionar imagen de fondo**: seleccione la imagen y cargue su propio archivo jpg, PNG o GIF con una resolución de 1366 x 50 píxeles, no superior a 15 KB. La imagen de fondo aparece en la barra de navegación superior de cada página.

      > [!NOTE]
      > Es posible que las imágenes que contengan texto no se muestren del modo previsto. Los elementos predefinidos que se muestran a derecha e izquierda de la barra de navegación pueden variar según los servicios, y es posible que el texto quede oscurecido por esos elementos. Debido a la naturaleza dinámica de la barra de navegación, en este momento no podemos ofrecerle instrucciones para configurar el relleno de imagen de forma que ofrezca una experiencia unificada. 

    - **Color**de la barra de navegación: Seleccione un color para usarlo en el fondo de la barra de navegación. Se mostrará en la parte superior de todas las páginas.

    - **Texto e iconos**: seleccione un color para usarlo para el texto y los iconos de la barra de navegación superior.

    - **Color de énfasis**: Seleccione un color para usarlo en el botón de barra de navegación color y acentos de página como botones y texto en ciertas aplicaciones.

     - **Impedir que los usuarios reemplacen el tema**: voltee este botón de alternancia para evitar que los usuarios elijan su propio tema desde nuestra selección de temas. Esto no impide que los usuarios puedan establecer un tema de contraste alto.

    - **Mostrar el nombre de usuario**: elija si desea mostrar el nombre completo de un usuario en el punto de entrada al administrador de cuentas en la parte superior derecha de la página cuando el usuario haya iniciado sesión. De forma predeterminada, los usuarios verán su foto o sus iniciales si no se ha cargado una foto.
    
4. Seleccione **Guardar cambios**.
    
Verá el nuevo tema en el centro de administración inmediatamente y, tras un breve retraso, lo verá en Microsoft 365, incluidas las páginas en Outlook, SharePoint, la [aplicación móvil de SharePoint para iOS](https://support.office.com/article/SharePoint-mobile-app-for-iOS-339402ce-16bb-4c97-9475-0c5375ccef7a)y la [aplicación móvil de SharePoint para Android](https://support.office.com/article/SharePoint-mobile-app-for-Android-d875654b-fb0a-4dbe-a17a-a676cf936284). Para obtener un ejemplo de dónde puede personalizar los cambios de tema desde el centro de administración, consulte la siguiente imagen.

![M365-admin-tenant-Theme-conceptual](../../media/m365-admin-tenant-theme-conceptual.png)

Podrá quitar el icono o los colores personalizados en cualquier momento. Simplemente vuelva a la página tema y seleccione **quitar temas personalizados**.
  
## <a name="best-practices"></a>Procedimientos recomendados

Al elegir una **imagen de logotipo**, se recomienda usar un tipo de archivo SVG, de modo que el logotipo tenga un aspecto de alta resolución en todas las pantallas y en todos los niveles de zoom.

Al elegir colores personalizados, elija un **color de fondo** de la barra de navegación que tenga una relación de contraste alto con la **imagen de logotipo** que ha seleccionado. Elija también un color de **texto e iconos** con una alta relación de contraste en el color de fondo de la **barra de navegación** para asegurarse de que todo el texto y los iconos se ven fácilmente.

Al elegir colores personalizados, elija un **color de énfasis** que se muestre bien en un fondo blanco o claro. El **color de énfasis** se usa para colorear algunos botones y vínculos que se muestran en un fondo blanco o claro. Por ejemplo, el **color de énfasis** se usa para colorear los elementos en la bandeja de entrada de un usuario y en su página de portal de Office.com. 
  
La relación de contraste recomendada entre el color de texto, icono o botón y el color de fondo es 4,5:1.

Este es un diagrama de flujo simple para ayudarle a configurar rápidamente un tema personalizado de Microsoft 365 visualmente atractivo para su organización:
  - Me gustaría usar una versión de color de nuestro logotipo.
    - Se recomienda la siguiente configuración:
      - **Imagen de logotipo**: el logotipo de color de la organización.
      - **Color**de la barra de navegación: color neutro. Se recomienda #FAF9F7 para un color claro y #252423 para un color oscuro.
      - **Color de texto e icono**: color para contrastar el color de la **barra de navegación**. Se recomienda #FAF9F7 para un color claro y #252423 para un color oscuro.
      - **Color de énfasis**: un color de marca oscuro. Con ciertas aplicaciones, este color debe estar visible en un fondo claro.
  - Me gustaría usar una versión neutra de nuestro logotipo y representar el color en la barra de navegación.
    - Se recomienda la siguiente configuración:
      - **Imagen de logotipo**: logotipo neutro de la organización.
      - **Color**de la barra de navegación: un color de marca que contrasta con el logotipo.
      - **Color del texto y el icono**: elija un color que contraste con el color de marca elegido para el color de la **barra de navegación**. Se recomienda #252423 para un color oscuro y #FAF9F7 para un color claro.
      - **Color de énfasis**: un color de marca oscuro. Con ciertas aplicaciones, este color debe estar visible en un fondo claro.
  
## <a name="related-articles"></a>Artículos relacionados

[Agregar iconos personalizados a la página Mis aplicaciones y al iniciador de aplicaciones](../manage/customize-the-app-launcher.md)
  
  
