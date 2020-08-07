---
title: Modificar una alerta de datos en el Diseñador de alertas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- editing, data alerts
- updating, data alerts
- editing, alerts
- updating, alerts
ms.assetid: dde3664d-90b5-4b12-969e-39152c86e58a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9906b33ae50d51733eaec1bf5c201c9f5b5d120e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747493"
---
# <a name="edit-a-data-alert-in-alert-designer"></a><span data-ttu-id="31bea-102">Modificar una alerta de datos en el Diseñador de alertas</span><span class="sxs-lookup"><span data-stu-id="31bea-102">Edit a Data Alert in Alert Designer</span></span>
  <span data-ttu-id="31bea-103">La definición de alerta de datos que desea editar se abre en el Administrador de alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="31bea-103">You open the data alert definition that you want to edit from Data Alert Manager.</span></span> <span data-ttu-id="31bea-104">Solo el usuario que creó la definición de la alerta puede modificarla.</span><span class="sxs-lookup"><span data-stu-id="31bea-104">Only the user that created the alert definition can edit it.</span></span> <span data-ttu-id="31bea-105">Para más información sobre cómo abrir el Administrador de alertas de datos, vea [Administrar mis alertas de datos en el Administrador de alertas de datos](manage-my-data-alerts-in-data-alert-manager.md).</span><span class="sxs-lookup"><span data-stu-id="31bea-105">For more information about opening Data Alert Manager, see [Manage My Data Alerts in Data Alert Manager](manage-my-data-alerts-in-data-alert-manager.md).</span></span>

 <span data-ttu-id="31bea-106">En la imagen siguiente se muestra el menú contextual de una alerta de datos en el Administrador de alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="31bea-106">The following picture shows you the context menu on a data alert in Data Alert Manager.</span></span>

 <span data-ttu-id="31bea-107">![Abrir el Diseñador de alertas de datos haciendo clic en Editar](media/rs-alertmanageriwopendesigner.gif "Abrir el Diseñador de alertas de datos haciendo clic en Editar")</span><span class="sxs-lookup"><span data-stu-id="31bea-107">![Open Data Alert Designer by clicking Edit](media/rs-alertmanageriwopendesigner.gif "Open Data Alert Designer by clicking Edit")</span></span>

 <span data-ttu-id="31bea-108">El procedimiento siguiente incluye los pasos para abrir la definición de alerta con objeto de modificarla en el Diseñador de alertas de datos desde el Administrador de alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="31bea-108">The following procedure includes the steps to open the alert definition for editing in Data Alert Designer from Data Alert Manager.</span></span>

### <a name="to-edit-a-data-alert-definition-in-data-alert-designer"></a><span data-ttu-id="31bea-109">Para editar una definición de alerta de datos en el Diseñador de alertas de datos</span><span class="sxs-lookup"><span data-stu-id="31bea-109">To edit a data alert definition in Data Alert Designer</span></span>

1.  <span data-ttu-id="31bea-110">En el Administrador de alertas de datos, haga clic con el botón derecho en la definición de alerta de datos que quiere editar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="31bea-110">In Data Alert Manager, right-click the data alert definition that you want to edit and click **Edit**.</span></span>

     <span data-ttu-id="31bea-111">La definición de alerta se abre en el Diseñador de alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="31bea-111">The alert definition opens in Data Alert Designer.</span></span>

2.  <span data-ttu-id="31bea-112">Actualice las reglas, la configuración de la programación y la de los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="31bea-112">Update the rules, schedule settings, and email settings.</span></span> <span data-ttu-id="31bea-113">Para más información, vea [Diseñador de alertas de datos](../../2014/reporting-services/data-alert-designer.md) y [Crear una alerta de datos en el Diseñador de alertas de datos](create-a-data-alert-in-data-alert-designer.md).</span><span class="sxs-lookup"><span data-stu-id="31bea-113">For more information, see [Data Alert Designer](../../2014/reporting-services/data-alert-designer.md) and [Create a Data Alert in Data Alert Designer](create-a-data-alert-in-data-alert-designer.md).</span></span>

    > [!NOTE]
    >  <span data-ttu-id="31bea-114">No puede elegir una fuente de distribución de datos diferente.</span><span class="sxs-lookup"><span data-stu-id="31bea-114">You cannot choose a different data feed.</span></span> <span data-ttu-id="31bea-115">Para utilizar otra fuente de distribución de datos, debe crear una nueva definición de alerta de datos.</span><span class="sxs-lookup"><span data-stu-id="31bea-115">To use a different data feed, you must create a new data alert definition.</span></span>

3.  <span data-ttu-id="31bea-116">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="31bea-116">Click **Save**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="31bea-117">Si el informe ha cambiado y las fuentes de distribución de datos generadas desde el informe han cambiado, la definición de la alerta podría no ser válida.</span><span class="sxs-lookup"><span data-stu-id="31bea-117">If the report has changed and the data feeds generated from the report have changed the alert definition might no longer be valid.</span></span> <span data-ttu-id="31bea-118">Esto ocurre cuando una columna a la que la definición de alerta hace referencia en sus reglas se elimina del informe, cuando cambia el tipo de datos o cuando se elimina o mueve el informe.</span><span class="sxs-lookup"><span data-stu-id="31bea-118">This occurs when a column that the alert definition references in its rules is deleted from the report or changes data type or the report is deleted or moved.</span></span> <span data-ttu-id="31bea-119">Puede abrir una definición de alerta que no sea válida, pero no puede volver a guardarla hasta que sea válida con arreglo a la versión actual de la fuente de distribución de datos del informe en la que se basa.</span><span class="sxs-lookup"><span data-stu-id="31bea-119">You can open an alert definition that is not valid, but you cannot resave it until it is valid based on the current version of the report data feed that it is built upon.</span></span> <span data-ttu-id="31bea-120">Para más información sobre cómo se generan las fuentes de datos de informes, vea [Generar fuentes de distribución de datos a partir de informes &#40;Generador de informes y SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="31bea-120">To learn more about how data feeds are generated from reports, see [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="31bea-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="31bea-121">See Also</span></span>
 <span data-ttu-id="31bea-122">[Administrador de alertas de datos para los administradores de alertas](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) [Reporting Services alertas de datos](../ssms/agent/alerts.md)</span><span class="sxs-lookup"><span data-stu-id="31bea-122">[Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>


