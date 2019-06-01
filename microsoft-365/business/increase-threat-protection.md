---
title: Aumentar la protección contra amenazas para Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Configurar la protección contra amenazas avanzada de Office 365 y proteger los datos confidenciales.
ms.openlocfilehash: b6e9941eee9de4f295b0f8056c1c91b7076e530c
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668408"
---
# <a name="increase-threat-protection"></a>Aumentar la protección contra amenazas

Este artículo le ayuda a aumentar la protección en su suscripción de Microsoft 365 para protegerse contra phishing, malware y otras amenazas. Estas recomendaciones son adecuadas para organizaciones con mayor necesidad de seguridad, como las oficinas de la ley y clínicas de atención médica.

Antes de empezar, Compruebe la puntuación segura de Office 365. La puntuación segura de Office 365 analiza la seguridad de su organización de Office 365 en función de las actividades habituales y la configuración de seguridad y asigna una puntuación. Empiece por tomar nota del resultado actual. La realización de las acciones recomendadas en este artículo aumenta su puntuación. El objetivo no es conseguir la puntuación máxima, sino que debe tener en cuenta las oportunidades para proteger su entorno que no afectan negativamente a la productividad de los usuarios. 

Para obtener más información, consulte [calificación segura de Microsoft](https://docs.microsoft.com/en-us/office365/securitycompliance/microsoft-secure-score).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Aumentar el nivel de protección contra malware en correo

El entorno de Office 365 o Microsoft 365 incluye protección contra malware, pero puede aumentar esta protección bloqueando los datos adjuntos con tipos de archivo que se usan habitualmente para malware. Para aumentar la protección contra malware en el correo electrónico:
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con las credenciales de su cuenta de administrador. 
    
2. En Office &amp; 365 Security Compliance Center, en el panel de navegación izquierdo, en **Administración de amenazas**, elija **anti-malware**de **Directiva** \> .
    
3. Haga doble clic en la directiva predeterminada para editar esta directiva de toda la compañía.
    
4. Haga clic en **configuración**.
    
5. En **filtro de tipos de datos adjuntos comunes**, seleccione **activado**. Los tipos de archivo que están bloqueados aparecen en la ventana que se encuentra justo debajo de este control.  Asegúrese de agregar estos FileTypes:
   - ADE, ADP, Ani, Bas, Bat, CHM, CMD, com, cpl, CRT, HLP, HT, HTA, INF, ins, ISP, Job, JS, JSE, lnk, MDA, MdB, MDE, MDZ, MSC, MSI, MSP, MST, PCD, reg, SCR, SCT, SHS, URL, VB, VBE, vbs, WSC, wsf, WSH, exe, PIF  <br/> Puede Agregar o eliminar tipos de archivo más adelante, si es necesario.
    
6. Haga clic en **Guardar**.
    
Para obtener más información, consulte [Anti-Malware Protection](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409).
  
## <a name="protect-against-ransomware"></a>Proteger contra ransomware

Ransomware restringe el acceso a los datos mediante el cifrado de los archivos o el bloqueo de las pantallas del equipo. A continuación, intenta extort dinero de víctimas solicitando "Ransom", normalmente en forma de cryptocurrencies como bitcoin, en Exchange para tener acceso a los datos. 
  
Puede proteger contra ransomware si crea una o más reglas de flujo de correo para bloquear extensiones de archivo que se usan con frecuencia para ransomware (estas se agregaron en el paso [elevar el nivel de protección contra malware en el correo](#raise-the-level-of-protection-against-malware-in-mail) ) o para advertir a los usuarios que reciben estos datos adjuntos en el correo electrónico.

Además de los archivos bloqueados en el paso anterior, también es aconsejable crear una regla para advertir a los usuarios antes de abrir datos adjuntos de archivos de Office que incluyan macros. Ransomware puede estar oculto dentro de las macros, por lo que se advertirá a los usuarios que no abren estos archivos de personas que no saben.

Para crear una regla de transporte de correo:
  
1. Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> y elija **centros** \> de administración **Exchange**.
    
2. En la categoría **flujo de correo** , haga clic en **reglas**.
    
3. Haga **+** clic en y, a continuación, haga clic en **crear una nueva regla**.
    
4. Haga clic en **más opciones** en la parte inferior del cuadro de diálogo para ver el conjunto completo de opciones. 
    
5. Aplique la configuración de la siguiente tabla para la regla. Deje el resto de las opciones de configuración en el valor predeterminado, a menos que quiera cambiarlos.
    
6. Haga clic en **Guardar **.
    
|**Valor**|**Advertir a los usuarios antes de abrir datos adjuntos de archivos de Office**||
|:-----|:-----|:-----|
|Nombre  <br/> |Regla antiransomware: advertir a los usuarios  <br/>  |
|Aplicar esta regla si. . .  <br/> |Los datos adjuntos. . . coincidencias de extensión de archivo. . .  <br/> |
|Especificar palabras o frases  <br/> |Agregue estos tipos de archivo:  <br/> dotm, docm, xlsm, sltm, XLA, XLAM, xll, pptm, potm, PPAM, ppsm sldm  <br/>|
|Haga lo siguiente. . .  <br/> |Notificar al destinatario con un mensaje  <br/> |
|Proporcionar el texto del mensaje  <br/> |No abra este tipo de archivos de personas que no sabe porque podrían contener macros con código malintencionado.  <br/> |
   
Para obtener más información, vea:
  
- [Cómo tratar con ransomware](https://go.microsoft.com/fwlink/?linkid=2016501&amp;clcid=0x409)
    
- [Restaurar su OneDrive](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)
    


## <a name="stop-auto-forwarding-for-email"></a>Detener el reenvío automático de correo electrónico

Los hackers que obtienen acceso al buzón de un usuario pueden robar el correo estableciendo el buzón para reenviar automáticamente el correo electrónico. Esto puede ocurrir incluso sin la conciencia del usuario. Puede evitar que esto suceda mediante la configuración de una regla de flujo de correo. 
  
Para crear una regla de transporte de correo, vea [este breve vídeo](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) o siga estos pasos:
  
1. En el centro de administración de Microsoft 365, haga clic en **centros** \> de administración **Exchange**.
    
2. En la categoría **flujo de correo** , haga clic en **reglas**.
    
3. Haga **+** clic en y, a continuación, haga clic en **crear una nueva regla**.
    
4. Haga clic en **más opciones** en la parte inferior del cuadro de diálogo para ver el conjunto completo de opciones. 
    
5. Aplique la configuración de la tabla siguiente. Deje el resto de las opciones de configuración en el valor predeterminado, a menos que quiera cambiarlos.
    
6. Haga clic en **Guardar **.
    
|**Valor**|**Advertir a los usuarios antes de abrir datos adjuntos de archivos de Office**|
|:-----|:-----|
|Nombre  <br/> |Impedir el reenvío automático de correo electrónico a dominios externos  <br/> |
|Aplicar esta regla si...  <br/> |El remitente. . . es externo/interno. . . Dentro de la organización  <br/> |
|Agregar condición  <br/> |Las propiedades del mensaje. . . incluir el tipo de mensaje. . . Reenvío automático  <br/> |
|Haga lo siguiente...  <br/> |Bloquear el mensaje. . . rechazar el mensaje e incluir una explicación.  <br/> |
|Proporcionar el texto del mensaje  <br/> |El reenvío automático de correo electrónico fuera de esta organización se impide por motivos de seguridad.  <br/> |


## <a name="protect-your-email-from-phishing-attacks"></a>Proteger el correo electrónico de ataques de suplantación de identidad

Si ha configurado uno o más dominios personalizados para el entorno de Office 365 o Microsoft 365, puede configurar la protección contra suplantas de identidad (phishing) dirigida. La protección contra suplantación de identidad ATP, parte de la protección contra amenazas avanzada de Office 365, puede ayudar a proteger a su organización de ataques de suplantación de identidad (phishing) malintencionados y otros ataques de suplantación de identidad. Si no ha configurado un dominio personalizado, no es necesario que lo haga.
  
Le recomendamos que empiece con esta protección creando una directiva para proteger a los usuarios más importantes y a su dominio personalizado. 

  
Para crear una directiva contra la suplantación de identidad ATP, vea [este vídeo de aprendizaje corto](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)o realice los pasos siguientes:
  
1. Vaya a [https://protection.office.com](https://protection.office.com). 
    
2. En el centro de navegación &amp; izquierdo de Office 365 Security Compliance Center, en **Administración de amenazas**, elija **Directiva**.
    
3. En la página **Directiva** , elija **ATP antiphishing**.
    
4. En la página contra la suplantación de **identidad** , seleccione **+ crear**. Se inicia un asistente que le guía por el proceso de definición de la Directiva antiphishing.
    
5. Especifique el nombre, la descripción y la configuración de la Directiva tal y como se recomienda en el siguiente gráfico. Para obtener más información, consulte [información sobre las opciones de directiva](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409) de antiphishing de ATP. 
    
6. Una vez que haya revisado la configuración, elija **crear esta directiva** o **Guardar**, según corresponda.
    

|**Configuración u opción**<br/>|**Configuración recomendada** <br/>|
|:-----|:-----|
|Nombre  <br/> |Dominio y personal de la campaña más valioso  <br/> |
|Descripción  <br/> |Asegúrese de que el personal más importante y nuestro dominio no se están suplantando.  <br/> |
|Agregar usuarios para protegerlos  <br/> |Seleccionar **+ Agregar condición, el destinatario es**. Escriba los nombres de usuario o escriba la dirección de correo electrónico del candidato, el administrador de campañas y otros miembros importantes del personal. Puede Agregar hasta 20 direcciones internas y externas que desee proteger de la suplantación.  <br/> |
|Agregar dominios para proteger  <br/> |Seleccionar **+ Agregar una condición, el dominio del destinatario es**. Escriba el dominio personalizado asociado con la suscripción de Microsoft 365, si ha definido uno. Puede escribir más de un dominio.  <br/> |
|Elegir acciones  <br/> |Si un usuario suplantado envía un correo electrónico: elija **redirigir un mensaje a otra dirección de correo electrónico**y, a continuación, escriba la dirección de correo electrónico del administrador de seguridad; por ejemplo, *Alicia<span><span>@contoso. com*.          Si un dominio suplantado envía un correo electrónico: elija **mensaje en cuarentena**.  <br/> |
|Inteligencia de buzones  <br/> |De forma predeterminada, la inteligencia de buzones se selecciona cuando se crea una nueva Directiva antiphishing. Deje esta configuración **activada** para obtener los mejores resultados.  <br/> |
|Agregar dominios y remitentes de confianza  <br/> |Aquí puede agregar sus propios dominios o cualquier otro dominio de confianza.  <br/> |
|Aplicado a  <br/> |Seleccione **el dominio del destinatario es**. En **cualquiera de estos**, seleccione **elegir**. Seleccione **+ Agregar**. Active la casilla de verificación situada junto al nombre del dominio, por ejemplo, *contoso.<span> com <span>*, en la lista y, a continuación, seleccione **Agregar**. Seleccione **listo**.  <br/> |
   
Para obtener más información, consulte [configurar las directivas de anti-phishing de Office 365 ATP](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409).
  
## <a name="protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a>Protección contra archivos adjuntos malintencionados y archivos con datos adjuntos seguros de ATP

Los usuarios envían, reciben y comparten con regularidad datos adjuntos, como documentos, presentaciones, hojas de cálculo, etc. No siempre es fácil saber si los datos adjuntos son seguros o malintencionados solo mirando un mensaje de correo electrónico. Office 365 Advanced Threat Protection incluye protección contra datos adjuntos seguros de ATP, pero esta protección no está activada de forma predeterminada. Le recomendamos que cree una nueva regla para comenzar a usar esta protección. Esta protección se extiende a los archivos de SharePoint, OneDrive y Microsoft Teams.
  
Para crear una directiva de datos adjuntos seguros de ATP, vea [este breve vídeo](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)o realice los pasos siguientes:
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta de administrador. 
    
2. En el centro de navegación &amp; izquierdo de Office 365 Security Compliance Center, en **Administración de amenazas**, elija **Directiva**.
    
3. En la página Directiva, seleccione **datos adjuntos seguros de ATP**.
    
4. En la página datos adjuntos seguros, aplique esta protección ampliando la selección de la casilla **Activar ATP para SharePoint, OneDrive y Microsoft Teams** . 
    
5. Seleccione **+** esta directiva para crear una nueva Directiva. 
    
6. Aplique la configuración de la tabla siguiente. 
    
7. Una vez que haya revisado la configuración, elija **crear esta directiva** o **Guardar**, según corresponda.
    

|**Configuración u opción**|**Configuración recomendada** <br/>|
|:-----|:-----|
|Nombre  <br/> |Bloquear los correos electrónicos actuales y futuros con malware detectado.  <br/> |
|Descripción  <br/> |Bloquear los mensajes de correo electrónico y datos adjuntos futuros y futuros con malware detectado.  <br/> |
|Guardar datos adjuntos respuesta de malware desconocida  <br/> |Seleccione **bloquear: bloquear los correos electrónicos y datos adjuntos actuales y futuros con malware detectado**.  <br/> |
|Redirigir datos adjuntos en detección  <br/> |Habilitar redirección (Seleccione esta casilla) escriba la cuenta de administrador o una configuración de buzón para la cuarentena.          Aplique la selección anterior si se produce un error de análisis de malware para datos adjuntos de tiempo de espera o error (Active esta casilla).  <br/> |
|Aplicado a  <br/> |El dominio del destinatario es. . . Seleccione su dominio.  <br/> |
   
Para obtener más información, consulte [configurar las directivas de anti-phishing de Office 365 ATP](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409).
  


## <a name="protect-against-phishing-attacks-with-atp-safe-links"></a>Proteger contra ataques de suplantación de identidad con vínculos seguros de ATP

A veces, los hackers ocultan sitios Web malintencionados en vínculos de correo electrónico u otros archivos. Vínculos seguros de ATP de Office 365 (vínculos seguros de ATP), parte de la protección contra amenazas avanzada de Office 365, puede ayudar a proteger su organización proporcionando una comprobación del tiempo de clic de direcciones web (URL) en mensajes de correo electrónico y documentos de Office. La protección se define mediante las directivas de vínculos seguros de ATP.
  
Le recomendamos que haga lo siguiente:
  
- Modifique la directiva predeterminada para aumentar la protección.
    
- Agregue una nueva Directiva dirigida a todos los destinatarios de su dominio.
    
Para configurar los vínculos seguros ATP, vea [este breve vídeo de aprendizaje](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)o siga los pasos que se indican a continuación:
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta de administrador. 
    
2. En el centro de navegación &amp; izquierdo de Office 365 Security Compliance Center, en **Administración de amenazas**, elija **Directiva**.
    
3. En la página Directiva, elija **vínculos seguros ATP**.
    
Para modificar la directiva predeterminada:
  
1. En la página vínculos seguros, en **directivas que se aplican a toda la organización**, seleccione la directiva **predeterminada** . 
    
2. En **configuración que se aplica al contenido excepto el correo electrónico**, seleccione **Office 365 ProPlus, Office para iOS y Android**.
    
3. Haga clic en **Guardar **. 
    
Para crear una nueva Directiva dirigida a todos los destinatarios de su dominio:
  
1. En la página vínculos seguros, en **directivas que se aplican a toda la organización**, haga clic **+** en para crear una nueva Directiva. 
    
2. Aplique la configuración que se muestra en la tabla siguiente.
    
3. Haga clic en **Guardar **. 

|**Configuración u opción**|**Configuración recomendada** <br/>|
|:-----|:-----|
|Nombre  <br/> |Directiva de vínculos seguros para todos los destinatarios del dominio  <br/> |
|Seleccionar la acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes  <br/> |Seleccione **activado: las direcciones URL se rescribirán y comprobarán con una lista de vínculos malintencionados conocidos cuando el usuario haga clic en el vínculo**.  <br/> |
|Usar datos adjuntos seguros para analizar contenido descargable  <br/> |Seleccione esta casilla.  <br/> |
|Aplicado a  <br/> |El dominio del destinatario es. . . Seleccione su dominio.  <br/> |
   
Para obtener más información, consulte [vínculos seguros de Office 365 ATP](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409).

## <a name="go-to-intune-admin-center"></a>Ir al centro de administración de Intune

1. Inicie sesión en [Azure portal](https://portal.azure.com/).

2. Seleccione **todos los servicios** y escriba *Intune* en el **cuadro de búsqueda**.

3. Una vez que se muestren los resultados, haga clic en el inicio junto a **Microsoft Intune** para convertirlo en un favorito y facilitar su búsqueda más adelante.

Además del centro de administración, puede usar Intune para inscribir y administrar los dispositivos de su organización. Para obtener más información, consulte [capacidades por método de inscripción para dispositivos Windows](https://docs.microsoft.com/intune/enrollment-method-capabs) y [Opciones de inscripción para dispositivos administrados por Intune](https://docs.microsoft.com/intune/enrollment-options).
