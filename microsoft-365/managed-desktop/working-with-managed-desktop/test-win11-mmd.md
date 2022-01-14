---
title: Vista previa y prueba de Windows 11 con Escritorio administrado de Microsoft
description: Cómo obtener Windows 11 en su entorno
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7c5526e532f14fc00ed52a6d260c017d0a019bae
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2022
ms.locfileid: "62035467"
---
# <a name="preview-and-test-windows-11-with-microsoft-managed-desktop"></a>Vista previa y prueba de Windows 11 con Escritorio administrado de Microsoft

 Cómo inscribirse y participar en el programa de pruebas de Windows 11 en el entorno de Escritorio administrado de Microsoft. Para obtener más información Windows 11 y Microsoft Managed Desktop en general, vea [Windows 11 y Microsoft Managed Desktop](../intro/win11-overview.md). 

## <a name="add-devices-to-the-windows-11-test-group"></a>Agregar dispositivos al grupo Windows 11 pruebas

A petición, crearemos el grupo de dispositivos (**Modern Workplace - Windows 11 Pre-Release Test Devices**) para probar y evaluar Windows 11. Los dispositivos de este grupo obtienen nuevas Windows 11 compilaciones y configuraciones de línea base de Escritorio administrado de Microsoft a medida que están disponibles y se supervisan para problemas de confiabilidad.

Puedes elegir cualquiera de los dispositivos existentes o nuevos para las pruebas de Windows 11, pero no debes inscribir dispositivos de producción en este grupo debido al elevado riesgo de defectos o problemas de compatibilidad en compilaciones previas a la versión. Las asignaciones de grupo de dispositivos anteriores se quitan tras la asignación a este grupo.

Para inscribir los dispositivos en el grupo de pruebas de versión previa:

1. Abra una nueva solicitud de servicio con el equipo de Ingeniería del servicio de escritorio administrado de Microsoft.
2. Use estos valores para los campos:
    - Título: inscripción Windows compatibilidad de 11
    - Tipo de solicitud: Solicitud de cambio
    - Categoría: dispositivos
    - Subcategoría: asignación de grupo de implementación
3. En el campo descripción, enumera los números de serie de los dispositivos que quieres usar para Windows 11 pruebas. Ten en cuenta que, si hay alguno, de los dispositivos especificados aún no están implementados en el inquilino de Microsoft Managed Desktop.

## <a name="prioritize-applications-to-submit-to-test-base"></a>Priorizar las aplicaciones que se deben enviar a Test Base

Las aplicaciones críticas para la empresa son las mejores candidatas para obtener más validación en un entorno Windows 11. Podemos ayudarte a priorizar las aplicaciones para Windows 11 pruebas basadas en datos de uso y confiabilidad. Para solicitar nuestras recomendaciones, siga estos pasos:

1. Abra una nueva solicitud de servicio con el equipo de Ingeniería del servicio de escritorio administrado de Microsoft. Si necesitas más información sobre cómo presentar la solicitud, consulta [Admin support](admin-support.md).
2. Use estos valores para los campos:
    - Título: Windows 11 candidatos de base de prueba
    - Tipo de solicitud: Solicitud de información
    - Categoría: Aplicaciones
    - Subcategoría: Otros

## <a name="report-issues"></a>Informar sobre problemas

Si encuentras Windows 11 problemas de compatibilidad con tus aplicaciones de línea de negocio o Microsoft 365, dennos informes para investigación y corrección. Para informar de un problema, siga estos pasos:

1. Abra una nueva solicitud de servicio con el equipo de Ingeniería del servicio de escritorio administrado de Microsoft.
2. Use estos valores para los campos:
    - Título: Windows 11 pruebas de compatibilidad
    - Tipo de solicitud: Incidente
    - Categoría: dispositivos
    - Subcategoría: Windows upgrade/update
3. Describa el comportamiento y la gravedad con la que esto dificultaría su negocio en un entorno de producción.

Microsoft Managed Desktop procesa y administra problemas con compilaciones de versión previa en función del efecto en la productividad. Aunque nuestra descripción del servicio no cubre los problemas con las compilaciones de versión previa, conferimos a los administradores de clientes para garantizar que los problemas que bloquean la productividad de los usuarios se resuelvan antes de iniciar la migración en cualquier espacio empresarial determinado.
