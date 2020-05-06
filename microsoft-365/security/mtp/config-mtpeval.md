---
title: Configurar los pilares de la protección contra amenazas de Microsoft para el entorno de pruebas de prueba
description: Configurar los pilares de la protección contra amenazas de Microsoft, Office 365 ATP, Azure ATP, Microsoft Cloud App Security y Microsoft defender ATP para su entorno de laboratorio de prueba
keywords: configurar Microsoft Threat Protection prueba, configuración de prueba de protección contra amenazas de Microsoft, configurar los pilares de la protección contra amenazas de Microsoft, pilares de la protección contra amenazas de Microsoft
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
ms.openlocfilehash: 68d8f06803d75c3f89cae6fa7998734fd54084ca
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049514"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-environment"></a>Configurar los pilares de la protección contra amenazas de Microsoft para el entorno de pruebas de prueba

**Se aplica a:**
- Protección contra amenazas de Microsoft


La creación de un entorno de laboratorio de prueba de Microsoft Threat Protection y su implementación es un proceso de tres fases:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Preparar el entorno de laboratorio de prueba de Microsoft Threat Protection" />
      <br/>Fase 1: preparación</a><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Configurar el entorno de laboratorio de prueba de Microsoft Threat Protection" />
      <br/>Fase 2: configuración</a><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Configurar cada pilar de protección contra amenazas de Microsoft para el entorno de laboratorio de prueba de Microsoft Threat Protection y los puntos de conexión incorporados" />
      <br/>Fase 3: configurar & incorporado</a><br>
</td>


  </tr>
</table>

Actualmente se encuentra en la fase de configuración.


La preparación es fundamental para todas las implementaciones correctas. En este artículo, se le guiará en los puntos que necesitará tener en cuenta a la hora de prepararse para implementar ATP de Microsoft defender.


## <a name="microsoft-threat-protection-pillars"></a>Pilares de la protección contra amenazas de Microsoft
La protección contra amenazas de Microsoft consta de cuatro pilares. Aunque un pilar ya puede proporcionar valor a la seguridad de su organización de red, la habilitación de los cuatro pilares de la protección contra amenazas de Microsoft dará mayor valor a su organización.

![Of_page de imagen](../../media/mtp-eval-31.png) <br>

Esta sección le guiará para configurar:
-   Protección contra amenazas avanzada de Office 365
-   Azure Advanced Threat Protection 
-   Microsoft Cloud App Security
-   Protección contra amenazas avanzada de Microsoft Defender


## <a name="configure-office-365-advanced-threat-protection"></a>Configuración de la protección contra amenazas avanzada de Office 365
>[!NOTE]
>Omita este paso si ya ha habilitado la protección contra amenazas avanzada de Office 365. 

Hay un módulo de PowerShell denominado analizador de configuración de la *protección contra amenazas avanzada de Office 365 (Orca)* que ayuda a determinar algunas de estas opciones. Cuando se ejecuta como administrador en su espacio empresarial, Get-ORCAReport le ayudará a generar una evaluación de la configuración de protección contra correo electrónico no deseado, anti-phish y otros mensajes. Puede descargar este módulo desde https://www.powershellgallery.com/packages/ORCA/. 

