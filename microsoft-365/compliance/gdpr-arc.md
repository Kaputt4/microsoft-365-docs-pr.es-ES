---
title: Listas de comprobación de preparación de responsabilidad para RGPD
description: En este artículo, aprenderá acerca de las listas de control de preparación para la rendición de cuentas para acceder a la información de apoyo a la GDPR cuando se utilizan productos y servicios de Microsoft.
keywords: Microsoft 365, Microsoft 365 Educación, documentación de Microsoft 365, RGPD
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 6952545060a524ef92af6e1e7a063da7091b0860
ms.sourcegitcommit: 4ee683c18442386f6fc5c76ffabfad2c28b81d42
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48214815"
---
# <a name="support-your-gdpr-program-with-accountability-readiness-checklists"></a>Apoye a su programa de RGPD con las listas de comprobación de preparación de responsabilidad

El RGPD añade nuevas normas organizaciones que ofrecen bienes y servicios a los ciudadanos de la Unión Europea (UE), o que recopilen y analicen datos de los residentes de la UE, sin importar donde estén ubicados usted o su empresa. El [tema Resumen del RGPD](gdpr.md) muestra información adicional.

## <a name="accountability-readiness-checklists"></a>Listas de comprobación de preparación de responsabilidad

Las listas de comprobación de preparación de responsabilidad ofrecen una forma cómoda de acceder a información que tal vez necesite para cumplir el RGPD cuando utilice productos y servicios de Microsoft. En estas listas de comprobación se muestran obligaciones establecidas por el RGPD que le pueden afectar y se le indica cómo puede ayudar a su organización a cumplir con el reglamento.

Puede ver una guía con cuatro secciones específicas para familias de productos y servicios de Microsoft:

- [Office 365](gdpr-arc-Office365.md)
- [Dynamics 365](gdpr-arc-Dynamics365.md)
- [Azure](gdpr-arc-Azure.md)
- [Soporte técnico y servicios profesionales de Microsoft](gdpr-arc-prof-services.md)

Puede administrar los elementos de esta lista de comprobación con el [Administrador de cumplimiento](compliance-manager.md) haciendo referencia al identificador de control y el título del control en Controles administrados de cliente en el icono RGPD.

Las listas de comprobación incluyen cuatro categorías básicas para un programa de privacidad compatible con el RGPD. Estas se muestran a continuación acompañadas con ejemplos de requisitos.

1. Condiciones de recopilación de datos y procesamiento:

    - ¿Cuándo se obtiene el consentimiento?  
    - Identificar y documentar el propósito  
    - Evaluación del impacto en la privacidad

2. Derechos del titular de los datos (DSR)  

    - Determinar la información relativa a las entidades de seguridad de DCP (titulares)  
    - Facilitar un mecanismo para modificar o retirar el consentimiento

3. Privacidad por diseño y de forma predeterminada  

    - Limitar la recopilación  
    - Cumplir con los niveles de identificación  
    - Archivos temporales

4. Protección y seguridad de los datos  

    - Conocer la organización y su contexto  
    - Planificación  
    - Directivas de seguridad de la información

## <a name="customer-agreements"></a>Acuerdos con el cliente

