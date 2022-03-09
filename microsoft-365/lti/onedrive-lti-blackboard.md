---
title: Integrar Microsoft OneDrive LTI con Blackboard
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
description: Cree y cale las asignaciones, cree y cura el contenido del curso y colabore en archivos en tiempo real con la nueva Microsoft OneDrive Learning Tools Interoperability for Blackboard.
ms.openlocfilehash: 94e77181244bbf02115bd706e86751a9382b906b
ms.sourcegitcommit: a9266e4e7470e8c1e8afd31fef8d266f7849d781
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2022
ms.locfileid: "63406595"
---
# <a name="integrate-microsoft-onedrive-lti-with-blackboard"></a>Integrar Microsoft OneDrive LTI con Blackboard

La integración Microsoft OneDrive LTI con Blackboard es un proceso de dos pasos. El primer paso hace que el Microsoft OneDrive LTI esté disponible en los cursos de Blackboard y el segundo paso activa Microsoft OneDrive para Blackboard.

> [!IMPORTANT]
> La persona que realiza esta integración debe ser un administrador de Blackboard y un administrador del Microsoft 365 inquilino.

## <a name="recommended-browser-settings"></a>Configuración recomendada del explorador

- Las cookies deben permitirse para Microsoft OneDrive.
- Los elementos emergentes no deben bloquearse para Microsoft OneDrive.

> [!NOTE]
>
> - Las cookies no están permitidas de forma predeterminada en el modo de incógnito del explorador Chrome y tendrán que permitirse.
> - Microsoft OneDrive LTI funciona en modo privado en Microsoft Edge explorador. Asegúrese de que no ha bloqueado las cookies (que están permitidas de forma predeterminada).

## <a name="register-the-onedrive-lti-13-tool-in-blackboard"></a>Registrar la OneDrive LTI 1.3 en Blackboard

1. En el Panel de administrador de Blackboard, seleccione  **Proveedores de herramientas de LTI**.
2. Seleccione  **Registrar herramienta LTI 1.3**.
3. En el campo Id. de cliente, escriba o copie y pegue este identificador: ``78cd1b1c-ccbd-4318-9f90-22241f63b1f5``

  > [!NOTE]
  > Agregar este identificador de cliente configurará dos ubicaciones diferentes en Blackboard: una que permite el acceso a la herramienta desde el Mercado de contenido, libros y herramientas y el editor de texto enriquecido, y otra que permite el acceso a la herramienta desde el menú Agregar contenido en el curso en línea para cursos Ultra.

4. Seleccione **Enviar**.
5. Revise todas las opciones de configuración rellenadas previamente en la vista  **Estado**  de la herramienta  y asegúrese de que el botón de ronda Estado de la herramienta seleccionado esté  **aprobado**.
6. En  **Directivas de ininstitution**, seleccione las **casillas Rol en curso** y Nombre en los campos de usuario que se van a enviar. Todos los demás campos de usuario son opcionales, pero se recomienda dejarlos en a prueba en el futuro en la OneDrive instalación.
7. **Permitir acceso al servicio de calificaciones**   **andAllow membership service access** are also optional at this time but might be required for future updates to the LTI tool.
8. Copie el **identificador de implementación**. Lo necesitará para configurar la herramienta LTI de Microsoft.
9. Seleccione el **botón Enviar** para finalizar.

## <a name="configure-the-microsoft-lti-tool-to-work-with-blackboard"></a>Configurar la herramienta LTI de Microsoft para que funcione con Blackboard

1. Inicie sesión en el [Microsoft OneDrive de registro de LTI](https://onedrivelti.microsoft.com/admin).
2. Seleccione el **botón Consentimiento de** administrador y acepte los permisos.

> [!CAUTION]
> Si este paso no se realiza, el siguiente paso le dará un error y no podrá realizar este paso durante una hora una vez que haya recibido el error.

3. Seleccione el **botón Crear nuevo inquilino de LTI** .
4. En la página Registro de LTI, elija **Blackboard en** el desplegable Plataforma de consumidores de LTI y, a continuación, seleccione el **botón** Siguiente.
5. Pegue el **id. de** implementación que copió al registrar la herramienta en Blackboard y seleccione **Siguiente**.
6. Revise y guarde los cambios. Se mostrará un mensaje al registrarse correctamente.
7. Los detalles de registro también se pueden revisar seleccionando el botón Ver **inquilinos de LTI** en la página principal.

Después de completar estos pasos, los instructores podrán abrir documentos desde OneDrive cuando usen el menú "más" en la página Contenido del curso.

## <a name="recommended-content"></a>Contenido recomendado

[Integraciones de Microsoft para Blackboard](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Microsoft)

[Microsoft Teams integración de clases de Microsoft Teams](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Microsoft_Classes)
