---
title: 'Tarea 4: crear un proyecto de SSIS con SQL Server Data Tools | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 8603ea91-2ec4-40b6-8070-4f824332f5d3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 07976dbd2c84b1385d79ce3f4ce4f616e0f706b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746629"
---
# <a name="task-4-creating-an-ssis-project-using-sql-server-data-tools"></a><span data-ttu-id="15f90-102">Tarea 4: Creación de un proyecto de SSIS con SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="15f90-102">Task 4: Creating an SSIS Project using SQL Server Data Tools</span></span>
  <span data-ttu-id="15f90-103">En esta tarea, creará un proyecto de SSIS usando **SQL Server Data Tools** para automatizar la limpieza y la búsqueda de coincidencias de los datos de proveedor.</span><span class="sxs-lookup"><span data-stu-id="15f90-103">In this task, you create an SSIS project by using **SQL Server Data Tools** to automate cleansing and matching supplier data.</span></span>

1.  <span data-ttu-id="15f90-104">Inicie **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="15f90-104">Launch **SQL Server Data Tools**.</span></span> <span data-ttu-id="15f90-105">Haga clic en Inicio, seleccione **Todos los programas**, expanda **Microsoft SQL Server 2012**y, a continuación, haga clic en **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="15f90-105">Click Start, point to **All Programs**, expand **Microsoft SQL Server 2012**, and click **SQL Server Data Tools**.</span></span>

2.  <span data-ttu-id="15f90-106">En el menú **Archivo** , elija **Nuevo**y, a continuación, haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="15f90-106">On the **File** menu, point to **New**, and click **Project**.</span></span>

3.  <span data-ttu-id="15f90-107">Expanda **Business Intelligence** en el panel **Plantillas instaladas** y seleccione **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="15f90-107">Expand **Business Intelligence** in the **Installed Templates** pane, and select **Integration Services**.</span></span>

     <span data-ttu-id="15f90-108">![Visual Studio - Cuadro de diálogo Nuevo proyecto](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-01.jpg "Visual Studio - Cuadro de diálogo Nuevo proyecto")</span><span class="sxs-lookup"><span data-stu-id="15f90-108">![Visual Studio - New Project Dialog Box](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-01.jpg "Visual Studio - New Project Dialog Box")</span></span>

4.  <span data-ttu-id="15f90-109">Seleccione **Proyecto de Integration Services** en la **lista de tipos de proyecto**.</span><span class="sxs-lookup"><span data-stu-id="15f90-109">Select **Integration Services Project** in the **list of project types**.</span></span>

5.  <span data-ttu-id="15f90-110">Escriba **CleanseAndCurateSuppliers** en **Nombre** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="15f90-110">Type **CleanseAndCurateSuppliers** for **Name** and click **OK**.</span></span>

6.  <span data-ttu-id="15f90-111">En la ventana **Explorador de soluciones** , haga clic con el botón secundario en **Package.dtsx** y seleccione **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="15f90-111">In **Solution Explorer** window, right-click **Package.dtsx** and select **Rename**.</span></span> <span data-ttu-id="15f90-112">Si no ve **Explorador de soluciones** ventana, haga clic en **Ver** en la barra de menús y, a continuación, haga clic en **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="15f90-112">If you don't see **Solution Explorer** window, click **View** on the menu bar and click **Solution Explorer**.</span></span>

     <span data-ttu-id="15f90-113">![Package.dtsx - Menú Renombrar](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-02.jpg "Package.dtsx - Menú Renombrar")</span><span class="sxs-lookup"><span data-stu-id="15f90-113">![Package.dtsx - Rename Menu](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-02.jpg "Package.dtsx - Rename Menu")</span></span>

7.  <span data-ttu-id="15f90-114">Escriba **CleanseAndCurate.dtsx** y presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="15f90-114">Type **CleanseAndCurate.dtsx** and press **ENTER**.</span></span> <span data-ttu-id="15f90-115">Asegúrese de que la **extensión** siga siendo **.dtsx**.</span><span class="sxs-lookup"><span data-stu-id="15f90-115">Make sure that the **extension** remains **.dtsx**.</span></span>

## <a name="next-step"></a><span data-ttu-id="15f90-116">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="15f90-116">Next Step</span></span>
 [<span data-ttu-id="15f90-117">Tarea 5: Adición de una tarea Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="15f90-117">Task 5: Adding Data Flow Task</span></span>](task-5-adding-data-flow-task.md)