1. Vaya a la**Directiva**de**Administración** > de amenazas [& cumplimiento del centro](https://protection.office.com/homepage) > de cumplimiento de Office 365.
![Of_page de imagen](../../media/mtp-eval-32.png) <br>
 
2. Haga clic en **anti-phishing ATP**, seleccione **crear** y rellene el nombre y la descripción de la Directiva. Haga clic en **Siguiente**.
![Of_page de imagen](../../media/mtp-eval-33.png) <br>

>[!NOTE]
>Edite la Directiva antiphishing de ATP avanzada. Cambiar el **umbral de suplantación de identidad avanzado** a **2-agresivo**.
<br>

3. Haga clic en el menú desplegable **Agregar condición** y seleccione su dominio o dominios como dominio del destinatario. Haga clic en **Siguiente**.
![Of_page de imagen](../../media/mtp-eval-34.png) <br>
 
4. Revise la configuración. Haga clic en **crear esta directiva** para confirmar. 
![Of_page de imagen](../../media/mtp-eval-35.png) <br>
 
5. Seleccione **datos adjuntos seguros de ATP** y seleccione la opción **Activar ATP para SharePoint, OneDrive y Microsoft Teams** .  
![Of_page de imagen](../../media/mtp-eval-36.png) <br>

6. Haga clic en el icono + para crear una nueva Directiva de datos adjuntos seguros, aplíquela como dominio del destinatario en sus dominios. Haga clic en **Guardar**.
![Of_page de imagen](../../media/mtp-eval-37.png) <br>
 
7. A continuación, seleccione la Directiva de **vínculos seguros ATP** y haga clic en el icono de lápiz para editar la directiva predeterminada.

8. Asegúrese de que la opción no **realizar seguimiento cuando los usuarios hagan clic en vínculos seguros** no esté seleccionada, mientras que el resto de las opciones están seleccionadas. Vea [configuración de vínculos seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) para obtener más información. Haga clic en **Guardar**. 
![Of_page de imagen](../../media/mtp-eval-38.png) <br>

9. A continuación, seleccione la directiva **antimalware** , seleccione la opción predeterminada y elija el icono de lápiz.

10. Haga clic en **configuración** y seleccione **sí y use el texto de notificación predeterminado** para habilitar la **respuesta de detección de malware**. Active el **filtro tipos de datos adjuntos comunes** en. Haga clic en **Guardar**.
<br>![Of_page de imagen](../../media/mtp-eval-39.png) <br>
  
11. Vaya a [Office 365 Security & cumplimiento del centro](https://protection.office.com/homepage) > **Search** > de**Auditoría** búsqueda y active la auditoría.  
![Of_page de imagen](../../media/mtp-eval-40.png) <br>

12. Integrar Office 365 ATP con Microsoft defender ATP. Vaya a [Office 365 Security & cumplimiento del centro](https://protection.office.com/homepage) > de**Administración** > **de amenazas y seleccione** **WDATP configuración** en la esquina superior derecha de la pantalla. En el cuadro de diálogo conexión ATP de Microsoft defender, Active **conectarse a ATP de Windows**.
![Of_page de imagen](../../media/mtp-eval-41.png) <br>

## <a name="configure-azure-advanced-threat-protection"></a>Configurar la protección contra amenazas avanzada de Azure
>[!NOTE]
>Omita este paso si ya ha habilitado la protección contra amenazas avanzada de Azure


1. Vaya a [Microsoft 365 Security Center](https://security.microsoft.com/info) > seleccione **más recursos** > **Azure Advanced Threat Protection**.
![Of_page de imagen](../../media/mtp-eval-42.png) <br>

2. Haga clic en **crear** para iniciar el Asistente de Azure Advanced Threat Protection. 
<br>![Of_page de imagen](../../media/mtp-eval-43.png) <br>

3. Elija **proporcionar un nombre de usuario y una contraseña para conectar con el bosque de Active**Directory.  
![Of_page de imagen](../../media/mtp-eval-44.png) <br>

4. Escriba sus credenciales locales de Active Directory. Puede ser cualquier cuenta de usuario que tenga acceso de lectura a Active Directory.
![Of_page de imagen](../../media/mtp-eval-45.png) <br>

5. A continuación, seleccione **descargar la configuración del sensor** y transferir el archivo a su controlador de dominio. 
![Of_page de imagen](../../media/mtp-eval-46.png) <br>

6. Ejecute la configuración del sensor ATP de Azure y comience a seguir el asistente.
<br>![Of_page de imagen](../../media/mtp-eval-47.png) <br>
 
7. Haga clic en **siguiente** en el tipo de implementación de sensor.
<br>![Of_page de imagen](../../media/mtp-eval-48.png) <br>
 
8. Copie la clave de acceso, ya que tendrá que escribirla a continuación en el asistente.
![Of_page de imagen](../../media/mtp-eval-49.png) <br>
 
9. Copie la clave de acceso en el asistente y haga clic en **instalar**. 
<br>![Of_page de imagen](../../media/mtp-eval-50.png) <br>

10. Enhorabuena, ha configurado correctamente la protección contra amenazas avanzada de Azure en el controlador de dominio.
![Of_page de imagen](../../media/mtp-eval-51.png) <br>
 
11. En la sección configuración de ATP de Azure [Azure](https://go.microsoft.com/fwlink/?linkid=2040449) , seleccione **ATP de Windows Defender**y, a continuación, cambie el botón de alternancia a. Haga clic en **Guardar**. 
![Of_page de imagen](../../media/mtp-eval-52.png) <br>

>[!NOTE]
>Windows Defender ATP ha cambiado de marca como ATP de Microsoft defender. Los cambios de personalización de marca en todos nuestros portales se están implementando para lograr coherencia.


## <a name="configure-microsoft-cloud-app-security"></a>Configurar Microsoft Cloud App Security
>[!NOTE]
>Omita este paso si ya ha habilitado Microsoft Cloud App Security. 

1. Vaya a [Microsoft 365 Security Center](https://security.microsoft.com/info) > **más recursos** > **Microsoft Cloud App Security**.
![Of_page de imagen](../../media/mtp-eval-53.png) <br>

2. En la solicitud de información para integrar ATP de Azure, seleccione **Habilitar la integración de datos de ATP de Azure**. 
<br>![Of_page de imagen](../../media/mtp-eval-54.png) <br>

>[!NOTE]
>Si no aparece este mensaje, puede significar que ya se ha habilitado la integración de datos de ATP de Azure. Sin embargo, si no está seguro, póngase en contacto con su administrador de TI para confirmarlo. 

3. Vaya a **configuración**, active la opción de alternancia de **Azure ATP Integration** y, a continuación, haga clic en **Guardar**. 
![Of_page de imagen](../../media/mtp-eval-55.png) <br>
>[!NOTE]
>Para las nuevas instancias de ATP de Azure, este cambio de integración se activa automáticamente. Confirme que la integración de ATP de Azure se haya habilitado antes de continuar con el paso siguiente.
 
4. En la configuración de detección en la nube, seleccione **integración de Microsoft defender ATP**y, a continuación, habilite la integración. Haga clic en **Guardar**.
![Of_page de imagen](../../media/mtp-eval-56.png) <br>

5. En configuración de detección en la nube, seleccione **enriquecimiento de usuario**y, a continuación, habilite la integración con Azure Active Directory.
![Of_page de imagen](../../media/mtp-eval-57.png) <br>

## <a name="configure-microsoft-defender-advanced-threat-protection"></a>Configurar la protección contra amenazas avanzada de Microsoft defender
>[!NOTE]
>Omita este paso si ya ha habilitado la protección contra amenazas avanzada de Microsoft defender.

1. Vaya a [Microsoft 365 Security Center](https://security.microsoft.com/info) > **más recursos** > **centro de seguridad de Microsoft defender**. Haga clic en **Open** (Abrir).
<br>![Of_page de imagen](../../media/mtp-eval-58.png) <br>
 
2. Siga el Asistente para la protección contra amenazas avanzada de Microsoft defender. Haga clic en **Siguiente**. 
<br>![Of_page de imagen](../../media/mtp-eval-59.png) <br>

3. Elija en función de la ubicación de almacenamiento de datos preferida, la Directiva de retención de datos, el tamaño de la organización y las características de vista previa. 
<br>![Of_page de imagen](../../media/mtp-eval-60.png) <br>
>[!NOTE]
>No puede cambiar algunos de los valores, como la ubicación de almacenamiento de datos, más adelante. 
<br>

Haga clic en **Siguiente**. 

4. Haga clic en **continuar** y se aprovisionará el inquilino ATP de Microsoft defender.
<br>![Of_page de imagen](../../media/mtp-eval-61.png) <br>

5. Incorpore los puntos de conexión a través de directivas de grupo, Microsoft Endpoint Manager o mediante la ejecución de un script local a ATP de Microsoft defender. Para simplificar, esta guía usa el script local.

6. Haga clic en **Descargar paquete** y copie el script de incorporación en los extremos.  
<br>![Of_page de imagen](../../media/mtp-eval-62.png) <br>

7. En el punto de conexión, ejecute el script de incorporación como administrador y elija Y.
<br>![Of_page de imagen](../../media/mtp-eval-63.png) <br>

8. Enhorabuena, ha incorporado el primer punto de conexión.  
<br>![Of_page de imagen](../../media/mtp-eval-64.png) <br>

9. Copie-pegue la prueba de detección desde el Asistente para ATP de Microsoft defender.
<br>![Of_page de imagen](../../media/mtp-eval-65.png) <br>

10. Copie el script de PowerShell en un símbolo del sistema con privilegios elevados y ejecútelo. 
<br>![Of_page de imagen](../../media/mtp-eval-66.png) <br>

11. Seleccione **empezar a usar ATP de Microsoft defender** desde el asistente.
<br>![Of_page de imagen](../../media/mtp-eval-67.png) <br>
 
12. Visite el [centro de seguridad de Microsoft defender](https://securitycenter.windows.com/). Vaya a **configuración** y, a continuación, seleccione **características avanzadas**. 
<br>![Of_page de imagen](../../media/mtp-eval-68.png) <br>

13. Active la integración con la **protección contra amenazas avanzada de Azure**.  
<br>![Of_page de imagen](../../media/mtp-eval-69.png) <br>

14. Active la integración con la **inteligencia sobre amenazas de Office 365**.
<br>![Of_page de imagen](../../media/mtp-eval-70.png) <br>

15. Active la integración con **Microsoft Cloud App Security**.
<br>![Of_page de imagen](../../media/mtp-eval-71.png) <br>

16. Desplácese hacia abajo y haga clic en **Guardar preferencias** para confirmar las nuevas integraciones.
<br>![Of_page de imagen](../../media/mtp-eval-72.png) <br>

## <a name="next-steps"></a>Pasos siguientes
[Active la protección contra amenazas de Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service) y, a continuación, [genere una alerta de prueba](generate-test-alert.md).
