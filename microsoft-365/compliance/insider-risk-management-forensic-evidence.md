---
title: Más información sobre las pruebas forenses de administración de riesgos internos (versión preliminar)
description: Obtenga información sobre las pruebas forenses de administración de riesgos internos en Microsoft Purview. Las pruebas forenses son una herramienta de investigación para ver la actividad del usuario capturada para ayudar a determinar si las acciones del usuario suponen un riesgo y pueden provocar un incidente de seguridad.
keywords: Microsoft 365, Microsoft Purview, riesgo interno, administración de riesgos, cumplimiento
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 484da1e07de1a160149f2a1159b5610a3d22192f
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68639028"
---
# <a name="learn-about-insider-risk-management-forensic-evidence-preview"></a>Más información sobre las pruebas forenses de administración de riesgos internos (versión preliminar)

>[!IMPORTANT]
>Administración de riesgos internos de Microsoft Purview correlaciona varias señales para identificar posibles riesgos internos malintencionados o involuntarios, como el robo de IP, la pérdida de datos y las infracciones de seguridad. La administración de riesgos internos permite a los clientes crear directivas para administrar la seguridad y el cumplimiento. Creados con privacidad por diseño, los usuarios se seudonimizan de forma predeterminada y los controles de acceso basados en roles y los registros de auditoría están en su lugar para ayudar a garantizar la privacidad del nivel de usuario.

Tener contexto visual es fundamental para que los equipos de seguridad durante las investigaciones forenses obtengan mejor información sobre las actividades de usuario potencialmente relacionadas con la seguridad. Con desencadenadores de eventos personalizables y controles integrados de protección de la privacidad del usuario, la evidencia forense permite capturar actividades visuales personalizables en todos los dispositivos para ayudar a su organización a mitigar, comprender y responder mejor a posibles riesgos de datos, como la filtración de datos no autorizados de datos confidenciales. Establezca las directivas adecuadas para su organización, incluidos los eventos de riesgo que son la prioridad más alta para capturar pruebas forenses, qué datos son más confidenciales y si se notifica a los usuarios cuando se activa la captura forense. La captura de pruebas forenses está desactivada de forma predeterminada y la creación de directivas requiere una autorización doble.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="feature-capabilities"></a>Funcionalidades de características

- **La captura visual** permite a las organizaciones capturar clips de actividades de usuario clave relacionadas con la seguridad, lo que permite una visibilidad más segura o compatible y satisface las necesidades de la organización.
- **Protección de la privacidad del usuario** a través de varios niveles de aprobación para la activación de la característica de captura.
- **Los desencadenadores personalizables y las opciones de captura** significan que los equipos de seguridad pueden configurar pruebas forenses para satisfacer sus necesidades, ya sea en función de incidentes (por ejemplo, *capture 5 minutos antes y 10 minutos después de que un usuario haya descargado "SecretResearchPlans.docx")* o en función de las necesidades de captura continua.
- **La segmentación de directivas centrada en el usuario** significa que los equipos de seguridad y cumplimiento pueden centrarse en la actividad del usuario, no en el dispositivo, para obtener una mejor información contextual.
- **Los fuertes controles de acceso basado en roles (RBAC)** significan que la capacidad de configurar y revisar clips forenses está estrechamente controlada y solo está disponible para los usuarios de la organización con los permisos adecuados.
- **Integración profunda con las características actuales de administración de riesgos** internos, lo que facilita la incorporación y los flujos de trabajo más familiares para los administradores de administración de riesgos internos y un enfoque de una sola plataforma de confianza.

## <a name="capturing-options"></a>Opciones de captura

