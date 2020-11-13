---
title: Limitar la exposición accidental
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
- m365initiative-externalcollab
ms.custom: ''
localization_priority: Priority
f1.keywords: NOCSH
description: Obtenga información sobre cómo limitar la exposición accidental de información al compartir archivos con usuarios externos a la organización.
ms.openlocfilehash: 430c00d46fa3801d0869b05a651fadd3bf5dea28
ms.sourcegitcommit: 8a726ed7ec19a8728c079780fa4d343a5f759fbb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49029974"
---
# <a name="limit-accidental-exposure-to-files-when-sharing-with-people-outside-your-organization"></a>Limitar la exposición accidental de archivos al compartirlos con usuarios externos a la organización

Al compartir archivos y carpetas con usuarios externos a la organización, hay una amplia variedad de opciones para reducir las posibilidades de compartir por error información confidencial. Puede elegir entre las opciones de este artículo para satisfacer las necesidades de su organización.

## <a name="use-best-practices-for-anyone-links"></a>Usar los procedimientos recomendados para los vínculos de tipo "Cualquiera"

Si los usuarios de su organización necesitan llevar a cabo un uso compartido sin autenticar, pero le preocupa que los usuarios sin autenticar modifiquen el contenido, lea los [Procedimientos recomendados para el uso compartido sin autenticar](best-practices-anonymous-sharing.md) para obtener instrucciones sobre cómo trabajar con el uso compartido sin autenticar en su organización.

## <a name="turn-off-anyone-links"></a>Desactivar vínculos de tipo Cualquiera

Se recomienda dejar habilitados los vínculos de tipo *Cualquiera* para el contenido adecuado, ya que es la manera más sencilla de compartir y puede ayudar a reducir el riesgo de que los usuarios soliciten otras soluciones que no están controladas por el departamento de TI. Los vínculos de tipo *Cualquiera* se pueden reenviar a otros usuarios, pero el acceso al archivo solo está disponible para los usuarios que tengan el vínculo.

Si quiere que los usuarios externos a la organización siempre tengan que autenticarse al obtener acceso al contenido de SharePoint, Grupos o Teams, puede desactivar el uso compartido de tipo *Cualquiera*. Esto impedirá que los usuarios compartan el contenido sin autenticar.

Si deshabilita los vínculos de tipo *Cualquiera* , los usuarios podrán seguir compartiendo con los invitados mediante los vínculos de *Personas específicas*. En este caso, todos los usuarios externos a la organización tendrán que autenticarse antes de poder tener acceso al contenido compartido.

En función de sus necesidades, puede deshabilitar los vínculos de tipo *Cualquiera* para sitios específicos o para toda la organización.

Para desactivar los vínculos de tipo *Cualquiera* de su organización, haga lo siguiente: 
1. En el Centro de administración de SharePoint, en el panel de navegación izquierdo, haga clic en **Uso compartido**.
2. Establezca la configuración de uso compartido externo de SharePoint como **Invitados nuevos y existentes**.

   ![Captura de pantalla de la configuración de uso compartido externo del sitio de SharePoint a nivel de organización](../media/sharepoint-organization-external-sharing-controls-new-users.png)

3. Haga clic en **Guardar**.

Desactivar los vínculos de tipo *Cualquiera*
1. En el Centro de administración de SharePoint, en el panel de navegación izquierdo, expanda **Sitios** y haga clic en **Sitios activos**.
2. Seleccione el sitio que quiere configurar.
3. En la cinta de opciones, haga clic en **Uso compartido**.
4. Asegúrese de que el uso compartido está establecido como **Invitados nuevos y existentes**.

   ![Captura de pantalla de la configuración de uso compartido externo del sitio de SharePoint a nivel de sitio](../media/sharepoint-site-external-sharing-settings.png)

5. Si ha realizado cambios, haga clic en **Guardar**.

## <a name="domain-filtering"></a>Filtrado de dominios

Puede usar las listas de dominios permitidos o rechazados para especificar qué dominios pueden utilizar sus usuarios al compartir con personas ajenas a su organización.

