---
title: Migrar directivas de prevención de pérdida de datos de Exchange Online al Centro de cumplimiento
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Obtenga información sobre cómo planear y migrar las directivas de prevención Exchange de pérdida de datos en línea a Microsoft 365 DLP.
ms.openlocfilehash: 744ba3edbee1c6b84df9b8b5316c7df7e734cd6d
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2021
ms.locfileid: "61374069"
---
# <a name="migrate-exchange-online-data-loss-prevention-policies-to-compliance-center"></a>Migrar directivas de prevención de pérdida de datos de Exchange Online al Centro de cumplimiento

[Exchange Online directivas de prevención de pérdida de datos (DLP)](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) están en desuso. [La funcionalidad DLP mucho](dlp-learn-about-dlp.md)más enriquec Exchange Online DLP se ofrece en el centro de [Microsoft 365 cumplimiento.](https://compliance.microsoft.com/datalossprevention?viewid=policies) Puede usar el Asistente para la migración de directivas DLP para ayudarle a llevar las directivas de DLP de Exchange Online al Centro de cumplimiento donde las administrará.

El asistente para migración funciona leyendo la configuración de las directivas DLP en Exchange y, a continuación, creando directivas duplicadas en el Centro de cumplimiento. De forma predeterminada, el asistente crea  las nuevas versiones de las directivas en modo de prueba, para que pueda ver el impacto que tendrían en el entorno sin aplicar ninguna de las acciones. Una vez que esté listo para realizar la transición completa a las versiones del Centro de cumplimiento, **_debe_**:

1. Desactive o elimine la directiva de origen en el Centro Exchange administración (EAC).
1. Edite la versión del Centro de cumplimiento de la directiva y cambie su estado de **Test** a **Enforce**. 

> [!WARNING]
> Si no elimina o desactiva la directiva de origen en el EAC antes de establecer la versión del Centro de cumplimiento en **Aplicar** ambos conjuntos de directivas, intentará aplicar acciones y recibirá eventos duplicados. **_Esta es una configuración no compatible._**


El asistente para migración solo migra directivas EXO y reglas de flujo de correo asociadas. Las Exchange de flujo de correo no se migran.

## <a name="migration-workflow"></a>Flujo de trabajo de migración

Hay cuatro fases para migrar directivas DLP desde Exchange a la consola de administración de DLP unificada en el Centro de cumplimiento.  

1. Preparación para la migración
    1. Evalúe y compare las directivas dlp Exchange Online (EXO) y las directivas DLP del Centro de cumplimiento para la funcionalidad duplicada.
    1. Decide qué directivas DLP de EXO quieres traer exactamente como están, puedes usar el asistente para migrar estas directivas.
    1. Decida qué directivas DE DLP de EXO desea consolidarlas y consolidarlas en el Centro de administración de Exchange y, a continuación, use el Asistente para migración para traerlas al Centro de cumplimiento.
1. Realizar la migración: use el asistente
1. Pruebas y validación: examinar los resultados
1. Activar las directivas migradas

## <a name="before-you-begin"></a>Antes de empezar

### <a name="licensing-and-versions"></a>Licencias y versiones

Antes de empezar con la migración de directivas DLP, debe confirmar su [Microsoft 365 suscripción](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) y los complementos. 

Para tener acceso y usar el Asistente para migración de directivas, debe tener una de estas suscripciones o complementos

- Microsoft 365 E3
- Microsoft 365 E5
- Microsoft 365 A5 (EDU)
- Cumplimiento de Microsoft 365 E5
- Cumplimiento de Microsoft 365 A5
- Gobierno y protección de información de Microsoft 365 E5
- Gobierno y protección de información de Microsoft 365 A5

Para obtener una lista detallada de los requisitos de licencias dlp, consulte [Microsoft 365 Licensing guidance for security & compliance, data loss prevention](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)


### <a name="permissions"></a>Permisos

La cuenta que use para ejecutar el asistente para migración debe tener acceso a la página DLP de consola de administración de Exchange y a la consola DLP unificada del Centro de cumplimiento.

## <a name="prepare-for-migration"></a>Preparación para la migración

1. Si no está familiarizado con DLP, la consola DLP del Centro de cumplimiento o la consola DLP del Centro de administración de Exchange, debe familiarizarse antes de intentar una migración de directivas.
    1. [Exchange Online de prevención de pérdida de datos (DLP)](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
    1. [Obtenga más información sobre la prevención de pérdida de datos de Microsoft 365 de punto de conexión](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention)
    1. [Crear, probar y ajustar una directiva DLP](create-test-tune-dlp-policy.md)
1. Evalúe las directivas Exchange DLP y el Centro de cumplimiento haciendo estas preguntas:


|Pregunta  |Action  | Procedimiento de migración|
|---------|---------|---------|
|¿Sigue siendo necesaria la directiva?    |Si no es así, elimínelo o desactíelo |no migrar|
|¿Se superpone con otras directivas DLP Exchange centro de cumplimiento?     |Si es así, ¿puede consolidar las directivas superpuestas?         |- Si se superpone con otra directiva de Exchange, cree manualmente la directiva DLP consolidada en el Centro de administración de Exchange y, a continuación, use el asistente para migración. </br> - Si se superpone con una directiva existente del Centro de cumplimiento, puede modificar la directiva existente del Centro de cumplimiento para que coincida, no migrar la versión Exchange cumplimiento|
|¿La Exchange DLP está estrechamente definida y tiene condiciones, acciones, inclusiones y exclusiones bien definidas?     |Si es así, este es un buen candidato para migrar con el asistente, tome nota de la directiva para que recuerde volver a eliminarlo más adelante.         | migrar con el asistente|

## <a name="migration"></a>Migración

Después de evaluar todas las directivas dlp Exchange y del Centro de cumplimiento por necesidad y compatibilidad, puede usar el Asistente para la migración.

1. Abra la [consola DLP Microsoft 365 centro de cumplimiento.](https://compliance.microsoft.com/datalossprevention?viewid=policies)
2. Si hay directivas Exchange DLP que se pueden migrar, aparecerá un banner en la parte superior de la página que se lo informe.
3. Elija **Migrar directivas en** el banner para abrir el asistente para migración. Se enumeran todas las Exchange DLP. No se pueden seleccionar directivas migradas anteriormente.
4. Seleccione las directivas que desea migrar. Puede migrarlos individualmente o en grupos mediante un enfoque por fases o todos a la vez . Seleccione **Siguiente**.
5. Revise el panel desplegable para ver si hay advertencias o mensajes. Resuelva los problemas antes de continuar.
6. Seleccione el modo en el que desea que se cree la nueva directiva del Centro de cumplimiento, **Active**, **Test** o **Disabled**.  El valor predeterminado es **Test**. Seleccione **Siguiente**.
7. Si lo desea, puede crear directivas adicionales basadas en las Exchange DLP para otras ubicaciones dlp unificadas. Esto dará como resultado una nueva directiva DLP unificada para la directiva de Exchange migrada y una nueva directiva DLP unificada para las ubicaciones adicionales que elija aquí.

> [!IMPORTANT]
> Las Exchange y acciones de directiva DLP que no sean compatibles con otras ubicaciones DLP, como Dispositivos, SharePoint, OneDrive, Local, MCAS o mensajes de chat y canal de Teams se eliminarán de la directiva adicional. Además, hay trabajo previo que debe realizarse para las otras ubicaciones. Vea:
>- [Obtenga más información sobre la prevención de pérdida de datos de Microsoft 365 de punto de conexión](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention)
>- [Introducción a la prevención de pérdida de datos en punto de conexión](endpoint-dlp-getting-started.md#get-started-with-endpoint-data-loss-prevention)
>- [Uso de la prevención de pérdida de datos en punto de conexión](endpoint-dlp-using.md#using-endpoint-data-loss-prevention)
>- [Obtenga más información sobre el examinador de prevención de pérdida de datos locales de Microsoft 365](dlp-on-premises-scanner-learn.md#learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner)
>- [Introducción al examinador de prevención de pérdida de datos en el entorno local](dlp-on-premises-scanner-get-started.md#get-started-with-the-data-loss-prevention-on-premises-scanner)
>- [Usar el examinador de prevención de pérdida de datos locales de Microsoft 365](dlp-on-premises-scanner-use.md#use-the-microsoft-365-data-loss-prevention-on-premises-scanner)
>- [Usar directivas de prevención de pérdida de datos para aplicaciones en la nube que no son de Microsoft](dlp-use-policies-non-microsoft-cloud-apps.md#use-data-loss-prevention-policies-for-non-microsoft-cloud-apps)
 
8. Revise la configuración de la sesión del asistente para migración. Seleccione **Siguiente**.
9. Revise el informe de migración. Preste atención a cualquier error que implique Exchange de flujo de correo. Puede corregirlas y volver a migrar las directivas asociadas.

Las directivas migradas aparecerán ahora en la lista de directivas DLP en la consola DLP del Centro de cumplimiento. 

## <a name="common-errors-and-mitigation"></a>Errores y mitigación comunes
|Mensaje de error  |Reason  | Pasos recomendados/mitigación|
|---------|---------|---------|
|Ya existe una directiva de cumplimiento con `<Name of the policy>` nombre en escenarios `Dlp` .    |Es probable que esta migración de directiva se haya realizado antes y, a continuación, vuelva a tentarse en la misma sesión |Actualice la sesión para actualizar la lista de directivas disponibles para la migración. Todas las directivas migradas anteriormente deben estar en el `Already migrated` estado.|
|Ya existe una directiva de cumplimiento con `<Name of the policy>` nombre en escenarios `Hold` .     |Existe una directiva de retención con el mismo nombre en el mismo espacio empresarial.       |- Cambie el nombre de la directiva DLP en EAC a otro nombre. </br> - Reintentar la migración de la directiva afectada. |
|`DLP-group@contoso.com` no se puede usar como valor para la condición Shared By porque es un grupo de distribución o un grupo de seguridad habilitado para correo. Use Shared by Member of predicate para detectar actividades de miembros de determinados grupos.     |Las reglas de transporte permiten que los grupos se utilicen en la condición, pero DLP unificado `sender is` no lo permite.         | Actualice la regla de transporte para quitar todas las direcciones de correo electrónico de grupo de la condición y agregar el grupo `sender is` a la condición si es `sender is a member of` necesario. Reintentar la migración de la directiva afectada|
|No se pudo encontrar el destinatario `DLP-group@contoso.com` . Si se acaba de crear, vuelva a intentar la operación después de algún momento. Si se elimina o expira, restablezca con valores válidos e inténtelo de nuevo.     |Es probable que la dirección de grupo usada en `sender is a member of` o `recipient is a member of` condición haya expirado o no sea válida.         | - Quitar o reemplazar todas las direcciones de correo electrónico de grupo no válidas en la regla de transporte en Exchange centro de administración. </br> - Reintentar la migración de la directiva afectada.|
|El valor especificado en predicado debe ser el grupo de seguridad `FromMemberOf` habilitado para correo.     |Las reglas de transporte permiten que los usuarios individuales se utilicen en la condición, pero DLP unificado `sender is a member of` no lo permite.         | - Actualizar la regla de transporte para quitar todas las direcciones de correo electrónico de usuario individuales de la condición y agregar los `sender is a member of` usuarios a la condición si es `sender is` necesario. </br> - Reintentar la migración de la directiva afectada.|
|El valor especificado en predicado debe ser el grupo de seguridad `SentToMemberOf` habilitado para correo.    |Las reglas de transporte permiten que los usuarios individuales se utilicen con la condición, pero DLP unificada `recipient is a member of` no lo permite.         | - Actualizar la regla de transporte para quitar todas las direcciones de correo electrónico de usuario individuales de la condición y agregar los `recipient is a member of` usuarios a la condición si es `recipient is` necesario. </br> - Reintentar la migración de la directiva afectada.|
|El uso `<Name of condition>` del parámetro solo se admite Exchange. Quite este parámetro o active solo la Exchange ubicación.         | Es probable que exista otra directiva con el mismo nombre en el Centro de cumplimiento con otras ubicaciones como SPO/ODB/Teams para las que no se admite la condición mencionada. | Cambie el nombre de la directiva DLP Exchange centro de administración y vuelva a intentar la migración.|

## <a name="testing-and-validation---prateek-and-aakash-to-provide-a-list-of-supported-predicates-and-known-issues-before-publishing--"></a>Pruebas y validación <!--PRATEEK AND AAKASH TO PROVIDE A LIST OF SUPPORTED PREDICATES AND KNOWN ISSUES BEFORE PUBLISHING-->

Pruebe y revise las directivas.

1. Siga los [procedimientos de directiva](create-test-tune-dlp-policy.md#test-a-dlp-policy) Probar una DLP.
2. Revise los eventos creados por la directiva en [el Explorador de actividades](data-classification-activity-explorer.md).

## <a name="review-the-policy-matches-between-exchange-admin-center-dlp-and-microsoft-365-unified-dlp"></a>Revisar las coincidencias de directiva entre Exchange DLP del Centro de administración y Microsoft 365 DLP unificada

Para asegurarse de que las directivas migradas se comportan como se esperaba, puede exportar los informes de ambos centros de administración y hacer una comparación de las coincidencias de directiva.

1. Conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
2. Exporte el [informe DLP del EAC](/powershell/module/exchange/get-maildetaildlppolicyreport?view=exchange-ps). Puede copiar este cmdlet e insertar los valores adecuados:

```powershell
Get-MailDetailDlpPolicyReport -StartDate <dd/mm/yyyy -EndDate <dd/mm/yyyy> -PageSize 5000 | select Date, MessageId, DlpPolicy, TransportRule -Unique | Export-CSV <"C:\path\filename.csv"> 
```
3. Exporte [el informe DLP unificado](/powershell/module/exchange/get-dlpdetailreport?view=exchange-ps). Puede copiar este cmdlet e insertar los valores adecuados:

```powershell
Get-DlpDetailReport -StartDate <dd/mm/yyyy> -EndDate <dd/mm/yyyy> -PageSize 5000 | select Date, Location, DlpCompliancePolicy, DlpComplianceRule -Unique | Export-CSV <"C:\path\filename.csv">  
```

## <a name="activate-your-migrated-policies"></a>Activar las directivas migradas

Una vez que esté satisfecho con el funcionamiento de las directivas migradas, puede establecerlas en **Aplicar**.

1. Abra la Exchange DLP del Centro de administración.
2. Desactive o elimine la directiva de origen.
3. Abra la [Microsoft 365 DLP del Centro de](https://compliance.microsoft.com/datalossprevention?viewid=policies) cumplimiento y seleccione la directiva que desea activar para editarla.
4. Cambie el estado a **Activar**.

## <a name="related-articles"></a>Artículos relacionados

- [Exchange Online de prevención de pérdida de datos (DLP)](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [Introducción al explorador de actividad](data-classification-activity-explorer.md)
- [Crear, probar y ajustar una directiva DLP](create-test-tune-dlp-policy.md)
- [Crear una directiva DLP desde una plantilla](create-a-dlp-policy-from-a-template.md)
- [Exchange Online de prevención de pérdida de datos (DLP)](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