[Desencadenar eventos, indicadores globales e indicadores de políticas](/microsoft-365/compliance/insider-risk-management-settings#indicators) desempeña un papel importante en todas las directivas de administración de riesgos internos, incluidas las políticas de pruebas forenses. Los eventos desencadenantes son acciones de usuario que determinan si los usuarios entran en el ámbito de la evaluación en las directivas de administración de riesgos internos. Los indicadores de configuración global se usan para determinar qué actividades recopila la administración de riesgos internos. Los indicadores de directiva se usan para determinar una puntuación de riesgo para un usuario dentro del ámbito.

Dependiendo de cómo su organización decida configurar pruebas forenses, hay dos opciones de captura:

- **Actividades específicas**: esta opción de directiva captura la actividad solo cuando un evento desencadenante ha puesto a un usuario aprobado en el ámbito de la directiva de pruebas forenses y cuando se detectan las condiciones de un indicador de directiva para el usuario. Por ejemplo, un usuario aprobado para la captura de pruebas forenses se incluye en el ámbito de la directiva de pruebas forenses y el usuario copia los datos en servicios de almacenamiento en la nube personales o dispositivos de almacenamiento portátiles. La captura se limita solo al período de tiempo configurado cuando el usuario copia los datos en el servicio de almacenamiento en la nube personal o en el dispositivo de almacenamiento portátil. Las capturas de esta opción estarán disponibles para su revisión en la pestaña **Pruebas forenses (versión preliminar)** del panel **Alertas** .
- **Todas las actividades**: esta opción de directiva captura cualquier actividad realizada por los usuarios. Esto incluye el movimiento del mouse, las pulsaciones de teclas y todas las actividades definidas por indicadores de riesgo internos. Por ejemplo, la organización tiene una necesidad de capturar actividades con un tiempo sensible para un usuario aprobado que participa activamente en actividades potencialmente de riesgo que pueden dar lugar a un incidente de seguridad. Es posible que los indicadores de directiva no hayan alcanzado el umbral para que la directiva genere una alerta y es posible que la actividad potencialmente de riesgo no esté documentada. La ayuda de captura continua evita que la actividad potencialmente arriesgada se pierda o no se detecte. Las capturas de esta opción estarán disponibles para su revisión en la pestaña **Pruebas forenses (versión preliminar)** del panel **Informes de actividad de usuario (versión preliminar).**

>[!IMPORTANT]
>Los clips de pruebas forenses se eliminan 120 días después de su captura o al final del período de vista previa, lo que sea antes. Puede descargar o transferir clips de evidencia forense antes de que se eliminen.

## <a name="workflow"></a>Flujo de trabajo

El flujo de trabajo general para detectar, investigar y corregir alertas que contienen captura de clip sigue los [mismos pasos básicos](/microsoft-365/compliance/insider-risk-management#workflow) que otras directivas de administración de riesgos internos. Sin embargo, hay algunas diferencias notables para la evidencia forense cuando se configura en su organización:

- **Los usuarios sujetos a captura deben tener solicitudes y aprobaciones de captura explícitas**: se trata de un proceso adicional que no se incluye como parte de la configuración de otras directivas de administración de riesgos internos. Los usuarios asignados a los grupos de roles *Insider Risk Management* o *Insider Risk Management* deben enviar una solicitud a los usuarios asignados al grupo de roles *Aprobadores de Insider Risk Management* antes de que cualquier usuario de su organización sea apto para cualquier opción de captura de clips. Por ejemplo, este requisito ayuda a admitir escenarios organizativos en los que los administradores de administración de riesgos internos deben obtener la aprobación explícita del personal legal o de recursos humanos designado antes de habilitar la captura para cualquier usuario.
- **Los dispositivos deben incorporarse y tener instalado el cliente de Microsoft Purview**: para que las pruebas forenses puedan recopilar y almacenar clips capturados para los usuarios aptos, sus dispositivos deben incorporarse al portal de cumplimiento Microsoft Purview. Además, cada dispositivo debe tener instalado el cliente de Microsoft Purview. Estos requisitos previos permiten la compatibilidad con la captura de dispositivos en línea y sin conexión.

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

- Consulte [Introducción a las pruebas forenses de administración de riesgos](/microsoft-365/compliance/insider-risk-management-forensic-evidence-configure) internos para obtener instrucciones paso a paso para configurar la captura de pruebas forenses en su organización.
- Consulte [Introducción a la administración de riesgos](/microsoft-365/compliance/insider-risk-management-configure) internos para configurar requisitos previos, crear directivas y empezar a recibir alertas.
