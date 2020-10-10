---
title: Configurar los pilares de la protección contra amenazas de Microsoft para el entorno piloto o el laboratorio de prueba
description: Configure Microsoft Threat Protection pilares, como Office 365 ATP, Azure ATP, Microsoft Cloud App Security y Microsoft defender ATP, para su laboratorio de pruebas o entorno piloto.
keywords: configurar Microsoft Threat Protection prueba, configuración de prueba de protección contra amenazas de Microsoft, configurar el proyecto piloto de Microsoft Threat Protection Pilot, configurar los pilares de la protección contra amenazas de Microsoft, pilares de la protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 7e9060c804fcdb8445c8d833d8a43dc90a738b04
ms.sourcegitcommit: a83acd5b9eeefd2e20e5bac916fe29d09fb53de9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "48418162"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-or-pilot-environment"></a>Configurar los pilares de la protección contra amenazas de Microsoft para el entorno de prueba o el entorno piloto

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Protección contra amenazas de Microsoft


La creación de un entorno piloto o un laboratorio de pruebas de Microsoft Threat Protection y su implementación es un proceso de tres fases:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Preparar el entorno piloto o el laboratorio de pruebas de Microsoft Threat Protection" />
      <br/>Fase 1: preparación </a><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab or pilot environment" title="Configurar el entorno piloto o el laboratorio de pruebas de Microsoft Threat Protection" />
      <br/>Fase 2: configuración </a><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Configurar cada pilar de protección contra amenazas de Microsoft para su laboratorio de prueba de Microsoft Threat Protection o entorno piloto y los extremos incorporados" />
      <br/>Fase 3: configurar & incorporado </a><br>
</td>
  </tr>
</table>

Actualmente se encuentra en la fase de configuración.


La preparación es fundamental para todas las implementaciones correctas. En este artículo, se le guiará en los puntos que necesitará tener en cuenta a la hora de prepararse para implementar ATP de Microsoft defender.


## <a name="microsoft-threat-protection-pillars"></a>Pilares de la protección contra amenazas de Microsoft
La protección contra amenazas de Microsoft consta de cuatro pilares. Aunque un pilar ya puede proporcionar valor a la seguridad de su organización de red, la habilitación de los cuatro pilares de la protección contra amenazas de Microsoft dará mayor valor a su organización.

![Solución de protección contra amenazas of_Microsoft de imágenes para los usuarios, la protección contra amenazas avanzada de Azure, para extremos protección contra amenazas avanzada de Microsoft defender, para aplicaciones en la nube, seguridad de aplicación en la nube de Microsoft y para datos, protección contra amenazas avanzada de Office 365  ](../../media/mtp-eval-31.png)

Esta sección le guiará para configurar:
-   Protección contra amenazas avanzada de Office 365
-   Azure Advanced Threat Protection 
-   Microsoft Cloud App Security
-   Protección contra amenazas avanzada de Microsoft Defender


## <a name="configure-office-365-advanced-threat-protection"></a>Configuración de la protección contra amenazas avanzada de Office 365

>[!NOTE]
>Omita este paso si ya ha habilitado la protección contra amenazas avanzada de Office 365. 

Hay un módulo de PowerShell denominado analizador de configuración de la *protección contra amenazas avanzada de Office 365 (Orca)* que ayuda a determinar algunas de estas opciones. Cuando se ejecuta como administrador en su espacio empresarial, Get-ORCAReport le ayudará a generar una evaluación de la configuración de protección contra correo electrónico no deseado, anti-phish y otros mensajes. Puede descargar este módulo desde https://www.powershellgallery.com/packages/ORCA/ . 

