---
title: 'Tarea 5: exportar los resultados de la limpieza a un archivo de Excel | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: eaeafd65-d0d4-4a7d-a3ad-110ef644e90b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0dbdc1bef348e03e211e4933132985ea2c089b97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675690"
---
# <a name="task-5-exporting-cleansing-results-to-an-excel-file"></a><span data-ttu-id="d4e10-102">Tarea 5: Exportación de los resultados de la limpieza a un archivo de Excel</span><span class="sxs-lookup"><span data-stu-id="d4e10-102">Task 5: Exporting Cleansing Results to an Excel File</span></span>
  <span data-ttu-id="d4e10-103">En esta tarea, exportará los resultados de la actividad de limpieza a un archivo de Excel.</span><span class="sxs-lookup"><span data-stu-id="d4e10-103">In this task, you export results from the cleansing activity to an Excel file.</span></span> <span data-ttu-id="d4e10-104">Vea el tema sobre la [fase de exportación](https://msdn.microsoft.com/library/hh213061.aspx#Export) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="d4e10-104">See [Export Stage](https://msdn.microsoft.com/library/hh213061.aspx#Export) topic for more details.</span></span>  
  
1.  <span data-ttu-id="d4e10-105">En el panel derecho, seleccione **Excel** para el **tipo de destino**.</span><span class="sxs-lookup"><span data-stu-id="d4e10-105">In the right pane, select **Excel** for the **Destination Type**.</span></span>  
  
2.  <span data-ttu-id="d4e10-106">Haga clic en **examinar**, especifique el nombre del archivo de salida como **proveedor con limpieza List.xls**y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="d4e10-106">Click **Browse**, specify the output file name as **Cleansed Supplier List.xls**, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="d4e10-107">Seleccione **solo datos** para que el formato de **salida** exporte solo los datos limpios.</span><span class="sxs-lookup"><span data-stu-id="d4e10-107">Select **Data Only** for the **Output** format to export just the cleansed data.</span></span> <span data-ttu-id="d4e10-108">La segunda opción, **datos y limpieza**, le permite exportar detalles de la actividad de limpieza junto con los datos limpios.</span><span class="sxs-lookup"><span data-stu-id="d4e10-108">The second option, **Data and Cleansing Info**, lets you export cleansing activity details along with the cleansed data.</span></span> <span data-ttu-id="d4e10-109">La opción de **formato normalizar** permite aplicar los formatos de salida definidos en un dominio a los valores de ese dominio.</span><span class="sxs-lookup"><span data-stu-id="d4e10-109">The **Standardize Format** option lets you apply any output formats you define on a domain to the values of that domain.</span></span> <span data-ttu-id="d4e10-110">En el tutorial no ha definido ningún formato de salida en ningún dominio.</span><span class="sxs-lookup"><span data-stu-id="d4e10-110">You have not defined an output format on any domain in the tutorial.</span></span>  
  
     <span data-ttu-id="d4e10-111">![Exportar página de resultados de limpieza](../../2014/tutorials/media/et-exportingcleansingresultstoanexcelfile.jpg "Exportar página de resultados de limpieza")</span><span class="sxs-lookup"><span data-stu-id="d4e10-111">![Export Cleansing Results Page](../../2014/tutorials/media/et-exportingcleansingresultstoanexcelfile.jpg "Export Cleansing Results Page")</span></span>  
  
4.  <span data-ttu-id="d4e10-112">Haga clic en **exportar** para exportar los datos.</span><span class="sxs-lookup"><span data-stu-id="d4e10-112">Click **Export** to export the data.</span></span> <span data-ttu-id="d4e10-113">No haga clic en **Finalizar** todavía.</span><span class="sxs-lookup"><span data-stu-id="d4e10-113">Do not click **Finish** yet.</span></span>  
  
5.  <span data-ttu-id="d4e10-114">Haga clic en **cerrar** en el cuadro de diálogo **exportación** .</span><span class="sxs-lookup"><span data-stu-id="d4e10-114">Click **Close** on the **Exporting** dialog box.</span></span>  
  
6.  <span data-ttu-id="d4e10-115">Haga clic en **Finalizar** para finalizar la actividad.</span><span class="sxs-lookup"><span data-stu-id="d4e10-115">Click **Finish** to finish the activity.</span></span> <span data-ttu-id="d4e10-116">Si olvidó exportar los resultados antes de hacer clic en **Finalizar**, haga clic en **Abrir proyecto de calidad de datos** en la Página principal del **cliente DQS**, seleccione **limpiar lista de proveedores** en la lista de proyectos y haga clic en **siguiente** en la parte inferior de la pantalla para volver a la fase de **exportación** del proceso de limpieza.</span><span class="sxs-lookup"><span data-stu-id="d4e10-116">If you forgot to export results before clicking **Finish**, click **Open Data Quality Project** in the main page of **DQS Client**, select **Cleanse Supplier List** from the list of projects, and click **Next** at the bottom of the screen to get to the **Export** stage of cleansing process again.</span></span> <span data-ttu-id="d4e10-117">También puede cambiar a la pestaña **administrar y ver resultados** haciendo clic en el botón **atrás** .</span><span class="sxs-lookup"><span data-stu-id="d4e10-117">You can also switch to **Manage and View Results** tab by clicking **Back** button.</span></span>  
  
7.  <span data-ttu-id="d4e10-118">Abra el **List.xlsdel proveedor limpio** y haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d4e10-118">Open the **Cleansed Supplier List.xls** and do the following:</span></span>  
  
    1.  <span data-ttu-id="d4e10-119">Asegúrese de que no haya direcciones de correo electrónico que terminen con adventure-work.com (sin el carácter ') buscando adventure-work.com en la hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="d4e10-119">Ensure that there are no email addresses that end with adventure-work.com (without character 's') by searching for adventure-work.com in the worksheet.</span></span>  
  
    2.  <span data-ttu-id="d4e10-120">Compruebe que no hay ningún valor de **Estados Unidos** en la columna **país** .</span><span class="sxs-lookup"><span data-stu-id="d4e10-120">See that there is no **USA** value in the **Country** column.</span></span>  
  
    3.  <span data-ttu-id="d4e10-121">Busque **Los Angeles** y compruebe que el valor de **State** está establecido en **CA**.</span><span class="sxs-lookup"><span data-stu-id="d4e10-121">Search for **Los Angeles** and see that the **State** is set to **CA**.</span></span>  
  
    4.  <span data-ttu-id="d4e10-122">Confirme que no hay términos **Co.**, **Corp.** y **Inc.**.</span><span class="sxs-lookup"><span data-stu-id="d4e10-122">Confirm that there are no terms **Co.**, **Corp.**, and **Inc.**.</span></span>  
  
    5.  <span data-ttu-id="d4e10-123">Elimine la columna **validación de direcciones** de la hoja de cálculo y guarde el archivo de Excel.</span><span class="sxs-lookup"><span data-stu-id="d4e10-123">Delete the **Address Validation** column from the spreadsheet and save the excel file.</span></span> <span data-ttu-id="d4e10-124">Esta columna adicional corresponde al dominio de compuesto Validación de direcciones.</span><span class="sxs-lookup"><span data-stu-id="d4e10-124">This additional column corresponds to the Address Validation composite domain.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="d4e10-125">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="d4e10-125">Next Step</span></span>  
 [<span data-ttu-id="d4e10-126">Tarea 6: Importación de valores del proyecto Limpiar lista de proveedores</span><span class="sxs-lookup"><span data-stu-id="d4e10-126">Task 6: Importing Values from the Cleanse Supplier List Project</span></span>](../../2014/tutorials/task-6-importing-values-from-the-cleanse-supplier-list-project.md)  
  
  
