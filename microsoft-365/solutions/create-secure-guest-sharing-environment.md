---
title: Crear un entorno seguro de uso compartido para invitados
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-security-compliance
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
description: En este artículo, aprenderá sobre las opciones disponibles para crear un entorno seguro para compartir invitados en Microsoft 365.
ms.openlocfilehash: 3ca7dba7c22f1eaa24f1285e42aa3f4caaf70b65
ms.sourcegitcommit: 21c3e44862854c74e4008cfb661840f069c6b709
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48787575"
---
# <a name="create-a-secure-guest-sharing-environment"></a>Crear un entorno seguro de uso compartido para invitados

En este artículo, analizaremos una amplia variedad de opciones para crear un entorno seguro de uso compartido para invitados en Microsoft 365. Se trata de ejemplos para dar una idea de las opciones disponibles. Puede usar estos procedimientos en distintas combinaciones para satisfacer las necesidades de seguridad y cumplimiento de su organización.

En este artículo se incluyen:

- Configurar autenticación multifactor para invitados
- Configurar condiciones de uso para invitados.
- Establecer revisiones trimestrales de acceso de invitados para validar periódicamente si los invitados continúan necesitando permisos en los equipos y en los sitios.
- Restringir el acceso de invitados a solo web para dispositivos no administrados.
- Configurar una directiva de tiempo de espera de la sesión para garantizar la autenticación de los invitados diariamente.
- Creación de un tipo de información confidencial para un proyecto altamente confidencial.
- Asignación automática de una etiqueta de confidencialidad a los documentos que contengan un tipo de información confidencial.
- Retirar automáticamente el acceso de invitado a los archivos con una etiqueta de confidencialidad.

Algunas de las opciones analizadas en este artículo requieren que los invitados tengan una cuenta de Azure Active Directory. Para asegurarse de que los invitados estén en el directorio cuando comparta archivos y carpetas con ellos, use la [Integración de SharePoint y OneDrive con la vista previa de Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview).

Tenga en cuenta que este artículo no describe cómo habilitar la configuración de uso compartido para invitados. Consulte [Colaborar con personas de fuera de su organización](collaborate-with-people-outside-your-organization.md) para obtener más información sobre cómo habilitar el uso compartido para invitados en diferentes situaciones.

## <a name="set-up-multi-factor-authentication-for-guests"></a>Configurar autenticación multifactor para invitados

La autenticación multifactor reduce considerablemente la probabilidad de que una cuenta sea atacada. Dado que los invitados pueden usar cuentas de correo personales que no cumplan con las directivas de la empresa o los procedimientos recomendados, es especialmente importante exigirles que usen una autenticación multifactor. Si se roba el nombre de usuario y la contraseña de un usuario invitado, tener un segundo factor de autenticación reduce considerablemente las posibilidades de que terceros obtengan acceso a sus sitios y archivos.

En este ejemplo, configuraremos la autenticación multifactor para invitados mediante el uso de una directiva de acceso condicional en Azure Active Directory.

Configurar autenticación multifactor para invitados

1. Vaya a [directivas de acceso condicional de Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).
2. En la hoja **Acceso condicional | Directivas** , seleccione **Nueva directiva** .
3. En el campo **Nombre** , escriba un nombre.
4. En **Asignaciones** , haga clic en **Usuarios y grupos** .
5. En la hoja **Usuarios y grupos** , seleccione **Seleccionar usuarios y grupos** , marque la casilla **Todos los invitados y usuarios externos** .
6. En **Tareas** , haga clic en **Aplicaciones o acciones en la nube** .
7. En la hoja **Aplicaciones o acciones en la nube** , seleccione **Todas las aplicaciones en la nube** en la pestaña **Incluir** .
8. En **Controles de acceso** , haga clic en **Conceder** .
9. En la hoja **Conceder** , marque la casilla **Requerir autenticación multifactor** y haga clic en **Seleccionar** .
10. En la hoja **Nuevo** , en **Habilitar directiva** , haga clic en **Activar** y, luego, haga clic **Crear** .

