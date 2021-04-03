---
title: Configurar los pilares de Microsoft 365 Defender para el entorno piloto o el laboratorio de prueba
description: Configure los pilares de Microsoft 365 Defender, como Microsoft Defender para Office 365, Microsoft Defender para la identidad, Microsoft Cloud App Security y Microsoft Defender para Endpoint, para su entorno piloto o laboratorio de prueba.
keywords: configurar la versión de prueba de Protección contra amenazas de Microsoft, la configuración de prueba de Protección contra amenazas de Microsoft, configurar el proyecto piloto de Protección contra amenazas de Microsoft, configurar los pilares de Protección contra amenazas de Microsoft, los pilares de Protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9b192a029704d1354867b169efdf0d489345030e
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580971"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>Configurar los pilares de Microsoft 365 Defender para el entorno piloto o el laboratorio de prueba

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender


Crear un entorno piloto o un laboratorio de prueba de Microsoft 365 Defender e implementarlo es un proceso de tres fases:

|[![Fase 1: Preparación](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)<br/>[Fase 1: Preparación](prepare-m365d-eval.md) |[![Fase 2: Configuración](../../media/phase-diagrams/setup.png)](setup-m365deval.md)<br/>[Fase 2: Configuración](setup-m365deval.md) |![Fase 3: Incorporación](../../media/phase-diagrams/onboard.png)<br/>Fase 3: Incorporación | [![Volver al piloto](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[Volver al libro de reproducción piloto](m365d-pilot.md) |
|--|--|--|--|
|| |*¡Estás aquí!* | |

Actualmente está en la fase de configuración.

La preparación es clave para cualquier implementación correcta. En este artículo, se te guiará sobre los puntos que tendrás que tener en cuenta mientras te preparas para implementar Microsoft Defender para endpoint.


## <a name="microsoft-365-defender-pillars"></a>Pilares de Microsoft 365 Defender
Microsoft 365 Defender consta de cuatro pilares. Aunque un pilar ya puede proporcionar valor a la seguridad de la organización de red, habilitar los cuatro pilares de Microsoft 365 Defender le dará a su organización el mayor valor.

![Image of_Microsoft 365 Defender solution for users, Microsoft Defender for Identity, for endpoints Microsoft Defender for Endpoint, for cloud apps, Microsoft Cloud App Security, and for data, Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

En esta sección se le guiará para configurar:
-   Microsoft Defender para Office 365
-   Microsoft Defender for Identity 
-   Microsoft Cloud App Security
-   Microsoft Defender para punto de conexión


## <a name="configure-microsoft-defender-for-office-365"></a>Configurar Microsoft Defender para Office 365

>[!NOTE]
>Omita este paso si ya ha habilitado Defender para Office 365. 

Hay un módulo de PowerShell denominado Analizador de configuración recomendada (ORCA) de Protección contra amenazas avanzada *de Office 365* que ayuda a determinar algunas de estas opciones de configuración. Cuando se ejecuta como administrador en el espacio empresarial, get-ORCAReport ayudará a generar una evaluación de la configuración de higiene de mensajes, contra correo no deseado y antiphishing. Puede descargar este módulo desde https://www.powershellgallery.com/packages/ORCA/ . 

1. Vaya a [Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat  >  **management**  >  **Policy**.

   ![Página de of_Office de administración de amenazas del Centro de seguridad & 365](../../media/mtp-eval-32.png)
 
2. Haga **clic en Anti-phishing**, **seleccione Crear** y rellene el nombre y la descripción de la directiva. Haga clic en **Siguiente**.

   ![Página de of_Office 365 Security & Compliance Center anti-phishing donde puede nombrar su directiva](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Edite la directiva anti phishing avanzada en Microsoft Defender para Office 365. Cambiar **el umbral de suplantación de** identidad avanzada a **2 : agresivo**.

3. Haga clic **en el menú desplegable Agregar** una condición y seleccione los dominios como dominio de destinatario. Haga clic en **Siguiente**.

   ![Página of_Office directiva contra phishing del Centro de seguridad & 365 donde puede agregar una condición para su aplicación](../../media/mtp-eval-34.png)
 
4. Revisa la configuración. Haga **clic en Crear esta directiva** para confirmar. 

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can review your settings and click the create this policy button](../../media/mtp-eval-35.png)
 
5. Seleccione **Datos adjuntos** seguros y seleccione la opción **Activar ATP para SharePoint, OneDrive y Microsoft Teams.**

   ![Página of_Office centro de seguridad y & 365 donde puede activar ATP para SharePoint, OneDrive y Microsoft Teams](../../media/mtp-eval-36.png)

6. Haga clic en el icono + para crear una nueva directiva de datos adjuntos seguros y aplicarla como dominio de destinatario a los dominios. Haga clic en **Guardar**.

   ![Página of_Office 365 Security & Compliance Center donde puede crear una nueva directiva de datos adjuntos seguros](../../media/mtp-eval-37.png)
 
7. A continuación, seleccione la **directiva Vínculos seguros** y, a continuación, haga clic en el icono de lápiz para editar la directiva predeterminada.

8. Asegúrese de que la opción No realizar **un seguimiento** cuando los usuarios hacen clic en vínculos seguros no está seleccionada, mientras que el resto de las opciones están seleccionadas. Consulta [Configuración de vínculos seguros](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) para obtener más información. Haga clic en **Guardar**. 

   ![Image of_Office 365 Security & Compliance Center page which shows that the option Do not track when users click safe is not selected](../../media/mtp-eval-38.png)

9. A continuación, **seleccione la directiva antimalware,** seleccione el valor predeterminado y elija el icono de lápiz.

10. Haga **clic en** Configuración y seleccione Sí y use el texto de notificación **predeterminado** para habilitar La respuesta **de detección de malware**. Active el **filtro Tipos comunes de datos adjuntos.** Haga clic en **Guardar**.

    ![Página of_Office Centro de seguridad y & cumplimiento de 365 365, que muestra que la respuesta de detección de malware está activada con la notificación predeterminada y el filtro de tipos de datos adjuntos comunes está activado](../../media/mtp-eval-39.png)
  
11. Vaya a [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  **Search**  >  **Log search** and turn Auditing on.

    ![Página of_Office centro de seguridad y & 365 donde puede activar la búsqueda de registro de auditoría](../../media/mtp-eval-40.png)

12. Integre Microsoft Defender para Office 365 con Microsoft Defender para endpoint. Vaya a [Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat management Explorer y seleccione Microsoft Defender for Endpoint Settings en la esquina superior derecha de la  >    >   pantalla.  En el cuadro de diálogo Conexión de Defender para extremo, active **Conectarse a Microsoft Defender para Endpoint**.

    ![Página of_Office centro de seguridad y & 365 donde puedes activar la conexión de Microsoft Defender para endpoint](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>Configurar Microsoft Defender para la identidad

>[!NOTE]
>Omita este paso si ya ha habilitado Microsoft Defender para Identity

1. Vaya a [Centro de seguridad de Microsoft 365](https://security.microsoft.com/info) > seleccione Más **recursos** De Microsoft Defender  >  **para identidad**.

   ![Imagen of_Microsoft página del Centro de seguridad de 365 donde hay una opción para abrir Microsoft Defender para identidad](../../media/mtp-eval-42.png)

2. Haga **clic en** Crear para iniciar el Asistente para Microsoft Defender para identidades. 

   ![Página of_Microsoft asistente de Defender for Identity en la que debes hacer clic en El botón Crear](../../media/mtp-eval-43.png)

3. Elija **Proporcionar un nombre de usuario y una contraseña para conectarse al bosque de Active Directory**.  

   ![Página of_Microsoft de inicio de Defender for Identity](../../media/mtp-eval-44.png)

4. Escriba las credenciales locales de Active Directory. Puede ser cualquier cuenta de usuario que tenga acceso de lectura a Active Directory.

   ![Página de of_Microsoft Defender para los servicios de directorio de identidad donde debe colocar sus credenciales](../../media/mtp-eval-45.png)

5. A continuación, **elija Descargar instalación del sensor** y transferir el archivo al controlador de dominio.

   ![Página de of_Microsoft Defender para identidad en la que puedes seleccionar Descargar configuración del sensor](../../media/mtp-eval-46.png)

6. Ejecute el programa de instalación del sensor de identidad de Microsoft Defender y comience a seguir el asistente.

   ![Página de of_Microsoft Defender para la identidad en la que debes hacer clic junto para seguir el Asistente para sensores de Microsoft Defender para identidad](../../media/mtp-eval-47.png)
 
7. Haga **clic en Siguiente** en el tipo de implementación del sensor.

   ![Página of_Microsoft Defender for Identity donde debes hacer clic junto para ir a la página siguiente](../../media/mtp-eval-48.png)
 
8. Copie la clave de acceso porque debe escribirla a continuación en el Asistente.

   ![Página de of_the sensores de imagen en la que debe copiar la clave de acceso que necesita escribir en la siguiente página del Asistente para la configuración del sensor de Microsoft Defender para identidades](../../media/mtp-eval-49.png)
 
9. Copie la clave de acceso en el Asistente y haga clic **en Instalar**. 

   ![Página of_Microsoft asistente del sensor defender para la identidad donde debe proporcionar la clave de acceso y, a continuación, haga clic en el botón instalar](../../media/mtp-eval-50.png)

10. Enhorabuena, ha configurado correctamente Microsoft Defender para Identity en el controlador de dominio.

    ![Finalización of_Microsoft instalación del asistente para el sensor de Defender for Identity donde debes hacer clic en el botón finalizar](../../media/mtp-eval-51.png)
 
11. En la [sección Configuración de Microsoft Defender para](https://go.microsoft.com/fwlink/?linkid=2040449) identidad, selecciona **Microsoft Defender para endpoint **, luego activa la alternancia. Haga clic en **Guardar**. 

    ![Página of_the configuración de Microsoft Defender para identidad donde debes activar la alternancia de Microsoft Defender para endpoint](../../media/mtp-eval-52.png)

> [!NOTE]
> Windows Defender ATP se ha cambiado de nombre como Microsoft Defender para Endpoint. Los cambios de marca en todos nuestros portales se están implantando para la coherencia.


## <a name="configure-microsoft-cloud-app-security"></a>Configurar Microsoft Cloud App Security

> [!NOTE]
> Omita este paso si ya ha habilitado Microsoft Cloud App Security. 

1. Vaya a [Centro de seguridad de Microsoft 365](https://security.microsoft.com/info)Más  >  **recursos** Microsoft  >  **Cloud App Security**.

   ![Imagen of_Microsoft página del Centro de seguridad de 365 donde puede ver la tarjeta de Microsoft Cloud App y debe hacer clic en el botón abrir](../../media/mtp-eval-53.png)

2. En el símbolo del sistema de información para integrar Microsoft Defender for Identity, seleccione **Habilitar Microsoft Defender para la integración de datos de identidad.**
  
   ![Mensaje de información of_the imagen para integrar Microsoft Defender for Identity donde debe seleccionar el vínculo Habilitar la integración de datos de Microsoft Defender para identidad](../../media/mtp-eval-54.png)

   > [!NOTE]
   > Si no ve este mensaje, puede significar que la integración de datos de Microsoft Defender para identidad ya está habilitada. Sin embargo, si no está seguro, póngase en contacto con el administrador de TI para confirmarlo. 

3. Vaya a **Configuración,** active el botón de alternancia de integración de **Microsoft Defender para identidades** y, a continuación, haga clic **en Guardar**. 

   ![Página de of_the configuración de imagen en la que debes activar el botón de alternancia de integración de Microsoft Defender para identidades y, a continuación, haz clic en Guardar](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > Para las nuevas instancias de Microsoft Defender para Identity, esta alternancia de integración se activa automáticamente. Confirme que la integración de Microsoft Defender para identidades se ha habilitado antes de continuar con el paso siguiente.
 
4. En La configuración de detección en la nube, **selecciona Microsoft Defender para la** integración de puntos de conexión y, a continuación, habilita la integración. Haga clic en **Guardar**.

   ![Imagen of_the página de Microsoft Defender para endpoint donde está activada la casilla bloquear aplicaciones no seleccionadas en Microsoft Defender para la integración de puntos de conexión. Haga clic en Guardar.](../../media/mtp-eval-56.png)

5. En Configuración de detección en la nube, seleccione **Enriquecimiento de usuarios** y, a continuación, habilite la integración con Azure Active Directory.

   ![Sección Imagen de enriquecimiento de usuarios en la que está activada la casilla enriquecer los identificadores de usuario detectados con nombres de usuario de Azure Active Directory](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a>Configurar Microsoft Defender para el extremo

>[!NOTE]
>Omita este paso si ya ha habilitado Microsoft Defender para Endpoint.

1. Vaya a [Centro de seguridad de Microsoft 365](https://security.microsoft.com/info)Más  >  **recursos** Centro  >  **de seguridad de Microsoft Defender**. Haga clic en **Open** (Abrir).

   ![Imagen of_Microsoft centro de seguridad de Defender en la página Centro de seguridad de Microsoft 365](../../media/mtp-eval-58.png)
 
2. Siga el Asistente para Microsoft Defender para puntos de conexión. Haga clic en **Siguiente**. 

   ![Página of_the asistente de bienvenida del Centro de seguridad de Microsoft Defender](../../media/mtp-eval-59.png)

3. Elija en función de la ubicación de almacenamiento de datos preferida, la directiva de retención de datos, el tamaño de la organización y la participación en las características de vista previa.

   ![Página of_the imagen para seleccionar el país de almacenamiento de datos, la directiva de retención y el tamaño de la organización. Haz clic en siguiente cuando termines de seleccionar.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > No puede cambiar parte de la configuración, como la ubicación de almacenamiento de datos, después. 

   Haga clic en **Siguiente**. 

4. Haga **clic en** Continuar y aprovisionará el inquilino de Microsoft Defender para endpoint.

   ![Página de of_the que le pedirá que haga clic en el botón Continuar para crear la instancia en la nube](../../media/mtp-eval-61.png)

5. Incorpore los puntos de conexión a través de directivas de grupo, Microsoft Endpoint Manager o ejecutando un script local en Microsoft Defender para endpoint. Para simplificar, esta guía usa el script local.

6. Haga **clic en Descargar paquete** y copie el script de incorporación en los puntos de conexión.

   ![Image of_page prompting you click the Download package button to copy the onboarding script to your endpoint or endpoints](../../media/mtp-eval-62.png)

7. En el punto de conexión, ejecute el script de incorporación como administrador y elija Y. 

   ![Image of_the commandline where you run the onboarding script and choose Y to proceed](../../media/mtp-eval-63.png)

8. Enhorabuena, ha incorporado su primer punto de conexión.

   ![Imagen of_the línea de comandos donde obtienes la confirmación de que has incorporado el primer punto de conexión. Presione cualquier tecla para continuar](../../media/mtp-eval-64.png)

9. Copie y pegue la prueba de detección desde el Asistente para Microsoft Defender para puntos de conexión.

   ![Image of_the un paso de prueba de detección donde debe hacer clic en Copiar para copiar el script de prueba de detección que debe pegar en el símbolo del sistema](../../media/mtp-eval-65.png)

10. Copie el script de PowerShell en un símbolo del sistema con privilegios elevados y ejecutarlo. 

    ![Símbolo of_command donde debe copiar el script de PowerShell en un símbolo del sistema con privilegios elevados y ejecutarlo](../../media/mtp-eval-66.png)

11. Seleccione **Empezar a usar Microsoft Defender para endpoint** en el Asistente.

    ![Mensaje of_the confirmación del asistente donde debe hacer clic en Empezar a usar Microsoft Defender para endpoint](../../media/mtp-eval-67.png)
 
12. Visite el [Centro de seguridad de Microsoft Defender](https://securitycenter.windows.com/). Vaya a **Configuración y,** a continuación, **seleccione Características avanzadas**. 

    ![Menú of_Microsoft configuración del Centro de seguridad de Defender donde debes seleccionar Características avanzadas](../../media/mtp-eval-68.png)

13. Activa la integración con **Microsoft Defender para Identity**.  

    ![Opciones of_Microsoft Advanced del Centro de seguridad de Defender, opción de Microsoft Defender para identidad que necesitas activar](../../media/mtp-eval-69.png)

14. Active la integración con Inteligencia de amenazas de **Office 365.**

    ![Características avanzadas of_Microsoft centro de seguridad de Defender, alternancia de la opción Inteligencia de amenazas de Office 365 que necesita activar](../../media/mtp-eval-70.png)

15. Activar la integración con **Microsoft Cloud App Security**.

    ![Opciones of_Microsoft Advanced del Centro de seguridad de Defender, opción Microsoft Cloud App Security que debes activar](../../media/mtp-eval-71.png)

16. Desplácese hacia abajo y haga **clic en Guardar preferencias** para confirmar las nuevas integraciones.

    ![Botón of_Save preferencias de imagen que necesita hacer clic](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>Iniciar el servicio de Microsoft 365 Defender

>[!NOTE]
>A partir del 1 de junio de 2020, Microsoft habilita automáticamente las características de Microsoft 365 Defender para todos los inquilinos elegibles. Vea este [artículo de microsoft Tech Community sobre la elegibilidad de licencias](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) para obtener más información. 


Vaya al [Centro de seguridad de Microsoft 365](https://security.microsoft.com/homepage). Vaya a **Configuración** y, a continuación, **seleccione Microsoft 365 Defender**.

![Imagen of_Microsoft captura de pantalla de la opción 365 Defender de la página Configuración del Centro de seguridad de Microsoft 365 ](../../media/mtp-eval-72b.png) <br>

Para obtener una guía más completa, [vea Activar Microsoft 365 Defender](m365d-enable.md). 

¡Enhorabuena! Acaba de crear el entorno piloto o el laboratorio de prueba de Microsoft 365 Defender. Ahora puedes familiarizarte con la interfaz de usuario de Microsoft 365 Defender. Vea lo que puede aprender en la siguiente guía interactiva de Microsoft 365 Defender y sepa cómo usar cada panel para sus tareas diarias de operación de seguridad.

[Consulte la guía interactiva](https://aka.ms/MTP-Interactive-Guide)

A continuación, puedes simular un ataque y ver cómo las capacidades entre productos detectan, crean alertas y responden automáticamente a un ataque sin archivos en un punto de conexión.

## <a name="next-step"></a>Paso siguiente

- [Generar una alerta de prueba:](generate-test-alert.md) ejecute una simulación de ataque en el laboratorio de prueba de Microsoft 365 Defender.