---
title: Prácticas recomendadas para el uso compartido no autenticado
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
description: En este artículo, obtendrá información sobre los procedimientos recomendados para compartir archivos y carpetas con usuarios no autenticados.
ms.openlocfilehash: afbd2cf5e2e522228987941977fd53b8562aa9d7
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845377"
---
# <a name="best-practices-for-sharing-files-and-folders-with-unauthenticated-users"></a>Prácticas recomendadas para compartir archivos y carpetas con usuarios no autenticados.

El uso compartido no autenticado (los vínculos para *Cualquiera* ) puede ser práctico y útil en diversos escenarios. Los vínculos para *Cualquiera* son la manera más fácil de compartir: los usuarios pueden abrir el vínculo sin autenticación y tienen la libertad de compartirlo con otros usuarios.

Por lo general, no todo el contenido de una organización es adecuado para el uso compartido no autenticado. Este artículo describe las opciones disponibles para ayudarle a crear un entorno en el que los usuarios puedan compartir sin autenticarse archivos y carpetas, pero donde existan medidas de seguridad para ayudar a proteger el contenido de su organización.

> [!NOTE]
> Para que funcione el uso compartido sin autenticarse, debe habilitarlo para su organización y para el sitio individual o el equipo que lo utilizará. Consulte [Colaborar con personas fuera de su organización](collaborate-with-people-outside-your-organization.md) para ver el escenario que quiere habilitar.

## <a name="set-an-expiration-date-for-anyone-links"></a>Establezca una fecha de expiración de los vínculos para Cualquiera

A menudo, los archivos se almacenan en sitios, grupos y equipos durante largos períodos de tiempo. En ocasiones, hay directivas de retención de datos que requieren que se conserven archivos durante años. Si esos archivos se comparten con usuarios no autenticados, esto podría originar un acceso inesperado y cambios en los archivos en el futuro. Para mitigar esta posibilidad, puede configurar una fecha de expiración de los vínculos para *Cualquiera*.

Una vez que el vínculo para *Cualquiera* haya expirado, ya no podrá usarse para acceder al contenido.

Establezca una fecha de expiración para los vínculos para Cualquiera a través de la organización

