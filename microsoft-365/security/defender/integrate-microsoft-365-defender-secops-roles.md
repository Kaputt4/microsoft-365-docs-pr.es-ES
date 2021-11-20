---
title: Paso 4. Definir Microsoft 365 Defender funciones, responsabilidades y supervisión
description: Los conceptos básicos de definición de roles, responsabilidades y supervisión al integrar Microsoft 365 Defender en las operaciones de seguridad.
keywords: incidentes, alertas, investigar, correlación, ataque, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, Microsoft 365, respuesta a incidentes, ciberataque, secops, operaciones de seguridad, soc
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
- m365solution-m365dsecops
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 1cacdf050c51b97f7ea6acbefcedfb2156814509
ms.sourcegitcommit: 07405a81513d1c63071a128b9d5070d3a3bfe1cd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2021
ms.locfileid: "61121464"
---
# <a name="step-4-define-microsoft-365-defender-roles-responsibilities-and-oversight"></a>Paso 4. Definir Microsoft 365 Defender funciones, responsabilidades y supervisión

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Su organización debe establecer la propiedad y la responsabilidad de las Microsoft 365 Defender, las configuraciones y la administración como tareas iniciales antes de poder definir los roles operativos. Normalmente, la propiedad de las licencias, los costos de suscripción y la administración de los servicios Microsoft 365 y Enterprise Security + Mobility (EMS) (que pueden incluir Microsoft 365 Defender) se encuentran fuera de los equipos del Centro de operaciones de seguridad (SOC). Los equipos de SOC deben trabajar con esas personas para garantizar una supervisión adecuada de Microsoft 365 Defender. 

Muchos SOC modernos asignan miembros de su equipo a categorías en función de sus conjuntos de aptitudes y funciones. Por ejemplo:

- Un equipo de inteligencia de amenazas asignado a tareas relacionadas con la administración del ciclo de vida de las funciones de análisis y amenazas.
- Un equipo de supervisión formado por analistas de SOC responsables del mantenimiento de registros, alertas, eventos y funciones de supervisión.
- Un equipo de & de operaciones asignado al ingeniero y optimizar los dispositivos de seguridad.

Las responsabilidades y roles de equipo de SOC Microsoft 365 Defender integran de forma natural en estos equipos.

En la siguiente tabla se desglosan las funciones y responsabilidades de cada equipo SOC y cómo se integran sus roles con Microsoft 365 Defender.

| Equipo de SOC | Roles y responsabilidades | Microsoft 365 Defender tareas  |
|:-------|:-----|:-------|
| Supervisión de SOC | <ul><li>Realiza gobierno de SOC</li><li>Establece procesos diarios, semanales y mensuales</li><li>Proporciona formación y concienciación</li><li>Contrata personal, participa en reuniones y grupos del mismo nivel</li><li>Realiza ejercicios de equipo azul, rojo y púrpura</ul>  | <ul><li>Microsoft 365 Defender de acceso al portal</li><li>Mantiene el registro de actualización de características/URL y licencias</li><li>Mantiene la comunicación con las partes interesadas de LA, legales, de cumplimiento y de privacidad</li><li>Participa en reuniones de control de cambios para iniciativas Microsoft 365 o Microsoft Azure nuevas</ul> |
| Análisis de inteligencia & amenazas  | <ul><li>Administración de fuentes intel de amenazas</li><li>Atribución de virus y malware</li><li>Modelado de amenazas & categorizaciones de eventos de amenazas</li><li>Desarrollo de atributos de amenazas de Insider </li><li>Programa de integración intel de amenazas con administración de riesgos</li><li>Integra información de datos con ciencia de datos, BI y análisis en equipos de recursos humanos, legales, DEA y seguridad<ul> | <ul><li>Mantiene Microsoft Defender para el modelado de amenazas de identidad</li><li>Mantiene Microsoft Defender para el Office 365 de amenazas</li><li>Mantiene Microsoft Defender para el modelado de amenazas de extremo</ul> |
| Supervisión | <ul><li>Analistas de nivel 1, 2 y 3</li><li>Ingeniería y mantenimiento de origen de registro</li><li>Ingesta de orígenes de datos </li><li>Análisis de SIEM, alertas, correlación, optimización</li><li>Generación de eventos y alertas</li><li>Análisis de eventos y alertas</li><li>Informes de eventos y alertas</li><li>Mantenimiento del sistema de vales</ul> | Usa: <ul><li>Centro de seguridad y cumplimiento</li><li>Portal de Microsoft 365 Defender</ul> |
| Ingeniería & SecOps | <ul><li>Administración de vulnerabilidades para aplicaciones, sistemas y puntos de conexión</li><li>Automatización XDR/SOAR</li><li>Pruebas de cumplimiento</li><li>Ingeniería de phishing y DLP</li><li>Ingeniería</li><li>Control de cambio de coordenadas</li><li>Coordina actualizaciones de runbook</li><li>Pruebas de penetración<ul> | <ul><li>Microsoft Defender for Cloud Apps</li><li>Defender para punto de conexión</li><li>Defender for Identity</ul> |
| Equipo de respuesta a incidentes de seguridad del equipo (CSIRT) | <ul><li>Investiga y responde a incidentes cibernéticos</li><li>Realiza exámenes forenses</li><li>**Puede que a menudo se aísla de SOC**</ul> | Colaborar y mantener los Microsoft 365 Defender de respuesta a incidentes |
||||


## <a name="next-step"></a>Paso siguiente

[Paso 5. Desarrollar y probar casos de uso](integrate-microsoft-365-defender-secops-use-cases.md)
