---
title: Preparar el entorno de laboratorio de prueba de Microsoft 365 Defender
description: Preparar el inicio de sesión de las partes interesadas, las escalas de tiempo, las consideraciones del entorno y el orden de adopción al configurar el entorno piloto o el laboratorio de prueba de Microsoft 365 Defender
keywords: Preparación de prueba de MTP, preparación del piloto de MTP, preparación para ejecutar un proyecto piloto de MTP, ejecutar un proyecto piloto de MTP, implementar, preparar, partes interesadas, escala de tiempo, entorno, punto de conexión, servidor, administración, adopción
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 35f1d3f0b5cefb0f14508571511449fc2c7d58a9
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930155"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Preparar el entorno piloto o el laboratorio de prueba de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Crear un entorno de prueba o piloto de Microsoft 365 Defender e implementarlo es un proceso de tres fases:

|![Fase 1: Preparar](../../media/phase-diagrams/prepare.png)<br/>Fase 1: Preparar |[![Fase 2: Configurar](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[Fase 2: Configurar](setup-mtpeval.md) |[![Fase 3: Incorporación](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)<br/>[Fase 3: Incorporación](config-mtpeval.md) | [![Volver al piloto](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[Volver al libro de reproducción piloto](mtp-pilot.md) |
|--|--|--|--|
|*¡Estás aquí!* | || |

Actualmente se encuentra en la fase de preparación.


La preparación es clave para una implementación correcta. Esta sección le guiará a través de lo que necesita tener en cuenta al prepararse para crear un entorno de prueba o piloto para su implementación de Microsoft 365 Defender.

## <a name="prerequisites"></a>Requisitos previos
Obtenga información sobre los requisitos de licencia, hardware y software, y otras opciones de configuración para aprovisionar y usar Microsoft 365 Defender. Vea los requisitos mínimos para [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites), [Microsoft Defender para](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements)Endpoint , Microsoft Defender para Office [365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), [Microsoft Defender para Identity](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites), Microsoft Cloud App [Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites).

## <a name="stakeholders-and-sign-off"></a>Partes interesadas e inicio de sesión
Identifique a todas las partes interesadas que participan en el proyecto y quién puede tener que cerrar sesión, revisar o mantenerse informada, ya sea para evaluación o ejecución de un proyecto piloto.

>[!NOTE]
>Es posible que no todas las organizaciones tengan la madurez de la organización de seguridad para tener dichos roles. En tal caso, consulte con su equipo directivo sobre las responsabilidades de revisión y aprobación.

Agregue las partes interesadas a la tabla siguiente según corresponda a su organización.

-   SO = Cerrar sesión en este proyecto

-   R = Revisar este proyecto y proporcionar entradas

-   I = Informado de este proyecto

| Nombre                 | Role                                                                                                                                                                                                          | Acción |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Escriba el nombre y el correo electrónico | **Director de seguridad de la información (CISO)** Un representante ejecutivo que actúa como patrocinador dentro de *la organización para la nueva implementación de tecnología.*                                                  | SO     |
| Escriba el nombre y el correo electrónico | Jefe del Centro de operaciones **de Cyber Defense (CDOC)** Un representante del equipo de CDOC encargado de definir cómo se alinea este cambio con los procesos del equipo de operaciones de *seguridad de los clientes.*       | SO     |
| Escriba el nombre y el correo electrónico | **Arquitecto de** seguridad Un representante del equipo de seguridad encargado de definir cómo se alinea este cambio con la arquitectura de *seguridad principal de la organización.*                         | R      |
| Escriba el nombre y el correo electrónico | **Arquitecto de área** de trabajo Un representante del equipo de IT encargado de definir cómo se alinea este cambio con la arquitectura del lugar de *trabajo principal de la organización.*                             | R      |
| Escriba el nombre y el correo electrónico | **Analista de seguridad** Un representante del equipo de CDOC que puede proporcionar comentarios sobre las capacidades de detección, la experiencia del usuario y la utilidad general de este cambio desde la perspectiva de *las operaciones de seguridad.* | I      |

## <a name="prepare-your-azure-active-directory"></a>Preparar Azure Active Directory
Omita este paso si ya ha habilitado la sincronización entre Active Directory y Azure Active Directory local. Revise la documentación de procedimientos recomendados existente de Azure Active Directory. Los siguientes pasos están optimizados para evaluar o ejecutar un proyecto piloto de Microsoft 365 Defender.

1. Vaya al portal [de Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) > Azure AD **Connect.** 
![Imagen de la página del portal de Azure Active Directory](../../media/mtp-eval-1.png) <br> 

2. Haga **clic en** Descargar desde Microsoft Azure Active Directory **Connect** y transfiédalo al controlador de dominio.
![Imagen de la página de descarga de Azure Active Directoru Connect](../../media/mtp-eval-2.png) <br>

3. En el controlador de dominio, siga el Asistente para Azure Active Directory Connect. Lea los términos de licencia y el aviso de privacidad y active la casilla si está de acuerdo. Haga clic en **Continuar**.
![Imagen de la página principal de Azure AD Connect](../../media/mtp-eval-3.png) <br>

4. Vaya a **Configuración express.**
![Imagen de la página Configuración express](../../media/mtp-eval-4.png) <br>

5. Escriba sus credenciales de administrador global. Haga clic en **Siguiente**.
![Imagen de la página Conectarse a Azure AD donde debe escribir las credenciales de administrador global](../../media/mtp-eval-5.png) <br>

6. Escriba sus credenciales de administrador de empresa de Servicios de dominio de Active Directory. Haga clic en **Siguiente**.
![Imagen de la página Conectarse a AD DS donde debe escribir sus credenciales](../../media/mtp-eval-6.png) <br>

7. Haga **clic en Instalar** para confirmar la configuración.
![Imagen de la página de confirmación de configuración](../../media/mtp-eval-7.png) <br>

8. Enhorabuena, ha configurado correctamente Azure Active Directory Connect.
![Imagen de una página de Azure Active Directory Connect configurada correctamente](../../media/mtp-eval-8.png) <br>

Ahora puede agregar [usuarios y grupos a Active Directory](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) y configurar una directiva [SAM-R](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc).  


## <a name="configuration-order"></a>Orden de configuración
En la tabla siguiente se indica el orden que Microsoft recomienda para configurar los componentes de Microsoft 365 Defender para su laboratorio de prueba o implementación de entorno piloto.

| Componente                               | Descripción                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Clasificación del orden de configuración |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|Microsoft Defender para Office 365|Microsoft Defender para Office 365 protege su organización contra las amenazas malintencionadas ocultas en mensajes de correo electrónico, vínculos (direcciones URL) y herramientas de colaboración. <br> [Aprende más.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)                                                                                                                                                                                                                                             | 1                    |
|Microsoft Defender for Identity|Microsoft Defender for Identity usa señales de Active Directory para identificar, detectar e investigar amenazas avanzadas, identidades comprometidas y acciones internas malintencionadas dirigidas a su organización. <br> [Más información](https://docs.microsoft.com/azure-advanced-threat-protection/).| 2  |
|Microsoft Cloud App Security| Microsoft Cloud App Security es un agente de seguridad de acceso a la nube (CASB) que funciona en varias nubes. Proporciona una visibilidad enriqueciendo, control sobre los viajes de datos y análisis sofisticados para identificar y combatir ciberamenazas en todos los servicios en la nube. <br> [Más información](https://docs.microsoft.com/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |3                   |
|Microsoft Defender para punto de conexión | Las capacidades de detección y respuesta de puntos de conexión de Microsoft Defender para puntos de conexión proporcionan detecciones avanzadas de ataques casi en tiempo real y que pueden actuar. Los analistas de seguridad pueden asignar prioridades a las alertas de forma eficaz, obtener visibilidad para todo el ámbito de la vulneración y llevar a cabo acciones de respuesta para corregir las amenazas. <br> [Aprende más.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>Paso siguiente
|![Fase 2: Instalación](../../media/setup.png) <br>[Fase 2: Instalación](setup-mtpeval.md) | Configurar el entorno piloto o el laboratorio de prueba de Microsoft 365 Defender
|:-------|:-----|

