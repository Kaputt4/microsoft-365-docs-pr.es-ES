---
title: Crear una directiva DLP a partir de una plantilla
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-mar2020
- admindeeplinkCOMPLIANCE
description: En este artículo, obtendrá información sobre cómo crear directivas DLP mediante una de las plantillas incluidas en Office 365.
ms.openlocfilehash: 67d21d3e5a057960a4d3fa92bfaa709345cf38ff
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66624595"
---
# <a name="create-a-dlp-policy-from-a-template"></a>Crear una directiva DLP a partir de una plantilla

La manera más sencilla y común de empezar a trabajar con directivas DLP es usar una de las plantillas incluidas en el portal de cumplimiento Microsoft Purview. Puede usar una de estas plantillas tal como está o personalizar las reglas para cumplir los requisitos de cumplimiento específicos de su organización.

Microsoft 365 incluye más de 40 plantillas listas para usar que pueden ayudarle a satisfacer una amplia gama de necesidades comunes de directivas empresariales y normativas. Ver; [Plantillas de directiva](dlp-policy-reference.md#policy-templates) para una lista completa. 

Puede ajustar una plantilla modificando cualquiera de sus reglas existentes o agregando otras nuevas. Por ejemplo, puede agregar nuevos tipos de información confidencial a una regla, modificar los recuentos de una regla para que sea más difícil o más fácil de desencadenar, permitir que los usuarios invaliden las acciones de una regla proporcionando una justificación empresarial o cambiar a quién se envían las notificaciones y los informes de incidentes. Una plantilla de directiva DLP es un punto de partida flexible para muchos escenarios de cumplimiento comunes.

También puede elegir la plantilla Personalizada, que no tiene reglas predeterminadas, y configurar la directiva DLP desde cero para cumplir los requisitos de cumplimiento específicos de su organización.

## <a name="permissions"></a>Permisos

Los miembros de su equipo de cumplimiento que vayan a crear directivas DLP necesitan permisos para el centro de cumplimiento. De forma predeterminada, el administrador de inquilinos tendrá acceso para dar acceso a los responsables de cumplimiento y a otras personas. Siga estos pasos:
  
1. Crear un grupo en Microsoft 365 y agregarle responsables de cumplimiento.
    
2. Cree un grupo de roles en la página **Permisos** de la portal de cumplimiento Microsoft Purview. 

3. Al crear el grupo de roles, use la sección **Elegir roles** para agregar el siguiente rol al grupo de roles: **Administración de cumplimiento dlp**.
    
4. Use la sección **Elegir miembros** para añadir el grupo de Microsoft 365 que creó antes del grupo de roles.

Use el rol **View-Only DLP Compliance Management** para crear un grupo de roles con privilegios de solo vista para las directivas DLP y los informes DLP.

Para obtener más información vea [Permisos en el portal de cumplimiento de Microsoft Purview](microsoft-365-compliance-center-permissions.md).
  
Estos permisos son necesarios para crear y aplicar una directiva DLP que no aplique directivas.

### <a name="roles-and-role-groups-in-preview"></a>Roles y grupos de roles en la versión preliminar

Hay roles y grupos de roles en la versión preliminar que puede probar para ajustar los controles de acceso.

Esta es una lista de los roles aplicables. Para obtener más información sobre ellos, consulte [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md)

- Administrador de Information Protection
- Analista de Information Protection
- Investigador de protección de información
- Lector de protección de información

Esta es una lista de los grupos de roles aplicables. Para obtener más información sobre, consulte [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md)

- Protección de la información
- Administradores de Information Protection
- Analistas de Information Protection
- Investigadores de Information Protection
- Lectores de Information Protection

### <a name="create-the-dlp-policy-from-a-template"></a>Creación de la directiva DLP a partir de una plantilla

1. Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento Microsoft Purview</a>.

2. En el portal de cumplimiento Microsoft Purview \> navegación \> izquierdo **Soluciones Directivas** \> de prevención  \> \> de **pérdida de datos** **+ Crear directiva**.

3. Elija la plantilla de directiva DLP que protege los tipos de información confidencial que necesita \> **a continuación**.

4. Asigne a la directiva \> el nombre **Siguiente**.
 
<!--In this example, you'll select **Privacy** \> **U.S. Personally Identifiable Information (PII) Data** because it already includes most of the types of sensitive information that you want to protect - you'll add a couple later.

    When you select a template, you can read the description on the right to learn what types of sensitive information the template protects.

    ![Page for choosing a DLP policy template.](../media/775266f6-ad87-4080-8d7c-97f2e7403b30.png)-->

5. Para elegir las ubicaciones que desea que la directiva DLP proteja y acepte el ámbito predeterminado para cada ubicación o personalice el ámbito. Consulte [Ubicaciones](dlp-policy-reference.md#locations) para ver las opciones de ámbito.

6. Elija \> **Siguiente**.
 
1. Realiza una de las siguientes acciones:

   - Elija **Todas las ubicaciones de Office 365** \> **Siguiente**.
   - Elija **Permitirme elegir ubicaciones** \> específicas **Siguiente**. En este ejemplo, elija esta opción.

   Para incluir o excluir una ubicación completa, como todos los correos electrónicos de Exchange o todas las cuentas de OneDrive, active o desactive el **estado** de esa ubicación.

   Para incluir solo sitios de SharePoint específicos o cuentas de OneDrive para la Empresa, cambie el **estado** a activado y, a continuación, haga clic en los vínculos de **Incluir** para elegir sitios o cuentas específicos. Cuando se aplica una directiva a un sitio, las reglas configuradas en dicha directiva se aplican automáticamente a todos los subsitios de ese sitio.

   ![Opciones para las ubicaciones en las que se puede aplicar una directiva DLP.](../media/all-locations.png)

   En este ejemplo, para proteger la información confidencial almacenada en todas las cuentas de OneDrive para la Empresa, desactive el **estado** para el **correo electrónico de Exchange** y **los sitios de SharePoint** y deje el **estado** activado para **las cuentas de OneDrive**.

7. Elija **Revisar y personalizar la configuración predeterminada en la plantilla** \> **Siguiente**.

8. Una plantilla de directiva DLP contiene reglas predefinidas con condiciones y acciones que detectan y actúan sobre tipos específicos de información confidencial. Puede editar, eliminar o desactivar cualquiera de las reglas existentes o agregar otras nuevas. Cuando haya terminado, haga clic en **Siguiente**.

    ![Reglas expandidas en la plantilla de directiva de PII de EE. UU.](../media/3bc9f1b6-f8ad-4334-863a-24448bb87687.png)

9. Elija detectar cuándo se comparte este contenido dentro de su organización o fuera de la organización si ha seleccionado cualquiera de estas ubicaciones:
    1. Exchange
    1. SharePoint
    1. OneDrive
    1. Mensajes de chat y canal de Teams 

10. Elija **Siguiente**.

11. En la página **Acciones de protección** , si lo desea, puede personalizar las notificaciones de sugerencias de directiva y los correos electrónicos de notificación. Habilite **Cuando el contenido coincida con las condiciones de la directiva, muestre sugerencias de directiva a los usuarios y envíeles una notificación por correo electrónico** y, a continuación, elija **Personalizar la sugerencia y el correo electrónico**.
12. Elija **Siguiente**.


<!--    In this example, the U.S. PII Data template includes two predefined rules:

   - **Low volume of content detected U.S. PII** This rule looks for files containing between 1 and 10 occurrences of each of three types of sensitive information (ITIN, SSN, and U.S. passport numbers), where the files are shared with people outside the organization. If found, the rule sends an email notification to the primary site collection administrator, document owner, and person who last modified the document.

   - **High volume of content detected U.S. PII** This rule looks for files containing 10 or more occurrences of each of the same three sensitive information types, where the files are shared with people outside the organization. If found, this action also sends an email notification, plus it restricts access to the file. For content in a OneDrive for Business account, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document.

    To meet your organization's specific requirements, you may want to make the rules easier to trigger, so that a single occurrence of sensitive information is enough to block access for external users. After looking at these rules, you understand that you don't need low and high count rules—you need only a single rule that blocks access if any occurrence of sensitive information is found.

    So you expand the rule named **Low volume of content detected U.S. PII** \> **Delete rule**.

    ![Delete rule button.](../media/bc36f7d2-0fae-4af1-92e8-95ba51077b12.png)

9. Now, in this example, you need to add two sensitive information types (U.S. bank account numbers and U.S. driver's license numbers), allow people to override a rule, and change the count to any occurrence. You can do all of this by editing one rule, so select **High volume of content detected U.S. PII** \> **Edit rule**.

    ![Edit rule button.](../media/eaf54067-4945-4c98-8dd6-fb2c5d6de075.png)

10. To add a sensitive information type, in the **Conditions** section \> **Add or change types**. Then, under **Add or change types** \> choose **Add** \> select **U.S. Bank Account Number** and **U.S. Driver's License Number** \> **Add** \> **Done**.

    ![Option to Add or change types.](../media/c6c3ae86-f7db-40a8-a6e4-db11692024be.png)

    ![Add or change types pane.](../media/fdbb96af-b914-4a6c-a97b-bbd014689965.png)

11. To change the count (the number of instances of sensitive information required to trigger the rule), under **Instance count** \> choose the **min** value for each type \> enter 1. The minimum count cannot be empty. The maximum count can be empty; an empty **max** value convert to **any**.

    When finished, the min count for all of the sensitive information types should be **1** and the max count should be **any**. In other words, any occurrence of this type of sensitive information will satisfy this condition.

    ![Instance counts for sensitive information types.](../media/5c6e08cb-59a9-4558-b54b-d899836d4737.png)

12. For the final customization, you don't want your DLP policies to block people from doing their work when they have a valid business justification or encounter a false positive, so you want the user notification to include options to override the blocking action.

    In the **User notifications** section, you can see that email notifications and policy tips are turned on by default for this rule in the template.

    In the **User overrides** section, you can see that overrides for a business justification are turned on, but overrides to report false positives are not. Choose **Override the rule automatically if they report it as a false positive**.

    ![User notifications section and User overrides section.](../media/62720e7a-a939-4c03-b414-67748f3d64a0.png)

13. At the top of the rule editor, change the name of this rule from the default **High volume of content detected U.S. PII** to **Any content detected with U.S. PII** because it's now triggered by any occurrence of its sensitive information types.

14. At the bottom of the rule editor \> **Save**.

15. Review the conditions and actions for this rule \> **Next**.

    On the right, notice the **Status** switch for the rule. If you turn off an entire policy, all rules contained in the policy are also turned off. However, here you can turn off a specific rule without turning off the entire policy. This can be useful when you need to investigate a rule that is generating a large number of false positives.

16. On the next page, read and understand the following, and then choose whether to turn on the rule or test it out first \> **Next**.

     Before you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before you fully enforce them. For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require to get their work done.

    If you're creating DLP policies with a large potential impact, we recommend following this sequence:

17. Start in test mode without Policy Tips and then use the DLP reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization.

18. Move to Test mode with notifications and Policy Tips so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules.

19. Turn on the policies so that the rules are enforced and the content's protected. Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.

    ![Options for using test mode and turning on policy.](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

20. Review your settings for this policy \> choose **Create**.

After you create and turn on a DLP policy, it's deployed to any content sources that it includes, such as SharePoint Online sites or OneDrive for Business accounts, where the policy begins automatically enforcing its rules on that content.


## Example: Identify sensitive information across all OneDrive for Business sites and restrict access for people outside your organization

OneDrive for Business accounts make it easy for people across your organization to collaborate and share documents. But a common concern for compliance officers is that sensitive information stored in OneDrive for Business accounts may be inadvertently shared with people outside your organization. A DLP policy can help mitigate this risk.

In this example, you'll create a DLP policy that identifies U.S. PII data, which includes Individual Taxpayer Identification Numbers (ITIN), Social Security Numbers, and U.S. passport numbers. You'll get started by using a template, and then you'll modify the template to meet your organization's compliance requirements—specifically, you'll:

- Add a couple of types of sensitive information—U.S. bank account numbers and U.S. driver's license numbers—so that the DLP policy protects even more of your sensitive data.

- Make the policy more sensitive, so that a single occurrence of sensitive information is enough to restrict access for external users.

- Allow users to override the actions by providing a business justification or reporting a false positive. This way, your DLP policy won't prevent people in your organization from getting their work done, provided they have a valid business reason for sharing the sensitive information.


## View the status of a DLP policy

At any time, you can view the status of your DLP policies on the **Policy** page in the **Data loss prevention** section of the Microsoft Purview compliance portal. Here you can find important information, such as whether a policy was successfully enabled or disabled, or whether the policy is in test mode.

Here are the different statuses and what they mean.

<br>

****

|Status|Explanation|
|---|---|
|**Turning on...**|The policy is being deployed to the content sources that it includes. The policy is not yet enforced on all sources.|
|**Testing, with notifications**|The policy is in test mode. The actions in a rule are not applied, but policy matches are collected and can be viewed by using the DLP reports. Notifications about policy matches are sent to the specified recipients.|
|**Testing, without notifications**|The policy is in test mode. The actions in a rule are not applied, but policy matches are collected and can be viewed by using the DLP reports. Notifications about policy matches are not sent to the specified recipients.|
|**On**|The policy is active and enforced. The policy was successfully deployed to all its content sources.|
|**Turning off...**|The policy is being removed from the content sources that it includes. The policy may still be active and enforced on some sources. Turning off a policy may take up to 45 minutes.|
|**Off**|The policy is not active and not enforced. The settings for the policy (sources, keywords, duration, etc) are saved.|
|**Deleting...**|The policy is in the process of being deleted. The policy is not active and not enforced. It normally takes an hour for a policy to delete.|
|

## Turn off a DLP policy

You can edit or turn off a DLP policy at any time. Turning off a policy disables all of the rules in the policy.

To edit or turn off a DLP policy, on the **Policy** page \> select the policy \> **Edit policy**.

![Edit policy button.](../media/ce319e92-0519-44fe-9507-45a409eaefe4.png)

In addition, you can turn off each rule individually by editing the policy and then toggling off the **Status** of that rule, as described above.

## More information

- [Learn about data loss prevention](dlp-learn-about-dlp.md)
- [Send notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md)
- [Create a DLP policy to protect documents with FCI or other properties](protect-documents-that-have-fci-or-other-properties.md)
- [What the DLP policy templates include](what-the-dlp-policy-templates-include.md)
- [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)
