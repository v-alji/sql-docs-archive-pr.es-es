---
title: Mensajes de alertas de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6819720c-d848-4b90-9b51-89501b4f4645
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d50c3dd24c0057f695a9318c5eef7ad9e7540a45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674644"
---
# <a name="data-alert-messages"></a><span data-ttu-id="f422f-102">Mensajes de alertas de datos</span><span class="sxs-lookup"><span data-stu-id="f422f-102">Data Alert Messages</span></span>
  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="f422f-103">envían dos tipos de mensajes de alertas de datos por correo electrónico: mensajes con resultados de alertas de datos y mensajes con descripciones de errores.</span><span class="sxs-lookup"><span data-stu-id="f422f-103">data alerts deliver two types of data alert messages by email: Messages with data alert results and messages with error descriptions.</span></span> <span data-ttu-id="f422f-104">Los mensajes con resultados informan a todos los destinatarios de los cambios realizados en los datos del informe que sean de interés común e importantes para las decisiones empresariales.</span><span class="sxs-lookup"><span data-stu-id="f422f-104">Messages with results keep all recipients informed about changes in report data that is of common interest and important to business decisions.</span></span> <span data-ttu-id="f422f-105">Si por alguna razón se produce un error y los resultados no están disponibles, se envía en su lugar el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="f422f-105">If for some reason an error occurs and the results are not available, the error message is sent instead.</span></span>

 <span data-ttu-id="f422f-106">El propietario de la definición de la alerta de datos también puede ver la información sobre la instancia de la alerta de datos en el Administrador de alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="f422f-106">The owner of the data alert definition also can view information about the data alert instance in Data Alert Manager.</span></span> <span data-ttu-id="f422f-107">Para más información, consulte [Data Alert Manager for SharePoint Users](../../2014/reporting-services/data-alert-manager-for-sharepoint-users.md).</span><span class="sxs-lookup"><span data-stu-id="f422f-107">For more information, see [Data Alert Manager for SharePoint Users](../../2014/reporting-services/data-alert-manager-for-sharepoint-users.md).</span></span>

##  <a name="data-alert-messages"></a><a name="DataAlertMessages"></a><span data-ttu-id="f422f-108">Mensajes de alerta de datos</span><span class="sxs-lookup"><span data-stu-id="f422f-108">Data Alert Messages</span></span>
 <span data-ttu-id="f422f-109">En las imágenes siguientes se muestra un mensaje de alerta de datos con resultados y un mensaje de alerta con una descripción de error.</span><span class="sxs-lookup"><span data-stu-id="f422f-109">The following pictures show a data alert message with results and an alert message with an error description.</span></span>

 <span data-ttu-id="f422f-110">**Mensaje de resultados**</span><span class="sxs-lookup"><span data-stu-id="f422f-110">**Results message**</span></span>

 <span data-ttu-id="f422f-111">![Mensaje de correo electrónico de alerta de datos con los resultados](media/rs-alertmessageresults.gif "Mensaje de correo electrónico de alerta de datos con los resultados")</span><span class="sxs-lookup"><span data-stu-id="f422f-111">![Data alert e-mail message with results](media/rs-alertmessageresults.gif "Data alert e-mail message with results")</span></span>

 <span data-ttu-id="f422f-112">**Mensaje de error**</span><span class="sxs-lookup"><span data-stu-id="f422f-112">**Error message**</span></span>

 <span data-ttu-id="f422f-113">![Mensaje de alerta de datos con mensaje de error](media/rs-alertmessageerrror.gif "Mensaje de alerta de datos con mensaje de error")</span><span class="sxs-lookup"><span data-stu-id="f422f-113">![Data alert message with error message](media/rs-alertmessageerrror.gif "Data alert message with error message")</span></span>

 <span data-ttu-id="f422f-114">Los mensajes incluyen los mismos tipos de información.</span><span class="sxs-lookup"><span data-stu-id="f422f-114">The messages include the same types of information.</span></span>

1.  <span data-ttu-id="f422f-115">**En nombre de** contiene el nombre de la persona que creó la definición de alerta de datos.</span><span class="sxs-lookup"><span data-stu-id="f422f-115">**On behalf of** contains the name of the person who created the data alert definition.</span></span>

2.  <span data-ttu-id="f422f-116">Si proporcionó una descripción en la definición de la alerta, esta se muestra bajo **en nombre de**.</span><span class="sxs-lookup"><span data-stu-id="f422f-116">If you provided a description in the alert definition, it displays below **On behalf of**.</span></span>

3.  <span data-ttu-id="f422f-117">En**Resultados de alertas** se muestran la filas de la fuente de distribución de datos del informe que satisfacen las reglas especificadas en la definición de la alerta en formato tabular o se muestra la descripción de un error.</span><span class="sxs-lookup"><span data-stu-id="f422f-117">**Alert Results** display the rows in the report data feed that satisfy the rules specified in the alert definition in a tabular format or display an error description.</span></span> <span data-ttu-id="f422f-118">No hay límite en el número de filas que se pueden mostrar.</span><span class="sxs-lookup"><span data-stu-id="f422f-118">There is no limit on the number of rows that displays.</span></span>

