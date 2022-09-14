---
title: Crear y administrar etiquetas de dispositivos
description: Uso de etiquetas de dispositivo para agrupar dispositivos para capturar contexto y habilitar la creación dinámica de listas como parte de un incidente
keywords: etiquetas, etiquetas de dispositivo, grupos de dispositivos, grupos, corrección, nivel, reglas, grupo de aad, rol, asignación, clasificación
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: cd5fcbf5142926da0d3bef2753b08a560414ab44
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67683151"
---
# <a name="create-and-manage-device-tags"></a>Crear y administrar etiquetas de dispositivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Agregue etiquetas en los dispositivos para crear una afiliación de grupos lógica. Las etiquetas de dispositivo son compatibles con la asignación adecuada de la red, lo que permite adjuntar diferentes etiquetas para capturar contexto y habilitar la creación de listas dinámicas como parte de un incidente. Las etiquetas se pueden usar como filtro en la vista **Inventario de** dispositivos o para agrupar dispositivos. Para obtener más información sobre la agrupación de dispositivos, consulte [Creación y administración de grupos de dispositivos](machine-groups.md).

Puede agregar etiquetas en dispositivos de las siguientes maneras:

- Usando el portal
- Estableciendo un valor de clave de registro

> [!NOTE]
> Puede haber cierta latencia entre el momento en que se agrega una etiqueta a un dispositivo y su disponibilidad en la lista de dispositivos y la página del dispositivo.

Para agregar etiquetas de dispositivo con la API, consulte [API para agregar o quitar etiquetas de dispositivo](add-or-remove-machine-tags.md).

## <a name="add-and-manage-device-tags-using-the-portal"></a>Agregar y administrar etiquetas de dispositivo con el portal

1. Seleccione el dispositivo en el que quiere administrar las etiquetas. Puede seleccionar o buscar un dispositivo desde cualquiera de las siguientes vistas:

   - **Panel de operaciones de seguridad** : seleccione el nombre del dispositivo en la sección Dispositivos principales con alertas activas.
   - **Cola de alertas**: seleccione el nombre del dispositivo junto al icono de dispositivo en la cola de alertas.
   - **Inventario de dispositivos** : seleccione el nombre del dispositivo en la lista de dispositivos.
   - **Cuadro de búsqueda**: seleccione Dispositivo en el menú desplegable y escriba el nombre del dispositivo.

     También puede acceder a la página de la alerta a través del archivo y las vistas IP.

2. Seleccione **Administrar etiquetas** en la fila de Acciones de respuesta.

    :::image type="content" source="images/manage-tags-option.png" alt-text="Imagen del botón Administrar etiquetas" lightbox="images/manage-tags-option.png":::
    

3. Escriba para buscar o crear etiquetas

    :::image type="content" source="images/create-new-tag.png" alt-text="Adición de etiquetas en device1" lightbox="images/create-new-tag.png":::

Las etiquetas se agregan a la vista de dispositivo y también se reflejarán en la vista **de inventario Dispositivos** . A continuación, puede usar el filtro **Etiquetas** para ver la lista pertinente de dispositivos.

> [!NOTE]
> Es posible que el filtrado no funcione en nombres de etiquetas que contengan paréntesis.
>
> Al crear una nueva etiqueta, se muestra una lista de etiquetas existentes. La lista solo muestra las etiquetas creadas a través del portal. No se mostrarán las etiquetas existentes creadas a partir de dispositivos cliente.

También puede eliminar etiquetas de esta vista.

:::image type="content" source="images/new-tag-label-display.png" alt-text="Adición de etiquetas en device2" lightbox="images/new-tag-label-display.png":::

## <a name="add-device-tags-by-setting-a-registry-key-value"></a>Agregar etiquetas de dispositivo estableciendo un valor de clave del Registro

> [!NOTE]
> Solo se aplica en los siguientes dispositivos:
>
> - Windows 11
> - Windows 10, versión 1709 o posterior
> - Windows Server, versión 1803 o posterior
> - Windows Server 2016
> - Windows Server 2012 R2
> - Windows Server 2008 R2 SP1
> - Windows 8.1
> - Windows 7 SP1

> [!NOTE]
> El número máximo de caracteres que se pueden establecer en una etiqueta es 200.

Los dispositivos con etiquetas similares pueden ser útiles cuando necesite aplicar acciones contextuales en una lista específica de dispositivos.

Use la siguiente entrada de clave del Registro para agregar una etiqueta en un dispositivo:

- Clave del Registro: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`
- Valor de clave del Registro (REG_SZ): `Group`
- Datos de clave del Registro: `Name of the tag you want to set`

> [!NOTE]
> La etiqueta de dispositivo forma parte del informe de información del dispositivo que se genera una vez al día. Como alternativa, puede optar por reiniciar el punto de conexión que transferiría un nuevo informe de información del dispositivo.
>
> Si necesita quitar una etiqueta que se agregó con la clave del Registro anterior, borre el contenido de los datos de clave del Registro en lugar de quitar la clave "Group".
