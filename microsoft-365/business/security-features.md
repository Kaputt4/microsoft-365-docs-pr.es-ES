---
title: Características de seguridad empresarial de Microsoft 365
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-security-compliance
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Obtenga información sobre las características de seguridad incluidas en Microsoft 365 Business.
ms.openlocfilehash: 24d4c4e79e7d8737beb82336796956774f127209
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286910"
---
# <a name="microsoft-365-business-security-features"></a>Características de seguridad empresarial de Microsoft 365

Microsoft 365 Business ofrece características de seguridad simplificadas para ayudarle a proteger sus datos en equipos, teléfonos y tabletas.
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Características de seguridad del centro de administración de Microsoft 365 Business

Puede administrar muchas de las características de seguridad empresarial de Microsoft 365 en el centro de administración, lo que le proporciona una forma simplificada de activar o desactivar estas características. En el centro de administración, puede hacer lo siguiente:
  
![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
- [Establezca la configuración de administración de aplicaciones para dispositivos Android o iOS](app-protection-settings-for-android-and-ios.md) . 
    
    Estas configuraciones incluyen la eliminación de archivos de un dispositivo inactivo después de un período de tiempo determinado, el cifrado de archivos de trabajo, lo que requiere que los usuarios establezcan un PIN, etc.
    
- [Establezca la configuración de protección de aplicaciones para dispositivos con Windows 10](protection-settings-for-windows-10-devices.md) . 
    
    Esta configuración se puede aplicar a los datos de la empresa en dispositivos de propiedad de la empresa o de propiedad personal.
    
- [Establezca la configuración de protección de dispositivos para dispositivos con Windows 10](protection-settings-for-windows-10-pcs.md) . 
    
    Puede habilitar el cifrado de [BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405) para ayudar a proteger los datos en caso de pérdida o robo de un dispositivo, y habilitar la protección contra [ataques de Windows](https://go.microsoft.com/fwlink/p/?linkid=871404) para proporcionar protección avanzada contra ransomware. 
    
- [Eliminar datos de la empresa de dispositivos](remove-company-data.md)
    
    Puede borrar datos de la empresa de forma remota si un dispositivo se pierde, si es robado o si un empleado abandona la compañía.
    
- [Restablece los dispositivos con Windows 10 a su configuración de fábrica](reset-devices-to-factory-settings.md) . 
    
    Puede restablecer cualquier dispositivo de Windows 10 que tenga aplicada la configuración de protección de dispositivos.
    
## <a name="additional-security-features"></a>Características de seguridad adicionales 

Hay disponibles características avanzadas de Microsoft 365 Business para ayudarle a proteger su negocio de las amenazas cibernéticos y salvaguardar la información confidencial.
  
- **[Protección contra amenazas avanzada de Office 365](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    La protección contra amenazas avanzada (ATP) ayuda a proteger su empresa contra ataques de suplantación de identidad y ataque de ransomware sofisticados, diseñados para comprometer la información de empleados o clientes Entre las características se incluyen:
    
  - Análisis sofisticado de archivos adjuntos y análisis con tecnología de AI para detectar y descartar mensajes peligrosos.
    
  - Comprobaciones automáticas de los vínculos Web en el correo electrónico para evaluar si forman parte de un esquema de suplantación de identidad. Esto le impide tener acceso a sitios web no seguros.
    
- **[Introducción a las directivas de prevención de pérdida de datos](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)** (DLP). 
    
    Puede configurar DLP para que detecte automáticamente información confidencial, como números de tarjetas de crédito, números de la seguridad social, etc., para evitar que se comparta involuntariamente fuera de la compañía.
    
- **[Archivado de Exchange Online](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    La licencia de archivado de Exchange Online permite archivar fácilmente los mensajes con una copia de seguridad de datos continua. Almacena todos los correos electrónicos de un usuario, incluidos los elementos eliminados, en caso de que se necesiten más adelante para su detección o restauración. Además, puede usar directivas de retención diferentes para conservar los datos de correo electrónico para retenciones por juicio, eDiscovery o para cumplir con los requisitos de cumplimiento.
    
- **[Azure Information Protection](https://go.microsoft.com/fwlink/p/?linkid=871406)**
    
    La protección de la información le ayuda a controlar el acceso a la información confidencial en correos electrónicos y documentos con controles como "no reenviar" y "no copiar". También puede clasificar la información confidencial como "confidencial" y especificar cómo se puede compartir la información clasificada fuera y dentro de la empresa. El cifrado de nivel empresarial es fácil de aplicar en el correo electrónico y los documentos para mantener la privacidad de la información. Microsoft 365 Business incluye todas las características del [plan 1 de Azure Information Protection](https://go.microsoft.com/fwlink/p/?linkid=871407). También puede instalar el complemento cliente de Azure Information Protection para aplicaciones de Office. Para obtener más información, consulte [Azure Information Protection Client por Guide](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide).
    
- **[Todas las capacidades de Intune en Azure portal](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    El acceso al centro de administración de Intune en Azure portal le permite configurar características de seguridad adicionales, como la administración de dispositivos de MacOS, dispositivos iPhone y Android junto con la administración avanzada de dispositivos para Windows, que no están disponibles a través de Microsoft 365 centro de administración empresarial.
    
En las secciones siguientes se describe cómo puede administrar estas características en el &amp; centro de seguridad y cumplimiento y el centro de administración de Intune. Con el tiempo, los controles simplificados se agregarán al centro de administración de Microsoft 365 Business.
  
## <a name="set-up-advanced-threat-protection-features"></a>Configurar las características de la protección contra amenazas avanzada

- **Protéjase contra datos adjuntos no seguros:** ATP identifica contenido malintencionado abriendo datos adjuntos de correo electrónico en un entorno virtual y realizando análisis del comportamiento resultante. El contenido se evalúa para determinar su propósito (ya sea normal o malicioso) y ATP bloquea la entrega de datos adjuntos inseguros, lo que ayuda a protegerse contra las tramas de suplantación de identidad y las infecciones por ransomware. Para activar la protección de datos adjuntos, consulte [configurar las directivas de datos adjuntos seguros de Office 365 ATP](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775).
    
- Proteja su entorno cuando los usuarios hacen clic en vínculos malintencionados: ATP también examina los vínculos en el correo electrónico en el momento en que el usuario hace clic en ellos. Si un vínculo no es seguro, se advierte al usuario de que no va a visitar el sitio ni que se le informe de que se ha bloqueado el sitio. Esto ayuda a proteger contra las tramas de suplantación de identidad. Puede [configurar directivas de vínculos seguros de office 365 ATP](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) o [configurar directivas de vínculos seguros de atp de Office 365](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).
    
## <a name="set-up-dlp-features"></a>Configurar las características de DLP

Consulte [crear una directiva DLP a partir de una plantilla](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) para obtener un ejemplo sobre cómo configurar una directiva para protegerla contra información de identificación personal (PII). 
  
DLP incluye varias plantillas de directiva listas para usarse para muchas configuraciones regionales diferentes. Por ejemplo, datos financieros de Australia, Act de información personal de Canadá, datos financieros de Estados Unidos, etc. Vea [Qué incluyen las plantillas de directiva de DLP](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) para obtener una lista completa. Todas estas plantillas se pueden habilitar de forma similar al ejemplo de plantilla PII. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Configurar la retención de correo electrónico con el archivado de Exchange Online

 Las características de licencia de archivado de **Exchange Online** ofrecen la capacidad de ayudarle a mantener el cumplimiento normativo y el cumplimiento de las normas al preservar el contenido de correo electrónico con fines de exhibición de documentos electrónicos. También ayuda a reducir el riesgo en caso de litigio y ofrece una forma de recuperar datos después de una infracción de seguridad o cuando se necesitan recuperar elementos eliminados. Para activar estas funciones, puede usar la retención por juicio para conservar todo el contenido de un usuario o usar directivas de retención para una mayor personalización. 
  
**Retención por juicio:** Puede conservar todo el contenido del buzón, incluidos los elementos eliminados, al poner el buzón completo de un usuario en retención por juicio. 
    
Para poner un buzón de correo en retención por juicio, en el centro de administración:
    
1. En el panel de navegación izquierdo, **** \> vaya a usuarios **activos**.
    
2. Seleccione un usuario cuyo buzón quiera poner en retención por juicio y, en el panel usuario, expanda **configuración de correo** y, junto a **configuración adicional** , elija **Editar propiedades de Exchange**.
    
3. En la página buzón del usuario, elija * * características de buzón * * en el panel de navegación izquierdo y, a continuación, elija el vínculo **Habilitar** en **retención por juicio**.
    
4. En el cuadro de diálogo **retención por juicio** , puede especificar la duración de retención por juicio en el campo **duración** de retención por juicio, deje el campo vacío si desea realizar una suspensión infinita. También puede agregar notas y dirigir el propietario del buzón de correo a un sitio web que tenga que explicar más sobre la retención \> **** por juicio.
    
**Retención:** Puede habilitar las directivas de retención personalizadas, por ejemplo, para conservarlas durante un período de tiempo determinado o eliminar el contenido de forma permanente al final del período de retención. Para obtener más información, vea [información general sobre las directivas de retención](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).
## <a name="set-up-azure-information-protection-features"></a>Configurar las características de Azure Information Protection

Azure Information Protection (AIP) es una solución basada en la nube que ayuda a una organización a clasificar y, de manera opcional, proteger sus documentos y correos electrónicos mediante la aplicación de etiquetas. Las etiquetas pueden ser aplicadas automáticamente por los administradores que definen las reglas y condiciones, manualmente por los usuarios o una combinación en la que los usuarios obtienen recomendaciones.

La capacidad de aplicar las siguientes restricciones cuando se envían correos electrónicos en Outlook en la web se habilita automáticamente para todos los usuarios:
  
- **** No reenviar: los destinatarios pueden leer el mensaje, pero no pueden reenviar, imprimir o copiar contenido
    
- **Encrypt**: todo el mensaje está cifrado. Los destinatarios deben realizar pasos adicionales para confirmar su identidad antes de obtener acceso al contenido cifrado y no pueden quitar el cifrado.
    
- **Confidencial**: proporciona a los empleados de su organización permisos totales para el contenido de correo electrónico y los datos adjuntos, pero no para los usuarios ajenos a la organización. Los propietarios de datos pueden realizar un seguimiento y revocar el contenido en cualquier momento.
    
- **Extremadamente confidencial**: esta restricción se puede aplicar a datos extremadamente confidenciales, lo que permite a los empleados ver, editar y responder, pero no reenviar, imprimir o copiar los datos. Los propietarios de datos pueden realizar un seguimiento y revocar el contenido en cualquier momento.

### <a name="make-sure-azure-information-protection-is-activated"></a>Asegurarse de que Azure Information Protection está activado

Para comprobar que se ha activado AIP:

1. Inicie sesión en [Azure portal](https://portal.azure.com/).

2. Seleccione **todos los servicios** y escriba *Azure Information Protection* en el **cuadro de búsqueda**.

3. Una vez que se muestren los resultados, haga clic en el inicio junto a **Azure Information Protection** para que sea un favorito y fácil de encontrar más adelante.

4. Seleccione **activación de protección** de **Azure Information Protection** \> y asegúrese de que el estado está establecido en activado. 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a>Ver la Directiva de Azure Information Protection y las etiquetas predeterminadas 

Para ver y modificar las etiquetas existentes:

1. En el panel de Azure Information Protection, seleccione **etiquetas**de **clasificación** \> . <br/>![Etiquetas estándar para Azure Information Protection.](media/AIPLabels.png)

2. Puede elegir cualquier etiqueta para ver las opciones, puede cambiar el nombre para mostrar, los colores, etc.
 
3. Vea [modificar y crear etiquetas nuevas](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) si desea crear las suyas propias. 

### <a name="install-the-azure-information-protection-client-manually"></a>Instalar el cliente de Azure Information Protection de forma manual

Para instalar manualmente el cliente de AIP:

1. Descargue **AzInfoProtection. exe** desde el [centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. Puede comprobar que la instalación ha funcionado viendo un documento de Word y asegurándose de que la opción **proteger** está disponible en la ficha **Inicio** . <br/>![Cuadro desplegable de la pestaña protección en un documento de Word.](media/Word_Protect.png)

Para obtener más información, consulte [instalar el cliente](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)

## <a name="go-to-intune-admin-center"></a>Ir al centro de administración de Intune

1. Inicie sesión en [Azure portal](https://portal.azure.com/).

2. Seleccione **todos los servicios** y escriba *Intune* en el **cuadro de búsqueda**.

3. Una vez que se muestren los resultados, haga clic en el inicio junto a **Microsoft Intune** para convertirlo en un favorito y facilitar su búsqueda más adelante.
 
Puede usar Intune para inscribir y administrar los dispositivos de su organización. Para obtener más información, consulte [capacidades por método de inscripción para dispositivos Windows](https://docs.microsoft.com/intune/enrollment-method-capabs) y [Opciones de inscripción para dispositivos administrados por Intune](https://docs.microsoft.com/intune/enrollment-options).
    
## <a name="faq"></a>Preguntas frecuentes

 ### <a name="are-these-security-features-available-in-all-markets"></a>¿Estas características de seguridad están disponibles en todos los mercados?
  
Sí, estas características están disponibles en todos los mercados en los que se vende Microsoft 365 Business.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>¿Cómo encuentro el centro de &amp; seguridad y cumplimiento?
  
1. [Inicie sesión en Microsoft 365 Business](https://portal.microsoft.com/) mediante sus credenciales de administrador. 
    
2. En el panel de navegación izquierdo, busque **centros de administración** y expándalo. 
    
    ![En el panel de navegación izquierdo del centro de administración de Microsoft 365, elija centros de administración.](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Elija **cumplimiento &amp; de seguridad** para ir al &amp; centro de seguridad y cumplimiento.