4.  <span data-ttu-id="f422f-119">**Ir a informe** es un vínculo al informe en el que se basa la definición de alerta.</span><span class="sxs-lookup"><span data-stu-id="f422f-119">**Go to report** is a link to the report that the alert definition is built upon.</span></span> <span data-ttu-id="f422f-120">Si el vínculo no es válido porque se ha movido o eliminado el informe, se muestra un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="f422f-120">If the link is not valid because the report was moved or deleted, an error message displays.</span></span>

5.  <span data-ttu-id="f422f-121">En**Reglas** se muestran las reglas y las cláusulas de la definición de alerta.</span><span class="sxs-lookup"><span data-stu-id="f422f-121">**Rule(s)** lists the rules and clauses in the alert definition.</span></span> <span data-ttu-id="f422f-122">Esta información le ayuda a comprobar y entender los resultados de la alerta, así como a identificar reglas en la definición de alerta de datos que tal vez desee cambia para restringir o ampliar los resultados.</span><span class="sxs-lookup"><span data-stu-id="f422f-122">This information helps you verify and understand the alert results and identify rules in the data alert definition that you might want to change to narrow or broaden results.</span></span>

6.  <span data-ttu-id="f422f-123">En**Parámetros de informe** se muestran los parámetros y los valores de parámetro que se usaron cuando se ejecutó el informe.</span><span class="sxs-lookup"><span data-stu-id="f422f-123">**Report parameters** list the parameters and parameter values that were used when the report was run.</span></span> <span data-ttu-id="f422f-124">Los parámetros y los valores de parámetro le ayudan a entender los resultados de las alertas.</span><span class="sxs-lookup"><span data-stu-id="f422f-124">Parameters and parameter values help you understand the alert results.</span></span>

7.  <span data-ttu-id="f422f-125">En**Valores contextuales** se muestran los nombres y valores de los elementos del informe que están fuera de las regiones de datos del informe.</span><span class="sxs-lookup"><span data-stu-id="f422f-125">**Contextual values** list the names and values of report items that are outside of the report data regions.</span></span> <span data-ttu-id="f422f-126">Los elementos suelen ser cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="f422f-126">The items are typically text boxes.</span></span> <span data-ttu-id="f422f-127">Por ejemplo, un cuadro de texto con un valor constante como un asunto o una descripción de un informe.</span><span class="sxs-lookup"><span data-stu-id="f422f-127">For example, a text box with a constant value such as the subject or description of a report.</span></span>

 <span data-ttu-id="f422f-128">La única diferencia entre los dos tipos de mensajes es el elemento 5, **Resultados de alertas**.</span><span class="sxs-lookup"><span data-stu-id="f422f-128">The only difference between the two message types is item 5, **Alert Results**.</span></span> <span data-ttu-id="f422f-129">Si ocurre un error cuando se crea una instancia de alerta de datos o un mensaje de alerta de datos, **Resultados de alertas** muestra un mensaje de error que describe el problema.</span><span class="sxs-lookup"><span data-stu-id="f422f-129">If an error occurs when a data alert instance or data alert message is created, **Alert Results** displays an error message that describes the problem.</span></span> <span data-ttu-id="f422f-130">El mensaje de error, enviado a todos los destinatarios, permite saber que los resultados de alertas esperados para la toma de decisiones empresariales no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="f422f-130">The error message, sent to all recipients, let them know that the alert results that they are expecting and might rely on to make business decisions are not available.</span></span>

 

##  <a name="related-tasks"></a><a name="HowTo"></a> <span data-ttu-id="f422f-131">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="f422f-131">Related Tasks</span></span>
 <span data-ttu-id="f422f-132">En esta sección se muestran los procedimientos para crear y editar las definiciones de alertas de datos que proporcionan la mayor parte de la información que se muestra en los mensajes de alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="f422f-132">This section lists procedures that show you how to create and edit the data alert definitions that provide much of the information that you see in data alert messages.</span></span>

-   [<span data-ttu-id="f422f-133">Creación de una alerta de datos en el Diseñador de alertas de datos</span><span class="sxs-lookup"><span data-stu-id="f422f-133">Create a Data Alert in Data Alert Designer</span></span>](create-a-data-alert-in-data-alert-designer.md)

-   [<span data-ttu-id="f422f-134">Modificación de una alerta de datos en el Diseñador de alertas</span><span class="sxs-lookup"><span data-stu-id="f422f-134">Edit a Data Alert in Alert Designer</span></span>](edit-a-data-alert-in-alert-designer.md)



## <a name="see-also"></a><span data-ttu-id="f422f-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f422f-135">See Also</span></span>
 <span data-ttu-id="f422f-136">[Diseñador de alertas de datos](../../2014/reporting-services/data-alert-designer.md) [Reporting Services alertas de datos](../ssms/agent/alerts.md)</span><span class="sxs-lookup"><span data-stu-id="f422f-136">[Data Alert Designer](../../2014/reporting-services/data-alert-designer.md) [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>


