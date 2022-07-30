---
title: Personalización del tema de la organización
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- VSBFY23
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 8275da91-7a48-4591-94ab-3123a3f79530
description: Aprenda a cambiar el tema predeterminado de la parte superior de la barra de navegación de Microsoft 365 y a personalizarlo para que coincida con el logotipo o el color de su empresa.
ms.openlocfilehash: 6af086c9fff4ce30d52456103dac14d7fb93ee36
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2022
ms.locfileid: "67086569"
---
# <a name="customize-the-microsoft-365-theme-for-your-organization"></a>Personalización del tema de Microsoft 365 para su organización

Como administrador de la organización, puede crear varios temas para las personas de su organización y seleccionar los temas que se aplican a los distintos miembros de la organización. El tema de la organización es lo que aparece en la barra de navegación superior para los usuarios de la organización.

Puede agregar o actualizar un tema predeterminado que se aplique a todos los usuarios de su organización. También puede crear hasta cuatro temas de grupo adicionales que se pueden asignar a varios grupos de Microsoft 365.
  
## <a name="add-or-update-your-organizations-theme"></a>Agregar o actualizar el tema de la organización

1. En el centro de administración, vaya a la página **Configuración** \> **de la organización** y, a continuación, elija la pestaña **Perfil** de organización.

2. En la pestaña **Perfil de organización** , seleccione **Temas personalizados**.

Todos los temas de la organización se pueden personalizar mediante las pestañas siguientes.