Ahora, el invitado deberá inscribirse en la autenticación multifactor para acceder al contenido compartido, a los sitios o a los equipos.

### <a name="more-information"></a>Más información

[Planificar una implementación de autenticación multifactor de Azure](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)

## <a name="set-up-a-terms-of-use-for-guests"></a>Configurar condiciones de uso para invitados

En determinadas situaciones, puede que los invitados no hayan firmado contratos de no divulgación ni otros acuerdos jurídicos con su organización. Puede obligar a los invitados a aceptar sus términos de uso antes de darles acceso a los archivos compartidos. Los términos de uso se les pueden mostrar la primera vez que intenten acceder a un archivo o sitio compartido.

Para crearlos, primero elabore el documento en Word u otro programa de creación y, luego, guárdelo como un archivo PDF. Este archivo se puede cargar en Azure AD.

¿Por qué crear términos de uso de Azure AD?

1. Inicie sesión en Azure como administrador global, administrador de seguridad o administrador de acceso condicional.
2. Vaya a [Términos de uso](https://aka.ms/catou).
3. Haga clic en **Nuevos términos** .

   ![Captura de pantalla de la configuración de nuevos términos de uso de Azure AD](../media/azure-ad-guest-terms-of-use.png)

4. Escriba un **Nombre** y **Nombre para mostrar** .
6. En **Documento de términos de uso** explore hasta encontrar el archivo PDF que creó y selecciónelo.
7. Seleccione el idioma para su documento de términos de uso.
8. En **Requerir a los usuarios que expandan los términos de uso** , seleccione **Activado** .
9. En **Acceso condicional** , de la lista **Exigir con plantillas de directiva de acceso condicional** elija **Crear directiva de acceso condicional más adelante** .
10. Haga clic en **Crear** .

Una vez haya creado los términos de uso, el siguiente paso es crear una directiva de acceso condicional que muestre los términos a los invitados.

Para crear una nueva directiva de acceso condicional, haga lo siguiente:

1. Vaya a [directivas de acceso condicional de Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).
2. En la hoja **Acceso condicional | Directivas** , seleccione **Nueva directiva** .
3. En el cuadro **Nombre** , escriba un nombre.
4. En **Asignaciones** , haga clic en **Usuarios y grupos** .
5. En la hoja **Usuarios y grupos** , seleccione **Seleccionar usuarios y grupos** , marque la casilla **Todos los invitados y usuarios externos** .
6. En **Tareas** , haga clic en **Aplicaciones o acciones en la nube** .
7. En la pestaña **Incluir** , elija **Seleccionar aplicaciones** y, a continuación, haga clic en **Seleccionar** .
8. En la hoja **Seleccionar** , elija **Microsoft Teams** , **Office 365 SharePoint Online** y **Grupos de Outlook** y, a continuación, haga clic en **Seleccionar** .
9. En **Controles de acceso** , haga clic en **Conceder** .
10. En la hoja **Conceder** , seleccione **Términos de uso de invitado** y, a continuación, haga clic en **Seleccionar** .
11. En la hoja **Nuevo** , en **Habilitar directiva** , haga clic en **Activar** y, luego, haga clic **Crear** .

A partir de ahora, cuando un usuario invitado acceda por primera vez al contenido, a un grupo o a un sitio de su organización, se le pedirá que acepte los términos de uso.

> [!NOTE]
> El uso del acceso condicional requiere una licencia de Azure AD Premium P1. Para más información, consulte [Qué es el acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

### <a name="more-information"></a>Más información

[Términos de uso de Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)

## <a name="set-up-guest-access-reviews"></a>Configurar revisiones de acceso de invitados

Con las revisiones de acceso en Azure AD, puede realizar automáticamente revisiones periódicas del acceso de usuarios a diversos equipos y grupos. Al requerir una revisión de acceso específicamente para invitados, se asegura de que los invitados no tengan acceso a información confidencial de su organización durante más tiempo del necesario.

Las revisiones de acceso se pueden organizar en distintos programas. Un programa es una agrupación de revisiones de acceso similares. Sirve para organizar las revisiones de acceso para propósitos como la creación de informes o auditorías.

Para crear un programa:

1. Inicie sesión en Azure Portal y abra la página [Identity Governance](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade).
2. En el menú de la izquierda, haga clic en **Programas** .
3. Haga clic en **Nuevo programa** .
4. Escriba un **Nombre** y una **Descripción** .
5. Haga clic en **Crear** .

Una vez que haya creado el programa, puede crear una revisión de acceso de invitados y asociarla a él.

Crear una revisión de acceso de invitados

1. En la página [Identity Governance](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade), en el menú de la izquierda, haga clic en **Revisiones de acceso** .
2. Haga clic en **Nueva revisión de acceso** .

   ![Captura de pantalla de la configuración de revisión de acceso en Azure AD](../media/azure-ad-create-access-review.png)

3. En el cuadro **Nombre** , escriba un nombre.
4. En **Frecuencia** , elija **Trimestral** .
5. En **Finalización** , elija **Nunca** .
6. En **Ámbito** , elija **Solo usuarios invitados** .
7. Haga clic en **Agrupar** , seleccione los grupos que desea incluir en la revisión de acceso y, a continuación, haga clic en **Seleccionar** .
8. En **Programas** , haga clic en **Vincular al programa** .
9. En la hoja **Seleccionar un programa** , elija **Programa de revisión de acceso para invitados**
10. Haga clic en **Iniciar** .

Se creará una revisión de acceso independiente para cada grupo que especifique. Los propietarios de cada grupo recibirán un correo cada trimestre para aprobar o denegar el acceso de los invitados a sus grupos.

Hay que tener en cuenta que los invitados pueden recibir acceso tanto a equipos o grupos, como a archivos y carpetas individuales. Cuando se da acceso a archivos y carpetas, es posible que los invitados no se agreguen a un grupo específico. Si desea realizar revisiones de acceso para invitados que no pertenezcan a un equipo o grupo, puede crear un grupo dinámico en Azure AD que contenga todos los invitados y, a continuación, crear una revisión de acceso para ese grupo. Los propietarios del sitio también pueden administrar una [expiración para invitados del sitio](https://support.microsoft.com/office/25bee24f-42ad-4ee8-8402-4186eed74dea)

### <a name="more-information"></a>Más información

[Administre el acceso de los invitados con las revisiones de acceso de Azure AD](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)

[Cree una revisión de acceso de grupos o aplicaciones con las revisiones de acceso de Azure AD](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)

## <a name="set-up-web-only-access-for-guest-users"></a>Establezca que los usuarios invitados solo puedan acceder a través de la web

Puede limitar sus zonas vulnerables a un ataque y facilitar las tareas de administración si obliga a los invitados a que accedan a sus equipos, sitios y archivos a través de un navegador web.

Para Grupos de Microsoft 365 y Teams, esto se realiza mediante una directiva de acceso condicional de Azure AD. En el caso de SharePoint, se configura en el Centro de administración de SharePoint. (También puede [usar etiquetas de confidencialidad para restringir el acceso de invitados a solo web](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites))

Cómo restringir el acceso de los invitados a solo web para grupos y equipos

1. Vaya a [directivas de acceso condicional de Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).
2. En la hoja **Acceso condicional - Directivas** , seleccione **Nueva directiva** .
3. En el cuadro **Nombre** , escriba un nombre.
4. En **Asignaciones** , haga clic en **Usuarios y grupos** .
5. En la hoja **Usuarios y grupos** , seleccione **Seleccionar usuarios y grupos** , marque la casilla **Todos los invitados y usuarios externos** .
6. En **Tareas** , haga clic en **Aplicaciones o acciones en la nube** .
7. En la pestaña **Incluir** , elija **Seleccionar aplicaciones** y, a continuación, haga clic en **Seleccionar** .
8. En la hoja **Seleccionar** , elija **Microsoft Teams** y **Outlook Groups** y, a continuación, haga clic en **Seleccionar** .
9. En **Tareas** , haga clic en **Condiciones** .
10. En la hoja **Condiciones** , haga clic en **Aplicaciones cliente** .
11. En la hoja **Aplicaciones cliente** , haga clic en **Sí** para **Configurar** , y seleccione la configuración de **Clientes de aplicaciones móviles y de escritorio** , **Clientes de Exchange ActiveSync** y de **Otros clientes** . Desactive la casilla **Explorador** .

    ![Captura de pantalla de la configuración de acceso condicional para aplicaciones cliente en Azure AD](../media/azure-ad-conditional-access-client-mobile.png)

12. Haga clic en **Listo** .
13. En **Controles de acceso** , haga clic en **Conceder** .
14. En la hoja **Conceder** , seleccione **Requerir que el dispositivo esté marcado como compatible** y **Requerir un dispositivo unido de Hybrid Azure AD** .
15. En **Para varios controles** , seleccione **Requerir uno de los controles seleccionados** y, a continuación haga clic en **Seleccionar** .
16. En la hoja **Nuevo** , en **Habilitar directiva** , haga clic en **Activar** y, luego, haga clic **Crear** .

Cómo restringir el acceso de los invitados a solo web para SharePoint

1. En el [Centro de administración de SharePoint](https://admin.microsoft.com/sharepoint), expanda **Directivas** y haga clic en **Control de acceso** .
2. Haga clic en **Dispositivos no administrados** .
3. Seleccione la opción **Permitir el acceso limitado a solo web** y, a continuación, haga clic en **Guardar** .

Tenga en cuenta que esta configuración del Centro de administración de SharePoint crea una directiva de apoyo de acceso condicional en Azure AD.

## <a name="configure-a-session-timeout-for-guest-users"></a>Configurar un tiempo de espera de sesión para los usuarios invitados

Requerir que los invitados se autentiquen periódicamente puede reducir la posibilidad de que usuarios desconocidos accedan al contenido de la organización si el usuario invitado no protege su dispositivo correctamente. Azure AD le permite configurar una directiva de acceso condicional de tiempo de espera de sesión para usuarios invitados.

Cómo configurar una directiva de tiempo de espera de sesión para invitado

1. Vaya a [directivas de acceso condicional de Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).
2. En la hoja **Acceso condicional - Directivas** , seleccione **Nueva directiva** .
3. En el cuadro **Nombre** , escriba *Tiempo de espera de sesión para invitado* .
4. En **Asignaciones** , haga clic en **Usuarios y grupos** .
5. En la hoja **Usuarios y grupos** , seleccione **Seleccionar usuarios y grupos** , marque la casilla **Todos los invitados y usuarios externos** .
6. En **Tareas** , haga clic en **Aplicaciones o acciones en la nube** .
7. En la pestaña **Incluir** , elija **Seleccionar aplicaciones** y, a continuación, haga clic en **Seleccionar** .
8. En la hoja **Seleccionar** , elija **Microsoft Teams** , **Office 365 SharePoint Online** y **Grupos de Outlook** y, a continuación, haga clic en **Seleccionar** .
9. En **Controles de acceso** , haga clic en **Sesión** .
10. En la hoja **Sesión** , seleccione **Frecuencia de inicio de sesión** .
11. Seleccione **1** y **días** para el período de tiempo y, a continuación, haga clic en **Seleccionar** .
12. En la hoja **Nuevo** , en **Habilitar directiva** , haga clic en **Activar** y, luego, haga clic **Crear** .

## <a name="create-a-sensitive-information-type-for-a-highly-sensitive-project"></a>Crear un tipo de información confidencial para un proyecto altamente confidencial.

Los tipos de información confidencial son cadenas predefinidas que se pueden usar en flujos de trabajo de directiva para aplicar requisitos de cumplimiento. El Centro de cumplimiento de Microsoft 365 incluye más de 100 tipos de información confidencial, como números de licencia de conducir, números de tarjeta de crédito, números de cuentas bancarias, etc.

Puede crear tipos de información confidencial personalizados para ayudar a administrar el contenido específico de su organización. En este ejemplo, vamos a crear un tipo de información confidencial personalizado para un proyecto altamente confidencial. Podemos usar este tipo de información confidencial para aplicar automáticamente una etiqueta de confidencialidad.

Cómo crear un tipo de información confidencial

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), en el panel de navegación izquierdo, expanda **Clasificación** y, a continuación, haga clic en **Tipos de información confidencialidad** .
2. Haga clic en **Crear** .
3. En **Nombre** y **Descripción** , escriba **Proyecto Saturno** y haga clic en **Siguiente** .
4. Haga clic en **Agregar un elemento** .
5. En la lista **Detectar contenido que contenga** , seleccione **Palabras clave** y, a continuación, escriba *Proyecto Saturno* en el cuadro de palabras clave.
6. Haga clic en **Siguiente** y después en **Finalizar** .
7. Si se le solicita si quiere probar el tipo de información confidencial, haga clic en **No** .

### <a name="more-information"></a>Más información

[Tipos de información confidencial personalizados](https://docs.microsoft.com/Office365/SecurityCompliance/custom-sensitive-info-types)

## <a name="create-an-auto-labeling-policy-to-assign-a-sensitivity-label-based-on-a-sensitive-information-type"></a>Crear una directiva de etiquetado automático para asignar una etiqueta de confidencialidad basada en un tipo de información confidencial

Si utiliza etiquetas de confidencialidad en la organización, puede aplicar automáticamente una etiqueta a los archivos que contengan tipos definidos de información confidencial. 

Crear una directiva de etiquetado automático

1. Abra el [Centro de administración de Cumplimiento de Microsoft 365](https://compliance.microsoft.com).
2. En el panel de navegación izquierdo, haga clic en **Protección de la información** .
3. En la pestaña **Etiquetado automático** , haga clic en **Crear una directiva de etiquetado automático** .
4. En la página **Elegir la información a la que desea aplicar esta etiqueta** , elija **Personalizado** y haga clic en **Siguiente** .
5. Escriba un nombre y una descripción para la directiva y haga clic en **Siguiente** .
6. En la página **Elegir las ubicaciones a las que desea aplicar la etiqueta** , active **Sitios de SharePoint** y haga clic en **Elegir sitios** .
7. Agregue las direcciones URL de los sitios en los que quiera activar el etiquetado automático y haga clic en **Listo** .
8. Haga clic en **Siguiente** .
9. En la página **Configurar reglas comunes o avanzadas** , elija **Reglas comunes** y haga clic en **Siguiente** .
10. En la página **Definir reglas para el contenido en todas las ubicaciones** , haga clic en **Nueva regla** .
11. En la página **Nueva regla** , asigne un nombre a la regla, haga clic en **Agregar condición** y, a continuación, haga clic en **El contenido contiene tipos de información confidencial** .
12. Haga clic en **Agregar** y en **Tipos de información confidencial** , seleccione los tipos de información confidencial que desee usar, haga clic en **Agregar** y, a continuación, en **Guardar** .
13. Haga clic en **Siguiente** .
14. Haga clic en **Elegir una etiqueta** , seleccione la etiqueta que desee utilizar y, a continuación, haga clic en **Agregar** .
15. Haga clic en **Siguiente** .
16. Deje la directiva en modo de simulación y haga clic en **Siguiente** .
17. Haga clic en **Crear directiva** y, a continuación, en **Listo** .

Con la directiva en vigor, cuando un usuario escriba "Proyecto Saturno" en un documento, la directiva de etiquetado automático aplicará automáticamente la etiqueta especificada al analizar el archivo.

### <a name="more-information"></a>Más información

[Aplicar una etiqueta de confidencialidad automáticamente al contenido](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

## <a name="create-a-dlp-policy-to-remove-guest-access-to-highly-sensitive-files"></a>Crear una directiva DLP para retirar el acceso de un invitado a archivos altamente confidenciales

Puede usar la [prevención de pérdida de datos (DLP)](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) para evitar que los invitados realicen un uso compartido no deseado de contenido confidencial. La prevención de pérdida de datos puede actuar en función de la etiqueta de confidencialidad de un archivo y eliminar el acceso de invitado.

Crear una regla DLP

1. En el centro de administración del centro de cumplimiento de Microsoft 365, vaya a [Prevención de pérdida de datos](https://compliance.microsoft.com/datalossprevention).
2. Haga clic en **Crear directiva** .
3. Elija **Personalizado** y haga clic en **Siguiente** .
4. Escriba el nombre de la directiva y haga clic en **Siguiente** .
5. En la página **Ubicaciones en las que aplicar la directiva** desactive todas las páginas de configuración excepto **Sitios de SharePoint** y **Cuentas de OneDrive** y, a continuación, haga clic en **Siguiente** .
6. En la página **Definir configuración de directiva** , haga clic en **Siguiente** .
7. En la página **Personalizar las reglas DLP avanzadas** , haga clic en **Crear regla** y escriba un nombre para la regla.
8. En **Condiciones** , haga clic en **Agregar condición** y elija **El contenido incluye** .
9. Haga clic en **Agregar** , seleccione **Etiquetas de confidencialidad** , elija las etiquetas que desee usar y haga clic en **Agregar** .

   ![Recorte de pantalla de las opciones de condiciones, tipos de información confidencial, etiquetas de confidencialidad y etiquetas de retención.](../media/limit-accidental-exposure-dlp-conditions.png)

10. En **Acciones** haga clic en **Agregar una acción** y elija **Restringir el acceso o cifrar el contenido en la ubicaciones de Microsoft 365** .
11. Active la casilla **Restringir el acceso o cifrar el contenido en las ubicaciones de Microsoft 365** y, después, elija la opción **Solo los usuarios de fuera de la organización** .

      ![Recorte de pantalla de las opciones de acción de reglas DLP](../media/dlp-remove-guest-access-sensitive-files.png)

12. Haga clic en **Guardar** y, a continuación, en **Siguiente** .
13. Elija las opciones de prueba y haga clic en **Siguiente** .
14. Haga clic en **Enviar** y después en **Listo** .

Es importante tener en cuenta que esta directiva no retira el acceso si el invitado es miembro del sitio o del equipo en general. Si prevé disponer de documentos altamente confidenciales en un sitio o equipo con miembros invitados, considere usar [Canales privados en Teams](https://support.microsoft.com/office/de3e20b0-7494-439c-b7e5-75899ebe6a0e) y solo permitir que los miembros de su organización los usen.

## <a name="additional-options"></a>Opciones adicionales

Hay algunas opciones adicionales de Microsoft 365 y Azure Active Directory que pueden ayudar a proteger el entorno de uso compartido de invitados.

- Puede crear una lista de dominios permitidos o prohibidos para limitar los dominios con los que los usuarios podrán compartir. Consulte [restringir el uso compartido de contenido de SharePoint y OneDrive por dominio](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) y [permitir o bloquear las invitaciones a los usuarios B2B de organizaciones específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list) para obtener más información.
- Puede limitar el resto de los espacios empresariales de Azure Active Directory a los que se pueden conectar los usuarios. Consulte [Usar restricciones de espacio empresarial para administrar el acceso a aplicaciones en la nube de SaaS](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions) para obtener más información.
- Puede crear un entorno administrado donde los asociados pueden ayudar a administrar cuentas de invitado. Para obtener más información, consulte [crear una extranet de B2B con invitados administrados](https://docs.microsoft.com/Office365/Enterprise/b2b-extranet).

## <a name="see-also"></a>Consulta también

[Reducir la exposición accidental de archivos al compartirlos con invitados](share-limit-accidental-exposure.md)

[Prácticas recomendadas para compartir archivos y carpetas con usuarios no autenticados](best-practices-anonymous-sharing.md)

Para obtener más información, consulte [Crear una extranet de B2B con invitados administrados](b2b-extranet.md).
