---
title: Microsoft Defender para Empresas guía del usuario de prueba
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.collection:
- m365-security
- tier1
ms.localizationpriority: high
ms.date: 10/07/2022
ms.service: microsoft-365-security
ms.subservice: mdb
search.appverid:
- MOE150
- MET150
description: Aprovechar al máximo la prueba de Defender para empresas con esta guía. Prepárese rápidamente y comience a usar sus nuevas funcionalidades de seguridad.
ms.custom: trial-playbook
ms.openlocfilehash: edcc5cebcce868cd11806d0a14cc33dd87f6f4fa
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68804123"
---
# <a name="trial-user-guide-microsoft-defender-for-business"></a>Guía del usuario de prueba: Microsoft Defender para Empresas

**Bienvenido a la guía del usuario de prueba de Defender for Business.**

Esta guía le ayudará a configurar y usar características clave de la evaluación gratuita. Con las recomendaciones de este artículo del equipo de Microsoft Defender, obtenga información sobre cómo Defender for Business puede ayudar a elevar la seguridad de la protección antivirus tradicional a la protección de última generación, la detección y respuesta de puntos de conexión y la administración de vulnerabilidades.

## <a name="what-is-defender-for-business"></a>¿Qué es Defender para Empresas?

Defender para Empresas es una nueva solución de seguridad de puntos de conexión diseñada especialmente para pequeñas y medianas empresas con hasta 300 empleados. Con esta solución de seguridad del punto de conexión, los dispositivos de su organización están bien protegidos contra ransomware, malware, suplantación de identidad (phishing) y otras amenazas.

:::image type="content" source="media/mdb-offering-overview.png" alt-text="Datos y funcionalidades de Defender para Empresas.":::

**Comencemos**

## <a name="set-up-your-trial"></a>Configurar la edición de prueba

Esta es la manera de configurar la suscripción de prueba:

