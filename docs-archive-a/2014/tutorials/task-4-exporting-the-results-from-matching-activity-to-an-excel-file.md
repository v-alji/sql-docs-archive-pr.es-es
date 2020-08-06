---
title: 'Tarea 4: exportar los resultados de la actividad de coincidencia a un archivo de Excel | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 644454c4-3c5a-469a-90ec-e51dc7fb99fc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b583e44f887fc0595fb904ec977f1de28c2fecd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747751"
---
# <a name="task-4-exporting-the-results-from-matching-activity-to-an-excel-file"></a><span data-ttu-id="16c02-102">Tarea 4: Exportación de los resultados de la actividad de coincidencia a un archivo de Excel</span><span class="sxs-lookup"><span data-stu-id="16c02-102">Task 4: Exporting the Results from Matching Activity to an Excel File</span></span>
  <span data-ttu-id="16c02-103">En esta tarea, exportará los resultados de la actividad de coincidencia a un archivo de Excel.</span><span class="sxs-lookup"><span data-stu-id="16c02-103">In this task, you export the results from the matching activity to an Excel file.</span></span>

1.  <span data-ttu-id="16c02-104">En la página **exportar** , seleccione **archivo de Excel** para el **tipo de destino**.</span><span class="sxs-lookup"><span data-stu-id="16c02-104">In the **Export** page, select **Excel File** for the **Destination Type**.</span></span>

2.  <span data-ttu-id="16c02-105">Seleccione la opción **resultados de permanencia** .</span><span class="sxs-lookup"><span data-stu-id="16c02-105">Select **Survivorship Results** option.</span></span> <span data-ttu-id="16c02-106">En el proceso de permanencia, DQS determina un registro de permanencia para cada clúster en función de la **regla de permanencia** seleccionada.</span><span class="sxs-lookup"><span data-stu-id="16c02-106">In the survivorship process, DQS determines a survivor record for each cluster based on the **Survivorship Rule** you selected.</span></span>

3.  <span data-ttu-id="16c02-107">Haga clic en **examinar** y navegue hasta la carpeta en la que desea almacenar el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="16c02-107">Click **Browse** and navigate to the folder where you want to store the output file.</span></span>

4.  <span data-ttu-id="16c02-108">Escriba **limpiar y coincidir Suppliers.xls** para el nombre y haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="16c02-108">Type **Cleansed and Matched Suppliers.xls** for the name and click **Open**.</span></span>

5.  <span data-ttu-id="16c02-109">Confirme que se ha seleccionado **registro dinámico** para la **regla de permanencia**.</span><span class="sxs-lookup"><span data-stu-id="16c02-109">Confirm that **Pivot Record** is selected for the **Survivorship Rule**.</span></span> <span data-ttu-id="16c02-110">Al seleccionar esta opción, se elige el registro dinámico de cada clúster para la salida de un clúster.</span><span class="sxs-lookup"><span data-stu-id="16c02-110">When you select this option, the pivot record for each cluster is picked for the output from a cluster.</span></span> <span data-ttu-id="16c02-111">Las demás opciones de la regla de supervivencia son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="16c02-111">The other options for the Survivorship Rule are:</span></span>

    1.  <span data-ttu-id="16c02-112">**Registro más completo:** El registro de permanencia es el que tiene el mayor número de campos rellenos.</span><span class="sxs-lookup"><span data-stu-id="16c02-112">**Most complete record:** Survivor record is the one with the largest number of populated fields.</span></span>

    2.  <span data-ttu-id="16c02-113">**Registro más largo:** El registro de permanencia es el que tiene el mayor número de términos en los campos de origen.</span><span class="sxs-lookup"><span data-stu-id="16c02-113">**Longest record:** Survivor record is the one with the largest number of terms in source fields.</span></span>

    3.  <span data-ttu-id="16c02-114">**Registro más completo y más largo:** El registro de permanencia es el que tiene el mayor número de campos rellenos y tiene el mayor número de términos en cada campo.</span><span class="sxs-lookup"><span data-stu-id="16c02-114">**Most complete and longest record:** Survivor record is the one with the largest number of populated fields, and has the largest number of terms in each field.</span></span>

     <span data-ttu-id="16c02-115">![Exportar resultados de la página de coincidencias](../../2014/tutorials/media/et-exportingtheresultsfrommatoanexcelfile.jpg "Exportar resultados de la página de coincidencias")</span><span class="sxs-lookup"><span data-stu-id="16c02-115">![Export Results from Matching Page](../../2014/tutorials/media/et-exportingtheresultsfrommatoanexcelfile.jpg "Export Results from Matching Page")</span></span>

6.  <span data-ttu-id="16c02-116">Haga clic en **exportar** para exportar los resultados a un archivo de Excel.</span><span class="sxs-lookup"><span data-stu-id="16c02-116">Click **Export** to export the results to an Excel file.</span></span>

7.  <span data-ttu-id="16c02-117">Haga clic en **cerrar** para cerrar el cuadro de diálogo **exportar correspondiente** .</span><span class="sxs-lookup"><span data-stu-id="16c02-117">Click **Close** to close the **Matching Export** dialog box.</span></span>

8.  <span data-ttu-id="16c02-118">Haga clic en **Finalizar** para finalizar la actividad de búsqueda de coincidencias.</span><span class="sxs-lookup"><span data-stu-id="16c02-118">Click **Finish** to finish the matching activity.</span></span>

9. <span data-ttu-id="16c02-119">Abra el archivo **limpio y el Suppliers.xlsxde coincidencia** y confirme que no ve ningún duplicado (IdProveedor).</span><span class="sxs-lookup"><span data-stu-id="16c02-119">Open the **Cleansed and Matched Suppliers.xlsx** file and confirm that you do not see any duplicates (SupplierID).</span></span>

 <span data-ttu-id="16c02-120">Ahora, tiene datos de proveedor que se han limpiado y en el que se han buscado coincidencias para quitar valores duplicados.</span><span class="sxs-lookup"><span data-stu-id="16c02-120">Now, you have supplier data that has been cleansed and matched to remove duplicates.</span></span>

## <a name="next-step"></a><span data-ttu-id="16c02-121">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="16c02-121">Next Step</span></span>
 [<span data-ttu-id="16c02-122">Lección 4: Almacenamiento de datos de proveedor en MDS</span><span class="sxs-lookup"><span data-stu-id="16c02-122">Lesson 4: Storing Supplier Data in MDS</span></span>](../../2014/tutorials/lesson-4-storing-supplier-data-in-mds.md)


