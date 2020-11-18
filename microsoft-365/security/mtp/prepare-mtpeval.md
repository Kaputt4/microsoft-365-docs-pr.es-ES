---
title: Preparar el entorno de laboratorio de prueba de Microsoft 365 defender
description: Preparar la aprobación de los participantes, escalas de tiempo, consideraciones del entorno y orden de adopción cuando configure el entorno piloto o el laboratorio de pruebas de Microsoft 365 defender
keywords: Versión de prueba de MTP, preparación piloto de MTP, preparación para la ejecución de un proyecto piloto MTP, ejecución de un proyecto piloto MTP, implementación, preparación, parte de la información del participante, escala de tiempo, entorno, extremo, servidor, administración, adopción
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: 7149524de868a3670807556f5f423ba0ee4a772a
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131270"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Preparar el entorno piloto o el laboratorio de prueba de Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La creación de un entorno de prueba de Microsoft 365 defender o un entorno piloto y su implementación es un proceso de tres fases:

|![Fase 1: preparación](../../media/phase-diagrams/prepare.png)<br/>Fase 1: preparación |[![Fase 2: configurar](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[Fase 2: configurar](setup-mtpeval.md) |[![Fase 3: incorporada](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)<br/>[Fase 3: incorporada](config-mtpeval.md) | [![Volver a la prueba piloto](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[Volver a la guía piloto](mtp-pilot.md) |
|--|--|--|--|
|*Ya está aquí.* | || |

Actualmente está en la fase de preparación.


La preparación es fundamental para todas las implementaciones correctas. Esta sección le guiará a través de lo que debe tener en cuenta al prepararse para crear un laboratorio de pruebas o un entorno piloto para la implementación de Microsoft 365 defender.

## <a name="prerequisites"></a>Requisitos previos
Obtenga información sobre las licencias, los requisitos de hardware y software, y otras opciones de configuración para aprovisionar y usar Microsoft 365 defender. Vea los requisitos mínimos para [microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites), [Microsoft defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements), [Microsoft defender para Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), [Microsoft defender para identidad](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites), Microsoft [Cloud App Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites).

## <a name="stakeholders-and-sign-off"></a>Partes interesadas y la firma
Identifique todas las partes interesadas involucradas en el proyecto y que puedan tener que cerrar, revisar o mantenerse informado, ya sea para la evaluación o la ejecución de un proyecto piloto.

>[!NOTE]
>Es posible que no todas las organizaciones tengan el vencimiento de la organización de seguridad para estas funciones. En este caso, consulte con su equipo de liderazgo sobre accountabilities de revisión y aprobación.

Agregue partes interesadas a la tabla siguiente según corresponda para su organización.

-   Por lo tanto, la firma de este proyecto

-   R = revisar este proyecto y proporcionar información

-   I = informado de este proyecto

| Nombre                 | Role                                                                                                                                                                                                          | Action |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Escriba el nombre y el correo electrónico | Director General de seguridad de la **información (CISO)** *un representante ejecutivo que sirve de patrocinador dentro de la organización para la nueva implementación de la tecnología.*                                                  | PARA     |
| Escriba el nombre y el correo electrónico | **Director de operaciones de la defensa en el ciberespacio (CDOC)** *un representante del equipo de CDOC a cargo de definir cómo se alinea este cambio con los procesos del equipo de operaciones de seguridad de clientes.*       | PARA     |
| Escriba el nombre y el correo electrónico | **Arquitecto de seguridad** *un representante del equipo de seguridad a cargo de definir cómo se alinea este cambio con la arquitectura de seguridad principal de la organización.*                         | R      |
| Escriba el nombre y el correo electrónico | **Arquitecto de trabajo** *un representante del equipo de ti encargado de definir cómo se alinea este cambio con la arquitectura principal del área de trabajo de la organización.*                             | R      |
| Escriba el nombre y el correo electrónico | **Analista de seguridad** *un representante del equipo de CDOC que puede enviar comentarios sobre las capacidades de detección, la experiencia del usuario y la utilidad general de este cambio desde el punto de vista de las operaciones de seguridad.* | I      |

## <a name="prepare-your-azure-active-directory"></a>Preparar Azure Active Directory
Omita este paso si ya ha habilitado la sincronización entre Active Directory y Azure Active Directory local. Revise la documentación de procedimientos recomendados existentes de Azure Active Directory. Los siguientes pasos están optimizados para evaluar o ejecutar un proyecto piloto de Microsoft 365 defender.

1. Vaya al portal de [Azure active directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) > **Azure ad Connect**. 
![Imagen de la página del portal de Azure Active Directory](../../media/mtp-eval-1.png) <br> 

2. Haga clic en **Descargar** desde **Microsoft Azure Active Directory Connect** y transfiéralo a su controlador de dominio.
![Imagen de la página de descarga de Azure Active Directoru Connect](../../media/mtp-eval-2.png) <br>

3. En el controlador de dominio, siga el Asistente de Azure Active Directory Connect. Lea los términos de licencia y el aviso de privacidad y active la casilla si está de acuerdo. Haga clic en **Continuar**.
![Imagen de la Página principal de Azure AD Connect](../../media/mtp-eval-3.png) <br>

4. Vaya a **Configuración rápida**.
![Imagen de la página de configuración rápida](../../media/mtp-eval-4.png) <br>

5. Escriba sus credenciales de administrador global. Haga clic en **Siguiente**.
![Imagen de la página conectar a Azure AD donde debe especificar las credenciales de administrador global](../../media/mtp-eval-5.png) <br>

6. Escriba sus credenciales de administrador de empresa de servicios de dominio de Active Directory. Haga clic en **Siguiente**.
![Imagen de la página conectar con AD DS donde debe escribir sus credenciales](../../media/mtp-eval-6.png) <br>

7. Haga clic en **instalar** para confirmar la configuración.
![Imagen de la página de confirmación de configuración](../../media/mtp-eval-7.png) <br>

8. Enhorabuena, ha configurado correctamente Azure Active Directory Connect.
![Imagen de una página de Azure Active Directory Connect configurada correctamente](../../media/mtp-eval-8.png) <br>

Ahora puede [Agregar usuarios y grupos a Active](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) Directory y [configurar una directiva Sam-R](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc).  


## <a name="configuration-order"></a>Orden de configuración
En la tabla siguiente se indica el orden que Microsoft recomienda para configurar los componentes de Microsoft 365 defender para su laboratorio de prueba o para la implementación del entorno piloto.

| Componente                               | Descripción                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Rango de orden de configuración |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|Microsoft Defender para Office 365|Microsoft Defender para Office 365 protege su organización contra las amenazas malintencionadas ocultas en mensajes de correo electrónico, vínculos (direcciones URL) y herramientas de colaboración. <br> [Aprende más.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)                                                                                                                                                                                                                                             | 1                   |
|Microsoft Defender for Identity|Microsoft defender para identidad usa señales de Active Directory para identificar, detectar e investigar amenazas avanzadas, identidades comprometidas y acciones de Insider dañinas dirigidas a la organización. <br> [Más información](https://docs.microsoft.com/azure-advanced-threat-protection/).| segundo |
|Microsoft Cloud App Security| Microsoft Cloud App Security es un agente de seguridad de acceso a la nube (CASB) que funciona en varias nubes. Proporciona una gran visibilidad, control sobre los recorridos de datos y análisis sofisticados para identificar y combatir ciberamenazas en todos sus servicios en la nube. <br> [Más información](https://docs.microsoft.com/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |3                   |
|Microsoft Defender para punto de conexión | Las capacidades de detección y respuesta de Microsoft defender para extremo de punto de conexión proporcionan detecciones de ataques avanzadas que se encuentran casi en tiempo real y accionables. Los analistas de seguridad pueden asignar prioridades a las alertas de forma eficaz, obtener visibilidad para todo el ámbito de la vulneración y llevar a cabo acciones de respuesta para corregir las amenazas. <br> [Aprende más.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>Paso siguiente
|![Fase 2: configuración](../../media/setup.png) <br>[Fase 2: configuración](setup-mtpeval.md) | Configurar el entorno piloto o el laboratorio de prueba de Microsoft 365 defender
|:-------|:-----|

