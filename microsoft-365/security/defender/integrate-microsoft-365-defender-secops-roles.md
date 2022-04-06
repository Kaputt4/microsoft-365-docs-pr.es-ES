---
title: Paso 4. Definición de roles, responsabilidades y supervisión de Microsoft 365 Defender
description: Los conceptos básicos de la definición de roles, responsabilidades y supervisión al integrar Microsoft 365 Defender en las operaciones de seguridad.
keywords: incidentes, alertas, investigación, correlación, ataque, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, Microsoft 365, respuesta a incidentes, ciberataque, secops, operaciones de seguridad, soc
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-m365dsecops
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5410db413ece81a39453070985e6c744e8b684a6
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664070"
---
# <a name="step-4-define-microsoft-365-defender-roles-responsibilities-and-oversight"></a>Paso 4. Definición de roles, responsabilidades y supervisión de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Su organización debe establecer la propiedad y la responsabilidad de las licencias, configuraciones y administración de Microsoft 365 Defender como tareas iniciales antes de que se puedan definir los roles operativos. Normalmente, la propiedad de las licencias, los costos de suscripción y la administración de los servicios Microsoft 365 y Enterprise Security + Mobility (EMS) (que pueden incluir Microsoft 365 Defender) se encuentran fuera de los equipos de Security Operations Center (SOC). Los equipos de SOC deben trabajar con esas personas para garantizar una supervisión adecuada de Microsoft 365 Defender. 

Muchos SOC modernos asignan a sus miembros del equipo a categorías en función de sus conjuntos de aptitudes y funciones. Por ejemplo:

- Un equipo de inteligencia sobre amenazas asignado a tareas relacionadas con la administración del ciclo de vida de las funciones de análisis y amenazas.
- Un equipo de supervisión compuesto por analistas de SOC responsables de mantener registros, alertas, eventos y funciones de supervisión.
- Un equipo de operaciones de ingeniería & asignado a diseñar y optimizar dispositivos de seguridad.

Los roles y responsabilidades del equipo de SOC para Microsoft 365 Defender se integrarían naturalmente en estos equipos.

En la tabla siguiente se desglosan los roles y responsabilidades de cada equipo soc y cómo se integran sus roles con Microsoft 365 Defender.

| Equipo de SOC | Roles y responsabilidades | tareas de Microsoft 365 Defender  |
|:-------|:-----|:-------|
| Supervisión de SOC | <ul><li>Realiza la gobernanza de SOC</li><li>Establece procesos diarios, semanales y mensuales</li><li>Proporciona formación y reconocimiento</li><li>Contrata personal, participa en grupos y reuniones del mismo nivel</li><li>Realiza ejercicios de equipo azul, rojo y púrpura</ul>  | <ul><li>Microsoft 365 Defender controles de acceso del portal</li><li>Mantiene el registro de actualización de características o direcciones URL y licencias</li><li>Mantiene la comunicación con las partes interesadas de TI, legales, de cumplimiento y privacidad.</li><li>Participa en reuniones de control de cambios para nuevas iniciativas de Microsoft 365 o Microsoft Azure</ul> |
| Threat Intelligence & Analytics  | <ul><li>Administración de fuentes intel de amenazas</li><li>Atribución de virus y malware</li><li>Modelado de amenazas & categorizaciones de eventos de amenazas</li><li>Desarrollo de atributos de amenazas internas </li><li>Integración de Intel con amenazas con el programa de administración de riesgos</li><li>Integra información de datos con ciencia de datos, BI y análisis en equipos de RR. HH., legales, de TI y de seguridad<ul> | <ul><li>Mantiene el modelado de amenazas Microsoft Defender for Identity</li><li>Mantiene el modelado de amenazas Microsoft Defender para Office 365</li><li>Mantiene el modelado de amenazas Microsoft Defender para punto de conexión</ul> |
| Supervisión | <ul><li>Analistas de nivel 1, 2 y 3</li><li>Mantenimiento e ingeniería del origen de registro</li><li>Ingesta del origen de datos </li><li>Análisis, alertas, correlación y optimización de SIEM</li><li>Generación de eventos y alertas</li><li>Análisis de eventos y alertas</li><li>Informes de eventos y alertas</li><li>Mantenimiento del sistema de vales</ul> | Utiliza: <ul><li>Centro de seguridad y cumplimiento</li><li>Portal de Microsoft 365 Defender</ul> |
| Ingeniería & SecOps | <ul><li>Administración de vulnerabilidades para aplicaciones, sistemas y puntos de conexión</li><li>Automatización de XDR/SOAR</li><li>Pruebas de cumplimiento</li><li>Ingeniería de phishing y DLP</li><li>Ingeniería</li><li>Control de cambio de coordenadas</li><li>Coordina las actualizaciones del runbook</li><li>Pruebas de penetración<ul> | <ul><li>Microsoft Defender for Cloud Apps</li><li>Defender para punto de conexión</li><li>Defender for Identity</ul> |
| Equipo de respuesta a incidentes de seguridad del equipo (CSIRT) | <ul><li>Investiga y responde a incidentes cibernéticos</li><li>Realiza análisis forenses</li><li>**A menudo se puede aislar de SOC**</ul> | Colaborar y mantener Microsoft 365 Defender cuadernos de estrategias de respuesta a incidentes |
||||


## <a name="next-step"></a>Paso siguiente

[Paso 5. Desarrollar y probar casos de uso](integrate-microsoft-365-defender-secops-use-cases.md)