|Pestaña|What can you do?|
|---|---|
|[General](#general-modify-a-theme)|Modifique un nombre de tema y asígnelo a hasta cinco grupos (si procede).|
|[Logotipos](#logos-specify-your-theme-logos)|Agregue el logotipo de la organización, incluido el logotipo alternativo para el tema oscuro.|
|[Colors](#colors-choose-theme-colors)|Personalice una combinación de colores especificando los colores de la barra de navegación, el acento, el texto y el icono.|

## <a name="general-modify-a-theme"></a>General: Modificación de un tema

La experiencia en la pestaña General depende de si va a agregar o modificar el tema predeterminado o un tema de grupo.

### <a name="update-the-default-theme"></a>Actualización del tema predeterminado

El tema predeterminado es el primer tema mostrado.  

1. Si previamente ha personalizado un tema para su organización, seleccione **Tema predeterminado** y use una de las personalizaciones guardadas, o bien seleccione **Agregar tema**.
2. En la página **General** , puede impedir que los usuarios invaliden su tema y mostrar el nombre para mostrar del usuario.
3. Seleccione **Guardar** para guardar los cambios.  

> [!IMPORTANT]
> El tema predeterminado es único, no se puede cambiar de nombre y se aplica a todos los usuarios de la organización. Para eliminar el tema predeterminado, primero debe eliminar todos los demás temas.

:::image type="content" source="../../media/Default_Theme_Panel1.png" alt-text="Captura de pantalla: pestaña General que muestra el tema predeterminado de la organización":::

### <a name="create-a-group-theme"></a>Creación de un tema de grupo

Puede crear hasta cuatro temas de grupo adicionales.

1. En la página **General** , escriba un nombre para el nuevo tema.

2. En **Grupos**, puede seleccionar hasta 5 Grupos de Microsoft 365 que puedan ver el tema del grupo, en lugar de usar el tema predeterminado. También puede impedir que los usuarios reemplacen su tema y mostrar el nombre para mostrar del usuario.

3. Seleccione **Guardar**.

:::image type="content" source="../../media/default-theme-general-users1.png" alt-text="Captura de pantalla: pestaña General que muestra el tema predeterminado para un grupo de usuarios de la organización":::

## <a name="logos-specify-your-theme-logos"></a>Logotipos: especifique los logotipos del tema

En la página **Logotipos** , puede agregar los logotipos y especificar la dirección URL a la que navegarán los usuarios cuando seleccionen el logotipo.

- **Logotipo predeterminado**: agregue una ubicación de dirección URL que apunte al logotipo. Asegúrese de que la dirección URL usa HTTPS. Agregue una dirección URL de imagen HTTPS que permita el acceso anónimo y no requiera autenticación. Para el tema predeterminado, también tiene una opción para cargar una imagen de logotipo que sea inferior a 10 kb. El logotipo predeterminado puede estar en formato JPG, PNG, GIF o SVG. En el caso de las imágenes SVG, se ajustarán verticalmente a 24 píxeles. Las imágenes JPG, PNG y GIF se escalarán para ajustarse a 200 x 48 píxeles. La relación de aspecto del logotipo siempre se conservará.
- **Logotipo alternativo**: agregue una ubicación de dirección URL que apunte al logotipo. El logotipo alternativo debe optimizarse para su uso en temas oscuros de Office. Los mismos requisitos que el logotipo predeterminado.
- **Vínculo al hacer clic**: agregue una ubicación de dirección URL que apunte al logotipo. Puede usar el logotipo como vínculo a cualquier recurso de la empresa, por ejemplo, el sitio web de su empresa. Si no selecciona una ubicación de dirección URL para el logotipo, tendrá como valor predeterminado la página principal de Office.

Seleccione **Guardar** para guardar los cambios.

:::image type="content" source="../../media/Logos_Tab.png" alt-text="Captura de pantalla: pestaña Logotipos que muestra las opciones del logotipo":::

Puede quitar sus logotipos en cualquier momento. Simplemente vuelva a la página **Logotipos** y seleccione **Quitar**.
  
## <a name="colors-choose-theme-colors"></a>Colores: Elegir colores de tema

En la página **Colores** , puede establecer los colores predeterminados y elegir qué logotipo se debe usar.

- **Color de la barra** de navegación: seleccione un color que se usará para el fondo de la barra de navegación. La barra de navegación aparece en la parte superior de cada página.
- **Color de texto e icono**: seleccione un color que se usará para el texto y los iconos de la barra de navegación superior.
- **Color de énfasis**: elija uno que aparezca bien en un fondo blanco o claro. El color de énfasis se usa para colorear algunos vínculos y botones que aparecen en un fondo blanco o claro. Por ejemplo, el color de énfasis se usa para colorear elementos en la bandeja de entrada de un usuario y en su página del portal de Office.com.
- **Restablecer color**: seleccione este vínculo para restablecer los colores a los colores predeterminados.

:::image type="content" source="../../media/default-theme-colors1.png" alt-text="Captura de pantalla: pestaña Colores que muestra los colores de tema predeterminados de su organización":::

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="my-organization-already-has-a-theme-for-all-employees-how-will-this-change"></a>Mi organización ya tiene un tema para todos los empleados. ¿Cómo cambiará esto?

El tema predeterminado seguirá mostrándose a todos los empleados. Agregar un nuevo tema de grupo solo estará disponible para los grupos de Microsoft 365 asociados a ese tema.

### <a name="why-dont-i-see-group-themes-in-the-admin-center"></a>¿Por qué no veo temas de grupo en el Centro de Administración?

Solo los administradores globales pueden personalizar los temas de la empresa. Los lectores globales tienen acceso de solo lectura.

### <a name="how-many-different-themes-can-i-set-up-for-my-organization"></a>¿Cuántos temas diferentes puedo configurar para mi organización?  

Se pueden crear hasta cinco temas. Un tema predeterminado y cuatro temas de grupo.  

### <a name="can-i-use-security-groups-or-distribution-groups-instead-of-microsoft-365-groups"></a>¿Puedo usar grupos de seguridad o grupos de distribución en lugar de Grupos de Microsoft 365?

No, los nuevos temas de grupo deben asignarse a uno o varios grupos de Microsoft 365 y no a grupos de seguridad o grupos de distribución.

> [!NOTE]
> Puede convertir [grupos de distribución a grupos de Microsoft 365](../manage/upgrade-distribution-lists.md) en Outlook.

### <a name="can-i-manually-assign-a-theme-independent-of-microsoft-365-groups"></a>¿Puedo asignar manualmente un tema independiente de Grupos de Microsoft 365?  

No, los nuevos temas de grupo deben asignarse a uno o varios grupos de Microsoft 365. Los usuarios que sean miembros del grupo de Microsoft 365 obtendrán el tema aplicado a su grupo. Para [crear y agregar nuevos miembros a un grupo de Microsoft 365](../create-groups/create-groups.md), vaya a los **grupos** **de configuración** >  del Centro de administración.

### <a name="what-happens-if-a-user-is-assigned-to-multiple-group-themes"></a>¿Qué ocurre si un usuario está asignado a varios temas de grupo?  

A los usuarios asignados a varios temas de grupo se les mostrará el tema predeterminado.  

### <a name="why-cant-i-delete-the-default-theme"></a>¿Por qué no puedo eliminar el tema predeterminado?  

El tema predeterminado solo se puede eliminar una vez eliminados todos los temas de grupo. Asegúrese de eliminar todos los temas de grupo antes de intentar eliminar el tema del grupo.

### <a name="why-am-i-receiving-an-error-message-every-time-i-upload-a-logo-url"></a>¿Por qué recibo un mensaje de error cada vez que cargue una dirección URL del logotipo?  

Asegúrese de que el logotipo que usa se especifica como una dirección URL direccionable públicamente. Siga estos pasos para [cargar logotipos en Azure Blob Storage](/azure/storage/blobs/storage-upload-process-images?tabs=dotnet) o la [Office 365 Content Delivery Network con SharePoint Online](../../enterprise/use-microsoft-365-cdn-with-spo.md).

### <a name="why-am-i-receiving-the-message-doesnt-meet-minimum-color-contrast-ratio-of-451"></a>¿Por qué recibo el mensaje "No cumple la relación mínima de contraste de color de 4,5:1"?

La relación de contraste recomendada entre el texto, el icono o el color de botón y el color de fondo es 4.5:1. Puede invalidar esta recomendación y seguir guardando el tema, ya que esto no es un requisito.

### <a name="if-i-define-a-theme-which-places-in-microsoft-365-will-this-be-used"></a>Si defino un tema, ¿qué lugares de Microsoft 365 se usarán?

Cualquier tema aparece en la barra de navegación superior para todos los usuarios de la organización como parte del encabezado del conjunto de aplicaciones de Microsoft 365.  
  
## <a name="related-content"></a>Contenido relacionado

[Agregar iconos personalizados a la página Mis aplicaciones y al iniciador de aplicaciones](../manage/customize-the-app-launcher.md) (artículo)\
[Información general de Grupos de Microsoft 365 para administradores](../create-groups/office-365-groups.md) (artículo)
