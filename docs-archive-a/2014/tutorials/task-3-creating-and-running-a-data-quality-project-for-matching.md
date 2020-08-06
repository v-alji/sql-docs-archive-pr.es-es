---
title: 'Tarea 3: crear y ejecutar un proyecto de calidad de datos para buscar coincidencias | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6260e911-ea8b-4c69-a39d-d1bccd565a32
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 221d6d583c61ee035c20fcb63f0ed5278f2b8678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663858"
---
# <a name="task-3-creating-and-running-a-data-quality-project-for-matching"></a><span data-ttu-id="28f89-102">Tarea 3: Creación y ejecución de un proyecto de calidad de datos para buscar coincidencias</span><span class="sxs-lookup"><span data-stu-id="28f89-102">Task 3: Creating and Running a Data Quality Project for Matching</span></span>
  <span data-ttu-id="28f89-103">En esta tarea, creará un proyecto de calidad de datos para la actividad de búsqueda de coincidencias y ejecutará el proceso de coincidencia en los datos limpios de proveedores para quitar duplicados en los datos.</span><span class="sxs-lookup"><span data-stu-id="28f89-103">In this task, you create a Data Quality Project for the matching activity and run the matching process on cleansed supplier data to remove any duplicates in the data.</span></span>

1.  <span data-ttu-id="28f89-104">En la Página principal del **cliente DQS**, haga clic en **nuevo proyecto de calidad de datos**.</span><span class="sxs-lookup"><span data-stu-id="28f89-104">On the main page of **DQS Client**, click **New Data Quality Project**.</span></span>

2.  <span data-ttu-id="28f89-105">Escriba **quitar proveedores duplicados** del **nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="28f89-105">Type **Remove Supplier Duplicates** from the **Name of the project**.</span></span>

3.  <span data-ttu-id="28f89-106">Seleccione **proveedores** en la lista de KB del campo **usar base de conocimiento** .</span><span class="sxs-lookup"><span data-stu-id="28f89-106">Select **Suppliers** from the list of KBs for the **Use Knowledge Base** field.</span></span> <span data-ttu-id="28f89-107">En la lección anterior creó una directiva de coincidencia en esta base de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="28f89-107">You have created a matching policy in this knowledge base in the previous lesson.</span></span>

4.  <span data-ttu-id="28f89-108">Seleccione **coincidencia** en la **lista de actividades** en el panel de la parte inferior derecha.</span><span class="sxs-lookup"><span data-stu-id="28f89-108">Select **Matching** from the **list of activities** from the bottom-right pane.</span></span>

     <span data-ttu-id="28f89-109">![Nuevo proyecto de calidad de datos - Coincidencia seleccionada](../../2014/tutorials/media/et-creatingandrunningadqpformatching.jpg "Nuevo proyecto de calidad de datos - Coincidencia seleccionada")</span><span class="sxs-lookup"><span data-stu-id="28f89-109">![New Data Quality Project - Matching Selected](../../2014/tutorials/media/et-creatingandrunningadqpformatching.jpg "New Data Quality Project - Matching Selected")</span></span>

5.  <span data-ttu-id="28f89-110">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="28f89-110">Click **Next**.</span></span>

6.  <span data-ttu-id="28f89-111">En la página **Asignación** , seleccione **Archivo de Excel** en **Origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="28f89-111">In the **Map** page, select **Excel File** for **Data Source**.</span></span>

7.  <span data-ttu-id="28f89-112">Haga clic en **examinar** y seleccione **proveedor con limpieza List.xls**, que es el archivo de salida de la actividad limpieza.</span><span class="sxs-lookup"><span data-stu-id="28f89-112">Click **Browse** and select **Cleansed Supplier List.xls**, which is the output file from the cleansing activity.</span></span>

8.  <span data-ttu-id="28f89-113">Asigne la columna de origen **SupplierID** al dominio ID. de **proveedor** , la columna **nombre de proveedor** a dominio nombre de **proveedor** y la columna **ContactEmailAddress** al dominio **correo electrónico de contacto** .</span><span class="sxs-lookup"><span data-stu-id="28f89-113">Map **SupplierID** source column to the **Supplier ID** domain, **Supplier Name** column to **Supplier Name** domain, and **ContactEmailAddress** column to **Contact Email** domain.</span></span>

9. <span data-ttu-id="28f89-114">Haga clic en **siguiente** para cambiar a la página de **búsqueda de coincidencias** .</span><span class="sxs-lookup"><span data-stu-id="28f89-114">Click **Next** to switch to the **Matching** page.</span></span>

10. <span data-ttu-id="28f89-115">Haga clic en **iniciar** para iniciar el proceso de búsqueda de coincidencias.</span><span class="sxs-lookup"><span data-stu-id="28f89-115">Click **Start** to start the matching process.</span></span> <span data-ttu-id="28f89-116">Debe ver unos resultados similares a los de la tarea anterior porque ha usado el mismo archivo de entrada para definir la directiva de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="28f89-116">You should see results similar to those from the previous task because you used the same input file for defining the matching policy.</span></span>

11. <span data-ttu-id="28f89-117">Examine todos los registros coincidentes y su puntuación de coincidencia en el cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="28f89-117">Review all the matched records and their matching score in the list box.</span></span> <span data-ttu-id="28f89-118">Los resultados deben ser los mismos que los de la tarea anterior.</span><span class="sxs-lookup"><span data-stu-id="28f89-118">The results should be same as the ones you saw in the previous task.</span></span> <span data-ttu-id="28f89-119">Vea los pasos de la tarea anterior para analizar los resultados de esta actividad de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="28f89-119">See the steps in the previous task to analyze the results from this matching activity.</span></span>

12. <span data-ttu-id="28f89-120">Haga clic en **siguiente** para cambiar a la página **exportar** .</span><span class="sxs-lookup"><span data-stu-id="28f89-120">Click **Next** to switch to the **Export** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="28f89-121">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="28f89-121">Next Step</span></span>
 [<span data-ttu-id="28f89-122">Tarea 4: Exportación de los resultados de la actividad de coincidencia a un archivo de Excel</span><span class="sxs-lookup"><span data-stu-id="28f89-122">Task 4: Exporting the Results from Matching Activity to an Excel File</span></span>](../../2014/tutorials/task-4-exporting-the-results-from-matching-activity-to-an-excel-file.md)