1. Abra el [Centro de administración de SharePoint](https://admin.microsoft.com/sharepoint).
2. En el panel de navegación izquierdo, haga clic en **Uso compartido**.
3. En la **Elegir opciones de permisos y expiración para vínculos para Cualquiera** , seleccione la casilla **Los vínculos deben expirar dentro de este número de días**.</br>
   ![Captura de pantalla de la configuración de los vínculos para Cualquiera en el nivel de organización de SharePoint](../media/sharepoint-organization-anyone-link-expiration.png)
4. Escriba un número de días en el cuadro y después haga clic en **Guardar**.

Establezca una fecha de expiración para los vínculos para Cualquiera de un sitio concreto

1. Abra el [Centro de administración de SharePoint](https://admin.microsoft.com/sharepoint).
2. En el panel de navegación izquierdo, expanda **Sitios** y, después, haga clic en **Sitios activos**.
3. Seleccione el sitio web que quiera cambiar y haga clic en **Uso compartido**.
4. En **Configuración avanzada para los vínculos para Cualquiera** , en **Expiración de los vínculos para Cualquiera** , desactive la casilla **Igual que la configuración de nivel de organización**.</br>
   ![Recorte de pantalla de la configuración de la expiración de los vínculos para Cualquiera en el nivel del sitio de SharePoint](../media/sharepoint-organization-anyone-link-expiration-site.png)
5. Seleccione la opción **Los vínculos deben expirar dentro de este número de días** y escriba un número de días en el cuadro.
6. Haga clic en **Guardar**.

Tenga en cuenta que una vez que el vínculo para *Cualquiera* expire, el archivo o la carpeta se podrá volver a compartir con un nuevo vínculo para *Cualquiera*.

Puede establecer la caducidad del vínculo para *Cualquiera* para un OneDrive específico con [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite).

## <a name="set-link-permissions"></a>Establezca permisos de vínculos

De forma predeterminada, los vínculos para *Cualquiera* para un archivo permiten a los usuarios editar el archivo, mientras que los vínculos para *Cualquiera* para una carpeta permiten a los usuarios ver, editar los archivos, y cargar archivos nuevos en la carpeta. Puede cambiar estos permisos para los archivos y las carpetas independientemente de si está en modo solo vista.

Si desea permitir el uso compartido sin autenticarse, pero le preocupa que los usuarios sin autenticación modifiquen el contenido de su organización, considere la posibilidad de configurar los permisos de archivos y carpetas al modo **Vista**.

Establezca los permisos para los vínculos para Cualquiera a través de la organización

1. Abra el [Centro de administración de SharePoint](https://admin.microsoft.com/sharepoint).
2. En el panel de navegación izquierdo, haga clic en **Uso compartido**.
3. En **Configuración avanzada de vínculos para "Cualquiera"** , seleccione los permisos de los archivos y carpetas que quiera usar.</br>
   ![Captura de pantalla de la configuración de permisos de los vínculos para Cualquiera en el nivel de organización de SharePoint](../media/sharepoint-organization-anyone-link-permissions.png)

Con los vínculos para *Cualquiera* que se establecen en **Vista** , los usuarios pueden seguir compartiendo archivos y carpetas con los invitados y concederles permisos de edición mediante vínculos para *Personas específicas*. Estos vínculos requieren la autenticación de los usuarios externos a la organización. Puede realizar un seguimiento de la actividad de los invitados en los archivos y carpetas compartidos con dichos vínculos.

## <a name="set-default-link-type-to-only-work-for-people-in-your-organization"></a>Establezca el tipo de vínculo predeterminado para que solo funcione para las personas de su organización

Cuando *Cualquiera* está habilitado para su organización, el vínculo de uso compartido predeterminado está generalmente establecido para **Cualquiera**. Aunque esto puede resultar conveniente para los usuarios, puede aumentar el riesgo de un uso compartido involuntario sin autenticarse. Si un usuario olvida cambiar el tipo de vínculo mientras comparte un documento confidencial, podría crear accidentalmente un vínculo de uso compartido que no requiera autenticación.

Para mitigar este riesgo, puede cambiar la configuración de vínculo predeterminado a un vínculo que solo funcione para las personas de su organización. Los usuarios que quieran compartir con otros usuarios no autenticados tendrían que seleccionar esa opción específicamente.

Para establecer el vínculo de uso compartido de archivos y carpetas predeterminado para la organización
1. Abra el [Centro de administración de SharePoint](https://admin.microsoft.com/sharepoint).
2. En el panel de navegación izquierdo, haga clic en **Uso compartido**.
3. En **Vínculos de archivos y carpetas** , seleccione **Solo personas de la organización**.

   ![Recorte de pantalla de la configuración del tipo de vínculo predeterminado de SharePoint](../media/sharepoint-default-sharing-link-company-link.png)

4. Haga clic en **Guardar**

Para establecer el vínculo de uso compartido de archivos y carpetas predeterminado para un sitio web concreto
1. Abra el [Centro de administración de SharePoint](https://admin.microsoft.com/sharepoint).
2. En el panel de navegación izquierdo, expanda **Sitios** y, después, haga clic en **Sitios activos**.
3. Seleccione el sitio web que quiera cambiar y haga clic en **Uso compartido**.
4. En **Tipo de vínculo de uso compartido predeterminado** , desactive la casilla **Igual que la configuración de nivel de organización**.

   ![Recorte de pantalla de la configuración del tipo de vínculo predeterminado para el nivel del sitio de SharePoint](../media/sharepoint-organization-anyone-link-permissions-site.png)

5. Seleccione la opción **Solo personas de la organización** y haga clic en **Guardar**.

## <a name="prevent-unauthenticated-sharing-of-sensitive-content"></a>Impida el uso compartido no autenticado de contenido confidencial

Puede usar la [prevención de pérdida de datos (DLP)](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) para evitar el uso compartido no autenticado de contenido confidencial. La prevención de pérdida de datos puede actuar basándose en la etiqueta de confidencialidad, en la etiqueta de retención o en la información confidencial del archivo en sí.

Para crear una regla DLP
1. En el centro de administración del centro de cumplimiento de Microsoft 365, vaya a [Prevención de pérdida de datos](https://compliance.microsoft.com/datalossprevention).
2. Haga clic en **Crear directiva**.
3. Elija **Personalizado** y haga clic en **Siguiente**.
4. Escriba el nombre de la directiva y haga clic en **Siguiente**.
5. En la página **Ubicaciones en las que aplicar la directiva** desactive todas las páginas de configuración excepto **Sitios de SharePoint** y **Cuentas de OneDrive** y, a continuación, haga clic en **Siguiente**.
6. En la página **Definir configuración de directiva** , haga clic en **Siguiente**.
7. En la página **Personalizar las reglas DLP avanzadas** , haga clic en **Crear regla** y escriba un nombre para la regla.
8. En **Condiciones** , haga clic en **Agregar condición** y elija **El contenido incluye**.
9. Haga clic en **Agregar** y elija el tipo de información para el que desea evitar el uso compartido no autenticado.

   ![Recorte de pantalla de las opciones de condiciones, tipos de información confidencial, etiquetas de confidencialidad y etiquetas de retención.](../media/limit-accidental-exposure-dlp-conditions.png)

10. En **Acciones** haga clic en **Agregar una acción** y elija **Restringir el acceso o cifrar el contenido en la ubicaciones de Microsoft 365**.
11. Active la casilla **Restringir el acceso o cifrar el contenido de las ubicaciones de Microsoft 365** y, después, elija la opción **Solo personas a las que se les ha concedido el acceso al contenido mediante las opciones "Cualquiera con el vínculo"**.

      ![Recorte de pantalla de las opciones de acción de reglas DLP](../media/limit-accidental-exposure-dlp-anyone-links.png)

12. Haga clic en **Guardar** y, a continuación, en **Siguiente**.
13. Elija las opciones de prueba y haga clic en **Siguiente**.
14. Haga clic en **Enviar** y después en **Listo**.

## <a name="protect-against-malicious-files"></a>Protéjase contra archivos maliciosos

Cuando permite que los usuarios anónimos carguen archivos, aumenta el riesgo de que alguien cargue un archivo malintencionado. En Microsoft 365, puede usar la característica *Datos adjuntos seguros* en Microsoft Defender para Office 365, para analizar automáticamente los archivos cargados y los archivos en cuarentena que se encuentren como no seguros.

Para activar los datos adjuntos seguros
1. Abra la página [Datos adjuntos seguros ATP](https://protection.office.com/safeattachmentv2) en el Centro de seguridad y cumplimiento.
2. Haga clic en **Configuración global**.
3. Habilite ATP para SharePoint, OneDrive y Microsoft Teams.

   ![Recorte de pantalla de la opción datos adjuntos seguros en el Centro de seguridad y cumplimiento](../media/safe-attachments-setting.png)

4. De manera opcional, habilite también Documentos seguros y, a continuación, haga clic en **Guardar**

Consulte [ATP para SharePoint, OneDrive y Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) y [Activar ATP para SharePoint, OneDrive y Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams) para obtener más información.

## <a name="add-copyright-information-to-your-files"></a>Agregar información de copyright a los archivos

Si usa etiquetas de confidencialidad en el centro de administración de Cumplimiento de Microsoft 365, puede configurar las etiquetas para agregar automáticamente una marca de agua, un encabezado o un pie de página a los documentos de Office de su organización. De esta forma, puede asegurarse de que los archivos compartidos contengan derechos de autor u otra información de propiedad.

Para agregar un pie de página a un archivo con etiqueta

1. Abra el [Centro de administración de Cumplimiento de Microsoft 365](https://compliance.microsoft.com).
2. En el panel de navegación izquierdo, en **Soluciones** , haga clic en **Protección de la información**.
3. Haga clic en la etiqueta que desea que agregue un pie de página y, a continuación, haga clic en **Editar etiqueta**.
4. Haga clic en **Siguiente** para ampliar la pestaña **Marcado de contenido** y, a continuación, seleccione **Activar** el marcado de contenido.
5. Active la casilla de verificación del tipo de texto que desee añadir y después, haga clic en **Personalizar texto**.
6. Escriba el texto que quiere agregar a sus documentos, seleccione las opciones de texto que desee y después, haga clic en **Guardar**.</br>
   ![Captura de pantalla de la configuración de marcado de contenido para una etiqueta de sensibilidad](../media/content-marking-for-anonymous-sharing.png)
7. Haga clic en **Siguiente** para ir al final del asistente y, a continuación, en **Guardar etiqueta**.

Con el marcado de contenido habilitado para la etiqueta, el texto que haya especificado se agregará a los documentos de Office cuando un usuario aplique dicha etiqueta.

## <a name="see-also"></a>Vea también

[Información general de etiquetas de confidencialidad](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels)

[Reducir la exposición accidental de archivos al compartirlos con invitados](share-limit-accidental-exposure.md)

[Crear un entorno seguro de uso compartido para invitados](create-secure-guest-sharing-environment.md)