1. Vaya a la Directiva de administración de amenazas [& cumplimiento del centro de cumplimiento de Office 365](https://protection.office.com/homepage)  >  **Threat management**  >  **Policy**.

   ![Página de la Directiva de administración de amenazas de seguridad of_Office 365 de & de seguridad del centro de cumplimiento](../../media/mtp-eval-32.png)
 
2. Haga clic en **anti-phishing ATP**, seleccione **crear** y rellene el nombre y la descripción de la Directiva. Haga clic en **Siguiente**.

   ![Página de la Directiva de la Directiva antiphishing del centro de cumplimiento de la & de seguridad of_Office 365, donde puede asignar un nombre a la Directiva](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Edite la Directiva antiphishing de ATP avanzada. Cambiar el **umbral de suplantación de identidad avanzado** a **2-agresivo**.

3. Haga clic en el menú desplegable **Agregar condición** y seleccione su dominio o dominios como dominio del destinatario. Haga clic en **Siguiente**.

   ![Página de la Directiva de la Directiva antiphishing del centro de cumplimiento de la & de seguridad of_Office 365, donde puede Agregar una condición para su aplicación](../../media/mtp-eval-34.png)
 
4. Revise la configuración. Haga clic en **crear esta directiva** para confirmar. 

   ![Imagen of_Office 365 de seguridad & página de la Directiva de antiphishing del centro de cumplimiento, donde puede revisar la configuración y hacer clic en el botón crear esta Directiva](../../media/mtp-eval-35.png)
 
5. Seleccione **datos adjuntos seguros de ATP** y seleccione la opción **Activar ATP para SharePoint, OneDrive y Microsoft Teams** .

   ![Imagen of_Office 365 la página del centro de cumplimiento de & de seguridad donde puede activar ATP para SharePoint, OneDrive y Microsoft Teams](../../media/mtp-eval-36.png)

6. Haga clic en el icono + para crear una nueva Directiva de datos adjuntos seguros, aplíquela como dominio del destinatario en sus dominios. Haga clic en **Guardar**.

   ![Imagen of_Office 365 la página del centro de cumplimiento de & de seguridad donde puede crear una nueva Directiva de datos adjuntos seguros](../../media/mtp-eval-37.png)
 
7. A continuación, seleccione la Directiva de **vínculos seguros ATP** y haga clic en el icono de lápiz para editar la directiva predeterminada.

8. Asegúrese de que la opción no **realizar seguimiento cuando los usuarios hagan clic en vínculos seguros** no esté seleccionada, mientras que el resto de las opciones están seleccionadas. Vea [configuración de vínculos seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) para obtener más información. Haga clic en **Guardar**. 

   ![Página of_Office 365 de seguridad & de centro de cumplimiento que muestra que la opción no realiza un seguimiento cuando los usuarios hacen clic en seguro no está seleccionado](../../media/mtp-eval-38.png)

9. A continuación, seleccione la directiva **antimalware** , seleccione la opción predeterminada y elija el icono de lápiz.

10. Haga clic en **configuración** y seleccione **sí y use el texto de notificación predeterminado** para habilitar la **respuesta de detección de malware**. Active el **filtro tipos de datos adjuntos comunes** en. Haga clic en **Guardar**.

    ![Página of_Office 365 de seguridad & de centro de cumplimiento que muestra que la respuesta de detección de malware está activada con notificación predeterminada y el filtro tipos de datos adjuntos comunes está activado](../../media/mtp-eval-39.png)
  
11. Vaya a [Office 365 Security & cumplimiento del centro](https://protection.office.com/homepage)  >  **Search**  >  de**Auditoría** búsqueda y active la auditoría.

    ![Imagen of_Office 365 la página del centro de cumplimiento de & de seguridad donde puede activar la búsqueda de registros de auditoría](../../media/mtp-eval-40.png)

12. Integrar Office 365 ATP con Microsoft defender ATP. Vaya a [Office 365 Security & cumplimiento](https://protection.office.com/homepage)  >  del centro de**Administración de amenazas**  >  **Explorer** y seleccione **WDATP configuración** en la esquina superior derecha de la pantalla. En el cuadro de diálogo conexión ATP de Microsoft defender, Active **conectarse a ATP de Windows**.

    ![Imagen of_Office 365 la página del centro de cumplimiento de & de seguridad donde puede activar la conexión ATP de Windows Defender](../../media/mtp-eval-41.png)

## <a name="configure-azure-advanced-threat-protection"></a>Configurar la protección contra amenazas avanzada de Azure

>[!NOTE]
>Omita este paso si ya ha habilitado la protección contra amenazas avanzada de Azure

1. Vaya a [Microsoft 365 Security Center](https://security.microsoft.com/info) > seleccione **más recursos**  >  **Azure Advanced Threat Protection**.

   ![Página del centro de seguridad de Image of_Microsoft 365 donde hay una opción para abrir la protección contra amenazas avanzada de Azure](../../media/mtp-eval-42.png)

2. Haga clic en **crear** para iniciar el Asistente de Azure Advanced Threat Protection. 

   ![Imagen of_Azure página del asistente de protección contra amenazas avanzada donde debe hacer clic en el botón crear](../../media/mtp-eval-43.png)

3. Elija **proporcionar un nombre de usuario y una contraseña para conectar con el bosque de Active**Directory.  

   ![Imagen of_Azure Página principal de la protección contra amenazas avanzada](../../media/mtp-eval-44.png)

4. Escriba sus credenciales locales de Active Directory. Puede ser cualquier cuenta de usuario que tenga acceso de lectura a Active Directory.

   ![Imagen of_Azure página de servicios de directorio de protección contra amenazas avanzada donde debe colocar sus credenciales](../../media/mtp-eval-45.png)

5. A continuación, seleccione **descargar la configuración del sensor** y transferir el archivo a su controlador de dominio.

   ![Imagen of_Azure página protección avanzada contra amenazas donde puede seleccionar Descargar configuración del sensor](../../media/mtp-eval-46.png)

6. Ejecute la configuración del sensor ATP de Azure y comience a seguir el asistente.

   ![Imagen of_Azure página protección avanzada contra amenazas, en la que debe hacer clic en siguiente para seguir el Asistente para sensores ATP de Azure](../../media/mtp-eval-47.png)
 
7. Haga clic en **siguiente** en el tipo de implementación de sensor.

   ![Imagen of_Azure página protección avanzada contra amenazas en la que debe hacer clic en siguiente para ir a la página siguiente](../../media/mtp-eval-48.png)
 
8. Copie la clave de acceso porque tiene que escribirla a continuación en el asistente.

   ![Página de of_the de la imagen sensores donde debe copiar la clave de acceso que necesita escribir en la próxima página del Asistente para la configuración de sensores de ATP de Azure](../../media/mtp-eval-49.png)
 
9. Copie la clave de acceso en el asistente y haga clic en **instalar**. 

   ![Imagen of_Azure página del Asistente para la protección contra amenazas avanzada de Azure ATP donde debe proporcionar la clave de acceso y, a continuación, haga clic en el botón instalar](../../media/mtp-eval-50.png)

10. Enhorabuena, ha configurado correctamente la protección contra amenazas avanzada de Azure en el controlador de dominio.

    ![Imagen of_Azure protección contra amenazas avanzadas Asistente para sensores ATP de Azure finalización de la instalación donde debe hacer clic en el botón Finalizar](../../media/mtp-eval-51.png)
 
11. En la sección configuración de ATP de Azure [Azure](https://go.microsoft.com/fwlink/?linkid=2040449) , seleccione **ATP de Windows Defender**y, a continuación, active la alternancia. Haga clic en **Guardar**. 

    ![Imagen of_the página de configuración de ATP de Azure Azure donde deberías activar el botón de alternancia de ATP de Windows Defender](../../media/mtp-eval-52.png)

>[!NOTE]
>Windows Defender ATP ha cambiado de marca como ATP de Microsoft defender. Los cambios de personalización de marca en todos nuestros portales se están implementando para lograr coherencia.


## <a name="configure-microsoft-cloud-app-security"></a>Configurar Microsoft Cloud App Security

>[!NOTE]
>Omita este paso si ya ha habilitado Microsoft Cloud App Security. 

1. Vaya a [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **más recursos**  >  **Microsoft Cloud App Security**.

   ![Página del centro de seguridad de of_Microsoft de imágenes 365 donde puede ver la tarjeta de Microsoft Cloud App y debe hacer clic en el botón abrir](../../media/mtp-eval-53.png)

2. En la solicitud de información para integrar ATP de Azure, seleccione **Habilitar la integración de datos de ATP de Azure**.
  
   ![Imagen of_the información sobre la solicitud de integración de ATP de Azure donde debe seleccionar el vínculo habilitar la integración de datos de ATP de Azure](../../media/mtp-eval-54.png)

   > [!NOTE]
   > Si no aparece este mensaje, puede significar que ya se ha habilitado la integración de datos de ATP de Azure. Sin embargo, si no está seguro, póngase en contacto con su administrador de TI para confirmarlo. 

3. Vaya a **configuración**, active el botón de alternancia **integración de ATP de Azure** y haga clic en **Guardar**. 

   ![Página de configuración de of_the de imágenes donde debe activar el botón de alternancia integración de ATP de Azure y, a continuación, haga clic en guardar](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > Para las nuevas instancias de ATP de Azure, este cambio de integración se activa automáticamente. Confirme que la integración de ATP de Azure se haya habilitado antes de continuar con el paso siguiente.
 
4. En la configuración de detección en la nube, seleccione **integración de Microsoft defender ATP**y, a continuación, habilite la integración. Haga clic en **Guardar**.

   ![Imagen of_the página ATP de Microsoft defender en la que la casilla bloquear aplicaciones no autorizadas de la integración de ATP de Microsoft defender está seleccionada. Haga clic en guardar.](../../media/mtp-eval-56.png)

5. En configuración de detección en la nube, seleccione **enriquecimiento de usuario**y, a continuación, habilite la integración con Azure Active Directory.

   ![Imagen de la sección enriquecimiento de usuario donde está seleccionada la casilla enriquecer los identificadores de usuario detectados con nombres de usuario de Azure Active Directory](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-advanced-threat-protection"></a>Configurar la protección contra amenazas avanzada de Microsoft defender

>[!NOTE]
>Omita este paso si ya ha habilitado la protección contra amenazas avanzada de Microsoft defender.

1. Vaya a [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **más recursos**  >  **centro de seguridad de Microsoft defender**. Haga clic en **Open** (Abrir).

   ![Imagen of_Microsoft defender Security Center Option en la página del centro de seguridad de Microsoft 365](../../media/mtp-eval-58.png)
 
2. Siga el Asistente para la protección contra amenazas avanzada de Microsoft defender. Haga clic en **Siguiente**. 

   ![Imagen of_the página del asistente de bienvenida del centro de seguridad de Microsoft defender](../../media/mtp-eval-59.png)

3. Elija en función de la ubicación de almacenamiento de datos preferida, la Directiva de retención de datos, el tamaño de la organización y las características de vista previa.

   ![Imagen of_the página para seleccionar su país de almacenamiento de datos, la Directiva de retención y el tamaño de la organización. Haga clic en siguiente cuando haya terminado de seleccionar.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > No puede cambiar algunos de los valores, como la ubicación de almacenamiento de datos, más adelante. 

   Haga clic en **Siguiente**. 

4. Haga clic en **continuar** y se aprovisionará el inquilino ATP de Microsoft defender.

   ![Imagen of_the página que le pide que haga clic en el botón continuar para crear su instancia de nube](../../media/mtp-eval-61.png)

5. Incorpore los puntos de conexión a través de directivas de grupo, Microsoft Endpoint Manager o mediante la ejecución de un script local a ATP de Microsoft defender. Para simplificar, esta guía usa el script local.

6. Haga clic en **Descargar paquete** y copie el script de incorporación en los extremos.

   ![Imagen of_page le pregunta si desea hacer clic en el botón Descargar paquete para copiar el script de incorporación en el extremo o los extremos](../../media/mtp-eval-62.png)

7. En el punto de conexión, ejecute el script de incorporación como administrador y elija Y. 

   ![Image of_the CommandLine donde se ejecuta el script de incorporación y elija y para continuar.](../../media/mtp-eval-63.png)

8. Enhorabuena, ha incorporado el primer punto de conexión.

   ![Image of_the CommandLine donde recibirá la confirmación de que ha incorporado el primer punto de conexión. Presione cualquier tecla para continuar](../../media/mtp-eval-64.png)

9. Copie-pegue la prueba de detección desde el Asistente para ATP de Microsoft defender.

   ![Imagen of_the ejecute un paso de prueba de detección en el que debe hacer clic en copiar para copiar el script de prueba de detección que debe pegar en el símbolo del sistema](../../media/mtp-eval-65.png)

10. Copie el script de PowerShell en un símbolo del sistema con privilegios elevados y ejecútelo. 

    ![Image of_command prompt donde debe copiar el script de PowerShell en un símbolo del sistema con privilegios elevados y ejecutarlo](../../media/mtp-eval-66.png)

11. Seleccione **empezar a usar ATP de Microsoft defender** desde el asistente.

    ![Imagen of_the mensaje de confirmación del asistente donde debe hacer clic en empezar a usar ATP de Microsoft defender](../../media/mtp-eval-67.png)
 
12. Visite el [centro de seguridad de Microsoft defender](https://securitycenter.windows.com/). Vaya a **configuración** y, a continuación, seleccione **características avanzadas**. 

    ![Menú de configuración del centro de seguridad de imágenes of_Microsoft defender donde debe seleccionar características avanzadas](../../media/mtp-eval-68.png)

13. Active la integración con la **protección contra amenazas avanzada de Azure**.  

    ![Características avanzadas del centro de seguridad de imágenes of_Microsoft defender, opción de protección contra amenazas avanzada de Azure para alternar que debe activar](../../media/mtp-eval-69.png)

14. Active la integración con la **inteligencia sobre amenazas de Office 365**.

    ![Características avanzadas del centro de seguridad de imágenes of_Microsoft defender, Office 365 Threat Intelligence opción para alternar la activación](../../media/mtp-eval-70.png)

15. Active la integración con **Microsoft Cloud App Security**.

    ![Image of_Microsoft defender Security Center Advanced Security Features, Microsoft Cloud App Security opción alternar la activación](../../media/mtp-eval-71.png)

16. Desplácese hacia abajo y haga clic en **Guardar preferencias** para confirmar las nuevas integraciones.

    ![Botón de preferencias de of_Save de imagen en el que debe hacer clic](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-threat-protection-service"></a>Iniciar el servicio de Protección contra amenazas de Microsoft

>[!NOTE]
>A partir del 1 de junio de 2020, Microsoft habilita automáticamente las características de protección contra amenazas de Microsoft para todos los inquilinos elegibles. Consulte este [artículo de la comunidad tecnológica de Microsoft sobre la elegibilidad de licencias](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) para obtener más información. 


Vaya al [centro de seguridad 365 de Microsoft](https://security.microsoft.com/homepage). Vaya a **configuración** y, a continuación, seleccione **protección contra amenazas de Microsoft**.

![Imagen of_Microsoft captura de pantalla de la opción de protección contra amenazas de la página Configuración del centro de seguridad 365 de Microsoft ](../../media/mtp-eval-72b.png) <br>

Para obtener una guía más completa, consulte [activar la protección contra amenazas de Microsoft](mtp-enable.md). 

¡Enhorabuena! Acaba de crear su entorno de prueba de Microsoft Threat Protection o un entorno piloto. Ahora puede familiarizarse con la interfaz de usuario de Microsoft Threat Protection. Vea lo que puede aprender de la siguiente guía interactiva de Microsoft Threat Protection y sepa cómo usar cada panel para las tareas de la operación de seguridad diaria.


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

A continuación, puede simular un ataque y ver cómo las capacidades cruzadas del producto detectan, crean alertas y responden automáticamente a un ataque de archivos no deseados en un extremo.

## <a name="next-step"></a>Paso siguiente
|![Fase de simulación de ataques](../../media/mtp/run-sim.png) <br>[Fase de simulación de ataques](mtp-pilot-simulate.md) | Ejecute la simulación de ataques para su entorno piloto de Microsoft Threat Protection.
|:-------|:-----|