Con una lista de dominios permitidos, puede especificar una lista de dominios en los que los usuarios de su organización pueden compartir con usuarios externos a la organización. El uso compartido con otros dominios está bloqueado. Si su organización solo colabora con usuarios de una lista de dominios específicos, puede usar esta característica para evitar el uso compartido con otros dominios.

Con una lista de dominios rechazados, puede especificar una lista de dominios desde los que los usuarios de su organización no pueden compartir contenido con usuarios externos a la organización. El uso compartido con dominios en la lista está bloqueado. Esto puede resultar útil si tiene competidores que, por ejemplo, no quiere que tengan acceso al contenido de su organización.

Las listas de permitidos y rechazados solo afectan al uso compartido con invitados. Los usuarios aún podrán compartir con personas de dominios prohibidos mediante el uso de vínculos de tipo *Cualquiera* si no los ha deshabilitado. Para obtener los mejores resultados con las listas de dominios permitidos y de denegación, considere la posibilidad de deshabilitar los vínculos de tipo *Cualquiera* como se ha descrito anteriormente.

Para configurar una lista de dominios permitidos o denegados
1. En el centro de administración de SharePoint, en el panel de navegación izquierdo, haga clic en **Uso compartido**.
2. En **Configuración avanzada para uso compartido externo** , active la casilla **Limitar uso compartido externo por dominio**.
3. Haga clic en **Agregar dominios**.
4. Seleccione si quiere bloquear dominios, escriba los dominios y haga clic en **Aceptar**.

   ![Captura de pantalla de la configuración de SharePoint para limitar el uso compartido externo por dominio](../media/sharepoint-sharing-block-domain.png)

5. Haga clic en **Guardar**.

Si quiere limitar el uso compartido de dominios en un nivel más alto que SharePoint y OneDrive, puede [permitir o bloquear las invitaciones a los usuarios B2B desde organizaciones específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list) de Azure Active Directory. (Debe configurar la [integración de SharePoint y OneDrive con la versión preliminar de B2B de Azure AD](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) para que estas opciones de configuración afecten a SharePoint y OneDrive).

## <a name="limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups"></a>Limitar el uso compartido de archivos, carpetas y sitios con usuarios externos a la organización a grupos de seguridad específicos

Puede restringir el uso compartido de archivos, carpetas y sitios con usuarios externos a la organización a los miembros de un grupo de seguridad específico. Esto es útil si quiere habilitar el uso compartido externo, pero con un flujo de trabajo de aprobación o un proceso de solicitud. Como alternativa, puede requerir que sus usuarios completen un curso de capacitación antes de que se agreguen al grupo de seguridad y se les permita compartir con el exterior.

Para limitar el uso compartido externo a los miembros de un grupo de seguridad
1. En el [Centro de administración de SharePoint](https://admin.microsoft.com/sharepoint), en el panel de navegación izquierdo, en **Directivas** , haga clic en **Uso compartido**.
2. En **Uso compartido externo** , expanda **Más configuraciones de uso compartido externo**.

3. Seleccione **Permitir que solo los usuarios de grupos de seguridad específicos compartan externamente** y luego seleccione **Administrar grupos de seguridad**.

    ![Captura de pantalla del panel Administrar grupos de seguridad](https://docs.microsoft.com/sharepoint/sharepointonline/media/manage-security-groups.png)

4. En el cuadro **Agregar un grupo de seguridad** , escriba un nombre para el grupo de seguridad. Se mostrará el cuadro de grupo de seguridad.

5. Junto al nombre del grupo de seguridad, en el menú **Puede compartir con** , seleccione:

    - **Solo invitados autenticados** (predeterminado)
    - **Cualquiera**

6. Seleccione **Guardar**.

Tenga en cuenta que esto afecta a archivos, carpetas y sitios, pero no a los grupos de Microsoft 365 o Teams. Cuando los miembros inviten a invitados a un grupo privado de Microsoft 365 o Microsoft Teams, la invitación se enviará al propietario del grupo o equipo para que la apruebe.

## <a name="see-also"></a>Consulta también

[Crear un entorno seguro de uso compartido para invitados](create-secure-guest-sharing-environment.md)

[Procedimientos recomendados para compartir archivos y carpetas con usuarios anónimos](best-practices-anonymous-sharing.md)