1. [Agregar usuarios y asignar licencias](#step-1-add-users-and-assign-licenses).
2. [Visitar el portal de Microsoft 365 Defender](#step-2-visit-the-microsoft-365-defender-portal).
3. [Ejecutar el asistente de configuración](#step-3-use-the-setup-wizard-in-defender-for-business-recommended).
4. [Configurar y ajustar Defender para Empresas](#step-4-set-up-and-configure-defender-for-business).

### <a name="step-1-add-users-and-assign-licenses"></a>Paso 1: Agregar usuarios y asignar licencias

Después de registrarse en Defender para Empresas, el primer paso es **[agregar usuarios y asignar licencias](mdb-add-users.md)**.

> [!NOTE]
> Debe ser administrador global para realizar esta tarea. La persona que haya registrado su empresa en Microsoft 365 o Defender para Empresas será el administrador global de forma predeterminada. [Más información acerca de los roles y permisos](mdb-roles-permissions.md).

### <a name="step-2-visit-the-microsoft-365-defender-portal"></a>Paso 2: Visitar el portal de Microsoft 365 Defender

El portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) es una tienda integral donde se usa y administra Defender para Empresas. Incluye llamadas de ayuda para empezar a usar el programa, tarjetas que muestran información relevante y una barra de navegación que proporciona acceso fácil a las distintas características y funcionalidades.

- **[Visitar el portal de Microsoft 365 Defender](mdb-get-started.md)**.
- **[Explorar la barra de navegación](mdb-get-started.md#the-navigation-bar)** en el lado izquierdo de la pantalla para acceder a los incidentes, ver los informes y administrar las directivas de seguridad y la configuración.

### <a name="step-3-use-the-setup-wizard-in-defender-for-business-recommended"></a>Paso 3: Usar el Asistente de configuración en Defender para Empresas (recomendado)

Defender para Empresas fue diseñado para ahorrar tiempo y esfuerzo a las pequeñas y medianas empresas. Puede realizar la instalación y configuración iniciales a través de un asistente de configuración. El asistente para la instalación le ayuda a conceder acceso y configurar las notificaciones por correo electrónico para su equipo de seguridad e incorporar los dispositivos Windows de su empresa. **[Uso del asistente de configuración](mdb-use-wizard.md)**.

> [!NOTE]
> Solo puede usar el asistente de configuración una vez.

#### <a name="setup-wizard-flow-what-to-expect"></a>Flujo del asistente de configuración: qué esperar

> [!TIP]
> **El uso del asistente de configuración es opcional.** (Consulte [¿Qué ocurre si no uso el asistente?](mdb-use-wizard.md#what-happens-if-i-dont-use-the-wizard)). Si decide no usar el asistente o si el asistente se cierra antes de que se complete el proceso de instalación, puede completar el proceso de instalación y configuración por su cuenta. Consulte [Paso 4: Configurar y configurar Defender para empresas](#step-4-set-up-and-configure-defender-for-business).

1. **[Asignar permisos de usuario](mdb-roles-permissions.md#view-or-edit-role-assignments)**. Conceda a su equipo de seguridad acceso al portal de Microsoft 365 Defender.

2. **[Configurar notificaciones por correo electrónico](mdb-email-notifications.md#view-and-edit-email-notifications)** para el equipo de seguridad.

3. **[Incorporar y configurar dispositivos Windows](mdb-onboard-devices.md)**. La incorporación inmediata de dispositivos ayuda a proteger esos dispositivos desde el primer día.

   > [!NOTE]
   > Cuando se usa el asistente de configuración, el sistema detecta si tiene dispositivos Windows que ya estén inscritos en Intune. Se le preguntará si quiere usar la incorporación automática para todos los dispositivos Windows o solo para algunos de ellos. Puede incorporar todos los dispositivos Windows a la vez o seleccionar dispositivos específicos con los cuales empezar y, a continuación, agregar más dispositivos después. [Más información sobre la incorporación automática](mdb-use-wizard.md#what-is-automatic-onboarding).

   Para incorporar otros dispositivos, consulte [Paso 4: Configuración y configuración de Defender para empresas](#step-4-set-up-and-configure-defender-for-business).

4. **[Ver y editar directivas de seguridad](mdb-configure-security-settings.md)**. Defender para Empresas incluye directivas de seguridad predeterminadas para una protección de próxima generación y protección de firewall que se pueden aplicar a los dispositivos de la empresa. Estas directivas de seguridad preconfiguradas usan la configuración recomendada, por lo que estará protegido apenas incorpore los dispositivos a Defender para Empresas. Y también puede editar las directivas o crear otras nuevas.

### <a name="step-4-set-up-and-configure-defender-for-business"></a>Paso 4: Configurar Defender para Empresas

Si decide no usar el asistente de configuración, vea el siguiente diagrama que muestra el [proceso general de instalación y configuración](mdb-setup-configuration.md#the-setup-and-configuration-process) de Defender para Empresas.

[:::image type="content" source="media/mdb-setup-process-2.png" alt-text="Proceso de ajuste y configuración de Defender para Empresas.":::](mdb-setup-configuration.md)

Si usó el asistente para la instalación, pero necesita incorporar más dispositivos, como dispositivos que no son de Windows, vaya directamente al [paso 4](mdb-onboard-devices.md) en el procedimiento siguiente:

1. **[Revisar los requisitos](mdb-requirements.md)** para configurar y usar Defender para Empresas.

2. **[Asignar roles y permisos](mdb-roles-permissions.md)** en el portal de Microsoft 365 Defender.

   - [Obtener información sobre los roles en Defender para Empresas](mdb-roles-permissions.md#roles-in-defender-for-business). 
   - [Ver o editar las asignaciones de roles para el equipo de seguridad](mdb-roles-permissions.md#view-or-edit-role-assignments).

3. **[Configurar notificaciones por correo electrónico](mdb-email-notifications.md)** para el equipo de seguridad.

   - [Obtener información sobre los tipos de notificaciones por correo electrónico](mdb-email-notifications.md#types-of-email-notifications).
   - [Ver y editar la configuración de notificaciones por correo electrónico](mdb-email-notifications.md#view-and-edit-email-notifications).

4. **[Incorporar dispositivos](mdb-onboard-devices.md)**. Para incorporar clientes Windows y Mac, puede usar un script local.

5. **[Ver y configurar directivas de seguridad](mdb-configure-security-settings.md)**. Después de incorporar los dispositivos de la empresa a Defender para Empresas, el siguiente paso es ver y editar las directivas de seguridad y la configuración. 

Defender for Business incluye directivas de seguridad preconfiguradas que usan la configuración recomendada. Aunque también puede editar la configuración para adaptarla a sus necesidades empresariales.

Las directivas de seguridad que se van a revisar y configurar incluyen:

- [Directivas de protección de última generación](mdb-configure-security-settings.md#view-or-edit-your-next-generation-protection-policies) que determinan la protección antivirus y antimalware para los dispositivos de la empresa
- [Protección del firewall y reglas](mdb-configure-security-settings.md#view-or-edit-your-firewall-policies-and-custom-rules) que determinan qué tráfico de red puede fluir hacia y desde los dispositivos de la empresa
- [Filtrado de contenido web](mdb-configure-security-settings.md#set-up-web-content-filtering)que impide que las personas visiten determinados sitios web (DIRECCIONES URL) en función de categorías, como contenido para adultos o responsabilidad legal
- [Características avanzadas](mdb-configure-security-settings.md#review-settings-for-advanced-features) como investigación y respuesta automatizadas y detección y respuesta de puntos de conexión (EDR) en modo de bloque

## <a name="start-using-defender-for-business"></a>Empezar a usar Defender para Empresas

En los próximos 30 días, el equipo del producto le guía sobre las características clave para probar:

1. [Use el panel de Administración de vulnerabilidades de Microsoft Defender](#1-use-the-defender-vulnerability-management-dashboard). 

2. [Ver y responder a las amenazas detectadas](#2-view-and-respond-to-detected-threats).

3. [Revisar directivas de seguridad](#3-review-security-policies).

4. [Prepárese para la administración de seguridad en curso](#4-prepare-for-ongoing-security-management).

5. [Pruebe el tutorial Document Drops Backdoor](#5-try-the-document-drops-backdoor-tutorial).

### <a name="1-use-the-defender-vulnerability-management-dashboard"></a>1. Uso del panel de administración de vulnerabilidades de Defender

Defender for Business incluye un panel de Administración de vulnerabilidades de Defender diseñado para ahorrar tiempo y esfuerzo al equipo de seguridad. Obtenga información sobre cómo [usar el panel de Administración de vulnerabilidades de Defender](mdb-view-tvm-dashboard.md).

- Vea la puntuación de exposición que se asocia a los dispositivos de su organización.
- Vea las principales recomendaciones de seguridad, como abordar las comunicaciones deficientes con los dispositivos, activar la protección del firewall o actualizar las definiciones del antivirus de Microsoft Defender.
- Vea las actividades de corrección, como los archivos enviados a cuarentena o las vulnerabilidades encontradas en los dispositivos.

### <a name="2-view-and-respond-to-detected-threats"></a>2. Ver y responder a las amenazas detectadas

A medida que se detectan amenazas y se generan alertas, se crean incidentes. El equipo de seguridad de su organización puede ver y administrar incidentes en el portal de Microsoft 365 Defender. Obtenga información sobre cómo [ver y responder a las amenazas detectadas](mdb-view-manage-incidents.md). 

- [Ver y administrar incidentes](mdb-view-manage-incidents.md).
- [Responder a las amenazas y mitigarlas](mdb-respond-mitigate-threats.md).
- [Revisar las acciones de mediación en el Centro de actividades](mdb-review-remediation-actions.md).
- [Visualización y uso de los informes](mdb-reports.md).

### <a name="3-review-security-policies"></a>3. Revisar las directivas de seguridad

En Defender para Empresas, la configuración de seguridad se ajusta mediante directivas que se aplican a los dispositivos. Defender for Business incluye directivas preconfiguradas para ayudar a proteger los dispositivos de su empresa en cuanto se incorporan, lo que protege a su organización frente a amenazas de seguridad de identidades, dispositivos, aplicaciones y documentos. 

Obtenga información sobre cómo [revisar las directivas de seguridad](mdb-view-edit-create-policies.md).

### <a name="4-prepare-for-ongoing-security-management"></a>4. Prepararse para la administración de seguridad en curso

Los nuevos eventos de seguridad, como la detección de amenazas en un dispositivo, la adición de nuevos dispositivos y los empleados que se unan o abandonen la organización, requerirán que administre la seguridad. En Defender para Empresas, hay muchas maneras de administrar la seguridad de los dispositivos.

- [Ver una lista de los dispositivos incorporados](mdb-manage-devices.md#view-the-list-of-onboarded-devices) para ver su nivel de riesgo, nivel de exposición y estado de mantenimiento.
- [Tomar medidas en un dispositivo](mdb-manage-devices.md#take-action-on-a-device-that-has-threat-detections) con detecciones de amenazas.
- [Incorporar un dispositivo a Defender para Empresas](mdb-manage-devices.md#onboard-a-device).
- [Desincorporar un dispositivo de Defender para Empresas](mdb-manage-devices.md#offboard-a-device).

### <a name="5-try-the-document-drops-backdoor-tutorial"></a>5. Pruebe el tutorial Document Drops Backdoor

Para ver rápidamente cómo funciona Defender para empresas, pruebe un tutorial.

Simular un ataque que introduce malware basado en archivos en un dispositivo de prueba. En el tutorial se describe cómo usar el archivo de simulación y qué se debe observar en el portal de Microsoft 365 Defender.

>[!NOTE]
> Este tutorial requiere que Microsoft Word esté instalado en el dispositivo de prueba.

Para acceder al tutorial, haga lo siguiente:

1. Vaya al [portal de Microsoft 365 Defender](https://security.microsoft.com) e inicie sesión.

2. En el panel de navegación, en **Puntos de conexión**, elija **Tutoriales**.

3. Elija **Document Drops Backdoor (Puerta trasera de eliminación de documentos**).

## <a name="additional-resources"></a>Recursos adicionales

- [Información general de Defender para Empresas](mdb-overview.md)
- [Tutoriales y simulaciones en Defender para Empresas](mdb-tutorials.md)
- [Video: Protección de nivel empresarial para empresas pequeñas y medianas](https://youtu.be/umhUNzMqZto)
- [Obtener Defender para Empresas](get-defender-business.md)
