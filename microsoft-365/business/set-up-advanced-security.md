---
title: Configurar las directivas de seguridad avanzadas para los usuarios de Microsoft 365 empresa
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
ms.openlocfilehash: 4728e11a16fdf8a461f5687632df75699923f846
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "33663658"
---
# <a name="set-up-advanced-security-policies"></a>Configurar directivas de seguridad avanzada

Además de las directivas que puede configurar en el centro de [Administración](security-features.md#microsoft-365-business-admin-center-security-features), puede agregar protección adicional contra amenazas en la instalación si configura la [protección contra amenazas avanzada](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653) (ATP) de Office 365. También puede proteger la información confidencial mediante la configuración de [prevención de pérdida de datos](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) (DLP), Azure Information Protection (AIP), archivado de [Exchange Online](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)y también administrar los dispositivos en el portal de Intune. [](#go-to-intune-admin-center)

Consulte las [10 formas principales de proteger el plan de negocio de Microsoft 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) para obtener información general sobre las formas más importantes en las que puede proteger su empresa, incluido el uso de MFA para crear un segundo formulario de inicio de sesión.

Consulte [proteger los vídeos de aprendizaje empresarial](https://support.office.com/article/e12187b8-216a-4490-9e3b-df34a06fb787) para obtener instrucciones sobre las instrucciones de fácil seguimiento.

## <a name="increase-email-malware-protection"></a>Aumentar la protección contra malware del correo electrónico

El malware es software que puede dañar los equipos o la red, y posiblemente robar datos del usuario, incluida la información personal o de cliente. Microsoft 365 Business incluye un nivel básico de protección contra malware, pero puede aumentar esta protección si configura opciones adicionales. Consulte [Activar](https://support.office.com/article/02b5783a-eea0-42e8-8856-62440718c3f0) el vídeo de aprendizaje de detección de malware para obtener instrucciones.

## <a name="set-up-advanced-threat-protection-features"></a>Configurar las características de la protección contra amenazas avanzada

- **Protéjase contra datos adjuntos no seguros:** ATP identifica contenido malintencionado abriendo datos adjuntos de correo electrónico en un entorno virtual y realizando análisis del comportamiento resultante. El contenido se evalúa para determinar su propósito (ya sea normal o malicioso) y ATP bloquea la entrega de datos adjuntos inseguros, lo que ayuda a protegerse contra las tramas de suplantación de identidad y las infecciones por ransomware. Para activar la protección de datos adjuntos, consulte Configurar un vídeo de aprendizaje de [datos adjuntos seguros de Office 365 ATP](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775) y [proteger contra archivos malintencionados](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5) .
    
- **Proteja su entorno cuando los usuarios hacen clic en vínculos malintencionados:** ATP también examina los vínculos del correo electrónico en el momento en el que el usuario hace clic en ellos. Si un vínculo no es seguro, se advierte al usuario de que no va a visitar el sitio ni que se le informe de que se ha bloqueado el sitio. Esto ayuda a proteger contra las tramas de suplantación de identidad. Para activar esto, consulte [configurar vídeo seguro de Office 365 ATP](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies) ayuda y [proteger contra sitios malintencionados](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa) vídeo de aprendizaje corto.

- **Proteja su entorno del intento de suplantación de identidad:**  El antiphishing de ATP aplica un conjunto de modelos de aprendizaje automático junto con algoritmos de detección de suplantación a los mensajes entrantes para proporcionar protección frente a ataques de suplantación de identidad (phishing) en los que alguien está tratando de extraer la información que pretende ser un conocido Contact. Para activar esto, consulte Configurar el vídeo de la ayuda de la protección contra suplantación de identidad [(ATP](https://docs.microsoft.com/office365/securitycompliance/set-up-anti-phishing-policies) ) y [proteger contra phishing](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c) .

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

Para obtener más información, vea [instalar el cliente](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).

## <a name="go-to-intune-admin-center"></a>Ir al centro de administración de Intune

1. Inicie sesión en [Azure portal](https://portal.azure.com/).

2. Seleccione **todos los servicios** y escriba *Intune* en el **cuadro de búsqueda**.

3. Una vez que se muestren los resultados, haga clic en el inicio junto a **Microsoft Intune** para convertirlo en un favorito y facilitar su búsqueda más adelante.

Además del centro de administración, puede usar Intune para inscribir y administrar los dispositivos de su organización. Para obtener más información, consulte [capacidades por método de inscripción para dispositivos Windows](https://docs.microsoft.com/intune/enrollment-method-capabs) y [Opciones de inscripción para dispositivos administrados por Intune](https://docs.microsoft.com/intune/enrollment-options).

## <a name="microsoft-secure-score"></a>Puntuación de seguridad de Microsoft

