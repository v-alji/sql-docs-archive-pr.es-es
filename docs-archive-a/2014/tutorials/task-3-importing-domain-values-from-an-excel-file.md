---
title: 'Tarea 3: importar valores de dominio desde un archivo de Excel | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 242e8309-1195-495b-9cd5-aa127748c185
ms.author: lle
author: lrtoyou1223
ms.openlocfilehash: 707a3925bb6d0014e2a1248f904123b076024e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663856"
---
# <a name="task-3-importing-domain-values-from-an-excel-file"></a><span data-ttu-id="09b6e-102">Tarea 3: Importación de valores de dominio desde un archivo de Excel</span><span class="sxs-lookup"><span data-stu-id="09b6e-102">Task 3: Importing Domain Values from an Excel File</span></span>

  <span data-ttu-id="09b6e-103">En esta tarea, importará valores para el dominio **Estado** desde una hoja de cálculo de un archivo de Excel.</span><span class="sxs-lookup"><span data-stu-id="09b6e-103">In this task, you import values for the **State** domain from a worksheet of an Excel file.</span></span>

1.  <span data-ttu-id="09b6e-104">Haga clic en el dominio **Estado** en la lista **Dominio**.</span><span class="sxs-lookup"><span data-stu-id="09b6e-104">Click **State** domain in the **Domain list**.</span></span>

2.  <span data-ttu-id="09b6e-105">Asegúrese de que la pestaña **Valores del dominio** esté activa en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="09b6e-105">Ensure that the **Domain Values** tab is active in the right pane.</span></span>

3.  <span data-ttu-id="09b6e-106">En el panel derecho, en la barra de herramientas, haga clic en la **flecha abajo** situada junto al botón **Importar valores** y, a continuación, haga clic en **Importar valores válidos desde Excel**.</span><span class="sxs-lookup"><span data-stu-id="09b6e-106">In the right pane, from the toolbar, click **down arrow** next to the **Import Values** button, and click **Import Valid Values from Excel**.</span></span>

     <span data-ttu-id="09b6e-107">![Importar valores válidos del menú Excel](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-01.jpg "Importar valores válidos del menú Excel")</span><span class="sxs-lookup"><span data-stu-id="09b6e-107">![Import Valid Values from Excel Menu](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-01.jpg "Import Valid Values from Excel Menu")</span></span>

4.  <span data-ttu-id="09b6e-108">Haga clic en **Examinar**, seleccione **Suppliers.xls**y haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="09b6e-108">Click **Browse**, select **Suppliers.xls**, and click **Open**.</span></span>

5.  <span data-ttu-id="09b6e-109">Seleccione **StatesToImport$** en **Hoja de cálculo**.</span><span class="sxs-lookup"><span data-stu-id="09b6e-109">Select **StatesToImport$** for the **Worksheet**.</span></span>

     <span data-ttu-id="09b6e-110">![Cuadro de diálogo Importar valores de dominio](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-02.jpg "Cuadro de diálogo Importar valores de dominio")</span><span class="sxs-lookup"><span data-stu-id="09b6e-110">![Import Domain Values Dialog Box](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-02.jpg "Import Domain Values Dialog Box")</span></span>

6.  <span data-ttu-id="09b6e-111">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Importar valores del dominio** .</span><span class="sxs-lookup"><span data-stu-id="09b6e-111">Click **OK** to close the **Import Domain Values** dialog box.</span></span> <span data-ttu-id="09b6e-112">Debe ver todos los nombres de los estados que importó en la lista.</span><span class="sxs-lookup"><span data-stu-id="09b6e-112">You should see all the names of states you imported in the list.</span></span> <span data-ttu-id="09b6e-113">Observe que la opción **Mostrar solo nuevo** está seleccionada automáticamente después de la importación.</span><span class="sxs-lookup"><span data-stu-id="09b6e-113">Notice that **Show Only New** option is automatically selected after importing.</span></span> <span data-ttu-id="09b6e-114">Al importar valores y no ve los valores anteriores en la lista, es porque esta opción se habilita automáticamente después de la importación.</span><span class="sxs-lookup"><span data-stu-id="09b6e-114">When you import values and you don't see the old values in the list, it is because this option is automatically enabled after importing.</span></span> <span data-ttu-id="09b6e-115">Para ver todos los valores, desactive la casilla.</span><span class="sxs-lookup"><span data-stu-id="09b6e-115">To see all the values, clear the check box.</span></span> <span data-ttu-id="09b6e-116">Si importa de nuevo el mismo conjunto de valores, no se importa ninguno de los valores porque ya existen en el dominio.</span><span class="sxs-lookup"><span data-stu-id="09b6e-116">If you import the same set of values again, none of the values are imported as they already exist in the domain.</span></span>

     <span data-ttu-id="09b6e-117">![Mostrar solamente nueva casilla en valores de dominio](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-03.jpg "Mostrar solamente nueva casilla en valores de dominio")</span><span class="sxs-lookup"><span data-stu-id="09b6e-117">![Show Only New Checkbox on Domain Values](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-03.jpg "Show Only New Checkbox on Domain Values")</span></span>

## <a name="next-step"></a><span data-ttu-id="09b6e-118">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="09b6e-118">Next Step</span></span>
 [<span data-ttu-id="09b6e-119">Tarea 4: Configuración de reglas de dominio</span><span class="sxs-lookup"><span data-stu-id="09b6e-119">Task 4: Setting Domain Rules</span></span>](../../2014/tutorials/task-4-setting-domain-rules.md)


