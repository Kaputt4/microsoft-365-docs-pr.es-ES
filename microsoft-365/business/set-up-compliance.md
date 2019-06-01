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
ms.openlocfilehash: 53741a7726222bb32329a401953be72257df95cc
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668407"
---
# <a name="set-up-compliance-features"></a>Configurar las características de cumplimiento

Su empresa de Microsoft 365 incluye características para proteger sus datos y dispositivos, y ayudarle a mantener seguros a los suyos y a los clientes la información confidencial.

## <a name="set-up-dlp-features"></a>Configurar las características de DLP

Consulte [crear una directiva DLP a partir de una plantilla](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) para obtener un ejemplo sobre cómo configurar una directiva para protegerla contra información de identificación personal (PII). 
  
DLP incluye varias plantillas de directiva listas para usarse para muchas configuraciones regionales diferentes. Por ejemplo, datos financieros de Australia, Act de información personal de Canadá, datos financieros de Estados Unidos, etc. Vea [Qué incluyen las plantillas de directiva de DLP](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) para obtener una lista completa. Todas estas plantillas se pueden habilitar de forma similar al ejemplo de plantilla PII. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Configurar la retención de correo electrónico con el archivado de Exchange Online

 Las características de licencia de archivado de **Exchange Online** ayudan a mantener el cumplimiento normativo y preservar el contenido de correo electrónico para eDiscovery. También ayuda a reducir el riesgo en el caso de un litigio y proporciona una forma de recuperar datos después de una infracción de seguridad o cuando se necesitan recuperar elementos eliminados. Puede usar la retención por juicio para conservar todo el contenido de un usuario o usar directivas de retención para personalizar lo que desea conservar.
  
**Retención por juicio:** Puede conservar todo el contenido del buzón, incluidos los elementos eliminados, al poner el buzón completo de un usuario en retención por juicio. 
    
Para poner un buzón de correo en retención por juicio, en el centro de administración:
    
1. En el panel de navegación izquierdo, **** \> vaya a usuarios **activos**.
    
2. Seleccione un usuario cuyo buzón quiera poner en retención por juicio y, en el panel usuario, expanda **configuración de correo** y, junto a **configuración adicional** , elija **Editar propiedades de Exchange**.
    
3. En la página buzón del usuario, elija * * características de buzón * * en el panel de navegación izquierdo y, a continuación, elija el vínculo **Habilitar** en **retención por juicio**.
    
4. En el cuadro de diálogo **retención por juicio** , puede especificar la duración de retención por juicio en el campo **duración** de retención por juicio, deje el campo vacío si desea realizar una suspensión infinita. También puede agregar notas y dirigir el propietario del buzón de correo a un sitio web que tenga que explicar más sobre la retención \> **** por juicio.
    
**Retención:** Puede habilitar las directivas de retención personalizadas, por ejemplo, para conservarlas durante un período de tiempo determinado o eliminar el contenido de forma permanente al final del período de retención. Para obtener más información, vea [información general sobre las directivas de retención](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).

## <a name="set-up-azure-information-protection-features"></a>Configurar las características de Azure Information Protection

Azure Information Protection (AIP) le ayuda a clasificar y, de manera opcional, proteger sus documentos y correos electrónicos mediante la aplicación de etiquetas. Las etiquetas pueden ser aplicadas automáticamente por los administradores que definen las reglas y condiciones, manualmente por los usuarios o mediante una combinación en la que los usuarios obtienen recomendaciones.

En Outlook en la web, puede aplicar las siguientes restricciones y etiquetas integradas a sus correos electrónicos:
  
- **** No reenviar: los destinatarios pueden leer el mensaje, pero no pueden reenviar, imprimir o copiar contenido
    
- **Encrypt**: todo el mensaje está cifrado. Los destinatarios deben confirmar su identidad antes de obtener acceso al contenido cifrado y no pueden quitar el cifrado.
    
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
