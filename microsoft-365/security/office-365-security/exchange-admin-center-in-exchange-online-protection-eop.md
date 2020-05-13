---
title: Centro de administración de Exchange en EOP independiente
f1.keywords:
- NOCSH
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
description: Obtenga información sobre la interfaz de administración web en la protección independiente de Exchange Online (EOP).
ms.openlocfilehash: 378754f2565604236f7ac33e471d1f991238d304
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209744"
---
# <a name="exchange-admin-center-in-standalone-eop"></a>Centro de administración de Exchange en EOP independiente

El centro de administración de Exchange (EAC) es una consola de administración basada en web para la protección independiente de Exchange Online (EOP).

¿Está buscando la versión de Exchange Online de este tema? Vea [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

## <a name="open-the-eac-in-eop"></a>Abrir el EAC en EOP

Los clientes de EOP independientes pueden tener acceso al EAC mediante los métodos siguientes:

- **En el centro de administración de Microsoft 365**:

  1. Vaya a <https://admin.microsoft.com> y haga clic en **Mostrar todo**.

     ![Haga clic en Mostrar todo en el centro de administración de Microsoft 365](../../media/m365-center-show-all.png)

  2. En la sección **centros de administración** que aparece, haga clic en **todos los centros de administración**.

     ![Haga clic en todos los centros de administración en el centro de administración de Microsoft 365](../../media/m365-center-select-all-admin-centers.png)

  3. En la página **todos los centros de administración** que aparece, haga clic en **protección en línea de Exchange**.

- Ir directamente a `https://admin.protection.outlook.com/ecp/` .

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a>Elementos comunes de la interfaz de usuario en el EAC en EOP

En esta sección se describen los elementos de la interfaz de usuario del EAC.

![EOP: AdminCenter](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a>Panel de características

Este es el primer nivel de navegación para la mayoría de las tareas que realizará en el EAC. El panel de características se organiza por áreas.

- **Destinatarios**: aquí es donde se ven los grupos y los contactos externos.

- **Permisos**: aquí donde podrá administrar los roles de administrador.

- **Administración de cumplimiento**: aquí es donde encontrará el informe de grupo de roles de administrador y el registro de auditoría de administrador.

- **Protección**: aquí puede administrar las directivas antimalware, la Directiva de filtro de conexión predeterminada y DKIM.

  > [!NOTE]
  > Debe administrar las directivas antimalware y la Directiva de filtro de conexión predeterminada en el centro de seguridad & cumplimiento. Para obtener más información, vea [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) y [Configure Connection Filtering in EOP](configure-the-connection-filter-policy.md).

- **Flujo de correo**: aquí es donde administrará las reglas de flujo de correo (también conocidas como reglas de transporte), dominios aceptados y conectores, así como donde puede ir a ejecutar seguimiento de mensajes.

- **Híbrido**: aquí puede ejecutar el [Asistente para la configuración híbrida](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)y donde puede instalar el [módulo de PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell).

### <a name="tabs"></a>Pestañas

Las pestañas son el segundo nivel de navegación. Las áreas de características contienen varias pestañas y cada área representa a una característica.

### <a name="toolbar"></a>Barra de herramientas

Al hacer clic en la mayoría de las pestañas, verá una barra de herramientas. La barra de herramientas tiene iconos que realizan una acción específica. La siguiente tabla describe los iconos y sus acciones.

||||
|---|---|---|
|**Icono**|**Nombre**|**Action**|
|![Agregar icono](../../media/ITPro-EAC-AddIcon.gif)|Agregar, nuevo|Utilice este icono para crear un nuevo objeto. Algunos de estos iconos tienen una flecha hacia abajo asociada donde puede hacer clic para mostrar objetos adicionales que puede crear.|
|![Icono Editar](../../media/ITPro-EAC-EditIcon.gif)|Editar|Utilice este icono para editar un objeto.|
|![Eliminar icono](../../media/ITPro-EAC-DeleteIcon.gif)|Eliminar|Utilice este icono para eliminar un objeto. Algunos iconos eliminados tienen una flecha hacia abajo donde puede hacer clic para mostrar opciones adicionales.|
|![icono de Buscar](../../media/ITPro-EAC-.gif)|Búsqueda|Usar este icono para abrir una casilla de búsqueda donde puede escribir una frase de búsqueda para el objeto que desee encontrar.|
|![Icono Actualizar](../../media/ITPro-EAC-RefreshIcon.gif)|Actualizar|Utilice este icono para actualizar la vista de lista.|
|![Icono Más opciones](../../media/ITPro-EAC-MoreOptionsIcon.gif)|Más opciones|Use este icono para ver más acciones que puede realizar para los objetos de la pestaña. Por ejemplo, al hacer clic en este icono en **Destinatarios \> Usuarios**, se muestra la opción para realizar una **Búsqueda avanzada**.  |
|![Icono flecha arriba](../../media/ITPro-EAC-UpArrowIcon.gif)![Icono flecha abajo](../../media/ITPro-EAC-DownArrowIcon.gif)|Flecha hacia arriba y flecha hacia abajo|Utilice estos iconos para mover la prioridad de un objeto hacia arriba o hacia abajo.|
|![Icono de quitar](../../media/ITPro-EAC-RemoveIcon.gif)|Quitar|Utilice este icono para quitar objetos de la lista.|
|

### <a name="list-view"></a>Vista de lista

Cuando seleccione una pestaña, en la mayoría de los casos verá la vista de lista. El límite de visualización de la vista de lista del EAC es de 10.000 objetos aproximadamente. Además, la paginación se incluye para que pueda paginar los resultados.

### <a name="details-pane"></a>panel Detalles

Cuando seleccione un objeto de la vista de lista, la información acerca del objeto se muestra en el panel de detalles. En algunos casos, el panel de detalles incluye tareas de administración.

### <a name="me-tile-and-help"></a>Mosaico Yo y Ayuda

El mosaico **Yo** permite cerrar sesión en el EAC e iniciar sesión como un usuario diferente. Desde el menú desplegable en **Ayuda**![Icono de ayuda](../../media/ITPro-EAC-HelpIcon.gif), puede realizar las siguientes acciones:

- **Ayuda**: haga clic en ![ el icono ayuda ](../../media/ITPro-EAC-HelpIcon.gif) para ver el contenido de la ayuda en línea.

- **Comentarios**: dejar comentarios.

- **Comunidad**: publique una pregunta para encontrar respuestas en los foros de la comunidad.

- **Deshabilitar la burbuja de ayuda**: la burbuja de ayuda muestra la ayuda contextual de los campos cuando se crea o edita un objeto. Puede desactivar el globo de Ayuda o activarlo si estaba deshabilitado.

- **Mostrar registro de comandos**: se abre una nueva ventana que muestra los comandos de PowerShell equivalentes en función de lo que haya configurado en el EAC.

## <a name="supported-browsers"></a>Exploradores compatibles

Para conseguir la mejor experiencia con EAC, le recomendamos que use siempre la versión más actualizada de los exploradores, clientes de Office y aplicaciones. También le recomendamos que instale las actualizaciones de software cuando estén disponibles. Para obtener más información acerca de los exploradores compatibles y los requisitos del sistema para el servicio, vea [System Requirements for Office](https://products.office.com/office-system-requirements).

## <a name="supported-languages"></a>Idiomas admitidos

Los siguientes idiomas son compatibles y están disponibles para el EAC en un EOP independiente.

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
