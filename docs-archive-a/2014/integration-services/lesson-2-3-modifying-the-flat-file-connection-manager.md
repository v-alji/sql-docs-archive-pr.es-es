---
title: 'Paso 3: Modificar el Administrador de conexiones de archivos planos | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 459e3995-2116-4f15-aaa2-32f26113869c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b897f9412a8f2978ebe4137e3e79bf1d28c97844
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663580"
---
# <a name="step-3-modifying-the-flat-file-connection-manager"></a><span data-ttu-id="446e1-102">Paso 3: Modificación del Administrador de conexiones de archivos planos</span><span class="sxs-lookup"><span data-stu-id="446e1-102">Step 3: Modifying the Flat File Connection Manager</span></span>
  <span data-ttu-id="446e1-103">En esta tarea, modificará el administrador de conexiones de archivos planos que creó y configuró en la lección 1.</span><span class="sxs-lookup"><span data-stu-id="446e1-103">In this task, you will modify the Flat File connection manager that you created and configured in Lesson 1.</span></span> <span data-ttu-id="446e1-104">Cuando se creó inicialmente, el administrador de conexiones de archivos planos se configuró para cargar de forma estática un único archivo.</span><span class="sxs-lookup"><span data-stu-id="446e1-104">When originally created, the Flat File connection manager was configured to statically load a single file.</span></span> <span data-ttu-id="446e1-105">Para permitir que el Administrador de conexiones de archivos planos cargue archivos de forma iterativa, debe modificar la propiedad ConnectionString del administrador de conexiones de modo que acepte la variable `User:varFileName`, definida por el usuario, que contiene la ruta de acceso del archivo que se cargará en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="446e1-105">To enable the Flat File connection manager to iteratively load files, you must modify the ConnectionString property of the connection manager to accept the user-defined variable `User:varFileName`, which contains the path of the file to be loaded at run time.</span></span>  
  
 <span data-ttu-id="446e1-106">Al modificar el administrador de conexiones para que use la variable definida por el usuario `User::varFileName`para rellenar la propiedad ConnectionString del administrador de conexiones, este podrá conectarse a distintos archivos planos.</span><span class="sxs-lookup"><span data-stu-id="446e1-106">By modifying the connection manager to use the value of the user-defined variable, `User::varFileName`, to populate the ConnectionString property of the connection manager, the connection manager will be able to connect to different flat files.</span></span> <span data-ttu-id="446e1-107">En tiempo de ejecución, cada iteración del contenedor de bucles Foreach actualizará dinámicamente la variable `User::varFileName` .</span><span class="sxs-lookup"><span data-stu-id="446e1-107">At run time, each iteration of the Foreach Loop container will dynamically update the `User::varFileName` variable.</span></span> <span data-ttu-id="446e1-108">A su vez, actualizar esta variable da lugar a que el administrador de conexiones se conecte a un archivo plano distinto, y que la tarea de flujo de datos procese un conjunto de datos distinto.</span><span class="sxs-lookup"><span data-stu-id="446e1-108">Updating the variable, in turn, causes the connection manager to connect to a different flat file, and the data flow task to process a different set of data.</span></span>  
  
### <a name="to-configure-the-flat-file-connection-manager-to-use-a-variable-for-the-connection-string"></a><span data-ttu-id="446e1-109">Para configurar el Administrador de conexiones de archivos planos de modo que utilice una variable para la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="446e1-109">To configure the Flat File connection manager to use a variable for the connection string</span></span>  
  
1.  <span data-ttu-id="446e1-110">En el panel **Administradores de conexión** , haga clic con el botón derecho en **Sample Flat File Source Data**y, después, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="446e1-110">In the **Connection Managers** pane, right-click **Sample Flat File Source Data**, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="446e1-111">En el ventana Propiedades, para las **expresiones**, haga clic en la celda vacía y, a continuación, haga clic en el botón de puntos suspensivos **(...)**.</span><span class="sxs-lookup"><span data-stu-id="446e1-111">In the Properties window, for **Expressions**, click in the empty cell, and then click the ellipsis button **(...)**.</span></span>  
  
3.  <span data-ttu-id="446e1-112">En el cuadro de diálogo **Editor de expresiones de propiedad** , en la columna **propiedad** , escriba o seleccione `ConnectionString` .</span><span class="sxs-lookup"><span data-stu-id="446e1-112">In the **Property Expressions Editor** dialog box, in the **Property** column, type or select `ConnectionString`.</span></span>  
  
4.  <span data-ttu-id="446e1-113">En la columna **expresión** , haga clic en el botón de puntos suspensivos **(...)** para abrir el cuadro de diálogo **generador de expresiones** .</span><span class="sxs-lookup"><span data-stu-id="446e1-113">In the **Expression** column, click the ellipsis button **(...)** to open the **Expression Builder** dialog box.</span></span>  
  
5.  <span data-ttu-id="446e1-114">En el cuadro de diálogo **Generador de expresiones** , expanda el nodo **Variables** .</span><span class="sxs-lookup"><span data-stu-id="446e1-114">In the **Expression Builder** dialog box, expand the **Variables** node.</span></span>  
  
6.  <span data-ttu-id="446e1-115">Arrastre la variable **User:: varFileName**al cuadro **expresión** .</span><span class="sxs-lookup"><span data-stu-id="446e1-115">Drag the variable, **User::varFileName**, into the **Expression** box.</span></span>  
  
7.  <span data-ttu-id="446e1-116">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Generador de expresiones** .</span><span class="sxs-lookup"><span data-stu-id="446e1-116">Click **OK** to close the **Expression Builder** dialog box.</span></span>  
  
8.  <span data-ttu-id="446e1-117">Haga clic en **Aceptar** de nuevo para cerrar el cuadro de diálogo **Editor de expresiones de propiedad** .</span><span class="sxs-lookup"><span data-stu-id="446e1-117">Click **OK** again to close the **Property Expressions Editor** dialog box.</span></span>  
  
## <a name="next-lesson-task"></a><span data-ttu-id="446e1-118">Tarea de la siguiente lección</span><span class="sxs-lookup"><span data-stu-id="446e1-118">Next Lesson Task</span></span>  
 [<span data-ttu-id="446e1-119">Paso 4: Prueba del paquete del tutorial de la lección 2</span><span class="sxs-lookup"><span data-stu-id="446e1-119">Step 4: Testing the Lesson 2 Tutorial Package</span></span>](../integration-services/lesson-2-4-testing-the-lesson-2-tutorial-package.md)  
  
  
