---
title: Introducción al centro de temas en Temas de Microsoft Viva
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
ROBOTS: ''
localization_priority: None
description: Obtenga información sobre el centro de temas en Temas de Microsoft Viva.
ms.openlocfilehash: bd3bdbc368ca95b1c795043c5c083aaebfcf5742
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287286"
---
# <a name="topic-center-overview-in-microsoft-viva-topics"></a>Introducción al centro de temas en Temas de Microsoft Viva

En Temas de Microsoft Viva, el centro de temas es un sitio SharePoint moderno que sirve como centro de conocimientos para su organización. Se crea durante la configuración [de Viva Topics](set-up-topic-experiences.md) en el Centro de administración de Microsoft 365.

El centro de temas tiene una página principal predeterminada con el elemento web **Temas** donde todos los usuarios con licencia pueden ver los temas a los que tienen una conexión.

Aunque todos los usuarios con licencia que puedan ver temas tendrán acceso al centro de temas, los administradores de conocimientos también pueden administrar los temas a través de la página Administrar **temas.** La **pestaña Administrar temas** solo se mostrará a los usuarios que tengan permisos Administrar temas.

## <a name="where-is-my-topic-center"></a>Dónde está mi centro de temas

El centro de temas se crea durante la instalación de Viva Topics. Una vez completada la instalación, un administrador puede encontrar la dirección URL en la [página de administración del centro de temas.](./topic-experiences-administration.md#to-access-topics-management-settings)


1. En el Centro de administración de Microsoft 365, seleccione **Configuración** y, a continuación, seleccione **Configuración de la organización**.
2. En la **pestaña Servicios,** seleccione **Experiencias del tema**.

    ![Conectar personas al conocimiento](../media/admin-org-knowledge-options-completed.png)

3. Seleccione la **pestaña Centro de** temas. En **Dirección del sitio** es un vínculo al centro de temas.

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-center.png)

## <a name="home-page"></a>Página principal

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LAhZ]

</br>

En la página principal del centro de temas, puede ver los temas de su organización a los que tiene una conexión.

- Conexiones sugeridas: verá los temas enumerados en **We've listed you on these topics. ¿Lo hemos hecho bien?** Estos son temas en los que se ha sugerido la conexión al tema a través de la IA. Por ejemplo, puede ser un autor de un archivo o sitio relacionado. Se le pedirá que confirme que debe mantenerse en la lista como una persona relacionada para el tema.

   ![Conexiones sugeridas](../media/knowledge-management/my-topics.png)

- Conexiones confirmadas: se trata de temas en los que está anclado en la página del tema o ha confirmado una conexión sugerida al tema. Los temas pasarán de la sección sugerida a confirmada cuando confirme una conexión sugerida.

   ![Temas confirmados](../media/knowledge-management/my-topics-confirmed.png)

Una vez que un usuario confirma su conexión a un tema, el usuario puede realizar modificaciones en la página del tema para seleccionar su conexión. Por ejemplo, pueden proporcionar más información sobre su conexión con el tema.

## <a name="manage-topics-page"></a>Página Administrar temas

Para trabajar en la página **Administrar temas** del centro de temas, debe tener los permisos necesarios administrar temas necesarios para el rol de administrador de conocimientos. El administrador puede asignar estos permisos a los usuarios durante [](topic-experiences-knowledge-rules.md) la configuración de [Temas de Viva,](set-up-topic-experiences.md)o un administrador puede agregar nuevos usuarios después a través del Centro de administración de Microsoft 365.

En la **página Administrar temas,** el panel de temas muestra todos los temas, a los que tiene acceso, que se identificaron desde las ubicaciones de origen especificadas. Cada tema mostrará la fecha en que se descubrió el tema. Un usuario al que se asignaron permisos administrar temas puede revisar los temas no confirmados y elegir:

- Confirmar el tema: indica a los usuarios que un curador humano validó un tema sugerido por IA.

- Publicar el tema: edite la información del tema para mejorar la calidad del tema que se identificó inicialmente y resalta el tema para todos los usuarios que tienen acceso a temas.

- Quitar el tema: hace que el tema no se pueda detectar para los usuarios finales. El tema se mueve a la **pestaña Quitado** y se puede confirmar más adelante si es necesario.

Para obtener más información sobre cómo administrar temas en la página Administrar **temas,** vea [Administrar temas](manage-topics.md).

## <a name="create-or-edit-a-topic"></a>Crear o editar un tema

Si tiene permisos crear y editar temas, puede:

- [Editar temas existentes:](edit-a-topic.md)puede realizar cambios en las páginas de temas existentes que se crearon mediante la detección.

- [Crear nuevos temas:](create-a-topic.md)puede crear nuevos temas para los que no se encontraron a través de la detección, o si las herramientas de inteligencia artificial no encontraron suficiente evidencia para crear un tema.

## <a name="see-also"></a>Vea también

[Administrar temas en el centro de temas](manage-topics.md)