- **Términos del servicio en línea**: encontrará los compromisos contractuales de Microsoft en lo que respecta al RGPD en los [términos del servicio en línea](https://go.microsoft.com/fwlink/p/?linkid=2052208).
- **Términos del producto de Microsoft**: Microsoft amplía los [compromisos de los términos del RGPD](https://go.microsoft.com/fwlink/p/?linkid=2052213) a todos los clientes de licencias por volumen.
- **Anexo sobre protección de datos**: los servicios Microsoft [amplían los compromisos](https://go.microsoft.com/fwlink/p/?linkid=2052215) a los clientes de los Servicios de consultoría de Microsoft y otros.

## <a name="gdpr-compliance-controls"></a>Controles de cumplimiento del RGPD

- **Usar el Administrador de cumplimiento**: revise e incorpore los controles que Microsoft usa para apoyar las obligaciones relativas al RGPD con el [Administrador de cumplimiento](compliance-manager.md).
- **Asignación de controles del RGPD**: obtenga acceso a una [asignación detallada](https://go.microsoft.com/fwlink/p/?linkid=2052220) de los controles de Microsoft para las obligaciones relativas al GDPR.

## <a name="records-of-processing-for-processors"></a>Registros de procesamiento para procesadores

Debido a la extensa y amplia variedad de servicios en línea que proporcionamos como procesadores a los clientes responsables, esperamos que los clientes puedan identificar los servicios para buscar los registros de procesamiento y recuperar los registros relevantes en las herramientas en línea que proporcionamos. Un ejemplo de ello son los registros de procesamiento para Azure, en los que se solicitaría los clientes identificar qué tipos de actividad de procesamiento buscarán los registros.

### <a name="azure-logs"></a>Registros de Azure

Por lo general, los clientes se interesarán en los registros de actividad y, potencialmente, en los registros de diagnóstico:

- **Registros de actividad**: los [registros de actividad](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview) proporcionan información sobre las operaciones efectuadas en los recursos de una suscripción. Los registros de actividad pueden ayudar a determinar el iniciador de una operación, el tiempo de la incidencia y su estado.
- **Registros de diagnóstico**: los [registros de diagnóstico](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview) son todos los registros emitidos por cada recurso. Entre estos registros se incluyen los del sistema de eventos de Windows, los de Azure Storage, los de la auditoría de Key Vault y los de acceso a la puerta de enlace de aplicaciones y firewall.
- **Archivado de registro**: todos los registros de diagnóstico se archivan en una cuenta de almacenamiento de Azure centralizada y cifrada. La retención se puede configurar por el usuario hasta por 730 días para cumplir los requisitos de retención específicos de la organización. Estos registros se conectan con los de Azure Monitor para su procesamiento, almacenamiento e informes de panel.

### <a name="other-logs"></a>Otros registros

Asimismo, las siguientes soluciones de supervisión se instalan como parte de esta arquitectura. Es responsabilidad del cliente configurar estas soluciones para que se alineen con los controles de seguridad de FedRAMP:

- [Evaluación de AD](https://docs.microsoft.com/azure/azure-monitor/insights/ad-assessment): la solución de comprobación de estado de Active Directory evalúa el riesgo y el estado de los entornos de servidor en un intervalo regular y proporciona una lista de priorizada de las recomendaciones específicas para la infraestructura de servidor implementada.
- [Evaluación contra el malware](https://docs.microsoft.com/azure/security-center/security-center-services?tabs=features-windows#supported-endpoint-protection-solutions-): la solución contra el malware informa sobre el malware, las amenazas y el estado de protección.
- [Azure Automation](https://docs.microsoft.com/azure/automation/automation-hybrid-runbook-worker): la solución Azure Automation almacena, ejecuta y administra los runbook.
- [Seguridad y auditoría](https://docs.microsoft.com/azure/security-center/security-center-introduction): el panel de seguridad y auditoría proporciona información de alto nivel sobre el estado de seguridad de los recursos al ofrecer métricas en dominios de seguridad, problemas notables, detecciones, inteligencia sobre amenazas y consultas de seguridad comunes.
- [Evaluación de SQL](https://docs.microsoft.com/azure/azure-monitor/insights/sql-assessment): la solución de comprobación de estado de SQL evalúa el riesgo y el estado de los entornos de servidor en un intervalo regular y proporciona a los clientes con una lista de priorizada de las recomendaciones específicas para la infraestructura de servidor implementada.
- [Administración de actualizaciones](https://docs.microsoft.com/azure/automation/update-management/update-mgmt-overview): la solución de administración de actualizaciones permite a los clientes administrar actualizaciones de seguridad del sistema operativo, incluyendo el estado de las actualizaciones disponibles y el proceso de instalación de las actualizaciones necesarias.
- [Estado del agente](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth): la solución de estado del agente informa sobre cuántos agentes se han implementado y su distribución geográfica, así como cuántos no responden y el número de los que están enviando datos operacionales.
- [Registros de actividad de Azure](https://docs.microsoft.com/azure/azure-monitor/platform/activity-log): la solución de análisis de registros de actividad ayuda a analizar los registros de actividad de Azure en todas las suscripciones de Azure para un cliente.
- [Seguimiento de cambios](https://docs.microsoft.com/azure/azure-monitor/platform/activity-log): la solución de seguimiento de los cambios permite a los clientes identificar fácilmente los cambios en el entorno.

Para obtener más información sobre las medidas técnicas y de seguridad para Azure, los clientes responsables deberán visitar la [documentación de seguridad de Azure](https://docs.microsoft.com/azure/security/). Como Microsoft no sabe si los datos de los clientes son datos personales o no, Azure procesa todos los datos de los clientes como si fueran datos personales, por lo que es probable que el cliente considere todo el material como relevante.

### <a name="processor-information"></a>Información del procesador

Office 365 es otro producto del que es posible que el cliente necesite registros de información de procesamiento para procesadores. Para ver información relacionada con Office 365, consulte el artículo sobre [Buscar el registro de auditoría en el centro de seguridad y cumplimiento](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

También puede ver información sobre Dynamics 365 gracias al centro de seguridad y cumplimiento.  Para ver la página del centro de seguridad y cumplimiento, asegúrese de que tiene la licencia correcta. Obtenga más información sobre las licencias con el artículo sobre la [descripción del servicio del centro de seguridad y cumplimiento](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center). Para buscar los eventos de Dynamics 365, visite el registro de auditoría unificado en el [centro de seguridad y cumplimiento](https://protection.office.com/unifiedauditlog).

### <a name="professional-services-information"></a>Información de servicios profesionales

En el caso de los servicios profesionales, los datos de soporte de los servicios profesionales los proporciona el cliente al ingeniero de soporte técnico por parte del representante del cliente.  Esto puede producirse cuando un cliente envía una solicitud de servicio a través del portal de producto en línea, del centro de servicios o por teléfono.

La información se almacena en los sistemas de CRM y solo se usa para los propósitos siguientes:

- Ofrecer servicios profesionales, incluyendo soporte técnico, planificación profesional, asesoría, orientación, migración de datos, implementación y servicios de desarrollo de soluciones y software.  
- Solución de problemas (prevención, detección, investigación, mitigación y reparación de problemas, incluyendo los incidentes de seguridad); y 
- La mejora continua (mantenimiento de los servicios profesionales, incluida la instalación de las actualizaciones más recientes, e implementar mejoras a la confiabilidad, la eficacia, la calidad y la seguridad). 

Debido a la escala de las operaciones de soporte técnico, Microsoft actúa como sistema CRM basado en grupos de producto. Los registros de procesamiento se incluirán en estos sistemas.
El historial de procesamiento se refleja en los registros mantenidos en nuestros sistemas de CRM.  En la mayoría de las ocasiones, el historial de solicitud de servicio está disponible en los portales o en el centro de servicios.
Para cualquier detalle específico que no esté disponible en los portales o cualquier otra consulta sobre el procesamiento de los datos, póngase en contacto con el administrador técnico de cuentas o contacte con el [soporte técnico de Microsoft](https://support.microsoft.com/contactus/).

## <a name="learn-more"></a>Más información

- [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
