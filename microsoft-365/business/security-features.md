---
title: Características de seguridad de Microsoft 365 empresarial
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Obtenga información sobre las características de seguridad que se incluyen con Microsoft 365 empresarial.
ms.openlocfilehash: 17bcc57d57e837f18b05f66cfd54185324f3cad8
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871471"
---
# <a name="microsoft-365-business-security-features"></a>Características de seguridad de Microsoft 365 empresarial

Microsoft 365 Business ofrece características de seguridad simplificada para ayudar a proteger los datos en PC, teléfonos y tabletas.
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Características de seguridad de Microsoft Business de 365 admin center

Puede administrar muchas de las características de seguridad de Microsoft 365 empresarial en el centro de administración, lo que ofrece una manera simplificada de activar o desactivar la estas características. En el centro de administración puede hacer lo siguiente:
  
![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
- [Establecer la configuración de administración de aplicaciones para dispositivos Android o iOS](app-protection-settings-for-android-and-ios.md) . 
    
    Estas opciones incluyen la eliminación de archivos desde un dispositivo inactivo después de un período definido, cifrar los archivos de trabajo, que requieren que los usuarios establecer un PIN, etcetera.
    
- [Establecer la configuración de protección de aplicación para Windows 10 dispositivos](protection-settings-for-windows-10-devices.md) . 
    
    Estas opciones se pueden aplicar a los datos de la compañía en ambas propietaria de la empresa o la propiedad de los usuarios de dispositivos.
    
- [Establecer la configuración de la protección de dispositivo para dispositivos Windows 10](protection-settings-for-windows-10-pcs.md) . 
    
    Puede habilitar el cifrado de [BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405) ayudar a proteger los datos en caso de pérdida o robo de un dispositivo y habilitar [Windows aprovechan Guard](https://go.microsoft.com/fwlink/p/?linkid=871404) proporcionar protección avanzada contra ransomware. 
    
- [Eliminar datos de la empresa de dispositivos](remove-company-data.md)
    
    Puede borrado datos de la compañía si un dispositivo se pierde, robado, o un empleado deja la compañía.
    
- [Dispositivos de restablecer el 10 de Windows a su configuración de fábrica](reset-devices-to-factory-settings.md) . 
    
    Puede restablecer todos los dispositivos de Windows 10 que tengan se les aplica la configuración de protección de dispositivo.
    
## <a name="additional-security-features"></a>Características de seguridad adicionales 

Características avanzadas de Microsoft 365 profesionales están disponibles para ayudarle a proteger su negocio contra amenazas de Internet y proteger la información confidencial.
  
- **[Protección contra amenazas avanzada de Office 365](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    Avanzada protección de amenaza (ATP) ayuda a protege su negocio frente a sofisticada de suplantación de identidad y los ataques de ransomware diseñados para poner en peligro los empleados o información del cliente. Las características incluyen:
    
  - Análisis de archivos adjuntos sofisticado y con tecnología AI análisis para detectar y descartar mensajes peligros.
    
  - Automático comprobaciones de vínculos web en correo electrónico para evaluar si son parte de una combinación de suplantación de identidad. Esto mantiene a salvo pueda tener acceso a sitios Web no seguros.
    
- **[Información general de las directivas de prevención de pérdida de datos](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)** (DLP). 
    
    Puede configurar DLP para detectar automáticamente la información confidencial, como números de tarjeta de crédito, números de seguridad social, etc., para evitar que sus accidentales compartir fuera de la compañía.
    
- **[Archivado de Exchange Online](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Archivado de Exchange Online licencia permite que los mensajes se archivan fácilmente con copia de seguridad continua de los datos. Todos los mensajes de correo electrónico de un usuario, incluidos los elementos eliminados, en caso de que sean necesarios para la detección o la restauración más adelante almacena. Además, puede usar las directivas de retención diferentes para conservar los datos de correo electrónico para retenciones para litigios, exhibición de documentos electrónicos, o para cumplir los requisitos de cumplimiento.
    
- **[Azure Information Protection](https://go.microsoft.com/fwlink/p/?linkid=871406)**
    
    Ayuda a de protección de información que controlar el acceso a información confidencial en documentos y correo electrónico con controles, como "No reenviar" y "No copia". También puede clasificar información confidencial, como "Confidencial" y especificar cómo se puede compartir información clasificado fuera y dentro de la empresa. Cifrado de nivel empresarial es fácil de aplicar a correo electrónico y documentos a proteger la información privada. Microsoft 365 empresarial incluye todas las características de [protección Plan 1 de información de Azure](https://go.microsoft.com/fwlink/p/?linkid=871407). También puede instalar el complemento cliente de protección de la información de Azure para las aplicaciones de Office. Para obtener más detalles, consulte la [Guía de por el Administrador de cliente de protección de la información de Azure](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide).
    
- **[Todas las capacidades de Intune en el portal de Azure](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    Obtener acceso a la Intune centro de administración en el portal de Azure le permite configurar las características de seguridad adicionales, como la administración de dispositivos, iPhone y dispositivos Android junto con la administración avanzada de dispositivos de Windows, Mac OS que no están disponibles a través de Microsoft Centro de administración empresarial 365.
    
Las secciones siguientes describen cómo pueden administrar estas características en la seguridad &amp; centro de cumplimiento y el centro de administración Intune. Con el tiempo se agregarán los controles simplificados para el centro de administración de Microsoft 365 Business.
  
## <a name="set-up-advanced-threat-protection-features"></a>Configurar las características de protección contra amenazas de avanzada

- **Protección contra los datos adjuntos no seguros:** ATP identifica contenido malintencionado al abrir datos adjuntos de correo electrónico en un entorno virtual y realizar un análisis del comportamiento resultante. El contenido se evalúa para determinar su intención (ya sea normal o malintencionado), y ATP bloquea la entrega de los datos adjuntos no seguros, ayudar a proteger el equipo contra esquemas de suplantación de identidad y ransomware infección. Para activar la protección de datos adjuntos, vea [configurar las directivas de Office 365 ATP los datos adjuntos seguros](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775).
    
- Proteja el entorno cuando los usuarios, haga clic en vínculos malintencionados: ATP también examina los vínculos en el correo electrónico en el momento en que un usuario hace clic en ellos. Si un vínculo no es seguro, el usuario se le advierte no para visitar el sitio o informado de que el sitio se ha bloqueado. Esto ayuda a proteger contra esquemas de suplantación de identidad. Puede [configurar las directivas de Office 365 ATP seguros vínculos](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) o [configurar las directivas de Office 365 ATP seguros vínculos](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).
    
## <a name="set-up-dlp-features"></a>Configurar las características DLP

Para obtener un ejemplo acerca de cómo configurar una directiva para proteger la información de identificación personal (PII), vea [crear una directiva de DLP desde una plantilla](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) . 
  
DLP incluye muchas plantillas de listas para usar Directiva para muchas configuraciones regionales diferentes. Por ejemplo, datos financieros Australia, Canadá acto de información Personal, datos financieros de Estados Unidos, etcetera. Para obtener una lista completa, vea [incluyen plantillas de directiva de DLP el qué](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) . Todas estas plantillas se pueden habilitar similar al ejemplo de plantilla PII. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Configurar la retención de correo electrónico con Exchange Online Archiving

 Las características de licencia de **Exchange Online Archiving** proporcionan la capacidad para ayudar a mantener los estándares regulatorios y cumplimiento de normas mediante la conservación de correo electrónico contenido para los fines de exhibición de documentos electrónicos. También ayuda a reducir el riesgo en caso de litigio y proporciona una forma de recuperar datos tras una infracción de seguridad o cuando se necesita recuperar elementos eliminados. Para activar estas funciones, puede usar juicio para conservar todo el contenido de un usuario, o usar las directivas de retención para mayor personalización. 
  
**Juicio:** Puede conservar todo el contenido de buzones de correo, con los elementos eliminados colocando todo el buzón de un usuario en litigio suspensión. 
    
Para colocar un buzón en suspensión por litigio, en el centro de administración:
    
1. En el panel de navegación izquierdo, vaya a **los usuarios** \> **usuarios activos**.
    
2. Seleccione un usuario cuyo buzón de correo que desea poner en litigio suspensión y en el panel de usuario, expanda **configuración de correo** y junto a **más opciones de configuración** , elija **Propiedades de edición de Exchange**.
    
3. En la página buzón de correo para el usuario, elija ** características de buzón ** en el panel de navegación izquierdo y, a continuación, elija el vínculo **Habilitar** en **juicio**.
    
4. En la **suspensión por litigio** cuadro de diálogo puede especificar la retención por juicio duración de la retención en el campo **duración de la suspensión por litigio** , deje el campo vacío si desea colocar una espera infinita. También puede agregar notas y dirigir el propietario del cuadro de correo a un sitio Web es posible que deba explican más información acerca de la retención por juicio suspensión \> **Guardar**.
    
**Retención:** Puede habilitar las directivas de retención personalizada, por ejemplo, para conservar para un período de tiempo específico o eliminar permanentemente el contenido al final del período de retención. Para obtener más información, vea [información general de las directivas de retención](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).
## <a name="set-up-azure-information-protection-features"></a>Configurar las características de protección de la información de Azure

Protección de información Azure (AIP) es una solución basada en la nube que ayuda a una organización a clasificar y proteger de forma opcional, sus documentos y mensajes de correo electrónico mediante la aplicación de las etiquetas. Se pueden aplicar etiquetas automáticamente por los administradores que definen las reglas y condiciones, manualmente por los usuarios, o una combinación donde los usuarios reciben las recomendaciones.

La capacidad para aplicar las siguientes restricciones al enviar mensajes de correo electrónico en Outlook en el web se habilita automáticamente para todos los usuarios:
  
- **No reenviar**: los destinatarios puede leer el mensaje, pero hacia delante, no se pueden imprimir o copiar contenido
    
- **Cifrar**: se cifra el mensaje completo. Los destinatarios deben realizar pasos adicionales para confirmar su identidad antes de obtener acceso a contenido cifrado y no pueden quitar el cifrado.
    
- **Confidencial**: proporciona a los empleados de la organización todos los permisos para el contenido de correo electrónico y los datos adjuntos, pero no para las personas de fuera de la organización. Los propietarios de los datos pueden realizar un seguimiento y revocar el contenido en cualquier momento.
    
- **Altamente confidencial**: esta restricción se puede aplicar a los datos altamente confidenciales, lo que permite a los empleados ver, editar y responder, pero no reenviar, imprimir o copiar los datos. Los propietarios de los datos pueden realizar un seguimiento y revocar el contenido en cualquier momento.

### <a name="make-sure-azure-information-protection-is-activated"></a>Asegúrese de que se activa la protección de la información de Azure

Para comprobar que está activada AIP:

1. Inicie sesión en el [portal de Azure](https://portal.azure.com/).

2. Seleccione **todos los servicios** y el tipo de *Protección de la información de Azure* en el **Cuadro de búsqueda**.

3. Una vez que muestren los resultados, haga clic en el inicio siguiente para la **Protección de la información de Azure** para que sea un favorito y fácil de encontrar más adelante.

4. Seleccione la **Protección de la información de Azure** \> **activación de la protección** y realizar, seguro de que el estado se establece un a activado. 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a>Ver las etiquetas de directiva y un valor predeterminado de la protección de la información de Azure 

Para ver y modificar, etiquetas de la existente:

1. En el panel de protección de la información de Azure, seleccione **las clasificaciones** \> **etiquetas**. <br/>![Etiquetas estándar para la protección de la información de Azure.](media/AIPLabels.png)

2. Puede elegir cualquiera de las etiquetas para ver las opciones, puede cambiar el nombre para mostrar, los colores, etcetera.
 
3. Vea [modificar y crear nuevas etiquetas](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) si desea crear su propio. 

### <a name="install-the-azure-information-protection-client-manually"></a>Instale manualmente el cliente de protección de la información de Azure

Para instalar manualmente el cliente AIP:

1. Descargue **AzInfoProtection.exe** desde el [Centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. Puede comprobar que la instalación se ha completado correctamente mediante la visualización de un documento de Word y asegurándose de que la opción de **proteger** está disponible en la ficha **Inicio** . <br/>![Ficha de protección de lista desplegable en un documento de Word.](media/Word_Protect.png)

Para obtener más información, vea [instalar el cliente](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)

## <a name="go-to-intune-admin-center"></a>Vaya al centro de administración de Intune

1. Inicie sesión en el [portal de Azure](https://portal.azure.com/).

2. Seleccione **todos los servicios** y escriba *Intune* en el **Cuadro de búsqueda**.

3. Una vez que muestren los resultados, haga clic en el inicio siguiente para **Microsoft Intune** para que sea un favorito y fácil de encontrar más adelante.
 
Puede usar Intune para inscribirse y administrar dispositivos de su organización. Para obtener más información, vea [funciones mediante el método de inscripción para los dispositivos de Windows](https://docs.microsoft.com/intune/enrollment-method-capabs) y [las opciones de inscripción para dispositivos administrados por Intune](https://docs.microsoft.com/intune/enrollment-options).
    
## <a name="faq"></a>Preguntas más frecuentes

 ### <a name="are-these-security-features-available-in-all-markets"></a>¿Están disponibles estas características de seguridad en todos los mercados?
  
Sí, estas características están disponibles en todos los mercados donde se vende 365 de Microsoft Business.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>¿Cómo encontrar la seguridad &amp; centro de cumplimiento?
  
1. [Inicie sesión en Microsoft 365 empresarial](https://portal.microsoft.com/) mediante sus credenciales de administrador. 
    
2. En el panel de navegación izquierdo, busque **centros de administración** y expándalo. 
    
    ![En el panel de navegación izquierdo en el centro de administración de Microsoft 365, elija centros de administrador.](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Elija **seguridad &amp; cumplimiento** para ir a la seguridad &amp; centro de cumplimiento.