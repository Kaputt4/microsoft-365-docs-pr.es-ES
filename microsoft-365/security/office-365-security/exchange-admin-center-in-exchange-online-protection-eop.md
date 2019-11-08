---
title: 'Centro de administración de Exchange en Exchange Online Protection '
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: El Centro de administración de Exchange (EAC) es la consola de administración basada en web para Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: bc825f7ebefa5d2d73a6e9cb954389a7d76cbd73
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "38032385"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a>Centro de administración de Exchange en Exchange Online Protection 

El Centro de administración de Exchange (EAC) es la consola de administración basada en web para Microsoft Exchange Online Protection (EOP).

¿Está buscando la versión de Exchange Server de este tema? Vea [Exchange admin center in Exchange 2013](https://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx).

¿Está buscando la versión de Exchange Online de este tema? Vea [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

## <a name="accessing-the-eac"></a>Acceso a EAC

En la mayoría de los casos, los clientes de EOP obtendrán acceso al EAC a través del centro de administración 365 de Microsoft. Encontrará un vínculo a EOP en el menú desplegable del icono **Administrador**, que está al lado del icono **Yo**. Haga clic en el icono **Administrador** y seleccione **Protección en línea de Exchange** en el menú desplegable para ir al EAC.

You can also access the EAC sign in page directly via the following URL: `https://admin.protection.outlook.com/ecp/<companydomain>`. For example, `https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com`. After specifying your user credentials you will be taken directly into the EAC.

## <a name="common-user-interface-elements-in-the-eac"></a>Elementos comunes de la interfaz de usuario en EAC

En esta sección se describen los elementos de la interfaz de usuario del EAC.

![EOP: AdminCenter](../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a>Panel de características

Este es el primer nivel de navegación para la mayoría de las tareas que realizará en el EAC. El panel de características se organiza por áreas.

1. **Destinatarios**: aquí es donde podrá ver los usuarios internos y los contactos externos.

2. **Permisos**: aquí donde podrá administrar los roles de administrador.

3. **Administración de cumplimiento**: aquí es donde se encuentran los registros de auditoría y los informes, como el informe de grupo de roles de administrador.

4. **Protección**: aquí es donde se administra la protección antimalware y contra correo no deseado para la organización, así como para administrar los mensajes en cuarentena.

5. **Flujo de correo**: aquí es donde se administran las reglas, los dominios aceptados y los conectores, así como el lugar en el que se realizará el seguimiento de mensajes.

### <a name="tabs"></a>Pestañas

Las pestañas son el segundo nivel de navegación. Las áreas de características contienen varias pestañas y cada área representa a una característica.

### <a name="toolbar"></a>Barra de herramientas

Al hacer clic en la mayoría de las pestañas, verá una barra de herramientas. La barra de herramientas tiene iconos que realizan una acción específica. La siguiente tabla describe los iconos y sus acciones.

|**Icono**|**Nombre**|**Action**|
|:-----|:-----|:-----|
|![Agregar icono](../media/ITPro-EAC-AddIcon.gif)|Agregar, nuevo|Utilice este icono para crear un nuevo objeto. Algunos de estos iconos tienen una flecha hacia abajo asociada donde puede hacer clic para mostrar objetos adicionales que puede crear.|
|![Icono Editar](../media/ITPro-EAC-EditIcon.gif)|Editar|Utilice este icono para editar un objeto.|
|![Eliminar icono](../media/ITPro-EAC-DeleteIcon.gif)|Eliminar|Utilice este icono para eliminar un objeto. Algunos iconos eliminados tienen una flecha hacia abajo donde puede hacer clic para mostrar opciones adicionales.|
|![icono de Buscar](../media/ITPro-EAC-.gif)|Búsqueda|Usar este icono para abrir una casilla de búsqueda donde puede escribir una frase de búsqueda para el objeto que desee encontrar.|
|![Icono Actualizar](../media/ITPro-EAC-RefreshIcon.gif)|Actualizar|Utilice este icono para actualizar la vista de lista.|
|![Icono Más opciones](../media/ITPro-EAC-MoreOptionsIcon.gif)|Más opciones|Use este icono para ver más acciones que puede realizar para los objetos de la pestaña. Por ejemplo, al hacer clic en este icono en **Destinatarios \> Usuarios**, se muestra la opción para realizar una **Búsqueda avanzada**.  |
|![Icono flecha arriba](../media/ITPro-EAC-UpArrowIcon.gif)![Icono flecha abajo](../media/ITPro-EAC-DownArrowIcon.gif)|Flecha hacia arriba y flecha hacia abajo|Utilice estos iconos para mover la prioridad de un objeto hacia arriba o hacia abajo.|
|![Icono de quitar](../media/ITPro-EAC-RemoveIcon.gif)|Quitar|Utilice este icono para quitar objetos de la lista.|

### <a name="list-view"></a>Vista de lista

Cuando seleccione una pestaña, en la mayoría de los casos verá la vista de lista. El límite de visualización de la vista de lista del EAC es de 10.000 objetos aproximadamente. Además, la paginación se incluye para que pueda paginar los resultados.

### <a name="details-pane"></a>panel Detalles

Cuando seleccione un objeto de la vista de lista, la información acerca del objeto se muestra en el panel de detalles. En algunos casos, el panel de detalles incluye tareas de administración.

### <a name="me-tile-and-help"></a>Mosaico Yo y Ayuda

El mosaico **Yo** permite cerrar sesión en el EAC e iniciar sesión como un usuario diferente. Desde el menú desplegable en **Ayuda**![Icono de ayuda](../media/ITPro-EAC-HelpIcon.gif), puede realizar las siguientes acciones:

1. **Ayuda**: haga ![clic en](../media/ITPro-EAC-HelpIcon.gif) el icono ayuda para ver el contenido de la ayuda en línea.

2. **Deshabilitar la burbuja de ayuda**: la burbuja de ayuda muestra la ayuda contextual de los campos cuando se crea o edita un objeto. Puede desactivar el globo de Ayuda o activarlo si estaba deshabilitado.

3. **Copyright**: haga clic en este vínculo para leer el aviso de copyright de Exchange Online Protection.

4. **Privacidad**: haga clic para leer la Directiva de privacidad de Exchange Online Protection.

## <a name="supported-browsers"></a>Exploradores compatibles

Para conseguir la mejor experiencia con EAC, le recomendamos que use siempre la versión más actualizada de los exploradores, clientes de Office y aplicaciones. También le recomendamos que instale las actualizaciones de software cuando estén disponibles. Para obtener más información acerca de los navegadores compatibles y los requisitos del sistema para el servicio, vea [Requisitos del sistema de Office 365](https://go.microsoft.com/fwlink/p/?LinkID=402699).

## <a name="supported-languages-in-eop"></a>Idiomas admitidos en EOP

Los siguientes idiomas están disponibles y son compatibles con Exchange Online Protection.

- Amhárico

- Árabe

- Vasco (Euskera)

- Bengalí (India)

- Búlgaro

- Catalán

- Chino (simplificado)

- Chino (tradicional)

- Croata

- Checo

- Danés

- Neerlandés

- Neerlandés

- Inglés

- Estonio

- Filipino (Filipinas)

- Finés

- Francés

- Gallego

- Alemán

- Griego

- Gujarati

- Hebreo

- Hindi

- Húngaro

- Islandés

- Indonesio

- Italiano

- Japonés

- Kannada

- Kazajo

- Kiswahili

- Coreano

- Letón

- Lituano

- Malayo (Brunei Darussalam)

- Malayo (Malasia)

- Malayalam

- Maratí

- Noruego (Bokmal)

- Noruego (Nynorsk)

- Odia

- Persa

- Polaco

- Portugués (Brasil)

- Portugués (Portugal)

- Rumano

- Ruso

- Serbio (cirílico, Serbia)

- Serbio (latino)

- Eslovaco

- Esloveno

- Español

- Sueco

- Tamil

- Telugu

- Tailandés

- Turco

- Ucraniano

- Urdu

- Vietnamita

- Galés


