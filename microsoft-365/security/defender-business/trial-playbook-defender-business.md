---
title: Cuaderno de estrategias de la edición de prueba de Microsoft Defender para Empresas
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: article
ms.collection: m365-security-compliance
ms.localizationpriority: high
ms.prod: m365-security
ms.technology: mdb
search.appverid:
- MOE150
- MET150
description: Saque el máximo partido de la edición de prueba de Defender para Empresas con este cuaderno de estrategias. Prepárese rápidamente y comience a usar sus nuevas funcionalidades de seguridad.
ms.custom: trial-playbook
ms.openlocfilehash: 16843ef3dcb2efe36f9102001fe5579e920287b4
ms.sourcegitcommit: fa90763559239c4c46c5e848939126763879d8e4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2022
ms.locfileid: "66998486"
---
# <a name="trial-playbook-microsoft-defender-for-business"></a>Edición de prueba del cuaderno de estrategias de Microsoft Defender para Empresas

**Le damos la bienvenida a la edición de prueba del cuaderno de estrategias de Defender para Empresas.**

Este cuaderno de estrategias es una guía sencilla que le ayudará a sacar el máximo partido a su prueba gratuita de 30 días. Use las recomendaciones del equipo de Microsoft Defender en este artículo para obtener información sobre cómo Defender para Empresas puede ayudar a elevar la seguridad de la protección antivirus tradicional a una protección de última generación con detección y respuesta de puntos de conexión y administración de amenazas y vulnerabilidades.

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
> **El uso del asistente de configuración es opcional.** (Vea [¿Qué pasa si no uso el asistente?](mdb-use-wizard.md#what-happens-if-i-dont-use-the-wizard)) Si decide no usar el asistente o si el asistente se cierra antes de que se complete el proceso de configuración, puede completar el proceso de instalación y configuración por su cuenta. Vea el [Paso 4](#step-4-set-up-and-configure-defender-for-business). 

1. **[Asignar permisos de usuario](mdb-roles-permissions.md#view-or-edit-role-assignments)**. Conceda a su equipo de seguridad acceso al portal de Microsoft 365 Defender.

2. **[Configurar notificaciones por correo electrónico](mdb-email-notifications.md#view-and-edit-email-notifications)** para el equipo de seguridad.

3. **[Incorporar y configurar dispositivos Windows](mdb-onboard-devices.md)**. La incorporación inmediata de dispositivos ayuda a proteger esos dispositivos desde el primer día.

   > [!NOTE]
   > Cuando se usa el asistente de configuración, el sistema detecta si tiene dispositivos Windows que ya estén inscritos en Intune. Se le preguntará si quiere usar la incorporación automática para todos los dispositivos Windows o solo para algunos de ellos. Puede incorporar todos los dispositivos Windows a la vez o seleccionar dispositivos específicos con los cuales empezar y, a continuación, agregar más dispositivos después. [Más información sobre la incorporación automática](mdb-use-wizard.md#what-is-automatic-onboarding).
   
   Para incorporar otros dispositivos, consulte el [paso 4](#step-4-set-up-and-configure-defender-for-business).

4.  **[Ver y editar directivas de seguridad](mdb-configure-security-settings.md)**. Defender para Empresas incluye directivas de seguridad predeterminadas para una protección de próxima generación y protección de firewall que se pueden aplicar a los dispositivos de la empresa. Estas directivas de seguridad preconfiguradas usan la configuración recomendada, por lo que estará protegido apenas incorpore los dispositivos a Defender para Empresas. Y también puede editar las directivas o crear otras nuevas.

### <a name="step-4-set-up-and-configure-defender-for-business"></a>Paso 4: Configurar Defender para Empresas

Si decide no usar el asistente de configuración, vea el siguiente diagrama que muestra el [proceso general de instalación y configuración](mdb-setup-configuration.md#the-setup-and-configuration-process) de Defender para Empresas.

[:::image type="content" source="media/mdb-setup-process-2.png" alt-text="Proceso de ajuste y configuración de Defender para Empresas.":::](mdb-setup-configuration.md)

Si ya usó el asistente de configuración pero necesita incorporar más dispositivos, como dispositivos que no son de Windows, vaya directamente al paso 4 del procedimiento siguiente:

1. **[Revisar los requisitos](mdb-requirements.md)** para configurar y usar Defender para Empresas. 

2. **[Asignar roles y permisos](mdb-roles-permissions.md)** en el portal de Microsoft 365 Defender.

   - [Obtener información sobre los roles en Defender para Empresas](mdb-roles-permissions.md#roles-in-defender-for-business). 
   - [Ver o editar las asignaciones de roles para el equipo de seguridad](mdb-roles-permissions.md#view-or-edit-role-assignments).

3. **[Configurar notificaciones por correo electrónico](mdb-email-notifications.md)** para el equipo de seguridad.

   - [Obtener información sobre los tipos de notificaciones por correo electrónico](mdb-email-notifications.md#types-of-email-notifications).
   - [Ver y editar la configuración de notificaciones por correo electrónico](mdb-email-notifications.md#view-and-edit-email-notifications).

4. **[Incorporar dispositivos](mdb-onboard-devices.md)**. Con Defender para Empresas, tiene varias opciones entre las cuales elegir para incorporar los dispositivos de su empresa. En primer lugar, seleccione el sistema operativo que desea incorporar.

   | Tipo de dispositivo | Métodos de incorporación |
   |:---|:---|
   | [Clientes de Windows](mdb-onboard-devices.md) | Elija una de las siguientes opciones para incorporar dispositivos cliente de Windows en Defender para Empresas:<ul><li>Script local (para la incorporación manual de dispositivos en el portal de Microsoft 365 Defender)</li><li>Directiva de grupo (si ya usa la directiva de grupo y prefiere este método)</li><li>Microsoft Intune (*recomendando*; incluido en [Microsoft 365 Empresa Premium](../../business-premium/index.md))</li></ul> |
   | [Mac](mdb-onboard-devices.md) | Elija una de las siguientes opciones para incorporar Mac:<ul><li>Script local para Mac (*recomendado*)</li><li>Microsoft Intune para Mac (Intune se incluye en [Microsoft 365 Empresa Premium](../../business-premium/index.md))</li></ul><p>Se recomienda usar un script local para incorporar Mac. Aunque puede [configurar la inscripción para dispositivos Mac en Intune](/mem/intune/enrollment/macos-enroll), el script local es el método más sencillo para incorporar dispositivos Mac en Defender para Empresas. |
   | Servidores Windows Server y Linux | *La capacidad de incorporar una instancia de Windows Server o de un servidor de Linux se encuentra actualmente en versión preliminar y requiere una licencia adicional*. Para obtener más información, vea los artículos siguientes: <ul><li>[Requisitos de Defender para Empresas](mdb-requirements.md)</li><li>[Incorporar dispositivos a Defender para Empresas](mdb-onboard-devices.md)</li></ul> |
   | [Dispositivos móviles](mdb-onboard-devices.md) | Necesita Microsoft Intune para incorporar dispositivos móviles, como dispositivos Android e iOS/iPadOS. Si tiene [Microsoft 365 Empresa Premium](../../business-premium/index.md), Intune forma parte de su suscripción. Intune también se puede comprar por separado. Consulte los siguientes recursos para obtener ayuda para inscribir estos dispositivos en Intune:<ul><li>[Inscribir dispositivos Android](/mem/intune/enrollment/android-enroll)</li><li>[Inscribir dispositivos iOS o iPadOS](/mem/intune/enrollment/ios-enroll)</li></ul> |

5. **[Ver y configurar directivas de seguridad](mdb-configure-security-settings.md)**. Después de incorporar los dispositivos de la empresa a Defender para Empresas, el siguiente paso es ver y editar las directivas de seguridad y la configuración. Defender para Empresas incluye directivas de seguridad preconfiguradas que usan los ajustes recomendados. Aunque también puede editar la configuración para adaptarla a sus necesidades empresariales.

   | Acción | Descripción |
   |:---|:---|
   | [Elija dónde administrar sus directivas de seguridad y dispositivos](mdb-configure-security-settings.md#choose-where-to-manage-security-policies-and-devices). | Si selecciona el [proceso de configuración simplificado](mdb-simplified-configuration.md), podrá ver y administrar las directivas de seguridad en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). Sin embargo, no está limitado a esta opción. Si ha estado usando [Intune](/mem/intune/protect/), puede seguir usando el Centro de administración de Microsoft Endpoint Manager para administrar sus dispositivos y directivas de seguridad. |
   | [Ver o editar las directivas de protección de próxima generación](mdb-configure-security-settings.md#view-or-edit-your-next-generation-protection-policies). | La configuración de protección de próxima generación incluye protección en tiempo real, bloqueo a primera vista, protección de red, acciones a realizar en aplicaciones potencialmente indeseadas y exámenes programados de antivirus.  |
   | [Ver o editar las directivas de firewall](mdb-configure-security-settings.md#view-or-edit-your-firewall-policies-and-custom-rules). | La protección del firewall determina qué tráfico de red puede fluir hacia y desde los dispositivos de la empresa. [Se pueden usar reglas personalizadas](mdb-custom-rules-firewall.md) para definir las excepciones para las directivas de firewall. |
   | [Configurar el filtrado de contenido web](mdb-configure-security-settings.md#set-up-web-content-filtering). | El filtrado de contenido web permite a su equipo de seguridad realizar seguimiento y regular el acceso a los sitios web en función de sus categorías de contenido, como contenido para adultos, ancho de banda alto, responsabilidad legal, ocio o no categorizado. |
   | [Revisar la configuración para las características avanzadas](mdb-configure-security-settings.md#review-settings-for-advanced-features). | En Defender para Empresas, las características de seguridad están preconfiguradas con los ajustes recomendados. Puede revisar y editar la configuración para adaptarla a sus necesidades empresariales. <br/><br/>Para acceder a la configuración de las características avanzadas, en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) vaya a **Configuración** > **Puntos de conexión** > **General** > **Características avanzadas**. |
   | Puede [Ver y editar otras opciones de configuración](mdb-configure-security-settings.md#access-your-settings-in-the-microsoft-365-defender-portal) en el portal de Microsoft 365 Defender. | Además de las directivas de seguridad que se aplican a los dispositivos, hay otras opciones que puede ver y editar en Defender para Empresas. Por ejemplo, se especifica la zona horaria que se va a usar y se pueden incorporar (o desincorporar) dispositivos. |

## <a name="start-using-defender-for-business"></a>Empezar a usar Defender para Empresas

En los próximos 30 días, le recomendamos probar las nuevas funcionalidades de seguridad según se describen en las secciones siguientes:

- [Uso del panel de Administración de amenazas y vulnerabilidades](#use-the-threat--vulnerability-management-dashboard) 
- [Ver y responder a las amenazas detectadas](#view-and-respond-to-detected-threats)
- [Revisar las directivas de seguridad](#review-security-policies)
- [Prepararse para la administración de seguridad continua](#prepare-for-ongoing-security-management)

### <a name="use-the-threat--vulnerability-management-dashboard"></a>Uso del panel de Administración de amenazas y vulnerabilidades

Defender para Empresas incluye un panel de Administración de amenazas y vulnerabilidades diseñado para ahorrar tiempo y esfuerzo al equipo de seguridad. [Uso del panel de Administración de amenazas y vulnerabilidades](mdb-view-tvm-dashboard.md).

- Vea la puntuación de exposición que se asocia a los dispositivos de su organización.
- Vea las principales recomendaciones de seguridad, como abordar las comunicaciones deficientes con los dispositivos, activar la protección del firewall o actualizar las definiciones del antivirus de Microsoft Defender.
- Vea las actividades de corrección, como los archivos enviados a cuarentena o las vulnerabilidades encontradas en los dispositivos.

### <a name="view-and-respond-to-detected-threats"></a>Ver y responder a las amenazas detectadas

A medida que se detectan amenazas y se generan alertas, se crean incidentes. El equipo de seguridad de su organización puede ver y administrar incidentes en el portal de Microsoft 365 Defender. [Ver y responder a las amenazas detectadas](mdb-view-manage-incidents.md). 

- [Ver y administrar incidentes](mdb-view-manage-incidents.md).
- [Responder a las amenazas y mitigarlas](mdb-respond-mitigate-threats.md).
- [Revisar las acciones de mediación en el Centro de actividades](mdb-review-remediation-actions.md).
- [Visualización y uso de los informes](mdb-reports.md).

### <a name="review-security-policies"></a>Revisión de las directivas de seguridad

En Defender para Empresas, la configuración de seguridad se ajusta mediante directivas que se aplican a los dispositivos. Defender para Empresas incluye directivas preconfiguradas para ayudar a proteger los dispositivos de la empresa apenas se incorporan, protegiendo su organización contra amenazas de seguridad de identidad, dispositivo, aplicación y documentos. [Revisar directivas de seguridad](mdb-view-edit-create-policies.md).

- [Más información sobre las directivas predeterminadas](mdb-view-edit-create-policies.md#default-policies-in-defender-for-business).
- [Ver las directivas existentes](mdb-view-edit-create-policies.md#view-your-existing-policies).
- [Comprender el orden de las directivas](mdb-policy-order.md). 
- [Comprender las opciones de configuración de última generación](mdb-next-gen-configuration-settings.md).
- [Revisar la configuración predeterminada del firewall](mdb-firewall.md#default-firewall-settings-in-defender-for-business).
- [Comprender la configuración del firewall que puede configurar](mdb-firewall.md#firewall-settings-you-can-configure-in-defender-for-business).
- [Configurar el filtrado de contenido web](mdb-configure-security-settings.md#set-up-web-content-filtering). El filtrado de contenido web permite al equipo de seguridad realizar un seguimiento y regular el acceso a los sitios web en función de sus categorías de contenido. Esta funcionalidad no está activada de forma predeterminada, por lo que debe configurarla si la desea para su organización.
  
### <a name="prepare-for-ongoing-security-management"></a>Prepararse para la administración de seguridad continua

Los nuevos eventos de seguridad, como la detección de amenazas en un dispositivo, la adición de nuevos dispositivos y los empleados que se unan o abandonen la organización, requerirán que administre la seguridad. En Defender para Empresas, hay muchas maneras de administrar la seguridad de los dispositivos.

- [Ver una lista de los dispositivos incorporados](mdb-manage-devices.md#view-the-list-of-onboarded-devices) para ver su nivel de riesgo, nivel de exposición y estado de mantenimiento.
- [Tomar medidas en un dispositivo](mdb-manage-devices.md#take-action-on-a-device-that-has-threat-detections) con detecciones de amenazas.
- [Incorporar un dispositivo a Defender para Empresas](mdb-manage-devices.md#onboard-a-device).
- [Desincorporar un dispositivo de Defender para Empresas](mdb-manage-devices.md#offboard-a-device).

## <a name="additional-resources"></a>Recursos adicionales

- [Información general de Defender para Empresas](mdb-overview.md)
- [Tutoriales y simulaciones en Defender para Empresas](mdb-tutorials.md)
- [Video: Protección de nivel empresarial para empresas pequeñas y medianas](https://youtu.be/umhUNzMqZto)
- [Obtener Defender para Empresas](get-defender-business.md)
