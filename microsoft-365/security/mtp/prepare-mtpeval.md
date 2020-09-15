---
title: Preparar el entorno de laboratorio de prueba de Microsoft Threat Protection
description: Preparar la aprobación de los participantes, escalas de tiempo, consideraciones del entorno y orden de adopción al configurar el entorno de laboratorio de prueba de Microsoft Threat Protection
keywords: Versión de prueba de MTP preparar, implementar, preparar, parte de la línea de parte, entorno, extremo, servidor, administración, adopción
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: ad2f34fbb94cafd22976c6ff7c75cdd254e913e3
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650098"
---
# <a name="prepare-your-microsoft-threat-protection-trial-lab-environment"></a>Preparar el entorno de laboratorio de prueba de Microsoft Threat Protection

**Se aplica a:**
- Protección contra amenazas de Microsoft

La creación de un entorno de laboratorio de prueba de Microsoft Threat Protection y su implementación es un proceso de tres fases:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Preparar el entorno de laboratorio de prueba de Microsoft Threat Protection" />
      <br/>Fase 1: preparación </a><br>
    </td>
     <td align="center"  >
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Configurar el entorno de laboratorio de prueba de Microsoft Threat Protection" />
      <br/>Fase 2: configuración </a><br>
        </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval">
        <img src="../../media/config-onboard.png" alt="Configure each Microsoft Threat Protection pillar" title="Configure cada pilar de protección contra amenazas de Microsoft y incorpore los puntos de conexión." />
      <br/>Fase 3: configurar & incorporado</a><br>
</td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
  </tr>
</table>

Actualmente está en la fase de preparación.


La preparación es fundamental para todas las implementaciones correctas. Esta sección le guiará a través de lo que debe tener en cuenta a medida que se prepara para crear un entorno de prueba de prueba para la implementación de Microsoft Threat Protection.

## <a name="prerequisites"></a>Requisitos previos
Obtenga información sobre las licencias, los requisitos de hardware y software, y otras opciones de configuración para aprovisionar y usar la protección contra amenazas de Microsoft. Vea los requisitos mínimos para [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?view=o365-worldwide), [ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements), [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites), [Microsoft Cloud App Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites).

## <a name="stakeholders-and-sign-off"></a>Partes interesadas y la firma
La siguiente sección sirve para identificar a todas las partes interesadas del proyecto y que pueden tener que cerrar la sesión, revisar o mantenerse informados, incluso para una evaluación o prueba de la prueba de concepto en seco.

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
| Escriba el nombre y el correo electrónico | **Analista de seguridad** *un representante del equipo de CDOC que puede proporcionar información sobre las capacidades de detección, la experiencia del usuario y la utilidad general de este cambio desde el punto de vista de las operaciones de seguridad.* | I      |

## <a name="prepare-your-azure-active-directory"></a>Preparar Azure Active Directory
Omita este paso si ya ha habilitado la sincronización entre Active Directory y Azure Active Directory local. Revise la documentación de procedimientos recomendados existentes de Azure Active Directory. Los siguientes pasos están optimizados para evaluar la protección contra amenazas de Microsoft.

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
La siguiente tabla indica el orden que Microsoft recomienda para configurar los componentes de la protección contra amenazas de Microsoft para la implementación del entorno de pruebas de prueba.

| Componente                               | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Rango de orden de configuración |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Protección contra amenazas avanzada de Office 365| Office 365 ATP protege a su organización frente a amenazas malintencionadas que plantean mensajes de correo electrónico, vínculos (URL) y herramientas de colaboración. <br> [Aprende más.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)                                                                                                                                                                                                                                             | 1                    |
|Azure Advanced Threat Protection|ATP de Azure usa las señales de Active Directory para identificar, detectar e investigar amenazas avanzadas, identidades comprometidas y acciones de Insider dañinas dirigidas a la organización. <br> [Más información](https://docs.microsoft.com/azure-advanced-threat-protection/).| 2  |
|Microsoft Cloud App Security| Microsoft Cloud App Security es un agente de seguridad de acceso a la nube (CASB) que funciona en varias nubes. Proporciona una gran visibilidad, control sobre los recorridos de datos y análisis sofisticados para identificar y combatir ciberamenazas en todos sus servicios en la nube. <br> [Más información](https://docs.microsoft.com/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |3                    |
|Protección contra amenazas avanzada de Microsoft Defender | Las funciones de detección y respuesta en el punto de conexión de ATP de Microsoft Defender proporcionan detecciones de ataques avanzadas que son casi en tiempo real y permiten tomar medidas. Los analistas de seguridad pueden asignar prioridades a las alertas de forma eficaz, obtener visibilidad para todo el ámbito de la vulneración y llevar a cabo acciones de respuesta para corregir las amenazas. <br> [Aprende más.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>Paso siguiente
![Fase 2: configuración](../../media/setup.png) <br>[Fase 2: configuración](setup-mtpeval.md)<br> Configurar el entorno de laboratorio de prueba de Microsoft Threat Protection

