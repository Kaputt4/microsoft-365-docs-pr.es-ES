---
title: Administrador de cumplimiento de Microsoft y RGPD
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: El Administrador de cumplimiento de Microsoft es una herramienta gratuita de evaluación de riesgos basada en flujos de trabajo en el Portal de confianza de servicios de Microsoft. El Administrador de cumplimiento le permite realizar un seguimiento, asignar y comprobar las actividades de cumplimiento normativo relacionadas con los servicios en la nube de Microsoft.
ms.openlocfilehash: 69e6551620fb654cb09d46554e6e3c98b6a2fc60
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595807"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a>Administrador de cumplimiento de Microsoft y RGPD

El Reglamento general de protección de datos (RGPD) que aprueba la Unión Europea puede afectar a su estrategia de cumplimiento y exige acciones específicas para administrar la información de los usuarios y los clientes que se usa en el Administrador de cumplimiento.

## <a name="user-privacy-settings"></a>Configuración de privacidad del usuario

Algunas normativas requieren que una organización pueda eliminar los datos del historial de usuarios. El Administrador de cumplimiento proporciona **funciones de configuración de privacidad** del usuario que permiten a los administradores:
  
- [Buscar un usuario](#search-for-a-user)
- [Exportar un informe de historial de datos de cuenta](#export-a-report-of-account-data-history)
- [Eliminar el historial de datos de usuarios](#delete-user-data-history)
  
## <a name="search-for-a-user"></a>Buscar un usuario

Para buscar una cuenta de usuario:
  
1. Escriba el alias de correo electrónico del usuario (la información a la izquierda del símbolo @) y elija el nombre de dominio de la lista de sufijos de dominio de la derecha. Para organizaciones con varios dominios registrados, compruebe el sufijo del nombre de dominio para asegurarse de que es correcto.

2. Cuando haya escrito correctamente el nombre de usuario, seleccione **Buscar**.

3. Para las cuentas de usuario no devueltas, la página muestra **Usuario no encontrado.** Compruebe la información de la dirección de correo electrónico del usuario y realice las correcciones necesarias. Para reintentar, seleccione **Buscar**.

4. Para las cuentas de usuario devueltas, el texto del botón cambia de **Buscar** a **Borrar**. Esto indica que la cuenta de usuario devuelta es el contexto operativo para las funciones adicionales y que estas funciones se aplican a esta cuenta de usuario.

5. Para borrar los resultados de la búsqueda y buscar un usuario diferente, seleccione **Borrar**.

## <a name="export-a-report-of-account-data-history"></a>Exportar un informe de historial de datos de cuenta

Para cada cuenta de usuario identificada, puede generar un informe de dependencias vinculadas a la cuenta. Esta información le permite reasignar elementos de acción abiertos o garantizar el acceso a evidencias cargadas anteriormente.
  
 Para generar y exportar un informe:
  
1. Seleccione **Exportar** para generar y descargar un informe de acciones de control del Administrador de cumplimiento asignada actualmente a la cuenta de usuario devuelta y la lista de documentos cargados por ese usuario. Si no hay acciones asignadas ni documentos cargados, un mensaje de error indica "No hay datos para este usuario".

2. El informe se descarga en segundo plano de la ventana activa del explorador: si no ve un elemento emergente de descarga que desea comprobar el historial de descargas del explorador.

3. Abra el documento para revisar los datos del informe.

> [!IMPORTANT]
> Los datos del informe no son una lista histórica que conserva y muestra los cambios de estado en el historial de asignaciones de elementos de acción. El informe generado es una instantánea de los elementos de acción de control asignados en el momento en que se ejecuta el informe (marca de fecha y hora escrita en el informe). Por ejemplo, cualquier reasignación posterior de elementos de acción dará como resultado datos de informe de instantáneas diferentes si el informe se vuelve a generar para el mismo usuario.
  
## <a name="delete-user-data-history"></a>Eliminar el historial de datos de usuarios

Establece todos los elementos de acción de control asignados al usuario devuelto en "sin asignar". Establece el **valor cargado por** los documentos cargados por el usuario devuelto en "usuario quitado".
  
Para eliminar el elemento de acción de la cuenta de usuario y el historial de carga de documentos:
  
1. Seleccione **Eliminar**.

    Se muestra un cuadro de diálogo de confirmación: " Se quitan todas las asignaciones de elementos de acción de control y el historial de carga de documentos *para el usuario seleccionado. Esta acción es permanente. ¿Está seguro de que desea continuar?*"

2. Para continuar, **seleccione Aceptar**; de lo contrario, **seleccione Cancelar**.
