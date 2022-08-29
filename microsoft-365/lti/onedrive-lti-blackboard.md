---
title: Uso de LTI de Microsoft OneDrive con Blackboard
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
ms.collection: m365initiative-edu
ms.localizationpriority: medium
description: Crear y calificar asignaciones, compilar y mantener contenido del curso, y colaborar en archivos en tiempo real con la nueva interoperabilidad de Herramientas de aprendizaje de Microsoft OneDrive para Blackboard.
ms.openlocfilehash: 2fd03732a9426bb13176dbfc16a7c996767f5430
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2022
ms.locfileid: "67388361"
---
# <a name="use-microsoft-onedrive-lti-with-blackboard"></a>Uso de LTI de Microsoft OneDrive con Blackboard

La integración de LTI de Microsoft OneDrive con Blackboard es un proceso de dos pasos. El primer paso hace que el LTI de Microsoft OneDrive esté disponible en los cursos de Blackboard y el segundo paso activa Microsoft OneDrive para Blackboard.

> [!IMPORTANT]
> La persona que realiza esta integración debe ser administrador de Blackboard y administrador del inquilino de Microsoft 365.

## <a name="recommended-browser-settings"></a>Configuración recomendada del explorador

- Se deben permitir cookies para Microsoft OneDrive.
- No se deben bloquear los elementos emergentes para Microsoft OneDrive.

> [!NOTE]
>
> - Las cookies no se permiten de forma predeterminada en el modo de incógnito del explorador Chrome y se deben permitir.
> - Microsoft OneDrive LTI funciona en modo privado en el explorador Microsoft Edge. Asegúrese de que no ha bloqueado las cookies (que están permitidas de forma predeterminada).

## <a name="register-the-onedrive-lti-13-tool-in-blackboard"></a>Registro de la herramienta OneDrive LTI 1.3 en Blackboard

1. En el Panel de administrador de Blackboard, seleccione **Proveedores de herramientas LTI**.
2. Seleccione **Register LTI 1.3 Tool (Registrar herramienta LTI 1.3).**
3. En el campo Id. de cliente, escriba o copie y pegue este identificador: ``78cd1b1c-ccbd-4318-9f90-22241f63b1f5``

   > [!NOTE]
   > Al agregar este identificador de cliente, se configurarán dos ubicaciones diferentes en Blackboard: una que permite el acceso a la herramienta desde el mercado de contenido, libros y herramientas y el editor de texto enriquecido, y otra que permite el acceso a la herramienta desde el menú Agregar contenido del curso en línea para cursos Ultra.

4. Seleccione **Enviar**.
5. Revise toda la configuración rellenada previamente en la vista Estado de la **herramienta** y asegúrese de que el botón de redondeo Estado de la **herramienta** seleccionado es **Aprobado**.
6. En **Directivas de institución**, seleccione las casillas **Rol en** curso y **Nombre** en los campos de usuario que se van a enviar. Todos los demás campos de usuario son opcionales, pero se recomienda dejarlos en para futuras pruebas de la instalación de OneDrive.
7. **Permitir el acceso al servicio de calificación** y **Permitir acceso al servicio de pertenencia** también son opcionales en este momento, pero podrían ser necesarios para futuras actualizaciones de la herramienta LTI.
8. Copie el **identificador de implementación**. Lo necesitará para configurar la herramienta LTI de Microsoft.
9. Seleccione el botón **Enviar** para finalizar.

## <a name="configure-the-microsoft-lti-tool-to-work-with-blackboard"></a>Configuración de la herramienta LTI de Microsoft para trabajar con Blackboard

1. Inicie sesión en el [Portal de registro de LTI de Microsoft OneDrive](https://onedrivelti.microsoft.com/admin).
2. Seleccione el botón **Administración Consentimiento** y acepte los permisos.

    > [!CAUTION]
    > Si no se realiza este paso, el siguiente paso le proporcionará un error y no podrá realizar este paso durante una hora una vez que haya recibido el error.

3. Seleccione el botón **Crear nuevo inquilino de LTI** .
4. En la página Registro de LTI, elija **Blackboard** en la lista desplegable Plataforma de consumidores de LTI y, a continuación, seleccione el botón **Siguiente** .
5. Pegue el **id. de implementación** que copió al registrar la herramienta en Blackboard y seleccione **Siguiente**.
6. Revise y guarde los cambios. Se mostrará un mensaje al registrarse correctamente.
7. Los detalles del registro también se pueden revisar seleccionando el botón **Ver inquilinos LTI** en la página principal.

Después de completar estos pasos, los instructores podrán abrir documentos desde OneDrive cuando usen el menú "más" en la página Contenido del curso.

## <a name="recommended-content"></a>Contenido recomendado

[Integraciones de Microsoft para Blackboard](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Microsoft)

[Integración de clases de Microsoft Teams](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Microsoft_Classes)
