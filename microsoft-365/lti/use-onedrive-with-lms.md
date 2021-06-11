---
title: Usar OneDrive interoperabilidad de herramientas de aprendizaje
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Cree y cale las asignaciones, cree y cura el contenido del curso y colabore en archivos en tiempo real con la nueva aplicación OneDrive Learning Tools Interoperability App.
ms.openlocfilehash: 97baf3e524e483e879d00f5e0c8495b450e13c92
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327803"
---
# <a name="use-microsoft-onedrive-with-your-learning-management-system"></a>Usar Microsoft OneDrive con el sistema de administración de aprendizaje

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Obtenga información sobre las ventajas de usar Microsoft OneDrive con su Sistema de administración de aprendizaje (LMS).

**Incluye Microsoft Office 365 directamente en los flujos de trabajo**

La aplicación Microsoft OneDrive Learning Tools Interoperability (LTI) se integra con su LMS para incluir Microsoft OneDrive y Microsoft Office 365 directamente en los flujos de trabajo más importantes que incluyen:

- Adjuntar recursos y organizar contenido.
- Iniciar documentos de colaboración.
- Creación y calificación de asignaciones.

**Proteger y cumplir completamente con los estándares LTI más recientes**

La Microsoft OneDrive LTI App es compatible con LTI 1.3 y LTI Advantage. Esta ventaja permite una experiencia de usuario altamente segura y estrechamente integrada.

**Experiencia de usuario moderna y enriquecte**

La Microsoft OneDrive LTI App aporta lo mejor de Microsoft directamente a tu experiencia de LMS. Estamos mejorando la integración de Office 365 existente en su LMS al ofrecer una experiencia de usuario más moderna, completa con un selector de archivos de Microsoft OneDrive nuevo y expandido y experiencias de edición más enriqueciendo para Office archivos. Microsoft también será el propietario completo de la Microsoft OneDrive LTI en el futuro, lo que significa que siempre recibirás lo último y lo mejor de Microsoft automáticamente.

La Microsoft OneDrive LTI app te permite:

- Adjunte Office 365 archivos, incluidos documentos de Word, PowerPoint presentaciones y Excel desde el Editor de contenido enriquecido.

- Distribuir Office 365 de nube.

- Vea y organice los archivos personales y Microsoft OneDrive curso.

- Cree colaboraciones donde los miembros del curso puedan trabajar juntos en documentos compartidos en tiempo real.

- Accede a varias Microsoft OneDrive, incluidas las cuentas personales y educativas.

- Integre Office 365 archivos con los módulos del curso.

- Use su cuenta microsoft para el inicio de sesión único con su LMS.

## <a name="integrate-with-canvas"></a>Integrar con Canvas

La persona que realiza esta integración debe ser un administrador de Canvas y un administrador del Microsoft 365 inquilino.

1. Inicie sesión en el portal Microsoft Azure con la cuenta de administrador de inquilinos. El administrador de inquilinos de Azure también debe tener el rol de administrador de grupo.

    ![administrador de grupo resaltado](../media/lti-media/lti-group-admin.png)

2. Inicie sesión en el portal [OneDrive LTI de](https://odltiappnl.azurewebsites.net/admin)Microsoft.

3. Acepte los permisos para completar el inicio de sesión.

    ![aceptar permisos](../media/lti-media/lti-permissions.png)

4. Seleccione **Agregar inquilino LTI**.

     ![agregar inquilino de LTI](../media/lti-media/lti-add-tenant.png)

5. Selecciona **Plataforma de consumidor de LTI** como **Lienzo** en el desplegable.

6. Seleccione **Dirección URL base de Canvas** y, a continuación, seleccione **Siguiente**.

    ![seleccione Canvas y agregue la dirección URL base](../media/lti-media/lti-canvas-base-url.png)

   En la siguiente pantalla se muestran los campos que son confidenciales para usted.

7. Seleccione **Siguiente** de ?? página. ¿LOS REVISORES PUEDEN RELLENAR EL ESPACIO EN BLANCO AQUÍ?

8. Seleccione **Siguiente** en la pantalla que muestra información confidencial para usted.

   La pantalla final de Azure Portal muestra los pasos siguientes para agregar la instancia de Canvas.

9. Copia las claves de desarrollador de esta pantalla. Lo usarás al crear la instancia de Canvas.

## <a name="add-the-canvas-instance"></a>Agregar la instancia de Canvas

1. En la instancia de Canvas, anule la selección de **Claves de desarrollador** de  >  **administración**.

2. Elija **Clave LTI en** la lista desplegable en Clave de **desarrollador**.

   ![Obtener las claves de desarrollador de LTI](../media/lti-media/lti-developer-keys.png)

3. Pegue las claves de desarrollador aquí.

     ![Pegar las claves de desarrollador](../media/lti-media/lti-developer-keys.png)

   La clave se crea en **modo OFF**

   ![Las claves de desarrollador creadas en modo desactivado](../media/lti-media/lti-copy-developer-keys.png)

4. Copie el texto resaltado.
    Esto sirve como identificador de cliente en Microsoft OneDrive portal LTI.

5. Pegue el texto en el **campo Id.** de cliente en Microsoft OneDrive portal LTI y, a continuación, **seleccione Siguiente**.

6. Seleccione **Guardar**.

7. Para ver la configuración, seleccione **Ver inquilinos de LTI**.
